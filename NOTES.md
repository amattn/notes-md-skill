# NOTES.md

## Project Context

**notes-md-skill** — a standalone Claude Code skill plugin that provides the `/notes` command. Maintains a living `NOTES.md` file as institutional memory for multi-session AI-assisted development. Captures design decisions, rationale, rejected alternatives, user insights, invariants, and conventions — the "why" behind project decisions.

Originally developed and battle-tested during plet-skills development (8+ parts, 50+ sessions). Extracted as a standalone skill so any Claude Code project can use it independently of plet.

**Repo:** `github.com/amattn/notes-md-skill`
**Source lineage:** `plet-skills/skills/notes/SKILL.md` (identical copy)

---

## Key Design Decisions

### SKILL.md description length (2026-03-12, decided)

Trimmed the implicit trigger scenarios in the frontmatter description. Kept explicit trigger phrases ("notes", "start notes", "capture this decision", etc.) and kept implicit triggers but condensed from ~50 words with parenthetical examples to one sentence summarizing the three scenarios. Removed trailing summary sentence that repeated the opening line.

- **Kept:** explicit trigger phrases — necessary for skill routing
- **Kept (condensed):** implicit triggers (decision recording, past decision queries, reorg) — valuable because they describe passive triggering not obvious from the skill name
- **Removed:** parenthetical examples within implicit triggers ("let's go with option A", "why did we") — Claude can infer these from the scenario description

### Install options in README (2026-03-12, decided)

Three install methods modeled after [ralph's README](https://github.com/snarktank/ralph): marketplace, global (`~/.claude/skills/`), and project-level (`.claude/skills/`). Covers all deployment scenarios.

### Semver policy added to CLAUDE.md (2026-03-13, decided)

Added versioning guidance to CLAUDE.md covering both version tracks:

- **Plugin version** (`plugin.json:version` + `marketplace.json:plugins[].version` for the corresponding entry): tracks skill behavior changes. PATCH for refinements, MINOR for features, MAJOR for breaking changes.
- **Marketplace version** (`marketplace.json:metadata.version`): tracks the listing/packaging itself. MINOR for adding companion plugins, MAJOR for removing plugins.

The two are independent because companion skills may be added later, and the marketplace version should reflect the collection changing even if individual plugin versions don't.


---

## Invariants & Critical Requirements

*(No invariants recorded yet.)*

---

## Important Concepts & Insights

### From the user

*(No user insights recorded yet.)*

### Emergent

*(No emergent insights yet.)*

---

## Taxonomy / Conventions

*(No conventions recorded yet.)*

---

## Open Questions


---

## Things to Monitor

*(No items to monitor yet.)*

---

## Artifact Approval Status

*(No artifacts under review yet.)*
