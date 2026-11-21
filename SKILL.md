---
name: prompting-management-26q4
description: "Use when creating, auditing, improving or migrating prompts, agent skills, AGENTS.md or other model-facing instructions."
version: 0.3.0
author: Xipong, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [prompting, skills, context-engineering, evaluation]
---

# Prompting Management — 2026 Q4

Help a capable model understand the task and produce a good result. Choose wording, context, examples and workflow around that goal.

## When to Use

Use when creating, reviewing or improving task prompts, reusable skills, AGENTS.md, application instructions, schema descriptions or capability cards.

## Approach

- State the goal, the context that matters and what a good result looks like. Explain important trade-offs and let the model choose how to solve the task.
- Supply knowledge the model needs: available operations, data meanings and units, relevant evidence, tool behavior and dependencies.
- Separate factual inputs, real requirements and preferences. Make the available design space clear, including where the model can invent, explore or propose alternatives.
- Match the prompt to its execution environment. Give an agent usable tools and feedback; give a single-shot generator the context needed to produce its answer.
- For agentic work, describe what counts as completion, which routine steps the agent can take and which decisions need the user. Let it recover from ordinary failures and continue independent work while waiting for an answer.
- Use examples when they communicate intent, quality, format or a difficult distinction. Choose examples that represent the range of acceptable results.
- Keep reusable guidance at a clear owner and route to detailed material when it helps the current task. Review the combined instructions as well as individual sentences: several reasonable rules can jointly steer the model toward a poor result.
- Improve the mechanism behind recurring failures. Clearer interfaces, better input data, tools and automatic checks can solve problems that wording alone cannot.

## Choose the work

| Task | Reference |
|---|---|
| Create a prompt, audit its effects or improve a weak result | [Creation and repair](references/create-and-repair.md) |
| Migrate to GPT-6.2 Astra, GPT-6.2 Sol or Claude Fable 5.2, or diagnose behavior specific to those models | [Model guidance](references/model-guidance.md) |
| Compare outcomes and choose a revision | [Evaluation and metrics](references/evaluation.md) |
| Read the reasoning and sources behind this approach | [Sources and rationale](references/sources.md) |
| Start from a prompt outline | [Prompt shapes](templates/prompt-shapes.md) |

Choose the scope of the change from the problem. A sentence edit may resolve an ambiguity; accumulated conflicts or a poor task framing may call for a full rewrite. Keep useful detail and expressive capacity while removing obsolete or irrelevant guidance.

Respect the user's requirements, permissions and resource limits. Distinguish those from inherited habits or self-imposed restrictions. When the task calls for changing a contract, update its instructions and consumers together.

Use the tools, examples and evaluations that help resolve the task. Match verification to the behavior affected and work within the available budget. Return the improved prompt or skill, explain the important choices, and give the evidence needed to judge the result.

## Sources

The approach draws on OpenAI and Anthropic guidance, Poteto/pstack, agent-skill research and their application in InfiniCrafterLocal. See [Sources and rationale](references/sources.md).
