# 绘约多智能体协作 Playbook（HuiYue Multi-Agent Playbook）

> 一套**经过实战检验的 AI 多角色协作方法论**，来自「绘约」画师约稿管理平台（Brushline-HuiYue）的真实开发过程。

在真实项目中，我们让 5 个 AI 角色（主理人/前端/后端/需求/Bug修复）像一支小团队一样协同开发。这套方法解决的核心问题是：**如何让多个 AI 长期协作一个不断演进的代码库，而不失控、不产生屎山、不互相覆盖。**

## 核心方法论

### 五角色分工（soul/）

| 角色 | 职责 | 文件 |
|------|------|------|
| 一号·主理人 | 门禁：审核、合并、派工、风险控制 | `soul/soul-01-lead.md` |
| 二号·客户前端 | 客户侧所有页面/交互/组件 | `soul/soul-02-client-frontend.md` |
| 三号·后端画师端 | 后端 API、数据库、画师/管理后台 | `soul/soul-03-backend-artist.md` |
| 四号·需求整理 | 把想法变成可验证的需求文档 | `soul/soul-04-requirements.md` |
| 五号·Bug修复 | 审计、修复、代码质量 | `soul/soul-05-bugfix.md` |

### 关键纪律

1. **Soul 只回答三个问题**：我是谁 / 我能做什么不能做什么 / 第一原则。事故教训放 skill，不背在脑子里。
2. **红线放最前**：模型最先看到的最重要。"高风险操作必须操作人确认"这类红线无条件执行。
3. **施工图派工**：派工写成"精确到行号 + before/after 代码"的施工图，执行窗口即使换便宜模型也能照抄执行。
4. **self-report 不可信**：角色说"完成"，门禁必须用工具验证改动真实落地。
5. **合入即删**：派工/交付文件合入后立即清理，comms 目录只留 STATUS + 有效参考。
6. **视觉质量必须显式测量**：视觉相关批次交付必附 before/after 截图，无截图不通过。

### Skills（skills/）

8 个经过 400+ 次实战迭代的技能，沉淀了多角色协作的完整踩坑与模式：

- `multi-role-lead-review-workflow`（主理人：审核/合并/派工/容器重建）
- `multi-role-client-frontend-workflow`（客户前端：EP 覆写/i18n/E2E 模式）
- `multi-role-backend-workflow`（后端：迁移/事务/表退役）
- `multi-role-bugfix-batch-workflow`（Bug 批：诊断/修复/验证）
- `multi-role-requirements-workflow`（需求：拷问/落档/验收标准）
- `commission-platform-architecture`（约稿平台架构）
- `huiyue-browser-regression-testing`（浏览器回归）
- `huiyue-visual-verification`（无 vision 的视觉量化验证）

## 如何使用

1. 把 `soul/` 下的文件作为各角色窗口的 system prompt / 角色定义
2. 把 `skills/` 导入你的 agent 技能库（Hermes: `hermes skills install` 或放入 skills 目录）
3. 按 soul 里的协作接口运转：一号门禁审核、角色独立 worktree、comms 文件流转

> ⚠️ 这是方法论仓库，不含「绘约」平台任何业务代码。业务代码在 [Brushline-HuiYue](https://github.com/AxelBeary/Brushline-HuiYue)（GPL-3.0）。

## 协议

本仓库采用 **CC BY-SA 4.0**（知识共享-署名-相同方式共享）：
- ✅ 可自由使用、修改、分享
- ✅ 必须署名（提及 [AxelBeary/奚怡熊](https://github.com/AxelBeary)）
- 🔄 衍生作品必须同样以 CC BY-SA 共享
