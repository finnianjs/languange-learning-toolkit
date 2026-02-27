# /setup — Configure Language Learning Toolkit

This skill personalizes the toolkit for the user's target language, level, and goals.

## Steps

1. **Ask the user the following questions** (one message, wait for all answers):

   a. **What language are you learning?**
      - e.g., Spanish, French, Japanese, Korean, Mandarin, etc.

   b. **What level do you want to reach?**
      - Use CEFR scale: A1 (Beginner), A2 (Elementary), B1 (Intermediate), B2 (Upper Intermediate), C1 (Advanced)
      - If they're unsure, briefly explain what each level means

   c. **What is your previous exposure to this language?**
      - e.g., "Complete beginner", "Took 2 years in high school", "Lived in France for a year", "Self-studied for 6 months"
      - Ask about approximate hours if they can estimate (listening, reading, speaking, writing)

   d. **Do you have any specific goals or a timeline?**
      - e.g., "Pass JLPT N3 by December", "Be conversational for a trip in 6 months", "Read novels in French"
      - Timeline is optional but helpful for structuring recommendations

   e. **Any other details about your study setup?**
      - e.g., tutoring platform, apps used, daily study time, topics of interest

2. **Update CLAUDE.md** with the user's answers:

   - Fill in the **Target Language** section with language, current level (estimate from their exposure), target level, timeline, and previous exposure
   - Fill in the **Learning Preferences** section with their goals, study routine, resources, and comfort topics
   - Fill in the **Grammar Priorities** section with a level-appropriate grammar progression for their target language and level
   - Update the **Response Language** section to specify the target language

3. **Create additional vocab files if needed:**

   - If the language has natural category splits (e.g., formal vs casual registers, regional variants, kanji readings), create additional files in `notes/Vocab/` and update the CLAUDE.md file structure section

4. **Update the lesson template** if needed:

   - Adjust the daily note template columns based on the language (e.g., add "Reading" column for languages with non-Latin scripts, add "Tone" for tonal languages)

5. **Display a summary** of the configuration to the user, confirming:
   - Target language and level
   - Grammar priorities for their level
   - Recommended weekly focus areas
   - How to get started (create your first daily note, try /weekly-tips)

## Important

- Be encouraging and welcoming — this is the user's first interaction with the toolkit
- If the user gives brief answers, that's fine — don't over-ask. Fill in reasonable defaults and tell them they can update CLAUDE.md anytime
- The grammar priorities should be specific to the language, not generic. For example, Japanese priorities look very different from Spanish priorities
- Estimate their current CEFR level from their exposure description and note it
