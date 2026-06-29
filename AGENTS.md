# DOX Framework

DOX is the repository instruction system for AI-assisted and human-assisted edits. Every `AGENTS.md` is an operational contract for its directory subtree.

## Purpose

- Keep repository work understandable from the active task, the applicable `AGENTS.md` chain, and durable project artifacts.
- Reduce agent exploration time by recording stable structure, commands, contracts, and verification where they are owned.
- Prevent instruction drift by updating DOX docs when durable behavior, workflow, ownership, or structure changes.

## Authority and Scope

- The root `AGENTS.md` is the project-wide DOX rail.
- A child `AGENTS.md` applies to its directory subtree.
- For any touched path, follow the nearest `AGENTS.md` plus every parent `AGENTS.md` up to the root.
- Active session instructions from the user, system, or developer override repository docs.
- Within repository docs, closer docs may specialize local details. A child doc must not weaken root DOX requirements or parent constraints unless the parent explicitly delegates that exception.
- Treat DOX as a behavioral contract, not a security boundary. Enforce hard blocks with tool settings, hooks, CI, permissions, code owners, or sandbox policy.

## Fast Start Before Editing

1. Read this root `AGENTS.md`.
2. Identify every file and folder expected to be read, edited, moved, generated, or deleted.
3. Discover applicable docs by scanning for `AGENTS.md` files along each target route from the repository root.
4. Read the full DOX chain for every target path, from root to nearest owner.
5. If a new target path appears during work, stop and read its DOX chain before touching it.
6. Use the nearest owning `AGENTS.md` for local details and parent docs for broader rules.
7. Do not rely on memory from previous sessions; re-read the applicable chain in the current session.

## Discovery and Indexing

- The Child DOX Index is a navigation aid, not the only source of truth.
- Before meaningful edits in an unindexed or stale area, scan recursively enough to find existing `AGENTS.md` files and durable boundaries.
- Refresh the affected parent index when a child `AGENTS.md` is created, deleted, moved, renamed, or rescopied.
- Do not create child docs merely to make the tree look complete. Create them only for durable boundaries with distinct rules, ownership, workflow, materials, or verification.

## What Belongs in DOX

Record stable, reusable contracts that affect future work:

- purpose, scope, ownership, and responsibilities
- architecture landmarks, source-of-truth files, generated artifacts, and durable data locations
- setup, build, test, lint, release, migration, or verification commands that are known to work
- required inputs, outputs, permissions, side effects, constraints, and artifact handling
- local coding or API conventions not already enforced by tools
- user or team preferences that should persist across sessions
- known command caveats, unsupported checks, and required workarounds

Do not use DOX for:

- secrets, credentials, private tokens, or sensitive personal data
- diary entries, task history, temporary plans, or changelog prose
- generic advice such as “write clean code” or “be careful”
- lint or format rules already enforced by configured tools, unless agents routinely need an explanation to avoid failed runs
- long procedures that belong in scripts, runbooks, or task-specific skills; link to the durable source and summarize only the trigger

## Update After Editing: DOX Pass

Every meaningful change requires a DOX pass before closeout.

Update the closest owning `AGENTS.md` when a change affects:

- purpose, scope, ownership, or responsibilities
- durable structure, contracts, workflows, operating rules, or source-of-truth locations
- setup, build, verification, release, migration, or artifact-generation behavior
- required inputs, outputs, permissions, constraints, side effects, or artifacts
- user or team preferences about behavior, communication, process, organization, or quality
- creation, deletion, move, rename, scope, or index contents of any `AGENTS.md`

Update parent docs when parent-level structure, ownership, workflow, or child index changes. Update child docs when parent changes alter local rules. Remove stale or contradictory text immediately.

Small edits that do not change behavior or contracts may leave docs unchanged, but the DOX pass still happens and the closeout report must say why docs were intentionally left unchanged.

## Hierarchy Model

- Root owns project-wide rules, global preferences, repository-wide workflow, and the top-level Child DOX Index.
- Child docs own local contracts for durable subtrees.
- Parent docs explain what each direct child covers and what remains parent-owned.
- Child docs should be more specific and practical than parent docs.
- Avoid duplicating parent rules in children. Reference the parent rule when local work only inherits it.

## Child AGENTS.md Creation Criteria

Create a child `AGENTS.md` when a folder has at least one durable difference from its parent, such as:

