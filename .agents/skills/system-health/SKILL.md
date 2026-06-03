---
name: system-health
description: Monitors and maintains the health of the writing harness system. Use when performing periodic system audits, when proposing updates to agent rules, when coordinating multi-agent tasks, or when updating the meta log. Only Meta Agent should activate this skill.
---

# System-Health · 系统健康与Meta管理

## 职责
监测整个写作Harness系统的健康状态。
管理和优化其他Agent的rules。
维护KB05-meta-log.md。
协调多Agent任务。

## 系统健康检查程序

### 基础检查（每次激活时运行）

```
Step 1: 读取 Meta Agent 的 memory 文件
        knowledge-base/KB05-system/memory/meta-agent-memory.md

Step 2: 检查各 Agent 状态与路由文件健康状况
        - Meta Agent: 检查 memory 中积压的系统任务与未解决的优化建议
        - Story Agent: 检查 story/story-index.md 中的章节索引、一致性问题与 Compact 状态
        - Writing Agent: 检查 story/character-profiles.md, narrative-arcs.md, character-states.md 的完整性
        - Knowledge Agent: 检查知识库缺口与审计记录

Step 3: 读取KB05-meta-log.md
        - 最近的session记录
        - 积压的系统问题

Step 4: 读取/story/story-index.md
        - 当前章节进度
        - 积压的一致性问题
        - Compact状态

Step 5: 快速汇总，若无问题则静默完成
        若发现问题，输出健康警告
```

```
⚠️ 系统健康警告
发现问题：[描述]
建议处理：[方向性建议]
是否需要立即处理？
```

### 完整系统审计（作者要求或每五章触发）

```
Step 1: 运行基础检查
Step 2: 检查各Agent rules文件是否需要更新
        对照实际使用中发现的问题
Step 3: 检查skills是否覆盖所有需要的功能
Step 4: 检查workflows是否仍然合理
Step 5: 统计各skill的使用频率（从meta日志推断）
Step 6: 输出完整审计报告
```

```
【系统健康审计报告】
审计日期：
写作进度：第X章

━━━ Agent状态 ━━━
Knowledge Agent：✅正常 / ⚠️[问题描述]
Story Agent：✅正常 / ⚠️[问题描述]
Writing Agent：✅正常 / ⚠️[问题描述]

━━━ 知识库状态 ━━━
积压缺口数：
未解决矛盾数：
最后审计时间：

━━━ Story状态 ━━━
最新章节：第X章
待Compact章节数：
积压一致性问题数：

━━━ 系统问题 ━━━
Rules需要更新：（如有）
Skills需要调整：（如有）
Workflows需要优化：（如有）

━━━ 优化建议 ━━━
[列表，按优先级排序]

━━━ 待作者确认的修改 ━━━
[列表]
```

## Rules更新程序

发现rules需要更新时（来源：Agent memory建议、系统审计、作者反馈）：

```
Step 1: 分析更新的必要性
Step 2: 起草更新内容
Step 3: 检查对skills和workflows的影响
Step 4: 向作者呈现更新建议（见格式）
Step 5: 等待作者确认
Step 6: 获确认后执行修改
Step 7: 检查并同步更新受影响的skills/workflows
Step 8: 在KB05-meta-log.md记录修改
```

```
【Rules更新建议】
涉及文件：.agents/rules/[文件名].md
章节：##[章节名]

当前内容：
[引用原文]

建议修改为：
[新内容]

修改原因：
影响的Skills：[列表]
影响的Workflows：[列表]

是否批准？
```

## Meta日志维护

每次有Agent被调用的session结束后更新：

```
Step 1: 收集本次session的所有操作记录
Step 2: 按格式写入KB05-meta-log.md
```

日志条目格式：
```markdown
---
日期：YYYY-MM-DD
写作内容：[描述，或"系统维护"]
调用的Agent和Skill：
  - [Agent名] · [Skill名]
  - [Agent名] · [Skill名]
主要发现：
  - [问题或成果]
知识库变动：
  - 新增：[条目]
  - 修改：[条目]
  - 缺口：[条目]
系统变动：
  - [rules/skills/workflows修改记录]
待处理事项：
  - [列表]
---
```

## Agent协调

当一个任务需要多个Agent协作时，
向作者说明建议的执行顺序：

```
【多Agent任务协调】
任务描述：[作者的需求]

建议执行顺序：
1. [Agent名] 使用 [Skill名]：[说明为什么先执行这个]
2. [Agent名] 使用 [Skill名]：[说明依赖关系]
3. [Agent名] 使用 [Skill名]：[说明最终整合]

预计产出：[描述最终输出]
是否按此顺序执行？
```

## 系统优化建议格式

```
【系统优化建议】
优化对象：[Agent/知识库/Skill/Workflow/Rules]
当前问题：[描述]
建议方案：[方向性描述]
预期效果：[描述]
实施风险：[描述或"无"]
是否批准？
```

## 记忆与日志压缩程序 (Compacting)

当触发记忆与日志压缩条件时，执行以下压缩程序：

```
Step 1: 扫描 Meta Agent 的 memory 文件字数与条目数，以及 KB05-meta-log.md 的行数。
Step 2: 对超载的 meta-agent-memory.md 文件，将历史累积的具体偏离记录（如已解决的问题）进行物理归类合并，提炼为 1-2 行长期的“文风/一致性特征画像”（例如：“已克服动漫傲娇词偏离”），重写该文件以清空琐碎的临时待办。
Step 3: 对超载的元日志，保留最近 3 次 session 的完整记录明细；将更早的历史 session 内容进行物理截断，并用一张高密度表格（如“前史 session 版本与纪要演进表”）来替代，大幅缩减文本行数。
Step 4: 校验修改后的文件，确保无非目标区域的内容丢失，完成后在下一 session 向作者报告。
```

## 禁止事项
- 禁止在未获作者确认的情况下修改任何rules文件
- 禁止在未获作者确认的情况下删除任何文件
- 禁止替作者做创作决定
- 禁止直接修改/story/文件夹内容
- 禁止自主执行对系统有结构性影响的操作
