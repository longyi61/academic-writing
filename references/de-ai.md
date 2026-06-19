# Stripping AI tells from journal prose

Load this when the user wants to **de-AI / humanize / de-slop** academic text, or when the main skill needs the mandatory final de-AI gate. The goal is not to make the paper casual. The goal is the same voice the rest of the skill describes: precise, economical, confidently authored, and free of generic machine fluency.

This reference adapts the `blader/humanizer` pattern catalog and audit loop to OM/MS journal prose. Use the pattern coverage from humanizer, but apply the journal-specific overrides below.

## What de-AI means for a journal paper

For a blog post, humanizing may mean adding opinions, humor, first person, and looser rhythm. Do not do that here. A journal paper's human signal is a competent author making exact claims, naming mechanisms, and explaining intuition.

So:

- Tighten toward precision, not personality.
- Use only words, phrases, and sentence structures that fit published Management Science / M&SOM prose or the user's supplied source passages.
- Preserve claims, notation, citations, numbers, and result directions.
- Do not invent mechanisms, statistics, examples, citations, or institutional facts to make the paragraph sound complete.
- If the text is vague because the content is missing, flag the missing content instead of smoothing it into fluent filler.
- Keep first-person plural "we" for author actions; never switch into first-person singular or conversational blog voice.

## Humanizer audit loop, adapted

Run this loop before returning any output under the skill:

1. **Scan** the full response, including notes and alternatives, for the pattern families below.
2. **Rewrite, do not merely delete.** Preserve the original coverage and substantive meaning. Replace AI-coded phrasing with exact claims, mechanisms, citations, or conditions.
3. **Ask:** "What in this still reads as machine-written?" Identify the remaining tells briefly for yourself.
4. **Revise again.** Return only the final cleaned version unless the user asks to see the audit.
5. **Check preservation.** Confirm that the cleaned version has not changed the result, notation, caveat, magnitude, citation, or comparison.

## Pattern families to remove

### 1. Significance inflation

**Watch for:** "plays a crucial/pivotal role," "underscores the importance of," "has far-reaching implications," "in an increasingly complex and dynamic landscape," "represents a significant step," "is a critical area of growing interest."

**Fix:** State the specific claim. "The holding cost determines the order quantity" beats "The holding cost plays a pivotal role in shaping inventory outcomes."

### 2. Superficial "-ing" analysis

**Watch for:** clauses ending in "highlighting," "underscoring," "reflecting," "showcasing," "contributing to," "emphasizing," "ensuring," "fostering."

**Fix:** Cut the tail, or replace it with a real causal or quantitative statement: "which raises the retailer's margin by 4%."

### 3. Promotional language

**Watch for:** "groundbreaking," "powerful," "rich," "fascinating," "vibrant," "seamless," "robust framework," "valuable insights," "breathtaking," "must-visit," "renowned."

**Fix:** Let the model, estimate, theorem, or example carry the point. In results narration, numbers and conditions persuade better than adjectives.

### 4. AI vocabulary clusters

**Watch for:** *delve, intricate, interplay, tapestry, leverage* as filler, *underscore, pivotal, crucial, nuanced* as filler, *holistic, multifaceted, realm, landscape, navigate, foster, garner, showcase, testament, vibrant*.

**Fix:** Replace each with the concrete word the sentence needs. Keep technical uses: "robust to misspecification" is fine; "a robust framework" is usually filler.

### 5. Copula avoidance

**Watch for:** "serves as," "stands as," "acts as," "boasts," "features," "represents," "constitutes" where "is" or "has" would do.

**Fix:** Use the plain verb unless the stronger verb has a real technical meaning. Keep "represents" only for genuine mappings, as in "Z represents the indicator."

### 6. Vague attribution and source fog

**Watch for:** "Studies have shown," "Experts argue," "It is widely believed," "Prior work suggests," "industry reports," "observers note," "several papers" when the sentence names no source or only cites two.

**Fix:** Name the paper and the finding: "Cui et al. (2020) show that removing a high-quality delivery option cut sales." If no source is available, either remove the claim or mark it as missing.

### 7. Notability and name-dropping

**Watch for:** lists of outlets, firms, awards, or media mentions used to imply importance without explaining the relevance.

**Fix:** Keep only the source or example that does analytical work. A named firm belongs in the paper when it grounds the phenomenon, assumption, or external validity, not when it merely decorates the motivation.

### 8. Speculative gap-filling

**Watch for:** "while specific details are limited," "based on available information," "it appears that," "likely," "it is believed that," followed by plausible filler.

**Fix:** Say what is known, cite it if possible, or flag the missing fact. Do not turn uncertainty into invented background.

### 9. Negative parallelism as filler

**Watch for:** "not only X but also Y," "not merely X; it is Y," "not just about X, but about Y," especially when X is a strawman.

**Fix:** State the point directly. Keep the construction only when X is a real prevailing view the paper overturns and the contrast is the contribution.

### 10. Rule of three

**Watch for:** triads that exist for rhythm: "efficient, scalable, and robust"; "practical, generalizable, and effective"; "innovation, insight, and impact."

**Fix:** Use the number of items the argument actually needs, often one or two.

### 11. Elegant variation

