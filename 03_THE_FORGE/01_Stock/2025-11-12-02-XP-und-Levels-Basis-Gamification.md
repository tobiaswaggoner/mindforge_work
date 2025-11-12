# XP & Levels (Basis-Gamification)

## Metadaten
- **Erstellt:** 2025-11-12 - Tobias Waggoner
- **Source Spark:** `02_SPARK_CHAMBER/2025-11-12-AI-Adaptive-Quiz-Generator.md`

## Was wird gebaut?
Richtige Antworten geben XP → User sammelt XP pro Fach → Levels pro Fach ("Level 8 in Mathe") → Fortschrittsanzeige nach Quiz-Ende → XP und Levels werden persistent gespeichert.

## Warum bauen wir das?
Gamification ist ein zentraler Motivations-Booster. XP und Levels geben sofortiges, sichtbares Feedback und machen Fortschritt messbar. Frühe Integration stellt sicher, dass Schüler von Anfang an den "Progress-Loop" erleben.

## Wer nutzt es?
Schüler (Mittel- und Oberstufe, 12-18 Jahre) - alle User, die Quizze machen

## User Journey

1. Sarah beantwortet eine Frage richtig → "+10 XP" erscheint kurz als Feedback
2. Nach Quiz-Ende: Ergebnis-Screen zeigt:
   - "8/10 richtig – Gut gemacht!"
   - "+80 XP"
   - "Level 7 in Mathe (noch 20 XP bis Level 8)"
3. Sarah macht am nächsten Tag ein Quiz zu Geschichte → "+60 XP" → "Level 3 in Geschichte"
4. Levels sind fach-spezifisch (Mathe, Geschichte, Deutsch, etc.)
5. User kann jederzeit seinen XP/Level-Status einsehen (z.B. in Profil oder Dashboard)

## Definition of Done

- [ ] Richtige Antworten geben XP (z.B. +10 XP pro richtiger Antwort)
- [ ] XP werden pro User und pro Fach getrackt (z.B. "150 XP in Mathe", "60 XP in Geschichte")
- [ ] Levels pro Fach (z.B. "Level 7 in Mathe")
- [ ] Level-Berechnung basiert auf XP (z.B. Level 1 = 0-100 XP, Level 2 = 100-250 XP, etc.)
- [ ] Nach Quiz-Ende: XP-Anzeige im Ergebnis-Screen ("+80 XP")
- [ ] Nach Quiz-Ende: Level-Anzeige mit Progress ("Level 7 in Mathe, noch 20 XP bis Level 8")
- [ ] XP und Levels werden in DB gespeichert (persistent)
- [ ] User kann XP/Levels einsehen (z.B. Profil-Screen oder Dashboard)
- [ ] Mobile-responsive (Mobile First!)

## Abhängigkeiten

- Feature 1 (Quiz-Generator-MVP) muss existieren
- User-Authentication/Profile-System (User müssen unterscheidbar sein)
- Datenbank für XP/Level-Tracking

## Scope: Was ist NICHT Teil dieses Features?

- ❌ Achievements/Badges (kommt in Feature 6)
- ❌ Daily Streaks (kommt in Feature 6)
- ❌ Bestenlisten/Social Compare (späteres Feature)
- ❌ XP-Boosts oder Multiplier (späteres Feature)
- ❌ Level-basierte Rewards (z.B. "Bei Level 10 schaltest du X frei")

## Notizen

- **Fach-Erkennung:** AI muss automatisch erkennen, zu welchem Fach das Quiz gehört (z.B. aus dem User-Prompt "Erstell ein Quiz zu quadratischen Funktionen" → Mathe)
- **XP-Balancing:** XP-Werte und Level-Kurven müssen getestet werden (z.B. wie viele Quizze braucht man für Level 10?)
- **Visual Feedback:** "+10 XP" sollte beim Beantworten kurz als Animation erscheinen (Micro-Interaction)
- **Level-Up-Animation:** Wenn User ein neues Level erreicht, sollte das besonders gefeiert werden ("🎉 Level 8 erreicht!")
