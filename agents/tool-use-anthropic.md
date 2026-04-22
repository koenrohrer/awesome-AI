# Tool use (Anthropic / Claude) `[provider-doc]`

## One-sentence pitch

Claude's structured tool-use API: you declare tools with JSON input schemas, the model emits `tool_use` blocks conforming to the schema, your code executes them and returns `tool_result` blocks, and the loop continues until Claude produces a final text response.

## Evidence

- **Primary docs:** [Tool use — Claude docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use)
- **Agent SDK:** [Claude Agent SDK](https://docs.anthropic.com/en/api/agent-sdk/overview) — higher-level SDK that wraps the tool-use loop with session management, memory, and built-in tools.

## The shape

```jsonc
// Request
{
  "model": "claude-...",
  "tools": [
    {
      "name": "get_weather",
      "description": "Return current conditions for a location.",
      "input_schema": { /* JSON Schema */ }
    }
  ],
  "messages": [...]
}

// Response contains one or more tool_use blocks:
{ "type": "tool_use", "id": "toolu_01...", "name": "get_weather", "input": {...} }

// Reply with tool_result blocks referencing the id, then loop.
```

## Practical rules the docs emphasize

- **Schemas are the contract.** Whatever you declare in `input_schema` is what the model will conform to. Be strict — narrow schemas, enums where possible, required fields marked required.
- **Tool descriptions matter.** Claude uses the description to decide *when* to call each tool. Vague descriptions lead to misrouted calls.
- **Parallel tool use** is supported — Claude can emit multiple `tool_use` blocks in one response when calls are independent. Execute them in parallel and return all results before looping.
- **`tool_choice` controls behavior.** Force a specific tool, disable tools, or leave the default "auto."
- **Prompt cache the tool definitions.** If your tool set is stable across calls, mark the `tools` block as cacheable — it's often the largest repeated chunk in an agent loop.

## Related to

- `agents/react.md` — the pattern the tool-use loop implements at API level.
- `prompting/structured-output.md` — tool use is the canonical structured-output path on Claude (more reliable than ad-hoc JSON prompting).
- `prompting/prompt-caching.md` — caching tool definitions cuts agent-loop cost dramatically.

## Status

`[provider-doc]`.
