# Zählerbuch Strom

Eine kleine Web-App zum Ablesen des Stromzählers. Sie braucht kein Konto, keinen Server und kein Claude. Alle Daten bleiben auf dem Gerät der jeweiligen Person.

## Inhalt dieses Ordners

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App (Design, Rechnung, Anleitung) |
| `manifest.webmanifest` | Damit man die App auf dem Handy installieren kann |
| `sw.js` | Damit die App auch ohne Internet startet |
| `icon*.png`, `icon.svg` | App-Symbol |

## Weitergeben an Freunde und Familie

Damit die App auf allen Geräten läuft und sich auf dem Handy installieren lässt, muss der Ordner einmal ins Internet. Danach verschickst du nur noch den Link.

### Möglichkeit 1: Netlify Drop (am einfachsten, ca. 2 Minuten)
1. https://app.netlify.com/drop öffnen und ein kostenloses Konto anlegen.
2. Den ganzen Ordner `zaehlerbuch-app` auf die Seite ziehen.
3. Du bekommst einen Link wie `https://zaehlerbuch-xyz.netlify.app`. Diesen Link verschickst du.

### Möglichkeit 2: GitHub Pages
1. Neues Repository auf GitHub anlegen und die Dateien hochladen.
2. Unter *Settings → Pages* als Quelle den Branch `main` wählen.
3. Der Link lautet dann `https://<dein-name>.github.io/<repository>/`.

### Möglichkeit 3: Nur die Datei verschicken
`index.html` per Mail schicken und am Computer im Browser öffnen. Das funktioniert, aber ohne Installation und ohne Offline-Modus. Auf dem Handy ist das nicht empfehlenswert, weil Safari Daten aus lokalen Dateien nicht zuverlässig behält.

## Gut zu wissen

- **Jede Person hat ihre eigenen Daten.** Auch wenn alle denselben Link nutzen, sieht niemand die Daten der anderen.
- **Sicherung:** In der App unter *Mehr → Sicherung speichern*. Mit dieser Datei zieht man auf ein neues Gerät um.
- **iPhone:** Die App unbedingt über *Teilen → Zum Home-Bildschirm* installieren. Sonst kann Safari die Daten löschen, wenn die Seite einige Wochen nicht geöffnet wurde.
- **Updates:** Die neuen Dateien unbedingt an **derselben Adresse** hochladen. Bei Netlify: Site öffnen → *Deploys* → Ordner in das Feld ziehen. Die Daten der Nutzer bleiben dann erhalten. Ein neuer Netlify-Drop erzeugt eine neue Adresse, und dort sind die Daten **nicht** vorhanden (sie hängen an der Adresse). Im Zweifel vorher eine Sicherung speichern und danach laden.
- **Ältere Sicherungen** (auch aus der ersten Version) werden beim Laden automatisch ins neue Vertragsformat umgewandelt.
- **Datenformat der Sicherung:** JSON mit `profil`, `vertraege` (Anbieter, Laufzeit, Frist, Bonus, Preise, Checkliste) und `readings` (Datum + Zählerstand). Eine CSV mit den Spalten `Datum;Zählerstand` lässt sich ebenfalls laden.
