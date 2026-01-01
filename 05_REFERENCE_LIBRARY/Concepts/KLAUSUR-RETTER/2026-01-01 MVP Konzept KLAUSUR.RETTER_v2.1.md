# KLAUSUR.RETTER v2: Kontext-Edition

> **Status:** Konzept v2 | **Datum:** 2026-01-01
> **Evolution von:** KLAUSUR.RETTER v1
> **Kern-Änderung:** Kollaborative Unterrichts-Erfassung + KST-Pfad

---

## 1. Executive Summary

### Was ist neu in v2?

**v1 Problem:** Generische Crash-Kurse zu "Binomische Formeln" - aber was genau davon war dran?

**v2 Lösung:** Die KI weiß, was im Unterricht passiert ist.

```
v1: "Mathe-Klausur in 3 Tagen, Thema: Binomische Formeln"
    → Generischer Crash-Kurs

v2: "Mathe-Klausur in 3 Tagen"
    → App kennt die letzten 6 Wochen Unterricht
    → Präziser Crash-Kurs mit EUREM Stoff
```

### Die drei Säulen von v2:

| Säule | Beschreibung |
|-------|--------------|
| **Stundenplan** | App weiß wann welches Fach ist |
| **Stoff-Erfassung** | Kollaborativ: Was war heute dran? |
| **KST-Pfad** | KI lernt über den Schüler (für später) |

---

## 2. Das "Was war dran?"-Problem

### Die Realität am Küchentisch:

```
Eltern: "Ihr schreibt in 2 Tagen Mathe. Gelernt?"
Kind:   "Geht so."
Eltern: "Was kommt dran?"
Kind:   "Bin nicht ganz sicher."
Eltern: "Was habt ihr in den letzten Wochen gemacht?"
Kind:   "Weiß nicht genau."
```

### Warum ist das so?
- 15 Fächer pro Woche - Niemand behält alles
- Keine Notizen - Oder unleserlich
- Lehrer sagt's einmal - und es wird vergessen
- Krank gewesen - Eine Woche fehlt komplett

---

## 3. Neue Features v2

### 3.1 Stundenplan-Integration

**Setup (einmalig, 2 Minuten):**
- Foto vom Stundenplan (OCR)
- Manuell eingeben
- Import aus Untis/WebUntis (falls Schule nutzt)

**Ergebnis:** App weiß Montag 3.+4. Stunde = Mathe bei Herr Müller

### 3.2 Post-Class Notification

**Trigger:** 5 Minuten nach Stundenende

```
🔔 Mathe ist gerade vorbei.
Was habt ihr heute gemacht?
[Schnell eintragen →]
```

**Eingabe (10-15 Sekunden):**
- Text: "Binomische Formeln weiter, Aufgabe 4a-c S.127"
- Foto von Tafel/Heft
- Spracheingabe
- Checkboxen: Klausur-Ankündigung? Hausaufgaben? Neues Thema?

### 3.3 Kollaborative Stoff-Erfassung

**Das Prinzip:**
- Nicht JEDER muss JEDE Stunde eintragen
- 3-5 Schüler einer Klasse reichen
- Die KI aggregiert und ergänzt

```
UNTERRICHTS-EINTRAG: Mathe, 13.01.

Quelle 1 (Max): "Binomische Formeln, Buch S.127"
Quelle 2 (Emma): [Foto von Tafelanschrieb]
Quelle 3 (Leonie): "4a bis 4c als Hausaufgabe"

─────────────────────────────────
KI-AGGREGAT:
├─ Thema: Binomische Formeln (Vertiefung)
├─ Seite: 127, Aufgaben 4a-c
├─ Hausaufgaben: bis Mittwoch
└─ Material: [Tafelbild angehängt]
```

### 3.4 "Frag die Klasse"-Mechanik

Wenn eine Lücke entsteht (niemand hat eingetragen):
- Push an alle: "Was war Freitag in Physik?"
- Jemand antwortet → Lücke gefüllt
- Keiner antwortet → Bleibt als "unbekannt" markiert

---

## 4. Angepasste User Journey

```
TÄGLICH (10 Sek)         WÖCHENTLICH          VOR KLAUSUR
────────────────         ───────────          ───────────
Post-Class Check-In  →   Wochen-Übersicht  →  Klausur-Modus
"Was war in Mathe?"      "Diese Woche:"       KONTEXT-BASIERTER
                         Quick-Review         CRASH-KURS
       ↓                       ↓                    ↓
Unterricht gespeichert   "5 Fragen zum Check" Basierend auf EUREM
→ Historie wächst                             Unterricht der letzten
                                              6 Wochen
```

### Persona-Anpassung Oberstufe:
- Höhere intrinsische Motivation (Abi-Druck)
- Tägliches Check-In wird eher akzeptiert
- Erklärungen können komplexer sein

---

## 5. KST-Pfad Integration

### Was lernt die KI über den Schüler?

**Erklärungs-Präferenzen:**
- Bevorzugter Stil: "Wie ein Freund" (72% Nutzung)
- Meidet: "Formal/Formel" (nur 8%)
- Bei Mathe: Visualisierung hilft

