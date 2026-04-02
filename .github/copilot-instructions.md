# KAIWorlds - Copilot Instructions

## Branch discipline

Never work on `main`. Always create a feature branch before making any changes.

Branch naming:
- `feat/<name>` - new world or new feature
- `fix/<name>` - corrections to existing content
- `chore/<name>` - infrastructure, scaffolding, housekeeping

## Release procedure

1. Work on a feature branch
2. Open a PR - the PR template checklist must pass before merge
3. Merge to `main` via PR only
4. Create a GitHub release with a version tag to trigger the release workflow
5. The workflow zips every world folder that contains `stack.md` and uploads the zip as a release asset
6. Download links in README files point to `github.com/ChBrain/KAIWorlds/releases/latest/download/<folder>.zip`

## Style

- Do not use em dashes. Use a hyphen (-) instead.

## PR checklist (from template)

- World files complete: `instructions.md`, `stack.md`, personas, places, pieces, processes, `README.md`, `REFERENCES.md`, `LICENSE`
- `LICENSE` is CC BY-NC 4.0 with KAI Worlds branding
- Download link points to `github.com/ChBrain/KAIWorlds/releases/latest/download/`
- World added to root `README.md`
- World added to `kaihacks.ai/worlds.html` in the website repo

## File standards

- Footer in content files (persona, piece, place, process, position): `v0.1.0 - KAI Worlds`
- Footer in scaffold files (stack, instructions, REFERENCES): `*v0.1.0 - KAI Worlds*` / date line
- Footer in README: `*Kai Schlueter - KAI HACKS AI - 2026*` / `*CC BY-NC 4.0*` / `*KAI Worlds - github.com/ChBrain/KAIWorlds*`
- A world folder is only included in zips if it contains `stack.md`
