# Sources and rationale

Evidence snapshot: **2026 Q4**; reviewed during **6–7 November 2026**. This guide is an original synthesis, not a vendor policy or a measured performance guarantee. The linked `main` files and vendor pages can change; the papers below use explicit versions and X posts have stable IDs.

## What informed the changes

| Source | Evidence or practice taken from it | What this guide does not infer |
|---|---|---|
| InfiniCrafterLocal contributor guidance | Goal, purpose, relevant context and good-result criteria; review old scaffolding; apply guidance to all model-facing surfaces, not only the main prompt.[1] | That ICL's immutable Author/frozen Repair rules apply to every LLM application. |
| OpenAI, *Rethinking skills and prompts for GPT-6 Astra*, 11 September 2026 | Narrow skill triggers and progressive disclosure; review accumulated instructions as model capabilities improve.[7] | That every skill should be deleted or that the shortest prompt is best. |
| Poteto, 16 October 2026 | Prefer architecture/invariants and automated checks over repeatedly relying on prose and manual review.[9] | That a validator makes model-facing explanations unnecessary. |
| Poteto, 24 October 2026 | The author expects to simplify pstack as models improve, with skills tending toward smaller saved prompts.[10] | That this expectation is a controlled result or a universal size limit. |
| Poteto, 5 November 2026 | Verification is relative to specified properties/assumptions; expose behavior so a person can judge whether it matches intent; combine formal and empirical checks where useful.[19] | That a proof establishes user intent or that every task needs formal verification. |
| pstack, `/sharpen` | Improve a task through professional methods, primary materials and an outside correctness signal while leaving user-owned choices open.[14] | That the model may expand scope or must emit a fixed four-part preamble on every task. |
| pstack, *Make it yours* | Learn from recurring failure classes, prefer structural remedies and compare skill changes without revealing preferred labels to candidates.[22] | That every wording change needs several model reviewers or a live evaluation. |
| pstack, benchmark checklist | Check errors, whether timed work really ran, variability and relevance to the complete user-visible path.[15] | That one benchmark's run-count rule is a universal budget requirement. |

The metric definitions, repair taxonomy and optional templates here are our operational synthesis. They are not claimed as verbatim recommendations from any one source.

## Research: helpful knowledge is not the same as more instructions

**SkillsBench v4** reports 87 tasks and 18 model–harness configurations. Curated skills raise the reported average pass rate from 33.9% to 50.5%, a gain of 16.6 percentage points; the abstract also reports better results from focused rather than exhaustive bundles.[12]

**Evaluating AGENTS.md v1** reports that context files can reduce task success and increase inference cost by over 20%; extra instructions encourage additional exploration and testing.[11]

These are different workloads and interventions. Their results support evaluating instruction relevance and useful procedural knowledge, not transferring a numerical gain to a new model, skill library or task. This package has not itself been through a live A/B benchmark.

## Source access and attribution

Repository text was read through GitHub's raw endpoints. Relevant OpenAI text and the versioned paper abstracts were retrieved through web extraction; the OpenAI browser route returned a 403, so no claim here depends on unread later sections. The X pages timed out in the browser. Their full text was read through the public FxTwitter API with the same post IDs, including [the 5 November post](https://api.fxtwitter.com/poteto/status/2118416074601545968). The original X URLs remain the publication references.

This package does not reproduce the pstack implementation, vendor manuals or research datasets. Linked works retain their respective ownership; the MIT license covers the original text in this package, not the external sources.

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
