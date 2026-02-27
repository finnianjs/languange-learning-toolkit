# /weekly-tips — Generate Weekly Study Recommendations

This skill generates personalized weekly study tips based on the user's recent lessons, level, and goals.

## Steps

1. **Gather context:**
   - Read `CLAUDE.md` for the user's target language, level, goals, and grammar priorities
   - Read the last 2-3 weeks of daily notes from `notes/Daily Notes/`
   - Read existing files in `notes/Weekly Tips/` to avoid repeating the same focus areas
   - If a timeline/exam goal exists, calculate remaining time

2. **Determine the week's focus** based on:
   - Grammar priorities listed in CLAUDE.md (work through them progressively)
   - Errors or patterns observed in recent daily notes
   - Topics not covered in the previous 4 weeks of tips
   - The user's current level and target level

3. **Create a new file** in `notes/Weekly Tips/` named `YYYY-MM-DD.md` (using today's date)

4. **Document structure:**

   ```markdown
   # Tips of the Week — [date range]

   Week [N] · [timeline context if applicable]

   ---

   ## Main Focus: [Grammar or skill focus]

   [2-3 paragraphs explaining the concept with clear examples in the target language]

   ### Suggested Exercises
   [3-4 concrete practice activities]

   ## Review: [Previous area that needs reinforcement]
   [Brief review with examples, based on recent lesson patterns]

   ## Vocabulary of the Week
   | Word/Phrase | Translation | Example |
   | ----------- | ----------- | ------- |
   [5-8 relevant words themed around the focus area]

   ## For Your Lessons This Week
   [2-3 specific suggestions for tutoring sessions or self-study]

   ## Tip of the Day
   [One motivational or practical learning tip]
   ```

5. **Write the document** in the user's target language at their current level, with English explanations where helpful for grammar concepts.

## Important

- Don't repeat the same main focus within 4 weeks — check previous tips files
- Reference specific errors or patterns from recent daily notes when relevant
- Keep suggestions actionable and specific, not generic
- Scale difficulty to the user's current level
- If no daily notes exist yet, base tips on the grammar priorities in CLAUDE.md and the user's stated level
- If CLAUDE.md hasn't been configured yet (no target language), ask the user to run `/setup` first
