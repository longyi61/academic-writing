---
name: utd-journal-writing
description: >-
  Write or revise academic prose in the style of top operations and management
  journals — Management Science, M&SOM, and Production and Operations Management
  (the UTD-24 journals) — using University of North Carolina Writing Center
  principles for flow, conciseness, paragraphs, and transitions. Use this skill
  whenever the user is drafting or polishing any part of an operations,
  management-science, or analytical-economics paper (introduction, model setup,
  results narration, intuition paragraphs, literature positioning, discussion),
  or asks to make academic text "read like Management Science / MSOM / POM,"
  tighten wordy prose, improve flow between sentences, or 润色 / 写 a paragraph for
  an OM/MS submission. Also use it to **de-AI / humanize / de-slop** an academic
  draft — strip the tells that make writing read as ChatGPT-generated and tighten
  it toward a precise, confident authorial voice. Trigger even when the user just
  pastes a rough paragraph and asks to "make this better," "make it sound less
  AI," or "remove the AI tone" in an academic-paper context.
---

# Writing for UTD operations/management journals

Top OM and management-science journals reward prose that is precise, economical, and easy to follow on the first read. A reviewer skims fast and is looking for reasons to stop. Good writing removes those reasons: each sentence lands one idea, each idea connects visibly to the last, and nothing makes the reader reread.

This skill produces and repairs that kind of prose. It works on any chunk of text the user gives you — a sentence, a paragraph, a section. Two entry points:

- **Revise**: the user pastes their own draft. Diagnose what breaks flow or wastes words, then rewrite. Preserve their claims and their notation exactly; change only how the prose carries them.
- **Draft**: the user gives notes, bullets, or an outline. Build paragraphs that argue, not lists that report.

**De-AI is always on, in both modes — not a separate service.** Every rewrite and every drafted paragraph must come out free of the tells that mark text as machine-written. This is a standing constraint on everything the skill produces, applied by default whether the user mentions AI tone or not. `references/de-ai.md` is the catalog of those tells; the most common ones (inflated significance, participial "-ing" tails, AI vocabulary, copula avoidance, rule-of-three cadence, vague attribution) should never survive into your output. When the user *explicitly* asks to "de-AI / humanize / de-slop," stripping these tells becomes the whole task and you should read the full reference; otherwise it is a quality gate on the revise/draft you were already doing. Either way the standard is identical. Critical for this genre: de-AI'ing means tightening toward a precise, confident author — naming mechanisms, stating exact claims — **never** loosening toward casual, first-person, opinionated blog voice. A general humanizer overcorrects here (hunting em-dashes, de-hyphenating compound modifiers, banning all signposting); the reference says exactly what to leave alone.

Default to a clean rewrite plus a short note on the two or three changes that mattered most, so the user learns the pattern rather than just taking the output.

When the text is an **introduction** — or the user is drafting, restructuring, or diagnosing one — read `references/introduction.md` first. These journals follow a stable six-move template for introductions (phenomenon → puzzle → earned questions → model preview → directional findings preview → novelty quarantined to the literature), and the prose guidance below sits on top of that structure. The reference covers structure; this file covers the sentences.

## The voice

Match how these journals actually sound:

