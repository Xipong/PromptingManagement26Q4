---
name: prompting-management-26q4
description: "Write, audit or revise task prompts, system instructions and agent skills when the user asks for help with prompting."
version: 0.3.0
author: Xipong, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [prompting, skills, prompt-design]
---

# Prompting Management — 2026 Q4

Write for the model that will receive the prompt. Say what the user wants to accomplish and give the model the facts it would otherwise have to guess. In a one-shot prompt, include the relevant material. For an agent that can inspect it, a precise reference may suffice.

Distinguish requirements from preferences. Give the reason for a constraint when it helps the model make a judgment. Specify a method when the task depends on it. Leave other decisions open.

For example, “stay faithful to the two source items” is ambiguous in a crafting prompt. Try “Keep the listed properties of both items accurate. Invent a new effect that draws on both identities using the available game mechanics.” This preserves factual accuracy and gives the model room to design.

## Auditing a prompt

Read the instructions as the receiving model sees them, including any examples, injected context or referenced guidance it actually receives. What would count as a good result for the user? Where could the model satisfy the instructions yet miss that goal? Look at how the parts work together. An example can quietly narrow the options that the prose leaves open.

When the model chooses from a set of operations, check what their descriptions let it infer. A schema may accept `duration: 30` while leaving the unit unclear. If a parameter only applies to certain operations, put that condition beside the field so the model can use it when choosing.

Ground each finding in a specific passage or missing fact. Explain the decision it steers and suggest a change if one would help. Use an existing answer when available, distinguishing what happened from what the wording might encourage. An audit can conclude that the prompt already serves its purpose. When the user also asks for fixes, apply the supported changes.

## When moving an existing prompt to a newer model

Use these observations when they explain something you see in the output.

- **GPT-6.2 Sol and Astra.** If a requested draft reads like internal notes, name its reader and the context that reader needs. For instance, “Write the release note for players who have never seen the bug report.” Astra already tends toward brevity. Revisit inherited “be concise” instructions if answers omit useful detail. [OpenAI prompting guidance](https://developers.openai.com/api/docs/guides/latest-model#prompting-best-practices)
- **Claude Fable 5.2.** Read old absolutes literally. If “never change the terminology” was meant to protect product names, say “Keep product names verbatim.” Role descriptions can also widen the task. Calling Claude the owner of a codebase can encourage unrelated cleanup even alongside a narrow edit request. Use a role only when its implied responsibility fits. [Anthropic prompting guidance](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)
