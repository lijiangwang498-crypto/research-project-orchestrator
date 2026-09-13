# research-project-orchestrator 使用说明

中文多阶段项目 Skill：Astra 规划与终审，Luna 低复杂度批量执行，Sol 复杂写作与整合。适用科研、论文、期刊/文献、公众号与自动化项目。

## 包内结构

```text
research-project-orchestrator/
├── SKILL.md
├── README.md
├── references/
│   ├── model-routing.md
│   ├── pdf-to-markdown.md
│   └── domain-workflows.md
└── assets/templates/
    ├── PROJECT_PLAN.md
    ├── PROGRESS.md
    ├── REVIEW_CHECKLIST.md
    ├── TASK_TEMPLATE.md
    └── HANDOFF.md
```

## 使用

在支持个人 Skill 目录的 Codex 环境，把完整文件夹放入该环境配置的 skills 目录（本机惯用位置为 `~/.codex/skills/`）；已有同名版本时先比较，勿直接覆盖。确认环境已发现此 Skill 后，用 `$research-project-orchestrator` 调用。本交付包未修改你的个人 Skill 目录。

在 ChatGPT Work/其他 Agent 中，按界面提供的 Skill 加载功能导入完整包；若没有此功能，可解压后提供 SKILL.md、相关 references 和模板，并明确要求读取执行。单纯上传 ZIP 不代表已安装，且不会自动切换模型。界面不支持读取 ZIP 时提供解压后的 Markdown 文件。

启动提示：

```text
使用 $research-project-orchestrator 推进项目。
目标：〔填目标〕
输入：〔填文件或来源〕
交付：〔填格式和用途〕
约束：〔填必须遵守的条件〕
先建立 PROJECT_PLAN.md 和 PROGRESS.md，然后推进已具备条件的任务。
按 Astra 规划与终审、Luna 批量执行、Sol 写作与整合建议路由，
记录实际模型；无法自动切换时生成 HANDOFF.md。
```

恢复提示：

```text
读取 HANDOFF.md、PROJECT_PLAN.md 和 PROGRESS.md，
核对产物后继续下一项 READY 任务，不重做已验收工作。
```

## 推荐项目目录（在项目中创建）

```text
my-project/
├── PROJECT_PLAN.md
├── PROGRESS.md
├── REVIEW_CHECKLIST.md
├── HANDOFF.md
├── tasks/                 # 按需从 TASK_TEMPLATE.md 复制 T001.md 等
├── inputs/                # 原始文件
├── work/                  # 提取副本、证据表和中间产物
│   └── pdf/               # PDF 按来源 ID 存放 Markdown 和索引
└── outputs/               # 最终交付物
```

计划、进度、审查清单填在项目目录，不修改包内模板。没有文件工具时，可让 Agent 输出同名 Markdown 内容，保存后用于下次交接。

设计依据：模型定位参考 [OpenAI 模型说明](https://learn.chatgpt.com/docs/models)，Skill 结构参考 [OpenAI 构建说明](https://learn.chatgpt.com/docs/build-skills)，核查日期 2026-09-13。具体阶段分工属于本 Skill 的工作策略，模型与工具可用性以实际环境为准。

