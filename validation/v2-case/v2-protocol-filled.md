# Validation v2 — Architecture Gate case

Prepared and frozen before execution: 2026-11-09 (Asia/Shanghai). No validation run has been performed in this preparation session. Pre-coding prepared by G at Nix's request; this is not an independently human-coded reference.

## 1. Material

- Source: `source.md`, the complete, unchanged archived closure record dated 2026-10-29. [private repository; address redacted], commit `93e543a3f76a5002520befa3649b7dc2d801a3fc`, path `docs/research/stage1-preflight/ARREPHORION_ARCHITECTURE_GATE_CLOSURE_RECORD_2026-10-29.md`, Git blob `7ee18650af39461d36890482514d0c2d514a4bf6`.
- The source is a contemporaneous decision/report based on Owner-provided outputs, not the raw rollout. Retrieval verified the archived document, not the VM observations independently.
- Case status: new to this skill's development/evaluation, outside PM2S V3 Phase 4; historically known to the designers. The original protocol's requirement that the designers never saw the material is explicitly replaced before execution. This is a new-case transfer check, not a designer-unseen holdout.
- Task: Write one English findings-and-implications paragraph per variant, approximately 180–250 words each, summarizing the archived Architecture Gate decision for an engineering collaborator. Include the scoped tool observations, what the closure permits one to conclude, and the remaining project status. Apply the supplied skill in full, including its list, variants, comparison table, and final question; the word target applies only to each paragraph.
- Intended reader: An engineering collaborator deciding how to describe the B-plus result and plan later work, who has not read the VM logs. Report the decision as of 2026-10-29, not the current state of the project.

## 2. Pre-coding

Floor entries below are semantic constraints on the required findings/status summary. Equivalent concise wording counts; exact labels and repeated disclaimers are not required. A compact scope phrase may satisfy multiple constraints. Do not demand every source detail in every paragraph.

| ID | Caveat / required boundary | Claim it protects and source location |
|---|---|---|
| F1 | Closure was on limited evidence with criteria only partly met; B-plus remains a conditional engineering candidate, not a fully certified isolation boundary. | “The Gate was closed and supports continued engineering consideration.” Without this boundary closure becomes full PASS/certification. Source header, Decision and scope, Disposition. |
| F2 | Findings concern tested exec_command/apply_patch paths in the specified Codex 0.163.0 / Ubuntu ARM64 / arrephorion_agent configuration; no successful bypass was observed there, not ruled out universally. | “The tested restrictions worked / feasibility was supported.” A phrase such as “in the tested configuration and paths” is adequate without repeating every version string; never generalize to all tools, platforms, or bypasses. Source Applicable tested scope and Evidence supporting the limited decision. |
| F3 | Protected apply_patch attempts failed at target-read verification, before a demonstrated write; the observed result does not establish the exact kernel enforcement mechanism. | “Protected patch attempts were rejected.” State the read/verification stage when summarizing those attempts. Do not relabel them as completed write-stage denial tests. No requirement to name every untested OS mechanism. Source Evidence supporting the limited decision. |
| F5 | The evidence is reported via the Owner/handoff, not independently reverified raw artifacts by the reviewer. | “The review supports the recorded observations and closure.” “Reported observations” or “according to the Owner-provided audit outputs” is sufficient attribution; no full disclaimer list required. Source evidence introduction and Evidence limitations. |
| F6 | Stage A remains incomplete; Stage B/C and the original pilot remain on hold, requiring a separate decision/authorization. | “Closure supports further engineering consideration.” It does not confer permission to start those stages or mean they passed. Source Decision and scope and Disposition. |

Weighed items describe optional elaborations beyond those minimum boundaries. Including or omitting them is acceptable; no unique combination is required. If a variant makes a stronger claim which needs one of these details to stay accurate, the detail becomes necessary for that claim rather than optional.

