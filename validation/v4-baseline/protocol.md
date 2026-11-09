# v4 — baseline comparison: same task with and without the skill

Question: on the Hume case, does the skill produce text that is more faithful and less redundant than the same model writing the paragraph without it? The v3 runs show the skill's output is faithful; they do not show it beats the baseline.

## Design

- **Skill condition:** the existing v3 runs ([../v3-case/](../v3-case/)), one per configuration. Not re-run.
- **Control condition:** [runner-control.md](runner-control.md): the same source, task, and reader as v3, without SKILL.md and without the sentence asking to apply it. One paragraph.
- **Configurations:** the same three as v3: Codex (Sol 6.1 high), ChatGPT work mode (Astra 6 light), ChatGPT chat (Sol 6 high). Fresh session, nothing else pasted. One run each; the first run is the result.
- **Scoring reference:** the frozen v3 pre-coding ([../v3-case/protocol.md](../v3-case/protocol.md)), unchanged. It was written before any control output existed.

## Measures

Each control paragraph and each skill variant is scored separately.

| ID | Measure | How |
|---|---|---|
| M1 | Floor coverage | Number of applicable F1–F4 cores present (F4 applies only if memory is mentioned). |
| M2 | Content errors | Hard errors and listed distortions from the v3 pre-coding, judged in context. |
| M3 | Repeated caveats | Caveats stated more than once in the same paragraph (same limitation in different words). |
| M4 | Length | Words. |

Comparison per configuration: the control paragraph against each skill variant, and in particular against Balanced (Floor + Weighed), the closest single-paragraph analogue.

## Possible outcomes, stated in advance

- **Skill better on M1/M2:** the skill adds faithfulness. Expected failure points for the control, from the v3 pre-coding: memory stated exclusively, the Appendix read as a retraction, the denial of a simple self widened, the verbal diagnosis extended to all questions of the self.
- **No difference on M1/M2:** these models are already faithful on this text without the skill. The skill's contribution is then the choice it offers (variants, marked differences), not faithfulness. This would be reported as such.
- **Control better:** reported as such.
- M3 tests the original anti-defensive aim: whether the control repeats limitations more than the skill's variants do.

## Limits

- One run per configuration per condition; one material. SUGGESTIVE at most.
- Scoring is by C, who knows which output is which. The measures are checklists against a frozen reference, but scoring is not blind. Optional: strip labels and marks, shuffle the control paragraph with the skill's Balanced variant per configuration, and have G score M2 and M3 blind.
- The skill outputs were produced earlier in the day than the control outputs, in separate sessions.
