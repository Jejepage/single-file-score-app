# Spezifikation: Punktestand

## 1. Ziel

Eine einfache mobile Web-App zur Verwaltung von Spielständen. Die App ist für die Bedienung auf dem iPhone optimiert, läuft vollständig im Browser und benötigt weder Frameworks noch externe Abhängigkeiten.

## 2. Technischer Rahmen

- Die vollständige App-Logik und Gestaltung befinden sich in einer einzelnen `index.html`.
- HTML, CSS und JavaScript sind direkt in dieser Datei eingebettet.
- Das Home-Bildschirm-Icon liegt separat als `apple-touch-icon.png` vor.
- Es gibt keinen Build-Schritt und keine Server-Komponente.
- Das aktuelle Spiel wird im `localStorage` des jeweiligen Browsers gespeichert.
- Die App wird als statische Website über GitHub Pages bereitgestellt.

## 3. Spiel einrichten

- Beim ersten Start sind Elly, Lisi, Julien, Anne und Joe voreingestellt.
- Über „Spieler hinzufügen“ können Spieler frei hinzugefügt werden.
- Namen können bearbeitet und Spieler wieder entfernt werden.
- Für den Spielstart sind mindestens zwei Spieler mit unterschiedlichen, nicht leeren Namen erforderlich.
- Es stehen die Vorlagen „Eigenes Spiel“, „FLIP 7“ und „SKYJO“ zur Verfügung.
- FLIP 7 verwendet 200 Punkte, automatisches Spielende und die höchste Punktzahl als Gewinnerregel.
- SKYJO verwendet 100 Punkte, automatisches Spielende und die niedrigste Punktzahl als Gewinnerregel.
- Beim eigenen Spiel lassen sich Zielwert, Gewinnerregel und automatisches oder manuelles Spielende frei bestimmen.
- Das Ändern einer Vorlageneinstellung wechselt automatisch zum eigenen Spiel, ohne die Spielerliste zu verändern.

## 4. Punkte erfassen

- Jeder Spieler besitzt einen sichtbaren Gesamtpunktestand.
- Für jeden Spieler wird pro Runde eine freie ganze Zahl eingegeben.
- Positive, negative und `0` Punkte sind erlaubt; ein `±`-Button wechselt zuverlässig das Vorzeichen.
- „Runde werten“ addiert alle Rundenwerte gleichzeitig zu den Gesamtständen.
- Alle Spieler benötigen vor der Wertung einen expliziten Wert, damit keine Eingabe versehentlich ausgelassen wird.
- Ein Spieler wird optisch hervorgehoben, sobald sein Punktestand die Zielmarke erreicht oder überschritten hat.
- Hinter jedem Spielernamen zeigt ein Fortschrittsbalken den Anteil des aktuellen Punktestands an der Zielmarke; negative Werte beginnen bei 0 %, Werte ab der Zielmarke enden bei 100 %.
- Ein Rundenzähler beginnt bei 1 und steigt nach jeder vollständigen Wertung.

## 5. Rückgängig

- Es kann genau die letzte vollständig gewertete Runde rückgängig gemacht werden.
- Dabei werden alle Gesamtstände und der Rundenzähler zurückgesetzt und die entfernten Rundenwerte wieder in die Eingabefelder eingesetzt.
- Nach dem Rückgängigmachen ist die Funktion deaktiviert, bis erneut eine Runde gewertet wurde.
- Die letzte rückgängig machbare Runde wird zusammen mit dem aktuellen Spiel gespeichert.

## 6. Runde und Spielende

- Die Gesamtstände bleiben zwischen den Runden bestehen.
- Bei automatischem Spielende wird die Zielbedingung erst nach der gemeinsamen Wertung aller Spieler geprüft.
- Bei SKYJO beendet eine Runde das Spiel, sobald mindestens ein Spieler 100 Punkte erreicht; die niedrigste Gesamtpunktzahl gewinnt.
- Bei FLIP 7 beendet eine Runde das Spiel, sobald mindestens ein Spieler 200 Punkte erreicht; die höchste Gesamtpunktzahl gewinnt. Bei Gleichstand an der Spitze wird weitergespielt.
- Ein eigenes Spiel verwendet die konfigurierte Gewinner- und Endregel.
- Das Spiel kann unabhängig davon jederzeit manuell beendet werden; offene, noch nicht gewertete Eingaben werden dabei ignoriert.
- Die Endansicht zeigt eine nach Punkten sortierte Rangliste.
- Die Sortierung richtet sich nach der gewählten Gewinnerregel; Gleichstände werden gemeinsam ausgezeichnet.
- Die Endansicht zeigt die Anzahl der gespielten Runden und ermöglicht die Korrektur der letzten Runde.
- „Neue Partie mit gleichen Spielern“ setzt Punkte und Rundenzähler zurück, behält aber Spieler und Einstellungen.
- „Neues Spiel einrichten“ öffnet die Einrichtung mit den Standardspielern.

## 7. Speicherung

- Vorlage, Regeln, Zielmarke, Spielernamen, Punktestände, Rundenzähler, offene Rundeneingaben und letzte gewertete Runde werden automatisch gespeichert.
- Nach Schließen oder Neuladen des Browsers wird das aktuelle Spiel wiederhergestellt.
- Es gibt kein Archiv früherer Spiele und keine Synchronisation zwischen Geräten.
- Die Speicherung gilt nur für den jeweiligen Browser und die jeweilige Web-Adresse.
- Die gewählte Designvariante wird als lokale Darstellungspräferenz unabhängig vom Spielstand gespeichert.

## 8. Gestaltung und Bedienbarkeit

- Mobile-First-Oberfläche im Stil einer nativen iPhone-App.
- Große Touch-Ziele, gut lesbare Typografie und deutliche Rückmeldungen.
- Die laufenden Punktestände erscheinen als kompakte einzeilige Liste, damit möglichst viele Spieler gleichzeitig sichtbar bleiben.
- Ein Umschalter wechselt zwischen dem ruhigen Standarddesign und einem verspielten, farbenfroheren Design mit individuellen Spielerfarben.
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
- Neue Spiele enthalten die fünf festgelegten Standardspieler, die entfernt oder erweitert werden können.
- FLIP 7 und SKYJO setzen Zielwert und Gewinnerregel korrekt.
- Positive und negative Punkte werden korrekt addiert.
- Eine Runde wird nur mit vollständigen Eingaben für alle Spieler gewertet.
- Rückgängig betrifft genau die letzte vollständige Runde und reduziert den Rundenzähler.
- SKYJO ermittelt nach Erreichen der Zielmarke den niedrigsten Gesamtstand als Gewinner.
- FLIP 7 ermittelt nach Erreichen der Zielmarke den höchsten eindeutigen Gesamtstand als Gewinner.
- Der Nutzer kann das Spiel weiterhin manuell beenden und erhält eine nach der Gewinnerregel sortierte Rangliste.
- Der aktuelle Stand bleibt nach einem Neuladen erhalten.
