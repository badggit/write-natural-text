# Signs of AI writing and how to avoid them

The signals that AI detectors and experienced readers use to spot machine-written English, grouped by type, with the fix for each one. Use it during the last edit of any English deliverable. Read "What this can and cannot do" first; it sets the expectations.

## What this can and cannot do

- Modern detectors are trained classifiers, not lists of banned words. Removing the surface tells below does not guarantee a "human" score, even after the text has been rewritten.
- Simple non-native prose gets flagged MORE, not less. Detectors that measure predictability flag a large share of genuine essays by non-native writers, because a narrow vocabulary makes the text easy to predict. So the B1 target and a low detector score pull in different directions. The way out is not fancier vocabulary. It is unpredictability from content: a specific fact, a real choice, an uneven argument, a detail only this author would mention.
- The real reader is a human grader or a contact on a social network, and people who use LLMs a lot recognise AI text most of the time. Write for that reader. Do not chase a detector.
- Signals only add up. One "not only ... but also", one "moreover", one triad prove nothing and are used by millions of people. The suspicious case is ten weak signals in one short text. Do not break a good sentence to remove a single tell.
- Do not claim that a text will pass a detector, and do not run the user's text through third-party rewriting tools.

## Signals and fixes

### Statistical shape of the text

| Signal | What to do |
| --- | --- |
| Uniform sentence length: 14, 16, 15, 17, 16 words in a row. | Read for mechanical rhythm. Merge or split sentences where it helps the thought; equal lengths alone do not require a change. Do not aim for a fixed pattern of short and long. |
| Uniform predictability: every sentence is the one a reader would guess next. | Replace the expected sentence with the specific one: the feature name, the number from the scenario, the actual worry. Content, not vocabulary, is what makes text less predictable at B1. |
| Uniform quality and register: every sentence polished to the same degree, same formality throughout. | Allow one plain sentence after a careful one. A blunt remark after a formal explanation is normal: "That part I'm less sure about." Do not script it into every paragraph. |
| Mismatch with the writer's profile: a B1 student submitting error-free, noun-heavy, highly varied prose, or a sudden style change compared with earlier texts. | If the user has earlier accepted texts, read one or two and keep the same habits: same connectors, same level of detail, same kind of examples. |

### Grammar and syntax

These are the strongest differences between LLM and human English. All of the fixes also make the text closer to real B1 writing.

| Signal | Example | Fix |
| --- | --- | --- |
| Trailing participial filler after a comma. | "..., highlighting the need for better planning." "..., ensuring that teams stay aligned." | Remove repeated commentary. If the clause carries a distinct claim, make it a direct sentence without adding certainty or causation. |
| Nominalizations: the action turned into a noun. | "the implementation of the reminder", "prioritization of features", "the utilization of spreadsheets" | Use the verb: "when we build the reminder", "decide which features go first", "using spreadsheets". |
| Avoiding "is", "are", "has". | "serves as", "stands as", "features", "offers", "marks", "boasts", "began his career as" | "is", "has", "was". Plain linking verbs are what a student writes. |
| Vague relation instead of a direct fact. | "was associated with teaching", "is involved in testing" | Use "taught" or "tests" only if the source establishes that role. Otherwise retain the uncertainty or ask; do not invent the relationship. |
| Stiff synonyms for plain verbs. | utilized, authored, relocated, attempted, commenced | used, wrote, moved, tried, started. |
| Paired contrast frames, including contrasts split across sentences. | "not only X but also Y", "Y rather than X", "No X. No Y. Just Z.", "This isn't about X. It's about Y." | State the point directly when the negative half adds nothing. Keep both halves when they carry distinct facts or correct a real misunderstanding. |
| Formal or stacked hedges. | "This could potentially possibly lead to issues." | "This could cause problems." Remove redundant qualifiers, not the uncertainty. Keep conditions, scope limits, and necessary legal or safety notices. |
| Grammar that is too clean: no sentence ever starts with "And" or "But", never a fragment, always an Oxford comma. | | Starting a sentence with "But" is fine. An occasional fragment is fine when it is how the thought comes out. Do not plant them on purpose. |
| No passives at all. Scrubbing every passive is itself a pattern. | | Leave a passive where the actor does not matter: "The order is packed the evening before." |

### Rhetoric and structure

