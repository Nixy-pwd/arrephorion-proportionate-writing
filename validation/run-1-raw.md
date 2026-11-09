# Evaluator check — run 1, raw output

Verbatim evaluator output as received (2026-11-09). Scoring is in [run-1.md](run-1.md).

---

# Evaluator check

## 1. Caveats from the source

There are three Floor caveats and two Weighed caveats. The distinction matters: the Floor caveats determine what can legitimately be concluded, while the Weighed caveats affect how strongly a reader interprets the findings.

### Floor — omitting these would misstate the result

F1. C2 is inconclusive by construction, not a PASS or FAIL.

The within-development n/2 reference 95th percentile is 0.499929, against a frozen margin of 0.100. This meets the construction-gate condition (reference percentile ≥ margin), producing `INCONCLUSIVE_BY_CONSTRUCTION` and a three-way `INCONCLUSIVE` classification. The criterion cannot independently trigger global failure.&#x20;

evaluator-check-prompt.md



F2. C3 is formally FAIL under the specified lower-bound rule.

The lower bound is approximately 3.079530 semitones, exceeding the 3.000000-semitone margin by 0.079530 semitones. The formal rule is \\(L\_{98.75} > \text{margin}\\). The FAIL-side bounds use Bonferroni family alpha 0.05 across four criteria, or alpha 0.0125 per criterion.&#x20;

evaluator-check-prompt.md



F3. The global verdict is FAIL because of C3, despite C2 being inconclusive; the official conclusion remains provisional.

The aggregation rule requires all four criteria to PASS for global PASS. Any individual FAIL produces global FAIL. With no FAIL but at least one INCONCLUSIVE, the global result would instead be INCONCLUSIVE. Here, C3 determines `DOMAIN_TRANSPORTABILITY_FAIL`. However, the official status is `PROVISIONAL_PENDING_PHASE_3B`, because Phase 3B parser and measurement-instrument validation has not been executed.&#x20;

evaluator-check-prompt.md



### Weighed — omission changes the reader's assessment

W1. C2 has reported numerical evidence that is more informative than simply saying the result is inconclusive.

The reported cross-corpus absolute probability difference is approximately 0.138838, which is 0.038838 above the 0.100 margin. Its reported bounds are:

- \\(U\_{95}\\): approximately 0.372143.
- \\(L\_{98.75}\\): approximately 0.003479.

These statistics are available, but the construction gate fixes the classification as inconclusive. The reader should not mistake the absence of a formal FAIL for evidence that the observed difference is small.&#x20;

evaluator-check-prompt.md



W2. The margins are not equally close for the different criteria.

| Criterion      | Bound    | Margin | Distance from margin |
| -------------- | -------- | ------ | -------------------- |
| C1 upper staff | 0.658067 | 2.000  | 1.341933 below       |
| C1 lower staff | 1.533836 | 2.000  | 0.466164 below       |
| C3             | 3.079530 | 3.000  | 0.079530 above       |

C3 formally fails, but its lower bound exceeds the margin by only approximately 2.65% of the margin. Conversely, the lower-staff C1 result passes with considerably less headroom than the upper-staff result.

This affects the interpretation: the global failure is formally decisive, but the numerical results show selective performance rather than uniform failure across dimensions.&#x20;

evaluator-check-prompt.md



## 2. Hard errors by paragraph

### A

1 hard error

Incorrect phrase:

> "its construction gate is not satisfied because the within-development n/2 reference 95th percentile (approximately 0.500) exceeds the frozen margin of 0.100"

Conflicting source fact:

The source explicitly states that the reference percentile meets the frozen gate condition of reference 95th percentile ≥ margin.

The gate condition is therefore satisfied, not unsatisfied. That condition produces `INCONCLUSIVE_BY_CONSTRUCTION`.

This reverses the meaning of the construction-gate decision.&#x20;

evaluator-check-prompt.md

evaluator-check-prompt.md



The remaining formal verdicts, numerical bounds, aggregation rule and provisional status are consistent with the source.

### B

No hard errors

All numerical values, criterion labels, formal verdicts and explanations of the construction gate are consistent with the source.

In particular, the distinction between C2 being inconclusive and C3 producing the global failure is correctly maintained.&#x20;

evaluator-check-prompt.md

evaluator-check-prompt.md



### C

1 unsupported extension

Phrase:

> "particularly for applications that depend on accurate cross-staff pitch relationships"

The source establishes a cross-staff pitch interval failure but contains no application-level evaluation or findings about particular applications.

This is a reasonable potential implication, not a reported source result. It should be distinguished from the established audit findings.&#x20;

evaluator-check-prompt.md

evaluator-check-prompt.md



The rest of the paragraph correctly represents C1, C2, C3, the aggregation rule and provisional status.

### D

1 unsupported extension

Phrase:

> "Phase 3B is therefore necessary to establish whether the observed cross-staff discrepancy persists under validated measurement procedures."

The source establishes that Phase 3B parser and measurement-instrument validation has not been executed. It also establishes the provisional status of the conclusion.

However, it does not specify that Phase 3B is intended to establish whether the particular cross-staff discrepancy persists.

The paragraph adds a purpose for Phase 3B that the source does not state.&#x20;

evaluator-check-prompt.md

evaluator-check-prompt.md



The description of the C3 failure as statistically supported is consistent with its formal lower-bound failure rule.

### E

No hard errors

