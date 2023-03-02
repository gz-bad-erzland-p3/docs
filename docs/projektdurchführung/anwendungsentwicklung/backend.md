# Backend

Das Backend der Projektarbeit umfasst die Datenverarbeitung und -speicherung im Hintergrund der Anwendung sowie die Benutzer-Authentifizierung.

## Warum Google Firebase?

### Anforderungen an das Backend-System

*   Kostengünstig / Kostenlos
*   Keine zusätzliche Hardware benötigt
*   Kann Datensicherheit und Ausfallsicherheit gewährleisten
*   Dezentrale Datenspeicherung (nicht Personen- oder Ortsgebunden, wie z.B. eine Virtuelle Maschine auf einem Stick oder Laptop)
*   Datenzugriff und -speicherung aus JavaScript-Frontend möglich
*   Einfache und wenn möglich automatisierte Backup-Möglichkeiten
*   Geringer Konfigurations- und Entwicklungsaufwand
*   Schnittstellen mit neuesten Sicherheitsstandards vorhanden
*   DSGVO-Konforme Datenverarbeitung muss möglich sein

### Vorteile von Cloud-Computing

*   Einfache Skalierbarkeit ggü. einem Self-Hosted Datenbank-Server
*   Kosteneinsparungen bei der Hardware
*   Kosteneinsparungen beim Betrieb der Anwendung, durch nutzungsabhängigen Zahlungsmodelle
*   Ausfallsicherheit und Datensicherheit durch Backup-Regeln
*   Schnelle Markteinführung möglich, da (fast) kein Installationsaufwand besteht
*   Cloud-Service-Provider (CSPs) betreiben die zugrunde liegende Infrastruktur, sodass wir uns auf die Anwendungsentwicklung und andere Prioritäten konzentrieren können
*   Einfacher und (meist) Plattformübergreifender Zugriff auf die Daten möglich

### Nutzwertanalyse/Entscheidung für einen Cloud-Service-Provider

<table><tbody><tr><td><strong>Anforderung</strong></td><td><strong>Azure SQL-Server</strong></td><td><strong>AWS Amplify</strong></td><td><strong>Google Firebase</strong></td></tr><tr><td>Cloud-Dienst</td><td><strong>✓</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr><tr><td>Automatische Backup-Regeln sind konfigurierbar</td><td><strong>✓</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr><tr><td>Geringer Konfigurations-Aufwand</td><td><strong>✘</strong></td><td><strong>✘</strong></td><td><strong>✓</strong></td></tr><tr><td>Plattformübergreifender Zugriff auf Daten</td><td><strong>✓</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr><tr><td>DSGVO-Konforme Datenspeicherung ist möglich</td><td><strong>✓</strong></td><td><strong>✘</strong></td><td><strong>✓</strong></td></tr><tr><td>Kostenlos zum Entwickeln und Testen</td><td><strong>✓</strong></td><td><strong>✘</strong></td><td><strong>✓</strong></td></tr><tr><td>Authentifizierungsdienst mit Schnittstelle zur Datenbank vorhanden</td><td><strong>✘</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr><tr><td>Einfache Echtzeit-Synchronisierung auf allen Clients möglich</td><td><strong>✘</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr><tr><td>JavaScript-API oder SDK</td><td><strong>✘</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr><tr><td>Regelmäßige Updates der Schnittstellen</td><td><strong>✓</strong></td><td><strong>✓</strong></td><td><strong>✓</strong></td></tr></tbody></table>

## Google Firebase

Google Firebase ist eine von Google entwickelte Plattform für die Entwicklung und den sicheren Betrieb mobiler Webanwendungen. Die Plattform stellt ein Software-Development-Kit (SDK) und die benötigte Infrastruktur zur Verfügung. Dies ermöglicht es, einfach und effizient Funktionalitäten auf verschiedenen Plattformen bereitzustellen.

Besonderheiten der Firebase-Plattform ggü. vergleichbaren Plattformen:

*   Datenzugriff und -speicherung erfoglt mithilfe von Methoden aus dem SDK direkt vom clientseitigen Code
*   Es wird kein Server benötigt, der API-Abfragen weiterverarbeitet

### Kostenplan

