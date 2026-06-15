# How to add AI to an existing workflow

## The Short Version

Start with the workflow, not the model. The useful question is where a model can remove a repeated decision, transformation, summary, or check from a process that already exists.

This section of the repository is still scaffolded. The integration primers define the intended surfaces, but curated integration entries are not mature yet. Use them as category boundaries, then borrow evidence from agent tool-use docs, safety entries, and vetted tools where they fit.

Prefer reversible, reviewable steps first: drafts, summaries, labels, triage notes, release-note candidates, or shell outputs that a human can inspect. Move toward side effects only after the routine has real examples and failure handling.

## Use This Guide When

Use this guide when you want AI inside an existing system: a CI pipeline, shell script, cron job, issue tracker, no-code flow, recurring report, or background automation. Opening a chat and pasting text is not an integration.

## Fast Path

- **[Integrations](../integrations/README.md)** — start with the section status and boundaries.
- **[Automations](../integrations/automations/README.md)** — use for recurring or trigger-based routines; entries are still planned.
- **[CI/CD integrations](../integrations/ci-cd/README.md)** — use for pipeline-native review, test, changelog, and release-note work; entries are still planned.
- **[Shell integrations](../integrations/shell/README.md)** — use for scripts, hooks, cron jobs, and terminal workflows; entries are still planned.
- **[Tool use (Anthropic / Claude)](../agents/tool-use-anthropic.md)** `[provider-doc]` — use a concrete schema protocol when the integration calls tools.
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]` — read before passing external content into an automated workflow.
- **[Hermes Agent](../tools/candidates/hermes-agent.md)** `[vetted-tool]` — inspect one local evidence trail for a vetted codebase-maintenance tool.

## Decision Points

Decide whether the integration is advisory or action-taking. Advisory flows can draft, classify, summarize, or suggest. Action-taking flows need permissions, audit logs, and rollback paths.

Decide where evidence will live. A serious integration should preserve inputs, model/tool outputs, human edits, and the final outcome so it can eventually qualify as `[tested]`.

Decide whether the host surface matters more than the AI component. CI/CD, shell, automations, and no-code flows fail in different ways, so the guide path should match the system that owns the trigger and side effects.

## Field Notes

Small automations are easier to trust. A daily digest, PR summary, or changelog draft gives you examples without giving the model authority over the system.

Tool schemas help integrations more than clever prose. If a workflow needs structured handoff, prefer provider tool-use or structured output over parsing free-form text.

Inputs are often untrusted. Webpages, issues, pull requests, emails, and chat messages can carry instructions that conflict with the workflow's actual policy.

The current integration area is not mature coverage. It is a scaffold for future `[tested]` recipes and `[vetted-tool]` entries.

## What To Avoid

Avoid claiming a workflow is proven because the model produced one good answer in chat.

Avoid hidden side effects. If an AI step can merge, deploy, send, delete, or bill, make the review point explicit.

Avoid adding bare integration entries. Until a candidate clears `[tested]` or `[vetted-tool]`, keep it out of the curated lists.

Avoid implying the repository already has complete integration coverage. The primers are useful boundaries, not mature catalogs.

## Evidence Library

- **[Integrations](../integrations/README.md)**
- **[Automations](../integrations/automations/README.md)**
- **[CI/CD integrations](../integrations/ci-cd/README.md)**
- **[Shell integrations](../integrations/shell/README.md)**
- **[No-code integrations](../integrations/no-code/README.md)**
- **[ReAct: Reasoning + Acting](../agents/react.md)** `[paper]`
- **[Tool use (Anthropic / Claude)](../agents/tool-use-anthropic.md)** `[provider-doc]`
- **[Tool use (OpenAI)](../agents/tool-use-openai.md)** `[provider-doc]`
- **[Indirect Prompt Injection](../learning/safety/indirect-prompt-injection.md)** `[paper]`
- **[Hermes Agent](../tools/candidates/hermes-agent.md)** `[vetted-tool]`
- **[OpenClaw](../tools/candidates/openclaw.md)** `[vetted-tool]`
- **[OpenShell](../tools/candidates/openshell.md)** `[vetted-tool]`
- **[Pi Agent](../tools/candidates/pi-agent.md)** `[vetted-tool]`
