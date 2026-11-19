# Build plan: {{TITLE}}

Loop step: 1 — Whiteboard

Started {{DATE}}. The lab loop: 1 Whiteboard → 2 Naive v1 → 3 Measure → 4 Fix bottlenecks → 5 Chaos → 6 Retro → 7 Ship → Done.

## Build path

One tag per step. Every step after `v1` fixes one bottleneck and has an ADR with before/after numbers.

| Step | Tag | Change | Status | ADR | Headline (results file) |
| --- | --- | --- | --- | --- | --- |
{{STEPS}}

## Loop checklist

- [ ] 1. Whiteboard (`/interview`): `00-interview-design.md` and `01-interview-feedback.md` committed
- [ ] 2. Naive v1 correct on one node, with the "why this store" ADR (`/adr decision`), tagged `v1` (`/tag-step`)
- [ ] 3. Measured to the breaking point (`/measure stress`, `/measure spike`) with the invariant checker passing
- [ ] 4. Fixes: one per tag, each with an ADR and before/after numbers (`/adr fix`, then `/tag-step`)
- [ ] 5. Chaos: at least one experiment written up (`/chaos`)
- [ ] 6. Retro written; lessons added to the workspace `docs/lessons.md` (`/retro`)
- [ ] 7. Ship: README, cheat sheet (`/cheatsheet`), blog post (`/blog-post`), CI green, images published; `/ship-check` passes
