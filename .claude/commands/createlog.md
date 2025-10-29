# Create log

Der Benutzer möchte etwas protokollieren.
Unsere Protokolle sind im Verzeichnis @04_FORGE_LOG/

## Anweisung

1. Stelle fest, wer der Benutzer ist (Tobias oder Michel oder Tim). 
Wenn das aus dem Kontext nicht hervorgeht kann man es eventuell aus dem konfigurierten Gituser ersehen:

Git User: !`git config user.name`
Git Email: !`git config user.email`

Wenn Du es nicht weißt: Frage bevor Du weitermachst!

2. Lies Dir den User Input unten durch. Stelle Rückfragen, wenn nötig.

3. Erzeuge oder erweitere 04_FORGE_LOG/!`date +%Y-%m-%d`.md

Wenn die Datei 04_FORGE_LOG/yyyy-mm-dd.md noch nicht existiert erzeuge sie, sonst ergänze das Log.
Hier der Inhalt des Verzeichnisses:
!`ls ./04_FORGE_LOG/ -la`

Format:

```markdown
# Change Log vom yyyy-mm-dd

## {hh:MM:ss} - {username}

{summary of user prompt}

---
```

---

## USER INPUT:
$ARGUMENTS