# /summarize-month — Monthly Learning Summary

This skill generates a summary of the user's learning progress over the past month.

## Steps

1. **Read all daily notes** from the current calendar month in `notes/Daily Notes/`

2. **Read weekly summaries** from `notes/Weekly Summaries/` for the current month

3. **Check vocab growth** — count entries added this month across all vocab files

4. **Create a summary file** in `notes/Monthly Summaries/` named `Month YYYY.md` (e.g., `February 2026.md`)

5. **Document structure** (write in the target language at the user's level):

   ```markdown
   # Monthly Summary: Month YYYY

   ## Overview
   - [X] days with notes
   - [X] new vocabulary words
   - Topics covered: [list]

   ## Trends
   - [Patterns observed across the month — recurring topics, grammar areas, strengths]

   ## Areas to Improve
   - [Persistent gaps, recurring errors identified across weekly summaries]

   ## Recommendations for Next Month
   - [Concrete suggestions oriented toward the user's goals and timeline]
   ```

## Important

- Synthesize across the whole month — don't just list each week
- Identify trends and patterns that may not be visible in weekly summaries
- Connect recommendations to the user's stated goals and timeline
- Write in the target language at the user's current level (refer to CLAUDE.md)
- If CLAUDE.md hasn't been configured, write in English
