<p align="center">
  <img src="resources/icon-256x256.png" width="120" alt="DeciFlow Logo">
</p>

<h1 align="center">DeciFlow</h1>

<p align="center">本地优先的 AI 数据运营助手</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-Proprietary-red.svg" alt="License">
  <img src="https://img.shields.io/badge/Electron-41-9FEAF9?logo=electron" alt="Electron">
  <img src="https://img.shields.io/badge/React-19-61DAFB?logo=react" alt="React">
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript" alt="TypeScript">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey" alt="Platform">
</p>

<p align="center">
  <a href="#下载安装">下载</a> ·
  <a href="#快速开始">快速开始</a> ·
  <a href="https://github.com/Terry-Xxxu/DeciFlow/issues">反馈问题</a>
</p>

---

![DeciFlow 界面预览](screenshots/dashboard.png)

---

## 产品简介

DeciFlow 是一款运行在本地的 AI 数据分析工具，面向运营、产品、业务等非技术人员设计。所有数据留存在本地，AI 服务由用户自行配置，支持主流云端服务商和本地模型。

核心理念：让不懂 SQL 的人也能做数据分析，让懂 SQL 的人做得更快。

---

## 核心功能

### Deci — 内置 AI 数据助手

![Deci 对话](screenshots/deci-chat.png)

Deci 是 DeciFlow 的内置 AI 助手，具备完整的数据分析工具链：

- 理解业务语言，支持用字段别名和自定义指标提问
- 自动执行 SQL 查询、生成图表、发现数据异常
- 配置监控规则，指标超阈值时主动推送告警
- 生成结构化经营分析报告，导出为 Word 文档
- 支持飞书机器人接入，在飞书中直接与 Deci 对话

### 数据接入

| 类型 | 支持范围 |
|------|---------|
| 文件 | CSV、Excel（支持多 Sheet） |
| 关系型数据库 | PostgreSQL、MySQL、SQLite、SQL Server |
| NoSQL | MongoDB、Redis |
| 列式数据库 | ClickHouse |
| 云服务 | 飞书多维表格 |
| 连接方式 | 直连、SSH 隧道、SSL/TLS |

### 分析工具

**快捷分析**：内置 17 个行业的分析模板（电商、SaaS、餐饮、制造、HR、财务等），一键执行，自动匹配数据字段。

**可视化查询构建器**：点选字段、配置聚合函数和筛选条件，实时预览 SQL，无需手写查询语句。

**原生 SQL 编辑器**：支持 SQL 语法高亮，Cmd/Ctrl+Enter 快捷执行，结果一键导出 CSV。

**数据透视表**：行列字段自由组合，支持 SUM、COUNT、AVG、MAX、MIN 聚合，可按值排序和显示合计。

**图表系统**：支持折线图、柱状图、饼图、面积图、漏斗图、热力图。支持点击数据点下钻查看原始数据，支持条件格式热力着色。

**计算字段**：基于现有字段创建派生列，支持数学运算和字符串拼接。

### 数据治理

**数据字典**：为字段配置中文名、业务含义和分析建议，自动注入 AI 上下文，提升查询准确性。

**表关系配置**：自动发现关联字段，支持手动添加外键关系，Deci 在跨表分析时自动使用正确的 JOIN 条件。

**涉密配置**：标记敏感表或字段，所有查询结果自动掩码，支持手机号、邮箱、身份证的格式化脱敏。

### AI 配置

支持的 AI 服务商：

| 服务商 | 说明 |
|--------|------|
| Anthropic Claude | claude-3-5-sonnet 等系列 |
| OpenAI | GPT-4o 等系列 |
| DeepSeek | deepseek-chat 等系列 |
| Moonshot Kimi | moonshot-v1 系列 |
| 阿里云通义千问 | qwen-plus 等系列 |
| 智谱 GLM | glm-4 等系列 |
| MiniMax | abab6.5 等系列 |
| Ollama | 本地部署，支持任意模型 |

所有服务商支持自定义 API 地址，适配私有化部署场景。无 AI 时，快捷分析、SQL 编辑器、可视化查询等功能仍可正常使用。

---

## 下载安装

前往 [Releases 页面](https://github.com/Terry-Xxxu/DeciFlow/releases) 下载对应平台的安装包。

| 平台 | 安装包 |
|------|--------|
| Windows 10/11（64 位） | `DeciFlow-Setup-x64.exe` |
| macOS Apple Silicon（M 系列） | `DeciFlow-arm64.dmg` |
| macOS Intel | `DeciFlow-x64.dmg` |
| Linux x64 | `DeciFlow-x64.AppImage` |

**macOS 首次启动说明**

如果 macOS 提示「无法验证开发者」，在终端执行以下命令后重新打开：

```bash
xattr -cr /Applications/DeciFlow.app
```

---

## 快速开始

**第一步：导入数据**

支持拖拽 CSV 或 Excel 文件直接导入，或在「数据源」页面添加数据库连接。

![数据源](screenshots/datasources.png)

**第二步：配置 AI（可选）**

在「设置」-「AI 配置」中填写 API Key。推荐使用 Claude 或 GPT-4o 以获得最佳分析质量。

![AI 配置](screenshots/settings-ai.png)

**第三步：开始分析**

在首页选择数据表，点击快捷分析模板，或直接在 Deci 对话框中用自然语言提问：
- 分析上个月每天的销售额趋势
- 找出退款率最高的产品类目
- 对比各地区的客单价和转化率

---

## 安全说明

- 数据文件和数据库连接配置均存储在本地，不上传任何服务器
- API Key 使用系统 Keychain 加密存储（macOS Keychain / Windows Credential Manager）
- 所有 SQL 查询经过安全校验，禁止 INSERT、UPDATE、DELETE 等写操作
- 涉密字段支持自动掩码，敏感数据不会出现在 AI 上下文中

---

## 技术栈

| 类别 | 技术 |
|------|------|
| 前端 | React 19、TypeScript 5、Tailwind CSS |
| 桌面框架 | Electron 41 |
| 图表 | Recharts |
| 文件数据库 | alasql |
| 关系型数据库 | node-postgres、mysql2、better-sqlite3、mssql |
| NoSQL | mongodb、ioredis |
| 构建工具 | Vite、electron-builder |
| AI 接入 | 多 Provider 适配层，兼容 OpenAI 标准接口和 Anthropic 接口 |

---

## 反馈与支持

- 提交 Bug 或功能建议：[Issues](https://github.com/Terry-Xxxu/DeciFlow/issues)
- 参与讨论：[Discussions](https://github.com/Terry-Xxxu/DeciFlow/discussions)

---

&copy; 2026 Terry. All rights reserved.