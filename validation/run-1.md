# Evaluator check — run 1

- Date: 2026-11-09
- Model, interface, settings: Codex, Sol 6.1 (per Nix); reasoning level not recorded.
- Inputs as used: [evaluator-check-prompt-run1-frozen.md](evaluator-check-prompt-run1-frozen.md). Scored against [ground-truth-run1-frozen.md](ground-truth-run1-frozen.md), which was revised once after the design audit and before this run (four primary items became three; see its header). No criteria were changed after seeing the output.
- Raw output: [run-1-raw.md](run-1-raw.md).

## Result: FAIL (1 of 3 primary items)

A lenient reading of P2b gives PARTIAL (2 of 3). The strict reading is recorded as the result because it applies the same standard used for paragraphs C and D (see P2b).

| Item | Outcome | Basis |
|---|---|---|
| P1 | Hit | C3's 2.65% clearance listed under Weighed (W2). |
| P2a | Hit | PROVISIONAL_PENDING_PHASE_3B listed under Floor (F3). |
| P2b | Miss (strict) | F1 states the classification ("inconclusive by construction, not a PASS or FAIL") but not that C2 is not evidence either way. The same gap (classification stated, evidential neutrality not stated) is what the secondary item for C and D records. |
| P2 | Miss | Requires P2a and P2b. |
| P3 | Miss | D's "limited domain transportability … rather than an unconditional rejection" not flagged. D was flagged for a different phrase. |

## False positives counted under the frozen definition: 0

None of the listed false-positive items was flagged. Decimal roundings, "requires all four criteria to pass", and "statistically supported deviation" were each judged consistent with the source.

Three further flags look like possible over-flagging but fall outside the frozen definition, so they are not counted. The false-positive measure did not cover this case; the score for this run stays as it is: C ("particularly for applications that depend on…"), D ("Phase 3B is therefore necessary to establish whether…"), F ("requiring further investigation"). Each is an interpretation, not a reported finding. The ground truth counts a flag as a false positive only if the source directly supports the flagged phrase, which it does not here. Whether each of the three is a reasonable interpretation depends on the full sentence and context; see finding 3.

## Secondary items

| Item | Flagged |
|---|---|
| B, C2 attribution | No (B judged error-free) |
| C and D, C2 evidential neutrality | No |
| E, "demonstrated satisfactory transportability" | No |
| A, "construction gate is not satisfied" | Yes, as a hard error ("reverses the meaning") |
| C3 closeness as tradeoff note | Partly: all six marked as giving the numbers; none computes the distance |
| Floor count | 3; no tier inflation observed |

## Findings

Observed facts are stated as such; explanations are marked PLAUSIBLE.

1. **The softened verdict in D was not reported.** The skill already required that formal verdicts keep their strength; the check did not report this sentence. PLAUSIBLE explanation: the procedure names verdicts and labels but does not say to check summary, interpretive, and closing sentences that restate a verdict in other words.
2. **W1 compares C2's point estimate with its margin.** W1 reports the point estimate (≈0.139) as 0.039 above the 0.1 margin and says the absence of a formal FAIL should not be read as evidence that the difference is small. The construction gate blocks formal inference from C2; it does not necessarily make describing the statistic illegitimate, and W1 does not use the comparison to claim a tolerance violation. Not scored as an error. It does show that derived values need a rule on what evidential role they may play. PLAUSIBLE: the instruction to compute implied values prompted this comparison.
3. **Three interpretive sentences were reported as unsupported claims.** C (an application implication), D (a purpose for Phase 3B), F (a call for further investigation). The hard-error rule ("a claim the source neither states nor supports") does not distinguish an inference presented as interpretation from an unsupported claim presented as a result. In the full skill, Step 3 would remove such sentences. Whether each of the three is reasonable has not been judged here.

Single run: SUGGESTIVE. B1 is now used twice and in-sample; from here on it is a regression check only, not new validation evidence.
