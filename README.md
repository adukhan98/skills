# Skills

Personal Codex skills I use day to day.

This repo is a working library, not a polished package registry. Each folder is one skill: a small set of instructions, prompts, scripts, or assets that make my agents better.

## Skills

| Skill | What it does |
| --- | --- |
| [`goalstorm`](./goalstorm) | Runs implementation work through an explicit goal, parallel agent delegation, synthesis, and verification. |

## Structure

```text
skill-name/
  SKILL.md
  agents/
    openai.yaml
```

`SKILL.md` is the source of truth. `agents/openai.yaml` adds the UI metadata Codex can show when the skill is listed or invoked.

## Install A Skill

Clone the repo:

```bash
git clone https://github.com/adukhan98/skills.git
cd skills
```

Copy a skill into your local Codex skills directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R goalstorm "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then restart Codex if the skill list does not refresh automatically.

## Updating Skills

Skills should stay short. Remove no-op instructions, duplicated guidance, and generic lines that do not change agent behavior.

Before committing a skill update, check that the frontmatter still parses:

```bash
ruby -ryaml -e 's=File.read(ARGV[0]); y=s.match(/\A---\n(.*?)\n---\n/m) or abort("missing frontmatter"); YAML.safe_load(y[1]); puts "ok"' goalstorm/SKILL.md
```

## License

Personal skill library. Reuse what is useful.
