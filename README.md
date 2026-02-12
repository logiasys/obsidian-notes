# ClawdNotes Template

A shareable Obsidian vault template designed for AI-assisted note-taking with Claude Code, OpenCode, Cursor, OpenClaw, and other AI coding assistants.

## What This Is

An opinionated, note-taking system that:
- Uses PARA organization (Projects, Areas, Resources, Archive)
- Integrates seamlessly with AI assistants
- Includes automation for daily briefings, inbox processing, and reviews
- Provides clear conventions that both humans and AI can follow

**Fork this, make it yours.**

## Quick Start

```bash
# Clone the template
git clone https://github.com/YOUR_USERNAME/clawdnotes-template ~/Notes

# Or use GitHub's template feature
# Click "Use this template" on GitHub

# Open in Obsidian
# File → Open Vault → Select the cloned folder
```

## Structure

```
.
├── 0-Inbox/           # Quick capture, unprocessed items
├── 1-Daily/           # Daily notes (YYYY-MM-DD.md)
├── 2-Project-Ideas/   # Pipeline of potential projects (pre-project)
├── 2-Projects/        # Active projects with deliverables
│   └── <project>/
│       ├── README.md, tasks.md, decisions.md, ideas.md
│       └── features/<feature>/PRD.md, DEV_PLAN.md
├── 3-Areas/           # Ongoing responsibilities (no end date)
├── 4-Resources/       # Reference material, topics of interest
├── 5-Archive/         # Completed/inactive items
├── _templates/        # Note templates (daily, project, feature-prd, dev-plan)
├── CLAUDE.md          # AI assistant instructions (overview)
├── CONTEXT.md         # Vault state index (auto-updated)
├── MEMORY.md          # Long-term memory (decisions, learnings)
└── docs/              # Guides and documentation
    ├── CONVENTIONS.md
    ├── AI-WORKSPACE-GUIDE.md
    ├── FEATURE-WORKFLOW.md
    ├── AUTOMATION.md
    └── WEEKLY-REVIEW.md
```

## Features

### For Humans
- 📝 Daily note workflow with morning/capture/review sections
- 📁 PARA organization keeps things findable
- 🔗 Wikilinks connect everything
- 📋 Project structure with README/tasks/decisions/ideas
- 🧪 Project idea pipeline (`2-Project-Ideas/`) to mature opportunities before execution
- 🚀 Feature workflow: idea → PRD → DEV_PLAN → implementation
- 🗄️ Clear archival process

### For AI Assistants
- 🤖 `CLAUDE.md` teaches AI your conventions
- 🧠 Autonomous behaviors (smart capture, proactive maintenance)
- 📅 Scheduled automation (morning briefings, inbox processing, reviews)
- 🔄 Session handoff for context continuity

## Getting Started

1. **Fork & Clone** this repository
2. **Open in Obsidian** (File → Open Vault)
3. **Create your first daily note**: `1-Daily/YYYY-MM-DD.md` using the template
4. **Start capturing**: Add thoughts to `0-Inbox/` or directly to your daily note
5. **Use Inbox template**: Set `action_type` (`normal`, `task`, `project-seed`, etc.) to route processing behavior
6. **Set up automation** (optional): See [AUTOMATION.md](docs/AUTOMATION.md)

## New: Action-Based Inbox Processing

- Use `[[_templates/inbox-item]]` for all new inbox captures.
- Define `action_type` in frontmatter to indicate processing path.
- Supported actions are documented in [`4-Resources/system/action-glossary.md`](4-Resources/system/action-glossary.md).
- If no action is set, the inbox processor defaults to `normal` flow.

## New: Project Ideas (outside active projects)

- Capture project opportunities in `2-Project-Ideas/` with `[[_templates/project-idea]]`.
- Promote an idea to `2-Projects/` only after basic validation (problem, value, owner, next action).
- This keeps execution projects clean while preserving strategic exploration.

## Documentation

| Guide | What It Covers |
|-------|----------------|
| [CLAUDE.md](CLAUDE.md) | Vault overview and AI assistant instructions |
| [CONVENTIONS.md](docs/CONVENTIONS.md) | Detailed folder rules, commit format, archival process |
| [CONTEXT.md](CONTEXT.md) | Current vault state (auto-updated by /sync) |
| [AI-WORKSPACE-GUIDE.md](docs/AI-WORKSPACE-GUIDE.md) | Complete setup for AI-assisted development |
| [FEATURE-WORKFLOW.md](docs/FEATURE-WORKFLOW.md) | Feature development: idea → PRD → DEV_PLAN → implementation |
| [AUTOMATION.md](docs/AUTOMATION.md) | Setting up cron jobs and scheduled tasks |
| [WEEKLY-REVIEW.md](docs/WEEKLY-REVIEW.md) | Weekly review process and maintenance |
| [QUALITY-IMPROVEMENTS.md](docs/QUALITY-IMPROVEMENTS.md) | Recommended quality and admin upgrades for scaling the vault |

## Customization

### Make It Yours

1. **Edit `CLAUDE.md`** — Adjust conventions to match your style
2. **Modify templates** — Customize `_templates/` for your needs
3. **Add your areas** — Create folders in `3-Areas/` for your responsibilities
4. **Configure automation** — Adjust schedules in [AUTOMATION.md](docs/AUTOMATION.md)

### Opinionated Defaults

This template has opinions. You might disagree. Here's what to change:

| If You Want | Change This |
|-------------|-------------|
| Different folder names | Rename folders + update `CLAUDE.md` references |
| Different daily note format | Edit `_templates/daily.md` |
| No emoji in status | Search/replace in `CLAUDE.md` |
| Flat project structure | Simplify project template, update `CLAUDE.md` |

## Tools Compatibility

Works with:
- **Obsidian** — Primary intended use
- **Claude Code** — Reads CLAUDE.md, supports slash commands
- **OpenCode** — Compatible (uses AGENTS.md alias)
- **Cursor** — Compatible (copy CLAUDE.md to .cursorrules)
- **OpenClaw** — Full automation support with cron jobs
- **Any AI assistant** — CLAUDE.md provides context

## Contributing

Found an improvement? Have a better workflow? PRs welcome!

1. Fork the repo
2. Make your changes
3. Submit a PR with a clear description of the improvement

## License

MIT — Use it, modify it, share it.

---

*Built by humans and AI, for humans and AI.*
