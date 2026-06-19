# Stripping AI tells from journal prose

Load this when the user wants to **de-AI / humanize / de-slop** academic text — "make this sound less like ChatGPT," "remove the AI tone," "this reads like it was generated." The goal is the same prose the rest of this skill describes: precise, economical, confidently authored. This file is the diagnostic checklist for the specific patterns that mark a draft as machine-written.

## What "de-AI" means for a journal paper — and what it does not

For a blog post, de-AI'ing means adding voice: opinions, humor, first-person, a little mess. **Do not do that here.** A journal paper's "human" signal is not personality — it is a competent author making exact claims, naming mechanisms, and explaining intuition. Removing AI slop from a paper means tightening toward that authorial voice, not loosening toward conversational voice. So: no "I genuinely think," no rhetorical questions for effect, no jokes, no tangents. The fix for sloppy AI prose in this genre is always *more precise and more confident*, never *more casual*.

## The tells that matter most in academic writing

Each is the AI pattern, why it reads as machine-written, and the journal fix. Several are already covered in SKILL.md (conciseness, hedging, triads, define-and-reuse, the "not X but Y" test) — this file adds the ones the core file doesn't name and sharpens the rest into a scan.

1. **Inflated significance.** "plays a crucial/pivotal role," "underscores the importance of," "has far-reaching implications," "in an increasingly complex and dynamic landscape," "is a critical area of growing interest." LLMs puff up importance instead of stating a claim. → State the specific thing: "The holding cost determines the order quantity" beats "The holding cost plays a pivotal role in shaping inventory outcomes."

2. **Participial tails of fake depth.** A clause ending in "…, highlighting the importance of …", "…, reflecting the complex interplay between …", "…, thereby contributing to …", "…, underscoring the need for …". These "-ing" tags add the *shape* of analysis without content. → Cut the tail, or turn it into a real clause that says something: "…, which raises the retailer's margin by 4%."

3. **AI vocabulary.** *delve, intricate, interplay, tapestry, leverage* (as filler), *underscore, pivotal, crucial, nuanced* (as filler), *robust* (as a vague compliment), *holistic, multifaceted, realm, landscape* (abstract), *navigate* (figurative), *foster, garner, showcase, testament, vibrant*. They co-occur and spike in post-2023 text. → Replace each with the specific word the sentence needs. "robust to misspecification" is fine (technical); "a robust framework" is filler.

4. **Copula avoidance.** "serves as," "stands as," "acts as," "represents," "constitutes" where "is" would do. → "The critical ratio is the cutoff" beats "The critical ratio serves as the cutoff." (Keep "represents" only when it means a genuine mapping, e.g., "Z represents the indicator.")

5. **Vague attribution / weasel words.** "Studies have shown," "It is widely believed," "Researchers argue," "Prior work suggests" with no citation, or "several papers" when you cite two. Deadly in a literature review. → Name the source and the finding: "Cui et al. (2020) show that removing a high-quality delivery option cut sales."

6. **Persuasive-authority tropes.** "The real question is," "At its core," "Fundamentally," "More importantly," "It is worth emphasizing that," "What truly matters is." These pretend to cut to a deeper truth, then restate an ordinary point. → Delete the windup and make the point.

7. **Generic upbeat closings.** "opens exciting new avenues," "paves the way for," "holds great promise for," "represents a significant step forward." → End on a concrete claim or a specific open question. (Calibration: applied/empirical papers in these journals tolerate *one* mildly elevated closing line — "win the last mile of e-commerce" — but it reads as AI the moment it's generic or stacked. One earned sentence, never a paragraph of uplift.)

8. **Stacked hedging.** "may potentially," "could possibly suggest," "it might be argued that perhaps." → One hedge, placed surgically (see SKILL.md "Confident on results, calibrated on interpretation"). "may affect," not "may potentially affect."

9. **Elegant variation.** Naming one construct three ways ("the order quantity"… "the procurement level"… "the stocking decision"). AI's repetition penalty drives this. → Pick one term, repeat it. (This is the SKILL.md "define, then reuse" rule; AI text violates it constantly.)

10. **Rule of three as cadence.** "efficient, scalable, and robust," "practical value, generalizability, and effectiveness." → Use the items the argument needs — often one or two. (SKILL.md "Avoid these tells.")

11. **Filler openers.** "It is important to note that," "It should be emphasized that," "In order to," "Due to the fact that," "It is widely recognized that." → Cut or compress (SKILL.md "Cut to the bone"). Distinguish from *functional* signposting ("Note that [a real fact]," "Recall that (7)…"), which is correct here — see the don't-overcorrect list.

12. **Formatting tells.** Title-Case Section Headings In The Body, **bold phrases** sprinkled mid-paragraph, inline-header bullet lists ("- **Performance:** the system is faster"), emojis, and chatbot residue ("Here is an overview…," "I hope this helps," "Certainly!"). → Sentence-case headings, prose instead of bolded lists, no emojis, no correspondence artifacts. (Note: these journals *do* title-case actual section titles — that's house style, not a tell. The tell is title-case and boldface used decoratively inside the text.)

## Don't overcorrect — where journal style diverges from generic de-AI

A naive de-AI pass (or running a general humanizer on a paper) breaks these. Leave them alone:

- **Em-dashes are fine.** These journals use them freely; do not hunt them. Only fix a dash that should be a period because the sentence is doing too much.
- **Hyphenated compound modifiers are correct.** "high-quality logistics," "data-driven decision," "first-difference estimator," "two-sided market" — keep the hyphens. Generic humanizers strip them; that is wrong here.
- **Functional signposting stays.** "Note that," "Recall that," "We organize the paper as follows," "In this section we…" earn their place. Cut only contentless throat-clearing. (See SKILL.md.)
- **"Not X but Y" can stay when load-bearing.** Banned only as empty rhythm; legitimate when X is a real prevailing view the paper overturns. (See SKILL.md.)
- **First-person *plural* "we" stays; do not switch to "I" or to casual voice.** The humanizer instinct to "add first-person honesty" is wrong for this genre.
- **Calibrated contribution adjectives stay in the contribution paragraph.** "we are the first to," "a novel form of" are house style there; strip such adjectives only when scattered through the body. (See SKILL.md "The voice.")
- **Curly vs. straight quotes don't matter** in a LaTeX/typeset paper; ignore.

## The audit loop

After a de-AI rewrite, run one explicit pass borrowed from the humanizer method:

1. Ask yourself plainly: **"What in this still reads as machine-written?"** List the remaining tells in a line or two.
2. Revise once more to kill them.
3. Read the result against the target: does it sound like a confident author stating exact claims, or like fluent filler? If filler, the problem is usually missing content, not bad wording — say what's actually true instead of smoothing the vagueness.

Report the two or three highest-value changes, as the main workflow prescribes.

## Attribution

The pattern catalog adapts [blader/humanizer](https://github.com/blader/humanizer) (MIT), itself based on [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) (WikiProject AI Cleanup). The academic-register calibration and the don't-overcorrect list are specific to this skill.
