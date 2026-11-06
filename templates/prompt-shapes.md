# Prompt shapes

Adapt these outlines to the task. Fill in facts from the available material and choose the detail needed for the receiving model.

## Tool-using agent

```text
Goal: <the result wanted and its purpose>.
Context: <primary input, observed behavior, relevant sources or entry point>.
Requirements: <what matters, including behavior to preserve and resource limits>.
Done means: <a useful result and how to recognize it>.
Deliver: <the artifact and evidence needed to review it>.
Choose an effective approach. Use the available tools and feedback to work
through the task; ask about user-owned decisions that materially change it.
```

For a clear small task, a direct sentence may carry everything needed.

## Single-shot generator

```text
Create <artifact> for <purpose>.
Facts and context: <relevant supplied material>.
Available capabilities: <operations, meanings and dependencies>.
Return <output contract>.
Aim for <quality criteria>, using <the creative freedom relevant to the task>.
```

Supply the context the generator needs to answer. Request explanations when they help a person or downstream stage use the result; use the consuming system to check executable behavior.

## Improve an existing prompt

```text
Improve <instruction or skill> for <goal or observed problem>.
Context: <current prompt, representative outputs and relevant consumers>.
Keep <actual requirements>; reconsider <the part we want to improve>.
Find what helps or obstructs the goal, including the effect of the combined
instructions. Fix the cause, changing the wording or structure as needed.
Deliver a usable revision and check it with evidence appropriate to the task.
```

Add particular model, budget or output requirements when they matter to this job.

## Reusable skill

Give the skill a clear trigger, useful knowledge, the decisions it helps with and routes to specialized material. Keep the main workflow understandable on its own. Put detailed procedures, examples and templates where the agent can load them for the relevant task.
