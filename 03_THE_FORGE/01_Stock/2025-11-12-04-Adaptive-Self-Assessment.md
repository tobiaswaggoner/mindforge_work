# Adaptive Self-Assessment

## Metadaten
- **Erstellt:** 2025-11-12 - Tobias Waggoner
- **Source Spark:** `02_SPARK_CHAMBER/2025-11-12-AI-Adaptive-Quiz-Generator.md`

## Was wird gebaut?
Nach jeder Frage bekommt der User drei Buttons: "Zu leicht" / "Genau richtig" / "Zu schwer". Die AI generiert on-the-fly neue Fragen basierend auf dem Feedback und passt den Schwierigkeitsgrad dynamisch an.

## Warum bauen wir das?
Adaptive Schwierigkeitsanpassung hält Schüler im Flow-Zustand: Nicht zu leicht (langweilig), nicht zu schwer (frustrierend), sondern genau richtig. Maximiert Engagement und Lernerfolg.

## Wer nutzt es?
Schüler (Mittel- und Oberstufe, 12-18 Jahre) - alle User, die Quizze machen

## User Journey

1. Sarah macht ein Quiz zu "Quadratischen Funktionen"
2. Nach Frage 1: Sarah klickt "Zu leicht"
3. AI generiert Frage 2 mit höherem Schwierigkeitsgrad (z.B. komplexere Funktion, mehr Rechenoperationen)
4. Nach Frage 2: Sarah klickt "Genau richtig"
5. AI bleibt auf diesem Niveau für Frage 3
6. Nach Frage 3 (falsch beantwortet): Sarah klickt "Zu schwer"
7. AI generiert Frage 4 mit niedrigerem Schwierigkeitsgrad (z.B. einfachere Funktion, mehr Kontext/Hinweise)
8. Quiz passt sich kontinuierlich an Sarahs Feedback an
9. Sarah bleibt im Flow und hat Erfolgserlebnisse

## Definition of Done

- [ ] Nach jeder Frage: Drei Buttons erscheinen ("Zu leicht" / "Genau richtig" / "Zu schwer")
- [ ] User kann Self-Assessment abgeben (optional - muss nicht, kann direkt "Weiter" klicken)
- [ ] AI generiert nächste Frage basierend auf Feedback:
  - "Zu leicht" → Schwierigkeitsgrad erhöhen
  - "Genau richtig" → Schwierigkeitsgrad beibehalten
  - "Zu schwer" → Schwierigkeitsgrad senken
- [ ] Schwierigkeitsgrad-Anpassung funktioniert dynamisch (nicht vorgefertigte Fragen-Pools)
- [ ] Self-Assessment wird geloggt (für spätere Analyse/Spaced Repetition)
- [ ] Mobile-responsive (Mobile First!)
- [ ] Buttons sind gut klickbar auf Mobile (Touch-optimiert)

## Abhängigkeiten

- Feature 1 (Quiz-Generator-MVP) muss existieren
- LLM-Integration für dynamische Fragengenerierung
- Schwierigkeitsgrad-Tagging (AI muss Fragen nach Schwierigkeit generieren können)

## Scope: Was ist NICHT Teil dieses Features?

- ❌ Automatische Schwierigkeitsanpassung basierend auf Richtig/Falsch-Rate (nur Self-Assessment im MVP)
- ❌ Machine Learning für Schwierigkeitsgrad-Prädiktion (AI-Schätzung reicht)
- ❌ Statistik-basierte Schwierigkeit (z.B. "80% der Schüler haben diese Frage falsch beantwortet")
- ❌ Spaced Repetition (späteres Feature)

## Notizen

- **Self-Assessment ist optional:** User MUSS nicht klicken, kann direkt "Weiter" gehen (dann bleibt Schwierigkeitsgrad gleich)
- **AI-Schwierigkeitsgrad:** AI muss Fragen mit variablem Schwierigkeitsgrad generieren können (z.B. via Prompt: "Erstell eine schwierigere Frage zu...")
- **UX-Flow:** Self-Assessment sollte NICHT den Flow unterbrechen - Buttons sollten klein/unaufdringlich sein
- **Schwierigkeitsgrad-Granularität:** Wie viele Stufen? (z.B. 1-5? Oder kontinuierlich?)
- **Feedback-Loop:** Wenn User immer "Zu leicht" klickt, sollte Quiz irgendwann "Obergrenze" erreichen (z.B. Uni-Niveau)
- **Mobile UX:** Buttons sollten groß genug sein (Touch-Targets), aber nicht zu dominant
