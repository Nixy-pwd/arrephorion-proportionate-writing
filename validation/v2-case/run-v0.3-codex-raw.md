# v0.3 regression — Codex, raw output

Model: Sol 6.1, reasoning high, Codex (same configuration as the v2 Codex run). Received 2026-11-09. Verbatim.

---

**1. 限定条件清单**

以下以附件中的历史记录为事实来源；英文段落报告的是 **2026-10-29** 的决定，不代表项目当前状态。

**Floor：保证陈述准确所必需**

| 限定条件 | 来源位置 | 保护的陈述 |
|---|---|---|
| Gate 已关闭，但标准仅部分满足，Owner 基于有限证据推进。 | 开头状态；Disposition | “Gate 已关闭”不能被理解为全部标准通过。 |
| 工具结果来自 Owner 提供的记录，适用范围限于指定版本、平台、权限配置和路径。 | Decision and scope；Evidence supporting… | 工具观察和可行性结论不能推广至其他运行条件。 |
| 两次受保护目标的 `apply_patch` 失败发生在验证时读取目标文件的阶段。 | Evidence supporting…，第 4 项 | 不能将其描述为已单独验证所有写入路径均被阻断。 |
| G8 是 SSH-on 诊断，原定 SSH-off 条件未满足。 | Evidence limitations，第 1 项 | 不能将该运行重新标为满足原测试条件。 |
| 证据只支持已测试路径的有限工程可行性，不构成完整隔离认证，也不覆盖所有工具、绕过路径或未经测试的 Mediator。 | Decision and scope；Evidence supporting…，结尾 | B-plus 的可行性结论必须保留范围。 |
| B-plus 仍是有条件的候选；Stage A 未完成；后续阶段及原 AFK pilot 仍须单独决定和授权。 | Disposition | Gate 关闭不等于阶段完成或后续工作获准。 |
| 当前证据未触发 A-narrow；后续获授权运行中的未授权访问或其他直接反证会触发重新比较。 | Disposition；Reopen condition | 不能将 A-narrow 描述为已启动或永久排除。 |
| 此次关闭没有计划或授权额外 Gate 会话，也不要求 Gate 专用重启或进一步审计。 | Disposition，最后一项 | 不能把后续 Gate 操作写成本次决定要求的工作。 |

**Weighed：影响读者如何衡量证据**

| 限定条件 | 来源位置 | 改变的读者判断 |
|---|---|---|
| 无法恢复历史会话实际收到的完整工具定义集。 | Evidence limitations，第 2 项 | 降低读者对工具覆盖范围可核查性的信心。 |
| 独立审阅者依赖交接和对话上下文，没有独立读取原始 rollout、launcher、配置及冻结授权文件。 | Evidence limitations，第 3 项 | 限制审阅独立性所能增加的证据权重；不能据此声称完成独立取证核验。 |

没有需要计算的派生数值。Careful 另外讨论来源明确支持的权限机制、哈希及网络字段解释；相应限定随这些新增内容出现。

**2. 写作版本**

**Direct**

As of 29 October 2026, the Architecture Gate was CLOSED—CRITERIA PARTIALLY MET; OWNER PROCEEDS ON LIMITED EVIDENCE—for deciding whether B-plus merits continued engineering. In Owner-reported tests of Codex CLI 0.163.0 on Ubuntu ARM64 under arrephorion_agent, shell checks returned 9/9 protected-path denials and an allowed workspace write succeeded; workspace apply_patch succeeded, while two protected-canary patches failed when verification tried to read their targets. This was an SSH-on diagnostic; the original SSH-off condition was unmet. These observations support limited engineering feasibility for the tested exec_command/apply_patch paths, not complete isolation certification or coverage of all bypasses, tools, or the untested Mediator. B-plus remains a conditional engineering candidate. Stage A is INCOMPLETE; Stage B, Stage C, and the original AFK pilot remain on HOLD pending a separate Owner decision and applicable authorization. A-narrow was not triggered; reopen the comparison upon later authorized evidence of successful unauthorized protected-target access or other direct falsification of the limited boundary claim. Closure neither plans nor authorizes another Gate session, and requires no Gate-specific VM restart or further Gate audit.

**Balanced**