**Konzept-Stärken:**
```
Bruchrechnung: ████████░░ 85%
Gleichungen:   ██████░░░░ 60%
Geometrie:     ████░░░░░░ 40%
Stochastik:    ██░░░░░░░░ 20% ← Lücke identifiziert
```

**Lern-Verhalten:**
- Aktive Zeit: Abends 20-22 Uhr
- Ø Session: 18 Minuten
- Ø Aufgaben: 7 pro Session

### Daten die wir sammeln:

| Datenpunkt | Erfassung | Nutzen |
|------------|-----------|--------|
| Gewählter Erklär-Weg | Bei "Ich häng" | Präferenz-Profil |
| Erfolg nach Erklärung | Nächste Aufgabe richtig? | Was funktioniert |
| Zeit pro Aufgabe | Automatisch | Automatisierungsgrad |
| Themen-Historie | Aus Unterricht | Abgedeckte Konzepte |
| Fehler-Muster | Falsche Antworten | Lücken-Erkennung |

### Vorbereitung für KST-Graph:

```
JETZT (v2):                    SPÄTER (Mindforge):
───────────                    ────────────────────
Implizites Tracking            Expliziter KST-Graph

"Max hat 3x bei Gleichungen    Bruchrechnen → Gleichungen
 die Bruch-Erklärung              (Prerequisite-Link
 gebraucht"                        automatisch erkannt)
        ↓
"Hypothese: Bruch-Lücke"
        ↓
"Bei nächster Klausur:
 Brüche vorschlagen"
```

---

## 6. Klassenverband-Lite

### Was es NICHT ist:
- ❌ Social Network
- ❌ Chat-Plattform
- ❌ Profile angucken

### Was es IST:
- ✅ Kollaborative Wissenssammlung
- ✅ Aggregierte Unterrichts-Historie
- ✅ Anonyme Beiträge möglich

### Cold-Start lösen:

1. Erster Schüler erstellt Klassenverband "Mathe 11b bei Herr Müller"
2. Teilt Link in Klassen-WhatsApp
3. Kritische Masse bei 3-5 Schülern
4. Ab da funktioniert kollaborative Erfassung

**Fallback:** Klassenverband mit 1 Person funktioniert auch (nur eigene Einträge)

---

## 7. Technische Erweiterungen

### Neue Datenmodell-Elemente:

```
schedules (Stundenplan)
├── user_id, day_of_week, period, subject_id

class_entries (Unterrichts-Einträge)
├── class_group_id, date, content, media_urls[]
├── entry_type (normal|homework|exam_announced)

class_groups (Klassenverband)
├── name, subject_id, teacher_name, invite_code

learning_profiles (Schüler-Lernprofil für KST)
├── preferred_explanation_styles[], concept_strengths{}
```

### Push-Notification-Regeln:
- Max 2 pro Tag
- Nie während Unterricht (Stundenplan-aware)
- Optimale Zeit: 5 Min nach Stundenende

---

## 8. Risiken & Mitigationen

| Risiko | Mitigation |
|--------|------------|
| **Niemand trägt ein** | Solo-Modus funktioniert auch alleine |
| **Zu unspezifisch** | KI fragt nach: "Welches Thema genau?" |
| **Privacy-Bedenken** | Anonyme Beiträge möglich, Profil nur für eigenen Crash-Kurs |
| **Adoption Stundenplan** | Foto-Import macht es in 30 Sek |

**Fallback-Kette:**
```
Klassenverband mit Daten → Beste Erfahrung
        ↓
Klassenverband ohne Daten → "Trag schnell ein"
        ↓
Kein Klassenverband → Generischer Modus (wie v1)
```

---

## 9. MVP-Scope v2

### Phase 1: Solo + Stundenplan (Sprint 1-2)
- Stundenplan-Setup (Foto oder manuell)
- Post-Class Notification
- Eigene Unterrichts-Einträge
- Klausur-Modus mit eigenem Kontext
- Basis-Lernprofil

### Phase 2: Klassenverband (Sprint 3-4)
- Klassenverband erstellen/beitreten
- Aggregierte Einträge
- "Frag die Klasse" Mechanik

### Phase 3: KST-Basis (Sprint 5-6)
- Erweitertes Lernprofil
- Lücken-Erkennung + Empfehlungen
- Konzept-Stärken-Visualisierung

### Neue Metriken:

| Metrik | Ziel |
|--------|------|
| Dokumentationsrate | 60% der Stunden |
| Ø Zeit pro Eintrag | <20 Sekunden |
| Klassenverband-Größe | Ø 5 Mitglieder |
| **Klausuren mit Kontext** | 70% (North Star) |

---

## 10. v1 → v2 Unterschiede

| v1 | v2 |
|----|----|
| Generischer Crash-Kurs | Kontext-basierter Crash-Kurs |
| Einmal-Nutzung (vor Klausur) | Kontinuierliches Tracking |
| Solo-only | Solo + Klassenverband |
| KI kennt Schüler nicht | KI lernt Präferenzen + Lücken |
| Panik-Squad (Social) | Klassenverband-Lite (Utility) |

### Der Kern-Unterschied:

> **v1:** "Was ist dein Thema?" → Generiere Crash-Kurs
>
> **v2:** "Wann ist die Klausur?" → Wir wissen schon was dran war

---

*v2 erstellt basierend auf Tobias' Feedback: Kontext ist der Schlüssel*
