# Automatisierung des Webservers
Die Bereitstellung und Konfiguration des Webservers erfolgt über [Vagrant](https://www.vagrantup.com/) und [Ansible](https://www.ansible.com/).

## Bereitstellung durch Vagrant
Vagrant läuft mit Version 2.3.4 auf dem lokalen Windows Rechner.
Für die Bereitstellung der VM wird im Verzeichnis das Vagrantfile benötigt.
Die VM kann dann wie folgt gestartet werden:
```
C:\Vagrant\lnx-docker>vagrant up --no-provision
```
Dabei wird der ".vagrant"-Ordner im aktuellen Verzeichnis angelegt, in dem sich dann bspw. die VMDK-Dateien (virtuelle Festplatte) der VM befinden.

Bei der Provisioniert wird unter anderem folgendes definiert:
- Name der Vagrantbox, auf der die VM gebaut wird [generic/centos9s](https://app.vagrantup.com/generic/boxes/centos9s)
- allgemeine Festlegungen der Ressourcen (2 GB vRAM, 2 vCPUs, 128 GB Festplatte (thin provisioned))
- Netzwerkadapter mit MAC-Adresse und virtuellem Netzwerk
Die restlichen Punkte können aus dem Vagrantfile selbst entnommen werden.

## Konfiguration durch Ansible

| Version        | ansible core 2.13.3 |
|----------------|---------------------------------------------------|
| Hardware       | CPU: 2 Kerne<br>RAM: 2GB<br>Hard Disk: 20GB       |
| IP-Adresse     | 172.15.254.252                                    |

Die Konfiguration des Webservers rfolgt durch den Ansible Control Node (lnx-ansible-ctl). 

Der Ordner lnx-docker von Windows ist direkt über die VMware Workstation mit der VM geteilt und an /home/admin/vagrant gemountet.

Außerdem sind folgende Inhalte zusätzlich in das Arbeitsverzeichnis von Ansible gemappt:
![ansible_mapped](https://user-images.githubusercontent.com/98982162/220671954-8b499a8e-a6e1-459f-9f9b-998fc17a85b7.png "gemappte Ordner in /etc/ansible")

Die vorkonfigurierte "ssh-config"-Datei im lnx-docker-Ordner wird für die SSH-Verbindung zum Host verwendet.
In dieser wird unter anderem der zu verwendende Port und die Schlüssel für die Verbindung definiert.

### Collection
Die Collection-Liste kann mit 
```
ansible-galaxy collection install name.connection
``` 
erweitert werden. Der aktuelle Stand ist in dieser [Liste](https://github.com/gz-bad-erzland-p3/docs/files/10805292/ansible_collection.txt) einsehbar.

### Playbooks
Im Ordner .playbooks im Arbeitsverzeichnis sind alle relevanten Dateien zu finden.

Die Konfigurationsdatei "ansible.cfg" bilden dabei den Grundstock für die Nutzung von Ansible.

Die "hosts"-Datei enthält die Managed Nodes, welche mittels dem Control Node konfiguriert werden. Diese können in Gruppen und die einzelnen Hosts aufgeteilt werden.

Die "resolve"-Datei kann als interner DNS verstanden werden, der zusätzlich zum DNS im Netzwerk lokal Adressen auflösen kann.

Die "site.yml"-Datei ist das Playbook, in dem die Konfiguration des Webservers definiert ist.
Das Playbook kann von dem Control Node aus, aus richtigen Ordner wie folgt ausgeführt werden:
```
[admin@lnx-ansible-ctl lnx-docker]$ ansible-playbook --vault-password-file=vault_pass playbooks/site.yml
```
Die Datei, die das Passwort zum Vault enthält, muss separat behandelt werden, damit die Sicherheit gewährleistet sein kann.

In dem Hauptplaybook wird im Teil der "pre_task", nach einer Abfrage des aktuellen Nutzers, der Standardnutzer, der durch Vagrant mitgeliefert wird, auf einen eigenen Nutzer geändert.
Im Hauptteil werden dann allgemeine Einstellungen gesetzt und andere Playbooks importiert. 
In den "post_tasks" werden alle nicht benutzten Container und der mitgelieferte Standardnutzer von Vagrant entfernt.

Für genauere Informationen zu den verschiedenen Playbooks empfiehlt es sich, diese selbst zu analysieren.

Im Ordner group_vars, im Hauptverzeichnis, befinden sich im Ordner "all" die yaml-Dateien "centOS.yml" und "vault.yml".
In der centOS-Datei sind alle benötigten Variablen für das Playbook definiert.
Die vault-Datei ist direkt über das von Ansible mitgelieferte Tool "Ansible Vault" mit AES256 verschlüsselt. Diese Datei kann nur im Control Node auf der Kommandozeile bearbeitet werden. Eine genauere Anleitung kann [hier](https://www.digitalocean.com/community/tutorials/how-to-use-vault-to-protect-sensitive-ansible-data) gefunden werden.

Der Ordner "files" bietet einen zentralen Ort, an dem alle Dateien zu finden sind, die während der Konfiguration des Managed Nodes auf diesen übertragen werden.

Im Ordner "units" befinden sich weitere Playbooks, die, wie weiter oben beschrieben, im Hauptplaybook inkludiert werden.

**check-git-service.yml**
- Skript zur automatischen Aktualisierung der Webseite wird bereitgestellt
- systemd.timer wird konfiguriert
- mehr Informationen: siehe #324-automatische-aktualisierung-der-website

**firewalld.yml**
- Firewalld wird angepasst
  - Ports und Services werden freigeschalten 

**install-podman.yml**
- Podman Paket wird installiert

**install-repository.yml**
- Repositorys werden installiert

**install-req-packages.yml**
- benötigte Pakete werden installiert

**remove-nextjs-systemd.yml**
- systemd container-nextjs-instance wird entfernt

**setup-cmk-agent.yml**
- CheckMK Agent wird vom Server heruntergeladen und anschließend installiert
- Registrierung am Server erfolgt

**setup-nextjs.yml**
- Podman Container mit Webseite wird im Usercontext gestartet 
- Image wird durch [Dockerfile](https://github.com/gz-bad-erzland-p3/projektarbeit/blob/main/Dockerfile) definiert
- systemd-Service wird generiert 

**setup-nextjs-service.yml**
- generierter Container Service wird aktiviert

**setup-nginx.yml**
- Podman Container mit Nginx wird im Usercontext gestartet
- benötigte Zertifikatsdatei werden kopiert
- systemd-Service wird generiert

**setup-nginx-service.yml**
- generierter Container Service wird aktiviert

**setup-pod.yml**
- der Pod "service_pod" wird entfernt und neu generiert
- hier werden auch die benötigten Ports exposed

**setup-proxy.yml**
- mittels ICMP-Ping wird geprüft, ob der Schulproxy erreichbar ist
- sollte dieser Erreichbar sein, wird auf dem Control Node der Proxy eingerichtet

**setup-ssl-cert.yml**
- die Zertifikate für die Webseite wird über einen Container erstellt
- Podman Container zur Zertifikatserstellung wird mit allen benötigten Parametern für das Zertifikat ausgestellt

**setup-user.yml**
- Nutzer wird erstellt und in "admin"- und "wheel"-Gruppen aufgenommen
- die Zertifikate zur Anmeldung über SSH werden verschoben

Die hier dargestellte Reihenfolge der Playbooks ist so nicht im Hauptplaybook inkludiert. Die tatsächliche Reihenfolge ist aus dem Playbook "site.yml" zu entnehmen.

Sowohl der Nginx-, als auch der Nextjs-Container laufen im "service_pod"-Pod. Durch diesen werden die Ports 3000 und 8443 exposed.
Der Port 8443 wird vom Nginx-Container verwendet, um die Webseite nach außen über eine verschlüsselte TSL-Verbindung bereitzustellen.
Der Port 3000 wird für die Kommunikation zwischen den beiden Containern. Diese Kommunikation läuft unverschlüsselt innerhalb des Pods. Der Nginx-Container dient dabei als Upstream Server.
