# Personal Assistant

A Claude Code project configured as a personal assistant for daily recurring tasks.

## How It Works

This is not a traditional application — it's a [Claude Code](https://claude.ai/claude-code) workspace. Open this folder in Claude Code and it will act as a personalized assistant, with persistent memory across sessions.

## Structure

```
├── CLAUDE.md                        # Assistant persona and project rules
├── .claude/
│   ├── commands/                    # Slash commands for common workflows
│   └── skills/                      # Always-active rules and conventions
└── data/                            # Persistent memory (Markdown files)
```

## Getting Started

1. Clone this repo
2. Open the folder in Claude Code
3. Start chatting — the assistant knows who you are and follows your conventions

## Custom Commands

Run these in Claude Code with `/<command>`:

| Command | Description |
|---------|-------------|
| `/hello` | Greet and summarize current memory state |

## Skills

Always-active rules that Claude follows automatically:

| Skill | Description |
|-------|-------------|
| [Git Conventions](.claude/skills/git-conventions.md) | Commit message format, atomic commits, safety protocol |
