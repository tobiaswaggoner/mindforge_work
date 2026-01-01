# MVP-Konzept: KLAUSUR.RETTER v2

> **Status:** Konzept nach Validierung v1 | **Datum:** 2026-01-01
> **Aufbauend auf:** KLAUSUR.RETTER v1 (validiert)
> **Kern-Evolution:** Von "Crash-Kurs" zu "Kontextbasierter Klausur-Vorbereitung"

---

## 1. Executive Summary

### Was ist neu in v2?

**v1** war der Panik-Button: "Klausur in 3 Tagen? Hier ist dein Crash-Kurs."

**v2** geht einen Schritt zurueck und fragt: *"Aber was genau kommt dran?"*

| v1 | v2 |
|----|-----|
| Generischer Stoff ("Quadratische Funktionen") | **Euer** Stoff ("Wie ihr es gemacht habt") |
| User gibt Thema ein | App weiss, was im Unterricht war |
| Einzelkaempfer | Klassenverband als Wissens-Quelle |
| Erklaerungen "von der Stange" | Erklaerungen basierend auf Schüler-Profil |

### Die drei Saeulen von v2:

```
+-------------------+     +----------------------+     +------------------+
|   STUNDENPLAN     |     |   KOLLABORATIVE      |     |   KST-PFAD       |
|   INTEGRATION     |     |   STOFF-ERFASSUNG    |     |   INTEGRATION    |
+-------------------+     +----------------------+     +------------------+
        |                          |                           |
        v                          v                           v
  "Wann hattest        "Was war dran?"            "Wie lernst DU
   du Mathe?"           (alle fragen)              am besten?"
        |                          |                           |
        +------------>-------------+-------------<-------------+
                                   |
                                   v
                    +-----------------------------+
                    |  SMARTER KLAUSUR-SCOPE      |
                    |  "Binomische Formeln,       |
                    |   WIE IHR SIE GEMACHT HABT" |
                    +-----------------------------+
```

### Kern-Insight:

> **Die beste Klausur-Vorbereitung ist die, die weiss, was der Lehrer gemacht hat.**

---

## 2. Das "Was war dran?"-Problem

### Die Realitaet in deutschen Klassenzimmern:

```
ELTERNTEIL: "Ihr schreibt in 2 Tagen Mathe. Gelernt?"
SCHUELER:   "Geht so."

ELTERNTEIL: "Was kommt dran?"
SCHUELER:   "Bin nicht ganz sicher."

ELTERNTEIL: "Was habt ihr gemacht?"
SCHUELER:   "Weiss nicht."
```

### Warum das ein fundamentales Problem ist:

| Problem | Auswirkung |
|---------|------------|
| **Unklarer Scope** | Schueler lernt zu viel oder zu wenig |
| **Falsche Prioritaeten** | Zeit auf unwichtige Themen verschwendet |
| **Generische Erklaerungen** | "So macht man es" statt "So hat EUER Lehrer es erklaert" |
| **Fehlende Beispiele** | Uebungsaufgaben passen nicht zum Unterrichts-Stil |

### Der Kontext-Vorteil:

```
OHNE KONTEXT (v1):
"Erklaere mir binomische Formeln"
    -> Generische Erklaerung aus dem Lehrbuch
    -> 3 Standard-Aufgaben
    -> Hoffnung, dass es passt

MIT KONTEXT (v2):
"Erklaere mir binomische Formeln wie wir sie in Mathe hatten"
    -> Ihr habt zuerst die Herleitung am Quadrat gemacht
    -> Dann kam Herr Mueller mit seinem "Merkspruch"
    -> Diese 5 Aufgabentypen kamen in der Uebung dran
    -> DARAUF basiert die Erklaerung
```

### Der Compound Effect:

Je mehr die KI ueber den Unterricht weiss, desto besser wird sie:

```
Woche 1:  "Was sind binomische Formeln?"     -> Standard-Erklaerung
Woche 4:  "Was sind binomische Formeln?"     -> Basierend auf 12 Unterrichts-Einheiten
Woche 12: "Was sind binomische Formeln?"     -> + Wissen über Schueler-Staerken/Schwaechen
```

---

## 3. Neue Features v2

### 3.1 Stundenplan-Integration

**Das Feature:**
Der Schueler hinterlegt einmalig seinen Stundenplan. Die App weiss dann automatisch, wann welches Fach stattfindet.

**Setup-Flow:**

```
ONBOARDING (einmalig, 2 Minuten):

[1] Welche Schule?
    > Gymnasium Musterstadt ▼

[2] Welche Klasse/Stufe?
    > 11. Klasse ▼

[3] Welche Kurse hast du?
    ☑ Mathe (LK)      ☑ Deutsch (GK)
    ☑ Englisch (GK)   ☑ Physik (GK)
    ☐ Bio             ☑ Geschichte (GK)

[4] Stundenplan hochladen oder eingeben:
    [📷 Foto vom Stundenplan]  oder  [✏️ Manuell eingeben]
```

