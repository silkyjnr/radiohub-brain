# radiohub-brain

The shared "second brain" for RadioHub Media: who we are, our brands, our repeatable jobs (as Claude skills) and what we've learned.

## Get started

1. Install [Claude Code](https://claude.com/claude-code) (desktop app or CLI) and git.
2. Clone this repo and open the folder in Claude Code:
   ```bash
   git clone https://github.com/<owner>/radiohub-brain.git
   ```
3. Claude reads `CLAUDE.md` automatically and loads skills from `.claude/skills/` when the job matches.
4. Connect the tools you need in Claude: Google Drive, Meta Ads, and Higgsfield (optional).

## What's here

| Path | What |
|---|---|
| `CLAUDE.md` | Who we are, current priorities, where things live, house rules. **Start here.** |
| `.claude/skills/radiohub-brand/` | RadioHub Media brand rules |
| `.claude/skills/making-memories-brand/` | Making Memories brand rules |
| `.claude/skills/making-memories-meta-ads/` | How we plan, build and review Making Memories ads, plus past results |
| `docs/` | Longer notes, plans and reports |

## Keep it alive

- Learned something? Add it to `CLAUDE.md` or the right skill.
- Doing a job for the second time? Make it a skill (ask Claude: "make a skill for this").
- Commit with a plain-English message and push. Pull before you start work (`git pull`).
- Never commit passwords, API keys, payment details or client personal info.
