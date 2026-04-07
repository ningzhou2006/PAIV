# PAIV Security Mechanism
> **Protecting the Sovereignty of Digital Identity**

---

## [English Version]

### 1. Layered Defense (L00-L05)
Security is applied according to the sensitivity of each PAIV layer:
* **L00-L02 (Public/Personal)**: Protected via standard TLS during transit.
* **L04 (Secrets)**: MUST be encrypted at rest using AES-256 or equivalent. API keys and credentials must never be stored in plain text.
* **L05 (Action)**: Requires explicit "Human-in-the-loop" confirmation for high-risk automated actions.

### 2. Identity Verification
Any system requesting access to a PAIV vector must:
* **Authenticate**: Prove system identity via signed certificates.
* **Authorize**: Request specific scope-limited access (e.g., "Read-only access to L02 Persona").

### 3. Secure Migration Protocol
When transferring a PAIV identity between platforms:
1. **End-to-End Encryption**: Data must be encrypted by the user's key before leaving the source.
2. **Integrity Check**: Use SHA-256 hashing to ensure the identity vector hasn't been tampered with during transit.

---

## [中文版]

### 1. 分层防御机制
根据 PAIV 各个层级的敏感程度实施不同的安全策略：
* **L00-L02 (基础/个性)**：传输过程中通过标准 TLS 加密保护。
* **L04 (凭据)**：**必须**使用 AES-256 或同等强度的算法进行静态加密。API 密钥和凭据绝不允许以明文形式存储。
* **L05 (执行)**：对于高风险的自动化操作，必须引入“人工确认”机制。

### 2. 身份验证与授权
任何请求访问 PAIV 向量的系统必须：
* **验证 (Authenticate)**：通过签名证书证明系统身份。
* **授权 (Authorize)**：申请特定范围的访问权限（例如：“仅 L02 个性层级的只读权限”）。

### 3. 安全迁移协议
在不同平台间迁移 PAIV 身份时：
1. **端到端加密**：数据在离开源端前必须由用户密钥加密。
2. **完整性校验**：使用 SHA-256 哈希值确保身份向量在传输过程中未被篡改。

---

> **"Security is not a feature, but the prerequisite for digital sovereignty."**
> **“安全不是一个功能，而是数字主权的前提。”**
