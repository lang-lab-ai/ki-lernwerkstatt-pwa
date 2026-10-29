# KI-Lernwerkstatt

Eine eigenständige Progressive Web App zum Lernen von BWL und KI. Sie enthält zehn Karteikarten, eigene Karten, einen Modellkostenrechner und lokale Notizen. Alle App-Dateien und Icons liegen im Projekt; es werden keine externen Bibliotheken oder Tracker geladen.

**App öffnen:** [KI-Lernwerkstatt auf GitHub Pages](https://lang-lab-ai.github.io/ki-lernwerkstatt-pwa/)

Die Lernwerkstatt verbindet Grundlagen zu künstlicher Intelligenz mit betriebswirtschaftlichen Fragen: Karteikarten helfen beim Wiederholen, der Rechner vergleicht Modellkosten anhand eigener Annahmen, und Notizen halten persönliche Erkenntnisse fest. Nach dem ersten Online-Besuch kann die App auch ohne Internetverbindung genutzt werden. Die Daten bleiben auf dem jeweiligen Gerät und können als JSON gesichert werden.

## Starten und offline nutzen

Für die installierbare App wird eine HTTPS-Adresse oder `localhost` benötigt. Ein direkter Aufruf über `file://` kann die Oberfläche anzeigen, aktiviert aber den Service Worker nicht. Nach dem ersten vollständigen Online-Aufruf auf dem jeweiligen Gerät werden die App-Dateien im Offline-Cache gespeichert. Erst danach funktioniert die App ohne Verbindung. Browser können Speicher bei Platzmangel oder beim Löschen der Website-Daten entfernen.

Ein lokaler Server lässt sich beispielsweise im Projektordner starten:

```sh
python -m http.server 8000
```

Dann `http://localhost:8000/` im Browser öffnen. Für GitHub Pages den Inhalt dieses Ordners in das Repository `ki-lernwerkstatt-pwa` hochladen und unter **Settings → Pages** den Branch `main` und `/(root)` wählen. Die vorgesehene Adresse lautet `https://lang-lab-ai.github.io/ki-lernwerkstatt-pwa/`. Sie ist erst nach Einrichtung und Veröffentlichung erreichbar.

## Nutzung

- **Karteikarten:** Karte antippen, um die Antwort zu sehen. Mit den Pfeilen wechseln und bekannte Inhalte als gelernt markieren. Eigene Karten können ergänzt und gelöscht werden.
- **Rechner:** Alle Preise sind illustrative Annahmen in Euro pro Million Tokens, keine aktuellen Anbieterpreise. Kosten = Anfragen × (Eingabetokens × Eingabepreis + Ausgabetokens × Ausgabepreis) ÷ 1.000.000. Das Mini-/Lokal-Szenario enthält zusätzlich monatliche Betriebskosten. Die Ersparnis ist die Differenz der Szenarien; Amortisation = Investition ÷ positive Ersparnis. ROI im ersten Jahr = (12 × Ersparnis − Investition) ÷ Investition. Bei null Investition ist der ROI nicht definiert.
- **Notizen und Sicherung:** Daten bleiben lokal im Browser des jeweiligen Geräts. Der JSON-Export enthält eigene Karten, Lernstand, Notizen, Rechnerwerte und Darstellung. Der Import zeigt vor dem Ersetzen eine Vorschau. Diese Datei enthält persönliche Notizen und sollte entsprechend aufbewahrt werden.

## Installation

- **iPhone/iPad:** Die HTTPS-Seite in Safari öffnen, **Teilen → Zum Home-Bildschirm**, gegebenenfalls **Als Web-App öffnen**, dann **Hinzufügen** wählen.
- **Android:** In Chrome die HTTPS-Seite öffnen, das Drei-Punkte-Menü wählen und **App installieren** oder **Zum Startbildschirm hinzufügen** auswählen.
- **Windows/macOS:** In einem unterstützten Browser die Seite öffnen und im Browsermenü oder in der Adressleiste **App installieren** wählen. In Safari auf dem Mac ist **Ablage → Zum Dock hinzufügen** eine weitere Möglichkeit.

## Aktualisierung

Bei Änderungen an App-Dateien die Cache-Version in `sw.js` erhöhen. Ein aktualisierter Service Worker wird aktiviert, sobald alte App-Tabs geschlossen sind und die App erneut geöffnet wird. Die Lerninhalte zum EU AI Act sind allgemeine Lerninformationen; Fristen und Pflichten können sich ändern und sollten anhand offizieller Quellen überprüft werden.
