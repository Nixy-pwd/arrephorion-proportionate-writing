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

Write the Discussion paragraph for the following domain transportability audit result, for an academic paper.

Results:

- C1 (within-staff pitch geometry): C1_upper PASS and C1_lower PASS for the piece-balanced 1-Wasserstein distances between within-staff signed pitch-change distributions. Upper-staff U_95 = 240036791340624555456990153844098043482331401780857149230197438441785340490603265156233172440669974765389373264415809/364760413518331513857623884096142323366997589388595585394938737267630127201259881243581420041790409989398707177448000 semitones; lower-staff U_95 = 116260791564518041226140673362371598046578992599706713337865048250359458968510800985215537004437203893820793566002251/75797411044995598778169479056941193235579008185614795570560811975062743891035926498035685631858178748829022522450000 semitones. The frozen margin is 2/1 semitones for each criterion; PASS requires U_95 < margin.
- C2 (crossing conditional on non-separated cells): INCONCLUSIVE_BY_CONSTRUCTION, with three-way classification INCONCLUSIVE. The exact construction-gate reason is MARGIN_BELOW_WITHIN_CORPUS_VARIABILITY: the within-DEVELOPMENT n/2 reference 95th percentile is 23351539/46709676, meeting the frozen gate condition of reference 95th percentile >= margin, where the margin is 1/10 absolute probability difference. The reported cross-corpus absolute probability difference is 5533731245179/39857366530800, U_95 = 692338271/1860407325, and L_98.75 = 7704108823/2214298140600. These statistics are available, but the construction gate fixes the criterion as inconclusive and cannot independently trigger global failure.
- C3 (cross-staff pitch interval): FAIL for the piece-balanced 1-Wasserstein distance between complete signed boundary-gap distributions, where g = min(upper-staff pitches) - max(lower-staff pitches). L_98.75 = 163883152246033077298770301262101356549778642121141225294709937781505159673774589621391696257690554991/53216929287433966930146058106660849144007384749752373258537216925896640237382342402765893243248025600 semitones, exceeding the frozen margin of 3/1 semitones. The formal FAIL rule is L_98.75 > margin.
- Global verdict: DOMAIN_TRANSPORTABILITY_FAIL, determined by C3 FAIL. The frozen rule requires all four criteria (C1_upper, C1_lower, C2, C3) to PASS for global PASS; any FAIL produces global FAIL; no FAIL with at least one INCONCLUSIVE produces global INCONCLUSIVE. The FAIL-side bounds use Bonferroni family alpha 0.05 across four criteria, with alpha 0.0125 per criterion. The official conclusion status is PROVISIONAL_PENDING_PHASE_3B; Phase 3B parser and measurement-instrument validation has not been executed.

Interpret what these results mean for the method's transportability to the new domain.

Apply the supplied skill in full, including its list, variants, comparison table, and final question.
