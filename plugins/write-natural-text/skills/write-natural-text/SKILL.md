---
name: write-natural-text
description: "Write, rewrite, or check text so it reads like a real person wrote it: plain B1-level words, a personal view, uneven structure, no AI writing tells, ASCII punctuation only. Use this skill whenever the user asks for text that should sound natural, human, or not machine-written, or asks to write a post, message, or piece for people to read: LinkedIn, Instagram, Twitter/X, Telegram, Facebook, a blog, an email or letter, a presentation, a comment, a bio, a course answer, a cover letter. Also use it when the user names it ('/write-natural-text', 'use write-natural-text'). Do not use it for code, commit messages, or technical reference docs unless the user asks."
argument-hint: "<what to write, or the text to rewrite or check, plus facts, level, length, and format>"
---

**Announce at start:** "Using skill: **Write Natural Text** to write plain, human-sounding English without AI tells."

# Write Natural Text

Produce text that a human reader would take for a person's own writing: someone who knows the subject and explains their view in ordinary words. The default picture is a fourth-year university student writing in English at B1 level. The text stays correct, specific, and honest; it does not imitate a human through planted mistakes.

This skill applies to any text meant for people to read: a post for LinkedIn, Instagram, Twitter/X, Telegram, or Facebook, an email or letter, the text of a presentation, a comment, a bio, a course answer, a blog article. Whenever the user asks for such a text, or asks for writing that should sound natural or human, follow this skill even if they did not name it.

Two reference files hold the detail. Read them before writing and again during the final check:

- `references/voice.md`: the default speaker, the B1 vocabulary and connector set, the structural patterns that make simple words sound prepared, and how to handle each kind of text.
- `references/ai-tells.md`: the measured signals that reveal machine-written English, the fix for each, the final checklist, and what this work cannot promise about detectors.

## Input

The request arrives in `$ARGUMENTS`. Work out from it:

1. **Mode.** `write` (new text from a brief), `rewrite` (an existing draft is supplied), `add` (one line or sentence to an existing text), or `check` (report the tells in a supplied text without rewriting it). When the mode is not obvious, a supplied text plus a complaint means `rewrite`; a supplied text alone means `check`.
2. **Facts.** The scenario, course material, notes, the user's opinion or reaction, earlier accepted texts. Everything in the output must come from here or be marked as an assumption.
3. **Level.** B1 by default. The user may raise it ("B2", "native", "technical blog"); then keep the same rules with a wider vocabulary.
4. **Length and format.** One line stays one line. A course answer keeps question numbers. A post has no headings. A file is written only when the user asks for one, in the format they name.
5. **Language.** Write in the language the user asks for. If none is named, match the language of the supplied draft or, for a new text, the language of the brief. The vocabulary and connector tables in the references are for English; the rules about structure, content, honesty, and formatting apply to any language. Talk to the user in the language they use.
6. **Platform.** A post follows the habits of its platform in length only (a tweet is short, a LinkedIn post is a few paragraphs, a presentation slide holds a few lines). The voice rules do not change: no hooks, no hashtag walls, no emoji lists, no call to action added by reflex.

## Process

1. **Collect the real material.** The most reliable human signal is a specific detail only this writer would mention: an actual opinion, what surprised them, what they disagree with, the exact feature or number from the scenario. Take it from the request and any files the user points to. If the user has earlier accepted texts, read one or two and match their habits.
2. **Ask once if a personal fact is missing.** When the text needs a personal detail (a reaction, an experience, a choice) and none was given, ask one short question before writing. If the user said to write without questions, use conditional wording ("Suppose ...", "I'd probably ...") and say in the reply which detail would make the text more personal. Never invent a project, a colleague, a customer call, a survey, or a number.
3. **Note what must survive.** For a course answer, every part of the question. For a rewrite, every point the user asked for earlier. Keep this list out of the final prose.
4. **Find the actual thought.** What the speaker chose, noticed, liked, disliked, or would do. Let that drive the explanation instead of the grading criteria.
5. **Write with common words.** Familiar verbs, the B1 connector set from `references/voice.md`, exact technical names where the task needs them, a concrete example where it helps understanding.
6. **Read the whole piece for patterns.** Same opening in several paragraphs, equal paragraph roles, explicit feature-to-benefit links, a generic closing. Fix the pattern rather than swapping a few words.
7. **Run the final check** from `references/ai-tells.md`: sentence-length scan, the search list of tell phrases, repeated evaluative words, one-sentence summary per paragraph, first and last sentence, triads and matched pairs, the "only this writer" question, ASCII check.
8. **Check facts and assumptions.** Nothing added to improve the voice. Assumptions placed where they matter ("I guessed two drivers per evening, because the scenario doesn't give a number"), not as a standard disclaimer at the end.
9. **Return the result.** For `check` mode, list the tells found with the sentence each one sits in, grouped by type, and say which ones matter most; do not rewrite unless asked. For the other modes, return the text; when a file was requested, save it, read it back, and confirm it contains only ASCII characters.

