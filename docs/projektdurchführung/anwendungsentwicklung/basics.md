# Grundlegendes über die Entwicklung der Anwendung

Im folgenden Abschnitt geben wir einen groben Überblick über die, in der Anwendung verwendeten, Entwicklungs-Technologien. 

## Warum eine Web-Anwendung?

Es gibt mehrere Vorteile einer Webanwendung gegenüber einer Desktop-Anwendung, darunter:

**Plattformunabhängigkeit**: Eine Webanwendung läuft auf jedem Gerät mit einem Webbrowser, unabhängig davon, ob es sich um einen Desktop-Computer, ein Mobiltelefon oder ein Tablet handelt. Im Gegensatz dazu müssen Desktop-Anwendungen für jede Plattform separat entwickelt werden, was Zeit und Ressourcen erfordert.

**Einfache Wartung**: Da Webanwendungen zentral auf einem Server ausgeführt werden, ist es einfacher, Updates und Änderungen durchzuführen. Benutzer müssen die Anwendung nicht jedes Mal aktualisieren, wenn eine Änderung vorgenommen wird.

**Einfacher Zugriff**: Webanwendungen sind überall zugänglich, solange eine Internetverbindung verfügbar ist. Im Gegensatz dazu müssen Desktop-Anwendungen auf jedem Gerät installiert werden, auf dem sie verwendet werden sollen.

**Kosteneffizienz**: Die Entwicklung einer Webanwendung ist oft kosteneffizienter als die Entwicklung einer Desktop-Anwendung. Es müssen keine teuren Lizenzen oder spezielle Hardwareanforderungen erfüllt werden, um die Anwendung auszuführen.

**Zusammenarbeit**: Webanwendungen ermöglichen es Benutzern, gemeinsam an Dokumenten oder Projekten zu arbeiten, unabhängig davon, wo sie sich befinden. Die Zusammenarbeit kann in Echtzeit erfolgen und Änderungen können sofort aktualisiert werden.

**Skalierbarkeit**: Webanwendungen können problemlos auf eine große Anzahl von Benutzern skaliert werden, ohne dass eine zusätzliche Hardware erforderlich ist. Im Gegensatz dazu können Desktop-Anwendungen aufgrund von Hardwarebeschränkungen nur eine begrenzte Anzahl von Benutzern unterstützen.

Insgesamt bieten Webanwendungen viele Vorteile gegenüber Desktop-Anwendungen und haben sich in den letzten Jahren zu einem bevorzugten Ansatz für die Bereitstellung von Software entwickelt.

## Technologien und Werkzeuge

Für eine reibungslose Zusammenarbeit im Team, zur Reduzierung der Entwicklungszeit, zur Fehlerminimierung und zur Minimierung der Ladezeiten verwenden wir folgende Entwicklungstechnologien:

### Programmiersprache - TypeScipt

**Was ist TypeScript?**

TypeScript ist eine von Microsoft entwickelte Skriptsprache, welche JavaScript um einige Funktionalitäten zu einer Objektorientierten Sprache erweitert.

**Warum verwenden wir TypeScript anstatt JavaScript?**

*   TypeScript ist im Gegensatz zu JavaScript eine objektorientierte Sprache
*   Verbesserte Kompatibilität und Interoperabilität mit anderen Codebibliotheken und Frameworks
*   Bessere IDE-Unterstützung
*   Bessere Lesbarkeit und Wartbarkeit durch statische Typisierung und verbesserte Fehlererkennung

### Versionsverwaltung - GitHub

**Was ist GitHub?**

GitHub ist ein Cloud-Dienst zur Versionsverwaltung für Software-Entwicklungsprojekte.

**Warum verwenden wir GitHub?**

*   Kostenlos
*   Sehr ausfallsicher
*   Einfache Verknüpfung mit Build- und Deployment-Tools, wie z.B. Vercel
*   Ermöglicht eine unkomplizierte Zusammenarbeit bei der Entwicklung

### Entwicklungsumgebung - Visual Studio Code

**Warum verwenden wir Visual Studio Code?**

*   Auf allen Plattformen verfügbar (WIN, MAC, LINUX)
*   Nützliche Debugging-Tools
*   Gute Vorkenntnisse aller Entwickler
*   Optimiert für die JavaScript/TypeScript-Entwicklung
*   Optimiert für die Verwendung von GitHub
*   Einfache Einarbeitung möglich
*   Geringer Installationsaufwand bei neuen Entwicklern

### React

**Was ist React?**

React ist eine JavaScript-Programmbibliothek zur Erstellung von webbasierten Benutzeroberflächen.

**Warum verwenden wir React?**

*   Gute Vorkenntnisse bei einigen Entwicklern unseres Teams
*   Einfacher Einstieg für unerfahrene Entwickler
*   Einfaches und intuitives Coding durch wiederverwendbare Komponenten, unkompliziertes Debugging und eine einfache Wartung
*   schnelle Ladezeiten durch einen Virtual DOM (Virtual DOM vergleicht die vorherigen Zustände der Komponenten und aktualisiert nur die geänderten Elemente im Real DOM)
*   Große Community rund um React (stellt viele kostenlose Online-Hilfen und Tutorials sowie fertige Open-Source-Implementierungen benötigter Funktionalitäten zur Verfügung)

**Beispiele bekannter React-Apps:**

*   Facebook
*   Instagram
*   Netflix
*   Airbnb
*   Cloudflare
*   Dropbox
*   Paypal
*   Reddit
*   Postmates
*   Whatsapp
*   Pinterest
*   BBC
*   NEU! Arbeitsplatzvermietung vom GZ Bad Erzland

### NextJS-Framework

**Was ist NextJS?**

NextJS, erstellt von Vercel, ist ein Open-Source-JavaScript-Framework, mit dem Entwickler dynamische und statische Webanwendungen und Websites erstellen können. Es bietet, neben anderen Funktionalitäten, eine fertige Lösung für das serverseitige Rendering (SSR) von React-Komponenten.

**Warum verwenden wir NextJS?**

*   Gebrauchsfertiges SSR
*   API-Unterstützung von Drittanbietern (z.B. Routing der Seiten vor und nach der Authentifizierung)
*   (Besser für SEO)
*   (Bildoptimierung)

**Beispiele bekannter NextJS-Apps:**

*   Netflix
*   Airbnb
*   TikTok
*   Uber
*   GitHub
*   Twitch
*   Docker
*   coinbase
*   Tripadviser
*   OpenAI

## **Coding-Richtlinien**

Die Benamung von Dateien und Funktionen erfolgt nach [diesen](https://makecode.com/extensions/naming-conventions) Grundlagen.

Das Einhalten einer einheitlichen und korrekten Syntax überwacht das IDE Tool ESLint. Dies ist vor dem Start der Entwicklung in der IDE hinzuzufügen.

Die ausschließliche Verwendung der Programmiersprache TypeScript (nicht nur JavaScript) bietet eine starke Typisierung, woraufhin bereits zur Übersetzungszeit bestimmte Fehler aufgedeckt werden können.

Die Verwendung von Fremdbibliotheken muss mit dem Entwicklungsleiter zuvor abgesprochen werden.

Die Verwendung von Funktionen, die ein Sicherheitsrisiko darstellen (z.B. eval() ) ist untersagt.
