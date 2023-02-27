# Firewall
## Systemüberblick

| Version        | IP-Fire Ver. 2.27 x86_64 - Core 172                                                                                                     |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Hardware       | CPU: 2 Kerne<br>RAM: 2GB<br>Hard Disk: 20GB                                                                                             |
| IP-Adresse(n)  | Rotes Interface: 192.168.72.254/24<br>Orangenes Interface: 192.168.1.2/24<br>Grünes Interface: 172.15.0.2/16<br>Blaues Interface: 172.16.0.2/16 |

## Konfiguration
### Allgemein

- Installation der virtuell Maschine durch das bereitgestellte Image von IPFire
- Einrichtung der Benuzter "admin" und "root" 
- Zuweisung der Netzwerkadapter und deren IP-Adressen (siehe [Netzwerkübersicht](#321-erstellung-der-netzwerkübersich))
- weitere Konfiguration über Web-User-Interface (WUI), zu erreichen über grünen Netzwerkadapter und Port 444 (https://172.15.0.2:444)
- SSH-Zugriff über "System" &rarr; "SSH Access" aktivieren 

### DHCP
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

### DNS
- als interner DNS-Server wird Unbound verwendet
- Konfiguration erfolgt über WUI oder Konfigurationsdatei
- Firewall dient in aktueller Situation als DNS-Weiterleitung (leitet Anfragen an Kserver weiter)
- Schema der DNS-Anfragen:

![firewall-dns](https://user-images.githubusercontent.com/98982162/220060622-c034e4ec-bb82-4529-a450-eecd72a0bf7b.png)

#### Konfiguration über WUI
- Konfiguration über "Network" &rarr; " "Domain Name System"
- aktuell ist der Kserver über unbound.conf eingerichtet &rarr; wird **nicht** in WUI angezeigt

#### Konfiguration über unbound.conf
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

### Proxy
- aktuell konfigurierter Proxy nur in Schulumgebung relevant
- Anpassungen unter "Network" &rarr; "Web Proxy" zu finden 
- Schulproxy (10.254.5.100:3128) als Upstream Proxy Server einrichten 

### Firewall-Regeln
#### Firewall-Gruppen
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

#### Firewall-Regeln
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

###  Zugang Blaues Netzwerk
- Konfiguration unter "Firewall" &rarr; "Blue Access"
- blaues Netzwerk für nicht adminsitrierte Geräte &rarr; Zugriff auf andere Netze & WUI muss eingeschränkt werden
- Kommunikation zwischen blauem und anderen Netzen grundsätzlich blockiert 
- rotes Netz von dieser Blockierung ausgeschlossen, wegen Internetzugang

#### MAC-Address filtering
- standardmäßig wird MAC-Address filtering (MAf) durch IPFire aktiviert
- blockiert Internetzugang von Clients im blauen Netzwerk
- Netzadresse des blauen Netzes als Gerät hinzufügen
![MAf-blue-network](https://user-images.githubusercontent.com/98982162/220071669-7d3a7cbf-bb20-431e-a8de-9ae0eaa2f00a.png)

#### WUI Zugriff
- Zugriff vom blauen Netz auf WUI der Firewall standardmäßig freigeschalten
- Anpassung der lokalen Firewall unter "/etc/sysconfig/firewall.local"
- Zugriff kann wie folgt über blaues und grünes Netzwerk deaktiviert werden, wenn die Quelladresse aus dem blauen Netz kommt

![wui-zugriff-von-blau](https://user-images.githubusercontent.com/98982162/220072488-30867dfb-2315-409d-9bd7-b232e28d869d.png)