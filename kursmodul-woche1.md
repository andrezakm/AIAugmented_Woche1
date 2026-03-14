# Kursmodul Woche 1: Von User-Interviews zum PRD mit KI

> **Zweck dieses Files:** Content-Planung und Rohstruktur für das Lernerskript.
> Aus diesem File wird das finale, interaktive Walkthrough-Script für die Kursteilnehmer generiert.

---

## Überblick

**Kurswoche:** 1
**Thema:** AI-Augmented Product Management — Von Interviews zum PRD
**Zielgruppe:** Produktmanager mit Basis-PM-Erfahrung, wenig bis keine Erfahrung mit KI-Workflows
**Zeitaufwand:** ca. 90–120 Minuten (hands-on)

**Szenario:** Die Teilnehmer schlüpfen in die Rolle eines PMs bei NeoEmployee — einem KI-Consulting-Startup, das KI-Agenten für Unternehmenskunden baut. Sie haben 10 User-Interviews vorliegen und müssen daraus ein PRD ableiten. Ohne KI wäre das ein halber Tag Arbeit. Mit KI: unter einer Stunde.

---

## Schritte & Lernziele

### Schritt 1 — Kurs installieren
**Lernziel:** Die Teilnehmer können diesen Kurs über Github herunterladen und lokal einrichten.

---

### Schritt 2 — Dateistruktur verstehen
**Lernziel:** Die Teilnehmer verstehen die Grundstruktur des Kursordners und können sie auf eigene Projekte übertragen.

Die vier Verzeichnisse und ihre Bedeutung:

| Verzeichnis | Inhalt | Rolle |
|-------------|--------|-------|
| `context/` | `company.md`, `strategy.md` | **Statischer Kontext** — wiederverwendbar, bleibt über alle Durchläufe konstant |
| `input/` | Interview-Files etc. | **Dynamischer Kontext** — wird nur für diesen spezifischen Automatisierungsdurchlauf einmalig hereingezogen |
| `output/` | Alle generierten Ergebnisse | Hier landen die Outputs |
| `scripts/` | Alle Prompt-Skripte | Hier liegen die Anweisungen an die KI |

> Diese Struktur ist kein Zufall — sie hilft immer wieder. Wer sie einmal verstanden hat, kann sie auf jedes KI-Automatisierungsprojekt übertragen.

---

### Schritt 3 — Das generelle Vorgehen verstehen
**Lernziel:** Die Teilnehmer kennen den goldenen Dreiklang der KI-Automatisierung und können ihn anwenden.

**Der goldene Dreiklang:**

1. **Ergebnis definieren** — Was wollen wir automatisieren? Wie sieht ein gutes Ergebnis aus? Wir müssen das Ergebnis so gut beschreiben können, dass wir es erkennen, wenn wir es sehen.

2. **Kontext definieren** — Welchen Kontext brauchen wir?
   - *Statischer Kontext:* Immer gleich, permanent aufgebaut (z.B. `company.md`, `strategy.md`)
   - *Dynamischer Kontext:* Einmalig, nur für diesen Durchlauf (z.B. die Interview-Files)

3. **Prozess bauen** — Wenn wir Kontext und Ergebnis klar haben, lassen wir Claude uns den Prozess bauen, der uns vom Kontext zum Ergebnis führt.

**Das Iterationsprinzip:**

Der erste Durchlauf liefert selten das optimale Ergebnis. Das ist normal — und kein Fehler. Die Frage ist: Wie geben wir der KI bessere Anweisungen?

Die Antwort: **Aufbrechen.** Einen groben Prozessschritt in mehrere kleinere Schritte unterteilen und in jeden Schritt gezielt den relevanten Kontext einziehen. Das gibt der KI mehr Fokus pro Aufgabe — und das verbessert die Ergebnisse sprunghaft.

---

### Schritt 4 — Skript anwenden, Ergebnis beurteilen, Skript verbessern
**Lernziele:**
- Verstehen, wie man ein Skript aufruft
- Verstehen, wie man ein Skript so anpasst, dass das Ergebnis besser wird

**Übung am Beispiel der Interview-Analyse:**

**4a — Skript aufrufen**