**Watch for:** synonym cycling for one construct: "order quantity," "procurement level," "stocking decision"; "platform," "marketplace," "intermediary" when these are not distinct.

**Fix:** Choose one term and repeat it. In technical prose, repetition is clarity.

### 12. False ranges

**Watch for:** "from X to Y" lists where X and Y are not endpoints on a meaningful scale: "from pricing to sustainability to algorithm design."

**Fix:** List the actual domains or state the unifying claim.

### 13. Filler openers and throat-clearing

**Watch for:** "It is important to note that," "It should be emphasized that," "In order to," "Due to the fact that," "At this point in time," "In today's competitive environment," "Over the past decades."

**Fix:** Cut or compress. Keep functional signposting only when it points to something specific: "Note that (7) binds when..." or "Recall that demand is censored."

### 14. Persuasive-authority tropes

**Watch for:** "The real question is," "At its core," "Fundamentally," "What truly matters is," "The heart of the matter."

**Fix:** Delete the windup and state the claim.

### 15. Stacked hedging

**Watch for:** "may potentially," "could possibly suggest," "it might be argued that perhaps," "appears to possibly."

**Fix:** Use one hedge, placed where uncertainty is real. Proven propositions and estimated coefficients are asserted; causal reach and managerial extrapolation may be qualified.

### 16. Generic upbeat conclusions

**Watch for:** "opens exciting new avenues," "paves the way for," "holds great promise," "the future looks bright," "a major step forward."

**Fix:** End on a concrete claim, a boundary condition, or a specific open question. One earned applied closing line can stay; a paragraph of uplift cannot.

### 17. Formulaic challenge/future sections

**Watch for:** "Despite these challenges..." followed by generic resilience or future-promise language.

**Fix:** Name the actual limitation, identification threat, modeling simplification, or external-validity boundary.

### 18. Passive voice and subjectless fragments

**Watch for:** "The problem is solved by..." when the actor matters, and fragments such as "No further assumptions needed" or "No manual tuning required."

**Fix:** Prefer active voice when it clarifies agency: "We solve the model by backward induction." Passive is fine when the actor is irrelevant: "The proofs are relegated to the appendix."

### 19. Formatting tells

**Watch for:** decorative boldface, inline-header bullets ("- **Mechanism:** ..."), emojis, title-case mini-headings inside prose, one-line headings that restate themselves, and chatbot residue such as "Here is an overview," "Certainly," "I hope this helps," "Would you like me to..."

**Fix:** Use prose. Keep real journal section headings in the target style, but avoid decorative formatting in the body.

### 20. Diff-anchored or revision-anchored wording

**Watch for:** "This paragraph was revised to," "This section now," "the previous version," unless the user asked for a change log.

**Fix:** Describe the idea as it stands. In the explanation note, say only the two or three editing moves that matter.

### 21. Manufactured punchlines and aphorism formulas

**Watch for:** stacked short fragments or reusable profundity: "The old rules were gone"; "X is the language of Y"; "the currency of"; "not a tool but a mirror"; "efficiency becomes a trap."

**Fix:** Replace the formula with the concrete mechanism or claim. A short sentence is fine; a string of dramatic closers is not.

### 22. Fake-candid rhetorical openers

**Watch for:** "Honestly?", "Look," "Here's the thing," "Real talk," "Let's be honest," especially as standalone hooks.

**Fix:** State the point directly. This register does not belong in journal prose.

## Don't overcorrect for journal prose

A generic humanizer can damage academic writing. Preserve these unless they are part of a larger cluster of filler:

- **Em dashes can stay.** OM/MS journals use them. Fix only dashes that hide a run-on sentence or fake drama.
- **Hyphenated compound modifiers are correct.** Keep "high-quality logistics," "data-driven decision," "first-difference estimator," "two-sided market," and similar attributive compounds.
- **Curly quotes do not matter** in LaTeX or typeset prose. Ignore them unless the user asks for plain-text normalization.
- **Functional signposting stays.** "Note that," "Recall that," "We organize the paper as follows," and "In this section we examine..." are fine when they orient the reader to a real object.
- **First-person plural stays.** "We develop," "we show," and "we find" are standard. Do not replace them with passive voice or casual first person.
- **Contribution adjectives can stay in the contribution paragraph.** "We are the first to," "a novel form of," and "important contributions" are normal there. Strip them when they leak into results narration or generic body prose.
- **Formal vocabulary is not itself an AI tell.** Remove specific filler words and clusters, not every academic word.

## Quick de-AI checklist

Before returning, ask:

- Does every sentence make a concrete claim, define an object, explain a mechanism, or guide the reader?
- Did I replace vague significance with exact model behavior, data, conditions, or citations?
- Did I remove fake-depth "-ing" tails and generic uplift?
- Did I replace generic academic phrasing with Management Science / M&SOM-attested wording and sentence frames?
- Did I preserve the user's notation, numbers, citations, result directions, and caveats?
- Did I avoid making the prose casual, chatty, or personality-driven?

## Attribution

The pattern catalog adapts [blader/humanizer](https://github.com/blader/humanizer) (MIT), itself based on [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) (WikiProject AI Cleanup). The academic-register calibration and the don't-overcorrect rules are specific to this skill.
