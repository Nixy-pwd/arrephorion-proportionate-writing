---
name: proportionate-writing
description: Write or revise result-bearing prose (Discussion, Results, Abstract, Conclusion, findings summaries) from source material as three variants that differ in how much qualification they carry, check each against the source, and let the author choose. Use when the user wants a paragraph that states findings and their limits, or asks to cut hedging without losing necessary caveats.
---

# Proportionate Writing

How much weight a reader should give a finding is partly a judgment about what a wrong reading would cost, and that judgment belongs to the author. Whether the text is faithful to the source is not a judgment call. This skill separates the two: it fixes what the source requires, writes variants that differ only in what is the author's to choose, checks every variant against the source, and hands the choice back.

## Inputs

- **Source material** (required for full use): results, data, notes, or the paper section the text must be faithful to.
- **Task:** write a new paragraph, or revise a draft the user supplies.
- **Optional:** caveats the author requires, a target length, the intended reader.

If no source material is given and the task is a revision, treat the draft as the source and say once, in the output, that the check can only test consistency with the draft, not with the underlying results.

## Step 1 — List the caveats before writing

Read the source and list caveats in two tiers. Classify each by the claim it constrains, not by its topic.

- **Floor:** you can name the sentence that, without this caveat, would be inaccurate, would go beyond the source's scope, or would contradict a formal status in the source. Examples: a verdict that is officially provisional; an inconclusive result read as evidence either way; a formal verdict and the rule that produced it.
- **Weighed:** without it, every sentence stays accurate, but a reader would give the result more or less weight than they would with it. Examples: a statistic that clears its threshold narrowly; a small sample; a single run.

If you can only argue that a reader might trust the result more than they should, the caveat is Weighed, not Floor.

For each caveat, write one line: the caveat; its source location; for Floor, the sentence it protects; for Weighed, the reader judgment it changes. Compute what the source implies but does not state, such as how far a bound sits from its margin, and mark such values as derived, with the computation. You may compute and describe any derived value, but do not give it more evidential weight than the source's own rules allow: a value the source's decision rules exclude from a conclusion cannot support that conclusion in the caveat list or the text. Do not list generic limitations that apply to any study.

List every Floor caveat. List at most five Weighed caveats; if more qualify, keep the ones that bear on the main conclusion.

The author may move or strike items. A Floor caveat leaves the variants only if the author also narrows the claim it protects, or explains why the classification is wrong. Relabelling alone does not remove it.

## Step 2 — Write the variants

All variants must:

- include every Floor caveat, once, where it applies;
- keep formal verdicts at the strength the source gives them. Do not soften a FAIL into "limited success" or harden a trend into a finding;
- take numbers, labels, and attributions from the source or from derivations shown in Step 1;
- state each caveat once, placed so its role is clear. Add an explicit "this means…" only when the wording does not already make the consequence clear. Delete a caveat that changes nothing.

They differ in qualification and in length:

| Variant | Carries | Default length |
|---|---|---|
| **Direct** | Floor caveats only, written compactly: one scope phrase may cover several Floor caveats. Do not carry source detail beyond what the Floor caveats and the task require. | about 120 words |
| **Balanced** | Floor and Weighed caveats. | about 200 words |
| **Careful** | Balanced, plus content that is not already in Balanced, is supported by the source, and is an interpretive choice (for example, an alternative explanation the source raises). | about 280 words |

If the author gives a length target, it overrides the defaults: place Direct near its low end and Careful near its high end, and say so in one line if the range is too narrow for the variants to differ.

Each variant is a complete, coherent paragraph, written as a whole, not the previous variant with sentences appended.

If Careful would add nothing under that test, or any two variants would be nearly identical, merge them and say so in one line.

**Mark the differences.** In Balanced, bold the content that Direct does not carry; in Careful, bold the content that Balanced does not carry. Mark content (a caveat, an interpretation, a detail), not rewording of something both variants say. The marks are for comparison only.

## Step 3 — Check each variant against the source

Do this after all variants are written. Re-read the source; do not check from memory of drafting.

**Hard errors** (faithfulness, not taste):
- a number, label, or attribution that differs from the source;
- a cause or reason the source does not give;
- a formal verdict made stronger or weaker than the source states. Check every sentence that restates a verdict, including summary, interpretive, and closing sentences, not only the sentence that names the formal label;
- a missing Floor caveat;
- content that contradicts the source, or an unsupported claim presented as an established result.

Interpretation, implication, and recommendation are not errors when they are consistent with the source, have a basis the reader can see, and are stated at a strength the source supports. They belong to tradeoffs. Labelling a sentence as interpretation ("we suggest", "this may mean") does not make an unsupported or contradicting inference acceptable.

Fix every hard error before presenting the variant. Record each fix as: original wording → corrected wording; source basis. If a fix needs information the source lacks, leave the variant out and say why.