Rufe das Interview-Analyse-Skript auf einem einzelnen Interview auf. Nutze dafür `input/Interview_Gen_10.md` als Eingabe und führe das Skript aus dem `scripts/`-Verzeichnis aus. Im `output/`-Verzeichnis sollte danach eine Analyse des Interviews erscheinen.

**4b — Ergebnis beurteilen**

Lies die generierte Analyse aufmerksam durch. Frage dich:
- Was gefällt mir? Was nicht?
- Was fehlt? Was ist zu viel?
- Welches Ergebnis hätte ich mir gewünscht?

Mach dir Notizen — du wirst sie gleich brauchen.

**4c — Skript anpassen**

Erkläre Claude jetzt, wie du die Analyse ändern möchtest. Wichtig: **Gib nicht zu genaue Anweisungen.** Beschreibe das gewünschte Ergebnis — nicht den Weg dorthin. Lass Claude entscheiden, wie das Skript geändert werden muss, um dieses Ergebnis zu liefern.

**4d — Nochmal laufen lassen**

Führe dasselbe Skript mit dem angepassten `scripts/interview-analysis.md` erneut aus. Vergleiche die neue Ausgabe mit der ersten. Ist das Ergebnis näher an dem, was du wolltest?

---

**Was steckt hinter diesem Skript? — Eine wichtige Beobachtung**

Schau dir `scripts/interview-analysis.md` genau an. Du wirst sehen, dass es bewusst zweistufig aufgebaut ist:

1. **Stufe 1:** Jedes Interview wird einzeln und parallel analysiert — ein Agent pro Interview
2. **Stufe 2:** Erst danach wird eine Synthese über alle Einzelanalysen gefahren

Das ist kein Zufall. Wenn man alle Interviews auf einmal analysiert, wird das Ergebnis dünner — die KI verliert den Fokus. Wenn man jedes Interview einzeln analysiert und die Einzelergebnisse erst dann zusammenführt, ist die Analyse tiefer und präziser.

**Das ist die praktische Demonstration des Iterationsprinzips aus Schritt 3:** Große Aufgaben in kleinere Schritte aufbrechen, in jeden Schritt gezielt Kontext einziehen — das verbessert die Ergebnisse sprunghaft. Merke dir dieses Muster für alle weiteren Skripte, die du baust.

---

### Schritt 5 — Alle Interviews analysieren — jetzt mit Spaß
**Lernziel:** Das verbesserte Skript auf alle Interviews anwenden und erleben, wie parallele Agenten arbeiten.

Jetzt lassen wir das verbesserte Skript auf alle zehn Interviews los. Kein einzelnes Interview mehr — der volle Durchlauf.

**Prompt:**
```
Führe das Skript scripts/interview-analysis.md aus.
Analysiere alle Interview-Files in input/.
Speichere alle Outputs in output/.
```

Lehne dich zurück und schau zu, was passiert. Claude wird:
1. Alle Interview-Files einlesen
2. Für jedes Interview einen eigenen Analyse-Agenten starten — parallel
3. Am Ende eine Synthese über alle Einzelanalysen erstellen

Im `output/`-Verzeichnis erscheinen danach:
- Eine Analyse-Datei pro Interview
- Eine gemeinsame Synthese-Datei über alle Interviews

**Schau dir das Ergebnis an.** Was fällt dir auf, verglichen mit der Einzelanalyse aus Schritt 4? Ist die Synthese tiefer? Sind die Einzelanalysen detaillierter?

---

### Schritt 6 — Zwischenschritt: Wer sind wir eigentlich?
**Lernziel:** Verstehen, dass Kontext über die Firma und Strategie entscheidend dafür ist, ob ein PRD gut wird oder nicht.

Bevor wir das PRD schreiben, machen wir einen kurzen Schritt zurück. Wir haben bisher nur auf die Interviews geschaut — aber wir haben noch gar nicht gefragt: Wer sind wir als Firma? Was ist unsere Strategie?

**Lies jetzt diese beiden Files:**

```
context/company.md
context/strategy.md
```

Was du dabei verstehen sollst:

- **NeoEmployee** baut KI-Agenten — nicht als Produkt von der Stange, sondern aktuell noch als Kastensoftware für einzelne Kunden.
- Die **Strategie** dahinter: Aus diesen individuellen Projekten sollen sich Muster herauskristallisieren, die wir eines Tages als skalierbare Produkte verkaufen können.

