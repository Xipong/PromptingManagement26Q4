---
name: prompting-management-26q4
description: "Write or revise task prompts, system instructions and agent skills when the user asks for help with prompting."
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

## Revising a prompt

Read the prompt alongside the request and, when available, an actual answer. Where could a model follow the wording and still miss the point? An example may accidentally prescribe a layout, or two individually reasonable rules may conflict. Edit the instruction that led to that reading. If a missing fact explains the failure, supply it. If you have a representative input, try the revision on it and judge the resulting answer by the user’s goal.

## When moving an existing prompt to a newer model

Use these observations when they explain something you see in the output.

- **GPT-6.2 Sol and Astra.** If a requested draft reads like internal notes, name its reader and the context that reader needs. For instance, “Write the release note for players who have never seen the bug report.” Astra already tends toward brevity. Revisit inherited “be concise” instructions if answers omit useful detail. [OpenAI prompting guidance](https://developers.openai.com/api/docs/guides/latest-model#prompting-best-practices)
- **Claude Fable 5.2.** Read old absolutes literally. If “never change the terminology” was meant to protect product names, say “Keep product names verbatim.” Role descriptions can also widen the task. Calling Claude the owner of a codebase can encourage unrelated cleanup even alongside a narrow edit request. Use a role only when its implied responsibility fits. [Anthropic prompting guidance](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)
