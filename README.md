# Arrephorion — Proportionate Writing

English · [中文](README.zh-CN.md)

A writing skill against defensive writing in result-bearing prose: fewer caveats that change nothing for the reader, without losing the ones that do.

It lists the caveats your source material supports, separates the ones faithfulness requires from the ones that are your call, writes three variants that differ only in the latter, checks each against the source, and asks you to choose.

**Status:** draft v0.3. In a blind-scored comparison, the skill's output had fewer repeated caveats and was a third shorter than the same models without it, with no necessary caveat lost (one material, one run per configuration: suggestive, not established). Works reliably in Codex and ChatGPT work mode; not recommended in ChatGPT chat. Details under [Evidence](#evidence).

## What it is for

**Defensive writing** is qualification that protects the writer rather than informs the reader:

- the same limitation restated in different words;
- generic disclaimers that change no interpretation;
- stacked hedges on one claim;
- disclaimers aimed at an imagined reviewer.

It is **not**: a qualification that changes what the reader may conclude, a clear line between evidence and inference, or an accurate statement of real uncertainty.

The test for every caveat: **name the reader judgment it changes, or delete it.**

Success has two parts, and both are required:

1. **Goal:** fewer decorative caveats.
2. **Guard:** no necessary caveat lost, and no claim made stronger than the source allows in the process.

Fewer caveats alone is not success. A tool that cuts hedging can also cut the caveat that keeps a sentence true.

## Examples

Real outputs from three cases, quoted verbatim with emphasis removed. Each compares the same model, source, and task with and without the full skill.

### Case 1 — Hume on personal identity (humanities; with vs without the full skill)

**Repetition (goal).** Without the skill (ChatGPT work mode), one paragraph says the positive account is incomplete at the start, in the middle, and at the end:

> Hume’s account in Treatise 1.4.6 provides a stronger basis for rejecting an experientially warranted conception of a simple, enduring self than for accepting his explanation of the unity of perceptions.
>
> It nevertheless leaves the positive account insecure, since appealing to connected perceptions cannot complete the explanation while their connection in consciousness remains unresolved.
>
> The resulting position is thus an enduring challenge to the simple self accompanied by an acknowledged failure to explain fully the unity attributed to its perceptual succession.

With the skill (same configuration), the limitation is stated once, where it applies:

> These considerations do not resolve the Appendix’s difficulty: Hume cannot reconcile perceptions’ distinct existence with the mind’s inability to perceive real connections among them, and finds no satisfactory account of their union in consciousness.

**A necessary caveat lost (guard).** The source says memory "does not so much produce as discover personal identity" (1.4.6.20), a comparison. Without the skill (ChatGPT chat), the comparison becomes a flat denial:

> Memory plays a central role in this process, not by producing identity itself, but by revealing connections among past perceptions …

With the skill (work mode; the Codex version keeps the same scope), the comparison survives:

> Memory reveals causal relations among perceptions, enabling identity to extend beyond remembered episodes rather than constituting it entirely (1.4.6.20).

### Case 2 — PM2S domain-transportability audit (empirical results; with vs without the full skill)

A statistical audit of a MIDI-to-score method on a new corpus. Formal verdict DOMAIN_TRANSPORTABILITY_FAIL, decided by criterion C3, whose lower bound (≈3.0795) clears its 3-semitone margin by about 2.65%; status PROVISIONAL_PENDING_PHASE_3B. Both conditions run in Codex, from the same frozen facts.

**Repetition and pre-emptive disclaimers (goal).** Without the skill, the provisional status is stated, then restated, and the paragraph adds disclaimers about things the source does not address (downstream performance, "every application of the method"):

> These findings suggest that compatibility of within-staff pitch motion is insufficient to justify transferring assumptions about cross-staff organization, but they do not directly establish a loss of downstream task performance.
>
> Crucially, the official conclusion remains provisional pending Phase 3B parser and measurement-instrument validation.
>
> Until that validation is completed, the observed discrepancy cannot be attributed confidently to domain differences alone, and the result should be interpreted as a provisional failure of the specified transportability audit rather than a definitive rejection of every application of the method in the new domain.

With the skill (Balanced), the status is stated once and nothing is added that the source does not support:

> The official conclusion remains PROVISIONAL_PENDING_PHASE_3B, with parser and measurement-instrument validation not yet executed.

**The caveat nobody wrote (guard).** How narrowly C3 failed is something a reader needs to judge how robust the failure is; the author had required it in advance. Without the skill, and in all six outputs of the earlier B1 experiment, it is never stated. The skill computes it from the exact fractions, lists it as a Weighed caveat ("The excess is small, although the formal FAIL remains unchanged"), and the Balanced variant states it without softening the verdict:

> This lower bound was approximately 3.07953 semitones, only 0.07953 semitones above the margin.