Das verändert, wie du die Interviews liest. Nicht jedes Problem, das Interviewpartner nennen, ist ein Problem, das wir lösen wollen. Wir suchen gezielt nach Problemen, die:
- zu unserem KI-Agenten-Ansatz passen
- sich vermutlich bei mehreren Kunden wiederholen
- schnell lieferbar sind (wir sind bootstrapped — wir brauchen Umsatz)

**Optional — aber empfohlen:**

Geh nochmal durch die Einzelanalysen in `output/`, die wir in Schritt 5 erstellt haben. Diesmal mit einer anderen Brille: Welche Probleme aus den Interviews passen zu NeoEmployee? Welche nicht?

**Prompt:**
```
Lies context/company.md und context/strategy.md.
Geh dann die Einzelanalysen in output/ durch.
Welche der identifizierten Probleme passen am besten zu NeoEmployees Ansatz
und Strategie? Begründe kurz für jedes Problem.
```

Erst wenn du diesen Überblick hast, macht das PRD im nächsten Schritt wirklich Sinn.

---

### Schritt 7 — PRD bauen lassen — nochmal Spaß
**Lernziel:** Erleben, dass ein kurzer, ungenauer Prompt ausreicht — weil die eigentliche Intelligenz im Skript steckt.

Jetzt lassen wir einen vollständigen PRD schreiben. Dazu rufst du den PRD Writer auf.

**Prompt:**
```
Schreib uns einen PRD. Nutze dazu die Interview-Analyse aus output/
sowie unseren Firmen- und Strategiekontext aus context/.
```

Das war's. Kein langer Prompt, keine detaillierten Anweisungen.

Das ist kein Zufall — und das ist der eigentliche Lernpunkt dieses Schritts:

**Der Prompt muss nicht präzise sein, weil das Skript es bereits ist.**

Claude Code liest `scripts/PRD-writer.md`, versteht was es tun soll, zieht sich selbst die richtigen Inputs und produziert ein strukturiertes PRD. Du hast die Arbeit einmal in das Skript gesteckt — und kannst es seitdem mit einem Satz aufrufen.

Im `output/`-Verzeichnis liegt danach ein fertiges PRD. Lies es durch:
- Klingt das nach einem Produkt, das NeoEmployee bauen würde?
- Ist das Problem klar formuliert?
- Würdest du dieses Dokument deinem Team geben?

---

### Schritt 8 — PRD analysieren und verbessern
**Lernziel:** Kritisch beurteilen, ob ein KI-Output gut ist — und wenn nicht, das Skript so anpassen, dass das Ergebnis besser wird. Das ist die Kernfähigkeit.

**8a — Analysiere den PRD**

Lies das generierte PRD sorgfältig durch. Frage dich:

- Welche Probleme aus den Interviews hat der PRD aufgegriffen?
- Kannst du diese Probleme in den Einzelanalysen und der Synthese aus `output/` wiederfinden?
- Wo stimmt das überein — und wo nicht?

**Prompt:**
```
Vergleiche den PRD in output/ mit der Interview-Synthese in output/.
Welche Probleme aus den Interviews spiegeln sich im PRD wider?
Welche fehlen? Was wirkt gut begründet, was nicht?
```

**8b — Beurteile: Wie sieht gut aus?**

Wenn du nicht zufrieden bist: Das ist der wichtigste Moment im Kurs.

Überlege, was dich stört. Dann schau in `scripts/PRD-writer.md` und frage dich: Wo im Skript kommt das her? Was müsste anders stehen, damit das Ergebnis so aussieht, wie du es willst?

Erkläre Claude dann — wieder ohne zu kleinteilig zu sein — wie das Ergebnis anders aussehen soll:

```
Der PRD ist zu oberflächlich im Abschnitt über das Problem.
Ich möchte dort konkrete Zitate aus den Interviews sehen.
Passe scripts/PRD-writer.md entsprechend an.
```

**8c — Nochmal laufen lassen**

Führe den PRD Writer erneut aus und vergleiche das neue Ergebnis mit dem alten.

