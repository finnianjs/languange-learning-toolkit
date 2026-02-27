# /update-vocab — Sync New Vocabulary to Central Lists

This skill reads daily lesson notes and syncs any new vocabulary into the central vocab files.

## Steps

1. **Read all daily notes** in `notes/Daily Notes/` (files named YYYYMMDD.md)

2. **Read current contents** of all vocab files in `notes/Vocab/`

3. **Parse vocab tables** from each daily note. Look for tables under `# Vocab:` headings. Extract each row's word/phrase, translation, note, and category.

4. **Identify new entries** — compare against existing vocab files. A word is "new" if it doesn't already appear in any central vocab file. Match on the Word/Phrase column (case-insensitive, ignore leading/trailing whitespace).

5. **Classify and add new entries** to the appropriate vocab file:
   - If a Category column value matches a separate vocab file name (e.g., words tagged "slang" go to `Slang.md` if it exists), add to that file
   - Otherwise, add to `General.md`

6. **For each new entry:**
   - Fill in the Translation if it was left empty in the lesson note (provide an accurate translation)
   - Copy any Note(s) from the daily note
   - Generate an example sentence in the target language at the user's current level (refer to CLAUDE.md for level and language details)
   - Leave the `Flashcard?` column empty (the user marks this themselves)

7. **Display a summary** showing:
   - How many new words were found
   - Which words were added to which vocab file
   - Any words that were skipped (already existed)

## Important

- Never remove or modify existing vocab entries
- Preserve the exact table formatting in vocab files
- If no new vocab is found, say so — don't create empty entries
- Example sentences should be natural and contextual, at the user's proficiency level
- If CLAUDE.md specifies a dialect or regional variant, use it naturally in example sentences
