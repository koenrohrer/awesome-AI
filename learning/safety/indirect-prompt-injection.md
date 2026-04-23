# Indirect Prompt Injection `[paper]`

## One-sentence TL;DR

When an LLM reads untrusted third-party content (a webpage, an email, a document), that content can contain instructions that hijack the model's behavior. This paper is the foundational framing of the threat; understanding it is prerequisite for building any agent that reads external data.

## Citation

Greshake, K., Abdelnabi, S., Mishra, S., Endres, C., Holz, T., & Fritz, M. (2023). *Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection.* AISec '23 workshop, CCS 2023. [arxiv.org/abs/2302.12173](https://arxiv.org/abs/2302.12173)

## Direct vs indirect injection

- **Direct prompt injection** — the *user* attempts to override system instructions ("ignore previous instructions and…"). This is the widely-understood version.
- **Indirect prompt injection** — a *third party* (whoever wrote the webpage, email, document, or database row the model reads) embeds instructions. The user is innocent; the data is the attacker.

Indirect injection is the strictly harder threat because the victim has no visibility into what the model ingests. Every retrieval-augmented app, every browser-using agent, every email-reading agent faces it.

## What the paper demonstrated

The authors show a spectrum of attacks across real LLM-integrated applications:
- Data exfiltration via prompt content exfiltrating conversation history to a third-party URL.
- Denial of service via content that causes the model to refuse legitimate requests.
- Phishing via content that causes the model to generate misleading output the user trusts.
- Information manipulation via content that biases summaries and answers.

All without the user typing anything adversarial.

## Why it's foundational

Every agent architecture now reckons with this threat. The fact that *the same tokens* are used for system instructions, user input, and tool-returned content means there's no cryptographic separation — trust is inferred from context and position, both of which are overridable by cleverly crafted content.

## Defensive directions (consolidated from the literature)

- **Never execute instructions from tool outputs without a trust boundary.** A returned webpage is data, not a command.
- **Sanitize or escape** untrusted content before it enters context (markers, visible/invisible character stripping, structure validation).
- **Use least-privilege tool access.** An agent that reads email should not also be able to send email without an independent confirmation step.
- **Output-side defenses.** Restrict what the model can emit (structured output, allowed URL domains, content filters) rather than trusting the input.
- **Monitor and log.** Agent actions should be reviewable post-hoc — detection complements (never replaces) prevention.

None of these are silver bullets. The field is open research.

## Related entries

- `learning/safety/gcg-attack.md` — universal adversarial prompts that can transfer across models.
- `learning/safety/jailbreak-failure-modes.md` — why safety training leaves gaps in the first place.
- `agents/react.md` — the agent-loop architecture where injection commonly bites.

## Status

`[paper]`.
