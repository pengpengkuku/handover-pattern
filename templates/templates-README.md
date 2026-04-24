# Templates: CLAUDE.md and HANDOVER.md

Drop-in templates for the [HANDOVER pattern](../handover-pattern.md) — a project management approach to AI-assisted development.

## What's here

- **`CLAUDE.md.template`** — the project's constitution. Stable facts, invariants, conventions. Read at the start of every AI session.
- **`HANDOVER.md.template`** — the session-to-session relay note. Written at the end of every session, read first thing in the next.

## How to use them

```bash
# Copy into your project root, removing the .template suffix
cp CLAUDE.md.template /path/to/your/project/CLAUDE.md
cp HANDOVER.md.template /path/to/your/project/HANDOVER.md
```

Then:

1. Open both files
2. Delete the `<!-- comment blocks -->` (they're instructions to you, not the AI)
3. Replace `[bracketed placeholders]` with your project's specifics
4. Fill in your first session's content in HANDOVER.md (mark it as session 1)
5. Commit both files

That's it. Next time you start an AI session, the AI reads CLAUDE.md first, then HANDOVER.md, and knows where to start.

## Three rules to internalize

These are non-negotiable. The pattern doesn't work without them:

1. **HANDOVER.md is updated last in every session** — after all real work is committed. Its job is to reflect reality at *that* commit.
2. **HANDOVER.md is read first in every session** — before exploring code, before "let me see what's here." This removes cold-start anxiety.
3. **The trap list (`⚠️` section in HANDOVER) is append-only** — never delete entries, only add. After 30 sessions it becomes the most valuable artifact in your project.

## Adapting for your stack

The templates are tool-agnostic on purpose. Replace:

- Test/lint/typecheck commands with your equivalents
- File paths with your project layout
- "Skill chain" workflow with your actual process
- Tech stack table with what's actually locked in

For monorepos / multi-tool projects, you can run two-layer HANDOVERs (platform-level + tool-level) — see the article for details.

## Suggestions welcome

If you adapt this pattern and your version evolves something interesting, open an issue or PR. The template should improve over time as more teams use it.
