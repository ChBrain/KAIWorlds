# KAIWorlds — Copilot Instructions

## Repository purpose

KAIWorlds is a standalone collection of AI roleplay worlds. Each world is self-contained: its own folder, its own LICENSE, its own README. The repo stands alone. It does not reference or depend on any other repository.

---

## Release strategy

### Branching

- All work happens on branches. No direct commits to main.
- One world per branch: `world/[worldname]`
- Fixes to an existing world: `fix/[worldname]-[short-description]`
- Infrastructure (workflow, root LICENSE): `feat/[short-description]`
- Root-level docs, architecture, templates: `docs/[short-description]`

### Versioning

Two independent versioning concepts apply simultaneously.

**Repo-level** — tracks the collection as a whole. Used for GitHub releases and tags.
- `v0.x.0` — a world added or replaced
- `v0.x.1` — a fix within an existing world (text, link, license)
- `v1.0.0` — when the intended set of worlds is live and clean

**World-level** — tracks each world independently. Appears in the world's README footer only.
- `v0.1.0` — world first published
- `v0.1.x` — fixes within that world
- `v0.x.0` — significant revision to the world's content or structure
- World versions are not tied to the repo version and do not need to match it.

### Release cadence

- Cut one release per world merged. Do not batch worlds into a single release.
- Release after merge, not before. Merge is a human step — Copilot opens the PR, the author merges it, then the release is cut.

### Release notes

- Name the world.
- One sentence describing what it is.
- List files added or changed.

### Zips

- The `release-zips` workflow fires automatically on release publish.
- Any folder containing `stack.md` gets zipped and attached.
- Re-run via `workflow_dispatch` if content is updated after a release (`--clobber` overwrites).

---

## What belongs inside a world folder

**Include:**
- `stack.md` — the world's instruction file for the AI
- `README.md` — user-facing description, download link, setup steps
- `LICENSE` — CC BY-NC 4.0, specific to this world
- `REFERENCES.md` — if the world draws on source material (primary sources only)
- Persona files (`persona_*.md`)
- Place files (`place_*.md`)
- Piece files (`piece_*.md`)

**Do not include:**
- Workflow files or any CI/CD configuration — those live at repo root only
- Files that reference or depend on content from another world
- Architecture documentation, methodology notes, or templates — those live at repo root, not inside world folders
- Build notes, production notes, or anything prefixed with `_` or `draft`

Each world folder must be self-contained. A user downloading the zip should have everything they need and nothing they don't.

### Upload instructions in every world README

The setup section must list files explicitly. Never write "upload all files in this folder."

Required wording:
```
Upload to your AI project: all `.md` files in this folder.
```

This prevents README prose, license text, and source citations from entering the AI's context and bleeding into the world's behaviour.

---

## World checklist — required before any PR is merged

- [ ] Folder contains `stack.md`
- [ ] Folder contains `LICENSE` — CC BY-NC 4.0
- [ ] README footer reads `CC BY-NC 4.0`
- [ ] Download link in README points to `https://github.com/ChBrain/KAIWorlds/releases/latest/download/[worldname].zip`
- [ ] README setup section uses the required upload wording
- [ ] No links point outside this repository except to Claude.ai and cited source material in REFERENCES.md
- [ ] REFERENCES.md (if present) cites only primary sources — no links to other code repositories
- [ ] World version in README footer is independent of repo version

---

## License

Two separate licenses apply.

**Root LICENSE** — CC BY-NC-ND 4.0.  
Covers the KAI Worlds architecture specification. The collection structure, component definitions, and structural requirements may be shared and cited but not adapted or released in derivative form.

**World LICENSE** (inside each world folder) — CC BY-NC 4.0.  
Each world carries its own license. Worlds may be shared and adapted for non-commercial purposes with attribution.

Do not change either license without explicit instruction. Do not apply the root license to world folders or vice versa.

---

## Root-level content

The repo root may contain:
- Architecture documentation and specification files
- Templates for world components
- Workflow files (`.github/`)
- Root `README` and root `LICENSE` (CC BY-NC-ND 4.0)

All root-level content falls under the root LICENSE (CC BY-NC-ND 4.0) — stricter than world licenses. Do not mix root content into world folders.

Worlds are the product. Root content is infrastructure and specification.