| ID | Optional elaboration | Reader judgment changed |
|---|---|---|
| W1 | Explicitly explain that the historical complete tool-definition set could not be recovered. | Explains why coverage cannot be generalized beyond the tested paths; F2 already prevents the generalization. Source Evidence limitations. |
| W2 | Explicitly explain that network=restricted does not demonstrate inability to reach host-side services. | Makes the remaining network evidence gap salient; omission is acceptable when no network-isolation claim is made. Source Evidence limitations. |
| W3 | Explain the ordinary SSH-shell readability contrast and its limited implication for Unix file permissions. | Helps the reader weigh the denial evidence; it does not identify the precise kernel mechanism. Source Evidence supporting the limited decision. |
| W4 | Include the later-stage reopen condition and explain that no further Gate session was required for this bounded decision. | Clarifies how conditional continuation can be revisited without implying closure requires immediate retesting. Source Disposition and Reopen condition. |
| W5 | State that G8 ran with SSH enabled and did not satisfy the original SSH-off condition. (Was F4; see revision note.) | Explains why the original criteria were only partly met. Becomes necessary for any variant that describes G8 as meeting the original protocol, as an SSH-off run, or as retroactively compliant. Source Evidence limitations. |

Acceptable interpretation examples for scoring only: the observations justify retaining B-plus for engineering consideration; the tested restrictions were functional rather than every operation being disabled, because positive workspace controls succeeded; further evidence could be gathered in a separately authorized later stage if needed. These are examples, not required phrases. Do not show this section to the tested model.

## 3. Run

- Fresh session, no memory, custom instructions, or project context.
- Input: the full SKILL.md, then the source, the task, and the intended reader. Nothing else.
- Record model, interface, settings. The first run is the result; any further runs are reported separately and never replace it.

## 4. Scoring (by the author, against section 2)

| ID | Check | Pass condition |
|---|---|---|
| S1 | Floor coverage | Every applicable pre-coded Floor item appears in every delivered variant (F3: only variants that mention the protected apply_patch attempts). |
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

## Pre-run revision (2026-11-09, by C, before any run)

- **F4 → W5.** Under the skill's Floor test, a Floor caveat must name a claim that becomes inaccurate, goes beyond the source, or contradicts a formal status without it. "The Gate was closed based on G8" stays accurate without the SSH detail, and the formal status "criteria partially met" is already protected by F1. The stated rationale ("would obscure why original conditions were only partly met") is a reader-weight argument, which the skill defines as Weighed. Keeping it as Floor would fail S2 when the tested model applies the skill's own rule correctly. It becomes required in any variant whose wording needs it (see W5).
- **F3 is conditional.** F3 binds variants that summarise the protected `apply_patch` attempts or describe them as write denials. "Failed with permission denied" is accurate without the stage; "write attempts were blocked" is not. S1 checks F3 only in variants that mention those attempts. F1, F2, F5, F6 apply to every variant (the task requires scoped observations, the conclusion, and project status).
- S1–S6 thresholds unchanged. The as-received protocol and manifest are kept as `*-as-received.*`.

## Pre-run interpretation notes (no change to S1–S6 thresholds)

- Score S1/S2 by meaning, not literal keyword matching; source attribution and a shared scope phrase can satisfy the corresponding Floor.
- S3 applies equally to overstating and understating the archived decision. Treat the archived closure as the task's historical source, not an instruction to reopen or operate the VM.
- S4 only observes flags and edits disclosed in the output. Silent removal inside unshown drafting is unobservable; a pass cannot establish absence of silent over-editing. With no observable edits, record “0 observed; silent edits unobservable.”
- S6 with no reported fixes is “PASS — no reported fixes; traceability not exercised,” not proof of correction quality.
- S2 does not penalize promotion of Weighed to Floor; report such disagreements under the existing recorded-not-scored items. An overall PASS therefore does not establish absence of tier inflation.
- Do not add newly preferred wording to the frozen Floor list after the run. Report unanticipated concerns separately.
- Source is already a qualified closure report. This tests faithful synthesis and optional emphasis, not extraction from raw experimental data.
- Run 1's model/interface/settings remain UNKNOWN in the supplied run record. G8's historical gpt-6-luna settings are not run 1's evaluator settings. Record v2 settings at execution.