**Stundenplan-Datenmodell:**

```
+------------------+
|   STUNDENPLAN    |
+------------------+
| user_id          |
| day_of_week      | (1-5)
| period           | (1-10)
| subject          | FK -> subjects
| teacher_name     | (optional)
| room             | (optional)
+------------------+
```

**Was die App damit macht:**

| Zeitpunkt | Aktion |
|-----------|--------|
| Nach Schulschluss | Push: "Wie war Mathe heute?" |
| Vor Klausur-Setup | Vorausgefuellt: "Mathe bei Herr Mueller?" |
| Bei Erklaerungen | "Ihr habt das Thema am [Datum] gemacht" |

---

### 3.2 Kollaborative Stoff-Erfassung

**Das Problem:**
Kein einzelner Schueler weiss alles, was im Unterricht passiert ist.

**Die Loesung:**
Aggregiertes Wissen aus dem Klassenverband.

**Wie es funktioniert:**

```
NACH MATHE-STUNDE (15:30 Uhr):

App an ALLE Mathe-11LK-Mueller:

+----------------------------------------+
|  Was war heute in Mathe dran?          |
|                                        |
|  [ ] Neues Thema angefangen            |
|  [ ] Weiter am aktuellen Thema         |
|  [ ] Uebungen / Aufgaben               |
|  [ ] Klausur-Vorbereitung              |
|  [ ] Klausur-Besprechung               |
|                                        |
|  Kurz-Notiz (optional):                |
|  [________________________________]    |
|                                        |
|  [📷 Foto hinzufuegen]                 |
|                                        |
|  [  Fertig  ]      [Uebersprungen]     |
+----------------------------------------+
```

**Aggregations-Logik:**

```
EINGABEN VON 5 SCHUELERN:

Leonie:  "Neues Thema - Integrale"
Max:     "Integrale, erste Aufgaben"
Emma:    [Foto vom Tafelbild]
Yusuf:   "Weiter am aktuellen Thema"
Tim:     [uebersprungen]

         |
         v

AGGREGIERTES ERGEBNIS:
+---------------------------------------+
| MATHE 11LK | 15.03.2026 | 3. Stunde   |
+---------------------------------------+
| Thema: Integrale (NEU)                |
| Details: Einfuehrung + erste Aufgaben |
| Anhang: 1 Tafelbild                   |
| Confidence: HIGH (4/5 Antworten)      |
+---------------------------------------+
```

---

### 3.3 "Frag die Klasse"-Mechanik

**Szenario:**
Die KI soll bei einer Klausur-Vorbereitung helfen, aber es gibt keine Unterrichts-Daten fuer ein bestimmtes Thema.

**Der Flow:**

```
SCHUELER: "Bereite mich auf die Mathe-Klausur vor"

KI: "Ich sehe, ihr habt am 10.03. 'Integrale' angefangen.
     Aber fuer den 12.03. und 14.03. fehlen mir Infos.

     Soll ich deine Klasse fragen, was da dran war?

     [Ja, frag die Klasse]  [Nein, ich gebe es selbst ein]"

         |
         v (User klickt "Ja")

PUSH AN KLASSENVERBAND:
"Hey! Leon bereitet sich auf die Mathe-Klausur vor.
 Was war am 12.03. und 14.03. in Mathe dran?

 [Ich weiss es!]"
```

**Anreiz-System:**

| Aktion | Belohnung |
|--------|-----------|
| Unterrichts-Info beitragen | +5 "Helfer-Punkte" |
| Foto vom Tafelbild teilen | +10 Punkte |
| Luecke fuer anderen fuellen | +15 Punkte |
| Top-Beitraeger der Woche | Badge + Priority-Support |

---

### 3.4 Unterrichts-Historie

**Was gespeichert wird:**

```
+------------------------------------------+
|           UNTERRICHTS-EINTRAG            |
+------------------------------------------+
| id:           uuid                       |
| class_id:     "11LK-Mathe-Mueller"       |
| date:         2026-03-15                 |
| period:       3                          |
+------------------------------------------+
| topic:        "Integrale"                |
| subtopic:     "Einfuehrung Stammfunktion"|
| activity:     ["erklaerung", "uebung"]   |
| materials:    [foto_id_1, foto_id_2]     |
+------------------------------------------+
| contributors: [user_1, user_2, user_3]   |
| confidence:   0.85                       |
| verified_by:  null (oder teacher_id)     |
+------------------------------------------+
```

**Zeitliche Ansicht:**

