# /create-flashcards — Create Anki Flashcards from Vocabulary

This skill creates Anki flashcards from vocab entries that haven't been turned into cards yet.

## Prerequisites

- **AnkiConnect** addon must be installed in Anki (addon code: `2055492159`)
- **Anki must be running** on the local machine

## Steps

1. **Read all vocab files** in `notes/Vocab/`

2. **Find unmarked entries** — rows where the `Flashcard?` column is empty (skip any marked "yes" or "no")

3. **Verify AnkiConnect is reachable:**
   ```bash
   curl -s http://localhost:8765 -X POST -d '{"action": "version", "version": 6}'
   ```
   If this fails, tell the user to open Anki and ensure AnkiConnect is installed.

4. **Ensure decks exist** — create decks if they don't exist yet:
   ```bash
   curl -s http://localhost:8765 -X POST -d '{"action": "createDeck", "version": 6, "params": {"deck": "DECK_NAME"}}'
   ```
   - Use the vocab file name as the deck name (e.g., `General.md` → deck "General Vocab", `Slang.md` → deck "Slang")

5. **Create flashcards** via AnkiConnect for each unmarked entry:
   ```bash
   curl -s http://localhost:8765 -X POST -d '{
     "action": "addNote",
     "version": 6,
     "params": {
       "note": {
         "deckName": "DECK_NAME",
         "modelName": "Basic",
         "fields": {
           "Front": "EXAMPLE_SENTENCE_WITH_BOLD_WORD",
           "Back": "TRANSLATION"
         },
         "options": {"allowDuplicate": false}
       }
     }
   }'
   ```
   - **Front:** The example sentence from the vocab file with the target word/phrase wrapped in `<b>...</b>` tags
   - **Back:** The English translation (or the user's native language translation)

6. **Update vocab files** — mark successfully created entries with "yes" in the `Flashcard?` column

7. **Display a summary:**
   - Number of flashcards created per deck
   - List of words added
   - Any errors (duplicates, connection issues)

## Important

- Only process entries where `Flashcard?` is empty — respect "no" entries (user chose to skip)
- If a word lacks an example sentence, generate one before creating the card
- Use `allowDuplicate: false` to prevent duplicate cards
- If AnkiConnect is not reachable, do not silently fail — clearly tell the user what to do
