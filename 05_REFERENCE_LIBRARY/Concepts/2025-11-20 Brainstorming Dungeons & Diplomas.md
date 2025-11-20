
https://gemini.google.com/app/f7fec79ec34a1010
# Game Design Document (GDD): Dungeons & Diplomas

Projektname: Dungeons & Diplomas (D&D)

Version: 2.0 (Comprehensive Master Document)

Genre: Educational Hybrid Rogue-lite / RPG

Plattform: Web & Mobile (Cross-Platform)

Zielgruppe: Schüler (Sekundarstufe I & II), Fokus auf Gamification-affine Lerner

Core Philosophy: "Mastery Learning disguised as a Dungeon Crawler"

## 1. Executive Summary & Vision

**"Dungeons & Diplomas"** löst das zentrale Problem von EdTech-Apps: Mangelnde intrinsische Motivation. Anstatt Lernen als "Arbeit" darzustellen, bettet D&D den Schulstoff (Mathe, Physik, Geschichte, Sprachen) als diegetische Waffe in ein fesselndes Rogue-lite Abenteuer ein.

Der Spieler kämpft nicht mit Schwertern, sondern mit Logik und Wissen gegen die Entropie. Durch die Kombination von schnellen Action-Elementen (Reflexe/Automatisierung) und rundenbasierten Taktik-Kämpfen (Tiefenverständnis/Elaboration) wird der Spieler permanent im "Flow" gehalten.

Das System nutzt **Stealth Assessment**: Während der Schüler spielt, erstellt die Engine im Hintergrund ein hochdetailliertes Kompetenzprofil, das präziser ist als jede klassische Schulnote, und passt die Spielwelt dynamisch an den Lernbedarf an.

## 2. Narrative & World Building

### 2.1 Die Prämisse: Ordnung vs. Entropie

Die Spielwelt ist ein Abbild des menschlichen Geistes. Sie wird von einer stabilisierenden Kraft zusammengehalten: Wissen (Order).

Wenn Wissen verloren geht oder vergessen wird, greift der Nebel (Gloom/Entropy) um sich.

- **Der Spieler:** Ein "Architekt der Ordnung" (oder _Lumen-Wächter_). Er besitzt die Fähigkeit, die Realität durch "Worte der Macht" (Fakten, Formeln, Vokabeln) zu stabilisieren.
    
- **Die Gegner:** Keine biologischen Monster, sondern Manifestationen von Chaos, Fehlkonzeptionen und Unwissenheit.
    
    - _Beispiel:_ Ein Goblin ist eine "kleine Inkonsistenz". Ein Boss ist ein "massives Logikloch" oder eine "kognitive Blockade".
        
- **Das Ziel:** Nicht Zerstörung, sondern **Wiederherstellung (Restoration)**. Ein Angriff mit dem Zauberstab "löscht" den Gegner nicht, sondern "korrigiert" ihn. Wenn ein Monster besiegt wird, löst es sich in harmonisches Licht oder geordnete Geometrie auf.
    

### 2.2 Visual Style: "The Stranger Things Effect"

Das Spiel nutzt einen starken visuellen Kontrast als primäres Feedback-System ("Cleaning Mechanic").

- **Korrumpiert (Upside Down):** Wenn der Spieler einen Raum betritt, ist dieser dunkel, glitchy, organisch überwuchert, verzerrt. Die Musik ist dissonant.
    
- **Gereinigt (Restored):** Nach dem Sieg über die Chaos-Wächter und der Aktivierung des Generators pulsiert eine Lichtwelle durch den Raum. Die Assets werden "geswappt": Aus Schleim wird Marmor, aus Dunkelheit wird warmes Licht. Die Musik wechselt zu harmonischen Klängen.
    
- **Effekt:** Dieser visuelle Belohnungseffekt ("PowerWash Simulator Effekt") befriedigt das menschliche Bedürfnis nach Ordnung und Abschluss.
    

## 3. Gameplay Mechanics (Der Hybrid-Ansatz)

Um kognitive Überlastung zu vermeiden und den Spielfluss (Pacing) zu erhalten, trennt D&D strikt zwischen zwei Gameplay-Modi.