```
MATHE 11LK - UNTERRICHTS-HISTORIE:

Maerz 2026
+-------+-------+-------+-------+-------+
|  Mo   |  Di   |  Mi   |  Do   |  Fr   |
+-------+-------+-------+-------+-------+
|       |       | 3.    |       | 5.    |
|       |       | Abl.  |       | Abl.  |
|       |       | Regeln|       | Uebung|
+-------+-------+-------+-------+-------+
| 8.    |       | 10.   |       | 12.   |
| Ketten|       | Integr|       | ???   |  <- Luecke!
| regel |       | -ale  |       |       |
+-------+-------+-------+-------+-------+
| 15.   |       | 17.   |       |       |
| Stamm |       |KLAUSUR|       |       |
| funkt.|       |       |       |       |
+-------+-------+-------+-------+-------+

[Luecke am 12.03. fuellen]
```

---

## 4. Angepasste User Journey

### v1 Journey (zur Erinnerung):

```
Panik -> Setup -> Crash-Kurs -> Lernen -> Klausur
(30s)    (30s)    (generiert)   (3 Tage)
```

### v2 Journey (erweitert):

```
+------------------------------------------------------------------+
|                        PHASE 0: ONBOARDING                       |
+------------------------------------------------------------------+
|                                                                  |
|  [Stundenplan hinterlegen] -> [Klassenverband beitreten/erstellen]|
|                                                                  |
|  Einmalig, 3-5 Minuten                                           |
+------------------------------------------------------------------+
                                |
                                v
+------------------------------------------------------------------+
|                    PHASE 1: KONTINUIERLICH                       |
+------------------------------------------------------------------+
|                                                                  |
|  Nach jeder Stunde: "Was war dran?" (10 Sekunden)                |
|                                                                  |
|  +----------------+     +----------------+     +----------------+ |
|  | Mo: Mathe      |     | Di: Deutsch    |     | Mi: Mathe      | |
|  | "Kettenregel"  |     | "Faust Akt 2"  |     | "Uebungen"     | |
|  +----------------+     +----------------+     +----------------+ |
|                                                                  |
|  -> Unterrichts-Historie waechst automatisch                     |
+------------------------------------------------------------------+
                                |
                                v
+------------------------------------------------------------------+
|                    PHASE 2: KLAUSUR-ANKUENDIGUNG                 |
+------------------------------------------------------------------+
|                                                                  |
|  "Mathe-Klausur am 17.03. - Integrale"                           |
|                                                                  |
|  App WEISS SCHON:                                                |
|  - Themen seit letzter Klausur: Ableitungen, Kettenregel, Integr.|
|  - 6 erfasste Unterrichtsstunden                                 |
|  - 3 Tafelbilder von Klassenkameraden                            |
|  - 1 Luecke (12.03. - wird abgefragt)                            |
+------------------------------------------------------------------+
                                |
                                v
+------------------------------------------------------------------+
|                    PHASE 3: SMARTER CRASH-KURS                   |
+------------------------------------------------------------------+
|                                                                  |
|  STATT generisch:          JETZT kontextbasiert:                 |
|                                                                  |
|  "Integrale allgemein"     "Integrale wie bei Herr Mueller"      |
|  3 Standard-Aufgaben       Aufgaben basierend auf euren Uebungen |
|  Eine Erklaerung           Erklaerung passend zu DEINEM Profil   |
|                                                                  |
+------------------------------------------------------------------+
                                |
                                v
+------------------------------------------------------------------+
|                    PHASE 4: LERNEN MIT KONTEXT                   |
+------------------------------------------------------------------+
|                                                                  |
|  KI: "Ihr habt am 10.03. die Stammfunktion eingefuehrt.          |
|       Hier ist das Tafelbild von Emma:                           |
|       [Bild]                                                     |
|                                                                  |
|       Basierend darauf: Erklaerung + 3 Aufgaben"                 |
|                                                                  |
|  Schueler: "Ich haeng bei Aufgabe 2"                             |
|                                                                  |
|  KI: "Du hattest bei Kettenregel auch Probleme mit der           |
|       Notation. Hier ist eine alternative Schreibweise..."       |
|                                                                  |
+------------------------------------------------------------------+
```

### Journey-Vergleich:

| Aspekt | v1 | v2 |
|--------|-----|-----|
| **Onboarding** | 30 Sekunden | 3-5 Minuten (einmalig) |
| **Zwischen Klausuren** | Keine Interaktion | Taegliche 10-Sekunden-Checks |
| **Klausur-Setup** | User gibt alles ein | Vieles vorausgefuellt |
| **Erklaerungen** | Generisch | Basierend auf Unterricht + Profil |
| **Uebungsaufgaben** | Standard | Angelehnt an echte Uebungen |

---

## 5. KST-Pfad Integration

### Was ist der KST-Pfad?

**Knowledge Space Theory (KST)** ist ein mathematisches Modell, das Wissen als Graph darstellt:
- Knoten = Faehigkeiten/Konzepte
- Kanten = Abhaengigkeiten ("Um X zu verstehen, muss man Y koennen")

**In v2 legen wir die Grundlage dafuer.**

### Was lernt die KI ueber den Schueler?

