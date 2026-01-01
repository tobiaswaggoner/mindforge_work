# Mindforge Flywheel Strategie

> **Datum:** 2026-01-01
> **Status:** Strategisches Kerndokument
> **Ziel:** 10.000€+ MRR in 12 Monaten, bootstrapped

---

## Die Vision in einem Satz

**Mindforge baut eine zentrale Lern-Profil-Plattform (KST), die durch Spin-Off-Apps gefüttert wird - jede App löst ein spezifisches Problem, alle teilen dieselbe Datenbasis.**

---

## Die Timeline

| Meilenstein | Datum | Status |
|-------------|-------|--------|
| **D&D Live** | KW 3 (Mitte Januar) | In 14 Tagen |
| **KLAUSUR.RETTER MVP** | KW 7 (Mitte Februar) | In 6 Wochen |
| **Erste zahlende Nutzer** | KW 8-10 | Nach Launch |
| **1.000€ MRR** | Q1 2026 | |
| **10.000€ MRR** | Q4 2026 | 12-Monats-Ziel |

---

## Die Flywheel

```
     D&D (kostenlos)                    KLAUSUR.RETTER (Premium)
     ════════════════                   ════════════════════════

     Schüler spielt                     Klausur steht an
           │                                   │
           ▼                                   ▼
     Stealth Assessment                 "Wir kennen deine Lücken
     (ELO pro Konzept)                   aus D&D bereits"
           │                                   │
           └───────────┬───────────────────────┘
                       │
                       ▼
              ┌─────────────────┐
              │  KST-PROFIL     │
              │  (Mindforge)    │
              │                 │
              │  IST + SOLL     │
              │  = LÜCKE        │
              └────────┬────────┘
                       │
                       ▼
              Personalisierter Plan
                       │
                       ▼
              Erfolg → Retention
                       │
           ┌───────────┴───────────┐
           │                       │
           ▼                       ▼
     Mehr D&D spielen        Nächste Klausur
```

---

## Warum das funktioniert

### 1. D&D löst das Akquisitions-Problem

**Ohne D&D:**
- KLAUSUR.RETTER muss Nutzer "kalt" gewinnen
- Erst bei Panik relevant
- Hohe Akquisitionskosten

**Mit D&D:**
- Nutzer spielen bereits
- KST-Profil existiert schon
- KLAUSUR.RETTER ist "Upgrade", nicht "Neustart"

### 2. Stealth Assessment ist der Datenschatz

| Was D&D liefert | Was das bedeutet |
|-----------------|------------------|
| ELO pro Frage | Konzept-Mastery |
| Antwortzeit | Automatisierungsgrad |
| Fehler-Muster | Lücken-Identifikation |
| Session-Länge | Lern-Ausdauer |

**Diese Daten sammeln sich spielerisch.** Kein Test-Stress, echte Kompetenz.

### 3. Die Kombination ist der Moat

```
D&D alleine:        Nettes Spiel, aber "nur" Gamification
KLAUSUR.RETTER:     Gute App, aber woher die Lücken kennen?
KOMBINIERT:         "Wir wissen was du kannst UND was drankommt"
```

**Das kann ChatGPT nicht.** Das kann StudySmarter nicht. Das ist proprietär.

---

## Die Produkte

### Dungeons & Diplomas

| Aspekt | Detail |
|--------|--------|
| **Preis** | Kostenlos |
| **Zweck** | Akquisition + Stealth Assessment |
| **Status** | Spielbar, Launch in 14 Tagen |
| **Tech** | Next.js, Canvas, SQLite/Supabase |
| **Kern-Feature** | Quiz-Combat mit ELO-System |

**Warum kostenlos?**
- Maximale Reichweite
- Daten sind wertvoller als Einnahmen
- Funnel für Premium-Produkte

### KLAUSUR.RETTER

| Aspekt | Detail |
|--------|--------|
| **Preis** | Freemium (15€/Monat Premium) |
| **Zweck** | Monetarisierung + Klausur-Vorbereitung |
| **Status** | MVP in 6 Wochen |
| **Kern-Feature** | Kontext-basierter Crash-Kurs |

**Value Proposition:**
> "Wir retten jede Klausur. Keine Deadline ist zu kurz."

**Der Twist mit D&D:**
> "Dein D&D-Profil zeigt Lücken in Stochastik. Dein Crash-Kurs fokussiert darauf."

---

## Monetarisierung

### KLAUSUR.RETTER Pricing

