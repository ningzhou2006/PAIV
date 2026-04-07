# PAIV Implementation Guide
**开发者实现指南：如何让你的系统支持 PAIV 协议**

---
**版本**: V1.0  
**状态**: Public RFC  

## 1. 快速入门
本指南旨在帮助开发者以最小成本、循序渐进地在 AI 系统中接入 PAIV 协议。

## 2. 最小可行性实现 (MVP)
要声明“兼容 PAIV”，你的系统**必须**支持以下核心组件：
- **L00 Identity 层**: 支持导入/导出用户的基本身份和称呼。
- **L02 Persona 层**: 支持用户的行为偏好设置。
- **manifest.json**: 所有的导出包必须包含这个索引清单文件。

## 3. 数据处理流程

### A. 导出流程 (Export)
当用户选择“导出我的 PAIV 身份”时，系统应执行：
1. 按照 `schemas/identity.schema.json` 格式化用户基础信息。
2. 将用户的行为指令（System Prompt 偏好）转为 PAIV 格式。
3. 生成 `manifest.json`，记录当前版本和包含的层级。
4. 打包成目录或压缩包供用户下载。

### B. 导入流程 (Import)
当用户携带 PAIV 包进入新系统时：
1. **校验**: 首先读取并校验 `manifest.json`。
2. **加载**: 根据清单加载支持的层级（如 L00, L02）。
3. **转换**: 将 PAIV 的标准字段映射到你系统的本地配置中。
4. **反馈**: 告知用户哪些层级已成功迁移。

## 4. 分级兼容标准
- **PAIV Core Compatible**: 支持 Identity + Persona + Manifest（适用于大多数聊天机器人）。
- **PAIV Secure Compatible**: 在核心基础上增加对 Secrets 层的加密支持。
- **PAIV Full Stack**: 支持全六层模型（适用于复杂的自主智能体）。

## 5. 最佳实践
- **保持简洁**: 身份层不要堆砌过多非标准字段。
- **严禁明文**: 永远不要在 L00-L03 层存储用户的明文密码或 API Key。
- **尊重用户**: 导入数据前应让用户确认覆盖范围。

---
*更多技术细节请参考 [Technical Specification](../protocol/SPECIFICATION.md)*