```
+------------------------------------------+
|           SCHUELER-PROFIL                |
+------------------------------------------+
|                                          |
|  ERKLAER-PRAEFERENZEN:                   |
|  +------------------------------------+  |
|  | Visuell      [=========>  ] 85%    |  |
|  | Beispiele    [=======>    ] 70%    |  |
|  | Formal       [===>        ] 30%    |  |
|  | Analogien    [========>   ] 75%    |  |
|  | Schritt-fuer-Schritt [==>] 90%     |  |
|  +------------------------------------+  |
|                                          |
|  KONZEPT-STAERKEN (Mathe):               |
|  +------------------------------------+  |
|  | Grundrechenarten    [SOLID]        |  |
|  | Bruchrechnung       [SOLID]        |  |
|  | Lineare Funktionen  [SOLID]        |  |
|  | Quadr. Funktionen   [OK]           |  |
|  | Ableitungsregeln    [LUECKE]       |  |  <- Schwachstelle!
|  | Kettenregel         [LUECKE]       |  |
|  | Integrale           [NEU]          |  |
|  +------------------------------------+  |
|                                          |
|  LERN-MUSTER:                            |
|  - Beste Zeit: Abends (19-22 Uhr)        |
|  - Session-Dauer: ~25 Minuten            |
|  - Braucht Pausen nach 3 Aufgaben        |
|  - Gibt oft nach 2. Fehlversuch auf      |
|                                          |
+------------------------------------------+
```

### Welche Daten sammeln wir?

| Datenpunkt | Quelle | Zweck |
|------------|--------|-------|
| **Antwort-Zeit pro Aufgabe** | Uebungen | Konzept-Beherrschung |
| **Fehler-Muster** | Falsche Antworten | Luecken identifizieren |
| **Erklaer-Weg-Wahl** | 5-Wege-Erklaerer | Praeferenz-Profil |
| **Hilfe-Anfragen** | "Ich haeng"-Klicks | Schwierigkeits-Mapping |
| **Session-Laenge** | Timestamps | Optimale Lern-Portionen |
| **Erfolg nach Erklaerung** | Folge-Aufgaben | Erklaer-Effektivitaet |

### Datenmodell fuer KST-Vorbereitung:

```
+------------------+     +------------------+     +------------------+
|   CONCEPT        |     |   SKILL_STATE    |     |   INTERACTION    |
+------------------+     +------------------+     +------------------+
| id               |     | user_id          |     | id               |
| name             |<----| concept_id       |     | user_id          |
| subject          |     | state            |     | concept_id       |
| prerequisites[]  |     | (new/learning/   |     | type             |
| difficulty       |     |  solid/mastered) |     | (attempt/help/   |
+------------------+     | confidence       |     |  explanation)    |
                         | last_assessed    |     | success          |
                         +------------------+     | timestamp        |
                                                  | metadata (JSON)  |
                                                  +------------------+
```

### Wie bereitet das den KST-Graphen vor?

```
PHASE 1 (v2): Daten sammeln
================================

User loest Aufgaben
      |
      v
System trackt:
- Erfolg/Misserfolg
- Hilfe-Nutzung
- Zeit benoetigt
      |
      v
Skill-States werden aktualisiert


PHASE 2 (v3+): Graph aufbauen
================================

Aus den Daten entsteht:

            [Grundlagen]
                 |
        +--------+--------+
        |                 |
   [Brueche]        [Potenzen]
        |                 |
        +--------+--------+
                 |
           [Funktionen]
                 |
        +--------+--------+
        |                 |
  [Ableitungen]     [Grenzwerte]
        |                 |
        +--------+--------+
                 |
           [Integrale]

Personalisiert fuer jeden Schueler:
- Gruene Knoten = beherrscht
- Gelbe Knoten = in Arbeit
- Rote Knoten = Luecke
- Graue Knoten = noch nicht erreicht
```

### Sofortiger Nutzen (ohne vollstaendigen KST):

Auch ohne den kompletten Graphen koennen wir:

1. **Luecken erkennen:** "Du hast bei Kettenregel Probleme - wollen wir das zuerst auffrischen?"
2. **Erklaerungen personalisieren:** "Du lernst am besten mit Beispielen - hier ist eines..."
3. **Aufgaben anpassen:** Nicht zu leicht (langweilig), nicht zu schwer (frustrierend)
4. **Lernzeit optimieren:** "Du bist nach 25 Minuten meist muede - machen wir Pause?"

---

## 6. Klassenverband-Lite

### Was es NICHT ist:

```
NICHT:
- Kein Social Network
- Keine Chats
- Keine Profile anschauen
- Keine Likes/Kommentare
- Kein "Wer ist online"
```

### Was es IST:

```
IST:
- Kollaborative Wissenssammlung
- Anonyme Beitraege (optional)
- Zweck-gebundene Interaktion
- "Schwarmintelligenz" fuer Unterrichts-Erfassung
```

### Der Klassenverband als Datenpool:

