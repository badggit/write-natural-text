# write-natural-text

## Install

### Claude Code

Inside a Claude Code session:

```
/plugin marketplace add badggit/write-natural-text
/plugin install write-natural-text@write-natural-text
```

Or from a terminal:

```
claude plugin marketplace add badggit/write-natural-text
claude plugin install write-natural-text@write-natural-text
```

The skill then appears as `write-natural-text:write-natural-text`. Call it explicitly with `/write-natural-text:write-natural-text <request>` (typing `/write-natural` is enough for autocomplete), or just ask for a post, an email, or a text that should sound human; the skill picks that up on its own.

### Codex

```
codex plugin marketplace add badggit/write-natural-text
codex plugin add write-natural-text@write-natural-text
```

Or open `/plugins` inside Codex and pick "Write Natural Text". Call it explicitly with `$write-natural-text <request>`, or let Codex apply it when the request matches.

### Skill only, without the plugin system

Copy `plugins/write-natural-text/skills/write-natural-text/` into a skills directory:

- Claude Code: `~/.claude/skills/write-natural-text/`
- Codex: `~/.agents/skills/write-natural-text/`

### Try it from a local clone

```
git clone https://github.com/badggit/write-natural-text
cd write-natural-text
claude --plugin-dir ./plugins/write-natural-text
```

## What it is

One skill, `write-natural-text`, that writes, rewrites, or checks text so it reads like a real person wrote it. It is built for text that people will read: posts for LinkedIn, Instagram, Twitter/X, Telegram, or Facebook, emails and letters, presentation text, comments, bios, course answers, blog articles.

"Natural" here means:

- plain words at about B1 level, with exact technical terms kept where the subject needs them;
- a clear opinion attached to a specific situation, not a balanced summary of everything;
- uneven structure: some ideas get more space than others, no thesis restated as a conclusion, no groups of three by reflex;
- no AI writing tells: trailing "-ing" clauses, nominalizations, "serves as" instead of "is", symmetric pros and cons, template hooks and closers, bold lead-ins, "In short" endings;
- ASCII punctuation only: straight quotes, plain hyphen, no em dashes, no decorative symbols.

It does not fake humanity. No typos, no broken grammar, no forced casual filler, no invented experiences or numbers. And it does not promise anything about AI detectors: they are trained classifiers, and simple non-native prose is flagged more often, not less. The target is a human reader.

## When it triggers

The skill applies whenever the request:

- asks for text that should sound natural, human, or not machine-written;
- asks for a post, message, or piece for people to read on any platform, an email or letter, a presentation, a comment, a bio, a course answer, a cover letter;
- names the skill directly.

It stays out of code, commit messages, and technical reference docs unless asked.

## What it does

1. Works out the mode: `write` a new text, `rewrite` a draft, `add` one line to an existing text, or `check` a text and report the tells without rewriting it.
2. Collects the real material: the brief, notes, the writer's actual opinion, earlier accepted texts if any. If a personal detail is required and missing, it asks one short question instead of inventing one.
3. Follows explicit requirements and the writer's supplied sample before the default voice: a fourth-year student who explains the subject in ordinary words. The level can be raised on request ("B2", "native"). Replies use the available conversation to avoid repeating known background; standalone texts keep the context they need.
4. Checks structural patterns before individual phrases, then compares the result with the original claims. Numbers, conditions, uncertainty, comparisons, and timing must survive a style edit. Real contrasts and lists stay when their content needs them.
5. Returns the finished text, or saves a file when requested. File edits preserve code, commands, paths, frontmatter, data, and link targets. ASCII checks apply to edited prose; verbatim quotations, names of works, proper names, and technical spans stay intact.

Language: the deliverable is written in the language the request asks for. The word lists in the references are for English; the rules about structure, content, and formatting apply to any language.

## Examples

```
/write-natural-text:write-natural-text a short post: a month ago we replaced daily stand-up calls with written updates in the team chat. I thought people would miss the calls, but nobody asked for them back. Updates are easier to find later and I save about twenty minutes every morning. I still prefer a call when something is actually broken, typing takes too long
```

```
/write-natural-text:write-natural-text rewrite this draft, it sounds like a brochure: <paste>
```

```
/write-natural-text:write-natural-text check: <paste>
```

```
/write-natural-text:write-natural-text add one line to the post above saying the written updates only help when everyone remembers to post them
```

In Codex, replace the slash form with `$write-natural-text`.

## Layout

```
.claude-plugin/marketplace.json        Claude Code marketplace
.agents/plugins/marketplace.json       Codex marketplace
AGENTS.md                              instructions for agents working on this repo
plugins/write-natural-text/
  .claude-plugin/plugin.json           Claude Code plugin manifest
  .codex-plugin/plugin.json            Codex plugin manifest
  skills/write-natural-text/
    SKILL.md                           the skill: input, process, rules
    agents/openai.yaml                 Codex display metadata
    references/voice.md                default voice, B1 vocabulary, kinds of text
    references/ai-tells.md             AI writing signals, fixes, final check
scripts/validate-plugin.sh             manifest and skill checks (run by CI)
```

The plugin lives under `plugins/write-natural-text/`; both marketplace files at the repo root point there. Codex requires the plugin directory to be distinct from the marketplace root, and Claude Code resolves the same relative source. Each harness reads its own manifest set and ignores the other.

## Validation

```
sh scripts/validate-plugin.sh
claude plugin validate .
claude plugin validate ./plugins/write-natural-text
```

The script checks that both plugin manifests and the marketplace carry the same version, that the marketplace entry matches the plugin manifest, that the skill's frontmatter name matches its directory, and that every skill file is ASCII only.

## Updating

Bump `version` in `plugins/write-natural-text/.claude-plugin/plugin.json`, `plugins/write-natural-text/.codex-plugin/plugin.json`, and `.claude-plugin/marketplace.json` together. Installed copies pick up the new version on the next `/plugin marketplace update` in Claude Code or `codex plugin marketplace upgrade` in Codex.

## Contributing

See `AGENTS.md` for the rules that apply to changes in this repository. They are written for coding agents but apply to people as well.
