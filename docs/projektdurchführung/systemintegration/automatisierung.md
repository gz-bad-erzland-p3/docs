# Automatische Aktualisierung der Website
Die Aktualisierung der Webseite erfolg über ein Skript, welches durch einen Service ausgeführt wird. Dieser Service wird durch einen Timer verwaltet.

Die Funktionsweise ist wie folgt:
- jeden Tag 0 Uhr werden die CommitIDs der Onlineversion und der lokalen Version verglichen
![timer](https://user-images.githubusercontent.com/98982162/221189637-4340ef00-7947-42f9-b533-18a8009ffac2.png)
- sind diese ungleich wird die Version von Github heruntergeladen und damit ein Textimage gebaut
- wenn der Container fehlerfrei gebaut werden konnte, wird er wieder entfernt
- anschließend wird die aktuelle Webseite über den Dienst gestoppt
- die Images werden umgetagget bzw. entfernt
- der neue Container wird mit seinem Dienst neu erstellt