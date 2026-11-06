# Creating, auditing and improving prompts

## Create: understand the job

Identify what the model should achieve, who will use the result and what the execution environment provides. A tool-using agent can inspect and act; a single-shot generator works from the context supplied to it. In a pipeline, give each stage clear inputs, decisions and outputs.

Build the prompt from the information that matters:

- **Goal:** the behavior or artifact wanted and the purpose behind it.
- **Context:** primary material, relevant background, available tools and capabilities.
- **Requirements:** output shape, important semantics, units, dependencies and user constraints.
- **Quality:** what makes the result useful, accurate or well designed for this task.
- **Judgment:** choices the model can make and decisions that need the user's preference.

Recover facts from the available material. Ask about a missing preference when it materially changes the result. For a noisy or ambiguous request, briefly state your understanding so a misunderstanding is easy to correct; continue clear work using the context already available.

For exploratory work, describe the question and useful evidence the model should seek. Let it refine an approach as it learns. Use the [prompt shapes](../templates/prompt-shapes.md) when a starting outline helps.

## Give the model useful context

Describe capabilities in terms the receiving model can use: what an operation does, what its parameters mean, and which dependencies affect a valid choice. Put coupled field requirements near the relevant fields. Keep the schema and prose consistent with the consumer.

Separate facts about existing material from choices about a new artifact. A model can faithfully use supplied facts while inventing a new design, explanation or composition. Say which freedoms serve the task.

Use examples to show quality, format, style or subtle semantics. A worked example can communicate more than a page of rules. Where several designs are acceptable, show or describe that range so the model understands which parts of the example matter.

Choose the amount of detail for the model and task. Concrete steps help with fragile tool sequences or domain procedures; a clear goal and context often suffice for familiar work. Revisit old scaffolding when the model, tools or task changes.

## Audit: read the instructions as the receiving model

For an application, inspect the effective messages, supplied context and output format. For a reusable skill, include the references and examples its trigger leads the model to read.

Ask what behavior the complete instruction set encourages:

- Is the intended result clear enough to guide decisions?
- Can the model discover the facts and capabilities it needs?
- Which choices are genuinely constrained, and which remain open?
- Do global rules conflict with local instructions or examples?
- Is there an easy compliant answer that misses the user's goal?
- Does the prompt reward useful work, or time spent proving compliance?

Follow the instruction and data flow far enough to understand the cause. Compare an actual weak result with a successful example when available. Also review prompts that already work when the goal is clearer wording, a different style, better quality or a more capable workflow.

## Locate the cause

| Observation | Useful response |
|---|---|
| Necessary context is missing | Improve retrieval, projection or the stage input. |
| The instruction disagrees with the consumer | Reconcile the contract at its owner and update affected projections. |
| Instructions conflict | Resolve their authority and remove the conflicting requirement. |
| The model chooses a technically valid but weak answer | Clarify the purpose, quality criteria and available design space. |
| The model performs irrelevant steps | Remove or narrow the obligation that triggers them. |
| A needed operation is unavailable | Find another effective approach or extend the capability within the task's scope. |
| A failure occurs despite apparently clear instructions | Inspect the example, model settings, tools and surrounding context before choosing a remedy. |
| The same error keeps recurring | Consider a better interface, data structure, diagnostic or automated check alongside prompt changes. |

Choose the remedy from the evidence. A prompt rewrite, an input fix and an interface improvement solve different problems.

## Improve at the right scope

Fix a local ambiguity locally. Rewrite the structure when accumulated rules obscure the goal or restrict useful solutions. Remove obsolete requirements and combine duplicated ones; keep the domain knowledge and choices the task still needs.

Identify what must remain stable and what the user wants changed. For behavior-preserving edits, retain the supported operations, units and meaningful conditions. For a contract redesign, change the prompt, validation and consumers together so the new design is coherent.

Give each durable rule a clear owner. Shared facts belong where their users can discover them; branch-specific detail belongs with that branch. Keep useful examples and explanations even when some invariants are enforced by code.

Write instructions and documentation directly. Explain an actual limitation where it affects a decision; use the rest of the space to help the reader do the work.

## Examples

### Replace a fixed itinerary with an outcome

Before:

> Always inspect every module, propose three options, run all tests and obtain an independent review.

After:

> Fix the duplicate record on retry while preserving ordinary delivery. Demonstrate that repeating the same logical operation creates one record. Choose the investigation and checks that cover the affected behavior.

### Open the creative space

Before:

> Never invent anything absent from the source items; always produce the simplest design.

After:

> Use the supplied item properties as facts. Create a useful new design from the available mechanics, drawing on both source identities. Choose the complexity that serves the result and describe what the design does.

### Give a compression request a meaningful target

Before:

> Make the prompt as short as possible.

After:

> Make the prompt easier to understand and use. Remove repetition and irrelevant guidance while retaining the capabilities, meanings and choices needed for the task.

## Check the result

Inspect the changed prompt as it will be received. Check meaning, examples, output shape and any affected consumers. For a behavioral question, try representative tasks and compare their results using [Evaluation and metrics](evaluation.md).

Keep the comparison tied to the change you made. If a result exposes another cause, follow that evidence and improve the solution. Finish with a usable prompt and the checks relevant to its purpose.
