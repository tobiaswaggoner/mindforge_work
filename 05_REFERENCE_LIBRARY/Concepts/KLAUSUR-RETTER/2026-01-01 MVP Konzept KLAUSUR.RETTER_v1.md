# MVP-Konzept: KLAUSUR.RETTER

> **Status:** Brainstorming-Ergebnis | **Datum:** 2026-01-01
> **Erstellt durch:** Deep Research Session mit Claude Opus 4.5

---

## Executive Summary

**KLAUSUR.RETTER** ist ein MVP-Konzept für eine KI-gestützte Lern-App, die Schülern bei der Klausurvorbereitung hilft. Der Kern: Statt gegen die Prokrastination zu kämpfen, optimieren wir dafür. Die App verwandelt "Panik 3 Tage vor der Klausur" in einen strukturierten Crash-Kurs.

**Tagline:** *"Panik? Wir auch nicht. Deine Klausur in 3 Tagen gerettet."*

**Timeline:** 2-3 Wochen bis MVP
**Kosten:** ~175€/Monat bei 1000 Usern
**Ziel:** 500-1000 Beta-User aufbauen

---

## 1. Das Problem (ehrlich)

### Was Schüler WIRKLICH tun:
- 80% fangen erst 2-3 Tage vor der Klausur an zu lernen
- ChatGPT gibt Antworten, aber keinen Plan
- WhatsApp-Gruppen explodieren mit "Was war nochmal dran?"
- Prokrastination → Panik → Chaos

### Was existierende Apps falsch machen:
- Sie wollen Schüler zu "besseren Lernern" erziehen
- Sie ignorieren dass Panik der natürliche Zustand ist
- Sie bieten keine zeitbasierte Struktur ("3 Tage bis Klausur")

---

## 2. Die Lösung

### Core Loop (30 Sekunden erklärt):
1. Schüler gibt ein: "Mathe-Klausur in 3 Tagen, Thema: Quadratische Funktionen"
2. App generiert sofort einen priorisierten Crash-Kurs
3. Jeden Tag: mundgerechte Lern-Portionen
4. Bei Problemen: 5 verschiedene Erklärwege (einer wird klicken)
5. Optional: Freunde einladen zum "Panik-Squad" (gemeinsam lernen)

### Warum das funktioniert:
- Akzeptiert Prokrastination als Realität
- Gibt Struktur in der Panik
- Social Pressure durch Squad
- Schneller Value (10 Sekunden bis zum Plan)

---

## 3. Zielgruppen-Personas

### Primär-Fokus:

#### Leonie (15, Prokrastiniererin)
- **Pain:** Kann nicht anfangen, macht alles um 23 Uhr
- **Need:** Panik-Button, schnelle Hilfe, Dopamin
- **Killer-Feature:** "Survival-Modus" mit Timer
- **Wie sie kommt:** TikTok, Freundinnen

#### Emma (18, Social Butterfly)
- **Pain:** Muss alle koordinieren, ist die Klassen-Info-Zentrale
- **Need:** Gruppen-Features, Community
- **Killer-Feature:** Panik-Squad mit Leaderboard
- **Wie sie kommt:** Lädt alle ein, ist Multiplikatorin

### Sekundär (wird mitgenommen):

#### Max (16, Überflieger)
- **Pain:** Zeitverschwendung, langweilige einfache Aufgaben
- **Need:** Effizienz, Wettbewerb
- **Killer-Feature:** Leaderboard, Speedrun

#### Yusuf (17, Stiller Kämpfer)
- **Pain:** Kann niemanden fragen, Scham
- **Need:** Anonyme, geduldige Hilfe
- **Killer-Feature:** 5-Wege-Erklärer (keine Fragen stellen müssen)
- **MUSS:** Kostenlos bleiben (Sozialfaktor)

---

## 4. Feature-Set MVP

### MUST-HAVE (Woche 1-2)

