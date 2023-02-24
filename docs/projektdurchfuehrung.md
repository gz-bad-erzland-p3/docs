# 3. Projektdurchführung

## 3.1 Anwendungsentwicklung
### 3.1.1 Landingpage
* <strong>Frontend</strong> </p>

Zuerst wurde eine Landingpage erstellt, über die man zum Online-Reservierungs-Tool gelangt. </p>

![LandingPage1](https://user-images.githubusercontent.com/72852065/215064333-7b0d153a-e669-4753-8e3d-858a1dc9a80e.png)

### 3.1.2 Arbeitsplatzkonfiguration
* <strong>Frontend</strong> </p>

<strong>Terminauswahl: </strong> </br>
Als erstes gelangt man zur Terminauswahl. Dort können der Zeitraum und die Start-, bzw. Endzeit ausgewählt werden.</p>

![grafik](https://user-images.githubusercontent.com/72852065/214051100-b5c7c2e9-46d4-47be-acec-2c0f92d36e3f.png) </p>

In der Terminauswahl muss die Mindest- und Maximalmietdauer beachtet werden. Wird die Mietdauer über-/unterschritten wird eine Meldung oben in der Ecke angezeigt. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214259770-c4acab74-c43d-495c-a5e6-a47b9f81e8ec.png) </p>

<strong>Arbeitsplatzauswahl:</strong></br>
Bei der Arbeitsplatzauswahl kann zwischen Einzel- oder Doppelarbeitsplatz gewählt werden. Optionen, welche ausgegraut werden sind aufgrund anderer Buchungen nicht mehr auswählbar. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214238131-8b658d7c-9440-4e11-8902-e0bc2cb3db5e.png) </p>

<strong>Konfiguration:</strong></br>
In der Konfiguration muss als erstes ausgewählt werden, ob ein eigenes Gerät mitgebracht werden soll oder nicht. Falls keins mitgebracht wird besteht die möglichkeit verschiedene Geräte zu konfigurieren. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214238195-7e06409d-9df7-4db1-ae86-0135241227f9.png) </p>

Wird "Ich brauche ein Gerät" gewählt, erweitert sich die Seite und es werden weitere Konfigurationsmöglichkeiten angezeigt. Nun kann zwischen Laptop, Desktop-PC und Barebone entschieden werden, eine Auswahl über das Betriebssystem getroffen und kostenlose Browser und Kommunikationsapplikationen ausgewählt werden. Zusätzlich können noch Bemerkungen bzw. Wünsche eingetragen werden. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214238626-97ce8523-f0ab-4072-9268-28c2ba0c282a.png)
![edited](https://user-images.githubusercontent.com/72852065/214238361-8646f52c-9586-41d5-8a88-c2136ac99559.png) </p>


* <strong>Backend</strong> </p>

### 3.1.3 Login
* <strong>Frontend</strong> </p>

<strong>Login:</strong> </br>
Der Login erfolgt über die Eingabe von E-Mail und Passwort. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214049304-9c73a252-9f38-41df-b893-3d81c5c005c1.png) </p>