### Case 3 — Linux VM sandbox gate (engineering decision record; with vs without the full skill)

A closure record for an architecture gate testing a Codex agent's permission profile in a Linux VM; status "CLOSED — CRITERIA PARTIALLY MET; OWNER PROCEEDS ON LIMITED EVIDENCE". Both conditions run in Codex.

Here the output without the skill was already clean: every limitation stated once, nothing overstated, no content errors. The record itself is fully qualified, so there was little defensive writing to remove. What the skill adds on such material is the choice: which limitations are required, and which are the author's call.

| Content | Without skill (238 words) | Direct (171) | Balanced (219) | Careful (280) |
|---|:-:|:-:|:-:|:-:|
| Status "criteria partially met"; B-plus conditional, not certified | ✓ | ✓ | ✓ | ✓ |
| Tested scope; 9/9 denials; patch attempts failed at the verification read | ✓ | ✓ | ✓ | ✓ |
| SSH-on run, original SSH-off condition unmet | ✓ | ✓ | ✓ | ✓ |
| Stage A incomplete; Stages B/C and pilot on hold; no further Gate session; reopen condition | ✓ | ✓ | ✓ | ✓ |
| Historical tool-definition set unrecovered | ✓ | | ✓ | ✓ |
| Audit did not independently inspect the original artifacts | ✓ | | ✓ | ✓ |
| `network=restricted` does not show host-service isolation | ✓ | | | ✓ |
| Ordinary SSH shell could read the same files; canary hashes unchanged | ✓ | | | ✓ |

Without the skill, the reader gets one paragraph with everything in it. With the skill, the first four rows are fixed in every variant, and the last four are the author's to include or leave out.

### What you get back

The skill returns its caveat list, three variants with additions in bold, and a table like this (abridged from a work-mode run on the Hume case):

| Variant | Words | Added over previous variant |
|---|---:|---|
| Direct | 121 | Baseline |
| Balanced | 199 | "no underlying stage"; "absence of a precise standard" and its exception |
| Careful | 272 | "separating uncertainty" about naming from unity; "felt transition" versus real connection; "explanatory gap" reading |

## Why variants

Two questions get mixed up when a model edits hedging:

- **Is the text faithful to the source?** Not a matter of taste. A softened formal verdict or a dropped "provisional" status is an error.
- **How much weight should a reader give the result?** Partly a value judgment about what a wrong reading would cost. A narrow margin or a small sample can reasonably be foregrounded or left out, depending on the reader.

In the tools we reviewed, the default workflow answers both at once and returns one edited version. This skill fixes the first and hands the second to the person who answers for the text.

## How it works

1. **List caveats, in two tiers.** A caveat is **Floor** if you can name the sentence it protects: without it, that sentence would be inaccurate, go beyond the source, or contradict a formal status. Otherwise it is **Weighed**: every sentence stays accurate, but the reader's sense of how much to trust the result changes. The skill computes what the source implies but does not state, such as how close a bound sits to its margin, and shows the computation.
2. **Write the variants.** Direct (Floor only, written compactly, about 120 words), Balanced (Floor + Weighed, about 200), Careful (adds source-supported interpretive content not already in Balanced, about 280, or merged away if there is none). Each is a complete paragraph written as a whole. All keep formal verdicts at source strength and state each caveat once. Content each variant adds over the previous one is in bold.
3. **Check each variant against the source.** Hard errors are fixed before you see them and logged as original → corrected, with the source basis. Tradeoffs are described.
4. **Hand back the choice.** Caveat list, marked variants, a table quoting what each variant adds, and one question. Once you choose or ask for a merge, the skill delivers a clean, continuous paragraph and re-checks it. You can move items between tiers, but a Floor caveat only leaves the text if the claim it protects is narrowed too.

Full instructions: [skills/proportionate-writing/SKILL.md](skills/proportionate-writing/SKILL.md). It works as a Claude Code or Codex skill, or pasted into a chat.

## Where to run it

Tested configurations, with results on two materials: [CONFIGURATIONS.md](CONFIGURATIONS.md). In short: use Codex (Sol 6.1, high) or ChatGPT work mode (Astra 6, light); ChatGPT chat (Sol 6, high) is not recommended, because it appended to earlier variants instead of rewriting them, did not mark differences, and made the one content error observed. Also listed: three things to check if you use another configuration.

## Use it for

Discussion, Results, Abstract, and Conclusion paragraphs, and findings summaries, where a reader will act on what the text claims. Three variants cost extra reading, so it is not meant for every sentence.

## Evidence

### Against the goal: with vs without the skill

Hume on personal identity; same source, task, and reader; three configurations; the skill's Balanced variant against the no-skill paragraph; blind-scored by a second model against a reference fixed before any no-skill output existed. [validation/v4-baseline/result.md](validation/v4-baseline/result.md)