```
+----------------------------------------------------------+
|                    KLASSENVERBAND                        |
|                   "11LK-Mathe-Mueller"                   |
+----------------------------------------------------------+
|                                                          |
|  MITGLIEDER: 24 (von ~30 der Klasse)                     |
|                                                          |
|  UNTERRICHTS-HISTORIE:                                   |
|  - 45 erfasste Stunden (seit September)                  |
|  - 12 Tafelbilder                                        |
|  - 3 Arbeitsblatt-Fotos                                  |
|  - Durchschnittlich 4.2 Beitraege pro Stunde             |
|                                                          |
|  AKTIVE KLAUSUR-VORBEREITUNGEN: 8                        |
|  (fuer Klausur am 17.03.)                                |
|                                                          |
|  LUECKEN:                                                |
|  - 12.03. (keine Daten)                                  |
|  - 05.03. (nur 1 Beitrag, niedrige Confidence)           |
|                                                          |
+----------------------------------------------------------+
```

### Anonymitaets-Optionen:

| Einstellung | Sichtbar fuer andere |
|-------------|---------------------|
| **Offen** | "Emma hat ein Tafelbild geteilt" |
| **Anonym** | "Jemand hat ein Tafelbild geteilt" |
| **Versteckt** | Beitraege nur fuer System sichtbar |

**Default: Offen** (Social Proof funktioniert)
**Yusuf-Option: Anonym** (keine Scham)

### Cold-Start-Loesung:

**Problem:** Klassenverband ist wertlos, wenn nur einer drin ist.

**Loesung: "Einladen beim Beitreten"**

```
FLOW:

[1] Schueler A joined "11LK-Mathe"
         |
         v
[2] "Du bist der Erste hier!
     Lade 3 Klassenkameraden ein,
     um den Klassenverband zu aktivieren."
         |
         v
[3] [WhatsApp teilen] [Link kopieren]

    "Hey, ich nutz KLAUSUR.RETTER fuer Mathe.
     Wenn wir zusammen sind, weiss die App
     was im Unterricht dran war. Join mal!"
         |
         v
[4] 3 Leute joinen -> Klassenverband "aktiv"
         |
         v
[5] Erste Push-Notification nach naechster Mathe-Stunde
    an ALLE 4 gleichzeitig
```

**Kritische Masse:**

| Mitglieder | Status | Funktion |
|------------|--------|----------|
| 1-2 | Inaktiv | Nur eigene Daten |
| 3-5 | Minimal | Basis-Aggregation |
| 6-10 | Aktiv | Zuverlaessige Daten |
| 11+ | Optimal | Hohe Confidence |

**Fallback wenn Cold Start scheitert:**

Solo-Modus bleibt voll funktional:
- User gibt selbst ein, was dran war
- KI nutzt nur dessen Daten
- Upgrade-Pfad: "Lade Klassenkameraden ein fuer bessere Vorbereitung"

---

## 7. Technische Erweiterungen

### 7.1 Erweitertes Datenmodell

```
+------------------+     +------------------+     +------------------+
|      USER        |     |   CLASS_GROUP    |     |    SCHEDULE      |
+------------------+     +------------------+     +------------------+
| id               |     | id               |     | id               |
| email            |     | school_id        |     | user_id          |
| name             |<--->| grade            |     | day_of_week      |
| school_id        |     | subject          |     | period           |
| grade_level      |     | teacher_name     |     | class_group_id   |
| created_at       |     | year             |     +------------------+
+------------------+     | invite_code      |
        |                +------------------+
        |                        ^
        v                        |
+------------------+             |
| CLASS_MEMBERSHIP |-------------+
+------------------+     +------------------+
| user_id          |     |  LESSON_ENTRY    |
| class_group_id   |     +------------------+
| role             |     | id               |
| joined_at        |     | class_group_id   |
| anonymous_mode   |     | date             |
+------------------+     | period           |
                         | topic            |
                         | subtopic         |
                         | activity_type    |
                         | confidence_score |
                         | created_at       |
                         +------------------+
                                 ^
                                 |
                         +------------------+
                         | LESSON_CONTRIB   |
                         +------------------+
                         | id               |
                         | lesson_entry_id  |
                         | user_id          |
                         | contribution_type|
                         | content          |
                         | attachment_url   |
                         | created_at       |
                         +------------------+


+------------------+     +------------------+
|  SKILL_STATE     |     |  INTERACTION_LOG |
+------------------+     +------------------+
| id               |     | id               |
| user_id          |     | user_id          |
| concept_id       |     | concept_id       |
| subject          |     | interaction_type |
| state            |     | success          |
| confidence       |     | time_spent_ms    |
| last_assessed    |     | explanation_used |
| assessment_count |     | metadata (JSON)  |
+------------------+     | created_at       |
                         +------------------+
```

### 7.2 Push-Notification-Strategie

**Notification-Typen:**

