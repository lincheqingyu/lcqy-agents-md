# 可复制 Agent 规则文档

本目录是被动的规则文档库。使用时将与目标项目匹配的内容复制到目标项目的 `AGENTS.md`，不要将整目录作为自动加载的上下文。

## 文档选择

- [`development-guidelines.md`](development-guidelines.md)：长期维护、SSOT、根因修复、变更流程、测试和文档规范。
- [`tech-stack-guidelines.md`](tech-stack-guidelines.md)：Java、Python、TypeScript/React、Rust/React 技术栈规范，按章节选择。
- [`templates/AGENTS.zh-CN.md`](templates/AGENTS.zh-CN.md)：中文项目的最小起始模板。

## `.agents/skills/`

该目录预留给 Codex/Pi 的项目级 Skill，当前不包含任何 Skill。普通规则文档不要放进去，只有带有效 YAML frontmatter 和 `SKILL.md` 入口的实际 Skill 才应进入该目录。

Claude Code 使用 `.claude/skills/<name>/SKILL.md`，因此同一份 Skill 内容如需支持 Claude Code，需要复制或发布到对应目录。

## 原始参考资料

原来的四个参考目录已经移动到 [`.tmp/references/`](../.tmp/references/)，来源、文件说明和归属信息见 [`../.tmp/references/README.md`](../.tmp/references/README.md)。参考资料不自动生效，也不是规则文档的第二个版本。
