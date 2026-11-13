# VerkehrsRadar Deutschland – Version 5

## Änderungen
- Karte dauerhaft oben sichtbar, Meldungen in eigenem Scrollbereich darunter.
- Button „⚙ Einstellungen“ öffnet alle Einstellungen separat.
- Roter Rahmen: anhand ausdrücklich genannter Beginn-/Enddaten aktuell.
- Gelber Rahmen: ausdrücklich genannter Beginn liegt in der Zukunft.
- Grauer Rahmen: Zeitstatus aus den gelieferten Angaben nicht zuverlässig bestimmbar.
- Kein Browser-Push; akustische Warnungen bei geöffneter App bleiben erhalten.
- Manuelle Autobahnwahl als Ausweichmöglichkeit, wenn Overpass ausfällt.

## Upload
In https://github.com/DARKI-HS/verkehrsradar die Dateien im Repository-Stamm ersetzen, insbesondere `index.html` und `sw.js`. Alle übrigen Dateien und den Ordner `icons` beibehalten.
Nach dem Commit https://darki-hs.github.io/verkehrsradar/?v=5 in Safari öffnen.
Bei älterer installierter PWA: App schließen und neu öffnen; bei Bedarf Safari-Websitedaten/Cache prüfen.

## Grenzen
Der Status aktuell/geplant wird aus Datumsangaben der API-Beschreibung abgeleitet und nicht extern verifiziert. Fehlende/uneindeutige Zeiträume bleiben grau. Live-Funktion auf dem iPhone wurde nicht getestet.
