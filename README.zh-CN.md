# Arrephorion — Proportionate Writing（相称写作）

[English](README.md) · 中文

一个针对"防御性写作"的写作 skill，用于承载研究结果的文字：减少对读者没有作用的限定，同时不丢掉有作用的限定。

它会先从原始材料中列出所有可能的限定，分清哪些是忠实于材料所必需的、哪些可以由作者取舍，然后只在后者上写出三个版本，逐一对照材料核查，最后交给作者选择。

**状态：** v0.3。在一次盲评对比中，同样的模型加上 skill 后，重复的限定更少，篇幅短了约三分之一，必要限定一条没丢（一份材料，每种配置各跑一次：属于初步迹象，尚未证实）。在 Codex 和 ChatGPT work 模式下表现稳定；不推荐在 ChatGPT 聊天模式下使用。详见[证据](#证据)。

## 用来解决什么

**防御性写作**是指保护作者、而不是帮助读者的限定，包括：

- 同一个限定换着说法重复说；
- 不改变任何解释的泛泛免责；
- 同一个论断上层层叠加的对冲；
- 为想象中的审稿人质疑而提前加的免责句。

以下**不算**防御性写作：会改变读者结论的限定、明确区分证据与推断、对真实存在的不确定性做准确限定。

每条限定都要过同一个检验：**说出它改变了读者的哪个判断，说不出来就删掉。**

成功包括两部分，缺一不可：

1. **目标：** 装饰性的限定变少。
2. **护栏：** 必要的限定一条不丢，也不能在删减过程中把结论说得比材料更重。

只是限定变少了，不算成功。删对冲的工具，也可能顺手删掉那条让句子保持准确的限定。

## 例子

以下是三个案例的真实输出，引文保留原句、去掉了加粗。每个案例都是在同一个模型、同一份材料、同一个任务下，对比加与不加完整 skill 的结果。

### 案例一：休谟论人格同一性（人文学科；完整 skill 加与不加）

**重复（对应目标）。** 不加 skill（ChatGPT work 模式）时，同一段在开头、中间、结尾各说了一次"正面解释不完整"：

> Hume’s account in Treatise 1.4.6 provides a stronger basis for rejecting an experientially warranted conception of a simple, enduring self than for accepting his explanation of the unity of perceptions.
>
> It nevertheless leaves the positive account insecure, since appealing to connected perceptions cannot complete the explanation while their connection in consciousness remains unresolved.
>
> The resulting position is thus an enduring challenge to the simple self accompanied by an acknowledged failure to explain fully the unity attributed to its perceptual succession.

加 skill（同一配置）时，这个限定只在用得上的地方说一次：

> These considerations do not resolve the Appendix’s difficulty: Hume cannot reconcile perceptions’ distinct existence with the mind’s inability to perceive real connections among them, and finds no satisfactory account of their union in consciousness.

**丢掉必要限定（对应护栏）。** 原文说记忆"与其说产生、不如说发现人格同一性"（does not so much produce as discover，1.4.6.20），这是一个比较句。不加 skill（ChatGPT 聊天模式）时，它被改写成了绝对否定：

> Memory plays a central role in this process, not by producing identity itself, but by revealing connections among past perceptions …

加 skill（work 模式；Codex 版本同样保住了这个范围）时，比较的意思保留了下来：

> Memory reveals causal relations among perceptions, enabling identity to extend beyond remembered episodes rather than constituting it entirely (1.4.6.20).

### 案例二：PM2S 领域可迁移性审计（实证结果；完整 skill 加与不加）

这是对一个 MIDI 转谱方法在新语料上的统计审计。正式结论为 DOMAIN_TRANSPORTABILITY_FAIL，由准则 C3 决定；C3 的下界（约 3.0795）只比 3 半音的界值高出约 2.65%；状态为 PROVISIONAL_PENDING_PHASE_3B（待 Phase 3B 验证的临时结论）。两组都在 Codex 上运行，用的是同一份冻结的事实。中文版例子用的是 Codex 用中文作答的输出（英文版 README 用的是英文输出）。

**重复与预防性免责（对应目标）。** 不加 skill 时，同一句话里把"暂定"说了两遍，还提前为材料根本没涉及的东西免责（"整体音乐结构或下游性能"、"该方法在新领域的所有用途"）：

> 上下声部内部有符号音高变化分布的分曲目平衡1-Wasserstein距离，其95%上界均低于2半音的容许界限，支持这两项声部内部几何特征在规定容差内的跨领域一致性；这一结论并不等同于整体音乐结构或下游性能的等价。
>
> 不过，由于Phase 3B解析器及测量工具验证尚未执行，正式结论仍为待验证的暂定状态：当前结果确立的是审计规则下的暂定失败，尚不能据此断言差异完全源于领域本身，或该方法在新领域的所有用途均会失效。

加 skill（Balanced 版）时，暂定状态只说一次，也没有添加材料不支持的内容：

> 正式状态仍为 PROVISIONAL_PENDING_PHASE_3B，解析器与测量工具验证尚未执行。

**没人写出的那条限定（对应护栏）。** C3 失败得有多勉强，是读者判断这个失败有多稳固时需要知道的，作者也事先要求写进去。不加 skill 时没有写；更早的 B1 实验里，六份输出也一份都没写。skill 根据精确分数算出了它，在限定清单里把它列为可选限定，并注明"不能据此软化正式 FAIL"；Balanced 版写了出来，同时没有把结论说轻：

> 该下界约为 3.07953 半音，仅高于界值约 0.07953 半音。

### 案例三：Linux VM 沙盒关卡（工程决策记录；完整 skill 加与不加）

这是一份架构关卡的关闭记录，测试的是 Codex agent 在 Linux 虚拟机中的权限配置；正式状态是 "CLOSED — CRITERIA PARTIALLY MET; OWNER PROCEEDS ON LIMITED EVIDENCE"（已关闭，标准部分满足，基于有限证据推进）。两组都在 Codex 上运行。

这一组里，不加 skill 的输出本身就很干净：每条限定只说一次，没有把结论说重，也没有内容错误。原因是这份记录本身已经把限定写好了，没有多少防御性写作可删。在这类材料上，skill 带来的是选择：哪些限定必须写，哪些由作者决定。

| 内容 | 不加 skill（238 词） | Direct（171） | Balanced（219） | Careful（280） |
|---|:-:|:-:|:-:|:-:|
| 状态"标准部分满足"；B-plus 是有条件的候选，未获认证 | ✓ | ✓ | ✓ | ✓ |
| 测试范围；9/9 拒绝；patch 尝试在验证读取阶段失败 | ✓ | ✓ | ✓ | ✓ |
| 诊断开着 SSH，原定的关闭 SSH 条件未满足 | ✓ | ✓ | ✓ | ✓ |
| Stage A 未完成；Stage B/C 和 pilot 暂停；不再开关卡会话；重开条件 | ✓ | ✓ | ✓ | ✓ |
| 历史会话的完整工具定义无法恢复 | ✓ | | ✓ | ✓ |
| 审计者没有独立检查原始文件 | ✓ | | ✓ | ✓ |
| `network=restricted` 不能说明主机服务被隔离 | ✓ | | | ✓ |
| 普通 SSH shell 能读同样的文件；canary 哈希未变 | ✓ | | | ✓ |

不加 skill 时，读者拿到的是一段把所有内容都塞进去的文字。加了 skill，前四行在每个版本里都固定保留，后四行由作者决定要不要写。

### 你会拿到什么

skill 会返回限定清单、三个版本（每版比上一版新增的内容加粗），以及一张这样的对比表（节选自 work 模式在休谟案例上的一次运行）：

| 版本 | 词数 | 比上一版新增 |
|---|---:|---|
| Direct | 121 | 基础版 |
| Balanced | 199 | "no underlying stage"；"absence of a precise standard" 及其例外 |
| Careful | 272 | 把"何时用'同一性'这个词"与"知觉如何构成一个心灵"分开；"感受到的过渡"与"真实联结"的区别；"解释缺口"的读法 |

## 为什么要给多个版本

模型修改对冲时，常把两个问题混在一起：

- **文字是否忠实于材料？** 这不是品味问题。把正式结论说轻了，或者漏掉"临时结论"这样的状态，都是错误。
- **读者应该给这个结果多大分量？** 这部分是价值判断，取决于误读的代价。一个勉强过线的阈值、一个很小的样本，可以强调，也可以不提，要看读者是谁。

我们调研过的工具，默认流程都是把这两个问题一并处理，只交出一个改好的版本。这个 skill 把第一个问题定死，把第二个问题交还给对文字负责的人。

## 工作流程

1. **分两层列出限定。** 如果能指出某条限定保护的是哪句话（没有它，那句话就会不准确、超出材料范围，或与正式状态相矛盾），它就是 **Floor**（必写）。否则是 **Weighed**（可选）：每句话都仍然准确，只是读者对结果的信任程度会变。skill 还会计算材料隐含但没有写明的东西，比如某个界离阈值有多近，并给出计算过程。
2. **写出三个版本。** Direct 只含 Floor，写得紧凑，约 120 词；Balanced 含 Floor + Weighed，约 200 词；Careful 在此基础上加入有材料依据、Balanced 里还没有的解释，约 280 词，没有可加的内容就合并掉。每版都是整段重写的完整段落，不改变正式结论的强度，每条限定只说一次。每版比上一版新增的内容会加粗。
3. **逐版对照材料核查。** 硬错误在交给你之前就修好，并按"原文 → 修正 + 依据"记录；取舍只做描述。
4. **把选择交还给你。** 你会拿到限定清单、标好差异的三个版本、一张引用新增内容的对比表，以及一个问题。你选定或要求合并后，skill 会交出一段去掉标记、读起来连贯的定稿，并重新核查。你可以调整限定的层级，但一条 Floor 限定要从正文中删掉，前提是它所保护的那句主张也相应收窄。

完整说明见 [skills/proportionate-writing/SKILL.md](skills/proportionate-writing/SKILL.md)。可以作为 Claude Code 或 Codex 的 skill 使用，也可以直接贴进对话。

## 在哪里运行

已测试的配置及其在两份材料上的结果见 [CONFIGURATIONS.md](CONFIGURATIONS.md)。简单说：推荐 Codex（Sol 6.1，high）或 ChatGPT work 模式（Astra 6，light）；不推荐 ChatGPT 聊天模式（Sol 6，high），因为它是在前一版后面追加句子而不是重写，没有标出差异，而且出现了唯一一处内容错误。该文件里还列了三项自查要点，供你在其他配置下使用时参考。

## 适用场景

Discussion、Results、Abstract、Conclusion 段落，以及研究发现的总结：也就是读者会依据其中主张采取行动的文字。三个版本意味着额外的阅读量，所以不适合每句话都用。

## 证据

### 对照目标：加不加 skill

材料是休谟论人格同一性；材料、任务和读者设定完全相同；三种配置；拿 skill 的 Balanced 版和不加 skill 写出的段落对比；由另一个模型盲评，评分标准在任何对照组输出出现之前就已冻结。[validation/v4-baseline/result.md](validation/v4-baseline/result.md)

| | 不加 skill | 加 skill |
|---|---|---|
| 重复的限定（目标） | 3 | 1 |
| 词数 | 876 | 590 |
| 缺失的必要限定（护栏） | 1 | 0 |
| 内容错误（护栏） | 2 | 0 |

- **目标达成：** 重复的限定更少，篇幅短了约三分之一。
- **护栏守住：** 必要限定全部保留，没有错误。在 Codex 和 work 模式下，两组都写得准确；不加 skill 时出现的护栏失守，都出在 ChatGPT 聊天模式。
- **局限：** 一份材料，每种配置各跑一次，一个评分者。加 skill 的段落更短，评分者可能据此猜出哪段来自哪组。

这和更早的 B1 实验一致：B1 只测了 skill 里关于限定的那条规则（一个更早、更严格的版本），加规则的三段全部比不加的三段冗余更少，而且没有出现限定的相对损失（[EVIDENCE.md](EVIDENCE.md)）。

### 护栏在新材料上的表现

- **技术决策记录**（一次架构关卡的关闭记录，[validation/v2-case/](validation/v2-case/)）：Codex 和 work 模式下都没有内容错误；"已关闭，标准部分满足"这一正式状态从未被转述成"通过"。
- **人文学科的解读**（休谟，[validation/v3-case/](validation/v3-case/)）：Codex 和 work 模式下都没有内容错误；ChatGPT 聊天模式把记忆的作用说重了。关于那句话的一处评分分歧已如实记录。

### 开发记录

- v0.1 第一次检验没有通过（样本内，[validation/run-1.md](validation/run-1.md)）：漏掉了一处被软化的结论，又把正当的解释标成了错误。v0.2 修正了这两点。
- v0.2 在新材料上保持了忠实，但三个版本几乎没有差别。v0.3 加入了长度预算、差异标注和整段重写。
- 我们自己对 Floor/Weighed 的预编码在不同审阅者之间有过变动，其中一条评分规则（条件性 Floor 项）被证明设计有误。两者都记录在各验证文件夹中。

## 局限

- 重要的文字，请你自己或另请一位审阅者确认 Floor 清单。
- 它不核查材料本身。你结果里的错误数字会被忠实地照搬。
- 不同模型对 Floor/Weighed 的划分不一致。目前出现的划分错误都是把可选的当成必写的，这只会让最短的版本变长，不会漏掉东西。
- 如果材料本身大多是必写内容，三个版本的差别会比较小。

## 已有工作

调研于 2026-11-09。各仓库的细节由另一个模型（GPT）读取仓库得出，我们没有逐个文件复核。

| 工作 | 做了什么 | 与本 skill 的区别 |
|---|---|---|
| [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) | 对限定语分类（不必要的免责、必要的范围条件、方法局限等），保留必要的 | 默认只返回一个修改版 |
| [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing)、[blader/humanizer](https://github.com/blader/humanizer)、[op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)、[MrGeDiao/shuorenhua](https://github.com/MrGeDiao/shuorenhua) | 去除 AI 腔，并有保留真实不确定性、范围和条件的规则。Humanizer-zh 和 shuorenhua 公开了小规模的保留测试集 | 默认只返回一个修改版 |
| [amanmaqsood/prose-humanizer](https://github.com/amanmaqsood/prose-humanizer)、[manavmishra/ZeroSlop](https://github.com/manavmishra/ZeroSlop) | 建立材料台账，改写后核查情态、范围和归属 | 在对照材料核查上最接近；默认只返回一个修改版 |
| [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) | 限定保护、论断强度阶梯、修改授权、限定漂移审计 | 整体最接近；没有在限定覆盖上有差异的多个版本，也没有逐版区分修正与取舍 |
| [ABScribe](https://arxiv.org/abs/2310.00117) 与 [Luminate](https://arxiv.org/abs/2310.12953)（CHI 2024） | 生成多个版本，或沿若干维度生成版本，供用户探索 | 公开描述中未见对照材料核查 |
| [Beyond Fluency](https://aclanthology.org/2026.wasp-1.15/)（WASP 2026） | 论断保留框架：衡量改写中认识论力度、证据关系、限定和归属的变化 | 是评估框架，不是写作工具 |

在我们调研的工具中，没有一个同时做到：从材料中列出限定、写出在限定覆盖上有差异的多个版本、逐版对照材料核查、并把选择交给作者。调研采用了 GitHub、ACM DL、arXiv 和 Semantic Scholar 上的定向检索；这不能证明此类工具不存在。

## 仓库内容

- [skills/proportionate-writing/SKILL.md](skills/proportionate-writing/SKILL.md)：skill 本体
- [CONFIGURATIONS.md](CONFIGURATIONS.md)：用哪种配置，附测试结果
- [EVIDENCE.md](EVIDENCE.md)：B1 和 A2（早期实验）
- [validation/](validation/)：run 1；v2 案例（决策记录）与 v0.3 回归；v3 案例（休谟）；v4 加不加 skill 对比
- [examples/](examples/)：B1 的 prompt、输出和限定示例

## 许可

- skill 本体（`skills/` 目录）：[MIT](LICENSE)。
- 其余内容（本 README、评测记录、数据）：[CC BY 4.0](LICENSE-docs)。使用其中的评测方法或数据时，请注明出自本仓库。
- 休谟原文节选属于公有领域（Standard Ebooks 转录，CC0）。