As of 29 October 2026, the Architecture Gate was CLOSED—CRITERIA PARTIALLY MET; OWNER PROCEEDS ON LIMITED EVIDENCE—for the narrow decision of whether B-plus merits continued engineering. Owner-reported tests covered Codex CLI 0.163.0 on Ubuntu ARM64 under arrephorion_agent: shell checks denied 9/9 specified protected-path operations while an allowed workspace write succeeded; workspace apply_patch also succeeded, whereas two protected-canary patches failed while reading targets during verification. The diagnostic ran with SSH enabled, leaving the original SSH-off condition unmet. The evidence supports limited engineering feasibility on these exec_command/apply_patch paths, not complete isolation certification, exhaustive bypass or tool coverage, or conclusions about the untested Mediator. **The historical session’s complete delivered tool-definition set could not be recovered. Moreover, the independent audit reviewer used the handoff and conversation context rather than independently inspecting the raw rollout, launcher, configuration originals, and frozen authorization file; closure therefore represents a bounded engineering decision, not independent forensic verification.** B-plus remains conditional, and A-narrow was not triggered. Stage A is INCOMPLETE; Stage B, Stage C, and the original AFK pilot remain on HOLD pending a separate Owner decision and applicable authorization. Later authorized evidence of successful unauthorized protected-target access, or other direct falsification of the limited boundary claim, would reopen the comparison. Closure plans and authorizes no additional Gate session and requires no Gate-specific VM restart or further Gate audit.

**Careful**

As of 29 October 2026, the Architecture Gate was CLOSED—CRITERIA PARTIALLY MET; OWNER PROCEEDS ON LIMITED EVIDENCE—to decide narrowly whether B-plus merits continued engineering. Owner-reported tests of Codex CLI 0.163.0 on Ubuntu ARM64 under arrephorion_agent produced 9/9 shell denials for specified protected-path operations alongside a successful workspace write; workspace apply_patch succeeded, while two protected-canary patches failed when verification read their targets. The diagnostic remained SSH-on, with the original SSH-off condition unmet. The historical session’s complete delivered tool-definition set was unrecoverable, and the independent audit reviewer relied on handoff and conversation context rather than independently reading the raw rollout, launcher, configuration originals, and frozen authorization file. Consequently, closure is a bounded engineering decision rather than independent forensic verification: it supports limited feasibility for the tested exec_command/apply_patch paths, without certifying complete isolation, exhaustive tool or bypass coverage, or the untested Mediator. **The Owner’s ordinary SSH shell could read the same canaries, arguing against ordinary Unix permissions as the direct cause of those denials without establishing the exact kernel mechanism. Reported canary hashes remained unchanged and no bypass was observed on the tested paths. Likewise, the runtime network=restricted field does not establish that host-side services were unreachable.** These distinctions support describing B-plus as a conditional engineering candidate while treating later-stage authorization as a separate decision. A-narrow was not triggered; Stage A remains INCOMPLETE, and Stage B, Stage C, and the original AFK pilot remain on HOLD pending a separate Owner decision and applicable authorization. Reopen the comparison upon later authorized evidence of successful unauthorized protected-target access or other direct falsification of the limited boundary claim. Closure plans and authorizes no further Gate session and requires no Gate-specific VM restart or additional Gate audit.

**3. 对比与核查**

已在三个初稿完成后重新读取来源逐项核查。词数按空白分隔统计，不含版本标签和比较标记；Direct 为保留必要限定及项目状态，长于默认约 120 词。

| 版本 | 词数 | 相比前版新增内容 | Weighed 条件 | 核查修正及来源依据 | 取舍 |
|---|---:|---|---|---|---|
| Direct | 171 | 基础版本 | 无 | “reconsideration requires…” → “reopen the comparison upon…”；Reopen condition 给出触发条件，不应改写为排他的必要条件。 | 适合简短交接；保留决定边界，较少解释证据质量。 |
| Balanced | 219 | “complete delivered tool-definition set”；“not independent forensic verification” | 两项全部包含 | “decision to continue evaluating B-plus” → “decision of whether B-plus merits continued engineering”；与 Decision and scope 的决策范围精确对齐。 | 让未读日志的协作者同时看到结果与证据可核查性的限制。 |
| Careful | 280 | “ordinary SSH shell”；“canary hashes remained unchanged”；“network=restricted” | 两项全部包含 | 无 | 增加机制与网络解释边界，适合需要据此讨论后续技术工作的读者；阅读负担最高。 |

**需要我决定的事项：**你希望采用哪个版本，或合并哪些内容？