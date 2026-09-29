# 战略机会洞察（Strategy Insight）

把原版“五看”调研做成可以按需使用的技能包：可以只研究趋势、客户、对手或团队自身，也可以连续完成机会发现、比较和完整洞察。[交互式方法指南](guide.html) 保留；安装与使用以本页为准。

这个技能沿用原版的方法边界：**先看市场，再看机会；市场吸引力与组织适配度分别评分；只对明星区做落地验证；最终停在“五看”，不代替团队完成“三定”。**

## 先从哪里开始

第一次使用任何入口，先完成原版 **3轮15问**：团队构成、产品与技术、资源与渠道。已有完整调研档案时可以核对后复用，不必重复回答。完成问答后，按你想解决的问题选择：

| 你想知道什么 | 使用入口 | 会得到什么 |
| --- | --- | --- |
| “这个行业正在发生什么？” | 看趋势 `strategy-trends` | 行业趋势简报 |
| “谁有需求，愿不愿意付钱？” | 看客户 `strategy-customers` | 客户市场简报 |
| “现在有哪些玩家和替代方案？” | 看对手 `strategy-competitors` | 竞争格局简报 |
| “我们的团队能做什么？” | 看自己 `strategy-capabilities` | 内部能力盘点 |
| “先把四个方面摸清楚” | 四看调研 `/four-views` | 调研方案与四份简报 |
| “帮我找有哪些业务方向” | 寻找机会 `/find-opportunities` | 机会扫描、初筛与8维深描 |
| “比较我手上的几个方向” | 比较机会 `/compare-opportunities` | 双维评分、四象限与明星区验证 |
| “从头到尾做一次调研” | 完整洞察 `/strategy-insight` | 原版全流程的11份成果 |

后半段会检查它需要的前置资料：已有四看或机会深描就核对后复用，缺少的才补做。比较用户指定的机会时，结果只代表这些候选，不声称已经扫描全市场。

## Skills (4)

- `strategy-trends` — 看趋势：行业、技术、政策、市场规模与价值迁移。
- `strategy-customers` — 看客户：客户分层、痛点、预算、渠道与决策链。
- `strategy-competitors` — 看对手：玩家、替代方案、定价、技术路线与竞争空白。
- `strategy-capabilities` — 看自己：团队能力、资源、渠道与技术资产。

四个技能各有标准 `SKILL.md` 和完整的Phase 0问答说明，可分别安装与使用。

## Commands (4)

- `/four-views` — 四看调研：先了解团队，再看清行业、客户、对手和自身条件。
- `/find-opportunities` — 寻找机会：在四看基础上扫描、初筛并深描业务方向。
- `/compare-opportunities` — 比较机会：对指定候选做8维深描、双维评分和落地验证。
- `/strategy-insight` — 完整洞察：从15问到最终报告，交付11份成果。

这些命令适用于支持自定义命令的平台。**在 ChatGPT/Codex 中，使用组合技能 `$strategy-insight`，直接说“四看调研”“寻找机会”“比较机会”或“完整洞察”即可**；`strategy-insight` 是四个工作流的原生入口，不是第五种独立研究方法。例如：

> 使用 `$strategy-insight` 完整调研中国宠物医疗行业的战略机会。

> 使用 `$strategy-insight` 比较我提供的三个业务方向；先检查已有四看资料，不足的部分再补齐。

## 安装与跨平台使用

核心是通用的 `SKILL.md` 目录结构，不依赖Coze、付费数据API或特定模型的并行任务功能。把需要的技能目录复制到平台的 skills 目录，并保持目录内部的 `references/` 与 `assets/`：

```text
skills/
├── strategy-trends/
├── strategy-customers/
├── strategy-competitors/
├── strategy-capabilities/
└── strategy-insight/          # ChatGPT/Codex 的四个组合工作流入口
    ├── SKILL.md
    ├── agents/openai.yaml     # OpenAI 客户端界面信息；其他平台可忽略
    ├── references/
    └── assets/matrix.html     # 离线可打开的双维矩阵模板
commands/                      # 支持自定义斜杠命令的平台使用
.claude-plugin/plugin.json     # Claude 插件元数据
```

- **ChatGPT/Codex Skills**：安装 `skills/` 下需要的目录；通过技能名或自然语言调用。组合工作流用 `strategy-insight`。
- **Claude Code/Cowork**：可使用 `commands/` 中的四个命令，命令调用同一套技能；也可以直接调用四个“看”。
- **Gemini CLI、OpenCode、Cursor、Kiro 等支持 Agent Skills 的工具**：复制对应的 `skills/` 目录，按其平台方式调用；不支持 `commands/` 时直接调用 `strategy-insight` 并说明模式。
- **不自动识别 Skills 的聊天界面**：将需要的 `SKILL.md` 和其引用资料加入项目知识或指令，按同样的模式提问。此方式不提供自动技能发现。

调研需要联网搜索和网页阅读。没有这些能力时，可以整理用户提供的材料，但不能把未经验证的市场事实写成已完成的行业研究。HTML矩阵模板不依赖外部图表CDN，离线也可打开。

## 来源与许可

这版沿用本仓库原有的“五看”、30–50个候选到15–25个深描、双维独立评分、明星区四项落地验证及11份交付物。原版单文件说明已由模块化技能替代。[方法指南](guide.html) 继续保留。项目许可证见 [LICENSE](LICENSE)。
