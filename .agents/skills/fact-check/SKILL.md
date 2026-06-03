---
name: fact-check
description: Verifies factual claims by cross-referencing the knowledge base and searching the web. Use when a specific fact needs verification, when knowledge base entries conflict with new information, or when story content references historical events that need confirmation. Produces a fact-check report with sources.
---

# Fact-Check · 事实核查

## 职责
核查具体事实的准确性。先查知识库，再查网络。
呈现多来源结果，不自行裁定，由作者判断。

## 核查程序

### Step 1：知识库优先查阅
```
使用kb-search检索相关条目
若知识库有记录：
  → 以知识库内容为基准
  → 记录知识库来源
若知识库无记录：
  → 标注【⚠️知识库缺口】
  → 进入网络搜索
```

### Step 2：网络搜索
搜索来源优先级（由高到低）：
1. 官方文件、政府声明、外交部记录
2. 主流英文媒体（NYT、WP、FT、The Guardian、Reuters）
3. 学术论文和专著
4. 中文官方媒体（用于了解官方立场，标注为官方口径）
5. 其他新闻媒体

搜索语言原则：
- 优先英文搜索
- 涉及中国内部事务补充中文搜索
- 两种语言结果有出入时，两者都记录并标注差异

### Step 3：对比分析
```
若多个来源一致：→ 标注✅确认
若来源有出入：  → 标注⚠️来源矛盾，列出各来源内容
若无法找到：    → 标注？无法核实
```

### Step 4：输出核查报告

```
【事实核查报告】
核查对象：
知识库记录：[内容或"无记录"]
网络搜索结果：
  来源1：[媒体名] [日期] [内容摘要]
  来源2：[媒体名] [日期] [内容摘要]
结论：
  ✅ 确认：[说明]
  ⚠️ 存疑：[说明矛盾所在]
  ❌ 错误：[说明错误内容]
  ？ 无法核实：[说明原因]
建议操作：
  - 更新知识库条目（如需要）
  - 修改故事内容（标注位置，不给具体文字）
```

### Step 5：更新知识库
核查完成后：
- 若发现知识库记录有误，通知Knowledge Agent更新
- 若知识库有缺口，询问作者是否需要补充
- 核查结果记录在KB05-meta-log.md

## 特殊情况处理

### 中国内部信息
中国内部政治信息往往有官方和非官方两种版本：
```
官方口径：[来源：新华社/人民日报等] [内容]
非官方记录：[来源：媒体/学者] [内容]
差异说明：
```
两种版本都呈现，不做立场判断。

### 时效性问题
对于快速变化的事实（如关税数字、外交立场）：
```
⚠️ 时效性提示
此信息可能已过时。
最新查阅日期：
建议定期核查。
```

## 禁止事项
- 禁止自行裁定哪个来源更可信
- 禁止在未核查的情况下将推测标注为事实
- 禁止直接修改故事文件
