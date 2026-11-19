# vibe development

一套 Claude Code 研发技能：拿到已过评审的 PRD，按团队技术栈出技术方案、写后端、写前端、做提测前的技术测试。

```
PRD（vibe-designing 产出）
  → vibe-development-architect   技术方案（团队技术文档模板）
  → vibe-development-backend     Python 3.12 + FastAPI + SQLModel + SQLite + Alembic
  ∥ vibe-development-frontend    后台 Ant Design Pro + C 端 ReactLynx
  → vibe-development-qa          单元 · 契约 · 集成 · 端到端 · 性能基线 → 技术测试报告
  → 提测，交 vibe-designing-qa 做业务验收
```

## 技能

| 技能 | 角色 | 产出 |
|---|---|---|
| `vibe-development` | 总入口 | 判断阶段、路由；持有共用规范：技术栈、仓库布局、接口契约、错误码 |
| `vibe-development-architect` | 技术架构师 | `docs/技术方案-*.md` |
| `vibe-development-backend` | 后端开发 | 后端代码、Alembic 迁移、根目录 `openapi.json` |
| `vibe-development-frontend` | 前端开发 | 后台与 C 端代码，请求代码由 `openapi.json` 生成 |
| `vibe-development-qa` | 技术测试 | 测试代码、`docs/技术测试报告-*.md` |

## 主要约定

- **接口只有一份真源**：FastAPI 生成的 `openapi.json` 放仓库根目录、随代码提交；前端请求代码由它生成、不手改。
- **一套错误码**：Ant Design Pro 的 `success / data / errorCode / errorMessage / showType` 结构，`errorCode` 用 `<模块>_<原因>` 字符串。
- **SQLite 单机单实例**：需求超出时把问题交给用户，不自行换库或加中间件。
- **后端、前端只交代码**；测试代码与技术测试报告归 qa。
- **自己定的默认值标 🔶、要用户答的标 🔵**，在回复末尾汇总。

## 安装

把 `*.skill`（ZIP）解压到 `~/.claude/skills/` 下，每个技能一个目录。

## 借鉴来源与许可

各技能只借思路、用自己的话写，出处写在各自 `SKILL.md` 末尾的「借鉴来源」：

| 来源 | 许可 |
|---|---|
| tt-a1i/archify | Apache-2.0 |
| Jeffallan/claude-skills | MIT |
| PramodDutta/qaskills | MIT |
| vercel-labs/agent-skills | MIT |
| vercel-labs/agent-browser | Apache-2.0 |
| wshobson/agents | MIT |
| obsidianmd/obsidian-skills（只调用） | MIT |