<strong>Registrierung:</strong> </br>
Wenn noch kein Konto vorhanden ist, besteht die Möglichkeit sich zu registrieren. </p>
![grafik](https://user-images.githubusercontent.com/72852065/214049524-e6706c16-2728-41c2-8bfa-6ebdd5f9c855.png) </p>

* <strong>Backend</strong> </p>

Zur Speicherung der Login-Daten in der Firebase-Datenbank werden diese mittels HTTP- bzw- REST-Request an die REST-API (Firebase) übermittelt. Nach Abschluss der Registrierung wird eine Bestätigungsmail gesendet.</p>

![grafik](https://user-images.githubusercontent.com/72852065/214237752-5b196db3-43d0-4670-8496-c3400c6bacda.png)


### 3.1.4 Profilübersicht
* <strong>Frontend</strong> </p>

In der Profilübersicht werden die Daten des Kontos angezeigt. Hier ist es auch möglich das Passwort zurückzusetzen, die Adresse zu ändern oder das Konto zu löschen. </p>
![grafik](https://user-images.githubusercontent.com/72852065/214782181-fedd5236-6d55-4dd7-87ed-2f74f864b8d7.png)</p>

<strong>Buchungsübersicht</strong> </p>
In der Profilübersicht werden die Buchungen angezeigt und es besteht die Möglichkeit die Buchungen zu stonieren. </p>
![grafik](https://user-images.githubusercontent.com/72852065/214781607-3d67e685-4958-4602-b5ef-4288738b47c9.png) </p>


* <strong>Backend</strong> </p>


### 3.1.5 Reservierung
* <strong>Frontend</strong> </p>

Nach erfolgreicher Anmeldung/Reservierung wird der Interessent gebeten auf einen Button zu klicken. Hiermit ist der konfigurierte Arbeitsplatz für 20min reserviert und es werden die Zahlungsmethoden angezeigt. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214779369-5d4ffa31-72c1-42e4-8db4-a852c3bacd98.png) </p>

* <strong>Backend</strong> </p>

### 3.1.6 Dokumentation / Hilfe Seiten
* Für die Hilfe im Online-Reservierungs-Tool wird auf die Projektdokumentation verwiesen. </p>


### 3.1.7 Zahlungsseite
* <strong>Frontend</strong> </p>

Auf der Zahlungsseite kann zwischen 3 Zahlungsmethoden ausgewählt werden. </p>
![grafik](https://user-images.githubusercontent.com/72852065/214248987-1a45aa94-9278-404d-a085-1e85b7e6f61d.png) </p>

Nach Auswahl der Zahlungsmethode wird die Meldung "Buchung erfolgreich!" angezeigt. Damit ist die Reservierung abgeschlossen und der Arbeitsplatz für den gewünschten Zeitraum gebucht. </p>
![grafik](https://user-images.githubusercontent.com/72852065/214775635-1ef426d6-a9ed-4fd8-9093-bf22147b758b.png) </p>

* <strong>Backend</strong> </p>

<strong>Bestätigungsmail bei Buchungsabschluss</strong> </p>
![grafik](https://user-images.githubusercontent.com/72852065/214774778-02909203-8ef8-4a3b-ae73-fff404f295fa.png) </p>

### 3.1.9 Programmtests



### 3.1.10 aufgetretene Probleme/Hürden
* Landingpage

* Terminauswahl

* Arbeitsplatztypauswahl

* Arbeitsplatzkonfiguration

* Login

* Profilübersicht

* Zahlungsübersicht

* Backend


## 3.2 Systemintegration
### 3.2.1 Erstellung der Netzwerkübersich
![Netzwerkübersicht drawio](https://user-images.githubusercontent.com/98982162/220851687-25a2a5a9-d464-47c8-852d-fc5f98ef8a8c.png)


|                    |       Netzadresse      |     Subnetzmaske    |    Gateway   | DHCP |                  Verwendung                  |
|--------------------|:----------------------:|:-------------------:|:------------:|:----:|:--------------------------------------------:|
| Rotes Netzwerk     | 192.168.72.0 (Class C) | 255.255.255.0 (/24) | 192.168.72.2 | Nein |              Zugang zum Internet             |
| Orangenes Netzwerk |  192.168.1.0 (Class C) | 255.255.255.0 (/24) |  192.168.1.2 | Nein |          Demilitarisierte Zone (DMZ)         |
| Grünes Netzwerk    |  172.15.0.0 (Class B)  |  255.255.0.0 (/16)  |  172.15.0.2  |  Ja  |    Netz für interne/administrierte Geräte    |
| Blaues Netzwerk    |  172.16.0.0 (Class B)  |  255.255.0.0 (/16)  |  172.16.0.2  |  Ja  | Netz für externe/nicht administrierte Geräte |

Die Netze werden durch den integrierten DHCP des VMWare Players bereitgestellt. Die Konfiguration dieses DHCPs erfolgt über die "vmnetconfig"-Datei (siehe ./doku/vmnetconf/vmnetconfig)

<strong>Übersicht der Server</strong>

| Name                    |  Netz  | Verwendung                    |
|-------------------------|:------:|-------------------------------|
| lnx-ipfire (siehe 2)    |   Rot  | Firewall, DHCP, DNS-forwarder |
| lnx-dns (siehe 3)       |  Grün  | Interner DNS-Server           |
| lnx-docker (siehe 4)    | Orange | Docker Host (Webserver, CA)   |
| lnx-cmk (siehe 5)       |  Grün  | Monitoring des Webservers     |
| lnx-ansible-ctl (siehe) |  Grün  | Ansible Controle Node         |

<strong>Zugangsdaten</strong>

| Server          | Benutzer | Passwort |
|-----------------|:--------:|:--------:|
| lnx-ipfire      |   root   |   bgyb   |
|                 |   admin  |   bgyb   |
| lnx-dns         | secnetit |   bgyb   |
| lnx-docker      |   admin  |   Test!  |
| lnx-checkMK     |   root   |   bgyb   |
|                 | cmkadmin |   bgyb   |
| lnx-ansible-ctl |   root   | 01219dd. |
|                 |   admin  |   bgyb   |

### 3.2.2 Automatisierung des Webservers
Die Bereitstellung und Konfiguration des Webservers erfolgt über [Vagrant](https://www.vagrantup.com/) und [Ansible](https://www.ansible.com/).

#### 3.2.2.1 Bereitstellung durch Vagrant
Vagrant läuft mit Version 2.3.4 auf dem lokalen Windows Rechner.
Für die Bereitstellung der VM wird im Verzeichnis das Vagrantfile benötigt.
Die VM kann dann wie folgt gesatrtet werden:
```
C:\Vagrant\lnx-docker>vagrant up --no-provision
```
Dabei wird der ".vagrant"-Ordner im aktuellen Verzeichnis angelegt, in dem sich dann bspw. die VMDK-Dateien (virutelle Festplatte) der VM befinden.

Bei der Provisioniert wird unter anderem folgendes definiert:
- Name der Vagrantbox, auf der die VM gebaut wird [generic/centos9s](https://app.vagrantup.com/generic/boxes/centos9s)
- allgemeine Festlegungen der Ressourcen (2 GB vRAM, 2 vCPUs, 128 GB Festplatte (thin provisioned))
- Netzwerkadapter mit MAC-Adresse und virtuellem Netzwerk
Die restlichen Punkte können aus dem Vagrantfile selbst entnommen werden.

#### 3.2.2.2 Konfiguration durch Ansible

| Version        | ansible core 2.13.3 |
|----------------|---------------------------------------------------|
| Hardware       | CPU: 2 Kerne<br>RAM: 2GB<br>Hard Disk: 20GB       |
| IP-Adresse     | 172.15.254.252                                    |

Die Konfiguration des Webservers erfolg durch den Ansible Control Node (lnx-ansible-ctl). 

Der Ordner lnx-docker von Windows ist direkt über die VMware Workstation mit der VM geteilt und an /home/admin/vagrant gemountet.

Außerdem sind folgende Inhalte zusätzlich in das Arbeitsverzeichnis von Ansible gemappt:
![ansible_mapped](https://user-images.githubusercontent.com/98982162/220671954-8b499a8e-a6e1-459f-9f9b-998fc17a85b7.png "gemappte Ordner in /etc/ansible")

Die vorkonfigurierte "ssh-config"-Datei im lnx-docker-Ordner wird für die SSH-Verbindung zum Host verwendet.
In dieser wird unter anderem der zu verwendende Port und die Schlüssel für die Verbindung definiert.

##### 3.2.2.2.1 Collection
Die Collection-Liste kann mit 
```
ansible-galaxy collection install name.connection
``` 
erweitert werden. Der aktuelle Stand ist in dieser [Liste](https://github.com/gz-bad-erzland-p3/docs/files/10805292/ansible_collection.txt) einsehbar.

##### 3.2.2.2.2 Playbooks
Im Ordner .playbooks im Arbeitsverzeichnis sind alle relevanten Dateien zu finden.

Die Konfigurationsdatei "ansible.cfg" bilden dabei den Grundstock für die Nutzung von Ansible.

Die "hosts"-Datei enthält die Managed Nodes, welche mittels dem Control Node konfiguriert werden. Diese können in Gruppen und die einzelnen Hosts aufgeteilt werden.

Die "resolve"-Datei kann als interner DNS verstanden werden, der zusätzlich zum DNS im Netzwerk lokal Adressen auflösen kann.

Die "site.yml"-Datei ist das Playbook, in dem die Konfiguration des Webservers definiert ist.
Das Playbook kann von dem Control Node aus, aus richtigen Ordner wie folgt ausgeführt werden:
```
[admin@lnx-ansible-ctl lnx-docker]$ ansible-playbook --vault-password-file=vault_pass playbooks/site.yml
```
Die Datei, die das Passwort zum Vault enthält, muss seperat behandelt werden, damit die Sicherheit gewährleistet sein kann.

In dem Hauptplaybook wird im Teil der "pre_task", nach einer Abfrage des aktuellen Nutzers, der Standardnutzer, der durch Vagrant mitgelieft wird, auf einen eigenen Nutzer geändert.
Im Hauptteil werden dann allgemeine Einstellungen gesetzt und andere Playbooks importiert. 
In den "post_tasks" werden alle nicht benutzten Container und der mitgelieferte Standardnutzer von Vagrant entfernt.

Für genauere Informationen zu den verschiedenen Playbooks empfielt es sich, diese selbst zu analysieren.

Im Ordner group_vars, im Hauptverzeichnis, befinden sich im Ordner "all" die yaml-Dateien "centOS.yml" und "vault.yml".
In der centOS-Datei sind alle benötigten Variablen für das Playbook definiert.
Die vault-Datei ist direkt über das von Ansible mitgelieferte Tool "Ansible Vault" mit AES256 verschlüsselt. Diese Datei kann nur im Control Node auf der Kommandozeile bearbeitet werden. Eine genauere Anleitung kann [hier](https://www.digitalocean.com/community/tutorials/how-to-use-vault-to-protect-sensitive-ansible-data) gefunden werden.

Der Ordner "files" bietet einen zentralen Ort, an dem alle Dateien zu finden sind, die während der Konfiguration des Managed Nodes auf diesen übrtragen werden.

Im Ordner "units" befinden sich weitere Playbooks, die, wie weiter oben beschrieben, im Hauptplaybook inkludiert werden.

### 3.2.3 Monitoring
#### 3.2.3.1 Systemüberblick

| Version        | Open Monitoring Distribution Version 2.1.0p20.cre |
|----------------|---------------------------------------------------|
| Hardware       | CPU: 2 Kerne<br>RAM: 2GB<br>Hard Disk: 20GB       |
| IP-Adresse     | 172.15.0.10                                       |

#### 3.2.3.2 Installation
Die Installation erfolge anhand der von [CheckMK](https://checkmk.com/de/download?method=cmk&edition=cre&version=2.1.0p21&platform=redhat&os=el9&type=cmk) zur Verfügung gestellten Anleitung.
#### 3.2.3.3 Konfiguration
- Erstellung der Site "gzbe"
- interne Firewall angepasst:
```
[root@lnx-cmk ~]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: ens160
  sources:
  services: cockpit dhcpv6-client http https ssh
  ports: 80/tcp 443/tcp 8000/tcp
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
```
- internen Webserver den Zugriff auf Interface ens160 via SE-Linux erlauben
```
setsebool -P httpd_can_network_connect 1
```
- Service "httpd" starten und aktivieren
- Anpassung der IPFire-Firewall (siehe [Firewall-Regeln](#325131-Firewall-Regeln))

#### 3.2.3.4 Agentinstallation
Die Überwachung von Servern läuft über einen mitgelieferten Agent, welcher auch auf dem CheckMK-Server selbst installiert wurde.
Es gibt zwei Möglichkeiten, den Agent zu finden:

- lokal: /opt/omd/versions/2.1.0p20.cre/share/check_mk/agents/
- über die Webansicht: http://172.15.254.253/gzbe/check_mk/agents/ 

Eine konkrete Anleitung für die Agentinstallation und Registrierung wird auch von [CheckMK](https://docs.checkmk.com/latest/de/agent_deployment.html) zur Verfügung gestellt.

Die benötigten Ports zur Kommunikation sind in der [Firewall](#32513-firewall-regeln) in der "check_mk-agent-group"-Gruppe konfiguriert.

### 3.2.4 Automatische Aktualisierung der Website



### 3.2.5 Firewall
#### 3.2.5.1 Systemüberblick

| Version        | IP-Fire Ver. 2.27 x86_64 - Core 172                                                                                                     |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Hardware       | CPU: 2 Kerne<br>RAM: 2GB<br>Hard Disk: 20GB                                                                                             |
| IP-Adresse(n)  | Rotes Interface: 192.168.72.254/24<br>Orangenes Interface: 192.168.1.2/24<br>Grünes Interface: 172.15.0.2/16<br>Blaues Interface: 172.16.0.2/16 |

#### 3.2.5.1 Konfiguration
##### 3.2.5.1.1 Allgemein

- Installation der virtuell Maschine durch das bereitgestellte Image von IPFire
- Einrichtung der Benuzter "admin" und "root" 
- Zuweisung der Netzwerkadapter und deren IP-Adressen (siehe [Netzwerkübersicht](#321-erstellung-der-netzwerkübersich))
- weitere Konfiguration über Web-User-Interface (WUI), zu erreichen über grünen Netzwerkadapter und Port 444 (https://172.15.0.2:444)
- SSH-Zugriff über "System" &rarr; "SSH Access" aktivieren 

##### 3.2.5.1.1 DHCP
In den blauen und grünen Netzwerksegmenten ist die Firewall gleichzeitig der DHCP-Server.
- Anpassung unter "Network" &rarr; "DHCP Server" wie folgt:

|                    | Grünes Interface             | Blaues Interface             |
|--------------------|------------------------------|------------------------------|
| Enabled            |              yes             |              yes             |
| Netzwerk           |         172.15.0.0/16        |         172.16.0.0/16        |
| Start-/End-Address |  172.15.1.0 / 172.15.254.254 |  172.16.1.0 / 172.16.254.254 |
| Min/Max Lease Time |        60min / 120min        |        60min / 120min        |
| DNS-Server         | 172.15.254.254<br>172.15.0.2 | 172.15.254.254<br>172.16.0.2 |

In beiden Netzen bleibt die Null im dritten Oktett für statische IP-Adressen frei. 
Daher stehen sowohl die 172.15.0.1 bis 172.15.0.254 im grünen Netz und 172.16.0.1 bis 172.16.0.254 im blauen Netz für statische Adressen zur Verfügung.

Als primärer DNS-server ist der lnx-dns (siehe [Einrichtung DNS-Server](#326-einrichtung-des-dns-servers)) in beiden Netzen eingetragen.
Als sekundärer DNS-Server ist die Firewall selbst eingetragen (siehe [DNS](#32512-dns)).

Die folgende Tabelle zeigt die aktuell reservierten Adressen:

| Name                           | IP-Adresse     |
|--------------------------------|----------------|
| DNS-Server (lnx-dns)           | 172.15.254.254 |
| CheckMK-Server (lnx-cmk)       | 172.15.254.253 |
| Control Node (lnx-ansible-ctl) | 172.15.254.252 |

##### 3.2.5.1.2 DNS
- als interner DNS-Server wird Unbound verwendet
- Konfiguration erfolgt über WUI oder Konfigurationsdatei
- Firewall dient in aktueller Situation als DNS-Weiterleitung (leitet Anfragen an Kserver weiter)
- Schema der DNS-Anfragen:

![firewall-dns](https://user-images.githubusercontent.com/98982162/220060622-c034e4ec-bb82-4529-a450-eecd72a0bf7b.png)

###### 3.2.5.1.2.1 Konfiguration über WUI
- Konfiguration über "Network" &rarr; " "Domain Name System"
- aktuell ist der Kserver über unbound.conf eingerichtet &rarr; wird **nicht** in WUI angezeigt

###### 3.2.5.1.2.2 Konfiguration über unbound.conf
- Kserver unterstützt kein DNSSEC &rarr; muss deaktiviert werden
- unbound.conf zu finden unter "/etc/unbound/unbound.conf"
- "harden-dnssec-stripped" besonders zu beachten!
```
        # Hardening Options
        harden-large-queries: yes
        harden-referral-path: yes
        #harden-dnssec-stripped: yes
```

- DNS-Weiterleitung über die Option "forward-zone" wie folgt konfigurieren:
```
forward-zone:
                name: "."
                forward-addr: 10.1.1.2 #add kserver as dns resolver
```

##### 3.2.5.1.2 Proxy
- aktuell konfigurierter Proxy nur in Schulumgebung relevant
- Anpassungen unter "Network" &rarr; "Web Proxy" zu finden 
- Schulproxy (10.254.5.100:3128) als Upstream Proxy Server einrichten 

##### 3.2.5.1.3 Firewall-Regeln
###### 3.2.5.1.3.1 Firewall-Gruppen
- Konfiguration unter "Firewall" &rarr; "Firewall Groups"
- Möglichkeit, Protokolle oder Clients zu Gruppen zusammenfassen
- folgende Servicegruppe gibt es aktuell: 

check_mk-agent-group
| Name                    | Port | Protocol |
|-------------------------|------|----------|
| check_mk-agent          | 6556 | TCP      |
| check_mk-agent-register | 8000 | TCP      |

dns
| Name      | Port | Protocol |
|-----------|------|----------|
| DNS (TCP) | 53   | TCP      |
| DNS (UDP) | 53   | UDP      |

###### 3.2.5.1.3.1 Firewall-Regeln
- Konfiguration unter "Firewall" &rarr; "Firewall Rules"

|       Protocol       |     Source     | Log |   Destination  | Handling |                    Description                   |
|:--------------------:|:--------------:|:---:|:--------------:|:--------:|:------------------------------------------------:|
|         ICMP         |       Any      | [ ] |       Any      |  accept  |                    ping global                   |
|          dns         |      BLUE      | [X] | 172.15.254.254 |  accept  |          blue pinhole for DNS #internal#         |
|          dns         |     ORANGE     | [X] |       RED      |  accept  |           orange dns access #outgoing#           |
|          dns         |  192.168.1.10  | [X] | 172.15.254.254 |  accept  |         allow internal dns for lnx-docker        |
|          ssh         | 172.15.254.254 | [X] |  192.168.1.10  |  accept  | ssh access from lnx-ansible-ctl<br>to lnx-docker |
|         snmp         |      GREEN     | [ ] |       Any      |  accept  |              snmp access to firewall             |
|         https        |  192.168.1.10  | [ ] |       Any      |  accept  |               internal https access              |
| check_mk-agent-group |  192.168.1.10  | [X] | 172.15.254.254 |  accept  |        access for cmk-agent from webserver       |

##### 3.2.5.1.3 Zugang Blaues Netzwerk
- Konfiguration unter "Firewall" &rarr; "Blue Access"
- blaues Netzwerk für nicht adminsitrierte Geräte &rarr; Zugriff auf andere Netze & WUI muss eingeschränkt werden
- Kommunikation zwischen blauem und anderen Netzen grundsätzlich blockiert 
- rotes Netz von dieser Blockierung ausgeschlossen, wegen Internetzugang

###### 3.2.5.1.3.1 MAC-Address filtering
- standardmäßig wird MAC-Address filtering (MAf) durch IPFire aktiviert
- blockiert Internetzugang von Clients im blauen Netzwerk
- Netzadresse des blauen Netzes als Gerät hinzufügen
![MAf-blue-network](https://user-images.githubusercontent.com/98982162/220071669-7d3a7cbf-bb20-431e-a8de-9ae0eaa2f00a.png)

###### 3.2.5.1.3.2 WUI Zugriff
- Zugriff vom blauen Netz auf WUI der Firewall standardmäßig freigeschalten
- Anpassung der lokalen Firewall unter "/etc/sysconfig/firewall.local"
- Zugriff kann wie folgt über blaues und grünes Netzwerk deaktiviert werden, wenn die Quelladresse aus dem blauen Netz kommt

![wui-zugriff-von-blau](https://user-images.githubusercontent.com/98982162/220072488-30867dfb-2315-409d-9bd7-b232e28d869d.png)

### 3.2.6 Einrichtung des DNS Servers
#### 3.2.6.1 Systemüberblick

| Version        | Dnsmasq Ver. 2.85                         |
|----------------|-------------------------------------------|
| Hardware       | CPU: 1 Kern<br>RAM: 1GB<br>Hard Disk: 20GB|
| IP-Adresse     | 172.15.254.254/16                         |

#### 3.2.6.2 Konfiguration
##### 3.2.6.2.1 Dnsmasq
- Konfiguration über "/etc/dnsmasq.conf"
- aktueller Stand wie folg:

| Zeile   | Syntax                                                    | Nutzen                                                                                   |
|---------|-----------------------------------------------------------|------------------------------------------------------------------------------------------|
| 55-58   | no-resolv                                                 | Verhindert das dnsmasq aus der resolv.conf Datei liest                                   |
| 64-67   | Server=172.15.0.2                                         | Hinzufügen des DNS-Servers für die Auflösung von unbekannten Adressen |
| 112-115 | listen-address=127.0.0.1<br>listen-address=172.15.254.254 | Gibt die Interfaces vor, an denen nach DNS-Anfragen gelauscht werden soll                 |

##### 3.2.6.2.2 DNS-Einträge
- Konfiguration über "/etc/hosts"
- aktueller Stand wie folgt:

![dns-hosts](https://user-images.githubusercontent.com/98982162/220074912-e47a16c2-54e5-4733-a2b8-ef001e8b3c69.png)



## 3.3 Projektpräsentation
### 3.3.1 Vorbereitung
### 3.3.2 Präsentation / Kundenübergabe
