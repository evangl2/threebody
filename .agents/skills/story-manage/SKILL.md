---
name: story-manage
description: Manages the story folder including archiving new chapters, updating story-index.md, tracking character states across chapters, and maintaining the overall story structure. Use when a new chapter is completed, when story-index needs updating, or when character state tracking needs to be refreshed.
---

# Story-Manage · 故事文件夹管理

## 职责
管理/story/文件夹的结构和内容。
维护story-index.md作为故事的导航系统。
追踪人物状态随时间线的推进。

## 管理范围
```
/story/
├── story-index.md          所有章节的结构性摘要与目录导航（我维护并写入）
├── character-states.md     核心人物物理与政治状态追踪（我维护并写入）
├── narrative-arcs.md       情感与细节生命周期弧线追踪（我维护并写入）
└── [章节文件].md           作者创建，我协助归档
```

## Story-Index.md 结构规范

```markdown
# 故事主索引 (Story Master Index)

## 🧭 故事分流与子简档导航 (Navigation Directory)
* **📂 角色空间与肉身状态**：👉 [character-states.md](file:///a:/Writing/threebody/story/character-states.md)
* **📂 情感弧线与细节流变**：👉 [narrative-arcs.md](file:///a:/Writing/threebody/story/narrative-arcs.md)

## 1. 章节大纲与 Compact 记录 (Chapter Chronicles)
| 章节 | 标题/简述 | 故事时间点 | 状态 | 备注/Compact 摘要 |
```

## Character-States.md 结构规范

```markdown
# 核心人物状态追踪 (Character States)

## 核心角色状态追踪
### [人物姓名]
- **年龄**/健康/空间位置/家庭与政治处境
- **物理快照**与心理成长轨迹
```

## Narrative-Arcs.md 结构规范

```markdown
# 情感弧线与细节流变追踪 (Narrative Arcs & Detail Tracker)

## 1. 情感关系追踪
- [关系对名称]：[情感线索发展描述]

## 2. 关键细节与叙事价值追踪 (Key Details & Narrative Value Tracker)
| 关键细节 | 出现位置 & 累计频次 | 每次出现的叙事价值与美学意义 | 当前生命状态与使用约束 |
```

## 新章节归档程序

作者完成新章节后调用此skill：

```
Step 1: 读取新章节内容
Step 2: 提取本章的物理与情感状态快照，以及关键物理细节的使用频次。
Step 3: 在 story-index.md 中新增本章的大纲与章节目录条目。
Step 4: 在 character-states.md 中更新各相关角色在当章时间点下的物理年龄与状态特征。
Step 5: 在 narrative-arcs.md 中更新情感弧线及细节生命周期（记录其是否处于沉睡/封存状态）。
Step 6: 检查并记录新的一致性风险点，汇报给 Meta Agent。
```

归档完成报告：
```
【章节归档完成】
章节：第X章
文件：[文件名].md
已更新 story-index.md、character-states.md 和 narrative-arcs.md：
  - 新增章节目录条目 ✅
  - 更新人物物理/政治状态追踪 ✅
  - 更新细节与情感生命周期追踪 ✅
⚠️ 新发现的一致性风险点：（如有）
```

## 全文一致性审计程序

```
Step 1: 读取 story-index.md 中的所有章节目录与时间表。
Step 2: 读取 character-states.md 和 narrative-arcs.md，建立物理与情感细节时间线。
Step 3: 检验人物状态的时间连续性（年龄推进、地标以及政治处境是否与时间轴吻合）。
Step 4: 检验女翻译状态与细节生命周期的连续性（如细节是否在饱和沉睡状态下被违规使用）。
Step 5: 输出审计报告。
```

```
【全文一致性审计报告】
审计范围：第X章至第X章
审计日期：

人物时间线问题：
女翻译状态问题：
情感弧线断裂点：
建议优先处理：
```

## 禁止事项
- 禁止修改作者的章节文件内容
- 禁止删除任何章节文件
- 禁止修改知识库文件
- 禁止修改.agents/文件夹内容
