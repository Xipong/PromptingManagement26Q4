# GPT-6.2 Astra, GPT-6.2 Sol and Claude Fable 5.2

Use this reference when tuning these models or migrating an existing prompt. Start with the observed failure in the target harness. Apply the relevant change, then compare it on [representative tasks](evaluation.md).

## Choose a starting effort

| Model | Starting point |
|---|---|
| GPT-6.2 Sol | OpenAI recommends Sol at `medium` for most API workflows, including coding in an existing repository. Try higher effort when the task needs multiple rounds of testing or revision. |
| GPT-6.2 Astra | OpenAI recommends Astra for demanding engineering and analysis. `medium` is the GPT-6.2 migration guide's starting point for new integrations. Measure whether increased effort improves completion on hard tasks. |
| Claude Fable 5.2 | Start at the Claude API default `high`. Compare `medium` for interactive work (the default in Claude apps and Claude Code) or `low` for well-specified work. Try `xhigh` for demanding runs where a measurable gain would justify the cost. |

Compare effort within each model and use the platform's supported settings. Effort labels are provider-specific controls. [OpenAI model selection](https://developers.openai.com/api/docs/guides/model-selection) · [GPT-6.2 migration quickstart](https://developers.openai.com/api/docs/guides/latest-model?model=gpt-6.2-astra#gpt-6-2-astra-migration-quickstart) · [Fable effort guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2#calibrate-effort)

Released coding evaluations can help choose which variants to try. On FrontierCode 2.0, OpenAI reports Sol within 0.5 points of Astra at about one fifth of the cost, both at `max`. Anthropic reports 49.1% for Fable 5.2 versus 32.4% for Fable 5.1 at `xhigh`. Use each release's comparison to choose candidates for your own evaluation. [OpenAI release results](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [Anthropic release results](https://www.anthropic.com/claude-fable-and-mythos-5-2)

## GPT-6.2 Astra and Sol

- **Follow-through.** The shared guide covers both models. If the agent offers a next step it could take itself, spell out the intended result, the evidence that finishes the task and the decisions the user owns. Give it room to act on a reversible assumption and verify the outcome. Try the [agent prompt shape](../templates/prompt-shapes.md#tool-using-agent).
- **Astra writing.** Astra is more direct and concise by default than its predecessor. Revisit inherited brevity rules. Give the model the audience, the vocabulary to use and the detail the reader needs. After a long task, make the final report understandable on its own.
- **Coding and visual work.** Describe the repo conventions, behavior callers rely on and the regression that matters. Reuse existing code when it fits and choose checks that cover the change. For a visual deliverable, give a concrete reference and relevant typography and imagery, then inspect the rendered result.

[OpenAI GPT-6.2 prompting guidance](https://developers.openai.com/api/docs/guides/latest-model?model=gpt-6.2-astra#gpt-6-2-astra-prompting-best-practices)

## Claude Fable 5.2

Apply a change where the behavior originates. In the table, measurements describe Anthropic's experiments on specific workloads.

| Observation | What to try | What Anthropic observed |
|---|---|---|
| Stops with recoverable work left, especially at `low` or `medium` | Define completion and recovery. Name actions the agent can already take and when it needs a decision. Audit stale approval or retry rules in skills and persistent notes. | At `medium`, about half as many replayed coding sessions stopped with work they could have continued. Output tokens rose about 30%. |
| Copies code or makes changes beyond the requested scope | Give the agent explicit responsibility for the component when structural changes are in scope. For a focused fix, name the component and the behavior it must preserve. Review the diff against its summary when granting broad ownership. | An unqualified maintainer role raised consolidation from under 10% to about 75% on small coding tasks, with roughly 70–80% more output tokens and some unsolicited changes. A separate scope warning still left consolidation above 50%. |
| Spawns more workers than the task needs | Review standing delegation rules first. If needed, specify in the tool description the work worth delegating, the expected result and the cost. Budget for the parent to verify and integrate the result. | In a delegation-heavy setup at `high`, a description explaining the cost roughly halved subagent counts. |
| Goes quiet during interactive tool use | Check if the client renders progress-update thinking blocks. If supported, request `thinking.display: "updates"` with the documented beta header or use `"summarized"`. An appended turn-scoped reminder after several silent tool steps can help where the API supports it. | In tested coding sessions, a reminder roughly halved the longest silence with no noticeable time or token increase. Prompting for an opening update increased output tokens by about 20%. |

Revisit inherited instructions to think less or to treat previous answers as settled. Tune latency via effort. Test whether follow-up prompts still let the model correct prior mistakes. If the harness shows a large token budget in prompt text, compare runs with that text removed. Anthropic saw lower cost with equivalent performance on tested coding tasks at `high` and `xhigh`.

[Anthropic Fable 5.2 prompting guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)

## When the application builds the requests

| API | Migration check |
|---|---|
| OpenAI Responses with GPT-6.2 | Put stable developer guidance in the first `input` message with role `developer`. Top-level `instructions` follows `input` and suits guidance for the current request. Keep earlier input stable and append updates. Prefix edits and certain model changes can drop prior reasoning items. |
| Anthropic Messages with Fable 5.2 | Keep `system`, `tools` and earlier messages stable within a conversation, and replay assistant blocks in their original order. A prefix mismatch can produce HTTP 400. Roll out changed baseline instructions in new conversations, or append new guidance using a supported message mechanism. Use supported compaction or context editing for long histories. |

Trace a real multi-turn request when diagnosing lost reasoning or cache reuse. Compare the serialized input, measure cached input and output where reported, and record whether the agent repeats work. [OpenAI GPT-6.2 API changes](https://developers.openai.com/api/docs/guides/latest-model?model=gpt-6.2-astra#gpt-6-2-astra-whats-new) · [Anthropic Fable 5.2 API changes](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2#editing-earlier-turns-invalidates-thinking-blocks)
