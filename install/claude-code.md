# Install — Claude Code

> **Recommended**: Run `./install.sh` from the repo root for automated installation with dual-mode support (@ reference + inline fallback).
> The manual steps below are for reference or troubleshooting.

## Quick install

```bash
# 1. Inject core rules into CLAUDE.md (direct content injection — works on all versions)
cat cognitive-protocol.md >> ~/.claude/CLAUDE.md
```

## What gets loaded where

| File | Destination | Purpose |
|---|---|---|
| `cognitive-protocol.md` | `~/.claude/CLAUDE.md` (appended) | Always-on core rules (~30 lines) |
| `SKILL.md` | `~/.claude/skills/double-loop-learning/SKILL.md` | Full reference (loaded on demand) |
| `anti-patterns.md` | `~/.claude/skills/double-loop-learning/anti-patterns.md` | Detailed anti-pattern guide |
| `examples.md` | `~/.claude/skills/double-loop-learning/examples.md` | Before/after reference |

## Full install (with skill files)

```bash
# 1. Core rules (inject directly into CLAUDE.md)
cat cognitive-protocol.md >> ~/.claude/CLAUDE.md

# 2. Skill files
mkdir -p ~/.claude/skills/double-loop-learning
cp SKILL.md ~/.claude/skills/double-loop-learning/
cp anti-patterns.md ~/.claude/skills/double-loop-learning/
cp examples.md ~/.claude/skills/double-loop-learning/

# 3. (Core rules already injected in step 1)
```

## Verify

Ask Claude Code: "What are the double-loop learning cognitive rules you're following?" It should list the six sections from `cognitive-protocol.md`: fix error vs fix assumption, reflect as daily practice, bracket presuppositions, cross-perspective reflection, close the loop, output self-check.

## Stacking with other cognitive bases

If First Principles is already injected into `CLAUDE.md`, no changes needed. Both protocols load independently. First Principles audits assumptions before reasoning; Double-Loop Learning audits assumptions after results arrive. No conflicts.

## Uninstall

```bash
# Remove the Double-Loop Learning section from ~/.claude/CLAUDE.md (search for "# Double-Loop Learning — Cognitive Protocol" header)
rm -rf ~/.claude/skills/double-loop-learning
```