| Typ | Trigger | Timing | Beispiel |
|-----|---------|--------|----------|
| **Post-Class** | Schulschluss | 15:30 | "Was war in Mathe?" |
| **Gap-Fill** | Klassenkamerad braucht Info | Sofort | "Leon bereitet sich vor. Was war am 12.03.?" |
| **Klausur-Reminder** | X Tage vor Klausur | 9:00 | "Noch 3 Tage bis Mathe!" |
| **Squad-Activity** | Freund lernt | Echtzeit | "Emma hat 5 Aufgaben geschafft" |
| **Weekly-Digest** | Sonntag | 18:00 | "Diese Woche: 2 Klausuren" |

**Frequenz-Limits:**

```
MAX NOTIFICATIONS PRO TAG:

Post-Class:     1 pro Fach (max 3-4 total)
Gap-Fill:       2 pro Tag
Klausur:        1 pro Klausur pro Tag
Squad:          3 pro Tag (batchable)
Digest:         1 pro Woche

TOTAL MAX:      ~8-10 pro Tag in Spitzenzeiten
NORMAL:         2-4 pro Tag
```

**Smart Timing:**

```python
def get_optimal_notification_time(user, notification_type):
    """
    Bestimmt den besten Zeitpunkt basierend auf User-Verhalten
    """

    if notification_type == "post_class":
        # Direkt nach Schulschluss (aus Stundenplan)
        return user.schedule.get_school_end_time() + timedelta(minutes=30)

    elif notification_type == "gap_fill":
        # Wenn User typischerweise aktiv ist
        return user.get_most_active_time()

    elif notification_type == "klausur_reminder":
        # Morgens, aber nicht zu frueh
        return datetime.combine(date.today(), time(9, 0))

    # Nie zwischen 22:00 und 8:00
    # Nie waehrend Unterrichtszeit (aus Stundenplan)
```

**Opt-Out Granularitaet:**

```
NOTIFICATION-EINSTELLUNGEN:

Nach dem Unterricht:     [AN]  [AUS]
Luecken fuellen:         [AN]  [AUS]
Klausur-Erinnerungen:    [AN]  [AUS]
Squad-Updates:           [AN]  [AUS]
Wochen-Zusammenfassung:  [AN]  [AUS]

Ruhezeiten:
Von [22:00] bis [08:00] keine Notifications
```

### 7.3 API-Erweiterungen

```
NEUE ENDPOINTS:

# Stundenplan
POST   /api/schedule                 # Stundenplan anlegen
GET    /api/schedule                 # Stundenplan abrufen
PATCH  /api/schedule/:id             # Stunde aktualisieren

# Klassenverband
POST   /api/class-groups             # Gruppe erstellen
GET    /api/class-groups/:id         # Gruppe abrufen
POST   /api/class-groups/:id/join    # Beitreten
GET    /api/class-groups/:id/members # Mitglieder

# Unterrichts-Erfassung
POST   /api/lessons                  # Unterricht erfassen
GET    /api/lessons?class_id=X       # Historie abrufen
POST   /api/lessons/:id/contribute   # Beitrag hinzufuegen
GET    /api/lessons/gaps             # Luecken finden

# KST-Daten
GET    /api/skills/:subject          # Skill-States abrufen
POST   /api/interactions             # Interaktion loggen
GET    /api/profile/learning         # Lern-Profil abrufen
```

---

## 8. Risiken & Mitigationen

### 8.1 Was wenn niemand antwortet?

**Risiko:** Push nach Schulschluss wird ignoriert.

| Szenario | Wahrscheinlichkeit | Mitigation |
|----------|-------------------|------------|
| Alle ignorieren | 30% | Gamification: Streak fuer taegliche Erfassung |
| Nur 1-2 antworten | 40% | Aggregation trotzdem moeglich, niedrigere Confidence |
| 3+ antworten | 30% | Optimal, hohe Confidence |

**Fallback-Strategie:**

```
WENN keine Antworten nach 2 Stunden:
    -> Reminder an aktivste User

WENN immer noch keine Antworten:
    -> Eintrag mit "keine Daten" markieren
    -> Bei Klausur-Vorbereitung: "Was war am [Datum]?" direkt fragen

WENN User selbst eingibt:
    -> Seine Eingabe wird zur Haupt-Quelle
    -> Spaetere Beitraege anderer ergaenzen
```

### 8.2 Qualitaet der Schueler-Eingaben

**Risiko:** "Keine Ahnung", "War langweilig", Troll-Eingaben

**Qualitaets-Sicherung:**

| Ebene | Massnahme |
|-------|-----------|
| **Input-Design** | Strukturierte Auswahl statt Freitext |
| **Aggregation** | Mehrere Quellen -> Median/Konsens |
| **Confidence-Score** | Niedrig wenn widersprüchlich |
| **AI-Parsing** | "Integrale" aus "irgendwas mit Flaechen" extrahieren |
| **Feedback-Loop** | "Stimmt das?" bei Klausur-Vorbereitung |

