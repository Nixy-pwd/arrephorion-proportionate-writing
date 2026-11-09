# v3 humanities case — ChatGPT chat result (draft by C; the author rules)

Run: ChatGPT web chat, Sol 6, high, unpersonalised. Input: frozen [runner-input.md](runner-input.md). Raw: [run-chat-raw.md](run-chat-raw.md). Single run.

## Result: FAIL (S1, S2 on F4; R2; R3 strict)

| Check | Outcome | Note |
|---|---|---|
| S1 Floor coverage | **FAIL** | F1, F2, F3 in all three. F4 core not met: Balanced and Careful say "Memory chiefly discovers, not produces, identity"; Direct says memory discovers "rather than producing identity". The supplied 1.4.6.20 says memory "does not so much produce as discover", within the causal view; the variants turn the comparison into an exclusive denial, which the F4 core excludes. Causal context and "not the whole of identity" are kept. Close call; this is the reading C itself drafted before review. |
| S2 Floor tiering | **FAIL** | Memory is listed as Floor, but in the exclusive form ("discovers rather than produces"), so F4's core is not in the list. F1–F3 cores listed. |
| S3 Faithfulness | PASS (apart from F4, scored under S1) | No other hard errors or listed distortions. "The Appendix does not withdraw the case against a simple self" is one of the two readings F2 allows. |
| S4 Over-flagging | PASS | 0 observed; no fixes. |
| S5 Variants differ | PASS | Content differs. |
| S6 Fix log | PASS | No reported fixes; traceability not exercised. |
| R1 Length spread | PASS | 137 / 210 / 276 words (verified; reported 208 / 274); Direct/Careful = 0.50. |
| R2 Marks | FAIL | No bold marks in the received text; unverified whether lost in copying. |
| R3 Table | FAIL (strict) / PASS (lenient) | Careful row quotes; Balanced row quotes one addition and describes the rest. |

## Recorded, not scored

- **Variants are appended, not rewritten.** Careful is Balanced verbatim plus two sentences (verified); Balanced shares Direct's opening sentences and extends it. Same pattern as this configuration's v0.3 regression run.
- Floor list: 7 items, promoting W2 (theatre), W3 (indeterminacy), W5 (not insoluble). Weighed: gradual character of identity, the Appendix's "promising aspect", epistemic modesty. The "promising aspect" item is not in our pre-coding and is well grounded in the supplied Appendix paragraph.
- Careful's added interpretation ("a genealogy of the attribution of identity … rather than a completed explanation of what objectively unites perceptions") is hedged ("suggests", "on this reading") and grounded.

## v3 across configurations

| Configuration | Result | Main issue |
|---|---|---|
| ChatGPT work mode, Astra 6 light | PASS | — |
| Codex, Sol 6.1 high | FAIL on frozen S2 only | Memory listed as Weighed; all memory statements accurate. Scoring-design issue. |
| ChatGPT chat, Sol 6 high | FAIL | Memory stated exclusively ("not produces"); variants appended; no marks. |

Only the chat run made a content error, and it is the error the pre-coding review specifically anticipated. The chat configuration also failed the v0.3 regression for the same instruction-following reasons (appending, no marks).
