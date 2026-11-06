# Creating and repairing prompts

Use the parts that fit the actual failure or task. The sequence below expresses dependencies, not a requirement to produce a report at every step.

## Create: start with the job

Identify what the receiving model must produce and what it can actually do. A tool-using agent, fixed multi-stage pipeline and one-shot generator have different means of satisfying a request. Give each stage its own inputs, decisions and output contract; do not let a stage promise work owned elsewhere.

Write a compact brief containing what the task needs:

- **Goal and purpose:** the behavior or artifact wanted and the reason relevant trade-offs matter.
- **Primary material:** authoritative inputs, evidence and tool access; mark observations, assumptions and unknowns separately.
- **Contract:** required output, valid operations, units, relevant bounds, permissions and preserved behavior.
- **Acceptance:** an observable result, or a human-quality rubric when no deterministic oracle exists.
- **Autonomy boundary:** what can be chosen independently and which unresolved decisions truly need the user.

Do not make the user fill a form when the repository or supplied material already answers it. Ask when the missing decision changes scope, cost, irreversible effects or the desired product. When a noisy request is easy to misunderstand, a brief readback can expose assumptions; it is not a mandatory approval stop for clear routine work.

The optional [prompt shapes](../templates/prompt-shapes.md) are starting points, not compulsory headings.

## Supply knowledge, not a performance of reasoning

Describe real operations at their source of authority. A useful capability card says what the operation does, its inputs/units, relevant conditions and its effects. Put a cross-field dependency where a reader can discover it while making that choice. Optional individual fields may still participate in an obligatory alternative; explain the alternative rather than prescribing one arbitrary option.

For an existing parent, document supplied facts faithfully. For a newly authored object, explain the available creative space. Do not allow a broad 'use only source-backed facts' sentence to turn all invention into prohibited behavior.

Use schema or typed validation for shape and enforceable invariants. Use prose for purpose, meaningful choices and semantics the schema cannot express. Avoid maintaining contradictory copies of the same contract. A validator rejecting an answer does not prove that the model was told a usable contract.

Examples should clarify an actual ambiguity: units, syntax, scope or a difficult boundary. Use diverse minimal examples when one would anchor every answer to the same design. Do not replace domain knowledge with a list of imagined failure warnings.

## Repair: classify the evidence before editing

Obtain a representative failure and, where relevant, a successful control. Inspect the actual messages and effective output format at the sender boundary, not just a source template. Read additional stages only when they participate in the suspected mechanism.

| Observation | Appropriate owner or response |
|---|---|
| A necessary fact never reaches the model | Fix retrieval, projection or stage input; a reminder cannot recover absent data. |
| The instruction disagrees with the consumer | Correct the canonical contract and its projections; do not invent a workaround in another stage. |
| Two instructions pull in different directions | Resolve authority and remove the conflict at its owner. Check higher-priority/global text as well as the local sentence. |
| Repeated global rules discourage useful choices | Explain the intended trade-off, preserve the real boundary, and remove cumulative pressure toward an easy but unhelpful answer. |
| The requested operation is unavailable | Expose the actual capability gap; implement it only within scope or revise the task with the user. |
| The answer violates an adequate contract once | Record a model error; do not automatically add another duplicate prohibition. |
| The output is valid but unhelpful | Improve the objective or acceptance criteria; inspect product quality rather than polishing the self-report. |
| The model spends time on irrelevant ceremony | Narrow the trigger or condition; remove the obligation if it does not affect the requested outcome. |

Distinguish a diagnosed instruction defect from a hypothesis about model behavior. Another reader understanding the text is useful evidence, not proof that the original wrong answer is acceptable or that all models will understand it.

## Make the smallest coherent repair

Change the instruction that owns the problem and its active duplicated projections. Preserve exact identifiers, units, permissions, valid alternatives and expressive capacity. Where separate task branches need different guidance, route to the right branch instead of accumulating exceptions in the root.

When an error recurs, prefer a better interface, type, diagnostic or automatic check when it can eliminate the mechanism. Do not remove still-useful explanatory prose merely because an invariant is enforced. Avoid writing a new 'never do X' rule for every historical incident.

### Illustrative transformations

These are invented examples, not measured before/after results or required production text.

**Procedure-heavy:** 'Always inspect every module, propose three options, run all tests and obtain an independent review.'

**Outcome-oriented:** 'Fix the duplicate record on retry while preserving ordinary delivery. Use the relevant producer and persistence boundary to demonstrate that the same logical operation creates one record. Broaden verification if the change crosses another contract.'

**Over-restrictive generation:** 'Never invent anything absent from the source items; always produce the simplest design.'

**Separated authority:** 'Treat supplied source-item properties as facts. Compose a new useful design from supported operations; source facts do not require copying either parent's mechanics. Choose complexity that serves the goal, and accurately describe the behavior you author.'

**Vague compression:** 'Make the prompt as short as possible.'

**Preserving meaning:** 'Remove repetition and irrelevant instructions while preserving every supported operation, necessary parameter, unit, condition and valid composition. Report size and behavioral evidence separately.'

## Check only the claim you need

For prose-only work, compare the old and new meaning and the affected rendered/serialized surface. A structural check establishes syntax or contract preservation, not improved quality. Replay can establish compatibility of saved examples, not fresh model understanding.

If the remaining question is behavioral and a run is authorized, use the matched-task protocol in [Evaluation and metrics](evaluation.md). Preserve the original failure and unknowns. Stop when the defect is repaired and the requested claim has adequate support; do not keep simplifying clear text to reach a size target.
