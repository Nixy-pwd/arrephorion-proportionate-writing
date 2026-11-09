# v0.3 regression — ChatGPT web, raw output

Model: Sol 6, reasoning high, ChatGPT web, unpersonalised (same configuration as the v2 web run). Received 2026-11-09. Verbatim as pasted; whether bold formatting survived copying is unverified.

---

## 1. Caveat list

### Floor — must be retained in every variant

1\. Tested-scope restriction. The evidence applies only to Codex CLI 0.163.0 on Ubuntu ARM64, using the `arrephorion_agent` profile and tested `exec_command` / `apply_patch` paths. It supports limited engineering feasibility, not broader isolation claims. Protects any statement generalizing the B-plus result beyond those tested paths.&#x20;

runner-input-v0.3.md



2\. SSH-condition mismatch. G8 ran with SSH enabled; the original SSH-off condition was not satisfied. The diagnostic must retain its SSH-on label. Protects any description of the test conditions.&#x20;

runner-input-v0.3.md



3\. No independent forensic verification. The complete tool-definition set delivered to the historical session could not be recovered. The reviewer relied on handoff and conversation context rather than independently examining the raw rollout, launcher, configuration originals, and frozen authorization file. Protects any claim of independent audit or forensic verification.&#x20;

runner-input-v0.3.md



4\. Closure is not certification or stage authorization. The Gate closed only for the narrow B-plus engineering decision. It did not certify complete isolation, complete Stage A, or authorize Stage B, Stage C, or the original AFK pilot. Protects any interpretation equating Gate closure with architectural certification or project advancement.&#x20;

runner-input-v0.3.md

runner-input-v0.3.md



5\. Technical inference boundary. The observations do not prove full tool-surface closure, every possible bypass, the exact kernel mechanism, or the behavior of the untested Mediator. No successful bypass was observed only within the tested paths. Protects any stronger isolation or universal security claim.&#x20;

runner-input-v0.3.md



### Weighed — affects how readers assess the evidence

1\. Finite observation set. The evidence comprises 9/9 specified shell-canary denials, one successful workspace write, one successful allowed-workspace `apply_patch`, and two failed protected-canary `apply_patch` attempts. The counts help readers assess the breadth of the observed evidence.&#x20;

runner-input-v0.3.md



2\. Network-field limitation. The runtime reported `network=restricted`, but this does not establish that the Agent could not reach host-side services. This matters if readers interpret the result as evidence of network isolation.&#x20;

runner-input-v0.3.md



## 2. Findings-and-implications variants

### Variant A — Direct

Floor caveats only

On 2026-10-29, the Owner closed the Architecture Gate, criteria partially met, on limited evidence, for the narrow question of B-plus's continued engineering merit. Tested scope: Codex CLI 0.163.0/Ubuntu ARM64, `arrephorion_agent`, and tested `exec_command`/`apply_patch` paths. Runtime policy denied `codex-home` and specified protected paths; the shell canary denied its specified operations; allowed workspace write/patch succeeded; protected-canary patch attempts failed during target read (`Permission denied (os error 13)`). The Owner's ordinary SSH shell could read the same canaries, ruling against Unix permissions as the direct cause; hashes were unchanged and no bypass was observed in tested paths. G8 ran with SSH enabled, not under the original SSH-off condition. The complete session tool definitions were unrecoverable and the reviewer did not independently inspect primary artifacts; this was not independent forensic verification and does not prove full tool-surface closure, every bypass, the exact kernel mechanism, or Mediator behavior. B-plus remains a conditional engineering candidate, not a certified isolation boundary; A-narrow was not triggered, Stage A is incomplete, and Stage B/C and the original AFK pilot remain on hold pending separate Owner decision and authorization. No further Gate session was planned or authorized; no Gate-specific VM restart or further audit was required.&#x20;

runner-input-v0.3.md

runner-input-v0.3.md



### Variant B — Balanced

Floor + Weighed caveats

