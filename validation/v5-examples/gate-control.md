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

Write one English findings-and-implications paragraph per variant, summarizing the archived Architecture Gate decision for an engineering collaborator. Include the scoped tool observations, what the closure permits one to conclude, and the remaining project status.

# Intended reader

An engineering collaborator deciding how to describe the B-plus result and plan later work, who has not read the VM logs. Report the decision as of 2026-10-29, not the current state of the project.
