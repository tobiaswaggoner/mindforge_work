# Quiz-Persistence & Sharing

## Metadaten
- **Erstellt:** 2025-11-12 - Tobias Waggoner
- **Source Spark:** `02_SPARK_CHAMBER/2025-11-12-AI-Adaptive-Quiz-Generator.md`

## Was wird gebaut?
Quizze werden als eigenständige Artifacts gespeichert (eigene URL) → User kann Quiz reaktivieren ("Mach das Quiz nochmal") → Quiz-Link ist teilbar (Freunde können das gleiche Quiz machen) → Ergebnisse sind private (jeder sieht nur seine eigenen).

## Warum bauen wir das?
Wiederverwendbarkeit und Social-Faktor. Schüler können Quizze wiederholen (Spaced Repetition), mit Freunden teilen oder sich gegenseitig challengen. Erhöht Engagement und Reichweite.

## Wer nutzt es?
Schüler (Mittel- und Oberstufe, 12-18 Jahre) - alle User, die Quizze erstellen oder teilen wollen

## User Journey

1. Sarah erstellt ein Quiz zu "Quadratischen Funktionen" → Quiz-ID/URL wird generiert
2. Sarah beendet das Quiz (8/10 richtig)
3. Quiz wird automatisch gespeichert (in Sarahs Profil/History)
4. Eine Woche später sagt Sarah im Chat: "Mach das Quiz zu quadratischen Funktionen nochmal"
5. AI reaktiviert das Quiz (gleiche Fragen wie beim ersten Mal)
6. Sarah macht das Quiz erneut → Neues Ergebnis (10/10) wird separat gespeichert
7. Sarah teilt den Quiz-Link mit ihrem Freund Tim: `mindforge.app/quiz/abc123`
8. Tim öffnet den Link → Kann das gleiche Quiz machen
9. Tim sieht NUR sein eigenes Ergebnis (nicht Sarahs Ergebnis)
10. Sarah sieht NUR ihr eigenes Ergebnis (auch wenn Tim das Quiz gemacht hat)

## Definition of Done

- [ ] Jedes Quiz bekommt eine eindeutige ID/URL (z.B. `mindforge.app/quiz/abc123`)
- [ ] Quizze werden in DB gespeichert (persistent)
- [ ] User kann Quiz reaktivieren (z.B. via Chat: "Mach das Quiz nochmal")
- [ ] Quiz-Link ist teilbar (z.B. via "Teilen"-Button im Quiz)
- [ ] Fremde User können geteilte Quizze über Link öffnen und machen
- [ ] Ergebnisse sind **private**: Jeder User sieht nur seine eigenen Ergebnisse
- [ ] Quizze sind **public**: Jeder kann jedes Quiz machen (wenn er den Link hat)
- [ ] User kann eigene Quiz-History einsehen (z.B. "Meine Quizze")
- [ ] Mobile-responsive (Mobile First!)

## Abhängigkeiten

- Feature 1 (Quiz-Generator-MVP) muss existieren
- Datenbank für Quiz-Storage (Fragen, Antworten, Metadaten)
- Datenbank für Results-Storage (User, Quiz-ID, Antworten, Score, Timestamp)
- User-Authentication (um Ergebnisse User-spezifisch zu speichern)

## Scope: Was ist NICHT Teil dieses Features?

- ❌ Bestenlisten/Leaderboards (späteres Feature)
- ❌ Social Compare ("Tim hat 10/10, du nur 8/10")
- ❌ Freunde-System (Link-Sharing reicht)
- ❌ Quiz-Editing (User kann Quiz nicht nachträglich ändern)
- ❌ Spaced Repetition (automatische Wiederholung nach X Tagen)
- ❌ Quiz-Discovery ("Beliebte Quizze", "Empfohlene Quizze")

## Notizen

- **Privacy-First:** Ergebnisse sind immer private. Später kann es opt-in Social-Features geben (z.B. "Teile dein Ergebnis"), aber Default ist private.
- **Quiz-Versionierung:** Wenn User sagt "Mach das Quiz nochmal", sollten die gleichen Fragen kommen (sonst ist Vergleich schwierig). ODER: AI bietet an: "Gleiches Quiz oder neue Fragen zum gleichen Thema?"
- **URL-Struktur:** `mindforge.app/quiz/{quiz-id}` (kurze, teilbare URLs)
- **Share-Button:** Quiz sollte "Teilen"-Button haben (Copy-Link, WhatsApp, etc.)
- **Quiz-Metadata:** Speichern: Ersteller, Thema, Schwierigkeitsgrad, Erstelldatum, Anzahl der Teilnehmer
- **Results-Tracking:** Speichern: User, Quiz-ID, Antworten (welche Frage, welche Antwort, richtig/falsch), Self-Assessment, Timestamp
