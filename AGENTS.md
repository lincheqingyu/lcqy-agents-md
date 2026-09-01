# AGENTS.md

You must follow the rules below.

## 工程原则

**Do what is right in the long run, without speculating about the future.**

- Make decisions based on known requirements and constraints. Prefer solutions that remain simple, maintainable, and verifiable over time. Do not introduce avoidable technical debt for short-term convenience, and do not add complexity for hypothetical future requirements.

### KISS

**Choose the simplest solution that fully satisfies the known requirements and constraints.**

- Do not introduce abstractions, indirection, configuration, or other mechanisms without a concrete benefit.
- Encapsulate necessary complexity behind clear boundaries; do not expose internal complexity to callers unless the caller must control it.
- If the current structure requires repeated workarounds, duplicated control flow, or special cases, simplify the structure instead of adding more exceptions.

### YAGNI

**Do not implement functionality or extensibility without a current, confirmed requirement.**

- Do not add extension points, configuration options, abstraction layers, or compatibility paths solely for hypothetical future use.
- Keep changes scoped to the task. Do not add unrelated features, upgrade unrelated dependencies, or perform unrelated refactors.
- Refactor existing structure only when doing so is necessary to implement the current task correctly or to remove complexity directly encountered by the change.

### Rule of Three

**Allow limited duplication until a stable abstraction is supported by repeated, concrete use cases.**

- On the first occurrence, implement the concrete case directly.
- On the second occurrence, tolerate limited duplication and determine whether the shared behavior and constraints are actually stable.
- On the third occurrence, consider extracting a shared abstraction if the repeated cases have the same semantics and are expected to evolve together.
- Abstract only behavior with shared semantics, constraints, and reasons to change. Keep superficially similar code separate when the cases may evolve independently.

### 其他工程约束

- 先阅读相关代码、配置、文档和测试，再决定新增、修改或重构方式。
- 优先复用现有实现、成熟第三方库和项目约定，而不是重新实现已有能力。
- 保持单一真相源（SSOT）。类型、配置、写入口、生成文件和文档都应有明确的权威来源，其他表示应派生或复用。
- 避免产生第二套入口、重复模型、平行实现或架构分叉。
- 发现结构性问题时修复根因；不要用特例、临时补丁、过度兜底或 hack 掩盖问题。
- 重构或替换实现后删除失效的旧代码，避免新旧实现长期并存。
- 使用适当程度的强类型；同一领域概念应有唯一的权威类型定义。
- 设计深度封装的组件：内部吸收复杂度，对外只暴露必要、稳定且易用的 API 和生命周期。
- 除非明确要求，否则不要为了历史行为主动增加新的兼容层；已有公开 API、数据格式、持久化结构、事务边界和错误语义的破坏性变化则必须有明确依据。
- 不以减少编码工作量为目标牺牲设计质量；在合理范围内选择长期更简单、更易维护的实现。

## 项目详情

- 项目目标：填写项目目标和主要边界。
- 项目目标：填写项目解决的问题和主要用户。
- 项目边界：填写本项目负责和不负责的内容。
- 运行环境：填写操作系统、语言版本、运行时和包管理器。
- 技术栈：填写语言、框架、主要依赖和版本事实源。
- 外部依赖：填写数据库、服务、凭据和本地资源的使用边界。
- 关键约束：填写业务规则、合规要求、兼容性要求和不可变契约。

## 开发流程

### 开始前

- 阅读项目 README、根目录和相关子目录的 `AGENTS.md`，再阅读受影响模块的代码、配置和测试。
- 将需求转换为可观察的结果，明确输入、输出、失败行为、边界条件和受影响的调用方。
- 找到项目已有的开发、格式化、静态检查、类型检查、测试和构建入口；不凭空创建命令。
- 变更前确认当前工作区状态，保留用户已有的未提交变更。

### 开发中

- 先建立能验证目标行为的最小实现或回归测试，再完成代码变更。
- 在负责失败语义的边界处理异常，保留原始原因；不得静默返回成功值、空结果或未经说明的降级结果。
- 复杂逻辑使用清晰的类型、命名和边界表达；注释只说明代码无法直接表达的意图、约束或决策，不重复代码本身。
- 删除被替代的实现、无效入口和废弃引用，但不要删除与当前任务无关的既有内容。
- 不在日志、错误信息、测试输出或提交内容中暴露密钥、令牌和其他敏感数据。
- 保持修改中的项目处于可编译、可运行或可验证状态。

### 完成前

- 检查行为变化、错误路径、边界条件、资源生命周期、并发影响和契约兼容性。
- 检查新增依赖、配置、生成文件、迁移文件和文档是否确有必要，并同步更新唯一权威入口。
- 复查实际 diff，确认没有临时文件、调试代码、无关格式化或重复实现。

## 验证与测试

- 优先运行覆盖本次变更的最小相关检查；只有在变更跨越共享边界、CI 要求或准备发布时扩大范围。
- 行为变化和 Bug 修复应增加或更新回归测试。Bug 修复应先让测试复现失败，再实现修复。
- 关键路径优先使用真实的下一层依赖和真实资源验证；只有边界依赖不可控或成本不合理时才使用 mock。
- 使用项目声明的 formatter、lint、类型检查、测试和构建入口，不为了通过检查而削弱检查。
- 如果某项检查未运行、无法运行或结果不完整，交付时明确说明，不得声称验证通过。

## 目录架构

- 关键目录：填写目录职责、模块边界和依赖方向。
- 关键文件：填写应用入口、配置、数据契约、生成文件和迁移文件。
- 外部依赖：填写数据库、消息队列、第三方服务和本地资源。

## 文档与配置

- 文档说明目的、入口、约束和决策背景，不复制代码已经表达的实现细节。
- README 负责导航和快速开始；模块细节、契约和操作说明放在最靠近其负责内容的位置。
- 代码、目录、命令、配置或契约发生变化时，检查相关文档、索引和示例是否仍然准确。
- 配置和数据格式应有唯一写入口；派生文件应能通过项目既有流程重新生成。

## 常用命令

- 安装或初始化：填写真实命令。
- 开发或运行：填写真实命令。
- 格式化与静态检查：填写真实命令。
- 测试：填写真实命令和测试范围。
- 构建与发布：填写真实命令及其前置条件。

## Git 与交付

- 不回滚、覆盖或清理与当前任务无关的用户变更。
- 不执行 `reset --hard`、强制覆盖、历史改写、远程推送或其他破坏性 Git 操作，除非用户明确授权。
- 不新增依赖、修改外部系统或执行发布操作，除非它们属于需求范围且已获授权。
- 交付前说明变更范围、实际运行的检查、检查结果、已知限制和未完成事项。

## 补充说明