---

**Das ist der eigentliche Kern dieser Woche:**

Wir üben genau zwei Dinge:

1. **Eigene Skripte erstellen lassen** — Du beschreibst Claude, was du willst. Claude baut das Skript. Du nutzt es.
2. **Bestehende Skripte anpassen** — Du schaust rein, beurteilst das Ergebnis, erklärst was fehlt, lässt es verbessern.

Beides zusammen ist die Fähigkeit, die dich als PM mit KI produktiver macht als ohne.

---

### Schritt 9 — Prototyp erstellen lassen — reiner Spaß
**Lernziel:** Erleben, wie schnell aus einem PRD ein klickbarer Prototyp entsteht.

Jetzt wird es sichtbar. Wir lassen aus dem PRD direkt einen HTML-Prototypen bauen.

**Prompt:**
```
Erstelle mir einen Prototypen auf Basis des PRDs, der in output/ liegt.
Es soll ein einfacher HTML-Prototyp sein, der nur die Basics der
besten Lösung aus dem PRD umsetzt.
Speichere ihn in output/ und öffne ihn danach direkt im Browser.
```

Claude wird:
1. Den PRD lesen
2. Die wichtigste Kerninteraktion identifizieren
3. Einen selbst enthaltenen HTML-Prototypen bauen — alles inline, keine externen Abhängigkeiten
4. Den Prototyp automatisch im Browser öffnen

**Was du siehst:** Kein Wireframe, kein graues Mockup — ein echter, klickbarer Prototyp mit echten Inhalten aus dem Interview-Kontext.

Schau ihn dir an. Kannst du in 30 Sekunden erklären, was das Produkt macht? Wenn ja, hat der Prototyp seinen Job gemacht.

---

### Schritt 10 — Reflexion: Was haben wir eigentlich getan?

Bevor du den Kurs abschließt, halte kurz inne.

Wir haben in dieser Woche eine fertige Struktur in Claude Code geladen und durchgearbeitet. Lass uns nochmal zusammenfassen, was diese Struktur war — und was der eigentliche Kern dahinter ist.

**Die Struktur:**

| Verzeichnis | Rolle |
|-------------|-------|
| `context/` | Statischer Kontext — wer wir sind, was unsere Strategie ist |
| `input/` | Dynamischer Kontext — was wir diesmal reinziehen |
| `scripts/` | Was wir tun — Anweisungen an die KI |
| `output/` | Was dabei rauskommt |

Das ist alles. Diese vier Ordner sind das ganze System.

---

**Das Denkmuster dahinter — und das ist der Kern:**

Wann immer du eine Aufgabe mit KI automatisieren willst, stellst du dir dieselben drei Fragen:

1. **Was will ich automatisieren — und wie sieht ein gutes Ergebnis aus?**
   Beschreibe das Ergebnis so präzise, dass du es erkennst, wenn du es siehst.

2. **Welchen Kontext brauche ich dafür?**
   Was ist statisch (immer gleich)? Was ist dynamisch (nur diesmal)?

3. **Welche Zwischenschritte helfen uns, dorthin zu kommen?**
   Große Aufgaben in kleine Schritte aufbrechen. In jeden Schritt nur den Kontext einziehen, den dieser Schritt braucht.

Das ist die ganze Arbeit. Immer wieder. Bei jeder Aufgabe.

---

**Zugabe 1 — Die Full-Pipeline: Interview2PRD**

Du hast diese Woche jeden Schritt einzeln durchgeführt. Es gibt aber auch ein Skript, das alles in einem Rutsch macht: `scripts/interview-to-PRD.md`.

Dieses Skript führt automatisch aus:
1. Interview-Analyse aller Files in `input/` (einzeln und parallel)
2. Synthese über alle Interviews
3. PRD-Writing auf Basis der Synthese
4. HTML-Prototyp erstellen und im Browser öffnen

Probiere es einmal aus:

```
Führe das Skript scripts/interview-to-PRD.md vollständig aus.
```

Das ist der Unterschied zwischen dem Weg, den wir gegangen sind — Schritt für Schritt, mit Anhalten und Verstehen — und dem, was möglich ist, wenn du weißt, was du tust: ein Satz, und der Rest passiert von selbst.

