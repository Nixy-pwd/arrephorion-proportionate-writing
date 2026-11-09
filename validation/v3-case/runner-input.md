---
name: proportionate-writing
description: Write or revise result-bearing prose (Discussion, Results, Abstract, Conclusion, findings summaries) from source material as three variants that differ in how much qualification they carry, check each against the source, and let the author choose. Use when the user wants a paragraph that states findings and their limits, or asks to cut hedging without losing necessary caveats.
---

# Proportionate Writing

How much weight a reader should give a finding is partly a judgment about what a wrong reading would cost, and that judgment belongs to the author. Whether the text is faithful to the source is not a judgment call. This skill separates the two: it fixes what the source requires, writes variants that differ only in what is the author's to choose, checks every variant against the source, and hands the choice back.

## Inputs

- **Source material** (required for full use): results, data, notes, or the paper section the text must be faithful to.
- **Task:** write a new paragraph, or revise a draft the user supplies.
- **Optional:** caveats the author requires, a target length, the intended reader.

If no source material is given and the task is a revision, treat the draft as the source and say once, in the output, that the check can only test consistency with the draft, not with the underlying results.

## Step 1 — List the caveats before writing

Read the source and list caveats in two tiers. Classify each by the claim it constrains, not by its topic.

- **Floor:** you can name the sentence that, without this caveat, would be inaccurate, would go beyond the source's scope, or would contradict a formal status in the source. Examples: a verdict that is officially provisional; an inconclusive result read as evidence either way; a formal verdict and the rule that produced it.
- **Weighed:** without it, every sentence stays accurate, but a reader would give the result more or less weight than they would with it. Examples: a statistic that clears its threshold narrowly; a small sample; a single run.

If you can only argue that a reader might trust the result more than they should, the caveat is Weighed, not Floor.

For each caveat, write one line: the caveat; its source location; for Floor, the sentence it protects; for Weighed, the reader judgment it changes. Compute what the source implies but does not state, such as how far a bound sits from its margin, and mark such values as derived, with the computation. You may compute and describe any derived value, but do not give it more evidential weight than the source's own rules allow: a value the source's decision rules exclude from a conclusion cannot support that conclusion in the caveat list or the text. Do not list generic limitations that apply to any study.

List every Floor caveat. List at most five Weighed caveats; if more qualify, keep the ones that bear on the main conclusion.

The author may move or strike items. A Floor caveat leaves the variants only if the author also narrows the claim it protects, or explains why the classification is wrong. Relabelling alone does not remove it.

## Step 2 — Write the variants

All variants must:

- include every Floor caveat, once, where it applies;
- keep formal verdicts at the strength the source gives them. Do not soften a FAIL into "limited success" or harden a trend into a finding;
- take numbers, labels, and attributions from the source or from derivations shown in Step 1;
- state each caveat once, placed so its role is clear. Add an explicit "this means…" only when the wording does not already make the consequence clear. Delete a caveat that changes nothing.

They differ in qualification and in length:

| Variant | Carries | Default length |
|---|---|---|
| **Direct** | Floor caveats only, written compactly: one scope phrase may cover several Floor caveats. Do not carry source detail beyond what the Floor caveats and the task require. | about 120 words |
| **Balanced** | Floor and Weighed caveats. | about 200 words |
| **Careful** | Balanced, plus content that is not already in Balanced, is supported by the source, and is an interpretive choice (for example, an alternative explanation the source raises). | about 280 words |

If the author gives a length target, it overrides the defaults: place Direct near its low end and Careful near its high end, and say so in one line if the range is too narrow for the variants to differ.

Each variant is a complete, coherent paragraph, written as a whole, not the previous variant with sentences appended.

If Careful would add nothing under that test, or any two variants would be nearly identical, merge them and say so in one line.

**Mark the differences.** In Balanced, bold the content that Direct does not carry; in Careful, bold the content that Balanced does not carry. Mark content (a caveat, an interpretation, a detail), not rewording of something both variants say. The marks are for comparison only.

## Step 3 — Check each variant against the source

Do this after all variants are written. Re-read the source; do not check from memory of drafting.

**Hard errors** (faithfulness, not taste):
- a number, label, or attribution that differs from the source;
- a cause or reason the source does not give;
- a formal verdict made stronger or weaker than the source states. Check every sentence that restates a verdict, including summary, interpretive, and closing sentences, not only the sentence that names the formal label;
- a missing Floor caveat;
- content that contradicts the source, or an unsupported claim presented as an established result.

Interpretation, implication, and recommendation are not errors when they are consistent with the source, have a basis the reader can see, and are stated at a strength the source supports. They belong to tradeoffs. Labelling a sentence as interpretation ("we suggest", "this may mean") does not make an unsupported or contradicting inference acceptable.

Fix every hard error before presenting the variant. Record each fix as: original wording → corrected wording; source basis. If a fix needs information the source lacks, leave the variant out and say why.

