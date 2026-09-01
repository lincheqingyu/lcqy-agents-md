# Agent 规则库

本仓库用于整理、维护和复用 `AGENTS.md` 规则。根目录的 `AGENTS.md` 是一份可以直接复制到其他项目使用的通用规则；`.agents/` 保存可按需组合的通用规范、技术栈指南和模板。

## 仓库内容

```text
.
├── AGENTS.md                         # 可直接复制的通用项目规则
├── README.md                         # 用途和使用入口
├── .agents/
│   ├── README.md                     # 可复制文档索引
│   ├── development-guidelines.md     # 通用开发规范
│   ├── tech-stack/                   # 按语言拆分的技术栈规范
│   ├── templates/                    # 新项目 AGENTS.md 模板
│   └── skills/                       # 项目级 Skill 入口
└── .tmp/references/                  # 用于研究的原始参考资料
```

## 如何使用

1. 将根目录的 `AGENTS.md` 复制到目标项目根目录。
2. 填写其中的项目目标、目录边界、技术栈、真实命令和项目约束；删除不适用的项目详情项。
3. 从 [`.agents/development-guidelines.md`](.agents/development-guidelines.md) 和 [`.agents/tech-stack/`](.agents/tech-stack/README.md) 选择需要追加的专项规则。
4. 根据目标项目事实验证所有命令、版本、路径和技术栈约束。

`.agents/` 下的普通 Markdown 是被动文档，不会自动应用到其他项目。只有放入 `.agents/skills/<name>/SKILL.md` 的内容才是 Codex/Pi 项目 Skill 入口。

## 参考资料

[`.tmp/references/`](.tmp/references/) 保存原始参考内容和项目示例，只用于研究和提炼，不是正式规则的第二个版本。参考资料的来源与索引见 [`.tmp/references/README.md`](.tmp/references/README.md)。

## 维护原则

新增、移动或拆分文档时，同时更新相关索引和相对链接；规则应保持单一真相源、范围清晰且可验证。
