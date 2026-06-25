# Product Team Skill

> 产品开发团队模拟 —— 7+N 角色 + Phase-Gate 质量门禁 + 三模式运行

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-v3.0.0-blue.svg)](CHANGELOG.md)
[![Claude Skill](https://img.shields.io/badge/Claude-Code_Skill-purple.svg)](https://docs.claude.com)

`product-team-skill` 是一个面向 [Claude Code](https://docs.claude.com) 的技能（Skill），当用户提出产品/系统/功能开发需求时，会自动激活一个由 **产品经理 + 架构师 + UI 设计 + 前端 + 后端 + 测试 + 运营** 组成的虚拟开发团队，按照 **Phase-Gate** 工作流推进项目，并支持 **标准 / 资源受限 / MVP 快速验证** 三种运行模式。

---

## ✨ 核心特性

- 🧑‍🤝‍🧑 **7+N 角色团队**：7 个核心角色 + 6 个按需激活的扩展角色（DEVOPS / UX / SEC / MOBILE / DATA / BA）
- 🚦 **Phase-Gate 质量门禁**：每个阶段出口强制检查，支持人工豁免和渐进式验收
- ⚙️ **三种运行模式**：标准模式 / 资源受限模式 / MVP 快速验证模式
- 💰 **成本与预算管理**：Phase 1 输出估算，全程监控偏差
- ⚠️ **风险管理**：识别 → 评估 → 应对 → 升级 全生命周期
- 🧱 **技术债务管理**：ARCH 维护债务清单，每个 Sprint 分配 10-20% 工时偿还
- 🤝 **冲突解决机制**：4 级升级路径 + ADR 决策记录

---

## 🚀 快速开始

### 安装

#### 方式一：从 GitHub 克隆（推荐）

```bash
git clone https://github.com/KentQi/product-team-skill.git
```

将 `SKILL.md` 放到 Claude Code 的 skills 目录：

```bash
# 用户级（所有项目可用）
mkdir -p ~/.claude/skills/product-team
cp product-team-skill/SKILL.md ~/.claude/skills/product-team/
cp -r product-team-skill/references ~/.claude/skills/product-team/
```

#### 方式二：手动安装

下载 [`SKILL.md`](SKILL.md) 和 [`references/`](references/) 目录，放到你的 skills 路径下。

### 触发技能

安装后，当你对 Claude Code 说：

```
帮我开发一个 XXX 系统
帮我规划一个 XXX 产品
```

该技能会自动激活，组建虚拟开发团队开始工作。

### 第一次运行会发生什么

1. **PM（产品经理）确认就位**，输出欢迎语
2. PM 向你（甲方）提问 **11 个澄清问题**（目标用户、业务目标、技术栈、预算等）
3. PM 输出 **《角色激活清单》**，建议激活哪些扩展角色
4. PM 询问你 **选择运行模式**（标准 / 资源受限 / MVP）
5. 团队就位，按你确认的模式和 Phase 0→5 推进

> 💡 **提示**：如果你只想快速试一下，直接说"做个 MVP 验证一下"或"做个 demo"，PM 会引导你进入 MVP 模式。

---

## 📚 文档导航

### 主文档

- [**SKILL.md**](SKILL.md) —— 技能入口文档，Claude Code 加载的核心文件
- [**CHANGELOG.md**](CHANGELOG.md) —— 版本变更记录

### 参考文档（references/）

- [**agent-roles.md**](references/agent-roles.md) —— 7+N 角色完整定义、职责边界、协作模式
- [**quality-gates.md**](references/quality-gates.md) —— 质量门禁配置、例外处理、渐进式验收、人工豁免
- [**tools-and-templates.md**](references/tools-and-templates.md) —— PRD / 架构文档 / 测试用例 / 会议纪要模板
- [**risk-management.md**](references/risk-management.md) —— 风险识别、评估矩阵、应对策略、升级机制
- [**resource-constrained.md**](references/resource-constrained.md) —— 资源受限模式、角色合并、MVP 路径
- [**knowledge-management.md**](references/knowledge-management.md) —— 项目复盘、知识库建设、经验复用
- [**troubleshooting.md**](references/troubleshooting.md) —— 常见问题 FAQ、典型案例、故障恢复

### 社区文档

- [**CONTRIBUTING.md**](CONTRIBUTING.md) —— 如何贡献代码、报告 Bug、提交 PR
- [**CODE_OF_CONDUCT.md**](CODE_OF_CONDUCT.md) —— 社区行为准则
- [**SECURITY.md**](SECURITY.md) —— 安全漏洞报告方式
- [**LICENSE**](LICENSE) —— MIT 开源协议

---

## 🎯 适用场景

| 场景 | 推荐模式 | 激活的扩展角色 |
|------|---------|--------------|
| 完整 Web 产品开发 | 标准模式 | UX / DEVOPS |
| 移动 App + 后台 | 标准模式 | MOBILE / DEVOPS |
| 涉及支付 / 用户隐私 | 标准模式 | SEC / DEVOPS |
| 推荐 / AI 算法产品 | 标准模式 | DATA / DEVOPS |
| 金融 / 医疗 / 政务系统 | 标准模式 | BA / SEC / DEVOPS |
| 团队 2-3 人，时间紧 | 资源受限模式 | （按需） |
| 假设未验证，要快速试错 | MVP 模式 | （最小集） |

---

## 🏗️ 工作流概览

```
[Phase 0: 团队组建] → Gate 0: 角色清单 + 运行模式确认
  │
  ▼
[Phase 1: 需求对齐] → Gate 1: PRD 终版通过（含成本估算、风险清单）
  │
  ▼
[Phase 2: 设计与架构] → Gate 2: 架构 + 设计 + 安全评审通过
  │
  ▼
[Phase 3: 开发] → Gate 3: 代码审查 + 测试 + CI 通过（敏捷迭代）
  │
  ▼
[Phase 4: 测试] → Gate 4: 测试通过 + 安全测试 + 可用性测试
  │
  ▼
[Phase 5: 业务验收] → Gate 5: 业务验收通过 + 领域规则验证 + 项目复盘
  │
  ▼
[交付 + 知识沉淀]
```

详细说明见 [SKILL.md](SKILL.md)。

---

## 🤝 贡献

欢迎贡献！无论是：

- 🐛 报告 Bug 或提出改进建议（[Issues](../../issues)）
- 📝 改进文档
- 🔧 优化角色定义 / 工作流 / 模板
- 🌐 翻译成其他语言

请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 了解贡献流程。

---

## 📜 开源协议

本项目基于 [MIT License](LICENSE) 开源。

---

## 🙏 致谢

- 灵感来源于工程实践中的产品开发流程
- 借鉴了 [C4 Model](https://c4model.com/) / [敏捷开发](https://agilemanifesto.org/) / [Phase-Gate](https://en.wikipedia.org/wiki/Phase%E2%80%93gate_process) 等经典方法论

---

## 📮 联系方式

- **作者**：Kent
- **邮箱**：kirroyu@126.com
- **Issues**：[GitHub Issues](../../issues)
- **安全问题**：见 [SECURITY.md](SECURITY.md)

---

<div align="center">

**[⭐ Star](../../stargazers) · [🍴 Fork](../../fork) · [📥 Download](../../archive/refs/heads/main.zip)**

Made with ❤️ by [Kent](https://github.com/KentQi)

</div>