| | Without skill | With skill |
|---|---|---|
| Repeated caveats (goal) | 3 | 1 |
| Words | 876 | 590 |
| Necessary caveats missing (guard) | 1 | 0 |
| Content errors (guard) | 2 | 0 |

- **Goal met:** fewer repeated caveats, about a third shorter.
- **Guard held:** all necessary caveats kept, no errors. In Codex and work mode both conditions were faithful; the guard failures without the skill came from ChatGPT chat.
- **Limits:** one material, one run per configuration, one scorer. The skill's paragraphs were shorter, so the scorer could have guessed which were which.

This matches the earlier B1 experiment, where the skill's caveat rule alone (an earlier, stricter version) made all three outputs less redundant than all three without it, with no relative loss of limitations ([EVIDENCE.md](EVIDENCE.md)).

### Guard on new material

- **Technical decision record** (an architecture gate closure, [validation/v2-case/](validation/v2-case/)): no content errors in Codex or work mode; the formal status "closed, criteria partially met" was never restated as a pass.
- **Humanities interpretation** (Hume, [validation/v3-case/](validation/v3-case/)): no content errors in Codex or work mode; ChatGPT chat stated memory's role too strongly. One scorer disagreement on that sentence is recorded.

### Development record

- v0.1 failed its first check (in-sample, [validation/run-1.md](validation/run-1.md)): it missed a softened verdict and flagged legitimate interpretation as error. v0.2 fixed both.
- v0.2 kept faithfulness on new material but its variants barely differed. v0.3 added length budgets, marked differences, and whole-paragraph rewriting.
- Our own Floor/Weighed pre-coding changed between reviewers, and one scoring rule (conditional Floor items) proved mis-specified. Both are documented in the validation folders.

## Limits

- For high-stakes text, confirm the Floor list yourself or with a separate reviewer.
- It does not check the source. A wrong number in your results will be reproduced faithfully.
- Floor/Weighed placement varies between models. Placement errors so far were promotions (a Weighed caveat treated as Floor), which lengthen the shortest variant but do not drop anything.
- When the source is mostly Floor material, the variants will differ less.

## Prior art

Surveyed 2026-11-09. Repository details were read from the repositories by a second model (GPT); we have not re-verified every file.

| Work | What it does | Difference from this skill |
|---|---|---|
| [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) | Classifies qualifiers (unnecessary disclaimer, necessary scope condition, methodological limitation, …) and keeps the necessary ones | Returns a single edited version by default |
| [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing), [blader/humanizer](https://github.com/blader/humanizer), [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh), [MrGeDiao/shuorenhua](https://github.com/MrGeDiao/shuorenhua) | Remove AI-style phrasing, with rules to keep real uncertainty, scope, and conditions. Humanizer-zh and shuorenhua publish small preservation test sets | Return a single edited version by default |
| [amanmaqsood/prose-humanizer](https://github.com/amanmaqsood/prose-humanizer), [manavmishra/ZeroSlop](https://github.com/manavmishra/ZeroSlop) | Build a source ledger and check modality, scope, and attribution after rewriting | Closest on source checking; single edited version by default |
| [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) | Caveat protection, a claim-strength ladder, revision authorisation, qualification-drift audit | Closest overall; no variants that differ in caveat coverage, no per-variant split of fixes and tradeoffs |
| [ABScribe](https://arxiv.org/abs/2310.00117) and [Luminate](https://arxiv.org/abs/2310.12953) (CHI 2024) | Generate multiple variants, or variants along dimensions, for the user to explore | Source checking not found in their published descriptions |
| [Beyond Fluency](https://aclanthology.org/2026.wasp-1.15/) (WASP 2026) | Claim-Preservation Framework: measures shifts in epistemic force, evidential relation, qualification, attribution under rewriting | An evaluation framework, not a writing tool |

No surveyed tool lists caveats from the source, writes variants that differ in caveat coverage, checks each against the source, and leaves the choice to the author. The survey used targeted searches on GitHub, ACM DL, arXiv, and Semantic Scholar; this does not show that no such tool exists.

## Repository

- [skills/proportionate-writing/SKILL.md](skills/proportionate-writing/SKILL.md): the skill
- [CONFIGURATIONS.md](CONFIGURATIONS.md): which configuration to use, with results
- [EVIDENCE.md](EVIDENCE.md): B1 and A2 (earlier experiments)
- [validation/](validation/): run 1; v2 case (decision record) and v0.3 regression; v3 case (Hume); v4 baseline comparison
- [examples/](examples/): B1 prompts, outputs, and caveat examples

## License

- The skill (`skills/`): [MIT](LICENSE).
- Everything else (this README, evaluation records, data): [CC BY 4.0](LICENSE-docs). If you use the evaluation method or data, please credit this repository.
- The Hume excerpts are public domain (Standard Ebooks transcription, CC0).
