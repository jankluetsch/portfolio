# Portfolio-Website — Setup & Deployment

Diese Anleitung beschreibt, wie du den Inhalt dieses Ordners in dein bestehendes
GitHub-Repo bringst und mit Claude Code weiterarbeitest.

## Inhalt dieses Ordners

- `index.html` — die aktuelle, fertige Version der Seite
- `impressum.html`, `datenschutz.html` — Rechtstexte
- `Lebenslauf_JanKluetsch.pdf` — wird von der Seite verlinkt
- `CLAUDE.md` — Projektkontext für Claude Code (Stil, Fakten, CI)
- `assets/fonts/` — enthält nur einen Platzhalter; hier kommen die Schriften rein

## Schritt 1 — Repo lokal klonen

Du hast das Portfolio-Repo auf GitHub bereits angelegt (mit der ersten HTML-Version).
Hole es auf deinen Rechner. Im Terminal, im Ordner wo das Projekt liegen soll
(z.B. in "Dokumente"):

    git clone https://github.com/DEINUSERNAME/DEINREPONAME.git

Das erstellt einen Ordner mit dem Repo-Namen. Dieser Ordner ist bereits mit
GitHub verbunden — eine separate "Git-Verbindung" musst du nicht einrichten.

## Schritt 2 — Dateien austauschen

Kopiere den gesamten Inhalt dieses website_build-Ordners in den geklonten
Repo-Ordner. Die alte erste Version von index.html wird dabei überschrieben,
das ist gewollt.

## Schritt 3 — Mit Claude Code weiterarbeiten

Im Terminal in den Repo-Ordner wechseln und Claude Code starten:

    cd DEINREPONAME
    claude

Claude Code liest automatisch die CLAUDE.md und kennt damit den Projektkontext.
Du kannst direkt Änderungswünsche formulieren.

## Schritt 4 — Veröffentlichen

Wenn eine Änderung fertig ist, übernimmt Claude Code das Veröffentlichen, oder du
machst es selbst:

    git add .
    git commit -m "Beschreibung der Aenderung"
    git push

GitHub Pages deployt automatisch. Nach ein bis zwei Minuten ist die Seite aktuell.

## Schriften nachrüsten (optional, empfohlen)

Die Seite nutzt Fraunces und Inter Tight. Solange die Schriftdateien fehlen,
greift ein System-Fallback, die Seite funktioniert, sieht nur etwas weniger
fein aus.

So rüstest du die echten Schriften nach:

1. Fraunces: https://fonts.google.com/specimen/Fraunces herunterladen
2. Inter Tight: https://fonts.google.com/specimen/Inter+Tight herunterladen
3. Die variablen woff2-Dateien als fraunces.woff2 und inter-tight.woff2
   in assets/fonts/ ablegen
4. Die Datei assets/fonts/PLATZHALTER.txt kann dann gelöscht werden
5. Committen und pushen

Falls keine fertigen woff2-Dateien dabei sind, kann Claude Code die ttf-Dateien
in woff2 konvertieren, einfach danach fragen.

## Hinweis

index.html enthält die Bilder als Base64 direkt eingebettet, deshalb ist die
Datei relativ groß (rund 540 KB). Das ist Absicht: die Seite funktioniert so
ohne separate Bilddateien.
