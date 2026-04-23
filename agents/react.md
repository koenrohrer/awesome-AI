# ReAct: Reasoning + Acting `[paper]`

## One-sentence pitch

Interleave reasoning (thought) and action (tool call) in the same loop — the model produces a Thought, takes an Action, observes the Observation, and repeats until done. The pattern underlies most modern tool-using agents.

## Evidence

- **Primary citation:** Yao, S., Zhao, J., Yu, D., Du, N., Shafran, I., Narasimhan, K., & Cao, Y. (2022). *ReAct: Synergizing Reasoning and Acting in Language Models.* ICLR 2023. [arxiv.org/abs/2210.03629](https://arxiv.org/abs/2210.03629)

## What the paper shows

On HotpotQA, FEVER, and ALFWorld, interleaving reasoning traces with actions outperforms either pure reasoning (CoT) or pure acting. The reasoning steps let the model plan what tool to call next; the observations from tool calls ground the reasoning in real state.

## The loop

```
Thought: <why I'm about to do this>
Action: <tool name + args>
Observation: <tool output>
Thought: ...
Action: ...
Observation: ...
...
Final Answer: ...
```

Every frontier-model tool-use API (Anthropic, OpenAI, Google) is a structured version of this loop.

## Practical rules

- **Make thoughts a first-class field.** Giving the model a dedicated "thinking" slot per step beats cramming reasoning into the action arguments.
- **Keep the observation concise.** A 10k-token tool response pollutes every subsequent loop step's context. Summarize or index.
- **Bound the loop.** Set a max step count. Otherwise a confused agent will thrash indefinitely.
- **Separate "plan" from "act" prompts when deep.** For deep task trees, a ReAct step that kicks off a planner subprocess outperforms one flat loop.

## Known failure modes

- **Premature conclusion.** Model decides it has the answer before enough tool calls.
- **Tool-call loops.** Same action taken repeatedly because prior observations weren't retained.
- **Reasoning drift.** Long thoughts that don't commit to a next action.

The hardening patterns for these failure modes deserve their own entries — they belong in a future hardening pass.

## Related entries

- `agents/toolformer.md` — a training-time alternative where tool calls are learned rather than prompted.
- `agents/reflexion.md` — adds a self-reflection phase after failures.
- `agents/tool-use-anthropic.md`, `agents/tool-use-openai.md` — provider-doc implementations of the ReAct loop.

## Status

`[paper]`.
