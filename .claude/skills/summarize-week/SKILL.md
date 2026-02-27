# /summarize-week — Weekly Learning Summary

This skill generates a summary of the user's learning progress over the past week.

## Steps

1. **Determine the date range** — past 7 days from today

2. **Read all daily notes** in `notes/Daily Notes/` whose filenames (YYYYMMDD.md) fall within the past 7 days

3. **Check vocab additions** from the past week by reading vocab files and cross-referencing with note dates

4. **Create a summary file** in `notes/Weekly Summaries/` named `YYYYMMDD - YYYYMMDD.md` (start date - end date)

5. **Document structure** (write in the target language at the user's level):

   ```markdown
   # Weekly Summary: YYYYMMDD - YYYYMMDD

   ## This Week
   - [Date]: [Brief description of topics, source/activity]
   ...

   ## New Vocabulary
   - [Count] new words added
   - Key words: [list notable additions]

   ## Areas to Improve
   - [Based on corrections, gaps, and patterns from lesson notes]

   ## Recommendations for Next Week
   - [Concrete suggestions oriented toward the user's goals]
   ```

## Important

- If no notes were recorded for the week, note this and provide general encouragement/recommendations
- Base improvement areas on actual patterns in the notes, not generic advice
- Keep recommendations specific and actionable
- Write in the target language at the user's current level (refer to CLAUDE.md)
- If CLAUDE.md hasn't been configured, write in English
