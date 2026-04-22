# Tests

`[tested]` entries live here. Each test is a self-contained directory:

```
prompting/tests/<slug>/
├── README.md      # what the test measures, model(s) used, prompt(s), date
├── baseline.md    # the prompt + full output without the technique applied
└── treatment.md   # the prompt + full output with the technique applied
```

## What a test is *not*

- A benchmark. These are not statistically significant runs — they're worked examples showing the technique in action on one specific task.
- A certification. A `[tested]` badge means a maintainer reproduced the effect on at least one case; it does not mean the technique always works.

## Writing a test

1. Pick one specific task the technique should help with.
2. Run the baseline (without the technique). Save `baseline.md` with the exact prompt and full output.
3. Run the treatment (with the technique). Save `treatment.md` similarly.
4. Write `README.md` stating:
   - Model + version used
   - Date of run
   - One sentence on what the comparison shows
   - Any caveats (flakiness, one-shot-only, etc.)

## Status

No test directories yet. This is the seed of the `[tested]` track.
