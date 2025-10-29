# Willkommen bei Mind Forge!

Dies ist der **AI-Native Project Hub** für unser Projekt **Mind Forge**: Eine KI-gestützte Lernplattform für Schüler – geschmiedet von einem kleinen, aber feinen Team.
Published to [Mindforge Work](https://tobiaswaggoner.github.io/mindforge_work/)

## 1. Das Team (The Smiths)

* **[Tobias](https://github.com/tobiaswaggoner):** Master Smith
* **[Michi](https://github.com/milchinien):** Apprentice / Rapid Prototyping
* **[Tim](https://github.com/Timiwagg):** Apprentice / Rapid Prototyping

## 2. Unsere Philosophie (Warum diese Schmiede?)

Wir verzichten bewusst auf "Old-School"-Tools wie Jira oder Azure DevOps. Unser Ziel ist ein **Low-Tech & AI-First**-Ansatz.

* **Low-Tech:** Alles ist Text (Markdown), alles ist in Git. Kein Einarbeiten in komplexe Tools. Die besten Werkzeuge sind einfach.
* **AI-First:** Die Struktur ist darauf optimiert, von KI-Agenten gelesen, verstanden und (später) modifiziert zu werden. Claude ist unser vierter Schmied.
* **Git als Event Source:** Wir nutzen die Git-Historie (insb. `git mv`-Befehle) als maschinenlesbares Protokoll unseres Fortschritts. Jede Bewegung einer Datei erzählt eine Geschichte.

**Die Schmiede-Metapher:** Wir nutzen Schmiede-Terminologie als durchgängiges Vokabular. Nicht als Gag, sondern als konsistente Sprache für unseren Prozess. Siehe `CLAUDE.md` für Details.

## 3. Die Struktur der Schmiede

Die Ordnerstruktur definiert den Prozess:

* **`README.md`**: (Diese Datei) Der Eingang zur Schmiede.
* **`01_BLUEPRINTS/`**: Die "großen" Pläne. Vision, Strategie, Roadmap. Was wollen wir bauen?
* **`02_SPARK_CHAMBER/`**: Unser Ideenraum. Jeder Funke, jede neue Idee kommt als `.md`-Datei hier hinein. Unstrukturiert, roh, lebendig.
* **`03_THE_FORGE/`**: Unser dynamisches Kanban-Board. Der Status einer Aufgabe wird durch ihren Ort definiert:
    * **`01_Stock/`**: Rohmaterial. Aufgaben, die bereit zum Schmieden sind.
    * **`02_At_the_Anvil/`**: Hier wird aktiv gearbeitet. Das Metall ist heiß, die Hämmer schwingen.
    * **`03_Tempered/`**: Gehärtet und fertig. Abgeschlossen, bereit für Feedback oder als Artifact archiviert.
* **`04_FORGE_LOG/`**: Der Schlüssel für asynchrone Arbeit. Wöchentliche Updates, wichtige Entscheidungen oder Probleme werden hier als datierte `.md`-Datei abgelegt. Das Logbuch der Schmiede.
* **`05_REFERENCE_LIBRARY/`**: Statisches Wissen. Konkurrenzanalysen, technische Konzepte, UI-Prinzipien. Die Bibliothek des Master Smith.

## 4. Der Workflow: "Von der Idee zur Umsetzung"

Unser Prozess ist mehrstufig und nutzt KI-gestützte Commands, um von rohen Ideen zu konkreten Features zu gelangen.

### Ein typischer Durchlauf:

1.  **Spark (Brainstorming):** Eine neue Idee entsteht.
    ```bash
    # Interaktiver Brainstorming-Dialog mit /brainstorm
    /brainstorm [deine Idee]

    # Ergebnis: 02_SPARK_CHAMBER/2025-XX-XX-Feature-Idee.md
    git add 02_SPARK_CHAMBER/2025-XX-XX-Feature-Idee.md
    git commit -m "SPARK: Feature-Idee hinzugefügt"
    ```

2.  **Planning:** Die Idee wird in umsetzbare Features zerlegt.
    ```bash
    # Interaktiver Planning-Dialog mit /plan
    /plan 2025-XX-XX-Feature-Idee.md

    # Ergebnis: 1-N Stock Items werden direkt in 03_THE_FORGE/01_Stock/ angelegt
    # z.B. 2025-XX-XX-01-Feature-A.md, 2025-XX-XX-02-Feature-B.md, ...
    git add 03_THE_FORGE/01_Stock/*.md
    git commit -m "PLAN: Feature-Idee in [N] Stock Items zerlegt"
    ```

3.  **Forge:** Tim beginnt zu schmieden.
    ```bash
    git mv 03_THE_FORGE/01_Stock/2025-XX-XX-01-Feature-A.md 03_THE_FORGE/02_At_the_Anvil/
    git commit -m "FORGE: Tim beginnt Arbeit an Feature-A"
    ```

4.  **Temper:** Tim ist fertig. Das Werk wird gehärtet.
    ```bash
    git mv 03_THE_FORGE/02_At_the_Anvil/2025-XX-XX-01-Feature-A.md 03_THE_FORGE/03_Tempered/
    git commit -m "TEMPER: Feature-A abgeschlossen"
    ```

**Pro-Tipp:**
- Sparks bleiben in der Spark Chamber (werden nicht verschoben)
- Stock Items sind das Ergebnis der Planning-Session
- Die Git-Historie wird dadurch zu einem perfekt lesbaren Protokoll des Projekts. Maschinen lieben das. Menschen auch.

## 5. Asynchronität (Das Briefing-Ritual)

* Wer arbeitet, hinterlässt am Ende der Session/Woche einen kurzen Eintrag im **`04_FORGE_LOG/`** (z.B. in `2025-11-05_Wochen-Sync.md`).
* **KI-Briefing für das Team:** Zu Beginn einer neuen Arbeitswoche kann jeder Apprentice (oder der Master Smith) einen KI-Agenten auf dieses Repo (und das Code-Repo) loslassen, um Journal-Einträge und Git-Logs der letzten 7 Tage zu analysieren und ein Status-Update zu erhalten.
* **Die Schmiede schläft nie:** Auch wenn nicht alle gleichzeitig arbeiten, bleibt der Kontext erhalten. Die Logs erzählen die Geschichte.

---

**Bereit? Dann ab an den Amboss.** 🔨