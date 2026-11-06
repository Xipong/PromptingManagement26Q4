# Sources and rationale

Sources reviewed on **6–7 November 2026**.

## Practical guidance

| Source | Contribution to this guide |
|---|---|
| InfiniCrafterLocal AGENTS.md | Project synthesis of the prompting guides below: convey the goal, context and good-result criteria across all model-facing instructions. This was the starting point for the standalone skill.[1] |
| OpenAI, *Rethinking skills and prompts for GPT-6 Astra*, 11 September 2026 | Focus skill triggers, use progressive disclosure and revisit accumulated instructions as models improve.[7] |
| Poteto, 16 October 2026 | Improve architecture, invariants and automated feedback so the environment helps agents do the right thing.[9] |
| Poteto, 24 October 2026 | Simplify skills as models become more capable.[10] |
| Poteto, 5 November 2026 | Make system behavior legible enough to compare with human intent; combine specification checks with running the actual code.[19] |
| pstack, `/sharpen` | Deepen the task through professional methods, primary materials and a useful correctness signal while keeping the user's choices open.[14] |
| pstack, *Make it yours* | Learn from recurring failure classes and compare skill revisions on real tasks using neutral candidate labels.[22] |
| pstack, benchmark checklist | Check that measured work ran, outputs were correct, variation was considered and the result matters to the complete user workflow.[15] |

## Research

**SkillsBench v4** evaluates 87 tasks across 18 model–harness configurations. Curated skills raise the reported average pass rate from 33.9% to 50.5%, a gain of 16.6 percentage points. The paper also reports better results from focused rather than exhaustive bundles.[12]

**Evaluating AGENTS.md v1** finds that extra repository instructions can reduce task success while increasing inference cost by over 20%; they encourage more exploration and testing.[11]

Together, these results motivate the guide's practical focus: add useful knowledge, remove irrelevant work and compare revisions on the tasks they should help.

## Sources

[1] https://github.com/Xipong/InfiniCrafterLocal/blob/main/LocalGenerator/infini_local/AGENTS.md — InfiniCrafterLocal: AGENTS.md
[7] https://learn.chatgpt.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra — OpenAI: Rethinking skills and prompts
[9] https://x.com/poteto/status/2111133080526495985 — Poteto, 16 October: architecture, checks and instructions
[10] https://x.com/poteto/status/2114099131845423142 — Poteto, 24 October: simplifying skills as models improve
[11] https://arxiv.org/html/2602.11988v1 — Evaluating AGENTS.md, v1
[12] https://arxiv.org/html/2602.12670v4 — SkillsBench, v4
[14] https://raw.githubusercontent.com/cursor/plugins/main/pstack/skills/sharpen/SKILL.md — pstack: sharpen
[15] https://raw.githubusercontent.com/cursor/plugins/main/pstack/skills/benchmark-checklist/SKILL.md — pstack: benchmark-checklist
[19] https://x.com/poteto/status/2118416074601545968 — Poteto, 5 November: specification, intent and verification
[22] https://raw.githubusercontent.com/cursor/plugins/main/pstack/docs/guide/09-make-it-yours.md — pstack: Make it yours
