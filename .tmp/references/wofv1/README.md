# AGENTS.md

> 让 Agent 写下的每一行代码，都服务于项目的下一年。

一套面向真实项目的 Agent 工程准则。它把长期主义、架构一致性、单一真相源、TDD、真实环境验证和可回滚交付带进每一次开发，让 Agent 不只完成眼前的任务，更能主动控制复杂度、消除架构分叉并守住长期质量。

## 它带来的价值

- **项目越改越干净**：优先解决根因，持续删除无效代码和历史包袱，避免用补丁换取短期完成。
- **架构始终只有一条主线**：统一结构、类型和写入口，用复用与派生维护单一真相源。
- **交付经得起真实使用**：先测试再实现，在真实环境中验证，并保持每次变更可编译、可运行、可回滚。
- **Agent 真正理解项目**：先阅读现有代码和文档，再设计、确认和开发，把已有能力变成新功能的地基。
- **一套标准覆盖所有仓库**：同一个版本化规则文件可以快速引入任何项目，团队与 Agent 始终遵循一致的工程判断。

完整规则见 [`AGENTS.md`](AGENTS.md)。

## 编写理念

这份规则由人类高级工程专家持续编辑和审定。每一条内容都来自对真实工程问题的抽象，追求用最少、最精炼的语言表达最具迁移价值的思想，让有限的上下文承载尽可能高的决策密度。

整体设计遵循“道、术、器”三个层次：

- **道**：决定什么是长期正确的事，建立稳定的工程价值观。
- **术**：定义可复用的判断方法和工作方式，把价值观落实到开发过程。
- **器**：承载具体工具、框架和实现，它们应由项目按需选择并随时代演进。

`AGENTS.md` 的重心放在“道”和“术”。它不试图收录所有工具用法，而是用最低的规则成本撬动最大的工程收益，让同一套原则能够跨项目、跨技术栈长期生效。

## 使用注意事项

这套规则的收益取决于模型对抽象工程原则的理解能力和指令遵循能力。

| 模型类型 | 使用建议 | 预期收益 |
| --- | --- | --- |
| Fable5 等大规模模型 | 按需使用 | 模型本身已经具备较强的工程理解，额外规则的边际提升相对有限。 |
| 5.6 Sol 等中等规模且指令遵循良好的模型 | 推荐使用 | 能够理解并稳定执行抽象原则，通常可以获得明显提升。 |
| 小模型 | 可选 | 更适合清晰、具体、步骤化的任务指令，难以充分吸收这类高抽象规则。 |

它最适合作为具备一定推理能力和良好指令遵循能力的 Agent 的工程放大器。小模型如果需要稳定产出，应优先补充面向具体任务的明确步骤和验收标准。

## 安装与更新

在项目根目录执行：

```shell
gh release download --repo w0fv1/AGENTS.md --pattern AGENTS.md --clobber
```

这条命令同时用于首次安装和后续更新，会将项目根目录的 `AGENTS.md` 替换为最新正式版本。

不使用 GitHub CLI 时，可以直接下载覆盖。

### Windows PowerShell

```powershell
Invoke-WebRequest "https://github.com/w0fv1/AGENTS.md/releases/latest/download/AGENTS.md" -OutFile "AGENTS.md"
```

### Windows CMD

```batch
curl.exe -fL "https://github.com/w0fv1/AGENTS.md/releases/latest/download/AGENTS.md" -o "AGENTS.md"
```

### macOS/Linux

```shell
curl -fL "https://github.com/w0fv1/AGENTS.md/releases/latest/download/AGENTS.md" -o AGENTS.md
```

也可以直接[下载最新版本](https://github.com/w0fv1/AGENTS.md/releases/latest/download/AGENTS.md)。

## 发布

版本由[发布工作流](.github/workflows/release.yml)自动生成，每个正式版本都可以独立下载和追溯。