| Feature | Beschreibung | Aufwand |
|---------|--------------|---------|
| **Klausur-Setup** | Fach, Datum, Thema → Plan generieren | 2 Tage |
| **5-Wege-Erklärer** | Ein Konzept auf 5 Arten erklärt | 2 Tage |
| **Tages-Portionen** | Strukturierter täglicher Lernplan | 1 Tag |
| **Progress-Bar** | Visueller Countdown + Fortschritt | 0.5 Tage |
| **Übungs-Generator** | KI generiert Aufgaben + Lösungscheck | 2 Tage |
| **Quick-Foto-Input** | Thema fotografieren → KI versteht | 1 Tag |

### SHOULD-HAVE (Woche 2-3)

| Feature | Beschreibung | Aufwand |
|---------|--------------|---------|
| **Panik-Squad** | Freunde einladen, gemeinsamer Progress | 2 Tage |
| **Leaderboard** | Wer ist am weitesten? | 0.5 Tage |
| **Push-Reminders** | "Noch 2 Tage! 3 Aufgaben offen" | 0.5 Tage |
| **Share-Card** | Post-Klausur Erfolgs-Screenshot | 0.5 Tage |

### NICE-TO-HAVE (Post-MVP)

- Probe-Klausur Generator
- Eltern-Report (Monetarisierungs-Hook)
- Offline-Modus
- Voice-Erklärungen

---

## 5. User Journey

```
TRIGGER: Sonntag Abend, 21 Uhr - "Scheiße, Mathe-Klausur Donnerstag!"

STEP 1: PANIK-ONBOARDING (30 Sekunden)
├── Was für eine Klausur? [Mathe]
├── Wann ist sie? [Donnerstag → 3 Tage]
├── Welches Thema? [Foto oder Text]
└── Wie stehst du? [😱 Panik | 😬 Unsicher | 😊 Okay]

STEP 2: CRASH-KURS (10 Sekunden generiert)
├── TAG 1: Grundlagen (15 Min + 5 Aufgaben)
├── TAG 2: Vertiefen (20 Min + 8 Aufgaben)
└── TAG 3: Probe-Klausur (45 Min)

STEP 3: LERNEN MIT SAFETY NET
├── Aufgabe anzeigen
├── Lösung eingeben
├── Bei Problemen: "🆘 ICH HÄNG!"
│   ├── [📐 Formel]
│   ├── [🎬 Video-Style]
│   ├── [🗣️ Wie ein Freund]
│   ├── [🎮 Beispiel]
│   └── [🔙 Von Anfang]
└── Weiter zur nächsten Aufgabe

STEP 4: PANIK-SQUAD (optional)
├── "Wer schreibt auch Mathe?"
├── Link teilen → Freunde joinen
├── Gegenseitiger Progress sichtbar
└── FOMO als Motivation

STEP 5: POST-KLAUSUR
├── "Wie lief's?" [😎 Gerettet | 😅 Ging so | 💀]
├── Share-Card für Instagram/WhatsApp
└── "Nächste Klausur?"
```

---

## 6. Differenzierung zu ChatGPT

| ChatGPT | KLAUSUR.RETTER |
|---------|----------------|
| Leeres Textfeld - "Was soll ich fragen?" | "Klausur in 3 Tagen" → fertiger Plan |
| Eine Antwort (hoffen dass sie passt) | 5 verschiedene Erklärwege |
| Kein Zeitmanagement | Countdown + tägliche Portionen |
| Alleine (keine Accountability) | Mit Freunden im Squad |
| Kein sichtbarer Fortschritt | Progress-Bar + Achievements |
| Versteht Schulkontext nicht | Gebaut für deutsche Lehrpläne |

**Kern-Insight:** ChatGPT ist ein Werkzeug. KLAUSUR.RETTER ist ein Coach.

---

## 7. Viral-Strategie

### Primärer Loop: "Panik-Squad"

