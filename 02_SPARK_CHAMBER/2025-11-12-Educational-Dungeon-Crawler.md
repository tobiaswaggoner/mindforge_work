# Educational Dungeon Crawler

## Erstellt
2025-11-12 - Michi (michi.waggoner@gmail.com)

## Vision in einem Satz
Ein Top-Down Turn-Based Roguelike Dungeon-Crawler, bei dem Schüler durch das Lösen von Lernaufgaben in Speed-Duellen gegen Monster kämpfen und durch prozedural generierte Dungeons voller Loot und Upgrades fortschreiten.
  
## Zielgruppe & Motivation
- **Primäre Nutzer:** Schüler Klassenstufe 1-12 (verschiedene Schwierigkeitsstufen)
- **Motivationale Treiber:**
  - Gaming-Erlebnis statt "Lernen" - Mathe fühlt sich wie echter Combat an
  - Speed-Race gegen Gegner erzeugt Adrenalin und Zeitdruck
  - Roguelike-Progression: Jeder Run macht dich permanent stärker
  - Fächer-spezifische Dungeons mit eigenem Loot-System
  - Endless-Mode: "Wie weit schaffst du es?" - Highscore-Charakter

## Beschreibung

### Core Game Loop (User Journey)

**1. Dungeon-Auswahl (Pre-Run):**
- Schüler öffnet eine Overworld-Map mit verschiedenen Gebieten
- Jedes Gebiet = ein Schulfach (Mathe, Physik, Deutsch, etc.)
- Innerhalb eines Gebiets: mehrere Dungeons (Unterkategorien des Fachs)
  - Beispiel Mathe: Algebra-Dungeon, Geometrie-Dungeon, Stochastik-Dungeon
- Dungeons sind nach Klassenstufen/Schwierigkeitsstufen organisiert
- Dungeons werden durch Progression freigeschaltet (du musst Level 1 schaffen um Level 2 zu unlocken)
- Schüler rüstet **1 permanentes Item** aus seinem Inventar aus

**2. Der Dungeon-Run (Endless Roguelike):**
- Schüler betritt einen prozedural generierten Dungeon
- Räume spawnen zufällig - verschiedene Raum-Typen:
  - **Gegner-Räume:** Combat!
  - **Treasure-Räume:** Free Loot (Gold/Items)
  - **Shop-Räume:** Kaufe temporäre Buffs/Items mit Gold (persistent currency)
  - **Boss-Räume:** (Frequenz noch offen - evtl. alle 10-15 Räume)
- Ziel: So weit wie möglich kommen - Endless Mode mit steigender Schwierigkeit

**3. Combat-System (Das Herzstück!):**

**Kampf-Start:**
- Schüler betritt Gegner-Raum
- 5-Sekunden-Countdown → Spannung aufbauen
- Lernaufgabe erscheint (z.B. "45 × 12 = ?")

**Speed-Race-Mechanik:**
- Schüler UND Gegner lösen die Aufgabe **gleichzeitig**
- Gegner hat eine Lösungszeit (Anfangs: 40 Sek, wird schneller mit Progression)
- Gegner zeigt **visuell** seinen Fortschritt (alle 4 Sek eine Stelle gelöst)
- **Beide greifen an** - aber wer schneller war, macht mehr Schaden

**Schaden & HP:**
- Schüler: 10 Basis-Schaden, 25 HP Start
- Gegner: 6-7 HP, 6-7 Schaden (Crit: 13-14)
- Items/Upgrades erhöhen Schaden

**Rundenablauf:**
- Aufgabe gelöst (richtig/schneller) → Schüler greift an (10+ Schaden)
- Aufgabe gelöst (richtig/langsamer) → Beide greifen an, Gegner macht mehr Schaden
- Aufgabe falsch → Schüler verliert Leben, neue Aufgabe kommt
- Gegner stirbt bei 0 HP → Loot (XP, Gold, Items)
- Schüler stirbt bei 0 HP → **Run Over** → Zurück zum Menü

**4. Progression-Systeme:**

**Im Run:**
- **Run-XP:** Temporäre XP während des Runs
  - Level-Ups schalten mehr Item-Slots frei (Start: 3 Items, später mehr)
  - Macht dich während des Runs stärker
- **Items:** Bis zu 3 temporäre Items im Run ausrüstbar (+ 1 permanentes Pre-Run)

