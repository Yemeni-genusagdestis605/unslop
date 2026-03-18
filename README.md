# anti-slop

Empirically detect and eliminate AI output patterns.

Every AI model has defaults it collapses toward — phrases it overuses, layouts it always reaches for, structures it falls back on. This is slop. It's the reason every AI blog post opens with "In today's rapidly evolving landscape" and every AI-generated landing page has the same hero section with a gradient blob.

**anti-slop** finds these patterns automatically and generates a skill file that eliminates them.

## How it works

1. You give it a domain (e.g., "blog writing" or "React landing pages")
2. It generates diverse prompts and runs them all through Claude Code
3. Claude reads through every output (or looks at every screenshot) and identifies the patterns
4. It produces a skill file — a set of specific instructions on what to avoid
5. It runs a before/after comparison so you can see the difference

The output is a single markdown file you can drop into any project as a Claude Code skill, paste into CLAUDE.md, or use as a system prompt.

## Quickstart

You need [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed.

```bash
git clone https://github.com/YOUR_USERNAME/anti-slop.git
cd anti-slop

# Recommended on macOS / Homebrew Python
python3 -m venv .venv
source .venv/bin/activate

# For writing / text domains
python anti_slop.py --domain "blog writing"

# For website / visual domains (requires playwright)
pip install playwright && playwright install chromium
python anti_slop.py --domain "React landing pages" --type visual

# Customize
python anti_slop.py --domain "marketing emails" --count 100 --concurrency 10

# Optional Claude tuning
python anti_slop.py --domain "React landing pages" --type visual --model sonnet --effort low
```

Output lands in `./anti-slop-output/`:

```
anti-slop-output/
  skill.md              ← the anti-slop skill file (this is what you want)
  analysis.md           ← raw pattern analysis with counts
  prompts.json          ← the prompts that were generated
  samples/              ← all raw outputs
  screenshots/          ← rendered pages (visual domains only)
  before-after/         ← vanilla vs anti-slop comparison
    before.md / .html
    after.md / .html
    before.png / after.png
```

## Options

| Flag | Default | Description |
|---|---|---|
| `--domain` | (required) | What to analyze: `"blog writing"`, `"React landing pages"`, `"Python tutorials"`, etc. |
| `--type` | `text` | `text` for writing/code, `visual` for websites/designs |
| `--count` | `50` | Number of samples to generate (10 to 10,000) |
| `--concurrency` | `5` | Parallel Claude Code calls |
| `--model` | Claude default | Claude model alias/name to pass through (`sonnet`, `opus`, etc.) |
| `--effort` | Claude default | Claude effort level to pass through (`low`, `medium`, `high`, `max`) |
| `--timeout` | `600` | Seconds to wait per Claude call before failing |
| `--analysis-timeout` | `1800` | Seconds to wait for the analysis pass |
| `--retries` | `1` | Retries per failed Claude call |
| `--output` | `./anti-slop-output` | Where to put results |
| `--skip-comparison` | `false` | Skip the before/after step |

## Using the skill file

The generated `skill.md` works anywhere you can provide instructions to an AI:

**Claude Code skill** — Copy `skill.md` into your project. Claude Code will automatically pick it up.

**CLAUDE.md** — Paste the contents into your project's `CLAUDE.md` file.

**System prompt** — Prepend the contents to your system prompt in any API call.

**Cursor rules** — Paste into `.cursorrules` in your project root.

**Codex** — Paste into the instructions field.

## Pre-built profiles

The `profiles/` directory has pre-generated anti-slop profiles you can grab and use right now without running the tool:

- [`profiles/writing.md`](profiles/writing.md) — Blog posts, essays, articles
- [`profiles/react-design.md`](profiles/react-design.md) — React/HTML landing pages and websites

These were generated from 100 samples each. Run the tool yourself for domain-specific or more targeted profiles.

## Philosophy

anti-slop focuses on what to **avoid**, not what to do instead. Prescribing alternatives just creates a new flavor of slop. The goal is to knock out the defaults and force the model to actually be creative.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) (`npm install -g @anthropic-ai/claude-code`)
- Python 3.10+
- On macOS/Homebrew Python, use a virtual environment before `pip install ...`
- For visual domains: `pip install playwright && playwright install chromium`

## License

MIT
