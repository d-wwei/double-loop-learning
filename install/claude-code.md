# Install — Claude Code

## Quick install

```bash
# 1. Copy cognitive protocol to Claude's config
cp cognitive-protocol.md ~/.claude/double-loop-learning.md

# 2. Add reference in CLAUDE.md
echo '@~/.claude/double-loop-learning.md' >> ~/.claude/CLAUDE.md
```

## What gets loaded where

| File | Destination | Purpose |
|---|---|---|
| `cognitive-protocol.md` | `~/.claude/double-loop-learning.md` | Always-on core rules (~30 lines) |
| `SKILL.md` | `~/.claude/skills/double-loop-learning/SKILL.md` | Full reference (loaded on demand) |
| `anti-patterns.md` | `~/.claude/skills/double-loop-learning/anti-patterns.md` | Detailed anti-pattern guide |
| `examples.md` | `~/.claude/skills/double-loop-learning/examples.md` | Before/after reference |

## Full install (with skill files)

```bash
# 1. Core rules
cp cognitive-protocol.md ~/.claude/double-loop-learning.md

# 2. Skill files
mkdir -p ~/.claude/skills/double-loop-learning
cp SKILL.md ~/.claude/skills/double-loop-learning/
cp anti-patterns.md ~/.claude/skills/double-loop-learning/
cp examples.md ~/.claude/skills/double-loop-learning/

# 3. Register in CLAUDE.md
echo '@~/.claude/double-loop-learning.md' >> ~/.claude/CLAUDE.md
```

## Verify

Ask Claude Code: "What are the double-loop learning cognitive rules you're following?" It should list the six sections from `cognitive-protocol.md`: fix error vs fix assumption, reflect as daily practice, bracket presuppositions, cross-perspective reflection, close the loop, output self-check.

## Stacking with other cognitive bases

If First Principles (`~/.claude/first-principles.md`) is already referenced in `CLAUDE.md`, no changes needed. Both protocols load independently. First Principles audits assumptions before reasoning; Double-Loop Learning audits assumptions after results arrive. No conflicts.

## Uninstall

```bash
rm ~/.claude/double-loop-learning.md
rm -rf ~/.claude/skills/double-loop-learning
# Remove the @~/.claude/double-loop-learning.md line from ~/.claude/CLAUDE.md
```
