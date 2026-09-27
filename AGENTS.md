# AGENTS.md

Instructions for agents (Claude Code, Codex, or any other) working in this repository, and for people who edit it by hand.

## Install the skill this repo ships

Claude Code, inside a session:

```
/plugin marketplace add badggit/write-natural-text
/plugin install write-natural-text@write-natural-text
```

Claude Code, from a terminal:

```
claude plugin marketplace add badggit/write-natural-text
claude plugin install write-natural-text@write-natural-text
```

Codex:

```
codex plugin marketplace add badggit/write-natural-text
codex plugin add write-natural-text@write-natural-text
```

Skill only, without the plugin system: copy `plugins/write-natural-text/skills/write-natural-text/` into `~/.claude/skills/` (Claude Code) or `~/.agents/skills/` (Codex).

Local test from this checkout, without installing:

```
claude --plugin-dir ./plugins/write-natural-text
```

The skill is then available as `/write-natural-text:write-natural-text` in Claude Code and `$write-natural-text` in Codex, and both harnesses apply it on their own when a request asks for a post, an email, a course answer, or any text that should sound human.

## What this repository is

A plugin with one skill, `write-natural-text`, plus the marketplace manifests that let Claude Code and Codex install it from this repo. The skill writes, rewrites, or checks text so it reads like a real person wrote it: plain B1-level words, a personal view, uneven structure, no AI writing tells, ASCII punctuation only.

```
.claude-plugin/marketplace.json        Claude Code marketplace (name: write-natural-text)
.agents/plugins/marketplace.json       Codex marketplace (same name)
plugins/write-natural-text/
  .claude-plugin/plugin.json           Claude Code plugin manifest
  .codex-plugin/plugin.json            Codex plugin manifest
  skills/write-natural-text/
    SKILL.md                           the skill: input, process, rules that apply to every text
    agents/openai.yaml                 Codex display metadata
    references/voice.md                default voice, B1 vocabulary and connectors, kinds of text
    references/ai-tells.md             AI writing signals with fixes, the final check, limits
scripts/validate-plugin.sh             checks run by CI (.github/workflows/validate.yml)
```

The plugin directory must stay distinct from the marketplace root: Codex requires it, and both marketplace files point to `./plugins/write-natural-text`.

## Rules for changes

### Content

- English only, ASCII only, in every file: straight apostrophe `'`, straight double quotes `"`, plain hyphen `-`, `...` for an ellipsis. No em dash, en dash, curly quotes, non-breaking spaces, emoji, or decorative symbols. The skill teaches this rule, so its own files must follow it; `scripts/validate-plugin.sh` fails on a non-ASCII character in any skill file.
- The skill must stay self-contained. `SKILL.md` and `references/` may point only at each other. No links to files outside the plugin directory, no dependence on a particular project, user, or course.
- Keep `SKILL.md` procedural: input, process, the short rule list, what not to do, a few examples. Catalogs, tables, and longer examples belong in `references/`.
- Every new AI-writing signal added to `references/ai-tells.md` needs the fix next to it. Do not add a word to the vocabulary list without a plain alternative or a reason. The skill's approach is structure and content first; a longer banned-word list on its own is not an improvement.
- Examples must be generic: made-up scenarios, roles instead of names, no real companies, products, or people beyond widely known tool names used as technical terms.
- No personal data of any kind, no private project details, no notes about where material came from, no statements about which assistant produced a file.
- No links, citations, study names, or numbers from studies in the skill files. The skill states its rules; it does not argue for them.
- Do not claim the skill makes text pass AI detectors. The references explain why; keep that section when editing.

### Manifests

- `name` is `write-natural-text` in both plugin manifests, both marketplace entries, and the skill frontmatter. The skill directory name must equal the frontmatter `name`.
- Bump `version` in `plugins/write-natural-text/.claude-plugin/plugin.json`, `plugins/write-natural-text/.codex-plugin/plugin.json`, and `.claude-plugin/marketplace.json` together. Marketplace plugin entries must not carry their own `version`.
- The `description` in `.claude-plugin/marketplace.json` must be identical to the one in the Claude plugin manifest. Keep the Codex manifest's description and `interface` block in step with it.
- Skill frontmatter: `description` under 1024 characters, no `->` inside it (Codex parses frontmatter strictly), and it must say when the skill should and should not trigger.

### Git

- Do not commit, push, or open pull requests unless asked to.
- Commit messages and pull request text in English, plain ASCII punctuation.
- Do not add files matched by `.gitignore`. `AGENTS.md` itself is tracked; machine-local variants (`*.local.md`) are not.

## Verify before finishing

Run all of these and read the output; a change is not done until they pass:

```
sh scripts/validate-plugin.sh
claude plugin validate .
claude plugin validate ./plugins/write-natural-text
LC_ALL=C grep -rnP '[^\x00-\x7F]' . --include='*.md' --include='*.json' --include='*.yaml' --include='*.sh'
```

The last command must print nothing. After editing `SKILL.md` or its frontmatter, also confirm the skill still loads:

```
claude --plugin-dir ./plugins/write-natural-text -p "Reply with the exact names of the skills available to you whose name contains natural." --max-turns 1
```

Expected output includes `write-natural-text:write-natural-text`.
