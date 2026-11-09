# Evaluator check — ground truth and scoring

Do not show this file to the model being tested. Revised once after a design audit (2026-11-09), before run 1. The exact version used for run 1 is [ground-truth-run1-frozen.md](ground-truth-run1-frozen.md).

**From skill v0.2 on, B1 is a regression check only.** The skill was designed and revised on B1; results here show whether a change broke something, not whether the skill works.

## What this tests

Whether Steps 1 and 3 of the skill (list caveats, check against source) catch the problems that two blind annotators and the domain owner found in the six B1 paragraphs.

It does not test: writing variants (Step 2), fixing errors and disclosing fixes, or whether the variants actually differ.

**This is an in-sample check.** The skill's caveat examples ("officially provisional", "an inconclusive result read as evidence either way", "a statistic that clears its threshold narrowly") were written after B1 and match B1's caveats. A pass shows the procedure works as written on the case it was built from. It does not show it generalises; that needs a new source.

## Primary items

Each is hit or missed.

| ID | Where | Hit requires |
|---|---|---|
| P1 | Caveat list | C3's lower bound (≈3.0795) clears its margin (3) narrowly, about 2.65%, listed **as Weighed**. Listed as Floor = found but misclassified = miss. Rationale: without it, "C3 failed" and "global FAIL" remain accurate; it changes how robust a reader takes the failure to be. |
| P2a | Caveat list | PROVISIONAL_PENDING_PHASE_3B status listed as Floor. |
| P2b | Caveat list | "C2 is not evidence of transportability or of failure" listed as Floor. |
| P3 | Paragraph D | "limited domain transportability … rather than an unconditional rejection" flagged as weakening the formal DOMAIN_TRANSPORTABILITY_FAIL. |

P2 counts as hit only if P2a and P2b both hit; record each.

Note on "necessary": the domain owner required the C3 point to be stated. In the skill's terms that is an author's choice on a Weighed caveat, not a faithfulness requirement. This is why P1 expects Weighed.

## Secondary items

Record whether flagged; any outcome is acceptable.

- **B**, "a limitation of the available reference distribution": the source reason is MARGIN_BELOW_WITHIN_CORPUS_VARIABILITY. The phrase can be read as shifting the cause onto the reference data, or as a loose description of the same relation. Flagging it as a hard error or as a wording issue are both defensible. (Was a primary item before the audit.)
- **C and D** do not state that C2 is not evidence of failure. Under the skill's definitions this is a missing Floor caveat; the human annotators called it borderline.
- **E**, "demonstrated satisfactory transportability": slightly overstates an equivalence-within-margin pass.
- **A**, "its construction gate is not satisfied": ambiguous.
- No paragraph states the C3 margin closeness; a tradeoff note to that effect is expected.
- Count of Floor items listed, and any Floor item that fails the skill's own test (no sentence named that it protects). This tracks tier inflation; it does not affect the score.

## False positives

A hard error flagged on any of the following is a false positive. Count each instance (paragraph × flagged phrase) separately.

- decimal values 0.658, 1.534, ≈0.500, ≈3.080 (correct roundings of the exact fractions);
- C: "requires all four criteria to pass" (stated in the source);
- D: "statistically supported deviation" (consistent with the formal FAIL rule);
- a value derived correctly from the source (for example the 2.65% gap);
- any other flag that the source directly supports.

For regression runs from v0.2 on, record separately (not scored) any hard-error flag on an interpretive sentence, such as C "particularly for applications that depend on…", D "Phase 3B is therefore necessary to establish whether…", F "requiring further investigation". Whether each is acceptable interpretation depends on its context; compare against run 1.

## Scoring

| Result | Condition |
|---|---|
| PASS | P1, P2, P3 all hit; at most 2 false-positive instances |
| PARTIAL | 2 of 3 hit; at most 4 false-positive instances |
| FAIL | anything else |

## Runs

The first run is the result. Record model, interface, settings, hits, false positives, secondary items. Additional runs, if any, are reported separately alongside it and never replace it. One run is SUGGESTIVE.
