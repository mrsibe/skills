# refactoring-ui

把「界面不好看」拆成可执行判断的视觉改造 Skill。面向会写代码、没学过设计的场景：不依赖审美直觉，用层级、间距、排版、颜色、层次五组规则定位问题，用有限的预设体系替代逐像素手调。

## 能做什么

- **诊断**：按「层级 → 间距 → 排版 → 颜色 → 层次 → 打磨」的顺序定位问题，而不是随机调样式。
- **改造现有界面**：给出「问题 → 原因 → 改法 → 涉及文件」的改动清单。
- **建立设计 token**：间距/尺寸阶梯、字号阶梯、9 阶色板、5 档阴影，附可落地的起始数值。
- **审查与验收**：可测量的检查清单，以及「症状 → 病因」对照表。
- **避免常见错误**：彩色背景上的灰字、栅格导致的宽度倒挂、等比缩放、全站一个阴影档、空状态缺失。

## 安装

使用 [Vercel Skills CLI](https://github.com/vercel-labs/skills)，需要 Node.js/npm 环境：

```bash
# 在目标项目目录执行，交互选择 Agent
npx skills add mrsibe/skills --skill refactoring-ui

# 或全局安装到 Pi；其他客户端可使用 claude-code、codex、cursor
npx skills add mrsibe/skills --skill refactoring-ui --global --agent pi
```

CLI 会安装完整技能包，包括 `references/`。多 Agent 安装、已安装列表和更新命令见[仓库安装指南](../../README.md#安装与更新)。

## 使用

```text
/skill:refactoring-ui 这个设置页看起来很像模板，帮我改一下，项目用的是 Tailwind
```

也可以通过自然语言触发：

```text
这个仪表盘信息层级很乱，帮我重新排一下优先级。
审查一下 components/Checkout 下的页面，列出视觉问题并按严重程度排序。
帮我给这个新项目定一套间距、字号、颜色和阴影 token。
侧边栏在宽屏上占得太多了，而且中等屏幕反而比大屏更宽，怎么改？
空状态和列表项都没设计，看起来像没做完。
```

## 目录

```text
refactoring-ui/
├── SKILL.md
├── README.md
└── references/
    ├── principles.md   # 9 个主题的完整规则、原因与反例
    ├── tokens.md       # 四套体系（间距/字号/颜色/阴影）的建立步骤与示例值
    └── checklist.md    # 可测量的审查清单与症状对照表
```

## 设计约束

- 这是方法 Skill，不附带组件库、模板或截图；不引入依赖、不换框架。
- 项目已有设计系统时优先对齐既有 token，不推翻重建。
- 只改视觉，不改行为；品牌个性由用户决定，不被「更稳妥」的规则覆盖。
- 没有渲染环境时必须在结论中标明「未做视觉验证」。
- 提炼自 Adam Wathan 与 Steve Schoger 的 _Refactoring UI_，规则已重写为可执行方法，不含原文译文与插图；建议购买原书：<https://www.refactoringui.com/>。中文在线阅读：<https://shallowhawk.github.io/refactoring-ui-zh/>。

## 方法参考

- Agent Skills Specification: https://agentskills.io/specification
- Refactoring UI 官方站点: https://www.refactoringui.com/
- WCAG 对比度要求: https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html
