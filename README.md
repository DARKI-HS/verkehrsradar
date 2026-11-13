# VerkehrsRadar Deutschland V9 – iPhone-Anpassung

- Drei kompakte Schaltflächen über der Karte, ohne überlappende Beschriftungen.
- Sechs Kategorienfilter vollständig sichtbar in zwei Reihen mit je drei Buttons.
- TomTom-Abfragen verwenden `timeValidityFilter=present`; diese Meldungen werden rot als „Aktuell laut TomTom“ gekennzeichnet. Dies ist die Aussage der Datenquelle, keine unabhängige Bestätigung.
- Eindeutig künftig beginnende Meldungen bleiben gelb, unklare Zeiträume grau.
- Karte oben fixiert, Meldungsliste darunter separat scrollbar.
- Einstellungen, GPS, TomTom und App-Symbol bleiben erhalten. Keine Push-Benachrichtigungen.

## Upload
Alle Dateien und den Ordner `icons` in das bestehende GitHub-Pages-Repository hochladen und vorhandene Dateien ersetzen. Insbesondere `index.html` und `sw.js` aktualisieren. Danach `https://darki-hs.github.io/verkehrsradar/?v=9` in Safari öffnen.

## Prüfung
JavaScript-Syntax geprüft. Tatsächliche iPhone-Darstellung und Live-API-Antworten sind nicht vor Ort getestet.
