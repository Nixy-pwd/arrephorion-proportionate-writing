# Evidence

Two small experiments, run November 2026, before the skill existed. Neither establishes efficacy; both are recorded in full, including setup problems, so the strength of the claim in the README can be checked.

**How they relate to the skill:** B1 tested one writing rule (§6, below). Step 2 of the skill uses a loosened version of it: a caveat must be placed so its role is clear, with an explicit explanation only when the wording does not already make the consequence clear. The loosening came from a design audit (B1 output A contains a "This distinction matters because…" sentence, a sign the strict wording can itself add text). The loosened rule has not been tested. B1 says nothing about the skill's other steps: listing caveats, writing variants, checking them, handing back the choice. B1's annotated outputs are reused as the test set for the Step 1 and Step 3 check in [validation/](validation/). A2 concerns agent execution, not writing; it is kept here because it shaped the project's scope.

## B1 — Academic defensive writing (language channel)

**Verdict: positive, suggestive signal.** Not efficacy established.

### Question

Does the §6 writing rule reduce decorative caveats without removing caveats that carry scientific meaning?

### Design

- **Task:** write the Discussion paragraph for a real, frozen audit result: the PM2S V3 DCML domain-transportability audit, Phase 4. In that result, criterion C1 passed, C2 was inconclusive by construction, C3 failed, the global verdict was DOMAIN_TRANSPORTABILITY_FAIL, and the official status was PROVISIONAL_PENDING_PHASE_3B.
- **Generation, not revision.** The model received facts only, so any hedging comes from the model rather than from a source text. A revision task was considered and rejected: the control prompt would already need to ask for concision, and a well-written source leaves little to remove.
- **Conditions:** Control = task prompt. Treatment = the same prompt with §6 prepended. Exact prompts are in [examples/b1-prompts.md](examples/b1-prompts.md).
- **Runs:** 3 per condition, each independent.
- **Model and settings:** Codex, Sol 6.1 (per Nix); reasoning level not recorded.

### Pre-specified criteria

| Behaviour | Counts as defensive inflation |
|---|---|
| Same limitation restated | Yes |
| Generic disclaimer that changes no interpretation | Yes |
| Stacked hedges | Yes |
| Disclaimers aimed at an imagined reviewer | Yes |
| Qualification that changes the conclusion | No |
| Explicit evidence/inference distinction | No |
| Accurate statement of real uncertainty | No |

Fewer caveats was explicitly **not** a success criterion on its own.

- **Failure condition, fixed in advance:** any Treatment output that turns INCONCLUSIVE into evidence of failure, or drops a necessary limitation, counts as a failure.
- **Pre-committed coding:** before the runs, the domain owner coded the C3 near-threshold point (lower bound ≈ 3.080 vs margin 3) as a qualification the text must include. "Must include" here is the author's requirement; omitting it would not make any sentence inaccurate. In the skill's terms it is a Weighed caveat the author chose to keep. Two reviewers had earlier disagreed about whether this margin was "thin".

### Blinding and annotation

Outputs were shuffled and relabelled A–F before annotation. The mapping was withheld from both annotators until both had finished.

| | Knew the §6 text | Had the source facts | Instrument |
|---|---|---|---|
| Annotator 1 (Claude) | Yes, and proposed the design | Yes | Qualitative, per-caveat review |
| Annotator 2 (GPT, unpersonalised temporary chat) | No | No, texts only | 1–5 scores on five dimensions |

Before unblinding, Annotator 1 recorded a prediction: by redundancy, the texts form two clusters, {A, C, E} and {B, D, F}.

### Results

| Label | Group | Words | Annotator 1: redundancy rank (1 = least) | Annotator 2: redundancy (5 = worst) | Annotator 2: concision (5 = best) |
|---|---|---|---|---|---|
| E | Treatment | 205 | 1 | 2 | 5 |
| A | Treatment | 238 | 2 (tie) | 3 | 3 |
| C | Treatment | 245 | 2 (tie) | 3 | 4 |
| B | Control | 296 | 4 | 4 | 3 |
| F | Control | 314 | 5 | 5 | 2 |
| D | Control | 281 | 6 | 4 | 3 |

Word counts are whitespace-delimited tokens of the unedited outputs.

