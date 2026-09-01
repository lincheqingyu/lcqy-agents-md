# Python 技术栈规范

- 使用项目声明的 `pyproject.toml` 和 `uv` 工作流，优先通过 `uv sync` 解析和同步环境。
- 除非项目明确要求，不引入 `pip` 虚拟环境、Poetry 或独立的 `requirements.txt` 作为第二套依赖入口。
- 使用明确的类型模型和类型提示，避免用松散的 `dict` 或字符串表示稳定的领域数据。
- 遵循项目现有的 formatter、lint、类型检查、测试和打包入口。
