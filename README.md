# sd-webui-agent-dev-2.4

SD WebUI 全能生图智能体扩展 — 通过自然语言对话驱动 Stable Diffusion WebUI 进行图像、视频生成与模型管理。

## 功能特性

- **对话式生图**：用自然语言描述需求，智能体自动调用工具生成图像
- **多供应商支持**：
  - 本地 LLM（llama.cpp / LM Studio）
  - ModelScope 云端推理
  - YoboxAI 图像 / 视频 API
- **工具集**：
  - 图像生成（文生图、图生图、高清修复）
  - 视频生成（H3 / Seedance 等）
  - 模型下载与管理
  - 工作区文件操作
  - Photoshop MCP 集成
- **@提及系统**：在对话中 `@模型名` 直接切换模型，`@工具名` 触发指定工具
- **可扩展工具注册表**：按领域拆分的工具架构，便于二次开发

## 安装

将本目录放入 Stable Diffusion WebUI 的 `extensions/` 下，重启 WebUI 即可。

## 配置

编辑 `agent_config.json` 设置 API 提供商与密钥：

```json
{
  "api_provider": "local-llama",
  "base_url": "http://127.0.0.1:1234/v1",
  "model": "qwen3.8-27b",
  "image_api_provider": "YoboxAI",
  "image_api_key": "sk-xxx",
  "video_api_provider": "YoboxAI",
  "video_api_key": "sk-xxx"
}
```

## 模块结构

| 文件 | 说明 |
|------|------|
| `agent.py` | 入口，注册 WebUI Tab |
| `agent_chat.py` | 对话核心（流式输出 / 工具执行） |
| `agent_ui.py` | Gradio 界面 / @mention 系统 |
| `agent_config.py` | 配置读写 |
| `agent_tools*.py` | 工具实现（按领域拆分） |
| `agent_prompts.py` | 系统提示词 |
| `agent_routing.py` | 路由分发 |
| `photoshop_mcp.py` | Photoshop MCP 集成 |

## 许可证

MIT
