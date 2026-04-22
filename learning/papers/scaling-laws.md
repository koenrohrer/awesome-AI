# Scaling laws (Kaplan 2020 + Chinchilla) `[paper]`

## One-sentence TL;DR

Two papers established that LLM performance scales predictably with compute, data, and parameters — and Chinchilla corrected an early mistake about the right ratio, showing that most models of the era were under-trained on data.

## Citations

- Kaplan, J., McCandlish, S., Henighan, T., Brown, T. B., Chess, B., Child, R., Gray, S., Radford, A., Wu, J., & Amodei, D. (2020). *Scaling Laws for Neural Language Models.* [arxiv.org/abs/2001.08361](https://arxiv.org/abs/2001.08361)
- Hoffmann, J., Borgeaud, S., Mensch, A., Buchatskaya, E., Cai, T., Rutherford, E., de Las Casas, D., Hendricks, L. A., Welbl, J., Clark, A., Hennigan, T., Noland, E., Millican, K., van den Driessche, G., Damoc, B., Guy, A., Osindero, S., Simonyan, K., Elsen, E., Rae, J. W., Vinyals, O., & Sifre, L. (2022). *Training Compute-Optimal Large Language Models.* NeurIPS 2022. "Chinchilla." [arxiv.org/abs/2203.15556](https://arxiv.org/abs/2203.15556)

## What Kaplan 2020 showed

Cross-entropy loss follows power laws in model size, dataset size, and training compute. The curves are smooth and predictable over many orders of magnitude. Prior to this, the expectation was much less regular — scaling was thought to be unreliable.

Kaplan's prescription: **under a fixed compute budget, scale parameters faster than data.** This guided GPT-3 and most 2020-era models.

## What Chinchilla 2022 corrected

Chinchilla ran a large set of training curves across different parameter/data ratios and found Kaplan's prescription was wrong: the compute-optimal policy is to **scale parameters and data roughly equally.** A 70B-parameter model trained on 1.4T tokens outperformed 175B-parameter models (like GPT-3) trained on less data.

Rule of thumb from Chinchilla: **~20 training tokens per parameter** for compute-optimal training.

## Why this still matters

- The Chinchilla ratio is what every frontier lab now trains toward (or past — modern frontier models intentionally over-train on data because inference cost dominates training cost at scale).
- The power-law framework is the lingua franca for reasoning about capability growth. "Emergent abilities" are a debated exception to the smooth-curve picture; see [learning/papers/](./) for that follow-up when it lands.
- Any argument about whether to train a bigger model or collect more data ultimately routes through these two papers.

## Read them when

- You're evaluating a lab's training plan.
- Someone claims a scaling breakthrough without citing these.
- You want to know why the sub-70B model you trained in 2023 didn't match a 2020-era 175B — usually, data.

## Status

`[paper]`.