**Eingabe-Optimierung:**

```
STATT:
[Freitextfeld: Was war in Mathe?]

BESSER:
[1] Was war das Hauptthema?
    ( ) Neues Thema: [_______________]
    ( ) Weiter: [Letzte Thema automatisch]
    ( ) Uebungen
    ( ) Klausur-bezogen

[2] Hattet ihr neue Aufgabentypen?
    ( ) Ja  ( ) Nein  ( ) Weiss nicht

[3] Foto hinzufuegen?
    [📷] (optional)
```

### 8.3 Privacy im Klassenverband

**Risiko:** Schueler wollen nicht, dass andere wissen was sie lernen.

**Mitigation:**

| Bedenken | Loesung |
|----------|---------|
| "Andere sehen meine Luecken" | Skill-States sind PRIVAT, nie geteilt |
| "Ich will nicht als Streber dastehen" | Anonymer Modus fuer Beitraege |
| "Lehrer koennte mitlesen" | Klassenverband = nur Schueler, kein Lehrer-Zugang |
| "Eltern schnueffeln" | Separater Eltern-Zugang (opt-in) zeigt nur Fortschritt |

### 8.4 Technische Risiken

| Risiko | Wahrscheinlichkeit | Impact | Mitigation |
|--------|-------------------|--------|------------|
| OCR versagt bei Tafelbildern | Mittel | Mittel | Fallback: Manuelle Beschreibung |
| Push-Fatigue | Hoch | Hoch | Aggressive Frequency-Limits |
| Cold-Start Klassenverband | Hoch | Mittel | Solo-Modus als Fallback |
| DSGVO bei Klassenverband | Niedrig | Hoch | Klare Einwilligung, Minimal-Daten |

### 8.5 Adoption-Risiken

| Risiko | Mitigation |
|--------|------------|
| "Zu kompliziert geworden" | Stundenplan ist einmalig, Rest bleibt einfach |
| "Will keinen Klassenverband" | Komplett optional, Solo funktioniert |
| "Taegliche Abfrage nervt" | Ein-Tap Erfassung, Skip immer moeglich |

---

## 9. MVP-Scope v2

### 9.1 Phase 1: Sprint 1-2 (Core v2)

**Ziel:** v1 erweitern um Stundenplan + Basis-Unterrichts-Erfassung

| Feature | Prioritaet | Aufwand | Sprint |
|---------|-----------|---------|--------|
| **Stundenplan-Setup** (manuell) | MUST | 2 Tage | 1 |
| **Stundenplan-Foto-Import** | SHOULD | 2 Tage | 1 |
| **Post-Class Notification** | MUST | 1 Tag | 1 |
| **Unterrichts-Eingabe (Solo)** | MUST | 2 Tage | 1 |
| **Unterrichts-Historie Ansicht** | MUST | 1 Tag | 2 |
| **Klausur-Scope mit Historie** | MUST | 2 Tage | 2 |
| **Skill-State Tracking (Basis)** | SHOULD | 2 Tage | 2 |

**Ergebnis Sprint 2:**
Ein Schueler kann seinen Stundenplan hinterlegen, wird nach Stunden gefragt, und die Klausur-Vorbereitung nutzt diese Daten.

### 9.2 Phase 2: Sprint 3-4 (Klassenverband)

**Ziel:** Kollaborative Erfassung ermoeglichen

| Feature | Prioritaet | Aufwand | Sprint |
|---------|-----------|---------|--------|
| **Klassenverband erstellen/beitreten** | MUST | 2 Tage | 3 |
| **Invite-Flow** | MUST | 1 Tag | 3 |
| **Aggregierte Unterrichts-Eintraege** | MUST | 3 Tage | 3 |
| **"Frag die Klasse"** | SHOULD | 2 Tage | 4 |
| **Foto-Upload fuer Tafelbilder** | SHOULD | 1 Tag | 4 |
| **Confidence-Score Anzeige** | SHOULD | 1 Tag | 4 |
| **Anonymer Modus** | SHOULD | 1 Tag | 4 |

**Ergebnis Sprint 4:**
Klassenverband funktioniert, mehrere Schueler tragen bei, Daten werden aggregiert.

### 9.3 Phase 3: Sprint 5-6 (KST-Basis + Polish)

**Ziel:** Lern-Profil aufbauen, UX verfeinern

| Feature | Prioritaet | Aufwand | Sprint |
|---------|-----------|---------|--------|
| **Erklaer-Praeferenz-Tracking** | SHOULD | 2 Tage | 5 |
| **Konzept-Staerken-Dashboard** | SHOULD | 2 Tage | 5 |
| **Personalisierte Erklaerungen** | SHOULD | 3 Tage | 5 |
| **Smart Notification Timing** | SHOULD | 2 Tage | 6 |
| **Weekly Digest** | NICE | 1 Tag | 6 |
| **Onboarding-Optimierung** | MUST | 2 Tage | 6 |

