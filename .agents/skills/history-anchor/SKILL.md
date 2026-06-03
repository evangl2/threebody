---
name: history-anchor
description: Verifies historical accuracy of story content. Use when a passage references real historical events, locations, meetings, dates, or political contexts. Cross-references against the timeline knowledge base and flags deviations from historical record without judging whether the deviation is intentional.
---

# History-Anchor · 历史锚点核查

## 职责
核查故事内容中涉及的真实历史元素是否准确。
标注虚构成分与史实的偏离点。
不评价偏离是否应该存在——那是作者的创作决定。

## 前置读取
根据段落涉及的时间段，读取对应的时间轴文件：
```
/knowledge-base/KB01-timeline/KB01-pre-2012.md
/knowledge-base/KB01-timeline/KB01-2012-2016.md
/knowledge-base/KB01-timeline/KB01-2017-2020.md
/knowledge-base/KB01-timeline/KB01-2021-2024.md
/knowledge-base/KB01-timeline/KB01-2025-present.md
```

## 检验程序

### Step 1：识别所有真实历史元素
扫描段落，列出所有涉及现实的元素：
- 具体日期和年份
- 真实地点和空间
- 真实历史事件
- 真实人物的姓名和职位
- 政治机构和组织
- 公开声明和话语

### Step 2：逐一核查

对每个历史元素：
```
QUERY KB01 [对应时间段] [关键词]
```
若知识库有记录：对比段落内容与知识库记录
若知识库无记录：标注【⚠️知识库缺口】，通知Knowledge Agent

### Step 3：空间细节核查
涉及特定地点时，额外核查：
- 该地点在该时期是否存在
- 空间布局细节是否有已知记录
- 该地点对应的政治和情感意涵
  （参照KB01中的空间记录和KB02人物档案）

### Step 4：时间关系核查
- 事件发生的顺序是否与时间轴一致
- 同期发生的其他事件是否影响人物状态
- 人物在该时刻的实际历史位置是否正确

### Step 5：输出核查报告

```
【历史锚点报告】
检验段落：[位置描述]
故事时间点：
调用知识库：[文件路径]

涉及的历史元素：
  1. [元素]
  2. [元素]

核查结果：
✅ 符合史实：[描述]
⚠️ 偏离史实：
  位置：[段落位置]
  史实记录：[知识库内容]
  段落内容：[段落描述]
  （不评价是否应该偏离）
？ 无法核实：[说明原因]
⚠️ 知识库缺口：[描述缺失内容]

💡 可补充的史实细节：
  [供作者选用的相关史实，不要求使用]
```

## 特殊情况

### 刻意的历史虚构
如果某个偏离明显是作者的虚构设定（如改变了会面地点），
只标注偏离，不重复标注，不追问原因：
```
⚠️ 偏离史实（可能为虚构设定）：[描述]
```

### 模糊的历史记录
某些历史细节（如私下谈话内容）本身就没有公开记录：
```
？ 历史记录空白：[描述]
此为合理虚构范围，无法核查。
```

## 禁止事项
- 禁止评价作者对史实的处理方式是对是错
- 禁止直接修改故事文件
- 禁止将知识库缺口当作史实错误处理
