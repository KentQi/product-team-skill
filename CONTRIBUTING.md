# 贡献指南

感谢你考虑为 `product-team-skill` 做出贡献！🎉

本项目是一个 Claude Code 技能（Skill），所有贡献都会直接帮助全球的产品开发者和团队更好地协作。

## 📋 目录

- [行为准则](#行为准则)
- [我能贡献什么](#我能贡献什么)
- [如何报告 Bug](#如何报告-bug)
- [如何提出改进建议](#如何提出改进建议)
- [如何提交 Pull Request](#如何提交-pull-request)
- [开发规范](#开发规范)
- [文档约定](#文档约定)

---

## 行为准则

参与本项目即表示你同意遵守 [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)。请在所有互动中保持尊重和专业。

---

## 我能贡献什么

我们欢迎以下类型的贡献：

### 🐛 Bug 修复
- 角色定义冲突或不一致
- 阶段流程逻辑错误
- 文档中的错别字、技术错误
- 模板中的字段缺失

### ✨ 功能增强
- 新增角色定义（如 SRE、数据分析师、增长黑客）
- 新增阶段或质量门禁
- 新增模板（如会议纪要、复盘报告）
- 新增 references 文档（如特定行业应用）

### 📝 文档改进
- 完善现有文档的可读性
- 补充使用示例
- 多语言翻译
- 配图、流程图

### 🌍 翻译
我们欢迎将文档翻译成其他语言。如有兴趣，请先在 Issue 中沟通，避免重复工作。

### 💡 经验分享
- 在 [Discussions](../../discussions) 分享你使用本技能的真实案例
- 提供特定行业（金融、医疗、教育等）的最佳实践

---

## 如何报告 Bug

在提交 Issue 前，请先：

1. **搜索现有 Issues**，确认问题未被报告
2. **更新到最新版本**，确认问题仍然存在
3. **准备复现步骤**：你输入什么、期望什么、实际发生什么

然后使用 [Bug Report 模板](../../issues/new?template=bug_report.md) 创建 Issue，包含：

- **清晰的标题**（如"PM 在 MVP 模式下未正确跳过成本估算"）
- **复现步骤**（一步一步的操作）
- **期望行为** vs **实际行为**
- **环境信息**（Claude Code 版本、操作系统）
- **截图**（如适用）

---

## 如何提出改进建议

使用 [Feature Request 模板](../../issues/new?template=feature_request.md) 创建 Issue，包含：

- **问题背景**：你遇到了什么问题？
- **建议方案**：你希望怎么解决？
- **替代方案**：考虑过哪些其他方法？
- **附加上下文**：行业、规模、相关案例

对于**重大变更**（如新增必选阶段、修改核心工作流），请先在 [Discussions](../../discussions) 发起讨论，等待维护者反馈后再创建 Issue。

---

## 如何提交 Pull Request

### 流程

1. **Fork 本仓库** 到你的 GitHub 账户
2. **从 `main` 创建特性分支**：`git checkout -b feat/your-feature-name`
3. **本地开发**（遵循下方"开发规范"）
4. **提交变更**：`git commit -m "feat: add DATA role definition for AI products"`
5. **推送到你的 Fork**：`git push origin feat/your-feature-name`
6. **创建 Pull Request** 到本仓库的 `main` 分支

### 提交信息规范

我们遵循 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/)：

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Type 类型**：

| Type | 说明 |
|------|------|
| `feat` | 新增功能（角色、阶段、模板） |
| `fix` | Bug 修复 |
| `docs` | 文档变更（不影响功能） |
| `refactor` | 重构（不新增功能也不修复 Bug） |
| `style` | 格式调整（不影响代码含义） |
| `test` | 添加或修改测试 |
| `chore` | 构建过程或辅助工具变更 |

**示例**：

```
feat(roles): add SRE role definition

- Add SRE role to extended team
- Define responsibilities for monitoring and incident response
- Update agent-roles.md and SKILL.md index

Closes #123
```

### PR 检查清单

提交 PR 前，请确认：

- [ ] 代码/文档已通过本地检查
- [ ] 已更新相关 references 文档
- [ ] 已更新 [CHANGELOG.md](CHANGELOG.md) 的"未发布"部分
- [ ] 提交信息遵循 Conventional Commits
- [ ] PR 标题清晰（如 `feat: 新增 DATA 角色定义`）
- [ ] 在 PR 描述中关联相关 Issue（`Closes #123`）

---

## 开发规范

### 文件组织

```
product-team-skill/
├── SKILL.md                    # 主入口文档（必读）
├── README.md                   # 项目主页
├── LICENSE                     # MIT 协议
├── CHANGELOG.md                # 版本变更
├── CONTRIBUTING.md             # 本文件
├── CODE_OF_CONDUCT.md          # 行为准则
├── SECURITY.md                 # 安全策略
└── references/                 # 参考文档
    ├── agent-roles.md
    ├── quality-gates.md
    ├── tools-and-templates.md
    ├── risk-management.md
    ├── resource-constrained.md
    ├── knowledge-management.md
    └── troubleshooting.md
```

### 修改 SKILL.md

`SKILL.md` 是 Claude Code 加载的核心文件，遵循以下原则：

1. **保持精炼**：避免过度细节，复杂内容放到 `references/`
2. **结构稳定**：核心结构（执行摘要 → 触发条件 → 团队架构 → 工作流 → 各阶段 → 门禁 → 约束）不要轻易变动
3. **风格一致**：使用表格、代码块、emoji 标识符（🚦 / ⚙️ / ⚠️ 等）
4. **一句话原则**：每条规则尽量简洁，便于 LLM 理解

### 修改 references/

每个 references 文件应有：

- **清晰的标题和摘要**
- **表格 / 列表 / 流程图**（避免大段文字）
- **可直接复用的模板**（如有）
- **互相引用**（用相对路径链接其他文档）

### Markdown 风格

- 使用 ATX 风格标题（`#`）
- 代码块标注语言（` ```bash `、` ```yaml `）
- 表格对齐使用 `|` 分隔
- 链接使用相对路径（`[agent-roles.md](references/agent-roles.md)`）
- 必要时使用 emoji 增强可读性

---

## 文档约定

### 角色命名

- 使用大写英文缩写：`PM`、`ARCH`、`UI`、`FE`、`BE`、`QA`、`OP`
- 扩展角色：`DEVOPS`、`UX`、`SEC`、`MOBILE`、`DATA`、`BA`

### 阶段编号

- 统一使用 `Phase 0` 到 `Phase 5`
- 门禁使用 `Gate 0` 到 `Gate 5`

### 模式名称

- 标准模式 / Standard Mode
- 资源受限模式 / Resource-Constrained Mode
- MVP 快速验证模式 / MVP Mode

---

## 🔍 评审流程

1. **自动检查**：PR 提交后会自动运行 markdown 语法检查和链接有效性检查
2. **人工评审**：维护者会在 3-5 个工作日内评审
3. **修订**：根据反馈修订后重新提交
4. **合并**：评审通过后由维护者合并

---

## 💬 交流渠道

- **GitHub Issues**：报告 Bug、提出改进
- **GitHub Discussions**：一般性问题、经验分享、想法碰撞
- **Security**：安全问题请遵循 [SECURITY.md](SECURITY.md)，**不要**公开在 Issue 中

---

## 📜 许可协议

提交贡献即表示你同意你的贡献遵循本项目的 [MIT License](LICENSE)。

---

再次感谢你的贡献！🙏