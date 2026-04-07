# PAIV Protocol Specification
> **Personal AI Identity & Values Protocol**

---

**Version**: V1.0  
**Status**: Public RFC  

---

## [English Version]

### 1. Purpose
This document defines technical standards for portable personal AI identities. The PAIV protocol allows identity, preferences, behavioral configurations, and context to flow between different AI systems, eliminating "vendor lock-in."

### 2. PAIV Six-Layer Identity Model (L00-L05)
PAIV structures personal identity into six layers to achieve fine-grained access control:

| Layer | Name | Core Purpose |
| :--- | :--- | :--- |
| **L00** | **Identity** | Basic identity, legal names, core values |
| **L01** | **Knowledge** | Personal knowledge assets, professional background |
| **L02** | **Persona** | Behavioral preferences, tone, style |
| **L03** | **Context** | Interaction history, short/long-term memory |
| **L04** | **Secrets** | Sensitive credentials, encrypted API keys |
| **L05** | **Action** | Automation permissions, tool mapping |

### 3. Core Rules
* **Mandatory Support**: Any implementation MUST support the L00 (Identity) layer.
* **Data Format**: Structured formats (JSON or YAML) MUST be used.
* **Security**: L04 (Secrets) layer MUST NOT be transmitted in plain text.
* **Portability**: A Manifest file MUST be provided for full migration.

### 4. Migration Protocol
1. **Export**: Generate a package containing layer data and `manifest.json`.
2. **Import**: Verify manifest, load supported layers, and generate an import report.

---

## [中文版]

### 1. 目的
本文件定义了可迁移个人 AI 身份的技术标准。PAIV 协议允许身份、偏好、行为配置和上下文在不同的 AI 系统之间流动，消除“平台锁定”。

### 2. PAIV 六层身份模型
PAIV 将个人身份结构化为六个层级，以实现细粒度的访问控制：

| 层级 | 名称 | 核心用途 |
| :--- | :--- | :--- |
| **L00** | **Identity** | 基础身份、法律姓名、核心价值观声明 |
| **L01** | **Knowledge** | 个人知识资产、专业背景、事实性数据 |
| **L02** | **Persona** | 行为偏好、语气风格、交互权重配置 |
| **L03** | **Context** | 交互历史、短期记忆、长期上下文连续性 |
| **L04** | **Secrets** | 敏感凭据、API 密钥（必须加密引用） |
| **L05** | **Action** | 自动化权限、工具映射、执行逻辑配置 |

### 3. 核心规则
* **强制支持**：任何实现都必须支持 L00 (Identity) 层。
* **数据格式**：必须使用结构化格式（如 JSON 或 YAML）。
* **安全性**：L04 (Secrets) 层绝对禁止明文传输。
* **可迁移性**：必须提供 Manifest（清单文件）以支持完整迁移。

### 4. 迁移协议
1. **导出**：生成包含各层数据及 `manifest.json` 的压缩包。
2. **导入**：验证清单文件，逐层加载支持的数据，并生成导入报告。

---

> **“PAIV Protocol: Ensuring the digital soul remains under human sovereignty.”**
> **“PAIV 协议：确保数字灵魂始终处于人类主权之下。”**
