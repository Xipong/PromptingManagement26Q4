# Optional prompt shapes

Use only the slots needed for the task. Fill recoverable facts from authoritative material instead of asking the user to supply them again. These shapes do not override the receiving platform's roles or tool contract.

## Tool-using agent

```text
Goal: <the behavior or artifact wanted, and why if relevant>.
Starting evidence: <primary input, observed symptom, source or entry point>.
Preserve: <existing behavior, exact contracts and resource boundaries>.
Done means: <observable result or artifact-level acceptance>.
Provide: <the evidence needed to accept the result, not a process diary>.
Choose the implementation within these boundaries. Ask only for unresolved
user-owned decisions that materially change the outcome, scope or cost.
```

A clear small request can be one sentence. The template is not a demand to make every user prompt longer.

## Single-shot generator

```text
Create <artifact> for <purpose>.
Use these authoritative facts: <facts, with unknowns kept explicit>.
Available choices and their meanings: <capabilities, units and dependencies>.
Return <output contract>.
A good result <quality criteria and allowed creative freedom>.
```

Do not ask a one-shot generator to inspect unavailable files, execute tests or certify runtime behavior. If explanations are useful downstream, request them for that purpose rather than treating a self-evaluation as proof.

## Repair an existing prompt

```text
Improve <the actual instruction surface> for <observed failure>.
Evidence: <failed example, relevant success/control, effective request>.
Preserve <capabilities, facts, contracts and permissions>.
Determine whether the defect belongs to wording, input data, a conflicting
instruction, an interface/capability, or evaluation. Change the owning
mechanism within scope; do not just add a warning for the example.
Deliver the revised prompt and the evidence available for the claimed change.
<Explicit model-run budget and route, only if a live comparison is authorized.>
```

## A reusable skill entry

Describe a narrow trigger, what knowledge or procedure the skill contributes, critical invariants and routes to optional depth. Put task history, benchmark receipts and long special cases outside the root. Retain enough actual guidance to choose and perform the ordinary case; do not reduce the skill to an unexplained link index.