---

**Zugabe 2 — Dein erstes eigenes Skript**

Jetzt bist du dran.

Lass Claude Code ein eigenes Skript für dich erstellen. Die Aufgabe ist einfach: Der PRD, den wir gebaut haben, soll kommuniziert werden — in verschiedenen Formaten für verschiedene Zielgruppen.

Beispiel-Prompt:
```
Erstelle mir ein Skript in scripts/, das den PRD aus output/ liest
und drei verschiedene Kommunikations-Versionen davon schreibt:
1. Eine kurze Slack-Nachricht an das Team
2. Eine Zusammenfassung für den Chef (max. 5 Sätze)
3. Eine Erklärung für Kollegen, die nicht im Projekt sind

Speichere alle drei Versionen als Markdown-File in output/.
```

Claude wird das Skript schreiben. Dann rufst du es auf. Schau dir die drei Outputs an.

Das war es. Du hast gerade dein erstes eigenes Skript gebaut — ohne eine Zeile Code zu schreiben.

---

**Das Prinzip, das sich durch alles zieht:**

> Kleinere Arbeitsschritte mit kleinerem, gezielterem Kontext bringen bessere Ergebnisse.

Nicht weil KI schwach ist — sondern weil Fokus funktioniert. Für Menschen genauso wie für KI.

Was du diese Woche gelernt hast, ist kein Trick und kein Tool. Es ist eine Denkweise. Und die kannst du ab jetzt auf jede Aufgabe anwenden, die du als PM hast.

---

## Vorbereitung / Setup

> **Was der Teilnehmer braucht:**
> - Zugang zu Claude (claude.ai oder API)
> - Die Kursfiles lokal oder in einem freigegebenen Ordner
> - Grundlegendes Verständnis was ein PRD ist (wird kurz aufgefrischt)

**Vorhandene Files im Kursordner:**
```
context/
  company.md        ← Wer ist NeoEmployee?
  strategy.md       ← Welche strategischen Constraints gibt es?
input/
  Interview_Gen_01.md  ← 10 generierte User-Interviews
  ...
  Interview_Gen_10.md
scripts/
  interview-analysis.md   ← Prompt-Skript: Interviews analysieren
  PRD-writer.md           ← Prompt-Skript: PRD schreiben
  interview-to-PRD.md     ← Prompt-Skript: Full Pipeline (alles in einem)
  My-PRD-Template.md      ← PRD-Template als Referenz
output/
  (leer — wird im Kurs befüllt)
```

---

## Modulstruktur (Content-Bausteine)

### Baustein 1 — Kontext verstehen (10 min)

**Was passiert hier:**
Teilnehmer lesen `context/company.md` und `context/strategy.md`. Ziel: Den Unternehmenskontext internalisieren, bevor man mit den Interviews arbeitet. Gute PMs schauen nie auf User-Daten ohne strategischen Rahmen.

**Kernfragen für den Teilnehmer:**
- Was baut NeoEmployee? Was ist das Geschäftsmodell?
- Was sind die wichtigsten Constraints (kein Investor-Geld, Bootstrap, T&M)?
- Was bedeutet das für das Produkt, das wir gleich bauen werden?

**Lernpunkt:** Kontext ist keine Pflichtübung — er verändert, was du im Interview hörst. Dieselbe Aussage eines Interviewpartners bedeutet etwas anderes, wenn du ein Cash-generierendes Beratungsprodukt baust vs. ein VC-finanziertes Startup.

---

### Baustein 2 — Raw Interviews lesen (15 min)

**Was passiert hier:**
Teilnehmer lesen 2–3 der Interview-Files in `input/` komplett durch. Nicht alle zehn — bewusst nur eine Stichprobe, um das Gefühl für das Rohmaterial zu bekommen.

**Empfehlung:** Interview 01 (Sarah Jenkins, SDR) + Interview 05 + Interview 09

**Aufgabe während des Lesens:**
Notiere auf einem Blatt Papier (nicht digital):
- 3 Probleme, die du identifizierst
- 1 Zitat, das dich besonders trifft
- Deine Einschätzung: Was ist das dringendste Problem?

