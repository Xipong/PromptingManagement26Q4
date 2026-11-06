# Evaluation and metrics

Choose measurements that help decide whether an instruction improves the task. A small wording edit may need inspection; a change to behavior is best judged on representative work.

## Define the outcome

Start with the result the user wants. Separate output validity, semantic correctness and product quality where they answer different questions. For example, a generated program can compile while implementing the wrong behavior.

Name the revision being tested, the tasks it should help and the trade-off that matters. Keep the user's requirements and resource limits in effect throughout the comparison.

## Choose useful measures

Select a primary outcome and supporting measures for the decision.

| Measure | Definition | Record alongside it |
|---|---|---|
| Accepted completion | Accepted tasks divided by all launched tasks under the declared acceptance rule. | Counts and reasons for rejected, failed and unresolved tasks. |
| Human correction burden | Corrective interventions and recorded human time. | Preference clarifications separately from corrections of mistakes. |
| False completion | Claimed completions that fail acceptance divided by all claimed completions. | Accepted/launched counts, so frequent refusal remains visible. |
| Cost per accepted result | Cost of all attempts divided by accepted results. | Failures, repairs and retries; tokens, money and human time in their own units. With no accepted result, report total spend and zero accepted results. |
| Time to accepted result | Time from task start to verified completion. | Completion-by-deadline, timeouts and unresolved cases beside completed-run quantiles. |
| Semantic or product quality | Rubric scores or blinded pairwise judgments of the artifact. | Criteria such as useful behavior, factual accuracy, clarity and design quality. |
| First-pass validity and repair | Initial valid answers divided by authentic initial answers; repair incidence and success separately. | Transport failures, shape failures, semantic failures and any project-specific repair boundaries. |

Use context size, skill selection, repeated tool actions and cache reuse to diagnose the process. Measure tokens from provider usage or a named tokenizer on the actual input. Measure time on the complete path the user waits for, with stage timing available to locate bottlenecks.

For creative tasks, include meaningful variety and the quality of the chosen design. Judge complexity by how it serves the result. For executable outputs, compare the description with the behavior of the actual consumer.

## Compare variants

Run current and proposed instructions on matched tasks, holding model, settings, tools, inputs and starting conditions fixed except for the treatment. A no-skill or simpler-prompt arm can help establish what the added instructions contribute.

Cover the original failure, normal work and nearby cases. For a reusable skill, include a case outside its trigger. Reserve some cases from repeated editing when tuning risks overfitting.

Give candidates ordinary task requests. Keep gold answers, preferred variant labels and evaluator-only notes with the evaluator. Present outputs under neutral labels and vary their order when judging may be order-sensitive. Check recorded actions when tool or skill use matters to the result.

Repeat or interleave runs when sampling variation, provider load, warmup or cache state affects the comparison. Report case counts, paired differences and variability. Treat repeated runs of the same task as related observations. If the observed gap is within ordinary variation, gather more evidence when the decision warrants it or report the comparison as inconclusive.

Choose the sample size and evaluation depth for the decision and available budget. Follow any applicable project acceptance requirements.

## Keep interpretable evidence

Record task and variant identity, the effective prompt/settings, output, outcome reason, attempts, time and available usage. Preserve initial failures after recovery and label saved-output replay as replay. Missing counters remain unknown.

Verify that the timed work ran and produced the intended output. For a subscription route priced at API rates, label the amount as an API-equivalent calculation. A combined change to the model, input data and prompt measures that combined treatment.

## Decide and report

Choose the revision that delivers the best task outcome within the relevant cost and quality constraints. Explain the trade-off with the observed results. Report the comparison, sample size and main finding; include unresolved issues when they affect the decision.
