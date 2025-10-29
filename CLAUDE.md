# Arbeiten im Mind Forge Repository

## Philosophie: Die Schmiede-Terminologie

Dieses Repository nutzt eine **Schmiede-Metapher** als durchgängige Terminologie.
Anleitung zum Prozess für Coworker in @README.md

**Wichtig:** Dies ist kein thematisches Rollenspiel, sondern professionelle Arbeit mit einem konsistenten, griffigen Vokabular. Die Metapher dient der Klarheit und dem Teamgefühl - nicht der Ablenkung.

### Leitprinzipien

1. **Augenzwinkern, nicht Übertreibung:** Die Terminologie soll Charakter haben, aber nie auf Kosten der Klarheit gehen.
2. **Konsistenz:** Wenn wir "Forge" sagen, meinen wir die aktive Bearbeitung. Wenn wir "Artifact" sagen, meinen wir ein fertiges Ergebnis.
3. **Professionell bleiben:** In technischen Diskussionen (Code, Architektur) nutzen wir Standard-Terminologie. Die Forge-Sprache gilt primär für Prozess und Organisation.

### Kern-Terminologie

| Standard | Mind Forge | Bedeutung |
|----------|------------|-----------|
| Team Roles | Master Smith, Apprentice | Klare Hierarchie ohne Old-School "Senior/Junior" |
| Backlog | Ready to Forge / Stock | Aufgaben, die bereit zur Bearbeitung sind |
| In Progress | At the Anvil | Aktive Arbeit |
| Done | Tempered / Artifacts | Abgeschlossene, "gehärtete" Ergebnisse |
| Ideas | Sparks / Raw Ore | Rohmaterial für künftige Arbeit |
| Documentation | Reference Library / Blueprints | Wissensdokumente |
| Weekly Sync | Forge Log | Protokolle und Journal-Einträge |

### Git Commit Conventions

Die Schmiede-Metapher spiegelt sich auch in Commit-Messages wider:

- `SPARK: [Idee]` → Neue Idee hinzugefügt (via `/brainstorm`)
- `PLAN: [Task]` → Spark in Stock Items zerlegt (via `/plan`)
- `FORGE: [Task]` → Aufgabe wird bearbeitet (in Arbeit verschoben)
- `TEMPER: [Task]` → Aufgabe abgeschlossen (in Done verschoben)
- `BLUEPRINT: [Strategie]` → Vision/Strategie-Update

### Ordnerstrukur

* **`README.md`**: (Diese Datei) Der Eingang zur Schmiede.
* **`01_BLUEPRINTS/`**: Die "großen" Pläne. Vision, Strategie, Roadmap. Was wollen wir bauen?
* **`02_SPARK_CHAMBER/`**: Unser Ideenraum. Jeder Funke, jede neue Idee kommt als `.md`-Datei hier hinein. Unstrukturiert, roh, lebendig.
* **`03_THE_FORGE/`**: Unser dynamisches Kanban-Board. Der Status einer Aufgabe wird durch ihren Ort definiert:
    * **`01_Stock/`**: Rohmaterial. Aufgaben, die bereit zum Schmieden sind.
    * **`02_At_the_Anvil/`**: Hier wird aktiv gearbeitet. Das Metall ist heiß, die Hämmer schwingen.
    * **`03_Tempered/`**: Gehärtet und fertig. Abgeschlossen, bereit für Feedback oder als Artifact archiviert.
* **`04_FORGE_LOG/`**: Der Schlüssel für asynchrone Arbeit. Wöchentliche Updates, wichtige Entscheidungen oder Probleme werden hier als datierte `.md`-Datei abgelegt. Das Logbuch der Schmiede.
* **`05_REFERENCE_LIBRARY/`**: Statisches Wissen. Konkurrenzanalysen, technische Konzepte, UI-Prinzipien. Die Bibliothek des Master Smith.

### Benutzer

* **[Tobias](https://github.com/tobiaswaggoner):** Master Smith
* **[Michi](https://github.com/milchinien):** Apprentice / Rapid Prototyping
* **[Tim](https://github.com/Timiwagg):** Apprentice / Rapid Prototyping

### Was NICHT tun

- ❌ Keine Fantasy-Sprache in Code-Kommentaren
- ❌ Keine "Rollenspiel"-Texte in technischen Spezifikationen
- ❌ Keine erzwungenen Metaphern, wenn Standard-Begriffe klarer sind

Die Schmiede-Terminologie ist ein **Werkzeug für Organisation und Kultur**, kein Selbstzweck.