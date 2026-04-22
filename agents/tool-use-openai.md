# Function calling / tool use (OpenAI) `[provider-doc]`

## One-sentence pitch

OpenAI's function-calling (now unified under "tools" in the Responses API): declare tools with JSON schemas, the model emits tool calls conforming to the schema, your code executes and returns results, the loop continues.

## Evidence

- **Primary docs:** [Function calling — OpenAI docs](https://platform.openai.com/docs/guides/function-calling)
- **Responses API:** [Tools — OpenAI docs](https://platform.openai.com/docs/guides/tools)
- **Built-in tools:** [web_search, file_search, code_interpreter, computer-use](https://platform.openai.com/docs/guides/tools) — provider-hosted tools that the loop can call without your implementing them.

## The shape

```jsonc
// Request
{
  "model": "gpt-...",
  "tools": [
    {
      "type": "function",
      "function": {
        "name": "get_weather",
        "description": "Return current conditions for a location.",
        "parameters": { /* JSON Schema */ }
      }
    }
  ],
  "input": [...]
}

// Response contains tool_calls — reply with tool-result items and loop.
```

## Practical rules the docs emphasize

- **Strict mode.** Setting `strict: true` on the function forces schema conformance at decoding time (same mechanism as Structured Outputs). Use it.
- **Descriptions are the router.** The model picks tools based on description; vague or overlapping descriptions cause miscalls.
- **Parallel tool calls** default to on. Return all results before looping.
- **Reasoning model interaction.** When using o-series models, tool-call orchestration happens alongside extended reasoning — the token budget for reasoning and tool-call planning is shared.
- **Hosted tools are different.** `web_search`, `file_search`, `code_interpreter`, and computer-use are executed by OpenAI's infrastructure, not yours. Cost and latency characteristics differ from user-defined functions.

## Related to

- `agents/react.md` — the underlying loop pattern.
- `agents/tool-use-anthropic.md` — the equivalent on Claude; the schema and loop are conceptually identical, the field names differ.
- `prompting/structured-output.md` — function calling shares the schema-constrained generation mechanism.

## Status

`[provider-doc]`.