```
Schüler hat Panik
      ↓
Erstellt Klausur-Plan
      ↓
"Wer schreibt auch? Lernt zusammen!"
[WhatsApp teilen]
      ↓
Freunde joinen (gleiches Problem!)
      ↓
Gegenseitiger Progress → FOMO → mehr Engagement
      ↓
Nach Klausur: Erfolg teilen
      ↓
Nächste Klausur → Cycle wiederholt
```

**Warum es funktioniert:**
- 3-5 Freunde haben die gleiche Klausur
- Panik = emotionaler Share-Moment
- Kein kaltes "Invite your friends" - sondern echtes gemeinsames Problem

### Sekundärer Loop: "Gerettet-Story"

Auto-generierte Share-Card für Instagram:
```
😱 → 😎
Mathe-Klausur GERETTET
3 Tage Vorbereitung | 47 Aufgaben | 2+
─────────────────────
KLAUSUR.RETTER
```

---

## 8. Monetarisierung

### Phase 1: Pure Free (Monat 1-3)
- Alles kostenlos, Fokus auf Wachstum
- Daten sammeln für Premium-Features

### Phase 2: Soft Paywall (Monat 4+)

| FREE | PREMIUM (4,99€/Monat) |
|------|----------------------|
| 1 Klausur gleichzeitig | Unlimited Klausuren |
| 3-Wege-Erklärer | 5-Wege-Erklärer |
| Basis-Übungen | Unbegrenzte Übungen |
| 1 Squad (3 Leute) | Unbegrenzte Squads |
| ❌ Probe-Klausuren | ✅ Probe-Klausuren |
| ❌ Eltern-Report | ✅ Eltern-Report |

### Preis-Optionen:
- **Premium Einzeln:** 4,99€/Monat
- **Klausur-Pass:** 9,99€/Quartal (Klausurphasen)
- **Familien-Pack:** 7,99€/Monat (alle Kinder)

### Yusuf-Schutz (Sozialkomponente):
- "Ich kann mir das nicht leisten" Option
- Bekommt trotzdem Premium (silent, keine Scham)
- Finanziert durch zahlende Nutzer

---

## 9. Tech-Stack

### Frontend
- **Next.js 14** (App Router) als PWA
- **Tailwind CSS + shadcn/ui**
- PWA statt Native App (kein App Store nötig)

### Backend
- **Supabase** (PostgreSQL + Auth + Realtime)
- Region: Frankfurt (DSGVO)

### AI/LLM
- **Claude API** (claude-3-haiku für Speed, sonnet für Komplexes)
- Prompt-Templates pro Erklärungs-Stil

### OCR
- **Google Cloud Vision API** (Handschrift)
- **Mathpix** als Fallback für Formeln

### Mathe-Validierung
- **SymPy** (Python) für algebraische Checks

### Hosting
- **Vercel** (Frontend)
- **Supabase Cloud** (Backend)

### Kosten-Schätzung (1000 User)
| Service | Kosten/Monat |
|---------|--------------|
| Vercel Pro | 20€ |
| Supabase Pro | 25€ |
| Claude API | ~100€ |
| Google Vision | ~30€ |
| **TOTAL** | **~175€** |

---

## 10. 2-Wochen Sprint-Plan

### Woche 1: Core Loop

| Tag | Tasks |
|-----|-------|
| 1-2 | Supabase Setup, Next.js + Tailwind, Basic Routing |
| 3-4 | Klausur-Setup Flow, Claude Integration, Progress-Tracking |
| 5-7 | 5-Wege-Erklärer, Übungs-Generator, Lösungs-Check |

### Woche 2: Social + Polish

| Tag | Tasks |
|-----|-------|
| 8-9 | Panik-Squad Feature, Realtime Updates |
| 10-11 | Foto-Upload + OCR, Push Notifications |
| 12-13 | Share-Card, Landing Page |
| 14 | Testing, Bug Fixes, Soft Launch (50 Schüler) |

---

## 11. Erfolgsmetriken (30 Tage)

### North Star Metric
**"Gerettete Klausuren"** = User mit >70% Plan-Completion

### Primäre Metriken

