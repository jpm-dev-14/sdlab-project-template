# Load tests

Every build follows the same contract. The implementation lands with the platform in Phase 0.

- `make load PROFILE=<profile>` drives the running stack, runs the invariant checker, and writes one results file to [`../results/`](../results/).
- Profiles: `smoke` (1 min), `load` (expected peak, 10 min), `stress` (ramp until it breaks), `spike` (zero to peak in seconds), `soak` (1 h at moderate load), plus `contention` wherever there's a hot key.
- Open workload model: arrival-rate executors only, so a slow server can't slow the load generator down and hide its own latency.
- Keys come from Zipf or power-law distributions over a dataset larger than the cache.
- `invariants/` holds this build's invariant checker, which exits non-zero and prints counterexamples on any violation.
