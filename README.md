# Explain for understanding

A small, portable Agent Skill that favors the clearest format for explaining complex work: direct writing, a diagram, an interactive HTML page, or an explainer video when it helps someone understand and inspect the result.

Inspired by [Andrej Karpathy's post](https://x.com/karpathy/status/2105819303471976479).

## Install the skill

Clone once, then link the same skill into the agents you use:

```sh
git clone https://github.com/jaouadou/explain-for-understanding.git ~/explain-for-understanding
mkdir -p ~/.codex/skills ~/.claude/skills
ln -s ~/explain-for-understanding ~/.codex/skills/explain-for-understanding
ln -s ~/explain-for-understanding ~/.claude/skills/explain-for-understanding
```

Codex and Claude Code can load the same `SKILL.md` because both support the Agent Skills format. Skills in these personal directories are available across local projects, and each agent may select the skill when an explanation is relevant. You can invoke it explicitly with `$explain-for-understanding` in Codex or `/explain-for-understanding` in Claude Code.

## Make it a default

Skill selection alone does not ensure the preference shapes every explanation. For Codex, add this line to `~/.codex/AGENTS.md`:

```md
For every response that explains a concept, result, or completed work to me, use the installed `explain-for-understanding` skill by default. Respect any format I explicitly request.
```

For Claude Code, install the included [output style](claude/output-styles/explain-for-understanding.md) and select it globally:

```sh
mkdir -p ~/.claude/output-styles
ln -s ~/explain-for-understanding/claude/output-styles/explain-for-understanding.md ~/.claude/output-styles/explain-for-understanding.md
```

Add `"outputStyle": "explain-for-understanding"` to `~/.claude/settings.json`, preserving any other settings. The style applies to the main conversation's responses and keeps Claude Code's coding instructions. It is an instruction, not a hard guarantee; project settings can override it.

To explicitly ask Claude Code to load the skill for explanations, also add the same personal-default sentence shown above to `~/.claude/CLAUDE.md`. This file loads at the start of local sessions across projects.

Claude Code's `~/.claude/skills/` and output style are local. For Cowork and cloud sessions, enable the skill in your claude.ai account, or commit it to a particular repository's `.claude/skills/` for cloud coding sessions. The local output style does not automatically sync to claude.ai.

Other agents that support Agent Skills can use the same [SKILL.md](SKILL.md), installed in that agent's documented skills directory. Their persistent instruction or output-style mechanism is separate and must be configured per agent if you want this preference by default.
