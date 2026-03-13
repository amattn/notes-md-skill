# notes-md-skill

A Claude Code skill plugin that maintains a living `NOTES.md` file as institutional memory for multi-session AI-assisted development.

## What it does

The `/notes` command captures what other project artifacts don't: the *why* behind decisions — rationale, rejected alternatives, user insights, invariants, and conventions. Every session starts with an accurate picture of what's been decided and why.

**Bootstrap** — On first use, creates a `NOTES.md` with scaffolded sections, wires it into `CLAUDE.md`, and adds the Notes Discipline so it's enforced every session.

**Notes Discipline** — Decisions are captured immediately (before moving to the next topic), rejected alternatives are documented, and user preferences are quoted in their own words.

**Reorganization** — Detects when the file's structure no longer fits the project and proposes restructuring.

**Multi-file support** — For larger projects, supports scoped `NOTES.md` files in subfolders with routing rules.

## Install

### Option 1: Claude Code Marketplace

```bash
/plugin marketplace add amattn/notes-md-skill
/plugin install notes-md-skill@notes-md-marketplace
```

### Option 2: Global Installation

Copy the skill into your Claude Code skills directory so it's available across all projects:

```bash
cp -r skills/notes ~/.claude/skills/
```

### Option 3: Project-Level Installation

Copy the skill into your project for per-project use:

```bash
mkdir -p .claude/skills
cp -r /path/to/notes-md-skill/skills/notes .claude/skills/
```

## Usage

```
/notes              # bootstrap or operate on NOTES.md
```

The skill also triggers automatically when you make decisions that should be recorded ("let's go with option A", "we decided", "let's not do X").

## Suggested starting sections

1. **Key Design Decisions** — what, why, rejected alternatives, status
2. **Invariants & Critical Requirements** — load-bearing rules
3. **Important Concepts & Insights** — user quotes and emergent principles
4. **Taxonomy / Conventions** — canonical vocabulary and naming
5. **Open Questions** — unresolved topics
6. **Things to Monitor** — drift risks, watchlist items
7. **Project Context** — brief orientation for fresh agents
8. **Artifact Approval Status** — review tracking

## Origin

Developed and battle-tested during [plet-skills](https://github.com/amattn/plet-skills) development (8+ parts, 50+ sessions). Extracted as a standalone skill for use in any Claude Code project.