| Tier | Preis | Features |
|------|-------|----------|
| **Free** | 0€ | 30 AI-Anfragen/Monat, Basis-Features |
| **Klausur-Pass** | 7€ einmalig | 7 Tage Vollzugriff, Unlimited AI |
| **Premium** | 15€/Monat | Unlimited AI, alle Features, KST-Integration |
| **Jahres-Abo** | 119€/Jahr | Premium (~10€/Monat effektiv) |
| **Klassen-Rabatt** | ab 10€/Monat | Ab 10 Personen: 10€, ab 20: 8€ |

### Markt-Kontext

| Wettbewerber | Preis/Monat |
|--------------|-------------|
| Simpleclub | ~7,50€ |
| Sofatutor Basis | ~15€ |
| ChatGPT Plus | ~19€ |
| Sofatutor Premium | 20-25€ |

**Positionierung:** Premium-Lern-App mit AI = zwischen Simpleclub und ChatGPT.

### Die Nachhilfe-Rechnung (für Eltern-Marketing)

```
NACHHILFE:        30-50€/Stunde × 4h = 120-200€ pro Klausur
KLAUSUR.RETTER:   15€/Monat = unbegrenzte Klausuren
ROI:              10-15x günstiger als Nachhilfe
```

### Kostenstruktur

**Fixkosten (bis ~10.000 User):**

| Posten | Betrag/Monat |
|--------|--------------|
| Hosting (Vercel + Supabase) | ~50€ |
| Domain + Tools | ~20€ |
| **Fixkosten gesamt** | **~70€** |

**Variable Kosten pro Premium-User:**

| Posten | Betrag/User/Monat |
|--------|-------------------|
| AI-API (Claude) | ~2,00€ |
| (inkl. Hintergrund-Tasks, Validierung, etc.) | |

### Deckungsbeitragsrechnung

**Pro User (bei 15€/Monat Premium):**

```
Umsatz:                     15,00€
- Variable Kosten (AI):      2,00€
─────────────────────────────────────
= Deckungsbeitrag:          13,00€  (87% Marge)
```

**Break-Even:**

```
Fixkosten 70€ ÷ DB 13€ = ~6 Premium-User
```

### Skalierung: Umsatz & Ertrag

| Premium-User | Umsatz | Variable Kosten | Fixkosten | **Gewinn** |
|--------------|--------|-----------------|-----------|------------|
| 10 | 150€ | 20€ | 70€ | **60€** |
| 50 | 750€ | 100€ | 70€ | **580€** |
| 100 | 1.500€ | 200€ | 70€ | **1.230€** |
| 250 | 3.750€ | 500€ | 70€ | **3.180€** |
| 500 | 7.500€ | 1.000€ | 70€ | **6.430€** |
| **667** | **10.000€** | **1.334€** | **70€** | **8.596€** |
| 1.000 | 15.000€ | 2.000€ | 70€ | **12.930€** |

### Pfad zu 10k MRR

**Ziel: 667 Premium-User bei 15€/Monat**

```
MRR:              10.000€
- API-Kosten:      1.334€
- Fixkosten:          70€
─────────────────────────
= Gewinn:          8.596€/Monat
                  (~103k€/Jahr)
```

**Conversion-Annahme:**
- 50.000 D&D-Spieler
- 10% installieren KLAUSUR.RETTER (5.000)
- 13% werden Premium (650)
- ≈ 10.000€ MRR

**Hinweis:** Bei Jahresabos (~10€/Monat effektiv) sinkt die Marge auf 8€ DB, aber Cash-Flow kommt vorab. Mix aus beiden ist realistisch.

---

## Marketing-Strategie

### Das gelöste Problem: Coding

GenAI macht einen Entwickler so produktiv wie ein 5er-Team. Coding ist kein Bottleneck.

### Die echte Challenge: Distribution

**Kanäle für D&D:**

| Kanal | Aufwand | Potenzial |
|-------|---------|-----------|
| **TikTok/Reels** | GenAI-generiert, niedrig | Hoch (Schüler-Zielgruppe) |
| **Reddit (r/schule, r/abitur)** | Organisch, niedrig | Mittel |
| **Discord-Server** | Community, niedrig | Mittel |
| **Schul-WhatsApp-Gruppen** | Viral, sehr niedrig | Sehr hoch |
| **Lehrer-Empfehlung** | Langsam, mittel | Langfristig wertvoll |

**Kanäle für KLAUSUR.RETTER:**

| Kanal | Aufwand | Potenzial |
|-------|---------|-----------|
| **D&D In-App** | Kostenlos | Höchste Conversion |
| **Instagram Stories** | GenAI, niedrig | Hoch |
| **"Gerettet"-Share-Cards** | Viral, kostenlos | Hoch |
| **Eltern-Facebook-Gruppen** | Organisch | Zahlungsbereit |

