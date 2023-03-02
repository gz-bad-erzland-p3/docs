# Frontend

Das Frontend der Projektarbeit bezieht sich auf alle Benutzeroberflächen der Anwendung sowie der grafischen Gestaltung der Startseite (zu engl. Landingpage) 

!!! info "Projektcode"

    Der gesamte Projektcode steht Open-Source auf [GitHub](https://github.com/gz-bad-erzland-p3/projektarbeit) zu verfügung 

## Überblick
### Schwerpunkte UI Design

Minimalistische UI Look im Corporate Design von Bad Erzland

- Modern
- Übersichtlich
- UX Opimiert

--> reduziert Fehlerquellen

### Technologien

| Technologie | Vorteil |
| ----------- | ------- |
| NextJS 12 | Bildoptimierung, einfaches Routing zwischen Seiten, Serverside Rendering |
| React | Wiederverwendbare Komponenten, verbesserte Ladezeiten, einfache Wartun, ... |
| TailwindCSS | Schnelle & Unkomplizierte Gestaltung mit vordefinierten Klassen |
| PostCSS | verbesserte Ladezeiten durch CSS optimierung |

## Landingpage

Zuerst wurde eine Landingpage erstellt, über die man zum Online-Reservierungs-Tool gelangt. </p>

![grafik](https://user-images.githubusercontent.com/72852065/221809334-0a52dd26-36a9-4bdb-b3f8-db82b9ada757.png)

## Buchungsseite
### Wizard

Die Buchungsseite ist das Kernstück des Projektes. Sie ist die zentrale Anlaufstelle, in welcher Benutzer eine Buchung tätigen. Die Buchungsseite ist so gestaltet, dass sie leicht zu navigieren ist und die Benutzererfahrung optimiert.

Um sicherzustellen, dass der Buchungsprozess reibungslos abläuft und Benutzer nicht von komplizierten Formularen oder verwirrenden Optionen abgeschreckt werden, wird ein "Wizard" eingesetzt. Der Wizard führt den Benutzer Schritt für Schritt durch den Buchungsprozess und stellt sicher, dass alle notwendigen Informationen korrekt erfasst werden. Durch diese Methode wird die Fehlerquote reduziert, da jeder Schritt auf Fehler geprüft wird, bevor der Benutzer zum nächsten Schritt gelangen kann.

Single-Page-Anwendungen sind eine häufige Art von Buchungsseite, da sie eine schnelle und nahtlose Benutzererfahrung bieten. Die gesamte Buchung wird auf einer einzigen Seite ausgeführt, ohne dass der Benutzer die Seite neu laden oder auf verschiedene Seiten navigieren muss. Dadurch wird die Navigation erleichtert und die Benutzerfreundlichkeit verbessert.

#### Terminauswahl
Als erstes gelangt man zur Terminauswahl. Dort können der Zeitraum und die Start-, bzw. Endzeit ausgewählt werden.

![grafik](https://user-images.githubusercontent.com/72852065/222348501-612855e5-9ecb-4fb4-b663-a2907bdcc4cd.png)

In der Terminauswahl muss die Mindest- und Maximalmietdauer beachtet werden. Wird die Mietdauer über-/unterschritten wird eine Meldung oben in der Ecke angezeigt.

![grafik](https://user-images.githubusercontent.com/72852065/222348869-5689fbbf-9f36-4fe4-aa25-2dbae1deec15.png)

#### Arbeitsplatzauswahl
Bei der Arbeitsplatzauswahl kann zwischen Einzel- oder Doppelarbeitsplatz gewählt werden. Optionen, welche ausgegraut werden sind aufgrund anderer Buchungen nicht mehr auswählbar.

![grafik](https://user-images.githubusercontent.com/72852065/222349232-4a37b591-3b46-4521-82dc-732e6574490a.png)

#### Konfiguration
In der Konfiguration muss als erstes ausgewählt werden, ob ein eigenes Gerät mitgebracht werden soll oder nicht. Falls keins mitgebracht wird besteht die möglichkeit verschiedene Geräte zu konfigurieren.

![grafik](https://user-images.githubusercontent.com/72852065/222349408-0ef1b596-2db1-437f-8e73-1df39cc55c61.png)

Wird "Ich brauche ein Gerät" gewählt, erweitert sich die Seite und es werden weitere Konfigurationsmöglichkeiten angezeigt. Nun kann zwischen Laptop, Desktop-PC und Barebone entschieden werden, eine Auswahl über das Betriebssystem getroffen und kostenlose Browser und Kommunikationsapplikationen ausgewählt werden. Zusätzlich können noch Bemerkungen bzw. Wünsche eingetragen werden.

![grafik](https://user-images.githubusercontent.com/72852065/222349812-e4af31f3-ea4d-4b62-8cf5-08d92e79ccc8.png)
![Unbenannt](https://user-images.githubusercontent.com/72852065/222350215-a7460d27-e64d-4120-8744-7596a1a3b547.png)

#### Reservierung

Nach erfolgreicher Anmeldung/Reservierung wird der Interessent gebeten auf einen Button zu klicken. Hiermit ist der konfigurierte Arbeitsplatz für 20min reserviert und es werden die Zahlungsmethoden angezeigt.

![grafik](https://user-images.githubusercontent.com/72852065/222350629-1f724ff5-4b9e-4c1c-b3bf-960711f20328.png)
![grafik](https://user-images.githubusercontent.com/72852065/222351133-8a90bb89-cd83-4acc-a676-48c1491ca2ce.png)

#### Zahlungsseite
Auf der Zahlungsseite wird zum einen eine Übersicht über die aktuelle Auswahl angezeigt und es kann zwischen 3 Zahlungsmethoden ausgewählt werden.

![grafik](https://user-images.githubusercontent.com/72852065/222351425-dcc75e8b-9a78-4b58-9a7d-3223ea64f6a3.png)

Nach Auswahl der Zahlungsmethode wird die Meldung "Buchung erfolgreich!" angezeigt. Damit ist die Reservierung abgeschlossen und der Arbeitsplatz für den gewünschten Zeitraum gebucht.

![grafik](https://user-images.githubusercontent.com/72852065/222351529-dce6f03d-e002-450a-9c71-19a224dc89af.png)

Nach Abschluss wird eine Buchungsbestätigung per E-Mail an die angegebene E-Mailadresse versendet.

![grafik](https://user-images.githubusercontent.com/72852065/222354009-1ddd4ed5-a5b8-4c40-8ba5-66973c6edbbb.png)


## Login
### Login
Der Login erfolgt über die Eingabe von E-Mail und Passwort.

![grafik](https://user-images.githubusercontent.com/72852065/214049304-9c73a252-9f38-41df-b893-3d81c5c005c1.png)

### Registrierung
Wenn noch kein Konto vorhanden ist, besteht die Möglichkeit sich zu registrieren.

![grafik](https://user-images.githubusercontent.com/72852065/214049524-e6706c16-2728-41c2-8bfa-6ebdd5f9c855.png)

Zur Speicherung der Login-Daten in der Firebase-Datenbank werden diese mittels HTTP- bzw- REST-Request an die REST-API (Firebase) übermittelt. Nach Abschluss der Registrierung wird eine Bestätigungsmail gesendet.</p>

![grafik](https://user-images.githubusercontent.com/72852065/214237752-5b196db3-43d0-4670-8496-c3400c6bacda.png)


## Profilübersicht

In der Profilübersicht werden die Daten des Kontos angezeigt. Hier ist es auch möglich das Passwort zurückzusetzen, die Adresse zu ändern oder das Konto zu löschen.

![grafik](https://user-images.githubusercontent.com/72852065/214782181-fedd5236-6d55-4dd7-87ed-2f74f864b8d7.png)

## Buchungsübersicht
In der Profilübersicht werden die Buchungen angezeigt und es besteht die Möglichkeit die Buchungen zu stonieren.

![grafik](https://user-images.githubusercontent.com/72852065/214781607-3d67e685-4958-4602-b5ef-4288738b47c9.png)

## Dokumentation / Hilfe Seiten
* Für die Hilfe im Online-Reservierungs-Tool wird auf die Projektdokumentation verwiesen.
