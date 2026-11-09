# v5 PM2S with skill — Codex, run 2 (English output), raw

Model: Codex (Sol 6.1, high). Input: pm2s-skill.md. Received 2026-11-09. Verbatim. Second run; answered in English.

---

### 1. Caveat list

**Floor — required in every variant**

| ID | Caveat and source location | Sentence it protects |
|---|---|---|
| F1 | C1 PASS applies specifically to piece-balanced 1-Wasserstein distances between within-staff signed pitch-change distributions, with U₉₅ < 2 semitones. **Source:** C1 results. | “Both within-staff criteria passed.” This cannot establish transportability of the method as a whole. |
| F2 | C3 assesses complete signed boundary-gap distributions, with g = min(upper-staff pitches) − max(lower-staff pitches). Its formal FAIL rule is L₉₈.₇₅ > 3 semitones. Failure-side bounds use Bonferroni family α = 0.05 across four criteria, or α = 0.0125 per criterion. **Source:** C3 and global results. | “The cross-staff criterion failed.” The measured quantity and decision rule must remain explicit. |
| F3 | C2 is INCONCLUSIVE_BY_CONSTRUCTION, with three-way classification INCONCLUSIVE. The within-DEVELOPMENT n/2 reference 95th percentile meets the gate condition ≥ 0.1: MARGIN_BELOW_WITHIN_CORPUS_VARIABILITY. Its cross-corpus statistics cannot independently trigger global failure. **Source:** C2 results. | “C2 is inconclusive.” Its available statistics cannot be repurposed as a PASS or FAIL verdict. |
| F4 | All four criteria must PASS for global PASS; any FAIL yields global FAIL; no FAIL with at least one INCONCLUSIVE yields global INCONCLUSIVE. C3 determines the current DOMAIN_TRANSPORTABILITY_FAIL. **Source:** global verdict. | “The method failed this transportability audit.” C1 passes cannot compensate for C3 failure. |
| F5 | The official status is PROVISIONAL_PENDING_PHASE_3B; parser and measurement-instrument validation has not been executed. **Source:** official conclusion status. | “The global verdict is failure.” It must remain a provisional conclusion pending validation. |

**Weighed — affects how readers assess the finding**

All numerical approximations below are derived from the supplied exact fractions.

| ID | Caveat, source, and derivation | Reader judgment affected |
|---|---|---|
| W1 | C1 headroom differs between staves. **Source:** C1 bounds. U₉₅ ≈ 0.65807 and 1.53384 semitones; derived headroom, 2 − U₉₅, is ≈ 1.34193 and 0.46616 semitones, respectively. | Both pass, but the lower-staff bound is closer to its margin. |
| W2 | C3’s lower bound only narrowly exceeds the margin. **Source:** C3 bound. L₉₈.₇₅ ≈ 3.07953 semitones; derived excess, L₉₈.₇₅ − 3, is ≈ 0.07953 semitones. | The excess is small, although the formal FAIL remains unchanged. This excess is not a point estimate of the distributional distance. |
| W3 | C2’s internal reference variability substantially exceeds its margin. **Source:** C2 construction gate. 23351539/46709676 ≈ 0.49993; derived excess above 0.1 is ≈ 0.39993. | Explains the scale underlying the construction gate; it supplies no additional evidence for cross-domain failure. |

### 2. Variants

**Direct**

Under the frozen audit rules, the method received DOMAIN_TRANSPORTABILITY_FAIL in the new domain, driven by C3 FAIL. Piece-balanced 1-Wasserstein comparisons of within-staff signed pitch-change distributions passed C1 for both staves (U₉₅ < 2 semitones). However, C3 failed for the complete signed boundary-gap distribution, where g = min(upper-staff pitches) − max(lower-staff pitches), because L₉₈.₇₅ > 3 semitones. Failure-side bounds used Bonferroni correction across four criteria (family α = 0.05; per-criterion α = 0.0125). C2, crossing conditional on non-separated cells, was INCONCLUSIVE_BY_CONSTRUCTION (three-way classification: INCONCLUSIVE): the within-DEVELOPMENT n/2 reference 95th percentile met or exceeded its 0.1 margin, so its cross-corpus statistics cannot independently trigger global failure. Global PASS requires all four criteria to pass; any FAIL yields global FAIL; otherwise, any INCONCLUSIVE yields global INCONCLUSIVE. Thus, within-staff passes do not offset the cross-staff failure. The official conclusion remains PROVISIONAL_PENDING_PHASE_3B because parser and measurement-instrument validation has not been executed.

**Balanced**

