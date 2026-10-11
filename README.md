# Explain for understanding

A small Codex skill that favors the clearest format for explaining complex work: direct writing, a diagram, an interactive HTML page, or an explainer video when it helps someone understand and inspect the result.

Inspired by [Andrej Karpathy's post](https://x.com/karpathy/status/2105819303471976479).

## Install

Clone this repository into your personal Codex skills directory:

```sh
git clone https://github.com/jaouadou/explain-for-understanding.git ~/.codex/skills/explain-for-understanding
```

Codex can select the skill for explanations. You can also invoke it explicitly with `$explain-for-understanding`.

## Make it a personal default

Automatic skill selection is possible, but is not guaranteed for every reply. To apply this preference across your Codex tasks, add this line to `~/.codex/AGENTS.md`:

```md
For every response that explains a concept, result, or completed work to me, use the installed `explain-for-understanding` skill by default. Respect any format I explicitly request.
```

The complete skill is in [SKILL.md](SKILL.md).
