# CloudBase AI Toolkit + Gemini CLI

<div align="center">

**🚀 Gemini CLI + 云开发 = 几分钟内从想法到上线的全栈应用**

[![GitHub Stars](https://img.shields.io/github/stars/TencentCloudBase/CloudBase-AI-ToolKit?style=social)](https://github.com/TencentCloudBase/CloudBase-AI-ToolKit)
[![开源协议](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/TencentCloudBase/CloudBase-AI-ToolKit/blob/main/LICENSE)

</div>

> 💡 **为什么选择 Gemini CLI + CloudBase AI Toolkit？**  
> Gemini CLI 是 Google 推出的开源命令行 AI 代理，提供强大的本地 AI 工作流和 MCP 协议支持，拥有 1M 令牌上下文窗口和丰富的内置工具。结合 CloudBase AI Toolkit，让你通过自然语言描述需求，AI 自动生成并部署全栈应用到腾讯云开发平台。特别适合命令行爱好者、自动化脚本开发和快速原型构建。

## ✨ 核心优势

| 🎯 **开发效率** | ⚡ **部署速度** | 🛡️ **稳定可靠** |
|---|---|---|
| AI 自动生成代码和架构<br/>内置云开发最佳实践规则<br/>智能错误修复和优化 | 一键部署到腾讯云开发<br/>国内 CDN 加速访问<br/>Serverless 架构免运维 | 330万开发者验证的平台<br/>企业级安全和稳定性<br/>完善的监控和日志系统 |

## 🚀 5分钟快速开始

### 方式一：使用项目模板（推荐）

选择预配置的项目模板，开箱即用：

<div align="center">

**[📦 查看所有项目模板](../templates)**

</div>

### 方式二：现有项目集成

如果你已有项目，只需 3 步集成：

```bash
# 1. 配置 MCP（具体配置见下方详细步骤）
# 2. 下载 AI 规则
# 3. 开始使用
```

配置完成后，对 AI 说：**"登录云开发"** 即可开始！

## 🔧 详细配置指南

### 步骤 1：安装 Gemini CLI

确保安装 Node.js 18+，然后全局安装 Gemini CLI：

```bash
npm install -g @google/gemini-cli
```

或直接运行：

```bash
npx @google/gemini-cli
```

首次运行时，使用个人 Google 账户登录即可获得免费额度（每分钟 60 次请求，每天 1000 次请求）。

### 步骤 2：配置 CloudBase MCP

> [!TIP] 
> 如果安装以后工具数量一直为 0，请参考[常见问题](https://docs.cloudbase.net/ai/cloudbase-ai-toolkit/faq#mcp-%E6%98%BE%E7%A4%BA%E5%B7%A5%E5%85%B7%E6%95%B0%E9%87%8F%E4%B8%BA-0-%E6%80%8E%E4%B9%88%E5%8A%9E)

如果使用模板项目，MCP 配置已经预置完成。

如果不是从模板开始，可以在用户主目录（`~`）或项目目录中创建 `.gemini/settings.json` 文件：

```json
{
  "mcpServers": {
    "cloudbase": {
      "command": "npx",
      "args": ["npm-global-exec@latest", "@cloudbase/cloudbase-mcp@latest"],
      "env": {
        "INTEGRATION_IDE": "Gemini"
      }
    }
  }
}
```

**一键配置验证：**

运行 Gemini CLI，然后使用以下命令：

```bash
gemini
> /mcp
```

查看已配置的 MCP 服务器。如果还没有配置 CloudBase MCP，可以手动添加配置文件。

### 步骤 3：启用 AI 规则

模板项目根目录已经包含 `GEMINI.md` 文件，包含 CloudBase 开发规则。

如果是现有项目，在 Gemini CLI 中对 AI 说：

```
在当前项目中下载云开发 AI 规则
```

如果你只想下载Gemini CLI相关的配置文件，避免项目文件混乱，可以指定IDE类型：
```
在当前项目中下载云开发 AI 规则，只包含Gemini CLI配置
```

### 步骤 4：开始开发

启动 Gemini CLI：

```bash
gemini
```

然后对 AI 说：

```
登录云开发
```

## 🎯 开始使用

配置完成后，对 AI 说：

```
登录云开发
```

然后就可以开始开发了，例如：

```
创建一个在线投票系统，支持创建投票、参与投票、结果统计，使用云数据库存储，最后部署
```

## 💡 Gemini CLI 特色功能

### 🔧 内置工具

Gemini CLI 提供丰富的内置工具：

- **Google Search**: 实时搜索信息
- **文件操作**: 读写、编辑文件
- **Shell 命令**: 执行系统命令
- **MCP 支持**: 扩展第三方能力

查看所有可用工具：

```bash
> /tools
```

### 📚 上下文记忆

Gemini CLI 支持分层的 `GEMINI.md` 文件：

- 全局规则：`~/.gemini/GEMINI.md`
- 项目规则：项目根目录/`GEMINI.md`
- 组件规则：子目录中的 `GEMINI.md`

查看当前加载的规则：

```bash
> /memory show
```

刷新规则：

```bash
> /memory refresh
```

### ⚡ 命令模式

常用命令：

- `/tools` - 查看可用工具
- `/mcp` - 查看 MCP 服务器状态
- `/memory` - 管理上下文记忆
- `/stats` - 查看会话统计
- `!command` - 执行 Shell 命令

### 🚀 YOLO 模式

自动执行所有操作，无需确认：

```bash
gemini --yolo
```

**⚠️ 注意：YOLO 模式会自动执行所有操作，请谨慎使用。**

## 🌟 CloudBase AI Toolkit 开源项目

<div align="center">

### 🔥 加入开源社区

[![GitHub](https://img.shields.io/badge/GitHub-TencentCloudBase/CloudBase--AI--ToolKit-black?style=for-the-badge&logo=github)](https://github.com/TencentCloudBase/CloudBase-AI-ToolKit)
[![CNB社区](https://img.shields.io/badge/CNB-CloudBase--AI--ToolKit-orange?style=for-the-badge)](https://cnb.cool/tencent/cloud/cloudbase/CloudBase-AI-ToolKit)

**⭐ Star 项目 | 🤝 贡献代码 | 💬 技术交流**

</div>

## 🛠️ 故障排除

### 常见问题

**Q: Gemini CLI 连接失败？**
A: 
1. 检查网络连接
2. 确认 Google 账户登录状态
3. 检查 `.gemini/settings.json` 配置格式

**Q: MCP 服务器启动失败？**
A:
1. 确认 Node.js 版本 >= 18
2. 检查 MCP 配置格式
3. 运行 `/mcp` 命令查看状态

**Q: AI 生成的代码不符合预期？**
A:
1. 检查 `GEMINI.md` 文件是否存在
2. 使用 `/memory show` 查看当前规则
3. 提供更详细的需求描述

更多问题请查看：[完整 FAQ](../faq)

## 🔗 官方资源

- [Gemini CLI GitHub](https://github.com/google-gemini/gemini-cli) - 官方开源仓库
- [Gemini CLI 文档](https://github.com/google-gemini/gemini-cli/tree/main/docs) - 详细使用文档
- [Google AI Studio](https://aistudio.google.com/) - 获取 API 密钥

## 📚 相关资源

- [📖 开发指南](../development) - 深入了解开发最佳实践
- [🎯 使用案例](../examples) - 查看实际应用案例  
- [🔧 MCP 工具](../mcp-tools) - 了解所有可用工具
- [❓ 常见问题](../faq) - 查看常见问题解答

## 💬 技术交流

### 微信技术交流群

<div align="center">
<img src="https://7463-tcb-advanced-a656fc-1257967285.tcb.qcloud.la/mcp/toolkit-qrcode.png" width="200" alt="微信群二维码"/>
<br/>
<i>扫码加入微信技术交流群</i>
</div>

---

<div align="center">

**🚀 立即开始使用 Gemini CLI + CloudBase AI Toolkit**

[开始使用](../getting-started) | [查看模板](../templates) | [GitHub 仓库](https://github.com/TencentCloudBase/CloudBase-AI-ToolKit)

</div> 