### 3.1 Modus A: Top-Down Exploration (Action & Reflexe)

- **Ansicht:** Klassische Zelda/Rogue-lite Vogelperspektive.
    
- **Fokus:** Erkundung, Bewegung, Ausweichen von Fallen, Ressourcen-Management.
    
- **Gegner:** "Trash Mobs" (kleine Chaos-Kreaturen).
    
- **Kampfsystem:** Echtzeit.
    
    - Der Spieler muss nicht rechnen, sondern **Muster erkennen**.
        
    - **Binäre Entscheidungen:** Gegner haben eine Aura oder ein Symbol (z.B. Rot vs. Blau, "Nomen" vs. "Verb", ">100" vs. "<100").
        
    - Der Spieler hat zwei Angriffsarten (A und B). Er muss blitzschnell den korrekten Konter wählen.
        
- **Lernziel:** Automatisierung von Basiswissen ("Muscle Memory"). Entlastung des Arbeitsgedächtnisses für komplexere Aufgaben.
    

### 3.2 Modus B: The Duel (JRPG Side-View)

- **Trigger:** Berührung eines Elite-Gegners (Wächter), Bosses oder Interaktion mit einem "Chaos-Generator" (Puzzle-Truhe).
    
- **Transition:** Coole Kamera-Fahrt oder Screen-Shatter-Effekt (wie Final Fantasy).
    
- **Ansicht:** 2D-Seitenansicht. Links der Held (groß, detailliert), rechts der Gegner.
    
- **Fokus:** Kognitive Anstrengung, Elaboration, Problemlösung.
    
- **Kampfsystem:** Rundenbasiert oder langsamer Active Time Battle (ATB).
    
    - Die Action friert ein. Der Bildschirm wird ruhig ("De-Cluttering" für Mobile UI).
        
    - **Die Waffe:** Eine komplexe Multiple-Choice-Frage wird eingeblendet.
        
    - **UI:** Antwortmöglichkeiten werden als schwebende Runen oder Zaubersprüche dargestellt.
        
    - **Visualisierung:**
        
        - _Korrekte Antwort:_ Der Held kanalisiert Energie, wirkt einen mächtigen Zauber ("Order Strike"), spektakuläre Partikeleffekte treffen den Gegner.
            
        - _Falsche Antwort:_ Der Zauber verpufft ("Fizzle"), der Held ist offen für einen Gegenangriff.
            
- **Zeitdruck:** Vorhanden (Simuliert Prüfungsstress), aber moderat. Nutzung von Items möglich, um Zeit zu manipulieren.
    

### 3.3 Map-Progression & "Gloom" (Persistenz)

- **Struktur:** Dungeons sind nicht rein zufällig und flüchtig, sondern basieren auf dem Lehrplan.
    
    - _Oberwelt (Hub):_ Campus mit Gebäuden für Fächer (Mathe-Turm, Geschichts-Bibliothek).
        
    - _Dungeon-Flügel:_ Repräsentieren Themengebiete (z.B. "Flügel der Algebra").
        
    - _Raum-Cluster:_ Repräsentieren Sub-Topics (z.B. "Lineare Gleichungen").
        
- **Die Vergessenskurve (Ebbinghaus-Mechanik):**
    
    - Gereinigte Räume bleiben "hell", solange das Wissen frisch ist.
        
    - Vergeht Zeit ohne Wiederholung, kriecht der "Gloom" (Nebel) zurück. Räume werden erst grau, dann dunkel, dann wieder monsterverseucht.
        
    - **Motivation:** Der Spieler muss seine "Basis" instand halten. Das Wiederholen von Stoff wird zur strategischen Notwendigkeit der Territorialverteidigung ("Unkraut jäten").
        

## 4. Didaktisches Konzept & KI-Steuerung

### 4.1 Das Fragen-Modell (Canonical Questions)

Um Auswendiglernen (Pattern Matching ohne Verständnis) zu verhindern, nutzt D&D ein parametrisiertes System.

1. **Canonical Question (Master):** Die logische Struktur (z.B. `Berechne Hypotenuse c, gegeben a und b als Ganzzahlen`).
    