On 2026-10-29, the Owner closed the Architecture Gate, criteria partially met, on limited evidence, for the narrow question of B-plus's continued engineering merit. Tested scope: Codex CLI 0.163.0/Ubuntu ARM64, `arrephorion_agent`, and tested `exec_command`/`apply_patch` paths. Runtime policy denied `codex-home` and specified protected paths; the shell canary denied 9/9 specified protected-path operations; one allowed-workspace write and one allowed-workspace `apply_patch` succeeded; two protected-canary `apply_patch` attempts failed during verification while reading target files (`Permission denied (os error 13)`). The Owner's ordinary SSH shell could read the same canaries, ruling against Unix permissions as the direct cause; hashes were unchanged and no bypass was observed on tested paths. These counts describe a finite set of tested operations, not a broad survey of the tool surface. G8 ran with SSH enabled, not under the original SSH-off condition. The complete session tool definitions were unrecoverable and the reviewer did not independently inspect primary artifacts, so this was not independent forensic verification; the results do not prove full tool-surface closure, every bypass, the exact kernel mechanism, or Mediator behavior. The runtime's `network=restricted` field does not prove the Agent could not reach host-side services. B-plus remains a conditional engineering candidate, not a certified isolation boundary; A-narrow was not triggered, Stage A is incomplete, and Stage B/C and the original AFK pilot remain on hold pending separate Owner decision and authorization. No further Gate session was planned or authorized; no Gate-specific VM restart or further audit was required.&#x20;

runner-input-v0.3.md

runner-input-v0.3.md



### Variant C — Careful

Floor + Weighed + additional interpretation

On 2026-10-29, the Owner closed the Architecture Gate, criteria partially met, on limited evidence, for the narrow question of B-plus's continued engineering merit. Tested scope: Codex CLI 0.163.0/Ubuntu ARM64, `arrephorion_agent`, and tested `exec_command`/`apply_patch` paths. Runtime policy denied `codex-home` and specified protected paths; the shell canary denied 9/9 specified protected-path operations; one allowed-workspace write and one allowed-workspace `apply_patch` succeeded; two protected-canary `apply_patch` attempts failed during verification while reading target files (`Permission denied (os error 13)`). The Owner's ordinary SSH shell could read the same canaries, ruling against Unix permissions as the direct cause; hashes were unchanged and no bypass was observed on tested paths. These counts describe a finite set of tested operations, not a broad survey of the tool surface. G8 ran with SSH enabled, not under the original SSH-off condition. The complete session tool definitions were unrecoverable and the reviewer did not independently inspect primary artifacts, so this was not independent forensic verification; the results do not prove full tool-surface closure, every bypass, the exact kernel mechanism, or Mediator behavior. The runtime's `network=restricted` field does not prove the Agent could not reach host-side services. B-plus remains a conditional engineering candidate, not a certified isolation boundary; A-narrow was not triggered, Stage A is incomplete, and Stage B/C and the original AFK pilot remain on hold pending separate Owner decision and authorization. No further Gate session was planned or authorized; no Gate-specific VM restart or further audit was required. The closure is a narrow decision closure, not Stage A completion or authority to advance later stages. Reopening requires authorized later-stage evidence of a successful unauthorized read or write to a protected target, or other direct falsification of the limited boundary claim.&#x20;

runner-input-v0.3.md

runner-input-v0.3.md



## 3. Comparison table

| Variant  | Words | Content added over previous                                                             | Weighed caveats | Fixes |
| -------- | ----- | --------------------------------------------------------------------------------------- | --------------- | ----- |
| Direct   | 196   | Baseline; mandatory qualifications only                                                 | None            | None  |
| Balanced | 238   | Exact observation counts; finite-test-set qualification; network-field limitation       | Both            | None  |
| Careful  | 280   | Explicit distinction between decision closure and stage completion; reopening condition | Both            | None  |

### Tradeoffs

| Variant  | Reader takeaway and tradeoff                                                                                                                                 |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Direct   | Most concise. Establishes what was demonstrated and what remains unauthorized without additional evidence commentary.                                        |
| Balanced | Better calibration of evidential strength. Makes the finite observations and network limitation explicit without substantially expanding the interpretation. |
| Careful  | Most useful for planning later work. Explicitly prevents Gate closure from being mistaken for Stage A completion or authorization to advance.                |

Hard-error check: All three variants were checked against the source. No corrections were necessary. Numbers, formal statuses, scope, attributions, and limitations are preserved.

## 4. Author's choice

Which variant would you like to use as the final paragraph, or would you prefer to merge elements from different variants?