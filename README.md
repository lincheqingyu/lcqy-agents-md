# Agent 指令规则库

本仓库用于收集、整理和复用 `AGENTS.md` 规则。目标是让具体项目中的 `AGENTS.md` 保持简洁，只保留项目事实、项目约束和少量稳定的工程原则；可迁移的规则按需选择，不整份搬运。

## 目录结构

```text
.
├── AGENTS.md                         # 本仓库的维护规则
├── README.md                         # 使用入口和目录索引
├── .agents/
│   ├── README.md                     # 可复制文档的选择指南
│   ├── development-guidelines.md     # 合并后的通用开发规范
│   ├── tech-stack-guidelines.md      # 合并后的技术栈规范
│   ├── skills/                       # Codex/Pi Skill 入口，当前为空
│   └── templates/                    # 新项目的最小起始模板
└── .tmp/
    └── references/                   # 原始模仿资料，不作为项目规则入口
```

## 如何为新项目准备 `AGENTS.md`

1. 在目标项目根目录写入项目专属信息：项目目标、目录边界、真实命令、构建和测试入口、不可违反的业务约束。
2. 从 [`.agents/development-guidelines.md`](.agents/development-guidelines.md) 选择需要的通用规范。
3. 从 [`.agents/tech-stack-guidelines.md`](.agents/tech-stack-guidelines.md) 复制实际使用技术栈对应的章节。
4. 删除不适用的条目，并根据目标项目事实重新验证命令、版本和路径。

`.agents/` 下的普通 Markdown 是可复制的文档，不会自动应用到其他项目。只有放入 `.agents/skills/<name>/SKILL.md` 的内容才会作为 Codex/Pi 项目 Skill 被发现。Claude Code 项目 Skill 应放在 `.claude/skills/<name>/SKILL.md`。

原始参考资料位于 [`.tmp/references/`](.tmp/references/)，只用于研究和提炼，不应整份复制到目标项目。