Siehe [https://firebase.google.com/pricing](https://firebase.google.com/pricing)

Im "No-cost Plan" sind u.a. folgende Spezifikationen verfügbar:

*   bis zu 50.000 Authentifizierungen pro Monat
*   bis zu 1 GB Realtime-Database Speicher **≈ 1** Millionen Buchungen insgesamt bei unserer Anwendung
*   bis zu 100 gleichzeitige (synchrone) Verbindungen mit der Realtime-Database
*   bis zu 10 GB Datentransfer (Upload und Download) pro Monat **≈** 10 Millionen Buchungen pro Monat bei unserer Anwendung
*   (bis zu 5 GB Cloud-Storage Speicher)

### Verbindungsaufbau

TODO

### Kommunikation

Die Kommunikation erfolgt im Gegensatz zu klassischen Web-Anwendungen direkt mit dem ... TODO

![](https://user-images.githubusercontent.com/71382635/222440948-0914bf7c-e815-4d50-954f-8e1eea0458d5.png)

## Datenbank

Als DBMS wird die Firebase-Console mit Echtzeitdatenbank von [Google Firebase](https://www.firebase.com) verwendet.

### Übersicht

Firebase bietet eine Cloudbasierte NoSQL-Echtzeitdatenbank, die speziell für die Verwendung in mobilen und Webanwendungen entwickelt wurde. Die Datenbank ist in der Lage, Daten in Echtzeit auf allen Clients zu synchronisieren und somit Änderungen in der Anwendung in Echtzeit darzustellen. Sollte die Anwendung offline gehen, bleiben die Daten erhalten. Sobald die Verbindung wiederhergestellt ist, werden die Änderungen automatisch in der Cloud-Datenbank aktualisiert.

Die Speicherung erfolgt in Form eines JSON-Objekts.

Die Datenbank kann eng mit anderen Firebase-Produkten, wie zum Beispiel der Firebase Authentifizierung, Cloud Messaging und Cloud Storage verknüpft werden. Dies ermöglicht es Entwicklern, leistungsfähige Anwendungen zu erstellen, die auf Echtzeitdaten basieren.

Firebase bietet auch eine benutzerfreundliche Konsole, mit der Entwickler die Datenbank konfigurieren, Daten visualisieren und Abfragen ausführen können.

Durch verschiendene SDKs ermöglicht Firebase den sicheren Zugriff auf die verschiedenen Produkte (z.B. Datenbank und den Authzentifizierungsdienst) direkt vom clientseitigen Code. Zudem ist das SDK in verschiedensten Programmiersprachen verfügbar, wie z.B. SwiftUI, Swift, Objective-C, Java, Kotlin, JavaScript (modular und namespaced), Flutter, REST, C++, Unity uvm.

### Sicherheitsregeln

Sicherheitsregeln dienen der Zugriffskontrolle und dem Schutz vor böswilligen Benutzern und Cyber-Attacken.

In unserem Fall beinhalten die Sicherheitsregeln nur die nötigsten Einschränkungen und sind sehr weit gefasst.

```json
{
  "rules": {
      "bookings": {
          ".read": true,
          ".write": "$uid === auth.uid"
      }
      "users": {
          "$uid": {
              ".read": "$uid === auth.uid",
              ".write": "$uid === auth.uid"
      }
    }
  }
}
```

Diese können jedoch ohne Komplikationen oder Datenverluste beim Produktivgang in ihrer Granularität verengt werden.

Siehe [Firebase-Dokumentation](https://firebase.google.com/docs/rules/rules-language?hl=de#database).

### Entity-Relationship-Model

![](https://user-images.githubusercontent.com/71382635/222356133-a7ff71ba-c460-4b63-80a6-980b45456c2f.png)

### Relationenmodell

siehe [Firebase Konsole](https://console.firebase.google.com/u/5/) (benötigt Anmeldung)

## Authentifizierung

### Übersicht

Firebase bietet eine elegante und sichere Lösung für die Authentifizierung von Nutzern in mobilen und Webanwendungen. Mit einer Fülle von Authentifizierungsmethoden wie beispielsweise E-Mail/Passwort, Google, Facebook, Twitter und GitHub, bietet Firebase eine nahtlose Integration von Authentifizierung in die Anwendungsentwicklung. Entwickler können so schnell und einfach Firebase-Authentifizierungsfunktionen erstellen und konfigurieren, indem sie auf eine benutzerfreundliche API und Konsole zugreifen.

Die Firebase-Authentifizierung ist bei korrekter Implementierung von hoher Sicherheit und bietet Schutz gegen gängige Angriffe wie Phishing, Brute-Force-Angriffe und Cross-Site Request Forgery (CSRF). Darüber hinaus bietet Firebase Funktionen wie Zwei-Faktor-Authentifizierung, Geräteüberprüfung und OAuth- und OpenID-Connect Unterstützung.

Das Firebase-Authentifizierungs SDK bietet Methoden zum Erstellen und Verwalten von Benutzern sowie das Senden von E-Mails zum Zurücksetzen von Passwörtern.

Grundlegende Funktionsweise ist wie folgt: Ein Authentifizierungstoken wird nach einer erfolgreichen Registrierung oder Anmeldung erstellt. Mit diesem kann auf die grundlegenden Profilinformationen des Benutzers zugegriffen werden und der Zugriff des Benutzers auf Daten gesteuert werden, die in anderen Firebase-Produkten gespeichert sind.

## Versenden von Emails

### Übersicht

[EmailJS](https://www.emailjs.com) ist ein Service, der es Entwicklern ermöglicht, E-Mails über ihre eigenen Frontend-Webanwendungen zu senden, ohne dass ein Backend-Server erforderlich ist. Es erleichtert die Integration von E-Mail-Versand in Webanwendungen, indem es eine API bereitstellt, die es Entwicklern ermöglicht, E-Mails zu senden, ohne dass sie sich um den Aufbau und die Verwaltung eines eigenen E-Mail-Servers kümmern müssen.

### Bestätigungsmail bei erfolgreicher Registrierung

![](https://user-images.githubusercontent.com/71382635/222359712-81eedce4-fea5-4072-b69d-6c85c0852654.png)

### Bestätigungsmail bei Buchungsabschluss

![](https://user-images.githubusercontent.com/71382635/222359448-2be7c25c-0b0b-44db-9fda-687c27aeff49.png)

## Beispiel-Implementierungen

### Abrufen der Firebase-DB und -AUTH Instanz

Importieren der benötigten Pakete des Firebase-SDK

```typescript
import { initializeApp } from "firebase/app";
import { getAuth, browserSessionPersistence, setPersistence } from "firebase/auth";
import { getDatabase } from "firebase/database";
```

Firebase-Konfigurationen hinterlegen

```typescript
const firebaseConfig = {
    apiKey: "AIzaSyBnDu6VFsaZIIPYG6AWNSqKqnVpgTEplY4",
    authDomain: "gz-bad-erzland-a5231.firebaseapp.com",
    projectId: "gz-bad-erzland-a5231",
    storageBucket: "gz-bad-erzland-a5231.appspot.com",
    messagingSenderId: "389584456404",
    appId: "1:389584456404:web:0af49a35ba216bbd0dc941",
    measurementId: "G-3QLDSXMNVG"
};
```

Firebase-App initialisieren

```typescript
initializeApp(firebaseConfig); //Funktion aus dem Firebase-JS-SDK (firebase/app)
```

Auth-Instanz und Database-Instanz der zuvor initialisierten Firebase-App abholen

```typescript
const auth = getAuth(); //Funktion aus dem Firebase-JS-SDK (firebase/auth)
const db = getDatabase(); //Funktion aus dem Firebase-JS-SDK (firebase/database)
```

Session-Cookie setzen (wird bei einer erfolgreicher Authentifizierung automatisch aktualisiert)

```typescript
setPersistence(auth, browserSessionPersistence) //Funktion aus dem Firebase-JS-SDK (firebase/auth)
```

### Benutzer-Registrierung und Speicherung der Benutzerdaten

Methode, um einen Benutzer im System zu erstellen und dessen angegebene Daten in der Datenbank zu speichern:

```javascript
async function signUp(email, passwort, name, prename, birthday, address_formatted, place_id) {
    await createUserWithEmailAndPassword(auth, email, passwort); //Funktion aus dem Firebase-JS-SDK (firebase/auth)
    const uid = auth.currentUser.uid;
    await set(ref(db, 'users/' + uid), { //Funktionen set und ref aus dem Firebase-JS-SDK (firebase/database)
      Name: name,
      Email: email,
      Vorname: prename,
      Geburtsdatum: birthday,
      Adresse_Formatiert: address_formatted,
      Adresse_GooglePlaceId: place_id
    });
};
```

Nach erfolgreicher Registrierung wird ein Benutzer im System hinzugefügt. Dieser ist nun in der Benutzerverwaltung sichtbar. Zudem werden seine dazugehörigen Daten in der Echtzeit-Datenbank gespeichert.

### Speicherung der Buchungsdaten

Beim Abschließen des Buchungsprozesses wird folgende Methode zum Speichern der Daten (Objekt `data` unter der `bookingId`) aufgerufen:

```typescript

async function sendBooking(db, bookingId, data) {
    try{
        await set(ref(db, 'bookings/' + bookingId), data); //Funktion aus dem Firebase-JS-SDK (firebase/util)
    } catch(e){
        console.log('Error while saving current booking', e)
    }    
}
```

Nach erfolgreicher Speicherung in der Echtzeit-Datenbank sind die Buchungsdaten in der Firebase-Console sichtbar.