**Lernpunkt:** Bevor du mit KI arbeitest, brauchst du eine eigene Hypothese. KI-Output ohne PM-Urteil ist gefährlich — du wirst sonst alles akzeptieren, was die KI dir sagt.

---

### Baustein 3 — Interview-Analyse mit KI (20 min)

**Was passiert hier:**
Teilnehmer führen das Interview-Analyse-Skript aus. Entweder:
- Option A: Nur ein einzelnes Interview analysieren (für den Einstieg)
- Option B: Das Parallel-Agenten-Setup aus `scripts/interview-analysis.md` vollständig ausführen

**Schritt-für-Schritt:**
1. Öffne `scripts/interview-analysis.md` und lies es vollständig
2. Verstehe die Struktur: Was soll jeder einzelne Agent tun? Was soll die Synthese leisten?
3. Führe das Skript aus — entweder manuell mit einem Interview, oder mit der vollen Pipeline
4. Speichere die Outputs in `output/`

**Reflexion nach diesem Schritt:**
- Deckt sich die KI-Analyse mit deinen handschriftlichen Notizen aus Baustein 2?
- Was hat die KI gefunden, was du übersehen hast?
- Was hast du gefunden, was die KI nicht erwähnt hat?

**Lernpunkt:** KI ist hervorragend in Vollständigkeit und Struktur. Menschen sind besser in Bedeutung und Kontext. Das Optimum liegt in der Kombination.

---

### Baustein 4 — Synthese verstehen (10 min)

**Was passiert hier:**
Teilnehmer lesen die generierte `interview-synthesis-[datum].md` und evaluieren sie kritisch.

**Bewertungsfragen:**
- Ist das identifizierte Root-Cause-Problem das richtige?
- Welche Probleme werden überbewertet, welche unterbewertet?
- Was fehlt, das in den Interviews durchgeklungen ist, aber in der Synthese verloren ging?

**Lernpunkt:** Synthese ist keine Zusammenfassung. Eine gute Synthese trifft Entscheidungen: Was ist wichtig? Was ist Signal, was ist Rauschen? Die KI liefert den Rohling — du triffst das Urteil.

---

### Baustein 5 — PRD schreiben mit KI (20 min)

**Was passiert hier:**
Teilnehmer führen `scripts/PRD-writer.md` aus — entweder direkt oder als Teil der Full-Pipeline mit `scripts/interview-to-PRD.md`.

**Schritt-für-Schritt:**
1. Lies `scripts/PRD-writer.md` vollständig
2. Verstehe, welche Inputs das Skript erwartet
3. Führe es aus
4. Öffne das generierte PRD in `output/`

**Reflexion nach diesem Schritt:**
- Würdest du dieses PRD in die Hände deines Engineering-Teams geben? Warum / warum nicht?
- Welche Abschnitte sind stark? Welche brauchen mehr PM-Arbeit?
- Wie lange hättest du gebraucht, dieses PRD von Hand zu schreiben?

**Lernpunkt:** KI schreibt ein 80%-PRD sehr schnell. Die letzten 20% — Priorisierung, Trade-offs, strategische Entscheidungen — sind dein Job als PM. Und das ist genau richtig so.

---

### Baustein 6 — Prompt-Architektur sezieren (15 min)

**Was passiert hier:**
Teilnehmer kehren zu den Skript-Files zurück und analysieren sie als Lernübung.

**Fragen für jeden Script:**
- Was ist das Ziel des Skripts in einem Satz?
- Welche Inputs werden explizit geladen?
- Wie sind die Instruktionen gegliedert — und warum in dieser Reihenfolge?
- Welche Constraints oder Regeln gibt es, und warum sind sie wichtig?
- Was würde passieren, wenn du diese Constraints weglässt?

**Mini-Übung:**
Schreib dein eigenes kleines Prompt-Skript für eine PM-Aufgabe deiner Wahl — z.B. "Analysiere ein Feature-Request-Backlog und priorisiere nach User-Schmerz und Business-Value."

**Lernpunkt:** Ein guter AI-Prompt ist wie ein gutes Brief an einen Junior-PM. Du definierst den Kontext, die Aufgabe, die Outputs, und die Grenzen. Je klarer das Brief, desto besser die Arbeit.

---

