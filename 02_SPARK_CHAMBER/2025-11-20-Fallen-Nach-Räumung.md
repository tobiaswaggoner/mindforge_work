# Fallen & Dekoration nach Dungeon-Räumung

## Kern-Idee
Nach erfolgreichem Abschluss eines Dungeon-Runs (Generator repariert, Gegner besiegt) kann der Spieler den geräumten Dungeon mit Fallen und Dekorationen ausstatten. Dies schafft einen motivierenden "Post-Victory"-Moment und belohnt erfolgreiche Lernaktivität.

## Gameplay-Mechanik

### Phase 1: Dungeon Räumen (Bestehend)
1. Spieler betritt prozedural generierten Dungeon
2. Bekämpft Gegner durch Lösen von Mathe-Aufgaben
3. (Sammelt Ressourcen/Schrott)
4. Repariert Generator durch Lösen komplexerer Mathe-Challenges
5. Dungeon ist "geräumt" → Victory Screen

Im Architect Mode kann der Spieler:
- **Fallen platzieren**: Spikes, Feuer, Eisflächen, Giftgas, Laser-Grids
- **Dekoration hinzufügen**: Kristalle, Fackeln, Banner, Trophäen, gruselige Elemente
- **Raum-Layouts anpassen**: Wände verschieben (begrenzt), Türen hinzufügen

## Pädagogischer Mehrwert

### 1. Belohnungssystem
- Direkte Belohnung für erfolgreiche Mathe-Aufgaben
- Motivation durch kreative Freiheit
- "Ownership" des geräumten Dungeons

### 2. Progression sichtbar machen
- Geräumte Dungeons werden in einer "Dungeon Gallery" gespeichert
- Jeder Dungeon zeigt Schwierigkeitsgrad und erreichte Punkte
- Visuelles Portfolio des Lernfortschritts

### 3. Wiederholungsanreiz
- Bessere Performance = mehr Fallen-Punkte = coolere Designs
- Schüler spielen Level mehrfach, um bessere Ergebnisse zu erzielen
- Implizites Üben ohne "Drill-Gefühl"

## Design-Varianten

### Variante A: "Trophy Dungeon" (Passiv)
- Geräumte Dungeons sind reine Galerie-Stücke
- Fokus auf Ästhetik und Sammler-Aspekt
- Keine weitere Interaktion

### Variante B: "Challenge Dungeon" (Aktiv)
- Spieler können ihre customized Dungeons als Challenge für andere freigeben
- Andere Schüler (oder KI-Bots) versuchen, den Dungeon zu meistern
- Creator erhält Bonus-Punkte, wenn sein Dungeon "tough but fair" ist

### Variante C: "Tower Defense Twist"
- Geräumter Dungeon wird zu einem Tower-Defense-Level
- Spieler platziert Fallen strategisch
- KI-Gegner versuchen, den Generator zurückzuerobern
- Fallen-Effektivität = neue Mathe-Mini-Challenges während der Verteidigung

## Technische Überlegungen

### Assets benötigt
- Fallen-Sprites (animiert): ~8-12 verschiedene Typen
- Deko-Assets: ~20-30 Objekte (verschiedene Themes)
- UI für Architect Mode: Drag-and-Drop Interface
- Speichersystem für customized Dungeons

### Komplexität
- **Low:** Variante A (reine Galerie)
- **Medium:** Variante B (mit Sharing)
- **High:** Variante C (Tower Defense Mechanik)

## Nächste Schritte (Vorschlag)

1. **Prototyp mit Variante A** beginnen (MVP)
2. User-Testing: Motiviert es wirklich zur Wiederholung?
3. Bei positivem Feedback: Variante B als Social Layer
4. Variante C als potentielles "Endgame Feature"

## Offene Fragen

- [ ] Sollen Fallen-Designs thematisch sein (z.B. Eis-Dungeon = Eis-Fallen)?
- [ ] Wie viele Fallen-Punkte pro Level-Schwierigkeit?
- [ ] Soll es seltene/legendäre Fallen geben (Gacha-Element)?
- [ ] Integration mit Schul-Curriculum: Themen-spezifische Deko (Geometrie-Dungeon)?