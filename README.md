# Language Learning Toolkit

A structured, markdown-based system for tracking your language learning journey — powered by [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills for vocabulary management, flashcard creation, and weekly study recommendations.

Works with any language. Works with any markdown editor (Obsidian, VS Code, Notion exports, or plain text files).

## What's Included

- **Daily note templates** for recording vocabulary, grammar, and anything else from your study sessions
- **Central vocabulary tracking** with automatic syncing from daily notes
- **Anki flashcard generation** via AnkiConnect integration
- **Weekly tips** with personalized study recommendations based on your level and goals
- **Weekly and monthly summaries** of your learning progress
- **A personalized CLAUDE.md** that adapts all skills to your target language, level, and goals

## Quick Start

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/languange-learning-toolkit.git
cd languange-learning-toolkit
```

### 2. Run setup

Open the project in Claude Code and run:

```
/setup
```

This will ask you:
- What language you're learning
- What level you want to reach (A1–C2)
- Your previous exposure to the language
- Any specific goals or timeline
- Details about your study setup

Your answers are saved to `CLAUDE.md`, which personalizes all other skills to your language and goals.

### 3. Start taking notes

Create your first daily note in `notes/Daily Notes/` using the format `YYYYMMDD.md`:

```markdown
Source: Italki lesson with Maria
Topics: Travel, Food

# Vocab:

| Word/Phrase | Translation | Note | Category |
| ----------- | ----------- | ---- | -------- |
| aubergine   |             | British English for eggplant | food |
| gare        | train station | la gare du Nord | |

# Grammar:
- Reviewed passé composé with être verbs

# Notes:
- Discussed trip to Lyon, practiced ordering at restaurants
- Watched a French cooking video — picked up kitchen vocabulary
```

Or copy the template from `notes/Templates/Daily Note Template.md`.

### 4. Use the skills

| Skill | What it does |
| ----- | ------------ |
| `/update-vocab` | Scans daily notes and adds new words to your central vocab list |
| `/create-flashcards` | Creates Anki flashcards from vocab entries (requires Anki + AnkiConnect) |
| `/weekly-tips` | Generates personalized study recommendations for the week |
| `/summarize-week` | Summarizes your past 7 days of learning |
| `/summarize-month` | Summarizes your past month of learning |
| `/setup` | (Re)configure your language, level, and goals |

## Directory Structure

```
├── CLAUDE.md                      # Your personalized learning config
├── .claude/skills/                # Claude Code skill definitions
│   ├── setup/
│   ├── update-vocab/
│   ├── create-flashcards/
│   ├── weekly-tips/
│   ├── summarize-week/
│   └── summarize-month/
└── notes/
    ├── Daily Notes/               # Your daily learning notes (YYYYMMDD.md)
    ├── Vocab/
    │   └── General.md             # Central vocabulary database
    ├── Weekly Summaries/
    ├── Weekly Tips/
    ├── Monthly Summaries/
    └── Templates/
        └── Daily Note Template.md
```

## Setting Up Anki Integration

The `/create-flashcards` skill pushes vocabulary directly to [Anki](https://apps.ankiweb.net/) using the AnkiConnect addon. Here's how to set it up:

### Install Anki

1. Download and install Anki from [apps.ankiweb.net](https://apps.ankiweb.net/)
2. Create a free AnkiWeb account at [ankiweb.net](https://ankiweb.net/account/signup) if you want to sync across devices

### Install AnkiConnect

1. Open Anki
2. Go to **Tools → Add-ons → Get Add-ons...**
3. Enter the addon code: `2055492159`
4. Click **OK** and restart Anki

### How it works

1. You take notes throughout the day, adding vocab to the table in your daily note
2. Run `/update-vocab` — new words are synced to `notes/Vocab/General.md` with translations and example sentences
3. Review the vocab list and decide which words you want as flashcards (you can leave `Flashcard?` empty for the ones you want, or mark "no" to skip)
4. Run `/create-flashcards` with Anki open — cards are created automatically and the vocab list is updated with "yes"

**Flashcard format:**
- **Front:** An example sentence with the target word in bold
- **Back:** The translation

### Syncing Anki across devices

- **Desktop ↔ AnkiWeb:** In Anki, click the sync button (or press Y) to sync with AnkiWeb
- **Mobile:** Install [AnkiMobile](https://apps.apple.com/app/ankimobile-flashcards/id373493387) (iOS, paid) or [AnkiDroid](https://play.google.com/store/apps/details?id=com.ichi2.anki) (Android, free) and sign in with your AnkiWeb account
- Your decks, cards, and review progress sync across all devices

## Using with Obsidian

[Obsidian](https://obsidian.md/) works particularly well with this toolkit because of its backlink and graph features. Here's how to set it up:

### Open the notes folder as a vault

1. Open Obsidian
2. Click **Open folder as vault**
3. Select the `notes/` directory inside this repo

### Set up templates

1. Go to **Settings → Core plugins** and enable **Templates**
2. Go to **Settings → Templates** and set the template folder to `Templates`
3. Now when creating a new note, use **Insert template** (Ctrl/Cmd+T) to insert the daily note template

### Use backlinks for organization

The daily note template uses double-bracket links that Obsidian turns into navigable backlinks:

```markdown
Source: [[Maria]] [[Italki]]
Topics: [[travel]] [[food]] [[grammar]]
```

This lets you:
- Click on a source to see all notes from that source
- Click on a topic to see all notes covering that topic
- Use the **Graph View** to visualize connections between notes, topics, and sources

I recommended making a Tags folder and moving any notes like this into that folder to stay organized.

## Tips

- **Be consistent with daily notes.** Even brief notes help the skills generate better summaries and recommendations.
- **Don't worry about filling every column.** Leave translations blank and `/update-vocab` will fill them in. Leave grammar notes empty if nothing notable came up.
- **Review vocab before creating flashcards.** The system lets you decide which words are worth memorizing — not every word needs a flashcard.
- **Run `/weekly-tips` at the start of each week.** It'll give you focus areas based on your recent progress and grammar priorities.
- **Update CLAUDE.md as you progress.** As your level changes or goals shift, edit the file directly or run `/setup` again.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) (for running skills)
- [Anki](https://apps.ankiweb.net/) + [AnkiConnect](https://ankiweb.net/shared/info/2055492159) (optional, for flashcard creation)
- A markdown editor of your choice

## License

MIT
