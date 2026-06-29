# DOX framework

DOX is the project’s documentation and instruction hierarchy for coding agents.

All work in this repository must follow the applicable DOX chain:
- the root `AGENTS.md`
- every parent `AGENTS.md` between the repository root and the target path
- the nearest `AGENTS.md` that governs the files being changed

Use this file for project-wide rules. Use child `AGENTS.md` files for narrower scopes.

## Purpose

- Keep durable project instructions in version-controlled Markdown files that agents can read directly.
- Keep repository knowledge understandable from the applicable DOX chain, not from chat history or unstated assumptions.
- Keep local rules close to the code, docs, assets, or workflows they govern.
- Keep documentation synchronized with meaningful changes.

## Precedence

- User instructions in the active chat/task override `AGENTS.md` files.
- Within the repository, the nearest applicable `AGENTS.md` controls local work.
- Parent `AGENTS.md` files still apply unless a closer file gives a more specific local rule.
- No child `AGENTS.md` may weaken or contradict this DOX framework. If a local exception is required, document it explicitly in the nearest parent that owns the exception.

## Core contract

- `AGENTS.md` files are durable workflow contracts for their scope.
- Agents must re-read the applicable DOX chain in the current session before editing.
- Do not rely on memory for repository rules.
- Every durable work product must remain understandable from the applicable DOX chain plus the repository contents it references.

## Read before editing

Before making changes:

1. Read the root `AGENTS.md`.
2. Identify the files and directories you expect to inspect, create, move, rename, or delete.
3. For each target path, walk from the repository root to that path.
4. Read every `AGENTS.md` encountered on that path.
5. Apply the nearest `AGENTS.md` as the local contract and all parent `AGENTS.md` files as inherited context.
6. If the applicable Child DOX Index is missing, stale, or incomplete, update it before or as part of the work when the repository is available to scan.

## Maintain DOX after changes

Perform a DOX pass after every meaningful change.

Update the nearest owning `AGENTS.md` when a change affects:
- purpose, scope, ownership, or responsibilities
- durable structure, architecture, boundaries, or workflows
- required inputs, outputs, permissions, constraints, side effects, or generated artifacts
- user preferences about behavior, communication, process, organization, or quality
- creation, deletion, move, rename, or re-scoping of any `AGENTS.md`

Update parent `AGENTS.md` files when parent-owned structure or child indexes change.
Update child `AGENTS.md` files when parent changes alter local rules.
Remove stale or contradictory instructions immediately.

Small edits that do not change durable behavior may leave `AGENTS.md` files unchanged, but the DOX pass is still required.

## Root responsibilities

The root `AGENTS.md` owns:
- project-wide instructions and constraints
- repository-wide workflow expectations
- durable documentation policy
- the top-level Child DOX Index

The root `AGENTS.md` should stay concise.
Put local commands, stack details, architecture notes, and workflow specifics in the closest child `AGENTS.md` that owns them.

## Child document rules

Create a child `AGENTS.md` when a directory becomes a durable boundary with its own:
- purpose
- ownership
- local contracts
- workflow or operating rules
- inputs or outputs
- verification expectations
- artifacts or assets

Each parent `AGENTS.md` must describe:
- which direct children exist
- what each direct child owns
- what remains owned by the parent

Default section order for child `AGENTS.md` files:
- Purpose
- Ownership
- Local Contracts
- Work Guidance
- Verification
- Child DOX Index

If a section has no current content:
- leave `Work Guidance` empty rather than inventing preferences
- leave `Verification` empty rather than inventing checks

## Style

- Keep instructions concise, specific, and testable.
- Prefer direct bullets, short sections, and explicit file or directory names.
- Use active voice and concrete verbs.
- Document stable rules and reusable workflows, not temporary task history.
- Put broad policy in parent docs and concrete practice in child docs.
- Avoid repeating the same rule across many files unless each scope truly needs a local copy.
- Reference canonical files and paths instead of duplicating large bodies of text.
- Delete stale guidance instead of preserving historical notes.

## Closeout

Before finishing a task:

1. Re-check the changed paths against the applicable DOX chain.
2. Update every affected `AGENTS.md`, including parents, children, and indexes.
3. Remove stale or contradictory guidance.
4. Run the existing verification commands for the changed scope when such commands exist.
5. Report which `AGENTS.md` files were updated.
6. Report any applicable `AGENTS.md` files intentionally left unchanged and why.

## User preferences

Record durable user preferences here or in the nearest child `AGENTS.md` that owns them.

Current durable preferences:
- Preferred language: en-US

## Child DOX Index

Status: pending initial repository scan.

Before substantive repository work continues, replace this placeholder with the actual top-level DOX index based on a recursive scan of the repository.

The index must list each direct child boundary owned by this file, what it covers, and where deeper child `AGENTS.md` files exist.
