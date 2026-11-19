# sdlab-project-template

The skeleton every build copies once through the workspace's `/start-build` skill. Changes here only affect builds created afterwards. Lab-wide rules: the workspace `../CLAUDE.md`.

## Rules

- Skeleton and conventions only; no build-specific logic.
- `.template/README.md` and `.template/CLAUDE.md` become the build's README and CLAUDE.md. Their placeholders must stay in sync with the `/start-build` skill: `{{NN}}`, `{{SLUG}}`, `{{TITLE}}`, `{{ONE_LINER}}`, `{{PROMPT}}`, `{{LEARN}}`, `{{DEMO}}`, `{{MEASURE}}`, `{{LOAD_PROFILE}}`, `{{STORES}}`, `{{BLOG_ANGLE}}`, `{{INVARIANTS}}`, `{{STEPS}}`, `{{DATE}}`.
- Once Phase 0 lands, the template must always work: a fresh copy passes `make up && make load PROFILE=smoke` in CI.

## Phase 0 checklist (with sdlab-platform v0.1.0)

- [ ] `.env` with `SDLAB_VERSION=0.1.0`, plus a CI check that `.env`, the devcontainer tag and the `sdlab-core` tag in every pyproject agree
- [ ] `compose.yaml`: postgres, redis and observability stacks via `include: - oci://…`, plus a hello-world `api` service with limits, a healthcheck and the `sdlab.scrape` label
- [ ] `services/api/`: Dockerfile per the platform pattern, `pyproject.toml` with `sdlab-core` as a git dependency at the tag, `src/` layout, unit and integration tests
- [ ] `Makefile`, GNU make 3.81 compatible: `help up down seed load chaos results check test test-integration platform-upgrade`
- [ ] `loadtest/`: k6 smoke profile (open model) and an invariant checker stub; results written through the platform exporter
- [ ] `.devcontainer/` on `sdlab-dev`; `.pre-commit-config.yaml` with ruff, mypy, whitespace and YAML checks
- [ ] The shared ruff and mypy settings present in the repo itself, so the editor, the host's format hook and `sdlab-dev check` in CI all apply the same rules
- [ ] `.github/workflows/ci.yml`: check, integration tests, k6 smoke; on `v*` tags, build and push multi-arch service images as `ghcr.io/jpm-dev-14/<repo>-<service>:<vN>`
- [ ] `web/` starter: Vite + React + TypeScript + Tailwind + shadcn/ui with the lab layout (controls left, system view middle, metrics right) and the shared components (LiveChart, EventLog, ControlPanel, ChaosButtons)
