# AI-Augmented PM — Woche 1: Von Interviews zum PRD

Willkommen. Dieses Repository enthält alle Materialien für Woche 1 des Kurses **AI-Augmented Product Management**.

Du lernst in dieser Woche, wie du mit Claude Code aus rohen User-Interviews ein vollständiges PRD und einen klickbaren Prototypen baust — in unter einer Stunde.

---

## Voraussetzungen

Du brauchst nur zwei Dinge:

### 1. Claude Code installieren

Claude Code ist die App, mit der du diesen Kurs durchläufst.

→ Installationsanleitung: [claude.ai/code](https://claude.ai/code)

Folge den Anweisungen auf der Seite für dein Betriebssystem.

### 2. Ein Terminal

- **Mac:** Das Programm heißt **Terminal** — bereits vorinstalliert (Programme → Dienstprogramme → Terminal, oder `Cmd + Leertaste` → "Terminal")
- **Windows:** Suche nach **PowerShell** in der Windows-Suche und öffne es

---

## Installation

### Schritt 1 — Kursordner herunterladen

Gehe auf die Kursseite (den Link hast du per E-Mail erhalten) und klicke auf den grünen **Code**-Button → **Download ZIP**.

![Download ZIP](https://docs.github.com/assets/cb-20363/mw-1440/images/help/repository/code-button.webp)

Entpacke die ZIP-Datei in einen Ordner deiner Wahl — zum Beispiel auf dem Schreibtisch oder in deinen Dokumente-Ordner.

### Schritt 2 — Claude Code im Kursordner starten

Öffne dein Terminal und navigiere in den entpackten Ordner:

**Mac:**
```bash
cd ~/Desktop/AIAugmentedPM-Woche1
claude
```

**Windows (PowerShell):**
```powershell
cd "$env:USERPROFILE\Desktop\AIAugmentedPM-Woche1"
claude
```

Falls du den Ordner woanders gespeichert hast, passe den Pfad entsprechend an.

Claude ist jetzt bereit. Tippe "Starte den Kurs" um zu beginnen.

---

## Kurs starten

Sobald Claude Code läuft, tippe einfach:

```
Starte den Kurs
```

Claude liest den Kurs ein und beginnt sofort mit der Begrüßung. Du kannst während des Kurses jederzeit:
- **`weiter`** tippen, um zum nächsten Schritt zu gehen
- **`überspringen`** tippen, um einen Schritt zu überspringen
- **`stop`** tippen, um den Kurs zu unterbrechen

Außerhalb des Kurses kannst du Claude normal verwenden — er startet den Kurs nur wenn du ihn explizit dazu auforderst.

---

## Dateistruktur

```
AIAugmentedPM-Woche1/
├── README.md              ← Diese Datei — lies sie zuerst
├── CLAUDE.md              ← Wird automatisch von Claude geladen
├── kurs.md                ← Der vollständige Kursinhalt
├── context/
│   ├── company.md         ← Wer ist NeoEmployee?
│   └── strategy.md        ← Was ist die Strategie?
├── input/
│   ├── Interview_Gen_01.md
│   └── ... (10 Interviews gesamt)
├── scripts/
│   ├── interview-analysis.md    ← Skript: Interviews analysieren
│   ├── PRD-writer.md            ← Skript: PRD schreiben
│   ├── interview-to-PRD.md      ← Skript: Full Pipeline
│   └── My-PRD-Template.md       ← PRD-Template als Referenz
└── output/
    └── (leer — wird im Kurs befüllt)
```

---

## Hinweis: Token-Limit

Dieser Kurs läuft komplett in Claude Code — das bedeutet, dass jeder Schritt Tokens verbraucht. Bei intensiver Nutzung kann Claude Code dich bitten, kurz zu warten. Das Token-Limit wird alle 5 Stunden zurückgesetzt.

**Wenn du Tokens sparen möchtest:** Öffne `kurs.md` direkt im Texteditor und lies die Schritte dort nach — dann arbeitest du parallel in Claude Code, ohne den Kurstext mitzuschleppen.

---

## Probleme?

- Claude findet die Dateien nicht → stelle sicher, dass du Claude Code **im Kursordner** gestartet hast
- Kurs startet nicht → stelle sicher, dass du das Repository vollständig heruntergeladen hast (nicht nur einzelne Dateien) und Claude Code neu startest