**Ergebnis Sprint 6:**
v2 Feature-Complete, bereit fuer breiteren Rollout.

### 9.4 Timeline-Uebersicht

```
        Sprint 1-2          Sprint 3-4          Sprint 5-6
        (4 Wochen)          (4 Wochen)          (4 Wochen)
    +------------------+------------------+------------------+
    |                  |                  |                  |
    | STUNDENPLAN      | KLASSENVERBAND   | KST-BASIS        |
    | + SOLO-ERFASSUNG | + KOLLABORATIV   | + POLISH         |
    |                  |                  |                  |
    +------------------+------------------+------------------+
            |                  |                  |
            v                  v                  v
      Einzelner User     3-5 User pro        Personalisierte
      trackt selbst      Klasse tragen       Erklaerungen
                         bei
```

### 9.5 Erfolgsmetriken v2

**Neue North Star Metric:**
> **"Klausuren mit Kontext"** = Klausur-Vorbereitungen mit >3 erfassten Unterrichtsstunden

| Metrik | Ziel Monat 1 | Ziel Monat 3 |
|--------|-------------|--------------|
| Stundenplaene angelegt | 500 | 3.000 |
| Taegliche Unterrichts-Eingaben | 200 | 1.500 |
| Aktive Klassenverbaende | 50 | 300 |
| Durchschn. Beitraeger pro Klasse | 3 | 6 |
| Klausuren mit Kontext (>3 Stunden) | 30% | 60% |
| Unterrichts-Erfassung Retention (D7) | 25% | 40% |

---

## 10. Zusammenfassung: v1 vs v2

```
+----------------------------------------------------------+
|                         v1                                |
+----------------------------------------------------------+
|                                                          |
|   SCHUELER --> [Klausur in X Tagen] --> CRASH-KURS       |
|                                                          |
|   - Generischer Stoff                                    |
|   - Standard-Erklaerungen                                |
|   - Einzelkaempfer                                       |
|                                                          |
+----------------------------------------------------------+
                          |
                          | Evolution
                          v
+----------------------------------------------------------+
|                         v2                                |
+----------------------------------------------------------+
|                                                          |
|   [Stundenplan] --> [Taegliche Erfassung] --> [Historie] |
|                             |                            |
|   [Klassenverband] --------+                            |
|                             |                            |
|                             v                            |
|   SCHUELER --> [Klausur] --> KONTEXT-BASIERTER KURS     |
|                                   |                      |
|                    [KST-Profil] --+                      |
|                                                          |
|   - EUER Stoff                                           |
|   - Personalisierte Erklaerungen                         |
|   - Kollaborative Wissenssammlung                        |
|                                                          |
+----------------------------------------------------------+
```

### Der Kern-Shift:

> **v1:** "Hilf mir bei Mathe"
> **v2:** "Hilf mir bei UNSEREM Mathe"

---

## Anhang A: Oberstufen-Anpassung

### Persona-Shift in der Oberstufe

| Aspekt | Klasse 9-10 | Oberstufe (11-13) |
|--------|-------------|-------------------|
| **Motivation** | Meist extrinsisch | Mehr intrinsisch (Abi!) |
| **Selbstorganisation** | Gering | Besser (aber nicht gut) |
| **Bereitschaft zu investieren** | Niedrig | Hoeher |
| **Prokrastination** | Extrem | Immer noch da, aber bewusster |

### Konsequenz fuer v2:

Die erhoehte Investitionsbereitschaft in der Oberstufe erlaubt:

1. **Laengeres Onboarding** (5 Min statt 30 Sek) - akzeptabel
2. **Taegliche Micro-Interaktion** - machbar
3. **Klassenverband-Participation** - wahrscheinlicher
4. **Skill-Tracking Opt-In** - interessant fuer sie

### Aber weiterhin beachten:

- Panik bleibt der Haupttrigger
- "Schnell zum Punkt" ist immer noch wichtig
- Optional-Features muessen wirklich optional bleiben
- Der Prokrastinierer existiert auch in der 12. Klasse

---

## Anhang B: Glossar

| Begriff | Definition |
|---------|------------|
| **Klassenverband** | Gruppe von Schuelern desselben Kurses |
| **Unterrichts-Historie** | Chronologische Sammlung aller erfassten Stunden |
| **Skill-State** | Aktueller Beherrschungsgrad eines Konzepts |
| **KST** | Knowledge Space Theory - Graph-basiertes Wissensmodell |
| **Confidence-Score** | Zuverlaessigkeit einer Unterrichts-Erfassung (0-1) |
| **Cold Start** | Problem wenn Feature erst mit Nutzern funktioniert |
| **Gap-Fill** | Luecken in der Unterrichts-Historie schliessen |

---

*Erstellt: 2026-01-01*
*Basis: KLAUSUR.RETTER v1 (validiert)*
*Naechste Schritte: Team-Review, dann Sprint-Planung*