2. **Varianten-Generierung (LLM):** Die KI generiert zur Laufzeit Varianten dieser Frage.
    
    - _Variante A:_ Klassische Textaufgabe.
        
    - _Variante B:_ Visuelle Darstellung (Dreieck).
        
    - _Variante C:_ "Story-Problem" im RPG-Kontext ("Die Leiter zur Burgmauer...").
        
3. **Quality Control:** Die Performance der Schüler auf den Varianten wird statistisch abgeglichen. Wenn eine Variante signifikant schlechter gelöst wird als der Durchschnitt des Clusters, wird sie als "Bad Question" geflaggt und überarbeitet.
    

### 4.2 Adaptivität & Elo-Rating

- **Das doppelte Rating:**
    
    1. **Question Rating (1-10):** Initiale Einschätzung durch KI, dynamische Anpassung durch globale Spielerdaten (Crowd-Wisdom).
        
    2. **Player Rating:** Elo-Score pro Sub-Skill (z.B. Algebra-Score: 1200, Geometrie-Score: 800).
        
- **Matching:** Das Spiel generiert Gegner, die Fragen stellen, die leicht über dem aktuellen Niveau des Spielers liegen (Zone der proximalen Entwicklung).
    
    - _Zu leicht:_ Wenig XP, wenig Loot.
        
    - _Perfekt:_ Hohe XP, guter Loot.
        
    - _Zu schwer:_ Warnung durch das System ("Danger Zone").
        

### 4.3 Das Profiling (Stealth Assessment)

Jede Interaktion wird mit Timestamp geloggt.

- Reaktionszeit (Indikator für Sicherheit/Automatisierung).
    
- Fehlerart (Flüchtigkeitsfehler vs. Verständnisproblem).
    
- Nutzung von Hilfsmitteln (Jokers).
    
    Daraus entsteht ein Kompetenzprofil, das dem KI-Tutor (siehe unten) als Datenbasis dient.
    

## 5. Metagame & Motivation (Gamification)

### 5.1 Risk & Reward (Selbstregulierung)

Schüler sollen lernen, ihre Fähigkeiten selbst einzuschätzen.

- **Schreine der Gier:** Der Spieler kann HP opfern oder einen "Fluch" akzeptieren (Gegner +2 Level/Schwierigkeit), um die Chance auf "Legendary Loot" zu verdoppeln.
    
- **Entscheidung:** "Traue ich mir heute schwere Matheaufgaben zu, um das coole Schwert zu kriegen?"
    

### 5.2 Consumables (Diegetische Lernhilfen)

Klassische Joker werden als RPG-Items verpackt.

- _Trank der Zeit:_ Friert den Timer im JRPG-Kampf für 15 Sek. ein (Stressreduktion).
    
- _Schriftrolle der Weisheit:_ Entfernt 2 falsche Antworten (50:50 Joker).
    
- _Orakel-Sphäre:_ Zeigt einen Hinweis/Tipp der KI an.
    
- **Economy:** Nicht genutzte Items können am Ende des Runs für Gold verkauft werden -> Anreiz, es "ohne Stützräder" zu schaffen.
    

### 5.3 Das Nemesis-System (Emotionalisierung)

- Wenn ein Schüler wiederholt an einem spezifischen Thema scheitert (z.B. Binomische Formeln), generiert das Spiel einen **einzigartigen Boss**.
    
- **Name:** "Der Binomische Brecher" oder "Lord der Klammern".
    
- Dieser Boss verfolgt den Spieler über mehrere Runs hinweg.
    
- **Belohnung:** Der Sieg über den Nemesis (und damit die Mastery des Themas) droppt ein einzigartiges Item ("Trophäe"), das permanenten Status-Bonus gibt. Das verwandelt Frust ("Ich kann das nicht") in eine persönliche Fehde ("Ich werde dich kriegen!").
    

## 6. Der Loop: Spiel & Tutor Verbindung

Hier schließt sich der Kreis zur Lernplattform.

### 6.1 Der Zen-Meister (KI-Tutor)

Der Hub (Campus) wird von einem NPC bewohnt, dem Zen-Meister. Er ist die Personifizierung der KI-Analyse.