| Signal | Fix |
| --- | --- |
| Rule of three: three adjectives, examples, or parallel sentences added for rhythm. | Keep three distinct items when the meaning needs them. Merge repetition, not different facts; do not delete an item just to change the count. |
| Symmetric balance: matching pros and cons regardless of substance. | Give each reason the space it needs. Preserve a stated choice or genuine uncertainty; do not invent a preference to make the argument lopsided. |
| Thesis stated, explained, then restated as the conclusion. | One idea in one place. Cut the closing restatement. Stop at the last useful point. |
| Sentences that explain the obvious: "This factor is important because it affects the project." | Ask what the reader learns from the sentence. If nothing, delete it. |
| A lesson after an example that already makes the point: "This shows why planning matters." | Cut the repeated lesson. Keep a consequence the example does not already establish. |
| Depth performed through a saying: "At its core, planning is the currency of trust." | State the supported relationship in plain words; if none is supplied, cut the flourish instead of inventing an explanation. |
| Answering an absent objection: "I'm not saying speed does not matter. The form needs clearer labels." | Keep "The form needs clearer labels" if speed was never at issue. Preserve real objections and alternatives the reader needs to weigh. |
| Inflating significance: linking a small point to "broader trends", "the fast-paced world", "crucial for success". | State the small point and its concrete effect on the project. |
| The "despite challenges, the future looks promising" closer. | End on the last concrete point or on the open question. |
| Colon reveals and punchlines: "Here's the kicker:", "The result:", "Let that sink in.", "Read that again.", "Unpopular opinion:", a one-line closer. | Write the fact in a normal sentence. |
| Template hooks and closers, mostly in posts: "Most people think X. They're wrong.", "Nobody tells you ...", "Excited/thrilled/honored to share", "Agree? Let me know in the comments", "Huge thanks to ...". | Start with the fact ("We stopped doing daily stand-up calls ...") and stop when the point is made. |
| Rhetorical question followed by its answer, repeated as a device. | Make the statement directly. |
| One universal hedge sentence: "In some cases this may help, but much depends on the context and individual circumstances." | One specific doubt about one specific thing: "I'm not sure two drivers are enough if the shop adds Sunday deliveries." |
| Equal enthusiasm for every topic. | Give the boring part a boring sentence. Not every part of a project is interesting. |
| "In short", "Bottom line", "To sum up" endings by default. | Stop at the last useful point; add a summary only when the text is long enough to need one. |
| A heading repeated by its first sentence: "Delivery times" followed by "Delivery times matter." | Delete the restatement and start with the actual times or constraints. |
| Narrating the document's assembly or visible layout: "The table below lists the options we collected." | Start with the options. Keep source credits, methods, or conventions needed to interpret them, and change history in release notes or migration guides. |
| A reply rebuilds context the recipient already supplied before reaching the answer. | Lead with the answer and keep new facts and necessary reasons. Use the conversation guidance in `voice.md`; standalone writing still needs context. |

### Vocabulary

Do not solve these by synonym swapping. When one of these words appears, ask whether a plain word or a concrete fact would do the job. If the word is exact (a primary "key" in a database, a "robust" method in statistics), keep it.

- Currently most overused verbs and adjectives: highlighting, emphasizing, showcasing, underscore, enhance, crucial, pivotal, key, valuable, robust, seamless, vibrant, landscape, journey, navigate, unlock, elevate, align with, testament, intricate, meticulous, commendable, multifaceted, garner, bolster, foster, leverage, delve, comprehensive, potential (as a noun), findings, "ensure" as filler, "it's worth noting", "importantly", "genuinely".
- Newer conversational tics from 2025-2026 models: quietly, honestly, frankly, "the real X", load-bearing, "earns its keep", "Honest caveat:", "good point", "good question", "here's the thing". Removing the old list tends to push the model toward these. Watch for them after a rewrite.
- Promotional tone: boasts, renowned, rich, powerful, incredibly exciting, game-changer, streamline.
- Repeated generic evaluative words. Count them in a 300-word answer: "important" eight times, "allows" seven, "effective", "significant", "necessary", "efficient". Replace most of them with what the thing actually does. This is different from repeating the topic noun, which is fine.
- Vague attribution: "experts say", "research shows", "studies suggest", "it is widely known". Use a supplied source and its actual claim. Do not invent a study or turn the claim into the writer's opinion. If support is missing, flag it or ask; absence of a citation alone does not justify deleting a claim during a style edit.
- Odd precision without a source: "27.4 percent", "13.6 months". Draft numbers are round: "about three weeks", "maybe a third of the orders".
- Invented default names (Sarah, Emily, John) and tidy examples that never go wrong. Prefer roles from the scenario ("the shop manager") or the names the assignment uses. An example can include something that did not work.

