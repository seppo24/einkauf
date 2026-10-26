# Einkauf-App – Einrichtung (einmalig, ca. 15 Minuten)

Die App besteht aus 5 Dateien: `index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`.
Sie liegt auf GitHub Pages, die Daten liegen in einer einzelnen Datei in eurem gemeinsamen Dropbox-Ordner.

## 1. Auf GitHub hochladen

1. Auf github.com einloggen → oben rechts **+ → New repository**.
2. Name: `einkauf` · **Public** · Haken bei „Add a README“ weglassen → **Create repository**.
3. **uploading an existing file** anklicken, die 5 Dateien (ZIP vorher entpacken) hineinziehen → **Commit changes**.
4. **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main` / `/ (root)` → **Save**.
5. Nach 1–2 Minuten ist die App erreichbar unter `https://DEIN-GITHUB-NAME.github.io/einkauf/`.

(Im öffentlichen Repository liegt nur der App-Code, keine Daten und keine Schlüssel.)

## 2. Dropbox-App anlegen (gibt der Einkauf-App Zugriff auf die Datei)

1. Auf https://www.dropbox.com/developers/apps → **Create app**.
2. **Scoped access** → **Full Dropbox** → Name z. B. `einkauf-seppo` → **Create app**.
3. Reiter **Permissions**: Haken bei `files.metadata.read`, `files.content.read`, `files.content.write` → **Submit**.
4. Reiter **Settings**:
   - **Redirect URIs**: `https://DEIN-GITHUB-NAME.github.io/einkauf/` eintragen → **Add**.
   - Bei **Development users** → **Enable additional users**, damit auch deine Frau sich verbinden kann.
   - Den **App key** kopieren.

## 3. In der App verbinden (auf jedem Handy)

1. App-Adresse in Chrome öffnen, Namen eingeben.
2. **Mehr → Einstellungen**: App-Key einfügen, bei „Datei in Dropbox“ den Pfad im **gemeinsamen Ordner** eintragen, z. B. `/Gemeinsam/Einkauf/einkauf.json` (der Ordner muss existieren, die Datei legt die App selbst an).
   Wichtig: Der Pfad muss so stimmen, wie der gemeinsame Ordner in *deinem* Dropbox-Account heißt. Bei deiner Frau kann er anders heißen.
3. **Mit Dropbox verbinden** → bei Dropbox „Zulassen“.
4. Oben rechts zeigt ein Punkt den Status: grün = synchronisiert, gelb = läuft, rot = Fehler (antippen für Details).

## 4. Als App installieren (Android)

Chrome → Menü ⋮ → **Zur Startseite hinzufügen / App installieren**.

## 5. Claude für Foto- und Link-Import (optional)

**Mehr → Einstellungen → Claude**: API-Key eintragen (wird nur auf dem Gerät gespeichert, nicht in Dropbox).
Ohne Key funktionieren Links nur bei Seiten, die ihr Rezept maschinenlesbar anbieten; Fotos brauchen den Key immer.

## Updates einspielen

Neue `index.html` (und `sw.js`) im GitHub-Repository hochladen (**Add file → Upload files**, gleiche Namen überschreiben).
Auf den Handys: **Mehr → Info → App neu laden**.

## Hinweise

- Die App funktioniert auch ohne Empfang; Änderungen werden synchronisiert, sobald wieder Verbindung besteht.
- Es gibt keine Push-Benachrichtigungen. Die Rückmeldung bei der Wochenplanung erscheint als Hinweis oben und als roter Punkt beim Tab „Woche“, sobald die App geöffnet wird (Abgleich alle 20 Sekunden bei geöffneter App).
- Der Versionsverlauf steht in der App unter **Mehr → Info**.