**Permanent (zwischen Runs):**
- **Gold:** Persistent currency - im Run gefunden, im Menü ausgegeben
  - Kaufe permanente Items im Shop
- **Permanente XP:** Pro Fach separate Level-Leiste!
  - Alle 5-10 Level: +1 Item-Slot global + HP-Boost
  - Jedes Fach hat eigene Progression
- **Items:** Fach-spezifisch & Klassenstufen-gebunden
  - Mathe-Items ≠ Physik-Items
  - Klasse 1 Items schwächer als Klasse 10 Items
  - Build permanentes Inventar auf

**5. Gegner-Typen (Varianten):**
- **Speedster:** Löst sehr schnell, aber wenig HP
- **Tank:** Langsam, aber viel HP und hoher Schaden
- **Trickster:** Könnte Aufgaben mittendrin ändern oder verwirren (Stretch Goal)

**6. Schwierigkeitsskalierung:**
- Gegner werden schneller (weniger Lösungszeit)
- Gegner werden stärker (mehr HP/Schaden)
- Aufgaben werden komplexer (je nach Klassenstufe)

## Besonderheiten & Innovations-Potenzial

**🎮 Speed-Race-Mechanik:**
- Noch nie gesehen: Du siehst den Gegner parallel die Aufgabe lösen
- Erzeugt echten Zeitdruck - keine entspannten "Lern-Sessions"
- Lernen wird zu Adrenalin-Sport

**🔄 Roguelike-Struktur:**
- Hohe Wiederspielbarkeit durch Zufalls-Generierung
- "One more run"-Sucht-Faktor
- Permanente Progression verhindert Frustration

**📚 Fächer-Diversität:**
- Jedes Fach = eigenes Mini-Game mit eigenem Loot
- Schüler können Lieblingsfächer "grinden"
- Langzeit-Motivation: Alle Fächer meistern

**⚔️ Gamification-Tiefe:**
- Builds erstellen (Item-Kombinationen)
- Highscores/Leaderboards (Stretch)
- Boss-Fights als Meilensteine

## Risiken & Herausforderungen

**Scope:**
- Vision ist SEHR groß (Multi-Fach, Multi-Klassenstufe, komplexes Item-System)
- Aufgaben-Content-Produktion ist massiv (tausende Aufgaben benötigt)
- Balancing: Gegner-Schwierigkeit vs Schüler-Skill

**Motivationale Risiken:**
- Könnte zu "grindy" werden wenn Progression zu langsam
- Falscher Schwierigkeitsgrad = Frustration oder Langeweile
- Race-Mechanik könnte schwache Schüler demotivieren (Gegner immer schneller)

**Technische Komplexität:**
- Prozedurale Dungeon-Generierung
- Item-System mit Stats & Balancing
- KI für Gegner-Lösungs-Simulation
- Multi-Fach-Content-Pipeline

## KI-Potenzial

- **Adaptive Schwierigkeit:** KI passt Gegner-Speed an Schüler-Performance an
- **Aufgaben-Generierung:** KI erstellt prozedural neue Aufgaben (statt manuell tausende zu schreiben)
- **Personalisierte Dungeons:** KI erkennt Schwächen und bietet passende Dungeons an
- **Boss-Dialoge:** KI generiert motivierende/witzige Gegner-Sprüche

## Nächste Schritte

**Entscheidung: MVP vs Full Vision?**
- **Option A (MVP):** Ein Fach (Mathe), 3 Dungeons, 1 Klassenstufe, Basic Items, Endless Mode
- **Option B (Full Vision):** Multi-Fach, Overworld, Klassenstufen 1-12, komplexes Item-System
- **Empfehlung:** Start mit MVP, validieren ob Core-Loop funktioniert, dann expandieren

**Research:**
- Benchmark ähnlicher Lern-Games (Prodigy Math, DragonBox, etc.)
- Technische Machbarkeit: Dungeon-Generation-Frameworks
- Content-Pipeline: Wie viele Aufgaben brauchen wir für 1 Dungeon?

**Bereit für:**
- Planning-Session mit `/plan` um MVP-Features zu definieren
- Technisches Proof-of-Concept: Speed-Race-Combat-Mechanik testen
- Art/Design-Direction: Top-Down-Stil festlegen (Pixel-Art? Low-Poly?)

---

**Status:** 🌟 Moonshot mit MVP-Potenzial - Großes Bild im Kopf, aber schrittweise Umsetzung empfohlen
