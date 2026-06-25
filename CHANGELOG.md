# Changelog

本项目的所有重要变更都会记录在此文件中。

格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，
版本号遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

---

## [3.0.0] - 2026-06-25

### 重大重构

- **完整重写 SKILL.md**：从单一文档重构为"主文档 + references/"分层结构
- **新增 references/ 目录**：将原本堆叠在 SKILL.md 中的细节内容拆分为 7 个独立参考文档
- **references 文档清单**：
  - `agent-roles.md` —— 7+N 角色完整定义
  - `quality-gates.md` —— 质量门禁配置
  - `tools-and-templates.md` —— 工具与模板
  - `risk-management.md` —— 风险管理
  - `resource-constrained.md` —— 资源受限模式
  - `knowledge-management.md` —— 知识管理
  - `troubleshooting.md` —— 故障排除

### 内容增强

- 强化"模式选择必须由用户确认"的原则，避免 PM 自动默认
- 完善决策树（11 个澄清问题）
- 完善三种模式的对比和适用场景
- 完善质量门禁的例外处理和渐进式验收规则
- 完善冲突解决机制（4 级升级路径 + ADR）
- 完善技术债务管理（新债不增、旧债渐还、10-20% 工时偿还）

### 开源基础设施

- 新增 `README.md`（开源项目主页）
- 新增 `LICENSE`（MIT 协议）
- 新增 `CONTRIBUTING.md`（贡献指南）
- 新增 `CODE_OF_CONDUCT.md`（社区行为准则）
- 新增 `SECURITY.md`（安全漏洞报告）
- 新增 `CHANGELOG.md`（版本变更记录）

---

## [2.x] - 历史版本

历史版本主要包含：

- 7+N 角色定义与协作机制
- Phase-Gate 工作流（Phase 0 → 5）
- 质量门禁控制（每阶段出口检查）
- 风险、成本、技术债务管理
- 三种运行模式（标准 / 资源受限 / MVP）

详见 [Git 历史](../../commits/main)。

---

## 版本说明

- **主版本号（Major）**：不兼容的重大重构或工作流变更
- **次版本号（Minor）**：向后兼容的新增角色、阶段、模板
- **修订号（Patch）**：向后兼容的 Bug 修复、文档完善