- Er spricht nicht wie ein Lehrer ("Du hast eine 4-"), sondern wie ein Trainer ("Deine Reflexe sind gut, aber deine Verteidigung gegen Geometrie-Angriffe hat Lücken").
    
- Er nutzt die gesammelten Daten aus den Dungeons, um den Schüler zu coachen.
    

### 6.2 Das Dojo (Deliberate Practice)

Nach einem Game Over (oder freiwillig) kann der Spieler das Dojo besuchen.

- **Revenge Training:** Der Zen-Meister stellt genau die Fragen-Typen zusammen, die zum Tod geführt haben.
    
- **Safe Space:** Kein Zeitdruck, keine Monster, reines Üben am "Boxsack".
    
- **Buff-Mechanik:** Wer das Training absolviert, erhält für den nächsten Run einen Buff ("Rache-Bonus: +20% Schaden gegen den Gegnertyp, der dich getötet hat").
    
- **Effekt:** Lernen wird zur direkten Vorbereitung auf den Sieg.
    

## 7. Technische Umsetzung & Roadmap

### 7.1 Tech Stack

- **Frontend/Game Client:** Unity oder Godot (beide hervorragend für 2D Top-Down + UI-Handling). Export als WebGL für Browser-Access + Native Mobile Build.
    
- **Backend:**
    
    - _Database:_ Firestore (NoSQL) für flexible User-Profile und Fragen-Kataloge.
        
    - _Auth:_ Firebase Auth.
        
    - _Logic:_ Cloud Functions für die Validierung von Antworten (Anti-Cheat) und Elo-Berechnung.
        
- **AI/Content:** Integration von LLM-APIs (OpenAI/Gemini) zur Generierung von Fragen-Batches ("Offline" Generierung -> Review -> Datenbank, nicht Live-Generierung im Client um Latenz zu vermeiden).
    

### 7.2 Entwicklungsphasen (Roadmap)

**Phase 1: Der Vertical Slice (Proof of Concept) - M1-M3**

- **Fokus:** Nur Mathe (Grundrechenarten).
    
- **Content:** 1 Dungeon, 1 Tile-Set (Dark/Light).
    
- **Mechanik:** Top-Down Movement, Trash Mobs (Binär), 1 Boss (JRPG-View statisch).
    
- **Ziel:** Den "Game Feel" validieren. Macht das Reinigen des Raumes Spaß?
    

**Phase 2: The Loop (Alpha) - M4-M6**

- **Fokus:** Persistenz und Progression.
    
- **Feature:** Backend-Anbindung. Speichern des Fortschritts.
    
- **Feature:** Gloom-Mechanik auf der Karte.
    
- **Feature:** Inventar & Consumables.
    
- **Ziel:** Testen der Retention. Kommen die Spieler am nächsten Tag wieder?
    

**Phase 3: Intelligence & Content Scale (Beta) - M7-M9**

- **Fokus:** Content-Masse und KI.
    
- **Feature:** Integration des LLM-Workflows für Fragen-Varianten.
    
- **Feature:** Elo-Algorithmus und Difficulty-Scaling.
    
- **Feature:** Nemesis-System.
    
- **Ziel:** Balancing der Schwierigkeit. Vermeidung von Frust und Langeweile.
    

### 7.3 Kritische Erfolgsfaktoren (KPIs)

- **Time on Task:** Wie lange verbringen Schüler freiwillig im Spiel?
    
- **Error Rate Delta:** Verbessert sich die Fehlerquote bei einem Thema nach Besuch des Dojos?
    
- **Retention Rate D1/D7/D30:** Wie regelmäßig kehren Spieler zurück, um den "Gloom" zu bekämpfen?
    

## 8. Schlusswort

"Dungeons & Diplomas" ist mehr als ein Spiel; es ist ein **Motivations-Wrapper** um einen hochkomplexen Lernprozess. Durch die Nutzung etablierter Mechanismen aus _Hades_, _Persona_ und _Zelda_ holen wir die Schüler dort ab, wo sie ihre Freizeit verbringen, und nutzen diese Energie für schulischen Erfolg. Der Schlüssel liegt nicht in "besseren Erklärvideos", sondern im **Erlebbar-Machen von Kompetenzsteigerung**.