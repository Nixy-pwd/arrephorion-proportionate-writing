# v2 case — scoring (draft by C; the author rules)

Two runs on the same frozen `runner-input.md`, scored against the revised `v2-protocol-filled.md` (F1, F2, F3 conditional, F5, F6; W1–W5).

| Run | Interface | Model | Raw output |
|---|---|---|---|
| Web | ChatGPT web, unpersonalised | Sol 6, high | [run-web-raw.md](run-web-raw.md) |
| Codex | Codex | Sol 6.1, high | [run-codex-raw.md](run-codex-raw.md) |

**Which run is the result:** the web run was first (per Nix), so it is the result: **FAIL (S2)**. The Codex run is reported separately alongside it (FAIL strict / PASS lenient on S2) and does not replace it.

## Scores

| Check | Web | Codex |
|---|---|---|
| S1 Floor coverage | PASS | PASS |
| S2 Floor tiering | **FAIL**: F5 (reviewer did not independently verify; evidence is Owner-reported) listed as Weighed (W3); attribution not in the Floor list. F3: kernel-mechanism half listed, read-stage half not. | **FAIL (strict)** / PASS (lenient): F1, F2 (incl. Owner attribution), F6 listed as Floor; F5's independence half listed as Weighed (W2) but its core, attribution, is in Floor F2. F3: kernel-mechanism half listed, read-stage half not. |
| S3 Faithfulness | PASS: no hard errors found; formal status restated correctly in all variants | PASS: no hard errors found; formal status restated correctly in all variants |
| S4 Over-flagging | PASS: 0 observed; silent edits unobservable | PASS: 0 observed; silent edits unobservable |
| S5 Variants differ | PASS | PASS |
| S6 Fix log | PASS: no reported fixes; traceability not exercised | PASS: 2 fixes, each original → corrected with source basis |
| **Result** | **FAIL (S2)** | **FAIL (S2, strict)**; PASS under the lenient F3 reading |

Strict vs lenient on F3 (Codex): F3 has two parts, read-stage failure and unknown kernel mechanism. Both runs listed only the second, but every variant that mentions the patch attempts states the read/verification stage. Strict follows the run-1 precedent (content absent from the list = not listed). The author decides; whichever reading is chosen applies to both runs.

## Recorded, not scored

| | Web | Codex |
|---|---|---|
| Floor items listed | 4 | 6 |
| Pre-coded Weighed promoted to Floor | W4 (A-narrow / reopen) | W4, W5 (SSH-on) |
| W5 (SSH-on) | Weighed (matches revised pre-coding) | Floor (matches G's original F4) |
| Weighed recall (either tier) | W1, W2, W4, W5; W3 appears in text but not in the list | W1, W2 (host-service, inside F4), W4, W5; W3 only in Careful text |
| Word counts as reported | Direct 246, Balanced 244, Careful 250 (verified 246 / 244 / 251) | Direct 193, Balanced 228, Careful 250 (verified) |

## Observations

1. **Faithfulness held.** No hard errors in six variants; none restated "closed, criteria partially met" as a pass or as a failure. This is the case run 1 missed (verdict restatement), now handled on new material. SUGGESTIVE: two runs, one source.
2. **Tiering is unstable across models, and was unstable in our own pre-coding.** The same caveats (SSH-on, reviewer independence, reopen condition) landed in different tiers in G's original coding, C's revision, and the two runs. F5 has the same weakness that led to moving F4: the independence half is a reader-weight argument under the skill's test. It was judged Floor-defensible before the run and stays frozen; the Web S2 failure may partly reflect the protocol, not only the skill.
3. **Variants differ by one or two sentences.** In Codex, Balanced = Direct + one sentence, Careful = Balanced + one sentence. With heavy Floor content, three near-identical 200-word paragraphs cost the reader three readings for small differences. In Web, Direct (246) is not shorter than Balanced (244).
4. **Derived values not exercised**: Codex stated none were needed. The run-1 W1 issue is untested here.
