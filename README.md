# 这是基于一个开源项目改的一个Agent
## 配置说明

需要配置使用的 LLM API，请按以下步骤设置：

1. 在 `config` 目录创建 `config.toml` 文件（可从示例复制）：

```bash
cp config/config.example.toml config/config.toml
```

2. 编辑 `config/config.toml` 添加 API 密钥和自定义设置：

```toml
# 全局 LLM 配置
[llm]
model = "gpt-4o"
base_url = "https://api.openai.com/v1"
api_key = "sk-..."  # 替换为真实 API 密钥
max_tokens = 4096
temperature = 0.0

# 可选特定 LLM 模型配置
[llm.vision]
model = "gpt-4o"
base_url = "https://api.openai.com/v1"
api_key = "sk-..."  # 替换为真实 API 密钥
```

## 快速启动

一行命令运行：

```bash
python main.py
```

然后通过终端输入你的创意！

如需使用 MCP 工具版本，可运行：
```bash
python run_mcp.py
```

如需体验不稳定的多智能体版本，可运行：

```bash
python run_flow.py
```

## 添加自定义多智能体

目前除了通用的  Agent, 还内置了DataAnalysis Agent，适用于数据分析和数据可视化任务，可以在`config.toml`中将这个智能体加入到`run_flow`中
```toml
# run-flow可选配置
[runflow]
use_data_analysis_agent = true     # 默认关闭，将其改为true则为激活
```
除此之外，你还需要安装相关的依赖来确保智能体正常运行：[具体安装指南](app/tool/chart_visualization/README.md##安装)
