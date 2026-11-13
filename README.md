# VerkehrsRadar Deutschland V7 – Symbol-Reparatur

- Das Symbol in der Kopfzeile ist direkt in index.html eingebettet und kann deshalb nicht mehr durch einen fehlenden icons-Pfad ausfallen.
- Favicon, Apple-Touch-Icon und Manifest erhalten Versionsparameter, um alte Browser-Caches zu umgehen.
- Service-Worker-Cache auf v7 aktualisiert.
- Alle Funktionen aus V6 einschließlich Kategorienfilter bleiben erhalten.

## GitHub-Upload

Alle Dateien aus dem entpackten ZIP in das Hauptverzeichnis von `DARKI-HS/verkehrsradar` hochladen; den `icons`-Ordner mit den drei PNG-Dateien beibehalten. Besonders `index.html`, `sw.js`, `manifest.webmanifest` ersetzen. Anschließend `https://darki-hs.github.io/verkehrsradar/?v=7` in Safari aufrufen.

Für das Symbol auf dem iPhone-Home-Bildschirm ggf. die alte Home-Bildschirm-Verknüpfung löschen und über Safari → Teilen → Zum Home-Bildschirm neu hinzufügen.

Hinweis: GitHub-Veröffentlichung und iPhone-Darstellung sind nicht live getestet.
