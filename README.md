# VerkehrsRadar Deutschland – GitHub Pages

## Upload mit dem iPhone oder PC

1. Auf GitHub **New repository** auswählen und z. B. `verkehrsradar` nennen; **Public** wählen (bei GitHub Free für Pages erforderlich).
2. Die **Inhalte dieses ZIP-Archivs entpacken**. Die Dateien müssen im Repository-Hauptverzeichnis liegen, insbesondere `index.html`, `manifest.webmanifest`, `sw.js` und der Ordner `icons/`. **Nicht** die ZIP-Datei allein hochladen.
3. Im Repository **Add file → Upload files** wählen, die entpackten Dateien samt Ordnerstruktur hochladen und **Commit changes** auswählen. Auf dem iPhone ist der Upload ganzer Ordner ggf. umständlich; am Computer oder mit Git ist es einfacher.
4. Unter **Settings → Pages → Build and deployment → Source: Deploy from a branch**, Branch **main**, Ordner **/(root)** und **Save** wählen.
5. Nach dem Deployment die URL `https://DEIN-NAME.github.io/verkehrsradar/` in Safari öffnen. Die tatsächliche URL steht unter **Settings → Pages**.
6. In Safari **Teilen → Zum Home-Bildschirm → Hinzufügen** auswählen. Standort freigeben und gewünschte Datenquellen einstellen.

## Was enthalten ist

- GPS mit Einwilligung, Suchradius 1–100 km und OpenStreetMap/Leaflet-Karte
- Autobahn-GmbH-Meldungen und optional TomTom Traffic API
- manuelle und einstellbare automatische Aktualisierung, Filter
- lokale Hinweise und akustischer Warnton bei neu erkannten Meldungen (sofern Browser die Wiedergabe erlaubt)
- Manifest, App-Symbol und Service Worker für installierbare Webapp

## Wichtige Grenzen

- **Keine garantierten iPhone-Hintergrundwarnungen.** Der Service Worker dient nur dem Offline-App-Shell-Cache; er implementiert **kein Web Push**. Browser-Benachrichtigungen via `new Notification()` aus der bestehenden App können auf iOS trotz Installation scheitern. Echte Push-Warnungen bei geschlossener App erfordern Push-Subscription, Server und Push-Versand.
- **API-Schlüssel:** Der TomTom-Schlüssel wird clientseitig verwendet und ist damit für Besucher der öffentlichen Seite prinzipiell einsehbar. Keinen geheim zu haltenden Schlüssel öffentlich eintragen. Für sicheren Betrieb ist ein serverseitiger Proxy mit Quoten-/Zugriffsschutz sinnvoll.
- **Verfügbarkeit:** Externe APIs, CORS, Overpass-Abfragen und API-Kontingente können ausfallen. Kein vollständiger Live-Test durchgeführt.
- **Deutschlandfilter:** Die bestehende Anwendung verwendet eine grobe geografische Begrenzungsbox, keine exakte Staatsgrenze.
- **Offline:** Nur App-Oberfläche und Icons sind offline zwischengespeichert. Kartenkacheln und aktuelle Meldungen brauchen Internet.
- **Standort:** GitHub Pages HTTPS ermöglicht GPS-Anfragen, sofern Safari die Berechtigung erteilt.

## Dateien

`index.html` – Anwendung; `manifest.webmanifest` – PWA-Konfiguration; `sw.js` – Offline-App-Shell; `icons/` – App-Symbole.

## Weiterführende Dokumentation

- https://docs.github.com/en/pages/quickstart
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://developer.apple.com/documentation/usernotifications/sending-web-push-notifications-in-web-apps-and-browsers

## Version ohne Push-Benachrichtigungen
Diese Version enthält keine Browser-Push-Benachrichtigungen oder Berechtigungsabfragen. Akustische Warnungen für neue Staus und Unfälle sind bei geöffneter App weiterhin möglich.


## Reparatur v3 – iPhone
- Auf kleinen Bildschirmen stehen die Standort- und Aktualisieren-Schaltflächen vor der Karte, statt erst darunter.
- Nach dem GPS-Tippen erscheint eine sichtbare Statusmeldung inklusive konkreter Fehlermeldung.
- Alternativ kann der Standort durch Tippen auf die Deutschlandkarte ausgewählt werden.
- Der Service-Worker-Cache ist auf v3 aktualisiert. Push-Benachrichtigungen sind nicht enthalten.
- Ersetze bei GitHub alle gleichnamigen Dateien (insbesondere `index.html` und `sw.js`).
- Die tatsächliche GPS-Funktion muss auf dem iPhone in Safari getestet werden.

## Version 4 – Autobahn-API-Diagnose
- Autobahn-Endpunkte entsprechen der dokumentierten API.
- Drei Overpass-Server werden nacheinander für die Erkennung naher Autobahnen versucht.
- Manuelle Autobahnnummern (z. B. A9, A14, A38) ermöglichen den Abruf ohne Overpass.
- Status zeigt Autobahnen, Rohmeldungen, gültige Koordinaten und API-Fehler.
- Nur Meldungen mit Koordinaten im eingestellten Radius werden angezeigt.
- Keine Push-Benachrichtigungen.
- Ersetzt auf GitHub mindestens index.html und sw.js.
