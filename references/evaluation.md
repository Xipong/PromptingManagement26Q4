# Evaluation and metrics

Use this reference when a decision depends on whether a prompt or skill changes outcomes. It does not authorize model calls or require an experiment for each prose edit.

## Define success before comparing variants

Choose a primary outcome that represents the user's goal. Keep mechanical validity, semantic correctness and human/product quality distinct. A build, schema-valid answer or fluent explanation can pass while the requested behavior fails.

Write down the treatment, the tasks it should help and the result that would change your decision. Preserve real permissions and safety/contract boundaries across all variants, including any no-skill baseline. An evaluation is not permission to remove restrictions that protect the user's resources or data.

## A small useful measurement panel

| Measure | Definition | Interpretation boundary |
|---|---|---|
| Accepted completion | Accepted tasks divided by all launched tasks under the declared acceptance rule. | Retain rejection reasons, infrastructure errors and unknowns; do not silently select successful outputs. |
| Human correction burden | Corrective interventions and, when actually recorded, human minutes. | Separate necessary preference clarification from correction of agent mistakes. Do not infer minutes from message count. |
| False completion | Claimed completions that fail acceptance divided by all claimed completions. | Also report the number accepted/launched so cautious refusal cannot look like high overall quality. |
| Cost per accepted result | Total observed cost of all attempts divided by accepted results. | Include failures, repair and retries; show tokens, money and human time separately. With no accepted result the ratio is undefined, not zero. |
| Time to accepted result | End-to-end time from task start to verified completion. | Show completion-by-deadline and timeout/unresolved counts alongside completed-run quantiles; do not hide long failures. |
| Semantic/product quality | Separate rubric scores or blinded pairwise judgments for the actual artifact. | Judge useful behavior, factual accuracy and fitness for purpose, not prose length or feature count. Calibrate a model judge against concrete controls and human disagreements. |
| First-pass validity and repair | Initial valid answers divided by authentic initial answers; repair incidence and repair success separately. | Distinguish transport failures with no answer, syntax/shape failures and semantic failures. Respect any bounded/frozen repair contract the target actually has. |

Treat loaded-context size, irrelevant skill loads, redundant tool actions and cache reuse as diagnostics, not primary success metrics. Measure the actual input envelope with a named tokenizer or observed provider usage when claiming tokens. Character counts are not token counts; a shorter static prompt is not an observed reduction in total task cost.

For creative generation, inspect diversity and intended freedom alongside usefulness. More effects or novelty is not automatically better. A rigid novelty score can penalize a deliberately simple, appropriate design. For a runtime pipeline, compare claimed behavior with what its consumers can execute; textual self-checks are not execution evidence.

## Match the experiment to the decision

For a substantial behavior change, compare the current and proposed instructions on the same representative tasks. An optional no-skill arm helps determine whether the instruction contributes anything, but is not mandatory for every repair.

Keep model/version, effort, tools, task inputs and initial environment equal except for the declared treatment. Include the original failure, adjacent cases, normal work and a task where the skill should not trigger. Hold some cases out of the editing loop when repeated tuning risks overfitting.

Use ordinary-looking task requests. Do not tell candidates which variant is preferred or leak the evaluator's private rubric, gold answer or other candidates' outputs. Label results neutrally for judging and vary presentation order when order effects are plausible. Verify tool/skill use from recorded actions, not self-reported compliance.

Repeat cases when stochastic variation matters, within the authorized budget. Match or interleave runs where provider load, warmup or cache state can change. A small pilot identifies issues; it does not establish a universal win. Report paired differences and sample counts; use task-level uncertainty estimates when there is enough data, treating repeats of one task as related rather than independent tasks. If the observed difference is within ordinary variability, call it inconclusive.

Do not turn an operational checklist from another benchmark into an arbitrary minimum sample size. A required publication, acceptance campaign or project gate can impose its own justified protocol.

## Record enough to make the result interpretable

Use the existing evidence owner. Keep task/variant identity, source and effective settings, input/output provenance, terminal outcome, acceptance reason, actual attempts, timing and authoritative usage when available. Keep missing counters unknown. Preserve original failures after recovery and source-bound saved outputs; do not count replay as new inference.

For latency, verify that the intended work happened inside the timed region and that outputs were correct. Distinguish per-stage and end-to-end results. For API-equivalent pricing on a subscription route, label the calculation as a comparison, not a bill or evidence about API latency.

## Decide and report

Prefer a variant that improves the selected outcome without violating the real constraints, or preserves quality with a useful reduction in complete cost. There is no universal percentage threshold: agree the trade-off appropriate to the task. A smaller prompt that loses capabilities is not equivalent optimization.

Report the objective, actual comparison, denominator, main result and limitations. Separate observed improvement from plausible explanation; a joint change to prompt, data and model does not isolate a prompt effect. Do not launch extra calls just to repair a local reporting error.
