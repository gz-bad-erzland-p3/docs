# Backend

## Entwicklungswerkzeuge

*   Programmiersprachen: TypeScript, CSS, HTML
    *   von Microsoft entwickelte Skriptsprache, welche JavaScript um die Funktionalitäten einer Objektorientierten Sprache erweitert.
*   Framework: Next.js  (React)
    *   Open-Source-Webentwicklungs-Framework, das React-basierte Webanwendungen mit serverseitigem Rendering ermöglicht.
*   Datenbank- und Authentifizierungs-Schnittstelle: Google Firebase 
    *   Entwicklungs-Plattform für mobile und Webanwendungen. Das SDK ermöglicht dem Entwickler, einfach und effizient Funktionalitäten mittels Programmierschnittstellen auf verschiedenen Plattformen bereitzustellen. 

## Google Firebase

Google Firebase ist eine von Google entwickelte Entwicklungs-Plattform für mobile und Webanwendungen. Sie stellt über ein Software Development Kit Tools und Infrastruktur zur Verfügung, die es einem Entwickler ermöglichen sollen, einfacher und effizienter Funktionen mittels Programmierschnittstellen auf verschiedenen Plattformen bereitzustellen.

### Nutzwertanalyse/Entscheidungstabelle

<table><tbody><tr><td>todo</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>AWS Amplify</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>Google Firebase</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>Backendless</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr></tbody></table>

Weitere Vorteile der Firebase-Plattform:

*   Optionale Objekteigenschaften sind besser abbildbar
*   Es ist ein sehr ausgereiftes Event-Handling implementiert
*   Extrem einfache Verknüpfung mit einem JavaScript-Frontend

### Implementierung

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

## Datenbank

Als Datenbanklösung wird die Echtzeitdatenbank von [Firebase](https://www.firebase.com) verwendet.

### Übersicht

Firebase bietet eine Cloudbasierte NoSQL-Echtzeitdatenbank, die speziell für die Verwendung in mobilen und Webanwendungen entwickelt wurde. Die Datenbank ist in der Lage, Daten in Echtzeit auf allen Clients zu synchronisieren und somit Änderungen in der Anwendung in Echtzeit darzustellen. Sollte die Anwendung offline gehen, bleiben die Daten erhalten. Sobald die Verbindung wiederhergestellt ist, werden die Änderungen automatisch in der Cloud-Datenbank aktualisiert.

Die Daten werden in Form eines JSON-Objekts gespeichert.

Die Datenbank kann eng mit anderen Firebase-Produkten, wie zum Beispiel der Firebase Authentifizierung, Cloud Messaging und Cloud Storage verknüpft werden. Dies ermöglicht es Entwicklern, leistungsfähige Anwendungen zu erstellen, die auf Echtzeitdaten basieren.

Firebase bietet auch eine benutzerfreundliche Konsole, mit der Entwickler die Datenbank konfigurieren, Daten visualisieren und Abfragen ausführen können.

Durch verschiendene SDKs ermöglicht Firebase den sicheren Zugriff auf die verschiedenen Produkte (z.B. Datenbank und den Authzentifizierungsdienst) direkt vom clientseitigen Code. Zudem ist das SDK in verschiedensten Programmiersprachen verfügbar, wie z.B. SwiftUI, Swift, Objective-C, Java, Kotlin, JavaScript (modular und namespaced), Flutter, REST, C++, Unity uvm.

### Entity-Relationship-Model

![](https://user-images.githubusercontent.com/71382635/222356133-a7ff71ba-c460-4b63-80a6-980b45456c2f.png)

### Beispiel-Implementierung (Use-Case 2)

Beim Abschließen des Buchungsprozesses wird folgende Funktion zum Speichern der Daten (Objekt `data` unter der `bookingId`) aufgerufen:

```typescript

async function sendBooking(db, bookingId, data) {
	try{
		await set(ref(db, 'bookings/' + bookingId), data); //Funktion aus dem Firebase-JS-SDK (firebase/util)
	} catch(e){
		console.log('Error while saving current booking', e)
	}	
}
```

Nach erfolgreicher Speicherung, sind die Daten in der Firebase-Console sichtbar:

## Authentifizierung

### Übersicht

Firebase bietet eine elegante und sichere Lösung für die Authentifizierung von Nutzern in mobilen und Webanwendungen. Mit einer Fülle von Authentifizierungsmethoden wie beispielsweise E-Mail/Passwort, Google, Facebook, Twitter und GitHub, bietet Firebase eine nahtlose Integration von Authentifizierung in die Anwendungsentwicklung. Entwickler können so schnell und einfach Firebase-Authentifizierungsfunktionen erstellen und konfigurieren, indem sie auf eine benutzerfreundliche API und Konsole zugreifen.

Die Firebase-Authentifizierung ist bei korrekter Implementierung von hoher Sicherheit und bietet Schutz gegen gängige Angriffe wie Phishing, Brute-Force-Angriffe und Cross-Site Request Forgery (CSRF). Darüber hinaus bietet Firebase Funktionen wie Zwei-Faktor-Authentifizierung, Geräteüberprüfung und OAuth- und OpenID-Connect Unterstützung.

Das Firebase-Authentifizierungs SDK bietet Methoden zum Erstellen und Verwalten von Benutzern sowie das Senden von E-Mails zum Zurücksetzen von Passwörtern.

Grundlegende Funktionsweise ist wie folgt: Ein Authentifizierungstoken wird nach einer erfolgreichen Registrierung oder Anmeldung erstellt. Mit diesem kann auf die grundlegenden Profilinformationen des Benutzers zugegriffen werden und der Zugriff des Benutzers auf Daten gesteuert werden, die in anderen Firebase-Produkten gespeichert sind. 

### Konfiguration in der Firebase-Console

![](https://user-images.githubusercontent.com/71382635/222352471-a1e8d792-5b90-4873-8817-dbfbe67e9a7c.png)

### Beispiel-Implementierung (Registrierung)

Beispiel-Methode, um einen Benutzer im System zu erstellen und dessen angegebene Daten in der Datenbank zu speichern:

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

Nach erfolgreicher Registrierung wird ein Benutzer im System hinzugefügt. Dieser ist nun in der Benutzerverwaltung sichtbar:

![](https://user-images.githubusercontent.com/71382635/222355890-ab8b0ed3-87dd-401d-b75e-13b889d26751.png)

Zudem werden seine Dazugehörigen Daten in der Datenbank gespeichert:

\[todo\]

## Versenden von Emails

### Übersicht

[EmailJS](https://www.emailjs.com) ist ein Service, der es Entwicklern ermöglicht, E-Mails über ihre eigenen Frontend-Webanwendungen zu senden, ohne dass ein Backend-Server erforderlich ist. Es erleichtert die Integration von E-Mail-Versand in Webanwendungen, indem es eine API bereitstellt, die es Entwicklern ermöglicht, E-Mails zu senden, ohne dass sie sich um den Aufbau und die Verwaltung eines eigenen E-Mail-Servers kümmern müssen.

### Bestätigungsmail bei erfolgreicher Registrierung

![](https://user-images.githubusercontent.com/71382635/222359712-81eedce4-fea5-4072-b69d-6c85c0852654.png)

### Bestätigungsmail bei Buchungsabschluss

![](https://user-images.githubusercontent.com/71382635/222359448-2be7c25c-0b0b-44db-9fda-687c27aeff49.png)
