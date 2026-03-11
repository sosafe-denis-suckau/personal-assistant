# Git Conventions

## Commit Message Format

```
<scope> <short summary>
```

## Scope

- Normally a Jira ticket number
- In this project, use `NO-TICKET` since we don't work with tickets

## Summary Rules

- Short summary of WHAT was done
- Use the imperative mood ("Add", not "Added" or "Adds")
- Use present tense
- Capitalise the first letter
- No period (.) at the end

## Examples

- `NO-TICKET Add CLAUDE.md with assistant persona configuration`
- `NO-TICKET Create daily standup slash command`
- `NO-TICKET Fix habit tracker date formatting`

## Atomic Commits

- Always make very small, atomic commits — one logical change per commit
- Never bundle unrelated changes into a single commit
- When multiple files were changed, consider whether they should be separate commits

## Git Safety Protocol

- NEVER update git config
- NEVER run destructive commands (--force, hard reset) without explicit request
- NEVER skip hooks (--no-verify) unless user asks
- NEVER force push to main/master
- NEVER add "Co-Authored-By" trailers to commit messages
- If commit fails due to hooks, fix and create a NEW commit (don't amend)
