# sdlab-{{NN}}-{{SLUG}}: {{TITLE}}

Build {{NN}} of the System Design Lab. The lab-wide method, rules, skills and hooks live in the sdlab workspace (`../CLAUDE.md`, `../.claude/`); launch Claude Code from the workspace root.

**Prompt:** {{PROMPT}}

**What this build teaches:** {{LEARN}}

## Invariants

The invariant checker (`loadtest/invariants/`) proves these after every load profile and chaos experiment. A run that violates one is a failed run, however fast it was.

{{INVARIANTS}}

## Where things are

- `design/build-plan.md`: build path, current loop step, tags, ADRs, headline numbers. Read it first.
- `design/00-interview-design.md`: the frozen whiteboard answer. Never edit it.
- `services/` Python services · `web/` demo UI · `loadtest/` scenarios and invariant checker · `chaos/` experiments · `results/` generated run data, never hand-edited.

## Commands

`make help` lists everything. Common: `make up`, `make down`, `make seed`, `make check`, `make test`, `make test-integration`, `make load PROFILE=smoke|load|stress|spike|soak|contention`, `make chaos EXP=<NN-slug>`, `make results`.

## Platform

Pinned to sdlab-platform through `SDLAB_VERSION` in `.env`, which must match the devcontainer image tag and the `sdlab-core` git tag in each `pyproject.toml`. Upgrade only with `make platform-upgrade V=X.Y.Z`, and only while actively working on this build.

## Build notes

<!-- Conventions, gotchas and decisions specific to this build, added as they come up. -->
