# Continuous Feedback

Generate structured monthly feedback for 1:1 sessions between Denis and a direct report. Feedback flows in both directions (employee and manager) and covers both positive and constructive sentiments.

## Input

- The direct report's name
- Raw notes, observations, or topics from the past weeks — for the employee, for Denis as manager, or both
- Context on which direction (employee feedback, manager feedback, or both)

## Output Format

Produce four sections, grouped by direction and sentiment. Each section is a flat bullet list — one bullet per feedback point, no nesting, no sub-bullets.

### Feedback for [Employee Name]

**Positive**

- [impact of the behavior] — [continue doing / amplify specific behavior]
- ...

**Constructive**

- [impact of the behavior] — [change / adjust specific behavior]
- ...

### Feedback for Denis (Manager)

**Positive**

- [impact of the behavior] — [continue doing / amplify specific behavior]
- ...

**Constructive**

- [impact of the behavior] — [change / adjust specific behavior]
- ...

## Bullet Format

Each bullet follows a strict structure:

1. **Impact first** — describe the observable effect on team, project, delivery, morale, or individuals
2. **Leading indicator behavior** — after a dash, point to the specific behavior to continue, amplify, change, or stop

Example positive: "Reduced cycle time on the migration project by unblocking reviews same-day — keep prioritizing fast review turnarounds even during busy sprints"

Example constructive: "Team was unsure about priorities after the roadmap shift, which slowed sprint planning — communicate reprioritization decisions to the team within 24 hours of the change"

## Conventions

- Do not invent observations — only refine what the user provided
- Preserve Denis's judgment and intent — don't soften constructive feedback or over-inflate positive feedback
- Every bullet must be situational and specific to recent weeks — no generic or evergreen statements
- One bullet per distinct feedback point — do not combine multiple observations into one bullet
- Keep bullets concise — one to two sentences max
- If input is ambiguous about direction (employee vs. manager) or sentiment (positive vs. constructive), ask
- Omit a section entirely if there is no input for it rather than leaving it empty
- Output in chat only — never save feedback to files
