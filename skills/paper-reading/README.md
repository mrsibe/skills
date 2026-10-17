# paper-reading

基于三遍阅读法的研究论文阅读 Agent Skill。面向 AI、深度学习、机器学习、计算机系统与算法论文。

## 能做什么

- **快速筛选**：判断论文是否值得精读。
- **系统讲解**：是什么、为什么出现、原理是什么、何时适用。
- **精读/审稿**：推导公式，核查证据、baseline、消融和适用边界。
- **研究与复现**：提出可证伪研究假设、设计最小实验和复现方案。
- **文献比较**：构造问题导向的研究对比矩阵。

## 安装

将整个 `paper-reading/` 文件夹放进 Agent 识别的 Skills 目录，不要只复制 `SKILL.md`（它引用了 `references/`）。

| 工具 | 个人 Skills 目录 | 项目 Skills 目录 |
| --- | --- | --- |
| Pi | `~/.pi/agent/skills/` 或 `~/.agents/skills/` | `.pi/skills/` 或 `.agents/skills/` |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| 其他兼容 Agent Skills 的客户端 | 参照客户端文档 | 参照客户端文档 |

把 **整个目录** 解压/复制到相应父目录下，例如：`~/.pi/agent/skills/paper-reading/SKILL.md`。

Pi 支持明确调用：

```text
/skill:paper-reading 帮我精读 https://arxiv.org/abs/1803.10122，重点讲解世界模型的训练与决策过程
```

也可以通过自然语言触发：

```text
帮我快速筛选这篇论文，告诉我值不值得读。
用 paper-reading 系统讲解这篇论文的核心机制和实验证据。
请按审稿人视角分析这篇论文的 baseline 是否公平。
比较这三篇世界模型论文，找可能值得验证的研究问题。
我只有一张 8GB GPU，给我设计一个最小复现实验。
```

## 目录

```text
paper-reading/
├── SKILL.md
├── README.md
└── references/
    ├── reading-notes.md
    ├── critical-review.md
    └── reproduction-protocol.md
```

## 设计约束

- 这是工作流 Skill，不会自动安装 PDF 阅读器、浏览器或代码执行环境。
- 需要全文分析时，Agent 必须有能力读取 PDF/网页或收到用户上传的文本。
- 原文无法取得时，必须明确限定分析范围。
- 论文主张、直接证据、推断和待验证猜想需要分开记录。

## 方法与规范参考

- Agent Skills Specification: https://agentskills.io/specification
- Anthropic Skill Authoring Best Practices: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices
- S. Keshav, *How to Read a Paper*: https://web.stanford.edu/class/cs245/readings/how-to-read-a-paper.pdf
- Pi Skills: https://pi.dev/docs/latest/skills