### Content and substance

- Regression to the mean is the core tell: specific facts get replaced by generic positives. "The text message customers get an hour before the driver arrives" becomes "valuable notification capabilities". Keep the specific: which feature, which lesson, which part of the brief, which number from the scenario.
- Unnecessary detail is the human signal, but it has to be real. Collect it from the user before writing: what they actually think, what surprised them, what they disagree with, which part they would skip. When the text needs a personal fact and there is none, ask one short question or use conditional wording. Never invent a project, a colleague, a customer call, or a survey.
- A loose end is allowed. "I'm not sure how we'd measure this" is better than a tidy conclusion the writer does not believe.
- Chatbot residue: "Certainly!", "Here's a ...", "I hope this helps", "Feel free to ...", "[Your Name]", an offer to expand the text. Search for these before returning the text.

### Formatting

Mostly relevant for posts, but course answers pasted into a text box have the same issue.

- No bold for emphasis (LLM text uses it far more often than people do) and no "**Bold lead-in:** explanation" bullets.
- No title-case headings, no "X and Y" section names, no headings at all in a short post.
- No functional emojis (check mark, rocket, brain, blue diamond), arrows, or "approximately equal" signs. Face emojis are what people use, and only if the user asks.
- No one-sentence-per-line layout unless the user writes that way themselves.
- Lists only for actual lists. A personal reflection is not a checklist.
- ASCII only in edited prose: straight apostrophe, straight double quotes, plain hyphen, "..." for an ellipsis. Preserve the protected spans defined in `SKILL.md`.

## The final check

Run this on the whole text after the draft is complete. In `check` mode, report findings without applying edits. These are diagnostic checks, not quotas.

1. Read for mechanical rhythm within and across paragraphs. Change it only where the result reads better; equal lengths alone do not require an edit.
2. Search the text for: ", highlighting", ", ensuring", ", allowing", ", emphasizing", ", showcasing", "not only", "rather than", "serves as", "stands as", "moreover", "furthermore", "additionally", "thus", "therefore", "crucial", "key", "robust", "seamless", "leverage", "ensure", "landscape", "journey", "honestly", "quietly".
3. Count "important", "allows", "effective", "significant", "necessary". More than two or three of any of them in a short answer means the specific effect is missing.
4. Summarize each paragraph privately. Merge repeated points while keeping distinct details. Check headings, examples, and their following sentences for redundant explanations.
5. Read the first and last sentence of the whole text. Restated prompt, template hook, summary of what was already said, or a closing call to action: rewrite or delete.
6. Check triads, matched pairs, and contrasts against their meaning. Keep distinct items and real alternatives; change only the imposed rhythm.
7. Ask: would a grader reading fifty answers see anything here that only this writer could have written? If not, the missing piece is a real opinion or detail from the user, not a style change.
8. Confirm edited prose is ASCII only. For a prose-only file, `grep -nP '[^\x00-\x7F]' <file>` must print nothing. For mixed files, check edited prose separately and compare protected spans with the original; do not normalize them.
9. If earlier accepted texts exist, check that the new text would sit next to one of them without a visible style jump.
10. Compare the final text with the required claims in both directions. Check numbers, dates, names, citations, negations, conditions, uncertainty, ranking, and timing. "More than 40" must not become "40"; "may help" must not become "helps". Reread the result for replacement tics after fixing any loss or addition.

## Constraints and gotchas

- Banned-word lists shift the pattern instead of removing it. Models replace one tell with a substitute ("delve" leaves, "good point" arrives). Check the rewrite for new tics, not only for the old list.
- Do not insert typos, broken articles, random punctuation, shuffled sentences, or Unicode tricks. These lower quality and are visible as planted imperfection.
- Do not force casualness: "honestly", "look,", "here's the thing", a contraction in every clause. Scripted informality is its own pattern.
- Do not over-scrub. Text with no adverbs, no passives, no hedges and no repetition reads sterile, which experienced readers also notice.
- Do not treat the B1 target as a reason to drop exact technical terms. Low perplexity comes from generic wording; a precise term makes the text more specific, not less.
- Things that do NOT indicate AI on their own: perfect grammar, a transition word here and there, mixed formal and casual register, an em dash, a single "not X but Y", unsourced claims. Do not rewrite a text over one of these.
- Humans are adopting LLM vocabulary too, and the tells drift every year. Re-check the word lists when this file feels stale.
