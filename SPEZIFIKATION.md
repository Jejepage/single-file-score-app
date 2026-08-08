# Spezifikation: Punktestand

## 1. Ziel

Eine einfache mobile Web-App zur Verwaltung von Spielständen. Die App ist für die Bedienung auf dem iPhone optimiert, läuft vollständig im Browser und benötigt weder Frameworks noch externe Abhängigkeiten.

## 2. Technischer Rahmen

- Die vollständige App befindet sich in einer einzelnen `index.html`.
- HTML, CSS und JavaScript sind direkt in dieser Datei eingebettet.
- Es gibt keinen Build-Schritt und keine Server-Komponente.
- Das aktuelle Spiel wird im `localStorage` des jeweiligen Browsers gespeichert.
- Die App wird als statische Website über GitHub Pages bereitgestellt.

## 3. Spiel einrichten

- Beim ersten Start sind keine Spieler voreingestellt.
- Über „Spieler hinzufügen“ können Spieler frei hinzugefügt werden.
- Namen können bearbeitet und Spieler wieder entfernt werden.
- Für den Spielstart sind mindestens zwei Spieler mit unterschiedlichen, nicht leeren Namen erforderlich.
- Es kann eine positive Zielpunktzahl festgelegt werden.
- Die Zielpunktzahl ist eine Zielmarke und kein automatisches Spielende.

## 4. Punkte erfassen

- Jeder Spieler besitzt einen sichtbaren Gesamtpunktestand.
- Punkte werden als freie ganze Zahl eingegeben und zum aktuellen Stand addiert.
- Positive und negative Werte sind erlaubt; `0` wird nicht als Änderung akzeptiert.
- Ein Spieler wird optisch hervorgehoben, sobald sein Punktestand die Zielmarke erreicht oder überschritten hat.
- Das Spiel läuft nach Erreichen der Zielmarke weiter.

## 5. Rückgängig

- Es kann genau die letzte Punkteingabe rückgängig gemacht werden.
- Nach dem Rückgängigmachen ist die Funktion deaktiviert, bis eine neue Punkteingabe erfolgt.
- Der letzte rückgängig machbare Schritt wird zusammen mit dem aktuellen Spiel gespeichert.

## 6. Runde und Spielende

- „Neue Runde“ setzt alle Punktestände auf `0`.
- Spielernamen und Zielmarke bleiben bei einer neuen Runde erhalten.
- Während eines laufenden Spiels muss das Zurücksetzen der Runde bestätigt werden.
- Das Spiel wird ausschließlich durch den Nutzer über „Spiel beenden“ beendet.
- Die Endansicht zeigt eine nach Punkten sortierte Rangliste.
- Die höchste Punktzahl gewinnt; bei gleicher Höchstpunktzahl werden mehrere Gewinner angezeigt.
- Aus der Endansicht kann eine neue Runde mit denselben Spielern gestartet werden.
- „Neues Spiel einrichten“ löscht den aktuellen Stand und öffnet eine leere Spielereinrichtung.

## 7. Speicherung

- Zielmarke, Spielernamen, Punktestände, aktueller Bildschirm und letzter Rückgängig-Schritt werden automatisch gespeichert.
- Nach Schließen oder Neuladen des Browsers wird das aktuelle Spiel wiederhergestellt.
- Es gibt kein Archiv früherer Spiele und keine Synchronisation zwischen Geräten.
- Die Speicherung gilt nur für den jeweiligen Browser und die jeweilige Web-Adresse.

## 8. Gestaltung und Bedienbarkeit

- Mobile-First-Oberfläche im Stil einer nativen iPhone-App.
- Große Touch-Ziele, gut lesbare Typografie und deutliche Rückmeldungen.
- Unterstützung für iPhone Safe Areas, Hellmodus, Dunkelmodus und reduzierte Animationen.
- Eingabefelder vermeiden den automatischen Safari-Zoom.
- Die Oberfläche bleibt auch auf größeren Displays responsiv.

## 9. Veröffentlichung

- Repository: `Jejepage/single-file-score-app`
- Produktionsbranch: `main`
- GitHub-Pages-Quelle: `/` im Branch `main`
- Öffentliche Adresse: <https://jejepage.github.io/single-file-score-app/>

## 10. Abnahmekriterien

- Die App funktioniert ohne externe Netzwerkressourcen.
- Ein Spiel kann mit mindestens zwei frei benannten Spielern gestartet werden.
- Positive und negative Punkte werden korrekt addiert.
- Rückgängig betrifft nur die letzte Eingabe.
- Eine neue Runde behält Namen und Zielmarke und setzt alle Punkte auf `0`.
- Das Erreichen der Zielmarke beendet das Spiel nicht.
- Der Nutzer kann das Spiel manuell beenden und erhält eine korrekte Rangliste.
- Der aktuelle Stand bleibt nach einem Neuladen erhalten.