The paragraph correctly distinguishes:

- C1 passing.
- C2 providing neither a PASS nor a FAIL.
- C3 formally failing.
- The global verdict being determined by C3.
- The official conclusion remaining provisional pending Phase 3B.

The statement that C2 provides neither evidence of transportability nor evidence of a violation accurately preserves the inconclusive classification.&#x20;

evaluator-check-prompt.md

evaluator-check-prompt.md



### F

1 unsupported addition

Phrase:

> "substantive audit findings requiring further investigation"

The source establishes the audit findings and the outstanding Phase 3B validation. It does not explicitly prescribe further investigation as a requirement.

This is an additional recommendation or interpretation rather than a reported source fact.&#x20;

evaluator-check-prompt.md

evaluator-check-prompt.md



The rest of the paragraph correctly describes the formal findings and provisional status.

## 3. Weighed caveats included and paragraph tradeoffs

For this comparison:

- W1: C2's reported cross-corpus difference and bounds, despite its construction-gated inconclusive status.
- W2: The numerical distance of the C1 and C3 bounds from their respective margins.

| Paragraph | W1: C2 statistics | W2: Margin comparisons |
| --------- | ----------------- | ---------------------- |
| A         | Omitted           | Included               |
| B         | Omitted           | Included               |
| C         | Omitted           | Included               |
| D         | Omitted           | Included               |
| E         | Omitted           | Included               |
| F         | Omitted           | Included               |

All six provide the approximate C1 and C3 values, allowing readers to calculate the margin distances. None explicitly calculates those distances. None includes the actual cross-corpus C2 statistics or explains the Bonferroni adjustment.

### A — Detailed but contains a consequential error

Tradeoff: The paragraph gives extensive attention to the distinction between C2's inconclusive result and the global failure. It also carefully explains provisional status. Its length makes it suitable for a detailed Discussion, but the reversed construction-gate statement is a substantive problem. A reader may misunderstand the reason for C2's inconclusive classification.

### B — Comprehensive and technically balanced

Tradeoff: B is particularly explicit about why C2 must not be interpreted as a failure and why C3 determines the global verdict. It also explains the provisional nature of the conclusion. Its length is substantial, but the technical reasoning is well developed.

It suits a technical or academic reader who needs the decision framework explained rather than merely reported.

### C — Direct and decisive

Tradeoff: C has a stronger opening and a more decisive overall framing. It emphasizes that satisfactory within-staff performance does not establish overall transportability. It is less expansive than A and B.

A reader is likely to take away that the method does not yet meet the overall acceptance criteria, notwithstanding C1 success. It suits a Discussion that prioritizes the central conclusion over extended procedural explanation.

### D — Interpretive and balanced

Tradeoff: D emphasizes the practical distinction between retaining within-staff properties and failing cross-staff transportability. Its description of C3 as the specific driver of global failure is particularly useful.

It also provides a more interpretive account of the Phase 3B implications than the source supports. Its reader is likely to view the result as a specific cross-staff limitation rather than a general failure of every evaluated dimension.

### E — Economical and carefully qualified

Tradeoff: E is one of the more concise treatments. Its strongest feature is the explicit statement that C2 provides neither evidence of transportability nor evidence of a violation. It avoids treating an inconclusive result as a negative finding.

It also clearly separates the present formal failure from the final validated conclusion. It suits readers who need the main results without extensive repetition of the aggregation framework.

### F — Most comprehensive explanation of the decision framework

Tradeoff: F provides a particularly thorough explanation of why C2 is inconclusive and why a single C3 failure determines the global verdict. It gives the reader a clear account of how the individual findings fit together.

However, the word "comfortably" in describing the C1 bounds gives a somewhat stronger impression of clearance than the lower-staff result alone warrants: that bound is only 0.466 semitones below the margin. The final recommendation about further investigation also goes beyond the source.

It suits readers who prefer an extended, explanatory account of the audit findings.

## Overall assessment

| Paragraph | Hard errors / unsupported additions | Main strength                            | Main weakness                                                  |
| --------- | ----------------------------------- | ---------------------------------------- | -------------------------------------------------------------- |
| A         | 1                                   | Detailed treatment of provisional status | Reverses C2 gate meaning                                       |
| B         | 0                                   | Technical completeness and balance       | Length                                                         |
| C         | 1                                   | Direct central conclusion                | Unsupported application-level implication                      |
| D         | 1                                   | Explains selective transportability      | Adds an unsupported Phase 3B purpose                           |
| E         | 0                                   | Concise and carefully qualified          | Omits C2 numerical evidence                                    |
| F         | 1                                   | Thorough explanation of aggregation      | Overstates C1 clearance and adds an unsupported recommendation |

B and E are the two paragraphs without hard errors or unsupported extensions.

Their principal difference is emphasis:

- B is more comprehensive in explaining the decision framework and the implications of C2.
- E communicates the same essential findings more economically and gives particularly clear treatment to the inconclusive result and provisional status.

One important limitation applies equally to both: neither reports the available C2 cross-corpus statistics. That omission does not misstate the formal verdict, but it reduces the numerical context available to the reader.

My evaluation: B is the more comprehensive technical Discussion; E is the more economical Discussion. Both preserve the essential formal conclusion: C1 passes, C2 is inconclusive by construction, C3 fails, and the global verdict is provisionally `DOMAIN_TRANSPORTABILITY_FAIL` pending Phase 3B.