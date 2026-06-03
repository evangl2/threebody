---
name: character-check
description: Checks character consistency in story passages. Use after the author submits a new passage or chapter, when verifying that character behavior, language, physical state, and relationships match the character archives and the historical moment. Also checks the translator narrator's information boundary.
---

# Character-Check · 人物一致性检验

## 职责
检验故事段落中人物的行为、语言、状态、关系
是否与知识库人物档案以及该历史时刻保持一致。
同时检验女翻译的信息边界是否被遵守。

## 前置读取（每次执行前必须）
```
/knowledge-base/KB02-characters/KB02-xi-jinping.md
/knowledge-base/KB02-characters/KB02-biden.md
/knowledge-base/KB02-characters/KB02-trump.md
/knowledge-base/KB03-symbolism/KB03-xi-narrative.md
/knowledge-base/KB03-symbolism/KB03-biden-narrative.md
/knowledge-base/KB03-symbolism/KB03-trump-narrative.md
/knowledge-base/KB04-story-settings/KB04-translator.md
```

## 检验程序

### Step 1：识别段落中的所有人物
列出段落中出现的所有人物及其行为/言语。

### Step 2：确认故事时间点
```
使用kb-search定位该时间点的时间轴条目：
QUERY KB01 [对应时间段]
确认：
- 该时期的中美关系状态
- 三个人物各自的政治处境
- 三个人物各自的年龄和健康状态
```

### Step 3：逐人物核查

针对每个出现的人物：

**语言习惯核查**
- 该人物的标志性词汇和句式是否保持？
- 是否出现了该人物不会用的表达方式？
- 正式场合vs私下场合的语言差异是否体现？

**行为模式核查**
- 该行为符合该人物已知的性格特征吗？
- 该行为符合该人物在该时期的政治处境吗？
- 人物之间的关系状态是否与该时间点吻合？

**身体状态核查**
- 该人物在该时期的年龄和健康状态是否体现？
- 是否有与已知健康记录矛盾的描写？

**象征体系核查**
- 人物使用的意象、隐喻是否符合其象征体系？
- 具身化方向是否正确？

### Step 4：女翻译信息边界核查
```
读取：/knowledge-base/KB04-story-settings/KB04-translator.md
      ##工作位置与信息获取边界

检验：
- 这个信息她能知道吗？（她在场吗？）
- 对拜登/特朗普内心的描写是否标注为推测？
- 是否有她不可能知道的信息被直接陈述为事实？
```

### Step 5：输出检验报告

```
【人物一致性报告】
检验段落：[位置描述]
故事时间点：
调用知识库：[列出文件路径]

━━━ [人物名] ━━━
✅ 符合档案：[描述]
⚠️ 存疑点：[描述问题，不给修改方案]
？ 无法核实：[材料不足，说明原因]

━━━ 女翻译信息边界 ━━━
✅ 在信息范围内：
⚠️ 越出信息边界：[描述位置和性质]
⚠️ 推测未标注：[描述位置]
```

## 判断原则
- 只标注问题，不提供修改文字
- 存疑点要说明是哪条档案记录与段落不符
- 无法核实的情况说明是知识库缺口还是合理虚构范围
- 不对作者的创作选择做价值判断

## 知识库缺口处理
发现检验所需信息在知识库中不存在时：
```
⚠️ 知识库缺口
需要信息：
影响检验：[说明哪个检验项无法完成]
建议：通知Knowledge Agent补充
```
