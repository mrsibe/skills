# independent-research

根据[《如何不被自媒体干扰，真正地独立思考》](https://mrsibe.top/posts/independent-thinking/)的方法设计的通用 Agent Skill。

核心流程：

```
明确研究问题与实际场景
        ↓
优先查原始资料：What / Why / How / Trade-off
        ↓
写出独立初判、关键假设和可能的反例
        ↓
阅读 Reddit / GitHub / 专业讨论，主动证伪
        ↓
有条件地实验或设计验证
        ↓
修正结论：依据、适用边界、不确定性
```

## 目录

```text
independent-research/
├── SKILL.md                      # Skill 入口与执行流程
├── README.md                     # 说明和安装
└── references/
    ├── source-checks.md          # 原始资料、Benchmark、Reddit 和反证校验
    └── report-template.md        # 三档调研输出模板
```

## 安装

使用 [Skills CLI](https://github.com/vercel-labs/skills)，需要 Node.js/npm：

```bash
npx skills add mrsibe/skills --skill independent-research
```

默认安装到当前项目，交互选择 Agent；加 `--global` 可全局安装。CLI 会安装完整技能包，包括 `references/`，无需手动复制。更新方式见[仓库安装指南](../../README.md#安装与更新)，将命令中的技能名替换为 `independent-research`。

## 使用

可以尝试的请求：

- “调研 vLLM 的 PagedAttention，为什么出现，原理是什么，和传统 KV Cache 管理的 trade-off 有什么不同？先看论文/源码，再看 Reddit 和 Issues。”
- “对比 Go 和 Rust 实现后台服务，从性能、可靠性、团队成本来选型，最后给个 PoC。”
- “某新 AI 模型号称超越所有模型。请核查原论文、榜单指标和测试条件，再看社区是否有反例。”

Skill 的主要约束是**先形成独立判断，再让外部观点挑战判断**，而不是依靠格式化的四问生成表面上完整的报告。
