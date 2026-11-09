# Validation v2 — full skill on new material

Out-of-sample test of skill v0.2, end to end (all four steps). Fill in sections 1–2 and freeze this file before the run.

## 1. Material (fill in before the run)

- **Source:** one set of real results from the author's own work, not from PM2S V3 Phase 4 and not seen by the models that designed the skill. Paste or attach it unchanged.
- **Task:** the paragraph to write (e.g. a Discussion paragraph for these results), in one or two sentences.
- **Intended reader:**

## 2. Author's pre-coding (fill in before the run)

**Floor.** For each item, name the claim it protects:

| ID | Caveat | Without it, this claim would be inaccurate / beyond the source / against a formal status |
|---|---|---|
| F1 | | |

**Weighed.** Caveats a reasonable author could include or leave out. These define the allowed options; no single combination is the correct answer.

| ID | Caveat | Reader judgment it changes |
|---|---|---|
| W1 | | |

## 3. Run

- Fresh session, no memory, custom instructions, or project context.
- Input: the full SKILL.md, then the source, the task, and the intended reader. Nothing else.
- Record model, interface, settings. The first run is the result; any further runs are reported separately and never replace it.

## 4. Scoring (by the author, against section 2)

| ID | Check | Pass condition |
|---|---|---|
| S1 | Floor coverage | Every pre-coded Floor item appears in every delivered variant. |
| S2 | Floor tiering | No pre-coded Floor item is listed by the skill as Weighed or omitted from its caveat list. |
| S3 | Faithfulness | No hard error in any delivered variant, using the skill's own definitions, including verdict restatements. |
| S4 | Over-flagging | At most one interpretive sentence the author judges consistent and supported is flagged, removed, or "fixed" as an error. |
| S5 | Variants differ | Delivered variants differ in Weighed coverage, or the skill says why it merged them. |
| S6 | Fix log | Every reported fix shows original → corrected and a source basis. |

Recorded, not scored:

- recall of the author's Weighed items in the skill's caveat list (in either tier), and any tier disagreements;
- caveats the skill listed that the author had not pre-coded, with the author's view of each;
- which variant the author would choose, and why.

**Result:** PASS if S1–S6 all pass. Otherwise FAIL, listing which checks failed. One run is SUGGESTIVE.

## Known limits

- The author pre-codes and scores, and knows the material. The checks are against a frozen list, but scoring is not blind.
- One source, one run.
