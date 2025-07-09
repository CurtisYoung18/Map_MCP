# MCP 高德地图智能助手

## 项目简介

本项目是一个基于 OpenAI GPT-4（或 GPT-3.5）与高德地图 API 的智能命令行助手。你可以通过自然语言与 AI 交互，自动调用高德地图相关工具（如周边搜索、路线规划、天气查询等），为出行、生活等场景提供智能化服务。

## 主要功能
- 支持自然语言对话，自动调用高德地图工具
- 支持酒店、餐馆、路线、天气等多种查询
- 支持自定义扩展高德地图 API 工具

## 环境依赖
- Python 3.8 及以上（推荐 3.10+）
- pip
- OpenAI API Key
- 高德地图开放平台 API Key

## 安装依赖
建议使用虚拟环境：

```bash
python3 -m venv venv
source venv/bin/activate
pip install mcp openai python-dotenv
```

## 配置 API Key

1. **高德地图 API Key**
   - 打开 `servers_config.json`，将 `url` 中的 `key` 替换为你自己的高德地图 API Key。
   - 示例：
     ```json
     {
       "mcpServers": {
         "amap-amap-sse": {
           "url": "https://mcp.amap.com/sse?key=你的高德key"
         }
       }
     }
     ```

2. **OpenAI API Key**
   - 打开 `client.py`，将 `api_key` 字段替换为你的 OpenAI API Key。
   - 如果你用的是 GPT-4，`self.model` 设置为 `gpt-4`；如用 GPT-3.5，设置为 `gpt-3.5-turbo`。
   - `base_url` 保持为 `https://api.openai.com/v1`。

## 运行方法

```bash
source venv/bin/activate
python client.py
```

## 使用示例

程序启动后，直接输入你的需求，例如：

```
>>> 我要去济南奥体中心出差，请你查询附近5km的酒店，为我安排行程
>>> 查询宜昌清江润城4期周边的餐馆
>>> 查询北京明天的天气
```

AI 会自动理解你的需求，调用合适的高德地图工具，并返回结果。

## 常见问题

1. **ModuleNotFoundError: No module named 'mcp'**
   - 请确保已在虚拟环境中安装依赖：`pip install mcp openai python-dotenv`

2. **zsh: command not found: python**
   - 请用 `python3` 运行脚本。

3. **API Key 无效或权限不足**
   - 检查 OpenAI 和高德地图的 Key 是否正确、有效。

4. **如何切换模型？**
   - 在 `client.py` 里修改 `self.model`，可选 `gpt-3.5-turbo` 或 `gpt-4`。

## 联系方式
如有问题或建议，请联系项目维护者。 # Map_MCP
