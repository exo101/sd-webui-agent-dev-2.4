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



## 许可证

MIT