- distinct ownership or responsibility
- different setup, build, test, release, verification, or deployment workflow
- distinct architecture, data, generated artifacts, or source materials
- local safety, permissions, side effects, or quality constraints
- recurring local guidance that would bloat the parent doc

Do not create a child doc for one-off changes, temporary task notes, or a folder whose rules are fully described by its parent.

## Standard Child Doc Shape

Use this section order unless a local parent contract says otherwise:

1. `Purpose`
2. `Scope`
3. `Ownership`
4. `Local Contracts`
5. `Structure Map`
6. `Work Guidance`
7. `Verification`
8. `Child DOX Index`

Section rules:

- `Purpose`: one or two bullets explaining why the subtree exists.
- `Scope`: exact paths or file groups owned by this doc.
- `Ownership`: responsible component, team, domain, or maintainer role when known.
- `Local Contracts`: binding local rules, invariants, side effects, dependencies, and source-of-truth files.
- `Structure Map`: concise path map for high-value files and folders only.
- `Work Guidance`: local conventions that agents need and tools do not already enforce.
- `Verification`: existing checks only. If no check exists, write `None yet.`
- `Child DOX Index`: direct child `AGENTS.md` files only.

## Child DOX Index Format

Each parent index lists direct child docs, not every descendant.

Recommended format:

| Path | Scope | Read when |
| --- | --- | --- |
| `path/to/AGENTS.md` | What this child owns | When touching `path/to/**` |

Index rules:

- Keep entries short and operational.
- Add, remove, or update entries in the same change that alters the child doc.
- Do not duplicate a grandchild index in the parent unless the parent needs a high-level warning or routing note.
- If a subtree has no child docs, say `None yet.`

## Verification

- Run the smallest relevant existing check from the nearest owning doc.
- Run broader checks when changes affect shared infrastructure, public APIs, generated artifacts, or cross-subtree behavior.
- Prefer documented project commands over ad hoc commands.
- When adding or changing a documented command, validate it when practical and record any prerequisite or known failure mode.
- If verification cannot run, report the reason, the command that should be run, and the risk left open.
- Never claim a check passed unless it was actually run and completed successfully.

## Context Budget and Performance

- Keep each `AGENTS.md` concise enough to be read every session; target under 200 lines unless the subtree genuinely needs more.
- Prefer exact paths, commands, and invariants over explanatory prose.
- Put broad rules in parents and local details in children.
- Remove duplicates, obsolete warnings, and rules that automated tools already enforce.
- Split large local guidance by durable subtree instead of growing the root indefinitely.
- For cross-cutting but rarely needed procedures, keep the procedure in a dedicated script, runbook, or skill and mention only when to use it.

## Interoperability Notes

- Keep `AGENTS.md` as the canonical DOX source.
- Agent-specific files may import, link, or delegate to `AGENTS.md`, but must not fork durable rules unless the difference is tool-specific and documented.
- If a tool cannot load nested `AGENTS.md` files, add a small adapter file or configuration that points the tool to this file.
- Do not maintain parallel copies of the same rules across `AGENTS.md`, `CLAUDE.md`, `.github/copilot-instructions.md`, `.github/instructions`, `.roo/rules`, `.devin/rules`, `.windsurf/rules`, `.cursorrules`, or `.gemini/settings.json`.

## Safety and Permissions

- Do not store secrets, credentials, private keys, or sensitive personal data in DOX docs.
- Treat generated files, migrations, data changes, network calls, destructive commands, and permission changes as side-effecting work that must be documented where durable.
- Use CI, hooks, sandbox settings, code owners, branch protections, or tool permissions for hard enforcement. DOX tells agents what to do; enforcement systems stop unsafe actions.

## Closeout

Before finishing any meaningful task:

1. Re-check every touched path against its DOX chain.
2. Run the DOX pass and update the nearest owning docs when triggers apply.
3. Refresh every affected Child DOX Index.
4. Remove stale, duplicate, or contradictory instructions.
5. Run relevant existing verification, or report why it was not run.
6. Report:
   - files changed
   - DOX chain read
   - docs updated, or docs intentionally unchanged with reason
   - verification run and result
   - remaining risks or follow-up needed

## User Preferences

Record durable behavior preferences here only when they apply project-wide. Put local preferences in the relevant child `AGENTS.md`.

- None yet.

## Child DOX Index

| Path | Scope | Read when |
| --- | --- | --- |
| `_UNINDEXED_` | This project has not yet been indexed. | Before the first meaningful edit, scan recursively for durable boundaries and existing `AGENTS.md` files, then replace this row with direct child docs. |
