# Copilot Skill Creator

A **GitHub Copilot CLI** adaptation of Anthropic's [skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator). The skill itself works with any AI that can read `SKILL.md` — the eval scripts specifically use `copilot -p` to measure whether Copilot triggers the skill for a set of test queries, then iteratively improve the skill description until they do.

For full feature documentation, see the [upstream README](https://github.com/anthropics/skills/tree/main/skills/skill-creator).

## Install

```bash
git clone https://github.com/b4ird/copilot-skill-creator.git ~/.agents/skills/skill-creator
```

Copilot CLI will discover the skill automatically. Running the eval scripts requires Copilot CLI to be installed and authenticated (they call `copilot -p` as a subprocess).

## Cost note

Each `copilot -p` call in the eval loop uses a premium request. A typical run of 20 queries × 3 iterations = ~60 premium requests.

## What changed from upstream

Three eval scripts were adapted for Copilot CLI (`run_eval.py`, `improve_description.py`, `run_loop.py`). Everything else is unmodified upstream content.

**[View the full diff →](https://github.com/b4ird/copilot-skill-creator/compare/upstream...main)**

## License

Apache License 2.0 — see [LICENSE.txt](LICENSE.txt). Original work by [Anthropic](https://github.com/anthropics).
