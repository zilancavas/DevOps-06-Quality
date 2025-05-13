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
| 15 | Anschliessend habe ich erneut ein `git pull --rebase` ausgeführt, um die lokalen Änderungen mit dem Remote-Branch zu synchronisieren. | ![quality-15](./images/quality-15.png) |
| 16 | Der SonarScanner-Befehl wurde angepasst und erneut ausgeführt.  | ![quality-16](./images/quality-16.png) |
| 17 | Die Analyse schlug diesmal auch fehl, da die definierten Qualitätsregeln nicht erfüllt wurden. Das Quality Gate wurde als „Failed“ angezeigt. | ![quality-17](./images/quality-17.png) |
| 18 | Nach einem erfolgreichen Push via Git (`git push -u origin main`) wurde der Branch korrekt auf GitHub synchronisiert. | ![quality-18](./images/quality-18.png) |
| 19 | Nach weiteren Anpassungen konnte die Analyse erneut erfolgreich durchgeführt werden. SonarQube meldete „Passed“ für das Quality Gate. | ![quality-19](./images/quality-19.png) |
| 20 | Dann habe ich ein neues Projekt für das Frontend erstellt auf SolaeQube | ![quality-20](./images/quality-20.png) 
| 21 | Für das Frontend-Projekt wurde in SonarQube ein neuer Token generiert. | ![quality-21](./images/quality-21.png) |
| 22 | Die SonarScanner-Konfiguration für das Frontend-Projekt wurde vorbereitet. | ![quality-22](./images/quality-22.png) |
| 23 | Die Analyse des Frontends war erfolgreich – erneut wurde „EXECUTION SUCCESS“ gemeldet. | ![quality-23](./images/quality-23.png) |
| 24 | Das Quality Gate wurde als „Passed“ angezeigt. | ![quality-24](./images/quality-24.png) |
| 25 | Das Ergebnis der Analyse für das Frontend wurde im SonarQube-Dashboard angezeigt – das Quality Gate wurde bestanden. | ![quality-25](./images/quality-25.png) |
| 26 | Zuletzt habe ich dann in der Selenium IDE wurde einen automatisierten Test aufgezeichnet. Der Test öffnet eine Website (https://example.com), setzt die Fenstergrössw auf 891×608 und klickt auf den Link „More information…“.| ![quality-27](./images/quality-27.png) |


## Fazit

Im Rahmen dieses Lernjournals habe ich zentrale Werkzeuge und Konzepte zur Sicherstellung von Softwarequalität kennengelernt und praktisch angewendet. Besonders im Fokus standen **statische Codeanalyse mit SonarQube**, **lokale Qualitätstools wie HTMLHint** sowie **automatisierte Tests mit Selenium IDE**.
Einige Arbeitsschritte erwiesen sich als herausfordernd – insbesondere:
- Die **Konfiguration von SonarQube** und die richtige Übergabe aller benötigten Parameter an den `sonar-scanner` (z. B. `sonar.token`, `sonar.sources`, `sonar.java.binaries`) war nicht auf Anhieb intuitiv.
- Auch das erste Setup mit dem **Quality Gate**, das beim ersten Durchlauf fehlschlug, erforderte gezielte Anpassungen im Code.
- Die **Synchronisation mit GitHub** sowie Push-Fehler mussten durch `git pull --rebase` aufgelöst werden.

Trotz dieser Herausforderungen konnte ich wichtige Erkenntnisse gewinnen:
- **Qualitätssicherung ist nicht nur ein finaler Schritt, sondern ein integraler Bestandteil** des gesamten Entwicklungsprozesses.
- Tools wie SonarQube helfen dabei, **technische Schulden frühzeitig zu erkennen** und gezielt zu beheben.
- **Automatisierte Tests mit Selenium IDE** bieten einen einfachen Einstieg in die Testautomatisierung und ermöglichen auch ohne tiefes Programmierwissen die Simulation von Benutzerinteraktionen.

Insgesamt hat dieses Lernjournal meine Fähigkeiten zur **Qualitätssicherung im DevOps-Kontext** deutlich gestärkt und mir einen praxisnahen Einblick in professionelle Analyse- und Testmethoden vermittelt.

## Praxisbezug

In meinem Berufsalltag bin ich als Softwareentwicklerin im ABAP-Bereich tätig und damit in der SAP-Entwicklung verankert. Auch dort ist die Qualität des Codes ein zentrales Thema. Allerdings erfolgen die Qualitätskontrollen aktuell manuell: Ich prüfe den Code eigenständig in der Entwicklungsumgebung und achte auf Lesbarkeit, Struktur, Wiederverwendbarkeit und Einhaltung von Konventionen. Das Arbeiten mit SonarQube im Rahmen dieses Lernjournals hat mir einen wertvollen Einblick in automatisierte Qualitätssicherung gegeben. Besonders beeindruckend war, wie schnell und strukturiert Schwachstellen, Code Smells oder Verstösse gegen Standards erkannt und dargestellt werden.




