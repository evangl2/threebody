---
name: kb-search
description: Searches the knowledge base for specific information. Use when the agent or author needs to retrieve facts, character details, historical events, timeline entries, symbolism records, or story settings from the knowledge base. Activate when the task requires referencing existing project materials before writing or making judgments.
---

# KB-Search · 知识库检索

## 职责
在知识库中检索指定信息，为写作、检验和核查任务提供材料支撑。

## 知识库目录结构
```
/knowledge-base/
├── KB01-timeline/
│   ├── KB01-pre-2012.md
│   ├── KB01-2012-2016.md
│   ├── KB01-2017-2020.md
│   ├── KB01-2021-2024.md
│   └── KB01-2025-present.md
├── KB02-characters/
│   ├── KB02-xi-jinping.md
│   ├── KB02-biden.md
│   └── KB02-trump.md
├── KB03-symbolism/
│   ├── KB03-xi-narrative.md
│   ├── KB03-biden-narrative.md
│   └── KB03-trump-narrative.md
├── KB04-story-settings/
│   ├── KB04-translator.md
│   ├── KB04-worldbuilding.md
│   └── KB04-style.md
└── KB05-system/
    └── KB05-meta-log.md
```

## 检索步骤

### Step 1：确定检索范围
根据检索关键词判断目标文件：

| 关键词类型 | 目标文件 |
|-----------|---------|
| 历史事件、年份、中美关系 | KB01对应时间段 |
| 人物行为、性格、经历 | KB02对应人物 |
| 话语体系、象征、自我叙事 | KB03对应人物 |
| 女翻译、文风、世界观 | KB04系列 |
| 系统记录、日志 | KB05-meta-log.md |

### Step 2：定位章节
使用markdown heading层级定位：
- `##` 是一级分类
- `###` 是具体条目
定位到具体章节后只读取该章节，不读取整个文件。

### Step 3：输出检索结果

```
【知识库检索结果】
检索词：
目标文件：/knowledge-base/[路径]/[文件名].md
目标章节：##[章节名]
相关内容摘要：
关联条目：（其他相关文件/章节）
```

### Step 4：处理检索失败
若找不到对应条目：
```
⚠️ 知识库缺口
检索词：
未找到对应条目
建议：是否需要Knowledge Agent补充此条目？
```

## 注意事项
- 只读取，不修改任何知识库文件
- 如有多个相关条目，全部列出，由请求方判断使用哪个
- 不对检索结果做价值判断，只呈现材料
