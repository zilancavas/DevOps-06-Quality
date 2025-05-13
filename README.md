# DevOps 06 Quality

## Lernjournal

| Schritt | Beschreibung | Screenshot |
|--------|--------------|------------|
| 1 | Ein einfaches HTML-Dokument wurde in Visual Studio Code erstellt. Die Datei `index.html` enthält eine grundlegende Struktur mit `<title>` und einer Überschrift. | ![quality-01](./images/quality-01.png) |
| 2 | Die Erweiterung **HTMLHint** wurde im VS Code Marketplace gesucht und installiert, um die HTML-Datei auf Qualitätsprobleme zu überprüfen. | ![quality-02](./images/quality-02.png) |
| 3 | Die installierte Erweiterung **HTMLHint** zeigt nach dem Speichern direkt Warnungen zu fehlenden Standards (z. B. `<!DOCTYPE html>`) an. | ![quality-03](./images/quality-03.png) |
| 4 | Die HTML-Datei wurde entsprechend den Hinweisen angepasst. Es wurden die fehlenden Elemente ergänzt, bis keine Warnungen mehr angezeigt wurden. | ![quality-04](./images/quality-04.png) |
| 5 | Anschliessend habe ich das Repository mit GitHub synchronisiert. Dabei trat zunächst ein Push-Fehler auf, der durch einen vorherigen `git pull --rebase` behoben wurde. | ![quality-05](./images/quality-05.png) |
| 6 | In SonarQube wurde das Projekt vorbereitet. Dabei wurden die verschiedenen Möglichkeiten zur Integration der Analyse angezeigt, unter anderem GitHub Actions und lokale Analyse. | ![quality-06](./images/quality-06.png) |
| 7 | Über Homebrew wurde das Tool `sonar-scanner` lokal installiert, um die Analyse direkt auf dem System durchführen zu können. | ![quality-07](./images/quality-07.png) |
| 8 | Die SonarQube-Analyse des Backends wurde mit `sonar-scanner` gestartet. Dabei wurden Projektinformationen und Plugins erfolgreich geladen. | ![quality-08](./images/quality-08.png) |
| 9 | Die Analyse schlug zunächst fehl, da keine Berechtigung zur Auswertung des Projekts vorlag. Ein Hinweis auf fehlende Autorisierung wurde angezeigt. | ![quality-09](./images/quality-09.png) |
| 10 | Die Projektberechtigungen wurden in SonarQube überprüft und so angepasst, dass autorisierte Benutzer die Analyse ausführen dürfen. | ![quality-10](./images/quality-10.png) |
| 11 | Dann habe icg SonarQube-Analyse erneut ausgeführt – diesmal erfolgreich. Die Meldung `EXECUTION SUCCESS` bestätigt den erfolgreichen Abschluss. | ![quality-11](./images/quality-11.png) |
| 12 | In SonarQube wurde die Auswertung angezeigt: Das Projekt hat das Quality Gate bestanden. Die Übersicht zeigt z. B. 49.4 % Testabdeckung und 0 % Duplikationen. | ![quality-12](./images/quality-12.png) |
| 13 | Unter „Issues“ in SonarQube wurden konkrete Verbesserungsvorschläge sichtbar, z. B. Namenskonventionen bei Package-Namen. Diese wurden dann umgesetzt. | ![quality-13](./images/quality-13.png) |
| 14 | Beim Öffnen der `build.gradle`-Datei in VS Code hat die Java-Extension von Red Hat um Erlaubnis für automatische Refactorings gebeten. | ![quality-14](./images/quality-14.png) |
| 15 | In der Datei `build.gradle` wurden die notwendigen Plugins wie `jacoco` und `org.sonarqube` definiert. Ausserdem wurde der Projektname gesetzt. | ![quality-15](./images/quality-15.png) |
| 16 | Anschliessend habe ich erneut ein `git pull --rebase` ausgeführt, um die lokalen Änderungen mit dem Remote-Branch zu synchronisieren. | ![quality-16](./images/quality-16.png) |
| 17 | Der SonarScanner-Befehl wurde angepasst und erneut ausgeführt. Dabei wurden zusätzliche Parameter übergeben wie z. B. `sonar.token` und `sonar.java.binaries`. | ![quality-17](./images/quality-17.png) |
| 18 | Die Analyse schlug diesmal auch fehl, da die definierten Qualitätsregeln nicht erfüllt wurden. Das Quality Gate wurde als „Failed“ angezeigt. | ![quality-18](./images/quality-18.png) |
| 19 | Nach einem erfolgreichen Push via Git (`git push -u origin main`) wurde der Branch korrekt auf GitHub synchronisiert. | ![quality-19](./images/quality-19.png) |
| 20 | Nach weiteren Anpassungen konnte die Analyse erneut erfolgreich durchgeführt werden. SonarQube meldete „Passed“ für das Quality Gate. | ![quality-20](./images/quality-20.png) 
| 21 | Für das Frontend-Projekt wurde in SonarQube ein neuer Token generiert. | ![quality-21](./images/quality-21.png) |
| 22 | Die SonarScanner-Konfiguration für das Frontend-Projekt wurde vorbereitet. | ![quality-22](./images/quality-22.png) |
| 23 | Die Analyse des Frontends war erfolgreich – erneut wurde „EXECUTION SUCCESS“ gemeldet. | ![quality-23](./images/quality-23.png) |
| 24 | In der Selenium IDE wurde ein einfacher Test aufgezeichnet, der eine Website öffnet und auf einen Link klickt. | ![quality-24](./images/quality-24.png) |
| 25 | Das Ergebnis der Analyse für das Frontend wurde im SonarQube-Dashboard angezeigt – das Quality Gate wurde bestanden. | ![quality-25](./images/quality-25.png) |
| 26 | Die Selenium IDE begrüsst die Nutzerin und bietet Optionen zum Erstellen oder Öffnen eines Projekts. | ![quality-26](./images/quality-26.png) |
| 27 | Es wurde ein neues Projekt in Selenium IDE erstellt mit dem Namen `SeleniumTest`. | ![quality-27](./images/quality-27.png) |
