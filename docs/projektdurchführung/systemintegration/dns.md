# Einrichtung des DNS Servers
## Systemüberblick

| Version        | Dnsmasq Ver. 2.85                         |
|----------------|-------------------------------------------|
| Hardware       | CPU: 1 Kern<br>RAM: 1GB<br>Hard Disk: 20GB|
| IP-Adresse     | 172.15.254.254/16                         |

## Konfiguration
### Dnsmasq
- Konfiguration über "/etc/dnsmasq.conf"
- aktueller Stand wie folg:

| Zeile   | Syntax                                                    | Nutzen                                                                                   |
|---------|-----------------------------------------------------------|------------------------------------------------------------------------------------------|
| 55-58   | no-resolv                                                 | Verhindert, dass dnsmasq aus der resolv.conf Datei liest                                   |
| 64-67   | Server=172.15.0.2                                         | Hinzufügen des DNS-Servers für die Auflösung von unbekannten Adressen |
| 112-115 | listen-address=127.0.0.1<br>listen-address=172.15.254.254 | Gibt die Interfaces vor, an denen nach DNS-Anfragen gelauscht werden soll                 |

### DNS-Einträge
- Konfiguration über "/etc/hosts"
- aktueller Stand wie folgt:

![dns-hosts](https://user-images.githubusercontent.com/98982162/220074912-e47a16c2-54e5-4733-a2b8-ef001e8b3c69.png)