# GitHub Actions Remote Debugging Assistant  VM-VPS

<!-- 中文版 -->
## 🇨🇳 中文文档

### 功能描述
本脚本专为CI/CD环境（如GitHub Actions）设计，用于创建安全的临时远程调试会话。当自动化流程失败时，脚本会通过tmate生成支持SSH/Web访问的实时终端，并向指定Telegram频道推送连接信息。开发者可接入会话进行实时诊断，完成后通过信号文件继续工作流。

### 核心功能
✅ 一键式tmate会话部署  
✅ 自动生成SSH密钥对（RSA 2048）  
✅ Telegram机器人实时通知  
✅ 会话信息轮播提示（默认10次）  
✅ 手动控制流程恢复  
✅ 跨平台支持（Linux/macOS）

### 使用示例
```bash
# 设置环境变量
export TELEGRAM_BOT_TOKEN="bot_xxxxxx"
export TELEGRAM_CHAT_ID="chat_12345"

# 启动调试会话
./tmate_debugger.sh

# 继续执行后续流程（调试完成后）
touch /tmp/continue
```

---

<!-- 英文版 -->
## 🇺🇸 English Documentation

### Description
This script creates secure temporary debugging sessions in CI/CD environments (e.g., GitHub Actions). When workflows fail, it spawns real-time terminal access via tmate (SSH/Web) and sends connection details to Telegram. Developers can debug interactively, then resume workflows by triggering a continuation signal.

### Key Features
✅ One-click tmate session deployment  
✅ Auto-generated SSH key pairs (RSA 2048)  
✅ Real-time Telegram notifications  
✅ Rotating session info display (default: 10 cycles)  
✅ Manual workflow resumption control  
✅ Cross-platform support (Linux/macOS)

### Usage Example
```bash
# Set environment variables
export TELEGRAM_BOT_TOKEN="bot_xxxxxx"
export TELEGRAM_CHAT_ID="chat_12345"

# Start debugging session
./tmate_debugger.sh

# Resume workflow (after debugging)
touch /tmp/continue
```

---

> **⚠️ 重要提示**  
> 1. 会话凭证通过Telegram明文传输，建议仅在私有频道使用  
> 2. CI环境默认超时限制为6小时（GitHub Actions标准）  
> 3. 调试结束后自动清理临时文件  



> **⚠️ Important Notes**  
> 1. Session credentials are sent via Telegram in plaintext - recommended for private channels only  
> 2. Default CI timeout is 6 hours (GitHub Actions standard)  
> 3. Temporary files auto-cleaned after session termination  


###  鸣谢
nobody now