### Baustein 7 — Reflexion & Transfer (10 min)

**Abschlussfragen:**
1. Welchen Teil deines aktuellen PM-Workflows könntest du mit diesem Ansatz beschleunigen?
2. Wo wäre KI in deinem Kontext besonders nützlich — und wo wäre sie gefährlich?
3. Was nimmst du aus dieser Woche mit, das du morgen anwenden kannst?

**Optional: Community-Aufgabe**
Teile in der Kurs-Community:
- Deinen eigensten Prompt aus der Mini-Übung
- Eine Beobachtung aus dem Vergleich deiner handschriftlichen Notizen vs. KI-Output

---

## Key Concepts (Glossar für das Lernerskript)

| Begriff | Erklärung |
|---------|-----------|
| **Prompt-Skript** | Ein strukturiertes Textdokument, das einer KI exakt beschreibt, was sie analysieren, entscheiden und ausgeben soll — vergleichbar mit einem SOP (Standard Operating Procedure) für KI |
| **Interview-Synthese** | Ein Dokument, das Muster und Erkenntnisse über mehrere Interviews hinweg aggregiert — nicht jede einzelne Aussage, sondern was über alle Interviews hinweg gilt |
| **PRD (Product Requirements Document)** | Das zentrale Dokument, das beschreibt, welches Problem wir lösen, warum jetzt, und welche Form die Lösung grob hat |
| **Root Cause** | Die eigentliche Ursache eines Problems — nicht das Symptom. Wenn SDRs 4h/Tag mit manueller Lead-Verifikation verbringen, ist das Symptom; der Root Cause ist fehlendes, aktuelles Kontaktdaten-Enrichment |
| **Parallel Agents** | Mehrere KI-Instanzen, die gleichzeitig und unabhängig arbeiten — im Kurs: eine Instanz pro Interview für maximale Tiefe und Geschwindigkeit |
| **Guardrail Metric** | Eine Kennzahl, die nicht schlechter werden darf, während du das Hauptziel anstrebst |

---

## Didaktische Notizen (für Kursdesign)

- **Hands-on first:** Teilnehmer sollen immer zuerst selbst eine Einschätzung haben, bevor die KI spricht. Das verhindert blinden Gehorsam gegenüber KI-Output.
- **Kontrast ist Lernen:** Der Vergleich "meine handschriftliche Hypothese vs. KI-Output" ist der pädagogische Kern dieser Woche.
- **Kein Copy-Paste-Kurs:** Das Ziel ist nicht, dass Teilnehmer lernen, diese spezifischen Skripte zu benutzen. Das Ziel ist, dass sie verstehen, wie sie eigene Skripte für ihre eigene Arbeit bauen.
- **Fail fast:** Wenn ein Teilnehmer einen schlechten Prompt schreibt und schlechten Output bekommt, ist das ein Lernmoment — kein Fehler.

---

## TODO / Offene Punkte für die Kursproduktion

- [ ] Entscheiden: Wird das Skript als interaktiver Walkthrough in einem Chat-Interface geliefert, oder als statisches Markdown-Dokument?
- [ ] Video-Erklärungen für Baustein 3 und 5 (Screencast: wie führt man ein Prompt-Skript aus)?
- [ ] Lösung/Musterlösung: Soll ein fertiger Output (interview-synthesis, PRD) als Referenz bereitliegen?
- [ ] Zeitplanung: 90 min ist ambitioniert — prüfen ob Aufspaltung in 2x45 min sinnvoller ist
- [ ] Sprachentscheidung: Kurs auf Deutsch oder Englisch? (Interviews + Skripte aktuell auf Englisch)
- [ ] Quiz/Checkpoints: Kleine Wissensabfragen nach jedem Baustein einbauen?

---

## Nächster Schritt

Aus diesem File wird das **Lernerskript** generiert — ein Markdown-Dokument, das der Kursteilnehmer Schritt für Schritt durchgeht. Es hat:
- Klare Anweisungen ("Öffne jetzt diese Datei...")
- Zeitangaben pro Schritt
- Reflexionsfragen
- Kein didaktisches Meta-Blabla — direkt und handlungsorientiert

→ Script generieren mit: `scripts/generate-learner-script.md` (noch zu erstellen)
