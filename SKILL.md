---
name: prompting-management-26q4
description: "Use when creating or repairing model-facing prompts."
version: 0.1.0
author: Xipong, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [prompting, skills, context-engineering, evaluation]
---

# Prompting Management — 2026 Q4

Create or repair instructions that help a capable model achieve the user's goal. Optimize accepted outcomes and the complete cost of getting them, not prompt length or obedience to a prescribed itinerary.

## When to Use

Use for task prompts, reusable agent instructions, application system/developer messages, schema descriptions and capability cards. Do not load this merely because a task uses an LLM, measures token usage or touches a repository containing AGENTS.md.

## Working model

- Give the model the goal, relevant evidence, real constraints and a recognizable good result. Leave interchangeable implementation choices open; prescribe order only for actual dependencies or fragile operations.
- Add knowledge the model cannot reliably infer: supported operations, data meanings and units, authority boundaries, consumer behavior and working tools. Preserve useful expressive capacity when simplifying.
- Separate source facts, mandatory contracts and advisory preferences. A restriction on claims about existing facts does not forbid creative synthesis within supported capabilities.
- Match instructions to the execution mode. A single-shot generator cannot perform an agent's tool-driven investigation; a self-report is not evidence that checks ran.
- Keep each rule at one owner. Put the main decision and critical invariants in the entry document; load task-specific depth only when relevant. A collection of links without enough guidance to choose a path is not a useful skill.
- Fix the failure mechanism. Repeated mistakes can point to missing data, unclear interfaces, unavailable capabilities or weak diagnostics rather than insufficient reminders. Enforce machine-checkable invariants in code while still explaining the contract to the model.
- Treat examples as demonstrations, not hidden requirements. Prefer examples that resolve a real ambiguity; do not accidentally impose one design, style or level of complexity on every answer.

## Choose the work

| Need | Read |
|---|---|
| Build a new prompt or repair an unsuccessful one | [Creation and repair](references/create-and-repair.md) |
| Decide whether an instruction change helps | [Evaluation and metrics](references/evaluation.md) |
| Understand the evidence, dates and limits behind this approach | [Sources and rationale](references/sources.md) |
| Start a task brief or a single-shot request | [Optional prompt shapes](templates/prompt-shapes.md) |

For a small edit, inspect the affected instruction and its real consumer. Broaden to the effective message hierarchy when a conflict, missing context or cumulative inhibition is plausible. Do not turn every wording change into a full audit, model experiment or multi-agent workflow.

## Preserve and verify

Preserve actual user permissions, accepted output contracts, units, supported choices and important applicability conditions. Do not weaken a check to make a response pass, invent missing source facts or silently remove a valid option during compression.

Use the cheapest evidence that answers the remaining question. Structural and semantic inspection can establish a prose edit's intended meaning; only appropriate task execution can establish a behavioral improvement. Fresh inference, paid services, tool launches and publication remain within the user's granted scope and budget.

Deliver the requested prompt or edit, the material decision behind it and the evidence obtained. Identify unresolved behavior without claiming an unrun experiment passed. Skip a change when the current instruction is already clear and consumer-correct.

## Provenance

This is an original synthesis informed by the dated sources in [Sources and rationale](references/sources.md), including InfiniCrafterLocal's contributor guidance, OpenAI, Poteto/pstack and agent-skill research. It is not a copy of pstack, a vendor policy or an ICL runtime contract. The Q4 label identifies the evidence snapshot, not a permanent rule that future models behave identically.
