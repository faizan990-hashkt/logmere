# logmere

A tiny CLI to clean, rotate and archive old log files

Started as a weekend hack, grew on me.

## Install

```bash
pip install -r requirements.txt
python -m logwash --help
```

## What it does

- Exit codes friendly for cron and CI
- Filter by age (--older-than) or size (--larger-than)
- Archive matched logs into a timestamped .tar.gz
- Dry-run mode shows what would happen, touches nothing
- Scan directories for log files by glob pattern

## Usage

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Project structure

```text
├── .github/
│   └── ISSUE_TEMPLATE/
│       └── bug_report.md
├── docs/
│   ├── configuration.md
│   ├── development.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   ├── errors.py
│   └── utils.py
├── tests/
│   └── test_cli.py
├── .editorconfig
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT licensed, see LICENSE.