- **"We" for what the authors do**: "We develop a model," "We show that," "We find." First-person plural is standard; first-person singular and contractions are not.
- **Present tense for results and model behavior**: "Proposition 1 shows that the optimal price increases in the holding cost." Not "showed," not "will show." The paper and its findings exist now. Cited prior findings also take the present ("Bertrand and Mullainathan show that…," "Edelman et al. find…"); reserve the past for what was physically *done* — data collection, the procedure of an earlier experiment.
- **Confident on results, calibrated on interpretation**: state propositions and headline numbers flatly. Hedge only the reach beyond them — "this suggests," "one explanation is," "appears to resemble" — and only when the hedge is real. The strongest papers hedge surgically: a result that is proven or precisely estimated is asserted; a causal leap or a claim about practice is qualified. A blanket "make it confident" or "make it cautious" pass flattens this asymmetry, which is often the argument's spine.
- **Calibrated self-claims, not scattered praise**: keep evaluative adjectives out of results narration — there, an exact number does the persuading ("achieves 66.9% of optimal in the worst case," "a 954% widening"). These journals *do* permit conventional contribution-framing in the contribution paragraph: "we are the first to," "a novel form of e-commerce," "important contributions," "a striking effect." So the tell is not the word "novel" itself; it is praise sprinkled through the body where a result should speak for itself. Confine the claims to the contribution paragraph and let figures carry the rest.
- **Define, then reuse — and name your mechanisms**: call a quantity by one name every time. Elegant variation ("the order quantity"… "the procurement level"… "the stocking decision" for one variable) makes the reader stop to check whether these are the same thing; in technical prose, repetition is clarity. Stronger still, *coin* a short label for a mechanism or construct and thread it through the paper as an anchor — these journals christen things (an *initial gap*, the platform's two *levers*, *information control*) and reuse the italicized label in every later section, so the reader always has a handle to grab.

## The flow engine: old information first

This is the single highest-leverage technique, and the one most rough drafts violate. Readers process familiar information faster than new information. So **open each sentence with something the reader already knows — usually an idea from the end of the previous sentence — and put the new information at the end.** This "old-to-new" chaining is what makes a paragraph feel like it pulls you forward instead of restarting every sentence.

Watch a chain form by making the new element of one sentence the subject of the next:

> The optimal order quantity is set by the critical ratio. **This ratio** depends on the relative size of the underage and overage costs. **When underage cost dominates**, the firm stocks aggressively to avoid lost sales.

Each sentence hands off its tail to the next. Compare the choppy version, where every sentence opens cold:

> The critical ratio sets the optimal order quantity. The relative size of the underage and overage costs matters. The firm stocks aggressively to avoid lost sales if underage cost is large.

Same facts, but the reader has to reassemble the thread each time.

When you revise for flow, the move is usually **reordering within the sentence**, not adding transition words. If a sentence feels disconnected, check what it opens with. If it opens with new information, find the known idea buried in its middle or end and move that to the front.

Use **"this"/"these" plus a summarizing noun** to carry an idea forward cleanly: not "This raises the price" (this *what*?) but "This substitution effect raises the price." The noun tells the reader exactly which thread you're picking up.

## Build every paragraph around a claim

A paragraph supports one idea. State that idea in the **first sentence as a claim, not a topic label.** "Next we consider the supplier's problem" announces a topic and commits to nothing. "The supplier prefers a wholesale-price contract to revenue sharing whenever demand is highly variable" makes a claim the rest of the paragraph can earn.

Then develop it. A reliable shape:

1. **Claim** — the topic sentence, stated as something that could be argued with.
2. **Support** — the analysis, the comparative static, the equation, the evidence.
3. **Why** — the intuition: in plain economic terms, *why* the result holds.
4. **Link** — hand off to the next paragraph.

The **intuition paragraph** is its own genre in these journals and worth singling out. After a proposition, readers want the mechanism in words — the economic force driving the math. Write it concretely: name the tradeoff, say which effect wins and why.

> The optimal price falls as competition intensifies. Two forces pull against each other. A lower price sacrifices margin on each unit, but it also defends market share against the rival. As the rival grows more aggressive, the share at risk grows faster than the margin given up, so the firm cuts price.

A close cousin worth keeping in the toolkit is the **concrete toy example** — a stripped-down numerical case that makes a mechanism visible before any formula. These journals lean on it constantly: "Consider two customers: A buys nothing without the service and one unit with it; B buys nine units without and ten with. Both show the same one-unit lift, so an effect-only rule ranks them equally — yet serving A consumes a tenth of the capacity, so A should come first." Two named cases and small integers do what a paragraph of abstract description cannot. Reach for it whenever the intuition turns on a comparison the reader can hold in their head.

Start a new paragraph when the controlling claim changes. A paragraph running past half a page usually holds two claims that want to separate.

## Cut to the bone

Wordiness buries the idea and signals that the author didn't reread. Cut on sight:

- **Wordy openers → one word**: "due to the fact that," "in light of the fact that," "for the reason that" → *because*. "in the event that" → *if*. "for the purpose of" → *to*. "it is necessary that the firm holds" → *the firm must hold*.
- **Expletive starts**: "There exists an equilibrium in which firms…" → "In equilibrium, firms…". "It is the case that demand is censored" → "Demand is censored." These "there is / it is" openers push the real subject to the back.
- **Nominalizations back into verbs**: "make an assumption that" → *assume*; "provides an explanation for" → *explains*; "the determination of the price is" → *the price is determined* (better: "we determine the price"). Buried verbs lengthen the subject and hide the action.
- **Empty qualifiers**: "very," "quite," "rather," "basically," "somewhat," "in nature," "really." "demand is stochastic in nature" → "demand is stochastic."
- **Redundant pairs**: "each and every," "first and foremost," "full and complete" — keep one.
- **Prefer active voice** when the actor matters: "The model is solved by backward induction" → "We solve the model by backward induction." Passive is fine when the actor is irrelevant or obvious ("The proofs are relegated to the appendix").

Run-on example, before and after:

> Due to the fact that demand is stochastic in nature, it is necessary that the firm holds a certain amount of safety stock in order to protect against the possibility of stockouts.

> Because demand is stochastic, the firm holds safety stock to protect against stockouts.

## Transitions carry logic, not decoration

A transition tells the reader what to do with the next sentence — add to, contrast with, or conclude from the last one. Use the word that names the true relationship: *however* / *yet* for genuine contrast, *therefore* / *thus* / *hence* for consequence, *moreover* / *furthermore* for addition, *for instance* / *specifically* for example.

But the strongest transitions are not words at all. They are **repeated key terms and old-to-new chaining** (above). A paragraph whose sentences share a vocabulary thread coheres without needing "Furthermore" bolted to the front of every line. Reach for a transition word when the logical turn would otherwise be invisible; don't sprinkle them as filler.

## Avoid these tells

These mark writing as unpolished or machine-generated, and reviewers notice:

- **The "not X, but Y" reflex used as filler** ("X is not just A; it is B," "rather than merely…"). The test is whether the negated clause is load-bearing. When X is a strawman or empty drama, cut it: "The contract coordinates the channel" beats "The contract does not merely shift risk; it coordinates the channel" — nobody claimed it only shifts risk. But the construction is legitimate, even powerful, when X names a *genuine prevailing view the paper overturns* and the contrast is the contribution: "last-mile delivery is not merely a cost center but also a revenue driver" works precisely because the field treats it as a pure cost — stating Y alone would throw away the reframe. So spend the construction on a real foil, ideally the headline contribution, and not as a sentence-level rhythm habit.
- **Hype adjectives loose in the body**: "crucial," "powerful," "rich," "fascinating," "very significant" dropped onto results as you narrate them. Replace with the specific thing or a number. (This is about placement, not vocabulary — a calibrated "we are the first to" or "a novel form of" in the contribution paragraph is standard; see "The voice.")
- **Contentless throat-clearing**: "It is worth noting that," "Interestingly," "It is important to point out that" when what follows carries no weight. Be careful here: *functional* signposting is expected and good in these journals, not a tell. The roadmap paragraph ("We organize the paper as follows…"), "Note that [a real fact the reader would miss]," "Recall that (7)…," and "In this section we examine…" all earn their place by pointing at something specific. Cut the signpost only when it points at nothing.
- **Three-item lists as a rhythm habit**: triads everywhere ("efficient, scalable, and robust") read as cadence-filling. Use the items the argument actually needs.
- **Throat-clearing openers**: "In today's competitive environment," "Over the past decades." Open on the actual point.
- **Vague "this" / "it"** with no referent. Always anchor with a noun.

These are the tells that surface most in OM/MS drafts. For a fuller catalog — inflated significance, participial "-ing" tails, AI vocabulary, copula avoidance, vague attribution, and the rules a generic de-AI pass gets *wrong* for this genre — see `references/de-ai.md`. Read it whenever the task is explicitly to strip AI tone, not just polish.

## Workflow

**Revising:** Read the passage for the one or two things that hurt it most — usually flow (sentences opening cold) and wordiness. Rewrite the whole passage clean. Keep the author's notation, claims, and structure; change the prose. Then tell the user the key moves you made and why, in two or three lines, so the lesson transfers.

**Drafting:** Turn each notes-cluster into a claim-first paragraph (claim → support → intuition → link). Don't pad to hit a length; if the notes only support two sentences, write two good ones. Surface anything the notes leave genuinely ambiguous rather than inventing a result.

Read your output once more before returning it, every time, checking three things: sentences that open with new information (fix the flow), any word that could be cut without loss (tighten), and the machine-written tells in `references/de-ai.md` — inflated significance, "-ing" tails, AI vocabulary, copula avoidance, vague attribution. Ask yourself plainly, "what here still reads as AI-generated?" and revise it out. This de-AI pass runs on drafts and revisions alike; it is not optional. Those passes catch most of what separates a draft from publishable prose.
