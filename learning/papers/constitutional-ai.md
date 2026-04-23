# Constitutional AI (CAI) `[paper]`

## One-sentence TL;DR

Replace most of the human preference labeling with an AI feedback loop: write a short set of principles ("a constitution"), have the model critique and revise its own responses against them, and train on the result. Scales alignment without scaling human labelers.

## Citation

Bai, Y., Kadavath, S., Kundu, S., Askell, A., Kernion, J., Jones, A., Chen, A., Goldie, A., Mirhoseini, A., McKinnon, C., Chen, C., Olsson, C., Olah, C., Hernandez, D., Drain, D., Ganguli, D., Li, D., Tran-Johnson, E., Perez, E., Kerr, J., Mueller, J., Ladish, J., Landau, J., Ndousse, K., Lukosuite, K., Lovitt, L., Sellitto, M., Elhage, N., Schiefer, N., Mercado, N., DasSarma, N., Lasenby, R., Larson, R., Ringer, S., Johnston, S., Kravec, S., El Showk, S., Fort, S., Lanham, T., Telleen-Lawton, T., Conerly, T., Henighan, T., Hume, T., Bowman, S. R., Hatfield-Dodds, Z., Mann, B., Amodei, D., Joseph, N., McCandlish, S., Brown, T., & Kaplan, J. (2022). *Constitutional AI: Harmlessness from AI Feedback.* Anthropic. [arxiv.org/abs/2212.08073](https://arxiv.org/abs/2212.08073)

## The pipeline

1. Start with an SFT'd helpful model.
2. Generate responses to harmful prompts.
3. Have the model **critique its own response** against a constitution (a list of principles like "the response should not contain harmful content" or "prefer the response that is most helpful given the constraints").
4. Have the model **revise** based on the critique.
5. Train a **preference model** on (original, revised) pairs — the AI provides the preference signal in place of human labelers.
6. Run an RLHF-style loop using this AI-generated preference data — "RLAIF" (RL from AI Feedback) — alongside the human preference data collected for helpfulness.

## Why it mattered

- **Scalability of oversight.** Human preference labeling is the bottleneck in RLHF. CAI shifts most of the harmlessness labeling load to the model itself, making it feasible to iterate faster on a model's behavior profile.
- **Transparency.** The "constitution" is a human-readable document. This makes it easier to describe *why* a model behaves a certain way — the principles are explicit and auditable, rather than emergent from anonymous labeler preferences.
- **Template for successors.** The pattern "have the model critique its own output" underpins many subsequent training pipelines, including Anthropic's later iterations and related work at other labs.

## Caveats

- **The constitution is still authored by humans** — bias and value choices move from labelers to principle authors, not away.
- **Model-generated feedback inherits model limitations.** If the model has blind spots, those propagate through the self-critique loop.
- **Helpfulness often still relies on human labels.** The paper applies CAI primarily to harmlessness; helpfulness preferences were still human-labeled.

## Related entries

- `learning/papers/instructgpt.md` — the RLHF baseline CAI modifies.
- `learning/papers/dpo.md` — an alternative objective that can use CAI-generated preferences.
- `prompting/self-refine.md` — the inference-time analog of CAI's training-time critique-and-revise loop.

## Read it when

- You're designing an alignment pipeline and human labeling is a bottleneck.
- You want to understand why modern models give similar-but-differently-shaped refusals — constitutional-style training is one of the factors.

## Status

`[paper]`.
