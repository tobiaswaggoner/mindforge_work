# Quiz-Generator-MVP

## Metadaten
- **Erstellt:** 2025-11-12 - Tobias Waggoner
- **Source Spark:** `02_SPARK_CHAMBER/2025-11-12-AI-Adaptive-Quiz-Generator.md`

## Was wird gebaut?
User chattet "Erstell mir ein Quiz zu [Thema]" → AI generiert 5-10 Multiple-Choice-Fragen → Quiz wird als Canvas-Artefakt angezeigt → User beantwortet Fragen → Sofortiges Feedback (Richtig/Falsch) → Ergebnis am Ende (z.B. "8/10 richtig").

## Warum bauen wir das?
Dies ist der absolute Kern des Quiz-Systems. Ohne funktionierende Quiz-Generierung und -Darstellung gibt es kein System. Liefert sofort Nutzen und ist die Basis für alle weiteren Features.

## Wer nutzt es?
Schüler (Mittel- und Oberstufe, 12-18 Jahre) - primär auf Mobile Devices

## User Journey

1. User öffnet Mind Forge Chat auf Smartphone
2. User tippt: "Erstell mir ein Quiz zu quadratischen Funktionen"
3. AI generiert 10 Multiple-Choice-Fragen
4. Quiz erscheint als Canvas-Artefakt (vertikales Stacking: Quiz oben, Chat unten auf Mobile)
5. User beantwortet Frage 1 → Sofortfeedback: "✅ Richtig!" oder "❌ Falsch (korrekte Antwort war: B)"
6. User klickt "Weiter" → Frage 2 erscheint
7. Nach 10 Fragen: Ergebnis-Screen: "8/10 richtig – Gut gemacht!"
8. User kann Quiz beenden oder Chat fortsetzen

## Definition of Done

- [ ] User kann im Chat ein Quiz-Thema anfragen (natürlichsprachlich)
- [ ] AI generiert 5-10 Multiple-Choice-Fragen zu dem Thema
- [ ] Quiz erscheint als Canvas-Artefakt (separater Bereich neben/über dem Chat)
- [ ] Quiz-UI ist mobile-responsive (Mobile First!)
- [ ] User kann Fragen beantworten (Single-Choice-Auswahl)
- [ ] Nach jeder Antwort: Sofortfeedback (Richtig/Falsch + korrekte Antwort bei Falsch)
- [ ] Ergebnis-Screen am Ende zeigt Score (z.B. "8/10 richtig")
- [ ] Desktop: Split-Layout (Chat + Quiz nebeneinander)
- [ ] Mobile: Vertikales Stacking (Quiz + Chat)
- [ ] Quiz kann maximiert werden (Fullscreen)
- [ ] Navigation zwischen Chat und Quiz funktioniert (Wischen/Buttons auf Mobile)

## Abhängigkeiten

- Mind Forge Chat-Grundgerüst muss existieren (UI + Backend)
- LLM-Integration (für Quiz-Generierung)
- Canvas/Artifact-Pattern (Split-Layout-System)

## Scope: Was ist NICHT Teil dieses Features?

- ❌ XP/Levels (kommt in Feature 2)
- ❌ Remediation/Erklärungen bei falschen Antworten (kommt in Feature 3)
- ❌ Adaptive Schwierigkeitsanpassung (kommt in Feature 4)
- ❌ Quiz speichern/teilen (kommt in Feature 5)
- ❌ Achievements (kommt in Feature 6)
- ❌ PDF/Link-Upload für Referenzmaterial (späteres Feature)
- ❌ Andere Quiz-Typen (Open-Text, Lückentexte, etc.)

## Notizen

- **Mobile First:** Das gesamte Layout MUSS auf Mobile perfekt funktionieren
- **Canvas-Pattern:** Quiz ist ein eigenständiges Artifact (ähnlich Claude Artifacts/Gemini Canvas)
- **Schwierigkeitsgrad:** AI schätzt Schwierigkeit automatisch, aber User kann sie noch nicht beeinflussen (kommt in Feature 4)
- **Multiple-Choice:** Nur Multiple-Choice in MVP (andere Typen später)
