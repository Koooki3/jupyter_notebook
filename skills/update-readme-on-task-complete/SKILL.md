---
name: update-readme-on-task-complete
description: Update repository README.md and requirements.txt after a thread task is completed so documentation and dependency declarations stay aligned with the latest experiments, datasets, scripts, notebooks, or workflow changes. Use when Codex finishes implementing, fixing, or reorganizing work in this repository and needs to decide whether README.md and requirements.txt should be refreshed, expanded, or left unchanged with an explicit check.
---

# Update README And Requirements On Task Complete

## Overview

Treat README and dependency maintenance as part of task completion, not as optional afterthoughts. Inspect the finished work, compare it with the current `README.md` and `requirements.txt`, update only the parts affected by the completed task, and keep both files concise and accurate.

## Workflow

1. Identify the user-visible repository change.
2. Open the root `README.md`, `requirements.txt`, and any touched files needed to verify the new behavior or structure.
3. Decide whether the task changes setup steps, directory layout, entry points, experiment locations, outputs, usage guidance, or Python dependencies.
4. Update `README.md` only where the task changed repository reality.
5. Update `requirements.txt` when the completed task added, removed, or made a Python dependency unnecessary.
6. In the final response, state whether `README.md` and `requirements.txt` were updated or explicitly checked and left unchanged.

## Decide Whether README Needs Changes

Update `README.md` when the completed task changes any of the following:

- Repository structure shown in docs
- Required dependencies, setup commands, or launch commands
- Canonical notebook paths, experiment folders, or data locations
- Supported workflows, scripts, or automation behavior
- Limitations, caveats, or expected outputs a future contributor should know

Do not update `README.md` for:

- Internal refactors with no user-visible effect
- Temporary debugging changes
- Pure formatting edits outside documentation scope
- Experimental branches of work that are not meant to be documented yet unless the user asks

If nothing material changed, say that `README.md` was reviewed and no update was necessary.

## Decide Whether Requirements Need Changes

Update `requirements.txt` when the completed task changes any of the following:

- A new imported runtime dependency is required for the repo workflow
- A previously required package is no longer needed
- A package version floor should change because the implementation now depends on a newer feature
- A newly documented script or notebook cannot run in the advertised environment without an added package

Do not update `requirements.txt` for:

- Libraries used only in one-off local debugging unless the repo now depends on them
- Packages that are already transitively installed but not actually imported or required by this repo
- Guesswork about optional tooling that was not introduced by the completed task

If the task did not change repository dependencies, say that `requirements.txt` was reviewed and no update was necessary.

## Update Rules

- Prefer editing existing sections over adding redundant new sections.
- Keep repository-specific paths accurate and copyable.
- Describe outcomes and usage at a high level; avoid turning the README into a change log.
- Preserve the existing language and structure unless they are now misleading.
- When adding a new capability, mention where it lives in the repo and how to use it.
- Keep dependency declarations minimal and repository-wide; do not add speculative packages.
- When a task adds a new recurring maintenance expectation, document the expectation in one short section or bullet.

## Final Response Requirement

Always report one of these outcomes:

- `README.md and requirements.txt updated to reflect ...`
- `README.md updated; requirements.txt checked with no dependency change needed.`
- `README.md checked; requirements.txt updated to reflect ...`
- `README.md and requirements.txt checked; no documentation or dependency change was needed.`

## Example Triggers

- "Finish this notebook refactor and sync the README and requirements."
- "Update the repository docs after reorganizing experiment folders."
- "Check whether README and requirements need changes before closing the task."
- "Add the new data-processing script and any dependency it needs."
