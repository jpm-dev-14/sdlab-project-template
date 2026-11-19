# sdlab-project-template

GitHub template for [System Design Lab](https://jpm-dev-14.github.io/sdlab-blog/) builds. Each build repo (`sdlab-NN-<slug>`) is created from it once and never synced afterwards; improvements are carried into an active build by hand.

> **Status:** skeleton. The runnable parts (Compose, Makefile, service Dockerfile, pyproject, devcontainer, pre-commit, CI and the web starter) land in Phase 0 together with [sdlab-platform](https://github.com/jpm-dev-14/sdlab-platform) v0.1.0.

## What a build gets

```
.env           SDLAB_VERSION, the platform version pin          (Phase 0)
compose.yaml   platform stacks via OCI includes, plus services  (Phase 0)
Makefile       up, down, seed, load, chaos, results, check      (Phase 0)
services/      Python services                                  (Phase 0)
web/           demo UI: React + TypeScript + Vite               (Phase 0)
loadtest/      k6 and Locust scenarios, invariant checker
chaos/         failure experiments and their write-ups
results/       generated benchmark runs, never hand-edited
design/        interview design, build plan, ADRs, journal, retro, cheat sheet
```

## Creating a build

Builds are created by the lab workspace's `/start-build NN` skill. It runs `gh repo create --template`, replaces this README and `CLAUDE.md` with the skeletons in `.template/`, and fills their placeholders from the curriculum.

## License

[MIT](LICENSE)
