# v2 验证材料包

已找回 2026-10-29 最终 Gate 关闭记录，并在运行前完成六条 Floor、四条 Weighed 预编码；运行前 C 将 F4 改为 W5，现为五条 Floor、五条 Weighed（见 v2-protocol-filled.md 的 Pre-run revision）。尚未运行验证。

## 怎么用

1. 把本包交给 C 存档。不要把整个包交给被测模型。
2. 在无记忆、无自定义指令、无项目上下文的新会话，只粘贴 `runner-input.md` 的全部内容。它已包含原样 v0.2 SKILL、完整来源、任务和读者。
3. 保存完整输出并记录实际模型、界面和设置。首次运行即正式结果。
4. C/Nix 使用 `v2-protocol-filled.md` 评分；其中预编码不得提前进入被测会话。

## 文件与来源

- `source.md`：GitHub 固定提交中的完整关闭记录，文字未改。
- `SKILL.md`：此次用户提供 v0.2 ZIP 内的原件，未修改。
- `runner-input.md`：唯一给被测模型的输入。
- `v2-protocol-filled.md`：填好的协议及预编码，保留原 S1–S6 阈值。
- `manifest.json`：上述文件的 SHA-256，锁定本次准备版本；不代表验证通过。

原文：[private repository; address redacted]/docs/research/stage1-preflight/ARREPHORION_ARCHITECTURE_GATE_CLOSURE_RECORD_2026-10-29.md

此前检索到的 INCONCLUSIVE/HOLD 报告是中间状态；本包采用后续已归档的最终关闭记录。G8 原始 rollout 未在本次独立重验。

协议的样本说明已在运行前修正：这是未用于 skill 开发的新案例，但设计者历史上看过，不称为 designer-unseen holdout。预编码由 G 受 Nix 委托准备，不称为独立人工编码。

run 1 模型/界面/设置仍未知；不可拿 VM 当时的模型设置代填。
