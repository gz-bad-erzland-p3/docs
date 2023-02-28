# Frontend

Das Frontend der Projektarbeit bezieht sich auf alle Benutzeroberflächen der Anwendung sowie der grafischen Gestaltung der Startseite (zu engl. Landingpage) 

!!! info "Projektcode"

    Der gesamte Projektcode steht Open-Source auf [GitHub](https://github.com/gz-bad-erzland-p3/projektarbeit) zu verfügung 

## Landingpage

Zuerst wurde eine Landingpage erstellt, über die man zum Online-Reservierungs-Tool gelangt. </p>

![LandingPage1](https://user-images.githubusercontent.com/72852065/215064333-7b0d153a-e669-4753-8e3d-858a1dc9a80e.png)

## Buchungsseite
### Wizard

Die Buchungsseite ist das Kernstück des Projektes. Sie ist die zentrale Anlaufstelle, in welcher Benutzer eine Buchung tätigen. Die Buchungsseite ist so gestaltet, dass sie leicht zu navigieren ist und die Benutzererfahrung optimiert.

Um sicherzustellen, dass der Buchungsprozess reibungslos abläuft und Benutzer nicht von komplizierten Formularen oder verwirrenden Optionen abgeschreckt werden, wird ein "Wizard" eingesetzt. Der Wizard führt den Benutzer Schritt für Schritt durch den Buchungsprozess und stellt sicher, dass alle notwendigen Informationen korrekt erfasst werden. Durch diese Methode wird die Fehlerquote reduziert, da jeder Schritt auf Fehler geprüft wird, bevor der Benutzer zum nächsten Schritt gelangen kann.

Single-Page-Anwendungen sind eine häufige Art von Buchungsseite, da sie eine schnelle und nahtlose Benutzererfahrung bieten. Die gesamte Buchung wird auf einer einzigen Seite ausgeführt, ohne dass der Benutzer die Seite neu laden oder auf verschiedene Seiten navigieren muss. Dadurch wird die Navigation erleichtert und die Benutzerfreundlichkeit verbessert.

#### Terminauswahl
Als erstes gelangt man zur Terminauswahl. Dort können der Zeitraum und die Start-, bzw. Endzeit ausgewählt werden.

![grafik](https://user-images.githubusercontent.com/72852065/214051100-b5c7c2e9-46d4-47be-acec-2c0f92d36e3f.png)

In der Terminauswahl muss die Mindest- und Maximalmietdauer beachtet werden. Wird die Mietdauer über-/unterschritten wird eine Meldung oben in der Ecke angezeigt.

![grafik](https://user-images.githubusercontent.com/72852065/214259770-c4acab74-c43d-495c-a5e6-a47b9f81e8ec.png)

#### Arbeitsplatzauswahl
Bei der Arbeitsplatzauswahl kann zwischen Einzel- oder Doppelarbeitsplatz gewählt werden. Optionen, welche ausgegraut werden sind aufgrund anderer Buchungen nicht mehr auswählbar.

![grafik](https://user-images.githubusercontent.com/72852065/214238131-8b658d7c-9440-4e11-8902-e0bc2cb3db5e.png)

#### Konfiguration
In der Konfiguration muss als erstes ausgewählt werden, ob ein eigenes Gerät mitgebracht werden soll oder nicht. Falls keins mitgebracht wird besteht die möglichkeit verschiedene Geräte zu konfigurieren.

![grafik](https://user-images.githubusercontent.com/72852065/214238195-7e06409d-9df7-4db1-ae86-0135241227f9.png)

Wird "Ich brauche ein Gerät" gewählt, erweitert sich die Seite und es werden weitere Konfigurationsmöglichkeiten angezeigt. Nun kann zwischen Laptop, Desktop-PC und Barebone entschieden werden, eine Auswahl über das Betriebssystem getroffen und kostenlose Browser und Kommunikationsapplikationen ausgewählt werden. Zusätzlich können noch Bemerkungen bzw. Wünsche eingetragen werden.

![grafik](https://user-images.githubusercontent.com/72852065/214238626-97ce8523-f0ab-4072-9268-28c2ba0c282a.png)
![edited](https://user-images.githubusercontent.com/72852065/214238361-8646f52c-9586-41d5-8a88-c2136ac99559.png)

#### Reservierung

Nach erfolgreicher Anmeldung/Reservierung wird der Interessent gebeten auf einen Button zu klicken. Hiermit ist der konfigurierte Arbeitsplatz für 20min reserviert und es werden die Zahlungsmethoden angezeigt.

![grafik](https://user-images.githubusercontent.com/72852065/214779369-5d4ffa31-72c1-42e4-8db4-a852c3bacd98.png)

#### Zahlungsseite
Auf der Zahlungsseite kann zwischen 3 Zahlungsmethoden ausgewählt werden.
![grafik](https://user-images.githubusercontent.com/72852065/214248987-1a45aa94-9278-404d-a085-1e85b7e6f61d.png)

Nach Auswahl der Zahlungsmethode wird die Meldung "Buchung erfolgreich!" angezeigt. Damit ist die Reservierung abgeschlossen und der Arbeitsplatz für den gewünschten Zeitraum gebucht.
![grafik](https://user-images.githubusercontent.com/72852065/214775635-1ef426d6-a9ed-4fd8-9093-bf22147b758b.png)

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
