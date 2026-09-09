# jsonl-runner

Feed a thousand prompts, get a thousand answers

## Usage

```bash
python batch.py prompts.jsonl -o answers.jsonl --workers 4 --rpm 300
```

## What it does

- Idempotent: ids already in the output are skipped on a rerun
- Real rate limiting: sliding windows on requests/min and tokens/min
- A bad input line is logged and skipped, never fatal
- JSONL in, JSONL out: the input is streamed line by line
- 4xx fails fast; 429 and 5xx retry with jittered backoff
- Per-row overrides for model, system, temperature and max_tokens
- Failures go to a sidecar file with error type, message and status
- Progress, token counts and a cost estimate on stderr

## Installation

```bash
pip install -r requirements.txt
export OPENAI_API_KEY=sk-...
```

## Project structure

```text
├── .github/
│   ├── workflows/
│   │   └── ci.yml
│   └── dependabot.yml
├── docs/
│   ├── configuration.md
│   ├── development.md
│   ├── tradeoffs.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── tests/
│   └── test_smoke.py
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
├── batch.py
├── prompts.sample.jsonl
└── requirements.txt
```

## License

MIT. Do whatever you want.