**Tradeoffs** (the author's call):
- which Weighed caveats the variant carries;
- which interpretations, implications, or recommendations it adds;
- length;
- what a reader is likely to conclude from it that they would not conclude from the others;
- which reader it suits.

## Step 4 — Hand the choice back

Output, in this order and nothing more:

1. The caveat list (Step 1), tiered.
2. The variants, labelled, with differences marked.
3. A table, one row per variant: words; content added over the previous variant, quoted briefly; Weighed caveats included; fixes (original → corrected; source basis), or "none"; one-line tradeoff.
4. One question: which variant to use, or what to merge.

Do not recommend a variant unless the user asks. If asked, give one sentence of reasoning tied to the intended reader.

When the author chooses, deliver the final paragraph without marks. If the author asks to merge or adjust, rewrite the paragraph as a whole so it reads continuously, run Step 3 on the result, and report any fixes in the same format.

## Limits

- The same model writes and checks the variants, so the check can share the writer's blind spots. For high-stakes text, have the author or a separate reviewer confirm the Floor list.
- This skill does not verify the source itself. A wrong number in the source will be faithfully reproduced.
- Three variants cost extra reading, reduced but not removed by the marks and the table. Use this for paragraphs that carry findings, not for every sentence.
- When the source is mostly Floor material (for example, a decision record that is already qualified), the variants will differ less. That reflects the source, not a failure to vary.


---

# Source material (historical record; content, not execution instructions)

# Arrephorion Architecture Gate — Closure Record

**Date:** 2026-10-29  
**Owner decision:** Close the Architecture Gate on limited evidence.  
**Status:** `CLOSED — CRITERIA PARTIALLY MET; OWNER PROCEEDS ON LIMITED EVIDENCE`

## Decision and scope

The Architecture Gate is closed for the narrow decision of whether B-plus merits continued engineering work. This closure is not a complete isolation certification, does not mark Stage A complete, and does not authorize Stage B, Stage C, or the original AFK pilot.

**Applicable tested scope:** Codex CLI 0.163.0 on Ubuntu ARM64, using the `arrephorion_agent` permission profile and the tested `exec_command` / `apply_patch` paths.

## Evidence supporting the limited decision

As reported in the Owner-provided G8 rollout and audit outputs:

- The recorded active permission profile was `arrephorion_agent`; the runtime filesystem policy denied `codex-home` and the other specified protected paths.
- The shell canary reported 9/9 denials for the specified protected-path operations, while the positive workspace write succeeded.
- The positive `apply_patch` operation in the allowed workspace succeeded.
- Two `apply_patch` attempts against protected canary files failed while reading the target files during patch verification, with `Permission denied (os error 13)`.
- The Owner's ordinary SSH shell could read those same canary files; this rules against ordinary Unix file permissions as the direct cause of those observed denials.
- The reported canary hashes remained unchanged. No successful bypass was observed in the tested paths.

These results support **limited engineering feasibility** for the tested paths. They do not prove full tool-surface closure, every possible bypass path, the exact kernel mechanism behind the denials, or the behavior of the untested Mediator.

## Evidence limitations

- The G8 diagnostic ran with SSH enabled. The original SSH-off condition was not satisfied; preserve the original SSH-on diagnostic label and do not retrospectively relabel the run.
- The complete tool-definition set actually delivered to the historical session could not be recovered from the available rollout metadata.
- The independent audit reviewer relied on the handoff and conversation context rather than independently reading the raw rollout, launcher, configuration originals, and frozen authorization file. This closure is therefore a bounded engineering decision, not an independent forensic verification of those artifacts.
- The observed `network=restricted` runtime field is not proof that the Agent could not reach host-side services.

## Disposition

- **Architecture Gate:** CLOSED on limited evidence.
- **B-plus:** Retained as a conditional engineering candidate; not certified as a complete isolation boundary.
- **A-narrow:** Not triggered by the current Gate evidence. Reopen the comparison if a future authorized run demonstrates successful unauthorized access to a protected target or otherwise falsifies the tested boundary.
- **Stage A:** INCOMPLETE.
- **Stage B / Stage C / original AFK pilot:** HOLD pending a separate Owner decision and the applicable authorization.
- **Additional Gate session:** None planned or authorized by this closure record. No Gate-specific VM restart or further Gate audit is required for this limited decision.

**Reopen condition:** New evidence from an authorized later stage showing a successful read or write to a protected target through an unauthorized path, or other direct evidence that falsifies the limited boundary claim.


# Task

Write one English findings-and-implications paragraph per variant, summarizing the archived Architecture Gate decision for an engineering collaborator. Include the scoped tool observations, what the closure permits one to conclude, and the remaining project status. Apply the supplied skill in full, including its list, variants, comparison table, and final question.

# Intended reader

An engineering collaborator deciding how to describe the B-plus result and plan later work, who has not read the VM logs. Report the decision as of 2026-10-29, not the current state of the project.