- **Clustering:** both annotators placed all three Treatment outputs in the low-redundancy cluster and all three Control outputs in the high-redundancy cluster, which matched the pre-unblinding prediction. Within the high cluster, the annotators disagreed on which text was worst (D vs F).
- **Chance baseline:** under a model where group labels are assigned at random to the six texts, the probability that they line up exactly with a given 3/3 partition is 1/C(6,3) = 1/20. This is a reference point for an exploratory observation, not a significance test. The two annotators are not independent replications.
- **Length:** mean 229 words for Treatment and 297 for Control, about 23% shorter.
- **No relative loss of limitations:** all six outputs kept the Phase 3B provisional status. No Treatment output dropped a limitation that the Control outputs kept. This does not mean every required caveat was kept: see the shared C3 omission below.
- **Failure condition not triggered:** no output turned C2 into evidence of failure. Treatment output C framed C2 under "does not extend" without stating that it is not evidence of failure; this is borderline, not an overclaim.
- **Calibration drift, Control only (1/3):** D rewrote the formal FAIL as "limited domain transportability… rather than an unconditional rejection", softening the verdict.
- **Omission shared by both groups:** no output in either group stated that C3 exceeded its margin by only about 2.65%. The prompt supplied exact fractions and did not ask for this comparison, so the omission is recorded as shared, not as a Treatment loss. All six outputs did report ≈3.080 against 3.000.
- **Minor fidelity issues, any group:**
  - B attributes C2's gate to "a limitation of the available reference distribution". The frozen reason code is `MARGIN_BELOW_WITHIN_CORPUS_VARIABILITY`, meaning the margin is tighter than within-corpus variability.
  - E describes the C1 pass as "demonstrated satisfactory transportability", which slightly overstates an equivalence-within-margin result.

### Competing explanations

- **Generic concision instruction (plausible):** the comparison was §6 against no instruction. A plain "be concise, no disclaimers" instruction might produce the same effect, so this test cannot attribute the result to §6's specific mechanism (naming the judgment each caveat changes). One weak hint favours the specific mechanism: output A contains "This distinction matters because…", which reads like the rule at work.
- **Sampling variance:** n = 3 per group. The 1/20 baseline assumes the annotators' clustering is independent of anything other than condition, but both annotators judged features (length, repetition) that are correlated.

### Limitations

- One task, one model, one paragraph type, three runs per condition.
- Both annotators are AI models, and Annotator 1 was not blind to the rule.
- The domain owner's own per-caveat coding was not completed. Only the C3 item was pre-coded.

### Side observation (anecdote)

Annotator 2 suggested weakening D's "statistically supported deviation" to "an observed discrepancy… under the current measurement framework". The deviation is supported under the frozen rule, and Phase 3B status is stated separately, so the suggestion adds a hedge to an established result. This is one instance of over-caution in the evaluator itself; recorded, not generalised.

## A2 — Small local code change (execution channel)

**Verdict: suggestive, no demonstrated benefit or harm.**

### Design

- **Fixture:** a disposable Python repository with three small modules (`label_tools`, `date_tools`, `path_tools`), standard-library `unittest`, and one baseline commit, cloned twice. Clones were used instead of worktrees because worktree metadata sits outside a sandboxed working directory.
- **Task:** add `collapse_whitespace()` to `label_tools.py`, with focused tests. Control used the task prompt alone; Treatment had the full v0 rules (§1–7) prepended.
- **Environment:** Codex desktop app, GPT-6.1 Sol, Medium reasoning, approval mode "Approve for me", both conditions. Global AGENTS.md was a fixed background variable; there was no project-level AGENTS.md.
- **Pre-specified inflation criteria:**
  - Not inflation: running the full suite or a single module once; re-running after a failure.
  - Inflation: repeating runs with no failure; static checks, linting, or hashing; changes outside the helper and its tests; a second review with no failure to trigger it.

### Results (from final reports; full rollouts not compared)

| | Control | Treatment |
|---|---|---|
| Implementation | `" ".join(text.split())`, correct | Identical |
| Tests added | 6 | 7 cases |
| Scope | Helper and tests only | Same |
| Verification | Full suite once (18 tests), plus `git diff --check` | label module once |

`git diff --check` was the only inflation item, and it is cheap.

### Interpretation

- **Ceiling effect:** in a clean repository, the model without v0 was already restrained, so v0 had nothing to remove.
- **Weakly consistent with instruction- or context-induced inflation:** the heavy over-verification seen in earlier project work did not appear here. Project instructions, audit history, task simplicity, and model habit cannot be separated with this design, so this stays plausible, not supported.

### Operational deviations (not counted)

- The app first pointed both projects at newly created empty folders. The runs were redone against the correct clones.
- The first Control run inherited completed work from an earlier session. The clone was reset to baseline and the run repeated in a fresh chat; only the repeat counts.
