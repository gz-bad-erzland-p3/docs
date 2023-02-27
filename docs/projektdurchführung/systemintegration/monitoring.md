# Monitoring
## Systemüberblick

| Version        | Open Monitoring Distribution Version 2.1.0p20.cre |
|----------------|---------------------------------------------------|
| Hardware       | CPU: 2 Kerne<br>RAM: 2GB<br>Hard Disk: 20GB       |
| IP-Adresse     | 172.15.0.10                                       |

## Installation
Die Installation erfolge anhand der von [CheckMK](https://checkmk.com/de/download?method=cmk&edition=cre&version=2.1.0p21&platform=redhat&os=el9&type=cmk) zur Verfügung gestellten Anleitung.
## Konfiguration
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

## Agentinstallation
Die Überwachung von Servern läuft über einen mitgelieferten Agent, welcher auch auf dem CheckMK-Server selbst installiert wurde.
Es gibt zwei Möglichkeiten, den Agent zu finden:

- lokal: /opt/omd/versions/2.1.0p20.cre/share/check_mk/agents/
- über die Webansicht: http://172.15.254.253/gzbe/check_mk/agents/ 

Eine konkrete Anleitung für die Agentinstallation und Registrierung wird auch von [CheckMK](https://docs.checkmk.com/latest/de/agent_deployment.html) zur Verfügung gestellt.

Die benötigten Ports zur Kommunikation sind in der [Firewall](#32513-firewall-regeln) in der "check_mk-agent-group"-Gruppe konfiguriert.