| Metrik | Ziel Tag 7 | Ziel Tag 30 |
|--------|-----------|-------------|
| Registrierungen | 200 | 2.000 |
| Klausuren erstellt | 150 | 1.500 |
| Completion Rate (>70%) | 30% | 45% |
| Squad-Invite-Rate | 25% | 35% |
| D7 Retention | 20% | 30% |

---

## 12. Risiken & Mitigationen

| Risiko | Mitigation |
|--------|------------|
| **OCR funktioniert schlecht** | Text-Input als Fallback, "Beta" labeln |
| **AI generiert falsche Lösungen** | SymPy-Validierung für Mathe, Community-Flagging |
| **Cold-Start Squad** | Squad optional, Solo-Modus muss alleine funktionieren |
| **Nur einmalige Nutzung** | Push für nächste Klausuren, Kalender-Integration |
| **DSGVO/Minderjährige** | Minimal-Daten, Server in DE, Eltern-Consent <16 |

---

## 13. Warum NICHT die ursprüngliche Idee?

Die ursprüngliche Idee (Klassenverband + sokratischer Tutor + Mitschriebe teilen) hat folgende Probleme:

### Problem 1: Sokratischer Tutor polarisiert
- Leonie (Prokrastiniererin): "Zu langsam, zu anstrengend" → Dealbreaker
- Yusuf (Stiller Kämpfer): "Perfekt für mich" → Loves it

**Lösung:** 5-Wege-Erklärer als Alternative - Schüler wählt selbst

### Problem 2: Klassenverband = Cold Start
- Feature ist wertlos für die ersten 29 von 30 Schülern
- Niemand tritt bei wenn niemand drin ist

**Lösung:** Solo-Modus als Core, Squad als optionaler Bonus

### Problem 3: ChatGPT ist der echte Konkurrent
- Kostenlos, sofort verfügbar, gibt die Antwort

**Lösung:** Kontext + Struktur + Social = was ChatGPT nicht kann

---

## 14. Launch-Strategie

### "Schule für Schule" (nicht breiter Deutschland-Launch)

1. **3 Pilotschulen identifizieren** (über Michi/Tim?)
2. **5-10 Seed-User pro Schule** in verschiedenen Klassen
3. **Erste Klausurphase abwarten** (Oktober/November)
4. **Messen:** "An Schule X nutzen es 40% der 11. Klasse"
5. **Nächste Stadt** erst wenn eine Schule "durch" ist

### Timing
- **Optimal:** 2-3 Wochen vor Klausurphase launchen
- **Q4 2024:** Erste echte Klausuren nach Sommerferien
- **Januar 2025:** Halbjahres-Push
- **April-Mai 2025:** Abi-Phase (maximale Panik)

---

## 15. Nächste Schritte

1. **[ ] Entscheidung:** Bauen wir KLAUSUR.RETTER?
2. **[ ] Team-Briefing:** Michi + Tim als Zielgruppen-Tester
3. **[ ] Tech-Setup:** Supabase + Next.js Projekt
4. **[ ] Prompt-Engineering:** 5 Erklärungs-Stile entwickeln
5. **[ ] Pilotschulen:** 3 Schulen identifizieren
6. **[ ] Landing Page:** "Coming Soon" mit Warteliste

---

## Anhang: Alternative Konzepte (nicht gewählt)

### BRAIN BATTLE
- Quiz-Wettbewerb mit Freunden
- **Warum nicht:** Cold-Start-Problem zu groß, Kahoot dominiert den Markt

### SCHULSTOFF.WTF
- 5-Wege-Erklärung für jedes Konzept
- **Warum nicht:** Zu nah an ChatGPT-Prompt, kein Lock-in

### Original-Idee (Klassenverband + Sokratischer Tutor)
- **Warum nicht:** Cold-Start, Sokratisch polarisiert, kein klarer Zeitpunkt

---

*Erstellt durch Multi-Agent Deep Research Session*
*Nächste Review: Nach Team-Feedback*
