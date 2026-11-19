# Book Library – als Web-App aufs iPhone

Dieser Ordner ist eine fertige Web-App (PWA). Sie braucht keinen Server mit Datenbank: Du lädst die Dateien irgendwo hoch, wo statische Webseiten gehostet werden, und öffnest sie dann im Safari.

## Inhalt

| Datei | Wofür |
|---|---|
| `index.html` | Die App selbst |
| `manifest.webmanifest` | Name, Farben und Icons für den Home-Bildschirm |
| `sw.js` | Offline-Unterstützung: Die App öffnet auch ohne Internet |
| `icons/` | App-Icons (iPhone, Android, Browser-Tab) |

## 1. Online stellen (eine Variante wählen)

**Variante A – Netlify Drop (am einfachsten, ca. 2 Minuten)**
1. Gehe auf https://app.netlify.com/drop und melde dich mit einem kostenlosen Konto an.
2. Entpacke die ZIP-Datei und ziehe den Ordner `book-library` in das Fenster.
3. Netlify zeigt dir eine Adresse wie `https://irgendwas.netlify.app`. Unter „Site settings“ kannst du den Namen ändern, z. B. `chantals-books.netlify.app`.

**Variante B – GitHub Pages**
1. Neues Repository auf GitHub anlegen und den *Inhalt* des Ordners `book-library` hochladen (`index.html` muss direkt im Hauptverzeichnis liegen).
2. Unter *Settings → Pages* als Quelle „Deploy from a branch“, Branch `main`, Ordner `/ (root)` wählen.
3. Nach ca. einer Minute ist die App unter `https://DEINNAME.github.io/REPO-NAME/` erreichbar.

Wichtig: Die Adresse muss mit **https** beginnen, sonst funktionieren Offline-Modus und Installation nicht.

## 2. Aufs iPhone holen

1. Die Adresse in **Safari** öffnen (nicht Chrome).
2. Unten auf **Teilen** tippen, dann **„Zum Home-Bildschirm“**.
3. Die App erscheint mit dem grünen Buch-Icon und öffnet ohne Browserleiste.

## 3. Deine Bücher aus dem Claude-Artefakt mitnehmen

Die Web-App hat einen eigenen Speicher. Deine bisherigen Einträge holst du so herüber:

1. Im Claude-Artefakt oben rechts auf das **Archiv-Symbol** tippen → **„Save backup file“** (oder „Copy JSON“).
2. In der neuen Web-App ebenfalls das **Archiv-Symbol** öffnen.
3. **„Replace library“** wählen und die Datei mit „Choose JSON file“ auswählen (oder den kopierten Text einfügen und „Import pasted backup“ tippen).

„Replace“ ersetzt die automatisch angelegte Startliste durch deinen Stand aus dem Artefakt, damit nichts doppelt ist.

## Gut zu wissen

- **Cover & Buchdetails:** In der Web-App funktioniert die Suche über Open Library. Cover, Erscheinungsjahr, Seitenzahl und Beschreibung werden beim ersten Öffnen automatisch für alle Bücher nachgeladen – nur für leere Felder, deine eigenen Einträge werden nie überschrieben. Was Open Library nicht kennt, bleibt mit Platzhalter, nichts wird erfunden.
- **Wo die Daten liegen:** Nur auf deinem Gerät, im Speicher dieser Web-App. Es gibt keine automatische Synchronisierung zwischen Geräten.
- **Backups:** Mach ab und zu über das Archiv-Symbol ein Backup („Save backup file“), z. B. in die Dateien-App oder iCloud Drive. Wenn du die App vom Home-Bildschirm löschst, löscht iOS auch ihre Daten.
- **Claude-Vorschläge bei der Suche** gibt es nur im Claude-Artefakt. Die Web-App sucht direkt bei Open Library.
- **Updates:** Wenn du später eine neue `index.html` hochlädst, holt sich die App die neue Version beim nächsten Öffnen mit Internet automatisch. Deine Daten bleiben dabei erhalten.
