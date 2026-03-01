> [!NOTE]
> **[Shannon Lite 在无提示、源码感知的 XBOW 基准测试中达到 96.15% 的成功率。&rarr;](https://github.com/KeygraphHQ/shannon/tree/main/xben-benchmark-results/README.md)**


<div align="center">

<a href="https://trendshift.io/repositories/15604" target="_blank"><img src="https://trendshift.io/api/badge/repositories/15604" alt="KeygraphHQ%2Fshannon | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

<img src="./assets/github-banner.png" alt="Shannon — AI 渗透测试框架" width="100%">

# Shannon 是你的全自动 AI pentester。

Shannon 的工作很简单：在别人之前攻破你的 Web 应用。<br />
你 vibe-coding 蓝队的红队搭档。<br />
每个 Claude（程序员）都值得拥有一个 Shannon。

---

[官网](https://keygraph.io) • [Discord](https://discord.gg/KAqzSHHpRt)

---
</div>

## 🎯 Shannon 是什么？

Shannon 是一个 AI pentester，交付实际 exploit，而不仅仅是告警。

Shannon 的目标是在别人之前攻破你的 Web 应用。它自主地在你的代码中搜寻攻击向量，然后使用内置浏览器执行真实 exploit，如 Injection 攻击和认证绕过，以证明漏洞确实可被利用。

**Shannon 解决了什么问题？**

得益于 Claude Code 和 Cursor 等工具，你的团队持续交付代码。但你的 pentest？一年才做一次。这造成了*巨大的*安全缺口。在其余的 364 天里，你可能在不知不觉中把漏洞部署到生产环境。

Shannon 通过充当按需 whitebox pentester 来弥合这一差距。它不只是发现潜在问题，而是执行真实 exploit，提供漏洞的具体证明。这让你可以自信地交付，知道每个构建都可以得到安全保障。

> [!NOTE]
> **从自主 Pentesting 到自动化合规**
>
> Shannon 是 **Keygraph 安全与合规平台**的核心组件。
>
> 虽然 Shannon 自动化了应用 pentesting 的关键任务，但我们的更广泛平台自动化了你的整个合规之旅——从证据收集到审计就绪。我们正在打造"网络安全领域的 Rippling"，一个单一平台来管理你的安全态势并简化 SOC 2 和 HIPAA 等合规框架。
>
> ➡️ **[了解更多关于 Keygraph 平台](https://keygraph.io)**

## 🎬 观看 Shannon 实战

**真实成果**：Shannon 在 OWASP Juice Shop 中发现了 20+ 个严重漏洞，包括完整的认证绕过和数据库外泄。[查看完整报告 &rarr;](sample-reports/shannon-report-juice-shop.md)

![演示](assets/shannon-action.gif)

## ✨ 功能特性

- **完全自主运行**：用一条命令启动 pentest。AI 处理从高级 2FA/TOTP 登录（包括 Google 登录）和浏览器导航到最终报告的所有内容，零干预。
- **Pentester 级别的报告与可复现 Exploit**：交付专注于已验证、可利用发现的最终报告，附带可复制的 Proof-of-Concept，消除误报并提供可操作的结果。
- **关键 OWASP 漏洞覆盖**：目前识别并验证以下严重漏洞：Injection、XSS、SSRF 和 Broken Authentication/Authorization，更多类型正在开发中。
- **代码感知动态测试**：分析你的源代码以智能引导其攻击策略，然后对运行中的应用执行基于浏览器和命令行的实时 exploit，以确认真实风险。
- **集成安全工具驱动**：通过利用领先的侦察和测试工具（包括 **Nmap、Subfinder、WhatWeb 和 Schemathesis**）增强其发现阶段，对目标环境进行深度分析。
- **并行处理加速结果**：更快获得报告。系统并行化最耗时的阶段，同时运行所有漏洞类型的分析和利用。

## 📦 产品线

Shannon 有两个版本：

| 版本 | 许可证 | 最适合 |
|---------|---------|----------|
| **Shannon Lite** | AGPL-3.0 | 安全团队、独立研究者、测试自己的应用 |
| **Shannon Pro** | 商业版 | 需要高级功能、CI/CD 集成和专属支持的企业 |

> **本仓库包含 Shannon Lite，**它使用我们的核心自主 AI pentesting 框架。**Shannon Pro** 在此基础之上增加了先进的、由 LLM 驱动的数据流分析引擎（灵感来自 [LLMDFA 论文](https://arxiv.org/abs/2402.10754)），用于企业级代码分析和更深入的漏洞检测。

> [!IMPORTANT]
> **仅 White-box。** Shannon Lite 专为 **white-box（源码可用）**应用安全测试设计。
> 它需要访问你的应用源代码和仓库结构。

[查看功能对比](./SHANNON-PRO.md)
## 📑 目录

- [Shannon 是什么？](#-shannon-是什么)
- [观看 Shannon 实战](#-观看-shannon-实战)
- [功能特性](#-功能特性)
- [产品线](#-产品线)
- [安装与使用说明](#-安装与使用说明)
  - [前置要求](#前置要求)
  - [快速开始](#快速开始)
  - [监控进度](#监控进度)
  - [停止 Shannon](#停止-shannon)
  - [使用示例](#使用示例)
  - [工作区与恢复](#工作区与恢复)
  - [配置（可选）](#配置可选)
  - [【实验性 - 不支持】Router 模式（替代提供商）](#实验性---不支持router-模式替代提供商)
  - [输出与结果](#输出与结果)
- [示例报告](#-示例报告)
- [架构](#️-架构)
- [覆盖范围与路线图](#-覆盖范围与路线图)
- [免责声明](#️-免责声明)
- [许可证](#-许可证)
- [社区与支持](#-社区--支持)
- [联系我们](#-联系我们)

---

## 🚀 安装与使用说明

### 前置要求

- **Docker** - 容器运行时（[安装 Docker](https://docs.docker.com/get-docker/)）
- **AI 提供商凭证**（选择其一）：
  - **Anthropic API key**（推荐）- 从 [Anthropic Console](https://console.anthropic.com) 获取
  - **Claude Code OAuth token**
  - **【实验性 - 不支持】通过 Router 模式的替代提供商** - 通过 OpenRouter 使用 OpenAI 或 Google Gemini（参见 [Router 模式](#实验性---不支持router-模式替代提供商)）

### 快速开始

```bash
# 1. 克隆 Shannon
git clone https://github.com/KeygraphHQ/shannon.git
cd shannon

# 2. 配置凭证（选择一种方法）

# 选项 A：导出环境变量
export ANTHROPIC_API_KEY="your-api-key"              # 或 CLAUDE_CODE_OAUTH_TOKEN
export CLAUDE_CODE_MAX_OUTPUT_TOKENS=64000           # 推荐

# 选项 B：创建 .env 文件
cat > .env << 'EOF'
ANTHROPIC_API_KEY=your-api-key
CLAUDE_CODE_MAX_OUTPUT_TOKENS=64000
EOF

# 3. 运行 pentest
./shannon start URL=https://your-app.com REPO=your-repo
```

Shannon 将构建容器、启动工作流并返回工作流 ID。Pentest 在后台运行。

### 监控进度

```bash
# 查看实时工作日志
./shannon logs

# 查询特定工作流的进度
./shannon query ID=shannon-1234567890

# 打开 Temporal Web UI 进行详细监控
open http://localhost:8233
```

### 停止 Shannon

```bash
# 停止所有容器（保留工作流数据）
./shannon stop

# 完全清理（删除所有数据）
./shannon stop CLEAN=true
```

### 使用示例

```bash
# 基础 pentest
./shannon start URL=https://example.com REPO=repo-name

# 使用配置文件
./shannon start URL=https://example.com REPO=repo-name CONFIG=./configs/my-config.yaml

# 自定义输出目录
./shannon start URL=https://example.com REPO=repo-name OUTPUT=./my-reports

# 命名工作区
./shannon start URL=https://example.com REPO=repo-name WORKSPACE=q1-audit

# 列出所有工作区
./shannon workspaces
```

### 工作区与恢复

Shannon 支持**工作区**，允许你恢复中断或失败的运行，而无需重新运行已完成的 agent。

**工作原理：**
- 每次运行都会在 `audit-logs/` 中创建工作区（默认自动命名，如 `example-com_shannon-1771007534808`）
- 使用 `WORKSPACE=<name>` 为运行指定自定义名称以便参考
- 要恢复任何运行，通过 `WORKSPACE=` 传递其工作区名称 — Shannon 会检测哪些 agent 成功完成并从中断处继续
- 每个 agent 的进度通过 git commit 进行 checkpoint，因此恢复的运行从干净、已验证的状态开始

```bash
# 使用命名工作区启动
./shannon start URL=https://example.com REPO=repo-name WORKSPACE=my-audit

# 恢复同一工作区（跳过已完成的 agent）
./shannon start URL=https://example.com REPO=repo-name WORKSPACE=my-audit

# 恢复之前运行的自动命名工作区
./shannon start URL=https://example.com REPO=repo-name WORKSPACE=example-com_shannon-1771007534808

# 列出所有工作区及其状态
./shannon workspaces
```

> [!NOTE]
> 恢复时 `URL` 必须与原始工作区 URL 匹配。Shannon 会拒绝不匹配的 URL 以防止跨目标污染。

### 准备你的仓库

Shannon 期望目标仓库放在项目根目录下的 `./repos/` 目录中。`REPO` 标志指代 `./repos/` 内的文件夹名称。将要扫描的仓库复制到 `./repos/`，或直接在那里克隆：

```bash
git clone https://github.com/your-org/your-repo.git ./repos/your-repo
```

**对于 monorepo：**

```bash
git clone https://github.com/your-org/your-monorepo.git ./repos/your-monorepo
```

**对于多仓库应用**（如独立的前端/后端）：

```bash
mkdir ./repos/your-app
cd ./repos/your-app
git clone https://github.com/your-org/frontend.git
git clone https://github.com/your-org/backend.git
git clone https://github.com/your-org/api.git
```

### 平台特定说明

**Windows：**

*原生（Git Bash）：*

安装 [Git for Windows](https://git-scm.com/install/windows) 并从安装了 Docker Desktop 的 **Git Bash** 运行 Shannon。

*WSL2（推荐）：*

**步骤 1：确保使用 WSL 2**

```powershell
wsl --install
wsl --set-default-version 2

# 检查已安装的发行版
wsl --list --verbose

# 如果没有发行版，安装一个（推荐 Ubuntu 24.04）
wsl --list --online
wsl --install Ubuntu-24.04

# 如果发行版显示 VERSION 1，将其转换为 WSL 2：
wsl --set-version <distro-name> 2
```

参考 [WSL 基本命令](https://learn.microsoft.com/en-us/windows/wsl/basic-commands)。

**步骤 2：在 Windows 上安装 Docker Desktop** 并在 *设置 > 常规 > 使用基于 WSL 2 的引擎* 下启用 **WSL2 后端**。

**步骤 3：在 WSL 中克隆并运行 Shannon。** 在 PowerShell 或 CMD 中输入 `wsl -d <distro-name>` 并按 Enter 打开 WSL 终端。

```bash
# 在 WSL 终端内
git clone https://github.com/KeygraphHQ/shannon.git
cd shannon
cp .env.example .env  # 用你的 API key 编辑
./shannon start URL=https://your-app.com REPO=your-repo
```

要访问 Temporal Web UI，在 WSL 中运行 `ip addr` 找到你的 WSL IP 地址，然后在 Windows 浏览器中访问 `http://<wsl-ip>:8233`。

Windows Defender 可能将报告中的 exploit 代码标记为误报；参见下方的 [杀毒软件误报](#6-windows-杀毒软件误报)。

**Linux（原生 Docker）：**

根据你的 Docker 设置，你可能需要使用 `sudo` 运行命令。如果遇到输出文件的权限问题，确保你的用户有权访问 Docker socket。

**macOS：**

安装 Docker Desktop 后即可直接使用。

**测试本地应用：**

Docker 容器无法访问你主机上的 `localhost`。使用 `host.docker.internal` 代替 `localhost`：

```bash
./shannon start URL=http://host.docker.internal:3000 REPO=repo-name
```

### 配置（可选）

虽然你可以在没有配置文件的情况下运行，但创建配置文件可以实现认证测试和自定义分析。将你的配置文件放在 `./configs/` 目录中 — 此文件夹会自动挂载到 Docker 容器中。

#### 创建配置文件

复制并修改示例配置：

```bash
cp configs/example-config.yaml configs/my-app-config.yaml
```

#### 基本配置结构

```yaml
authentication:
  login_type: form
  login_url: "https://your-app.com/login"
  credentials:
    username: "test@example.com"
    password: "yourpassword"
    totp_secret: "LB2E2RX7XFHSTGCK"  # 2FA 可选

  login_flow:
    - "Type $username into the email field"
    - "Type $password into the password field"
    - "Click the 'Sign In' button"

  success_condition:
    type: url_contains
    value: "/dashboard"

rules:
  avoid:
    - description: "AI 应避免测试注销功能"
      type: path
      url_path: "/logout"

  focus:
    - description: "AI 应重点测试 API 端点"
      type: path
      url_path: "/api"
```

#### 2FA 的 TOTP 设置

如果你的应用使用双因素认证，只需将 TOTP secret 添加到配置文件中。AI 将在测试期间自动生成所需的验证码。

#### 订阅计划速率限制

Anthropic 订阅计划的使用量在**滚动 5 小时窗口**内重置。默认的重试策略（最大回退 30 分钟）会在窗口重置前耗尽重试次数。将此添加到你的配置：

```yaml
pipeline:
  retry_preset: subscription          # 将最大回退延长至 6 小时，100 次重试
  max_concurrent_pipelines: 2         # 一次运行 5 个 pipeline 中的 2 个（减少突发 API 使用）
```

`max_concurrent_pipelines` 控制同时运行多少个漏洞 pipeline（1-5，默认：5）。较低的值降低触发速率限制的几率，但会增加挂钟时间。

### 【实验性 - 不支持】Router 模式（替代提供商）

Shannon 可以通过 claude-code-router 实验性地将请求路由到替代 AI 提供商。此模式不受官方支持，主要用于：

* **模型实验** — 使用 GPT-5.2 或 Gemini 3 系列模型尝试 Shannon

#### 快速设置

1. 将你的提供商 API key 添加到 `.env`：

```bash
# 选择一个提供商：
OPENAI_API_KEY=sk-...
# 或
OPENROUTER_API_KEY=sk-or-...

# 设置默认模型：
ROUTER_DEFAULT=openai,gpt-5.2  # provider,model 格式
```

2. 使用 `ROUTER=true` 运行：

```bash
./shannon start URL=https://example.com REPO=repo-name ROUTER=true
```

#### 实验性模型

| 提供商 | 模型 |
|----------|--------|
| OpenAI | gpt-5.2, gpt-5-mini |
| OpenRouter | google/gemini-3-flash-preview |

#### 免责声明

此功能是实验性的且不受支持。输出质量很大程度上取决于模型。Shannon 基于 Anthropic Agent SDK 构建，并针对 Anthropic Claude 模型进行了优化和主要测试。替代提供商可能会产生不一致的结果（包括早期阶段如 Recon 失败），具体取决于模型和路由设置。

### 输出与结果

所有结果默认保存到 `./audit-logs/{hostname}_{sessionId}/`。使用 `--output <path>` 指定自定义目录。

输出结构：
```
audit-logs/{hostname}_{sessionId}/
├── session.json          # 指标和会话数据
├── agents/               # 每个 agent 的执行日志
├── prompts/              # 用于可复现性的提示快照
└── deliverables/
    └── comprehensive_security_assessment_report.md   # 最终综合安全报告
```

---

## 📊 示例报告

> **寻找定量基准？** [查看完整基准方法和结果 &rarr;](./xben-benchmark-results/README.md)

观看 Shannon 对行业标准漏洞应用的 pentest 结果，了解其能力：

#### 🧃 **OWASP Juice Shop** • [GitHub](https://github.com/juice-shop/juice-shop)

*由 OWASP 维护的臭名昭著的不安全 Web 应用，旨在测试工具发现各种现代漏洞的能力。*

**性能**：在单次自动运行中识别出**超过 20 个高影响漏洞**，涵盖目标 OWASP 类别。

**主要成就**：

- **实现完整认证绕过**并通过 Injection 攻击外泄整个用户数据库
- **执行完整权限提升**，通过注册工作流绕过创建新管理员账户
- **识别并利用系统性授权缺陷（IDOR）**访问和修改任何用户的私人数据和购物车
- **发现 SSRF 漏洞**，实现内部网络侦察

📄 **[查看完整报告 &rarr;](sample-reports/shannon-report-juice-shop.md)**

---

#### 🔗 **c{api}tal API** • [GitHub](https://github.com/Checkmarx/capital)

*来自 Checkmarx 的故意存在漏洞的 API，旨在测试工具发现 OWASP API Security Top 10 的能力。*

**性能**：识别出**近 15 个严重和高危漏洞**，导致完整的应用沦陷。

**主要成就**：

- **通过隐藏调试端点中的命令链绕过 denylist，执行 root 级 Injection 攻击**
- **通过发现并针对遗留的未修补 v1 API 端点实现完整认证绕过**
- **利用用户资料更新功能中的 Mass Assignment 漏洞将普通用户提升为完整管理员权限**
- **展示高准确性**，正确确认应用的强大 XSS 防御，报告零误报

📄 **[查看完整报告 &rarr;](sample-reports/shannon-report-capital-api.md)**

---

#### 🚗 **OWASP crAPI** • [GitHub](https://github.com/OWASP/crAPI)

*来自 OWASP 的现代故意存在漏洞的 API，旨在基准测试工具针对 OWASP API Security Top 10 的有效性。*

**性能**：识别出**超过 15 个严重和高危漏洞**，实现完整的应用沦陷。

**主要成就**：

- **使用多种高级 JWT 攻击绕过认证**，包括 Algorithm Confusion、alg:none 和弱 key（kid）注入
- **通过 Injection 攻击实现完整数据库沦陷**，从 PostgreSQL 数据库外泄用户凭证
- **执行关键 SSRF 攻击**，成功将内部认证令牌转发到外部服务
- **展示高准确性**，正确识别应用的强大 XSS 防御，报告零误报

📄 **[查看完整报告 &rarr;](sample-reports/shannon-report-crapi.md)**

---

*这些结果展示了 Shannon 超越简单扫描的能力，以最小的误报和可操作的 Proof-of-Concept 执行深度上下文利用。*

---

## 🏗️ 架构

Shannon 使用复杂的多 agent 架构模拟人类 pentester 的方法论。它结合 white-box 源代码分析与 black-box 动态利用，跨越四个不同阶段：

```
                    ┌──────────────────────┐
                    │    Reconnaissance    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────┴───────────┐
                    │          │           │
                    ▼          ▼           ▼
        ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
        │ Vuln Analysis   │ │ Vuln Analysis   │ │      ...        │
        │  (Injection)    │ │     (XSS)       │ │                 │
        └─────────┬───────┘ └─────────┬───────┘ └─────────┬───────┘
                  │                   │                   │
                  ▼                   ▼                   ▼
        ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
        │  Exploitation   │ │  Exploitation   │ │      ...        │
        │  (Injection)    │ │     (XSS)       │ │                 │
        └─────────┬───────┘ └─────────┬───────┘ └─────────┬───────┘
                  │                   │                   │
                  └─────────┬─────────┴───────────────────┘
                            │
                            ▼
                    ┌──────────────────────┐
                    │      Reporting       │
                    └──────────────────────┘
```

### 架构概述

Shannon 旨在模拟人类 pentester 的方法论。它以 Anthropic 的 Claude Agent SDK 作为核心推理引擎，但其真正优势在于围绕它构建的复杂多 agent 架构。该架构将 **white-box 源代码分析**的深层上下文与 **black-box 动态利用**的真实验证相结合，由 orchestrator 通过四个不同阶段管理，确保专注于最小化误报和智能上下文管理。

---

#### **阶段 1：Reconnaissance**

第一阶段构建应用攻击面的全面地图。Shannon 分析源代码并与 Nmap 和 Subfinder 等工具集成以了解技术栈和基础设施。同时，它通过浏览器自动化执行实时应用探索，将代码级洞察与现实行为相关联，生成所有入口点、API 端点和认证机制的详细地图，供下一阶段使用。

#### **阶段 2：Vulnerability Analysis**

为了最大化效率，此阶段并行运行。使用 reconnaissance 数据，每个 OWASP 类别的专业 agent 并行搜寻潜在缺陷。对于 Injection 和 SSRF 等漏洞，agent 执行结构化数据流分析，追踪用户输入到危险的 sink。此阶段产生一个关键交付物：**假设的可利用路径**列表，传递给验证阶段。

#### **阶段 3：Exploitation**

继续并行工作流以保持速度，此阶段完全致力于将假设转化为证明。专用 exploit agent 接收假设路径并尝试使用浏览器自动化、命令行工具和自定义脚本执行真实攻击。此阶段执行严格的**"无 Exploit，无报告"**政策：如果假设无法成功利用以展示影响，则作为误报丢弃。

#### **阶段 4：Reporting**

最终阶段将所有验证的发现编译成专业、可操作的报告。Agent 整合 reconnaissance 数据和成功的 exploit 证据，清理任何噪声或幻觉产物。仅包含已验证的漏洞，附带**可复现、可复制的 Proof-of-Concept**，交付专注于已证明风险的最终 pentest 级别报告。


## 📋 覆盖范围与路线图

有关 Shannon 安全测试覆盖范围和开发路线图的详细信息，请参阅我们的 [覆盖范围与路线图](./COVERAGE.md) 文档。

## ⚠️ 免责声明

### 重要使用指南与免责声明

在使用 Shannon (Lite) 之前，请仔细查看以下指南。作为用户，你对自己的行为负责并承担所有责任。

#### **1. 潜在变异效应与环境选择**

这不是被动扫描器。Exploitation agent 旨在**主动执行攻击**以确认漏洞。此过程可能对目标应用及其数据产生变异效应。

> [!WARNING]
> **⚠️ 请勿在生产环境上运行 Shannon。**
>
> - 它专用于沙盒、预发布或本地开发环境，这些环境中数据完整性不是问题。
> - 潜在的变异效应包括但不限于：创建新用户、修改或删除数据、入侵测试账户，以及触发来自 injection 攻击的意外副作用。

#### **2. 法律与道德使用**

Shannon 仅用于合法的安全审计目的。

> [!CAUTION]
> **你必须获得目标系统所有者的明确书面授权**才能运行 Shannon。
>
> 未经授权扫描和利用你不拥有的系统是违法的，可能会根据《计算机欺诈和滥用法》(CFAA) 等法律被起诉。Keygraph 对 Shannon 的任何滥用不承担责任。

#### **3. LLM 与自动化注意事项**

- **需要验证**：虽然我们的"以利用为证明"方法论经过了大量工程投入以消除误报，但底层 LLM 仍可能在最终报告中产生幻觉或弱支持的内容。**人工监督**对于验证所有报告发现的合法性和严重性至关重要。
- **全面性**：由于 LLM 上下文窗口的固有局限性，Shannon Lite 的分析可能不够详尽。对于整个代码库更全面、基于图的分析，**Shannon Pro** 利用其先进的数据流分析引擎确保更深入、更彻底的覆盖。

#### **4. 分析范围**

- **目标漏洞**：Shannon Lite 的当前版本专门针对以下类别的*可利用*漏洞：
  - Broken Authentication & Authorization
  - Injection
  - Cross-Site Scripting (XSS)
  - Server-Side Request Forgery (SSRF)
- **Shannon Lite 不覆盖的内容**：此列表并非所有潜在安全风险的详尽列表。Shannon Lite 的"以利用为证明"模式意味着它不会报告无法主动利用的问题，如易受攻击的第三方库或不安全的配置。这些类型的深度静态分析发现是 **Shannon Pro** 中高级分析引擎的核心关注点。

#### **5. 成本与性能**

- **时间**：截至当前版本，完整测试运行通常需要 **1 到 1.5 小时**完成。
- **成本**：使用 Anthropic 的 Claude 4.5 Sonnet 模型运行完整测试可能产生约 **50 美元**的费用。成本因模型定价和应用复杂性而异。

#### **6. Windows 杀毒软件误报**

Windows Defender 可能将 `xben-benchmark-results/` 或 `deliverables/` 中的文件标记为恶意软件。这些是由报告中的 exploit 代码引起的误报。在 Windows Defender 中为 Shannon 目录添加排除项，或使用 Docker/WSL2。


## 📜 许可证

Shannon Lite 在 [GNU Affero General Public License v3.0 (AGPL-3.0)](LICENSE) 下发布。

Shannon 是开源的（AGPL v3）。此许可证允许你：
- 自由用于所有内部安全测试。
- 私下修改代码供内部使用，无需分享你的更改。

AGPL 的分享要求主要适用于将 Shannon 作为公共或托管服务（如 SaaS 平台）提供的组织。在这些特定情况下，对核心软件所做的任何修改都必须开源。


## 👥 社区与支持

### 社区资源

**贡献：** 目前，我们不接受外部代码贡献（PR）。
欢迎通过 Issues 报告 bug 和提出功能请求。

- 🐛 **通过 [GitHub Issues](https://github.com/KeygraphHQ/shannon/issues) 报告 bug**
- 💡 **在 [Discussions](https://github.com/KeygraphHQ/shannon/discussions) 中建议功能**
- 💬 **加入我们的 [Discord](https://discord.gg/KAqzSHHpRt)** 获取实时社区支持

### 保持联系

- 🐦 **Twitter**: [@KeygraphHQ](https://twitter.com/KeygraphHQ)
- 💼 **LinkedIn**: [Keygraph](https://linkedin.com/company/keygraph)
- 🌐 **官网**: [keygraph.io](https://keygraph.io)



## 💬 联系我们

### 对 Shannon Pro 感兴趣？

Shannon Pro 专为认真对待应用安全的组织设计。它提供企业级功能、专属支持和无缝 CI/CD 集成，全部由我们最先进的基于 LLM 的分析引擎驱动。在漏洞到达生产环境之前，发现并修复代码库深处的复杂漏洞。

有关功能、技术差异和企业用例的详细分解，请参阅我们的 [完整对比指南](./SHANNON-PRO.md)。

<p align="center">
  <a href="https://docs.google.com/forms/d/e/1FAIpQLSf-cPZcWjlfBJ3TCT8AaWpf8ztsw3FaHzJE4urr55KdlQs6cQ/viewform?usp=header" target="_blank">
    <img src="https://img.shields.io/badge/📋%20Express%20Interest%20in%20Shannon%20Pro-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="表达兴趣">
  </a>
</p>

**或直接联系我们：**

📧 **邮箱**: [shannon@keygraph.io](mailto:shannon@keygraph.io)

---

<p align="center">
  <b>由 Keygraph 团队用 ❤️ 打造</b><br>
  <i>让应用安全对每个人都可及</i>
</p>
