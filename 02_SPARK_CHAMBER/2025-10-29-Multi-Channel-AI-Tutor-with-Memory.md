# Multi-Channel AI-Tutor with Memory

## Erstellt
2025-10-29 - Tobias Waggoner

## Vision in einem Satz
Ein AI-Tutor, der über Web-UI und Discord erreichbar ist, sich an jeden User individuell erinnert und dessen Persönlichkeit im Dialog anpassbar ist - ohne ein einziges Formular.

## Zielgruppe & Motivation
- **Primäre Nutzer:** Entwickler-Team + 2-3 Freunde von Tim/Michi (erste Tester)
- **Motivationale Treiber:**
  - "Cooler als ChatGPT" - etwas, das sich persönlich anfühlt
  - Niedrigschwelliger Einstieg: Dort chatten, wo man eh schon ist (Discord)
  - Der Bot passt sich an - nicht der User an den Bot

## Beschreibung

### User Journey: Erste Interaktion

**Alex, 16 Jahre, loggt sich das erste Mal ein (Web-UI oder Discord):**

1. **Erster Kontakt:**
   - Der Bot startet neutral und freundlich
   - Im natürlichen Gesprächsfluss fragt er: "Wie soll ich eigentlich mit dir reden? Eher locker wie ein Kumpel, sachlich wie ein Coach, oder gemeinsam am lernen?"
   - Alex antwortet im Dialog - keine Dropdown, kein Formular
   - Der Bot wählt daraufhin eine von 3-4 Default-Personalities als Startpunkt

2. **Erste Gespräche:**
   - Alex chattet mit dem Bot über beliebige Themen (noch kein Schul-Fokus)
   - Im Flow stellt der Bot gelegentlich Profil-Fragen (Name, Alter, Interessen) - nur wenn es passt
   - Alex kann jederzeit sagen "kein Bock auf Fragen" → Bot stoppt für diese Session

3. **Personality-Anpassung:**
   - Alex sagt im Chat: "Kannst du bitte lockerer sein?"
   - Bot erkennt die Anfrage via Tool-Call
   - Im Hintergrund: LLM-Call passt den Personality-Prompt an (mit Guardrails)
   - Bot antwortet direkt in neuem Stil

4. **Memory in Action:**
   - Alex chattet montags im Web-UI, mittwochs auf Discord
   - Der Bot erinnert sich: "Hey, wir hatten neulich über [X] geredet - willst du da weiter machen?"
   - Zwischen den Sessions: Bot "denkt nach" (asynchroner Prozess) und bereitet Themen-Hints für das nächste Gespräch vor

5. **Channel-Awareness:**
   - **Auf Discord:** Bot ist lockerer, nutzt Emojis, bietet Reactions als Quick Actions (👍 = next, 🤔 = mehr Details)
   - **Im Web-UI:** Bot ist strukturierter, formatiert Antworten klarer

### Kern-Features

#### 1. Multi-Channel-Chat
- User kann über Web-UI oder Discord mit dem Bot chatten
- Gleicher Bot, gleiches Memory, verschiedene Kanäle
- User-Identifikation über Authentifizierung (Discord-User ↔ Web-User Mapping)

#### 2. Conversation Memory
- Simples Log (Datei oder DB) speichert alle Gespräche pro User
- Bot "erinnert" sich an vorherige Chats
- Memory funktioniert kanalübergreifend

#### 3. AI-First Personality-Customizing
- Keine UI-Formulare - alles im Dialog
- User sagt: "Sei lockerer" → Bot passt sich an
- Technisch: Tool-Call erkennt Anpassungswunsch → zweiter LLM-Call schreibt neuen Personality-Prompt (mit Guardrails)
- User darf den Bot "kaputt-prompten" (Early Stage = Vertrauen in Tester)

#### 4. Natürliches Onboarding
- Kein festes Onboarding-Script
- Bot stellt Profil-Fragen (Name, Alter, Interessen, Präferenzen) im natürlichen Gesprächsfluss
- User kann ablehnen → Bot fragt in dieser Session nicht weiter
- Profil-Struktur: JSON/YAML (Details offen)

#### 5. Default-Personality-Auswahl
- Beim ersten Chat: Bot fragt im Dialog, welcher Stil passt
- 3-4 Default-Personalities als Startpunkt (z.B. "Kumpel", "Coach", "Entdecker")
- Diese wird später vom User weiter customized

#### 6. Channel-spezifisches Prompting
- Discord: Lockerer Ton, Emojis, Reactions (👍🤔📝) als Quick Actions
- Web-UI: Strukturierter, formatiert, klarer
- Automatisch per Code injected (kein User-Setting)

#### 7. Asynchroner Hintergrund-Denkprozess
- Bot "denkt nach", wenn User offline ist
- Überlegt sich Themen für das nächste Gespräch
- Hints werden beim nächsten Login in System-Prompt injected
- Trigger: Nach jedem Chat (zeitgesteuert oder Flag-basiert)

## Technisches Fundament (grob)

- **Keine komplexen Agents:** Nur Chat + Memory Log
- **Kein Web-Zugriff:** Nur LLM-Calls
- **Tool-Calling:** Für Personality-Anpassung, Discord Reactions
- **Simple Architektur:** Conversation Log (Datei oder DB), User-Profil (JSON/YAML)

## Was NICHT im Scope ist

- ❌ Slash-Commands (z.B. `/show-prompt`)
- ❌ Gamification (Streaks, XP, Achievements)
- ❌ Auto-Summaries nach jedem Chat
- ❌ Mini-Challenges
- ❌ Lern-Content / Schul-Bezug (kommt später)
- ❌ Komplexe UI-Features (alles AI-first im Dialog)

## Nächste Schritte

- [ ] **Entscheidung:** 3-4 Default-Personalities definieren (konkrete Prompts)
- [ ] **Entscheidung:** Profil-Fragen festlegen (welche Kern-Infos braucht der Bot?)
- [ ] **Architektur:** Tech-Stack klären (Backend, Discord-Bot-Framework, Memory-Storage)
- [ ] **Design:** Erste Web-UI-Skizzen (minimalistisch, Chat-fokussiert)
- [ ] **Bereit für:** Stock (sobald Architektur-Entscheidungen getroffen sind)

---

**Status:** Ready to Forge 🔨
