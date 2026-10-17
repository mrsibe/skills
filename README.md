# Personal Agent Skills Library

个人 Agent 能力库：将可复用的开发经验、研究方法与工程流程整理为可版本管理、可验证的 [Agent Skills](https://agentskills.io/specification)。

目标是在 Claude Code、Codex、Cursor 和 Pi 等支持 Agent Skills 的工具间复用方法，而不是维护新的 Agent 框架或技能管理器。具体兼容性需在相应客户端实际验证。

> 当前包含一个待实测的 Skill，尚未发布版本。

## 目录结构

```text
.
├── skills/           # 每个 Skill 独占一个直接子目录
├── tests/            # 触发、效果与回归测试资料
├── AGENTS.md         # Agent 在本仓库工作时遵守的约定
├── CONTRIBUTING.md   # Skill 编写、验证与提交规范
├── LICENSE           # MIT 许可证
└── README.md
```

后续每个 Skill 使用 `skills/<skill-name>/SKILL.md` 作为入口。仅按实际需要增加 `scripts/`、`references/` 和 `assets/`，不提前创建空的技能包。

## 当前状态

- Skill 数量：**1**。
- [paper-reading](skills/paper-reading/README.md)：论文筛选、讲解、批判性分析、比较与复现规划。
- 已有[手动回归用例](tests/paper-reading/README.md)，尚未完成模型实测、效果评估或跨客户端验证。
- 尚未配置自动测试或 CI。
- 公开源码仓库：[mrsibe/skills](https://github.com/mrsibe/skills)。尚未发布版本。

## 安装与更新

使用 [Vercel Skills CLI](https://github.com/vercel-labs/skills)，需要本机有可运行 `npx` 的 Node.js/npm 环境，无需手动克隆仓库或复制技能目录。

```bash
# 查看仓库可安装的 Skills，不安装
npx skills add mrsibe/skills --list

# 安装到当前项目，交互选择目标 Agent
npx skills add mrsibe/skills --skill paper-reading

# 全局安装到指定 Agent（示例：Pi、Claude Code、Codex、Cursor）
npx skills add mrsibe/skills --skill paper-reading --global \
  --agent pi --agent claude-code --agent codex --agent cursor
```

不加 `--global` 时安装到当前项目；项目级安装应在目标项目目录执行。按实际使用的客户端保留 `--agent` 参数，或省略它以交互选择。CLI 负责安装路径及符号链接/复制方式，不需要自行维护各 Agent 的路径表。

```bash
# 查看已安装的全局 Skills
npx skills list --global

# 更新全局安装的 paper-reading
npx skills update paper-reading --global
```

项目级查看使用 `npx skills list`，更新使用 `npx skills update paper-reading --project`。更新由 CLI 手动执行，不会在仓库推送后自动同步。安装前请审查内容；CLI 支持安装不代表已验证每个客户端中的任务效果。

## 添加 Skill

参见 [CONTRIBUTING.md](CONTRIBUTING.md)。一个 Skill 应解决明确、可复用的问题，并包含触发条件、执行流程、输出要求和失败处理。仓库专属路径、业务配置与凭证不应写入通用技能。

使用 Skills CLI 分发，不在本仓库开发自定义安装器。新增 Skill 时同步维护目录和安装说明；CLI 用法和客户端支持以其官方文档为准。

## 安全与许可证

- 不提交密钥、令牌、个人数据或内部业务材料。
- 执行 Skill 脚本前先审查其行为；删除、部署、发布等操作必须取得明确授权。
- 本仓库采用 [MIT 许可证](LICENSE)。

## 参考

- [Agent Skills 规范](https://agentskills.io/specification)
- [Anthropic Skills 示例](https://github.com/anthropics/skills)
- [Skills CLI](https://github.com/vercel-labs/skills)
