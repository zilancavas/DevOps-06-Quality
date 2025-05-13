# DevOps 06 Quality

## Lernjournal

| Schritt | Beschreibung | Screenshot |
|--------|--------------|------------|
| 1 | Ein einfaches HTML-Dokument wurde in Visual Studio Code erstellt. Die Datei `index.html` enthält eine grundlegende Struktur mit `<title>` und einer Überschrift. | ![quality-01](./quality-01.png) |
| 2 | Die Erweiterung **HTMLHint** wurde im VS Code Marketplace gesucht und installiert, um die HTML-Datei auf Qualitätsprobleme zu überprüfen. | ![quality-02](./quality-02.png) |
| 3 | Die installierte Erweiterung **HTMLHint** zeigt nach dem Speichern direkt Warnungen zu fehlenden Standards (z. B. `<!DOCTYPE html>`) an. | ![quality-03](./quality-03.png) |
| 4 | Die HTML-Datei wurde entsprechend den Hinweisen angepasst. Es wurden die fehlenden Elemente ergänzt, bis keine Warnungen mehr angezeigt wurden. | ![quality-04](./quality-04.png) |
| 5 | Anschliessend habe ich das Repository mit GitHub synchronisiert. Dabei trat zunächst ein Push-Fehler auf, der durch einen vorherigen `git pull --rebase` behoben wurde. | ![quality-05](./quality-05.png) |
| 6 | In SonarQube wurde das Projekt vorbereitet. Dabei wurden die verschiedenen Möglichkeiten zur Integration der Analyse angezeigt, unter anderem GitHub Actions und lokale Analyse. | ![quality-06](./quality-06.png) |
| 7 | Über Homebrew wurde das Tool `sonar-scanner` lokal installiert, um die Analyse direkt auf dem System durchführen zu können. | ![quality-07](./quality-07.png) |
| 8 | Die SonarQube-Analyse des Backends wurde mit `sonar-scanner` gestartet. Dabei wurden Projektinformationen und Plugins erfolgreich geladen. | ![quality-08](./quality-08.png) |
| 9 | Die Analyse schlug zunächst fehl, da keine Berechtigung zur Auswertung des Projekts vorlag. Ein Hinweis auf fehlende Autorisierung wurde angezeigt. | ![quality-09](./quality-09.png) |
| 10 | Die Projektberechtigungen wurden in SonarQube überprüft und so angepasst, dass autorisierte Benutzer die Analyse ausführen dürfen. | ![quality-10](./quality-10.png) |
