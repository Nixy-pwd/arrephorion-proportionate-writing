# v4 baseline — result

Blind scoring by G ([blind-scoring-raw.md](blind-scoring-raw.md)), unblinded with [blind-key.json](blind-key.json). One run per configuration per condition; one material. SUGGESTIVE.

## Unblinded scores

| Configuration | Condition | Label | Words | F1–F4 present | Content errors | Repeated caveats |
|---|---|---|---:|---|---:|---:|
| Codex, Sol 6.1 high | without skill | P5 | 285 | 4/4 | 0 | 1 |
| Codex, Sol 6.1 high | with skill (Balanced) | P6 | 181 | 4/4 | 0 | 1 |
| Work mode, Astra 6 light | without skill | P1 | 278 | 4/4 | 0 | 1 |
| Work mode, Astra 6 light | with skill (Balanced) | P4 | 199 | 4/4 | 0 | 0 |
| Chat, Sol 6 high | without skill | P2 | 313 | 3/4 (F4 absent) | 2 | 1 |
| Chat, Sol 6 high | with skill (Balanced) | P3 | 210 | 4/4 | 0 | 0 |

Totals: without skill, 2 content errors and 3 repeated caveats in 876 words; with skill, 0 content errors and 1 repeated caveat in 590 words.

The chat control's errors: memory stated as "not by producing identity itself" without the causal scope (F4); "particularly resemblance and causation" presented as Hume's mechanism although resemblance is not in the supplied passages.

## Reading, against the outcomes stated in advance

- **Faithfulness (F1–F4, content errors):** no difference in Codex and work mode; both conditions were faithful. This is the pre-stated "no difference" outcome for these two configurations: here the models are faithful without the skill. In chat, the skill version was faithful and the control was not: the pre-stated "skill better" outcome, in one configuration.
- **Repetition and length:** with the skill, fewer repeated caveats (1 vs 3) and about a third shorter (590 vs 876 words), with no loss of F1–F4. This is the anti-defensive aim the project started from, and it matches B1.
- So on this material the skill's measurable effect in the strong configurations is concision without loss, plus the choice of variants; its faithfulness effect appeared only in the weakest configuration.

## Scorer disagreement, recorded not resolved

G scored the chat skill paragraph's "Memory chiefly discovers, not produces, identity: it supplies the notion of causation…" as meeting F4, reading "chiefly" and the causal clause after the colon as limiting it. C scored the same sentence as missing F4 in the v3 result ([../v3-case/result-chat.md](../v3-case/result-chat.md)), reading "not produces" as exclusive. Same proposition and same reference; the difference is in applying the core to this wording. Both readings are recorded; the frozen v3 result stands, and on G's reading that run's S1 would pass.

## Limits

- Length differed by condition (181–210 vs 278–313 words), so the scorer could have inferred which paragraphs came from the skill.
- The skill paragraphs were each one of three variants; the controls were the only output. Choosing Balanced for comparison was fixed before scoring.
- One material, one run per cell, one scorer.
