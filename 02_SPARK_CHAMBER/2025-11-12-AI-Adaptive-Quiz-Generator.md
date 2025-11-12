# AI-Adaptive Quiz Generator

## Erstellt
2025-11-12 - Tobias Waggoner

## Vision in einem Satz
Schüler fordern per Chat AI-generierte Quizze an, die sich automatisch an ihren Wissensstand anpassen und durch Gamification kontinuierliches Lernen motivieren.

## Zielgruppe & Motivation
- **Primäre Nutzer:** Schüler (Mittel- und Oberstufe), die aktiv besser werden wollen
- **Motivationale Treiber:**
  - Sofortiges Feedback und Erfolgserlebnisse
  - Sichtbarer Progress durch XP/Levels
  - Self-Paced Learning ohne Druck
  - Spielerische Elemente (Achievements, Vergleich mit Freunden)

## Beschreibung

### User Journey

**Start:**
Sarah lernt für die Mathe-Klausur zu "Quadratischen Funktionen". Sie öffnet Mind Forge und chattet mit dem AI-Bot:

> "Erstell mir ein Quiz zu quadratischen Funktionen"

**Quiz-Generierung:**
Die AI generiert sofort ein Multiple-Choice-Quiz mit 10 Fragen unterschiedlicher Schwierigkeitsgrade. Das Quiz öffnet sich als **Canvas-Element** neben dem Chat – hübsch designed, interaktiv, fokussiert.

**Quiz-Loop (Adaptive Session):**
Sarah beantwortet die erste Frage. Direkt nach ihrer Antwort:
- **Richtig?** → XP +10, nächste Frage
- **Falsch?** → AI erklärt, warum die Antwort falsch war, zeigt den richtigen Lösungsweg

Nach jeder Frage bekommt Sarah drei Buttons:
- **"Zu leicht"** → AI generiert schwierigere Fragen zum gleichen Thema
- **"Genau richtig"** → AI bleibt auf diesem Niveau
- **"Zu schwer"** → AI generiert einfachere Fragen, evtl. mit mehr Kontext

Plus: **"Weiter"** oder **"Beenden"**

**Session Ende:**
Sarah beendet nach 15 Minuten. Sie sieht:
- "8/10 richtig – Gut gemacht!"
- "+80 XP → Level 7 in Mathe (noch 20 XP bis Level 8)"
- "Achievement freigeschaltet: 🔥 Quiz-Streak: 3 Tage in Folge!"

Das Quiz wird gespeichert. Sie kann es später:
- **Reaktivieren** ("Mach das Quiz nochmal")
- **Teilen** (Link an Freunde: "Versuch du auch mal!")
- **Vertiefen** ("Erstell ein Follow-up zu meinen Schwachstellen")

### Technische Kern-Features

**1. AI-Generierung (Zero-UI-Overhead)**
- Input: Thema/Frage + Optional: Referenzmaterial (PDF, Link, Text)
- Output: Multiple-Choice-Quiz (5-20 Fragen, variable Länge)
- Schwierigkeitsgrad wird automatisch geschätzt und getaggt

**2. Canvas-Pattern**
- Quiz lebt als eigenständiges Artifact (eigene URL)
- Teilbar, wiederholbar, reaktivierbar
- Später: Basis für weitere "Minispiele" (Lückentexte, Drag&Drop, etc.)

**3. Adaptive Loop**
- Self-Assessment nach jeder Frage (Zu leicht / Genau richtig / Zu schwer)
- AI generiert on-the-fly neue Fragen basierend auf Feedback
- Schwierigkeitsgrad wird dynamisch angepasst

**4. Remediation**
- Falsche Antworten → AI erklärt mit Kontext
- Optional: "Ich hab's nicht verstanden" → AI vertieft das Konzept
- Schüler entscheidet selbst, wann "genug" ist

**5. Persistence & Results Tracking**
- Quizze sind **public** (jeder kann jedes Quiz machen)
- Ergebnisse sind **private** (jeder sieht nur seine eigenen)
- Log: Welche Frage, welche Antwort, Self-Assessment, Timestamp
- Daten-Grundlage für späteres Spaced Repetition System

**6. Gamification (MVP-Elemente)**
- **XP-System:** Richtige Antworten geben XP
- **Levels pro Fach:** "Level 8 in Mathe", "Level 3 in Geschichte"
- **Achievements:** Daily Streaks, "10 Quizze in einer Woche", "100% Score", etc.
- **Social Compare (Future):** Bestenlisten, Freunde challengen (mit Datenschutz-Consent)

### Offene Fragen / Weitere Verfeinerung

**Schwierigkeitsgrad-Rating:**
- Wie messen wir "Schwierigkeit"? (AI-Einschätzung, Statistik aus allen Schülern, Self-Assessment?)
- Soll die AI lernen, welche Fragen wirklich schwer sind?

**Spaced Repetition:**
- **Nicht im MVP**, aber Vision: Quizze werden automatisch nach X Tagen wieder vorgeschlagen
- Exponentiell wachsende Intervalle (1 Tag → 3 Tage → 1 Woche → 1 Monat → 6 Monate)

**Quiz-Typen:**
- MVP: Multiple-Choice
- Later: Open-Text, Lückentexte, Matching, Sortieren, etc.

**Referenzmaterial:**
- Kann der Schüler ein PDF/Link hochladen? ("Erstell ein Quiz aus diesem Kapitel")
- Oder nur natürlichsprachliche Prompts?

**Social & Sharing:**
- Datenschutz: Wer darf was sehen?
- Freunde-System nötig? Oder einfach Link-Sharing?

## Nächste Schritte
- **Entscheidung:** MVP-Scope definieren (welche Gamification-Features sind Pflicht?)
- **Research:** Wie machen Duolingo/Kahoot/Quizlet ihre Adaptive Engines? (Benchmarking)
- **Bereit für:** Planning-Session → Stock Items erstellen