## Rules that apply to every text

- ASCII only: straight apostrophe `'`, straight double quotes `"`, plain hyphen `-`, `...` for an ellipsis. No em dash, en dash, curly quotes, non-breaking spaces, emoji, or decorative symbols.
- Plain words over formal ones: use, help, choose, check, build, keep, find, change, ask, fix. Do not upgrade "use" to "utilize" or "wrote" to "authored".
- Connectors: and, but, because, so, then, also, for example, if, when, still, however (rarely). No cycling through moreover, furthermore, additionally, thus, therefore, "Firstly ... Secondly ... Finally".
- No trailing "-ing" clauses after a comma ("..., highlighting the need for ..."). Full stop, new sentence with a subject, or delete the clause.
- Verbs over nouns made from verbs: "when we build the reminder", not "the implementation of the reminder". "Is", "has", "was" instead of "serves as", "stands as", "features", "offers".
- No groups of three by reflex, no three pros and three cons, no "on one hand / on the other hand" without a decision. Real arguments are lopsided; say which side the writer takes.
- One idea in one place. No thesis restated as the conclusion. No "In short" or "Bottom line" by default. Stop at the last useful point.
- No metatext ("Let's look at the next aspect", "In this post I want to share"), no restated prompt as the first sentence, no template hooks or closers ("Excited to share", "Agree? Let me know in the comments").
- Repeat the topic noun instead of cycling synonyms. Do not repeat generic evaluative words ("important", "allows", "effective"); say what the thing actually does.
- Everyday hedges are allowed where a real doubt exists: "I think", "probably", "maybe". One specific doubt beats a universal "it depends on the context" sentence.
- A plain sentence after a careful one is normal. Not every sentence gets the same polish, and not every topic gets the same enthusiasm.
- No bold for emphasis, no bold lead-ins, no title-case headings, no headings in a short post, lists only for actual lists.
- No chatbot residue: "Certainly!", "I hope this helps", "[Your Name]", offers to expand the text.
- Do not add tool credits or a statement about which assistant produced the text, and do not add claims that the user wrote it independently.

## What not to do

- Do not insert typos, broken grammar, random punctuation, or fake foreign expressions. The user wants correct text that sounds like a person, not a performance of poor writing.
- Do not force casualness: "honestly", "look,", "here's the thing", a contraction in every clause. Scripted informality is its own pattern, and removing one tell list tends to push the model toward these substitutes.
- Do not over-scrub. Text with no adverbs, no passives, no hedges, and no repetition reads sterile.
- Do not score naturalness by a fixed number of contractions, sentence lengths, or filler words. That recreates the problem.
- Do not promise that a text will pass an AI detector, and do not send the user's text to third-party humanizer tools. Detectors are classifiers; simple non-native prose is flagged more often, not less. The target is a human reader.
- Do not drop exact technical terms to lower the level. A precise term from the course or the project makes the text more specific, which is what a human reader expects.

## Examples of the target

A short post, for length and tone only:

> We stopped doing daily stand-up calls last month and moved to short written updates in the team chat.
>
> I thought people would miss the calls. So far nobody has asked to bring them back. The updates are easier to find later, and I get twenty minutes of my morning back. When something is actually broken, I still prefer a quick call, because typing it all out takes too long.

A sentence that only reports that a criterion was met, and a better one:

> Before: Both features support the goal of the scenario: fewer missed deliveries and less work for the drivers.
>
> After: If I know I'll be late, I want to move my delivery to a later time myself. Calling the shop just for that is annoying.

A safe sentence that fits any answer, and a better one:

> Before: Planning delivery times needs careful testing.
>
> After: The app might let a customer pick a delivery time when no driver is free. The shop needs to see that before the customer gets a confirmation.
