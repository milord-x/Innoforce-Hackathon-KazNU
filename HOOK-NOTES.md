# Hook Behavior Notes

`my_solution.py` implements two stages:

- `input_hook` decides whether the user prompt is allowed to reach the model
- `output_hook` checks the model response for direct or disguised leakage

## Input-side strategy

The hook blocks requests that look like:

- prompt injection attempts
- system prompt extraction
- secret or password fishing
- obfuscation through encoding, reversal, translation, or spelling tricks
- common jailbreak phrasing in multiple languages

## Output-side strategy

The output hook blocks:

- direct password leakage
- reversed password leakage
- encoded variants when they match known transforms
- heavily overlapping fragments that reconstruct the protected value

## Why this file exists

The submission code is compact and tuned for the competition harness. These notes make the intent easier to understand without changing the behavior of the hook itself.
