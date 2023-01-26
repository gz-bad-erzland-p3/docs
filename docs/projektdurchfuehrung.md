# 3. Projektdurchführung

## 3.1 Anwendungsentwicklung
### 3.1.1 Landingpage
* <strong>Frontend</strong> </p>

Zuerst wurde eine Landingpage erstellt, über die man zum Online-Reservierungs-Tool gelangt. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214048801-516693a6-b6cb-4e47-a470-0658e38f95d4.png)

### 3.1.2 Arbeitsplatzkonfiguration
* <strong>Frontend</strong> </p>

<strong>Terminauswahl: </strong> </br>
Als erstes gelangt man zur Terminauswahl. Dort können der Zeitraum und die Start-, bzw. Eindzeit ausgewählt werden.</p>

![grafik](https://user-images.githubusercontent.com/72852065/214051100-b5c7c2e9-46d4-47be-acec-2c0f92d36e3f.png) </p>

<strong>Arbeitsplatzauswahl:</strong></br>
Bei der Arbeitsplatzauswahl kann zwischen Einzel- oder Doppelarbeitsplatz gewählt werden. Optionen, welche ausgegraut werden sind aufgrund anderer Buchungen nicht mehr auswählbar. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214238131-8b658d7c-9440-4e11-8902-e0bc2cb3db5e.png) </p>

<strong>Konfiguration:</strong></br>
In der Konfiguration muss als erstes ausgewählt werden, ob ein eigenes Gerät mitgebracht werden soll oder nicht. Falls keins mitgebracht wird besteht die möglichkeit verschiedene Geräte zu konfigurieren.

![grafik](https://user-images.githubusercontent.com/72852065/214238195-7e06409d-9df7-4db1-ae86-0135241227f9.png) </p>

Wird "Ich brauche ein Gerät" gewählt, erweitert sich die Seite und es werden weitere Konfigurationsmöglichkeiten angezeigt. Nun kann zwischen Laptop, Desktop-PC und Barebone entschieden werden, eine Auswahl über das Betriebssystem getroffen und kostenlose Browser und Kommunikationsapplikationen ausgewählt werden. Zusätzlich können noch Bemerkungen bzw. Wünsche eingetragen werden. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214238626-97ce8523-f0ab-4072-9268-28c2ba0c282a.png)
![edited](https://user-images.githubusercontent.com/72852065/214238361-8646f52c-9586-41d5-8a88-c2136ac99559.png) </p>


* <strong>Backend</strong> </p>

<strong>Terminauswahl: </strong> </br>
In der Terminauswahl muss die Mindest- und Maximalmietdauer beachtet werden. Wird die Mietdauer über-/unterschritten wird eine Meldung oben in der Ecke angezeigt. </p>

![grafik](https://user-images.githubusercontent.com/72852065/214259770-c4acab74-c43d-495c-a5e6-a47b9f81e8ec.png) </p>

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

In der Profilübersicht werden die Daten des Kontos angezeigt. Hier ist es auch möglich das Passwort zurückzusetzen, die Adresse zu ändern oder das Konto zu löschen.
![grafik](https://user-images.githubusercontent.com/72852065/214776870-31d778bb-c75c-4284-b5ef-e76be88cb5c5.png) </p>

* <strong>Backend</strong> </p>


### 3.1.5 Reservierung
* <strong>Frontend</strong> </p>

Nach erfolgreicher Anmeldung/Reservierung wird der Interessent gebeten auf einen Button zu klicken. Hiermit ist der konfigurierte Arbeitsplatz für 20min reserviert und es werden die Zahlungsmethoden angezeigt.


* <strong>Backend</strong> </p>

### 3.1.6 Dokumentation / Hilfe Seiten
* <strong>Frontend</strong> </p>
* <strong>Backend</strong> </p>
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
* <strong>Frontend</strong> </p>
* <strong>Backend</strong> </p>

## 3.2 Systemintegration
### 3.2.1 Automatisierung des Webservers
### 3.2.2 Monitoring
### 3.2.3 Automatische Aktualisierung der Website
### 3.2.4 Einrichtung der Firewall
### 3.2.5 Einrichtung des DNS Servers
### 3.2.6 Erstellung des Netzwerkplans
![Netzwerkübersicht](https://user-images.githubusercontent.com/72852065/212857433-0980954b-f5f4-4e52-86f0-db2f07fc1af8.png)

## 3.3 Projektpräsentation
### 3.3.1 Vorbereitung
### 3.3.2 Präsentation / Kundenübergabe
