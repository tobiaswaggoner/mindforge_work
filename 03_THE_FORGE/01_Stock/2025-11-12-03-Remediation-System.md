# Remediation-System

## Metadaten
- **Erstellt:** 2025-11-12 - Tobias Waggoner
- **Source Spark:** `02_SPARK_CHAMBER/2025-11-12-AI-Adaptive-Quiz-Generator.md`

## Was wird gebaut?
Bei falschen Antworten erklärt die AI, warum die Antwort falsch war und zeigt den richtigen Lösungsweg. Optional kann der User sagen "Ich hab's nicht verstanden" → AI vertieft das Konzept mit weiteren Erklärungen oder Beispielen.

## Warum bauen wir das?
Ohne Remediation ist das Quiz nur ein Test, kein Lernwerkzeug. Schüler lernen aus ihren Fehlern, wenn sie verstehen, WAS falsch war und WARUM. Macht das System lernwirksam statt nur "gamifiziert".

## Wer nutzt es?
Schüler (Mittel- und Oberstufe, 12-18 Jahre) - alle User, die Quizze machen und falsche Antworten geben

## User Journey

1. Tim beantwortet eine Mathe-Frage falsch (wählt Antwort B, richtig wäre C)
2. Feedback-Screen erscheint:
   - "❌ Falsch"
   - "Die richtige Antwort ist C: y = x² + 2x - 3"
   - **AI-Erklärung:** "Du hast die Normalform nicht korrekt umgestellt. Bei quadratischen Funktionen muss man zuerst die binomische Formel anwenden..."
3. Tim liest die Erklärung
4. Zwei Buttons:
   - **"Verstanden" / "Weiter"** → nächste Frage
   - **"Ich hab's nicht verstanden"** → AI vertieft das Konzept (z.B. zeigt ein Beispiel, erklärt Schritt-für-Schritt)
5. Wenn Tim "Nicht verstanden" klickt: AI gibt zusätzliche Erklärung oder ein simples Beispiel
6. Tim kann dann weitergehen zur nächsten Frage

## Definition of Done

- [ ] Bei falschen Antworten: AI generiert eine Erklärung, warum die Antwort falsch war
- [ ] Erklärung zeigt den richtigen Lösungsweg (nicht nur "richtig wäre C", sondern WARUM)
- [ ] Erklärung wird im Quiz-Canvas angezeigt (unterhalb des Feedbacks)
- [ ] Zwei Buttons: "Verstanden/Weiter" und "Ich hab's nicht verstanden"
- [ ] Wenn "Nicht verstanden" geklickt: AI vertieft das Konzept (z.B. Beispiel, Schritt-für-Schritt-Erklärung)
- [ ] User kann nach Remediation zur nächsten Frage weitergehen
- [ ] Mobile-responsive (Mobile First!)
- [ ] Bei richtigen Antworten: KEINE Remediation (nur "✅ Richtig!")

## Abhängigkeiten

- Feature 1 (Quiz-Generator-MVP) muss existieren
- LLM-Integration für dynamische Erklärungen

## Scope: Was ist NICHT Teil dieses Features?

- ❌ Adaptive Schwierigkeitsanpassung basierend auf Fehlern (kommt in Feature 4)
- ❌ Follow-up-Quizze zu Schwachstellen (späteres Feature)
- ❌ Spaced Repetition (späteres Feature)
- ❌ Quiz-Typ "Open-Text" (nur Multiple-Choice im MVP)

## Notizen

- **AI-First:** Erklärungen werden dynamisch von der AI generiert (nicht vorgefertigte Texte)
- **Tonalität:** Erklärungen sollten schülergerecht sein (verständlich, motivierend, nicht belehrend)
- **Länge der Erklärung:** Sollte kurz und knackig sein (2-4 Sätze), außer User will mehr ("Nicht verstanden")
- **Vertiefung:** Bei "Nicht verstanden" kann AI auch Gegenfragen stellen ("Was genau ist unklar? Die binomische Formel oder die Umstellung?")
- **UX-Flow:** Remediation sollte NICHT den Flow unterbrechen - User muss schnell weiterkommen können
