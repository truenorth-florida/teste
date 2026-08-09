## Projects

This is a construction manager and the projects folder contains all the current projects that we are managing.


## SKILLS
All skills files are stored in the `.sklls/` folder (ex.: `.sklls/VALIDACAO.md`).


## Execução do fluxo:

Rode um subagent para cada projeto e execute a skill VALIDACAO.md.

no fim, gere um report de tudo que foi feito.



Apesar de estar no windows, faça o git commmit sempre!!!


## Child DOX Index

| Scope (subtree root) | Doc path |
|---|---|
| `projects/apt-root/` | `.dox/projects/apt-root/AGENTS.md` |
| `projects/casa-maria/` | `.dox/projects/casa-maria/AGENTS.md` |
| `projects/casa-praia/` | `.dox/projects/casa-praia/AGENTS.md` |


# DOX framework

- DOX is highly performant AGENTS.md hierarchy installed here
- Agent must follow DOX instructions across any edits

## .dox Storage

Child docs live under `.dox/`, mirroring the scope directory they govern. Source trees stay free of scattered AGENTS.md files.

| Scope (subtree root) | Doc path |
|---|---|
| Repository root | `AGENTS.md` |
| `projects/teste1/` | `.dox/projects/teste1/AGENTS.md` |
| `src/api/handlers/` | `.dox/src/api/handlers/AGENTS.md` |

Rules:

- Only the root rail stays at `AGENTS.md`. Every other doc goes in `.dox/<mirrored-path>/AGENTS.md`.
- `<mirrored-path>` is the scope folder relative to the repo root, without a leading slash.
- Never create `AGENTS.md` beside source files or inside code directories.
- When creating, moving, or deleting a child doc, update the matching path under `.dox/` and keep the mirror aligned with the scope folder.
- Child DOX Index entries use the `.dox/...` path and name the scope folder they cover.

Resolution: for a target at `src/api/foo.ts`, walk `src/`, then `src/api/`, and read `.dox/src/AGENTS.md` and `.dox/src/api/AGENTS.md` when present. The nearest applicable doc is the deepest mirror on that walk.

## Core Contract

- AGENTS.md files are binding work contracts for their subtrees
- Work products, source materials, instructions, records, assets, and durable docs must stay understandable from the nearest applicable AGENTS.md plus every parent AGENTS.md above it

## Read Before Editing

1. Read the root `AGENTS.md`
2. Identify every file or folder you expect to touch, in case it doesnt exists, create it for every file you touch
3. Walk from the repository root to each target path
4. Along each route, read every mirrored doc at `.dox/<path>/AGENTS.md` for directories on that walk
5. If a parent doc lists a child doc whose scope contains the path, read that child at its `.dox/...` path and continue from there
6. Use the nearest applicable doc as the local contract and parent docs for repo-wide rules
7. If docs conflict, the closer doc controls local work details, but no child doc may weaken DOX

Do not rely on memory. Re-read the applicable DOX chain in the current session before editing.

## Update After Editing

Every meaningful change requires a DOX pass before the task is done.

Update the closest owning doc when a change affects:

- purpose, scope, ownership, or responsibilities
- durable structure, contracts, workflows, or operating rules
- required inputs, outputs, permissions, constraints, side effects, or artifacts
- user preferences about behavior, communication, process, organization, or quality
- doc creation, deletion, move, rename, or Child DOX Index contents under `.dox/`

Update parent docs when parent-level structure, ownership, workflow, or child index changes. Update child docs under `.dox/` when parent changes alter local rules. Remove stale or contradictory text immediately. Small edits that do not change behavior or contracts may leave docs unchanged, but the DOX pass still must happen.

If DOX doc doest not exists, you have to create it!!

## Hierarchy

- Root `AGENTS.md` is the DOX rail: project-wide instructions, global preferences, durable workflow rules, and the top-level Child DOX Index
- Child docs live at `.dox/<mirrored-path>/AGENTS.md` and own domain-specific instructions plus their own Child DOX Index
- Each parent explains what its direct children cover and what stays owned by the parent
- The closer a doc is to the work, the more specific and practical it must be

## Child Doc Shape

- Create a child doc at `.dox/<mirrored-path>/AGENTS.md` when a folder becomes a durable boundary with its own purpose, rules, responsibilities, workflow, materials, or quality standards
- Work Guidance must reflect the current standards of the project or user instructions; if there are no specific standards or instructions yet, leave it empty
- Verification must reflect an existing check; if no verification framework exists yet, leave it empty and update it when one exists

Default section order:
- Purpose
- Ownership
- Local Contracts
- Work Guidance
- Verification
- Child DOX Index

## Style

- Keep docs concise, current, and operational
- Document stable contracts, not diary entries
- Put broad rules in parent docs and concrete details in child docs
- Prefer direct bullets with explicit names
- Do not duplicate rules across many files unless each scope needs a local version
- Delete stale notes instead of explaining history
- Trim obvious statements, repeated rules, misplaced detail, and warnings for risks that no longer exist

## Closeout

1. Re-check changed paths against the DOX chain (resolve child docs via `.dox/` mirror)
2. Update nearest owning docs and any affected parents or children under `.dox/`
3. Refresh every affected Child DOX Index
4. Remove stale or contradictory text and delete orphaned `.dox/` mirrors when scopes are removed
5. Run existing verification when relevant
6. Report any docs intentionally left unchanged and why
