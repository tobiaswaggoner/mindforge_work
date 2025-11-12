# Achievements & Streaks

## Metadaten
- **Erstellt:** 2025-11-12 - Tobias Waggoner
- **Source Spark:** `02_SPARK_CHAMBER/2025-11-12-AI-Adaptive-Quiz-Generator.md`

## Was wird gebaut?
Daily Streaks ("3 Tage in Folge"), Achievement-Badges ("10 Quizze in einer Woche", "100% Score", "Quiz-Marathon", etc.) → Achievements werden nach Quiz-Ende angezeigt ("🔥 Achievement freigeschaltet!") → User kann alle Achievements in Profil einsehen.

## Warum bauen wir das?
Achievements und Streaks sind mächtige Motivations-Booster für Langzeit-Engagement. Belohnen kontinuierliches Lernen und außergewöhnliche Leistungen. Gamification-Element, das Duolingo & Co. so erfolgreich macht.

## Wer nutzt es?
Schüler (Mittel- und Oberstufe, 12-18 Jahre) - alle User, die Quizze machen

## User Journey

1. Sarah macht 3 Tage hintereinander mindestens 1 Quiz
2. Nach Quiz-Ende am 3. Tag: "🔥 Achievement freigeschaltet: Quiz-Streak: 3 Tage in Folge!"
3. Sarah macht 10 Quizze in einer Woche → "🏆 Achievement freigeschaltet: Quiz-Marathon!"
4. Sarah erreicht 100% in einem Quiz → "💯 Achievement freigeschaltet: Perfekter Score!"
5. Sarah kann alle Achievements in ihrem Profil einsehen (z.B. Badge-Collection)
6. Noch nicht freigeschaltete Achievements werden ausgegraut angezeigt (mit Hinweis, wie man sie freischaltet)

## Definition of Done

- [ ] Daily Streaks werden getrackt (User muss jeden Tag mindestens 1 Quiz machen)
- [ ] Streak-Anzeige nach Quiz-Ende (z.B. "🔥 3 Tage Streak!")
- [ ] Achievement-System (mindestens 5-10 verschiedene Achievements):
  - "Quiz-Streak: 3 Tage in Folge"
  - "Quiz-Streak: 7 Tage in Folge"
  - "Quiz-Marathon: 10 Quizze in einer Woche"
  - "Perfekter Score: 100% in einem Quiz"
  - "Erste Schritte: Erstes Quiz abgeschlossen"
  - "Level-Up: Level 10 in einem Fach erreicht"
  - etc.
- [ ] Achievements werden nach Quiz-Ende als Popup/Notification angezeigt
- [ ] User kann alle Achievements in Profil/Dashboard einsehen
- [ ] Noch nicht freigeschaltete Achievements werden ausgegraut angezeigt (mit Hinweis)
- [ ] Achievements werden in DB gespeichert (persistent)
- [ ] Mobile-responsive (Mobile First!)

## Abhängigkeiten

- Feature 1 (Quiz-Generator-MVP) muss existieren
- Feature 2 (XP & Levels) muss existieren (für Level-basierte Achievements)
- Feature 5 (Quiz-Persistence) muss existieren (für Streak-Tracking)
- User-Authentication (um Achievements User-spezifisch zu speichern)
- Datenbank für Achievement-Tracking

## Scope: Was ist NICHT Teil dieses Features?

- ❌ Social Compare (Bestenlisten, "Deine Freunde haben mehr Achievements")
- ❌ Achievement-Rewards (z.B. "Schalte Avatar-Skins frei")
- ❌ Achievement-Notifications außerhalb der App (z.B. Push-Notifications)
- ❌ Streak-Freeze (z.B. "Nutze einen Freeze, um deinen Streak zu retten")
- ❌ Custom Achievements (User erstellt eigene Achievements)

## Notizen

- **Achievement-Design:** Achievements sollten verschiedene Verhaltensweisen belohnen:
  - **Konsistenz:** Daily Streaks
  - **Volumen:** 10 Quizze in einer Woche
  - **Exzellenz:** 100% Score
  - **Progression:** Level 10 erreicht
  - **Exploration:** Quizze in 5 verschiedenen Fächern
- **Streak-Zeitzone:** Wie wird "Tag" definiert? (Mitternacht? 24h seit letztem Quiz?)
- **Streak-Reminder:** Sollte User erinnert werden, wenn Streak in Gefahr ist? (Nicht in MVP, aber später)
- **Achievement-Rarity:** Soll es "seltene" Achievements geben? (z.B. "30 Tage Streak" = nur 1% der User)
- **Visual Design:** Achievements brauchen Icons/Badges (gut für Mobile-UX)
- **Micro-Interactions:** Achievement-Popup sollte "satisfying" sein (Animation, Sound?)
- **Privacy:** Achievements sind private (Default). Später opt-in Social-Sharing.