### Virale Loops

**D&D:**
- "Challenge deinen Freund"
- Schul-Highscores
- Boss-Defeat Share-Cards

**KLAUSUR.RETTER:**
- Panik-Squad (Einladen = Eigeninteresse)
- "Gerettet"-Stories nach Klausur
- Klassen-Hub (Kollaborative Erfassung)

---

## Technische Architektur

### Zentrale User-Basis

```
┌─────────────────────────────────────────┐
│           MINDFORGE AUTH                │
│         (Supabase Auth)                 │
│                                         │
│  - Zentrale User-ID                     │
│  - SSO für alle Spin-Offs               │
│  - KST-Profil verknüpft                 │
└────────────────┬────────────────────────┘
                 │
      ┌──────────┼──────────┐
      │          │          │
      ▼          ▼          ▼
   ┌─────┐   ┌─────┐   ┌─────┐
   │ D&D │   │ K.R │   │ ... │
   └─────┘   └─────┘   └─────┘
```

### KST-Profil Schema (vereinfacht)

```typescript
interface KSTProfile {
  userId: string;

  // Concept Mastery aus allen Quellen
  concepts: {
    [conceptKey: string]: {
      mastery: number;        // 0-10
      confidence: number;     // Wie viele Datenpunkte?
      lastUpdated: Date;
      sources: string[];      // ['d&d', 'klausur-retter']
    }
  };

  // Lern-Präferenzen
  preferences: {
    explanationStyle: string;
    peakHours: number[];
  };
}
```

### Datenfluss

```
D&D: Spieler beantwortet Frage
           │
           ▼
     ELO-Update in D&D
           │
           ▼
     KST-Profil Update (async)
           │
           ▼
KLAUSUR.RETTER: Liest KST-Profil
           │
           ▼
     Personalisierter Crash-Kurs
```

---

## Risiken & Mitigationen

| Risiko | Wahrscheinlichkeit | Impact | Mitigation |
|--------|-------------------|--------|------------|
| D&D findet keine Nutzer | Mittel | Hoch | Aggressive TikTok-Präsenz, Schul-Fokus |
| Stoff-Erfassung funktioniert nicht | Hoch | Kritisch | Motivations-Engine (v3), Solo-Modus als Fallback |
| ChatGPT wird besser | Sicher | Mittel | Kontext-Moat, KST-Profil ist proprietär |
| Zahlungsbereitschaft fehlt | Mittel | Hoch | Eltern-Backdoor, klarer ROI ("besser als Nachhilfe") |
| Burnout (Solo-Founder) | Mittel | Kritisch | Tim + Michi als Support, GenAI für alles |

---

## Der persönliche Kontext

**Tobias (51):**
- B2B Consulting stirbt (GenAI-bedingt)
- 12 Monate Runway für den Wechsel zu EdTech
- Bootstrapped = keine Abhängigkeit
- Ziel: Solides Unternehmen, nicht Unicorn

**Das Team:**
- Tobias: Strategie, Development, alles
- Tim (15): Rapid Prototyping, Zielgruppen-Feedback
- Michi (16): Rapid Prototyping, Zielgruppen-Feedback
- Claude: Der vierte Schmied

**Der Hebel:**
- GenAI macht einen Entwickler so produktiv wie fünf
- Coding ist gelöst → Fokus auf Marketing & Product
- Schnelle Iteration > perfekte Planung

---

## Nächste Schritte

### Diese Woche (KW 1)
- [ ] D&D: Supabase-Migration finalisieren
- [ ] D&D: Landing Page live
- [ ] KLAUSUR.RETTER: MVP-Scope festzurren

### KW 2-3
- [ ] D&D: Soft Launch
- [ ] D&D: TikTok-Content starten
- [ ] KLAUSUR.RETTER: Core-Features entwickeln

### KW 4-7
- [ ] D&D: Iteration basierend auf Feedback
- [ ] KLAUSUR.RETTER: MVP fertigstellen
- [ ] Zentrale Auth vorbereiten

### KW 8+
- [ ] KLAUSUR.RETTER: Launch
- [ ] D&D → KLAUSUR.RETTER Funnel aktivieren
- [ ] Erste Premium-Conversions

---

## Der Erfolgsindikator

In 12 Monaten:

> "Ich habe mein Consulting beendet. Mindforge macht 10k+ MRR.
> D&D hat 50k+ Spieler. KLAUSUR.RETTER hat 700+ zahlende Nutzer.
> Das war die richtige Entscheidung."

---

*"Coding ist gelöst. Marketing ist die Challenge. Execution ist alles."*
