# Grundlegendes über die Entwicklung der Anwendung

Im folgenden Abschnitt geben wir einen groben Überblick über die, in der Anwendung verwendeten, Entwicklungs-Technologien. 

## Technologien und Werkzeuge

### Programmiersprache - TypeScipt

**Was ist TypeScript?**

s

**Warum verwenden wir GitHub?**

*   s

### Versionsverwaltung - GitHub

**Was ist GitHub?**

GitHub ist ein Cloud-Dienst zur Versionsverwaltung für Software-Entwicklungsprojekte.

**Warum verwenden wir GitHub?**

*   Kostenlos
*   Ausfallsicher
*   Einfache Verknüpfung mit Build- und Deployment-Tools, wie z.B. Vercel
*   Ermöglicht eine unkomplizierte Zusammenarbeit bei der Entwicklung

### Entwicklungsumgebung - Visual Studio Code

**Warum verwenden wir Visual Studio Code?**

### React

**Was ist React?**

React ist eine JavaScript-Programmbibliothek zur Erstellung von webbasierten Benutzeroberflächen.

**Warum verwenden wir React?**

*   Gute Vorkenntnisse bei einigen Entwicklern unseres Teams
*   Einfacher Einstieg für unerfahrene Entwickler unseres Teams
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