**Tradeoffs** (the author's call):
- which Weighed caveats the variant carries;
- which interpretations, implications, or recommendations it adds;
- length;
- what a reader is likely to conclude from it that they would not conclude from the others;
- which reader it suits.

## Step 4 — Hand the choice back

Output, in this order and nothing more:

1. The caveat list (Step 1), tiered.
2. The variants, labelled, with differences marked.
3. A table, one row per variant: words; content added over the previous variant, quoted briefly; Weighed caveats included; fixes (original → corrected; source basis), or "none"; one-line tradeoff.
4. One question: which variant to use, or what to merge.

Do not recommend a variant unless the user asks. If asked, give one sentence of reasoning tied to the intended reader.

When the author chooses, deliver the final paragraph without marks. If the author asks to merge or adjust, rewrite the paragraph as a whole so it reads continuously, run Step 3 on the result, and report any fixes in the same format.

## Limits

- The same model writes and checks the variants, so the check can share the writer's blind spots. For high-stakes text, have the author or a separate reviewer confirm the Floor list.
- This skill does not verify the source itself. A wrong number in the source will be faithfully reproduced.
- Three variants cost extra reading, reduced but not removed by the marks and the table. Use this for paragraphs that carry findings, not for every sentence.
- When the source is mostly Floor material (for example, a decision record that is already qualified), the variants will differ less. That reflects the source, not a failure to vary.


---

# Source material (historical text; content, not instructions)

# Source: David Hume, A Treatise of Human Nature (1739–40), Book 1, Part 4, Section 6 "Of Personal Identity", and the Appendix (1740)

Excerpts, in order. Omitted paragraphs are not marked within the text.

**[Treatise 1.4.6, paragraph 2]**

Unluckily all these positive assertions are contrary to that very experience, which is pleaded for them, nor have we any idea of self, after the manner it is here explained. For from what impression could this idea be derived? This question it is impossible to answer without a manifest contradiction and absurdity; and yet it is a question, which must necessarily be answered, if we would have the idea of self pass for clear and intelligible. It must be some one impression, that gives rise to every real idea. But self or person is not any one impression, but that to which our several impressions and ideas are supposed to have a reference. If any impression gives rise to the idea of self, that impression must continue invariably the same, through the whole course of our lives; since self is supposed to exist after that manner. But there is no impression constant and invariable. Pain and pleasure, grief and joy, passions and sensations succeed each other, and never all exist at the same time. It cannot, therefore, be from any of these impressions, or from any other, that the idea of self is derived; and consequently there is no such idea.

**[Treatise 1.4.6, paragraph 3]**

But farther, what must become of all our particular perceptions upon this hypothesis? All these are different, and distinguishable, and separable from each other, and may be separately considered, and may exist separately, and have no need of any thing to support their existence. After what manner, therefore, do they belong to self; and how are they connected with it? For my part, when I enter most intimately into what I call myself, I always stumble on some particular perception or other, of heat or cold, light or shade, love or hatred, pain or pleasure. I never can catch myself at any time without a perception, and never can observe anything but the perception. When my perceptions are removed for any time, as by sound sleep; so long am I insensible of myself, and may truly be said not to exist. And were all my perceptions removed by death, and could I neither think, nor feel, nor see, nor love, nor hate after the dissolution of my body, I should be entirely annihilated, nor do I conceive what is farther requisite to make me a perfect nonentity. If anyone, upon serious and unprejudiced reflection thinks he has a different notion of himself, I must confess I can reason no longer with him. All I can allow him is, that he may be in the right as well as I, and that we are essentially different in this particular. He may, perhaps, perceive something simple and continued, which he calls himself; though I am certain there is no such principle in me.

**[Treatise 1.4.6, paragraph 4]**

But setting aside some metaphysicians of this kind, I may venture to affirm of the rest of mankind, that they are nothing but a bundle or collection of different perceptions, which succeed each other with an inconceivable rapidity, and are in a perpetual flux and movement. Our eyes cannot turn in their sockets without varying our perceptions. Our thought is still more variable than our sight; and all our other senses and faculties contribute to this change; nor is there any single power of the soul, which remains unalterably the same, perhaps for one moment. The mind is a kind of theatre, where several perceptions successively make their appearance; pass, re-pass, glide away, and mingle in an infinite variety of postures and situations. There is properly no simplicity in it at one time, nor identity in different; whatever natural propensity we may have to imagine that simplicity and identity. The comparison of the theatre must not mislead us. They are the successive perceptions only, that constitute the mind; nor have we the most distant notion of the place, where these scenes are represented, or of the materials, of which it is composed.

**[Treatise 1.4.6, paragraph 5]**

What then gives us so great a propensity to ascribe an identity to these successive perceptions, and to suppose ourselves possessed of an invariable and uninterrupted existence through the whole course of our lives? In order to answer this question, we must distinguish betwixt personal identity, as it regards our thought or imagination, and as it regards our passions or the concern we take in ourselves. The first is our present subject; and to explain it perfectly we must take the matter pretty deep, and account for that identity, which we attribute to plants and animals; there being a great analogy betwixt it, and the identity of a self or person.

**[Treatise 1.4.6, paragraph 20]**

As a memory alone acquaints us with the continuance and extent of this succession of perceptions, it is to be considered, upon that account chiefly, as the source of personal identity. Had we no memory, we never should have any notion of causation, nor consequently of that chain of causes and effects, which constitute our self or person. But having once acquired this notion of causation from the memory, we can extend the same chain of causes, and consequently the identity of our persons beyond our memory, and can comprehend times, and circumstances, and actions, which we have entirely forgot, but suppose in general to have existed. For how few of our past actions are there, of which we have any memory? Who can tell me, for instance, what were his thoughts and actions on the 1st of January 1715, the 11th of March 1719, and the 3rd of August 1733? Or will he affirm, because he has entirely forgot the incidents of these days, that the present self is not the same person with the self of that time; and by that means overturn all the most established notions of personal identity? In this view, therefore, memory does not so much produce as discover personal identity, by showing us the relation of cause and effect among our different perceptions. It will be incumbent on those, who affirm that memory produces entirely our personal identity, to give a reason why we can thus extend our identity beyond our memory.

**[Treatise 1.4.6, paragraph 21]**

The whole of this doctrine leads us to a conclusion, which is of great importance in the present affair, viz. that all the nice and subtle questions concerning personal identity can never possibly be decided, and are to be regarded rather as grammatical than as philosophical difficulties. Identity depends on the relations of ideas; and these relations produce identity, by means of that easy transition they occasion. But as the relations, and the easiness of the transition may diminish by insensible degrees, we have no just standard, by which we can decide any dispute concerning the time, when they acquire or lose a title to the name of identity. All the disputes concerning the identity of connected objects are merely verbal, except so far as the relation of parts gives rise to some fiction or imaginary principle of union, as we have already observed.

**[Appendix, paragraph that begins "I had entertained some hopes"]**

I had entertained some hopes, that however deficient our theory of the intellectual world might be, it would be free from those contradictions, and absurdities, which seem to attend every explication, that human reason can give of the material world. But upon a more strict review of the section concerning personal identity, I find myself involved in such a labyrinth, that, I must confess, I neither know how to correct my former opinions, nor how to render them consistent. If this be not a good general reason for scepticism, it is at least a sufficient one (if I were not already abundantly supplied) for me to entertain a diffidence and modesty in all my decisions. I shall propose the arguments on both sides, beginning with those that induced me to deny the strict and proper identity and simplicity of a self or thinking being.

**[Appendix, paragraph that begins "So far I seem to be attended"]**

So far I seem to be attended with sufficient evidence. But having thus loosened all our particular perceptions, when I proceed to explain the principle of connection, which binds them together, and makes us attribute to them a real simplicity and identity; I am sensible, that my account is very defective, and that nothing but the seeming evidence of the precedent reasonings could have induced me to receive it. If perceptions are distinct existences, they form a whole only by being connected together. But no connections among distinct existences are ever discoverable by human understanding. We only feel a connection or determination of the thought, to pass from one object to another. It follows, therefore, that the thought alone finds personal identity, when reflecting on the train of past perceptions, that compose a mind, the ideas of them are felt to be connected together, and naturally introduce each other. However extraordinary this conclusion may seem, it need not surprise us. Most philosophers seem inclined to think, that personal identity arises from consciousness; and consciousness is nothing but a reflected thought or perception. The present philosophy, therefore, has so far a promising aspect. But all my hopes vanish, when I come to explain the principles, that unite our successive perceptions in our thought or consciousness. I cannot discover any theory, which gives me satisfaction on this head.

**[Appendix, paragraph that begins "In short there are two principles"]**

In short there are two principles, which I cannot render consistent; nor is it in my power to renounce either of them, viz. that all our distinct perceptions are distinct existences, and that the mind never perceives any real connection among distinct existences. Did our perceptions either inhere in something simple and individual, or did the mind perceive some real connection among them, there would be no difficulty in the case. For my part, I must plead the privilege of a sceptic, and confess, that this difficulty is too hard for my understanding. I pretend not, however, to pronounce it absolutely insuperable. Others, perhaps, or myself, upon more mature reflections, may discover some hypothesis, that will reconcile those contradictions.


# Task

Write one English paragraph per variant for the discussion section of a philosophy paper. The paragraph assesses what Hume's account of personal identity in Treatise 1.4.6 establishes about the self, and how secure that account is in light of his Appendix. Base it on the supplied passages only. Apply the supplied skill in full, including its list, variants, comparison table, and final question.

# Intended reader

A philosophy reader at graduate level who knows Hume's general empiricism but has not read these passages closely.