The method received DOMAIN_TRANSPORTABILITY_FAIL in the new domain because C3 failed, despite both within-staff C1 criteria passing. Piece-balanced 1-Wasserstein comparisons of signed pitch-change distributions gave U₉₅ < 2 semitones for both staves; **the upper- and lower-staff bounds were approximately 0.65807 and 1.53384 semitones, leaving respective headroom of 1.34193 and 0.46616 semitones, with less headroom for the lower staff.** Using the same distance, C3 failed for the complete signed boundary-gap distribution, defined by g = min(upper-staff pitches) − max(lower-staff pitches), because L₉₈.₇₅ exceeded 3 semitones. **This lower bound was approximately 3.07953 semitones, only 0.07953 semitones above the margin.** Failure-side bounds used Bonferroni correction across four criteria (family α = 0.05; per-criterion α = 0.0125). C2, crossing conditional on non-separated cells, was INCONCLUSIVE_BY_CONSTRUCTION (three-way classification: INCONCLUSIVE): the within-DEVELOPMENT n/2 reference 95th percentile met or exceeded the 0.1 margin; **its value was approximately 0.49993, exceeding the margin by 0.39993 and placing that margin below the internal reference variability.** Its cross-corpus statistics cannot independently trigger global failure. The frozen rules require all four criteria to pass for global PASS, any FAIL produces global FAIL, and otherwise any INCONCLUSIVE produces global INCONCLUSIVE. Consequently, the C1 passes cannot compensate for C3 failure. The official conclusion remains PROVISIONAL_PENDING_PHASE_3B, with parser and measurement-instrument validation not yet executed.

**Careful**

The audit yielded DOMAIN_TRANSPORTABILITY_FAIL for the method in the new domain, driven by C3 FAIL. **The contrast between passing within-staff criteria and a failing cross-staff criterion indicates that satisfying the audited limits on within-staff pitch changes does not ensure that relative pitch configurations between staves satisfy their corresponding limit; it does not establish why the cross-staff distributions differ.** Piece-balanced 1-Wasserstein comparisons of within-staff signed pitch-change distributions passed C1 for both staves: U₉₅ was approximately 0.65807 and 1.53384 semitones for the upper and lower staves, respectively, leaving 1.34193 and 0.46616 semitones below the 2-semitone margin and less headroom for the lower staff. C3 used the same distance for complete signed boundary-gap distributions, where g = min(upper-staff pitches) − max(lower-staff pitches). Its L₉₈.₇₅ was approximately 3.07953 semitones, exceeding the 3-semitone margin by 0.07953 semitones and therefore meeting the formal FAIL rule. Failure-side bounds used Bonferroni correction across four criteria (family α = 0.05; per-criterion α = 0.0125). C2, crossing conditional on non-separated cells, was INCONCLUSIVE_BY_CONSTRUCTION (three-way classification: INCONCLUSIVE), because the within-DEVELOPMENT n/2 reference 95th percentile, approximately 0.49993, exceeded the 0.1 margin by 0.39993, placing the margin below internal reference variability and triggering the construction gate. Its cross-corpus statistics cannot independently trigger global failure. All four criteria must pass for global PASS; any FAIL yields global FAIL; otherwise, any INCONCLUSIVE yields global INCONCLUSIVE. Thus, C1 cannot compensate for C3. The official status remains PROVISIONAL_PENDING_PHASE_3B because parser and measurement-instrument validation has not been executed. **The next step should be to complete Phase 3B and reassess the current verdict in light of that validation; if C3 failure persists, relative pitch configurations between staves should become a focus of adaptation and renewed auditing.**

### 3. Source check and comparison

Each variant was checked against the supplied results for numerical accuracy, verdict strength, decision rules, and Floor coverage. Word counts use whitespace-separated tokens.

| Variant | Words | Content added over previous variant | Weighed caveats | Fixes: original → corrected; source basis | Tradeoff |
|---|---:|---|---|---|---|
| Direct | 146 | Baseline | None | None | Suits readers familiar with the audit protocol; states the provisional failure without quantifying headroom. |
| Balanced | 209 | “less headroom for the lower staff”; “only 0.07953 semitones above”; reference value “approximately 0.49993” | W1, W2, W3 | “leaving respective margins” → “leaving respective headroom”; C1’s frozen margins remain 2 semitones, whereas the derived quantities are distances below those margins. | Shows proximity to decision boundaries and the gate’s scale, at the cost of more numerical detail. |
| Careful | 277 | “does not ensure that relative pitch configurations … satisfy their corresponding limit”; “complete Phase 3B”; conditional adaptation priority | W1, W2, W3 | None | Adds an interpretation and conditional research direction for readers assessing implications; does not establish the cause of the discrepancy. |

Which variant would you like to use, or what would you like to merge?