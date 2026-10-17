# DeutschMaster — offline-Paket / offline package

## Inhalt / Contents
- `index.html` — die App / the app (one file, ~1.4 MB)
- `sw.js` — Service Worker (Offline-Betrieb / offline mode)
- `manifest.webmanifest`, `icon-*.png` — Installation auf dem Startbildschirm / home-screen install

## Online stellen (einmalig) / Put it online (once)
Die App muss über eine **https-Adresse** laufen, sonst funktionieren Offline-Modus und Installation nicht.
The app must be served over **https**, otherwise offline mode and installation do not work.

1. **Netlify (am einfachsten / easiest):** app.netlify.com/drop → den ganzen Ordner hineinziehen / drag the whole folder in.
2. **GitHub Pages:** neues Repository → alle 6 Dateien hochladen → Settings → Pages → Branch `main`, Ordner `/ (root)`.
3. Jeder andere Webspace mit https geht auch / any other https web host works too.

## Auf dem Handy installieren / Install on the phone
- **Android (Chrome):** Menü ⋮ → „App installieren“ / „Zum Startbildschirm hinzufügen“.
- **iPhone (Safari):** Teilen-Symbol → „Zum Home-Bildschirm“.
Nach dem ersten Laden funktioniert alles außer den KI-Funktionen auch ohne Internet.
After the first load everything except the AI features works without internet.

## Neue Version veröffentlichen / Publishing an update
`index.html` ersetzen **und** in `sw.js` die Zeile `const CACHE='deutschmaster-v1';` auf `v2`, `v3` … erhöhen,
sonst zeigen Handys, die die App schon haben, weiter die alte Version.
Replace `index.html` **and** raise the number in `const CACHE='deutschmaster-v1';` in `sw.js`, otherwise phones keep showing the old version.

## Wichtig / Important
- Der Lernfortschritt liegt nur im Browser des Handys. Im Lernpfad unten: **Sichern** (Datei) und **Wiederherstellen**.
  Progress lives only in the phone's browser. Use *Sichern / Wiederherstellen* at the bottom of the Lernpfad.
- KI-Funktionen: eigener API-Schlüssel nötig (Tab KI → ⚙️ KI-Einstellungen). Der Schlüssel bleibt auf dem Gerät.
  AI features need your own API key (KI tab → settings). The key stays on the device.
- Die Inhalte (Lektionen, Fragen, Texte) sollte vor dem Einsatz im Unterricht eine Deutschlehrkraft prüfen — siehe `Pruefliste-Inhalte.xlsx`.
  A German teacher should review the content before classroom use — see `Pruefliste-Inhalte.xlsx`.
