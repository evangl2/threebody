---
description:  定期审查整个写作Harness系统的健康状态， 检查各Agent运作情况、知识库状态、 story进度，并提出优化建议。 由Meta Agent主导执行。
---



## 步骤

### Step 1：读取 Meta Agent 的 Memory 文件
读取以下文件，了解系统当前状态与待处理事项：
```
/knowledge-base/KB05-system/memory/meta-agent-memory.md
```

### Step 2：运行系统健康检查
使用system-health skill。
执行完整系统审计，输出系统健康报告。

### Step 3：知识库状态审计
使用kb-manage skill的审计功能。
检查：
- 积压未处理的缺口
- 内部矛盾
- 过时条目

### Step 4：Story状态审计
读取/story/story-index.md。
检查：
- 待Compact章节数
- 积压的一致性风险点
- 情感弧线追踪是否完整

### Step 5：系统文件审计
检查以下文件是否需要更新：
- .agents/rules/（各rules文件）
- .agents/skills/（各SKILL.md文件）
- .agents/workflows/（各workflow文件）

若发现需要更新的内容，
以【💡Rules/Skills/Workflows更新建议】形式列出，
不自行修改，等待作者确认。

### Step 6：输出综合审计报告

```
━━━ 系统健康审计报告 ━━━
审计日期：[日期]
写作进度：第X章

Agent状态：
  Knowledge Agent：✅正常 / ⚠️[问题]
  Story Agent：✅正常 / ⚠️[问题]
  Writing Agent：✅正常 / ⚠️[问题]

知识库状态：
  积压缺口：X个
  内部矛盾：X个
  过时条目：X个

Story状态：
  最新章节：第X章
  待Compact：X章
  一致性风险点：X个

系统文件状态：
  需要更新的文件：[列表或"无"]

优化建议：[列表，按优先级]

待作者确认的修改：[列表或"无"]
```

### Step 7：执行已确认的修改
若作者在报告基础上确认了某些修改，
由Meta Agent执行或移交相应Agent执行。
每次修改后在KB05-meta-log.md记录。

### Step 8：完成
更新Meta Agent memory文件。
更新KB05-meta-log.md，记录本次审计。

输出完成确认：
"系统审计完成。
下次建议审计时间：第X章完成后。"
