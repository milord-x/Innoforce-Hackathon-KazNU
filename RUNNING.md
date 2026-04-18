# Running the Innoforce Submission Locally

This repository stores the team submission and a sample local command for the competition container.

## Expected inputs

- Docker installed locally
- `my_solution.py` available in the repository root
- API key exported into `GEMINI_API_KEY`

## Example run

```bash
docker run -v "$PWD/my_solution.py:/app/solution.py" \
  c0rp/innoforce.kz:sec-guard-latest \
  --hook /app/solution.py \
  --api-key "$GEMINI_API_KEY"
```

## What to verify

- the hook file is mounted into `/app/solution.py`
- the container starts in live mode
- safe prompts still pass
- jailbreak and leakage prompts are blocked

## Notes

The repository is best treated as a competition artifact and reproducibility snapshot rather than a long-lived product codebase.
