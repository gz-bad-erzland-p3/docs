# Erstellung der Netzwerkübersicht

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
