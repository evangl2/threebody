---
name: style-check
description: Checks language style, narrative voice, and tonal balance in story passages. Use after the author submits a passage for review, to verify that the writing maintains the established oral history style, correct narrator voice, appropriate body description usage, and proper balance between serious and light-comedic tones.
---

# Style-Check · 语言风格与阶段心境检验

## 职责
以 [KB04-style.md](file:///a:/Writing/threebody/knowledge-base/KB04-story-settings/KB04-style.md) 为**唯一事实来源 (Source of Truth)**，检验故事段落的叙事声音与生命姿态是否符合人物所处阶段的特定心境。
标注声音漂移与时代干扰，不直接提供替换文字，不做价值判断。

## 前置读取（每次执行前必须）
每次执行风格检验前，必须实时读取并研读：
```
/knowledge-base/KB04-story-settings/KB04-style.md
```
严禁依赖记忆，必须从文件中拉取对应阶段的“心境与姿态”以及“黄金样本”作为对标标尺。

## 核心检验程序

### Step 1：确定当前阶段心境 (Identify active Phase)
*   读取故事段落，判定或根据作者指示，确认当前段落属于 `KB04-style.md` 中的哪一张 **Mindset Card** (例如：`Phase-01 晚年回溯` 或 `Phase-02 1985青葱`)。

### Step 2：心境漂移审计 (Mindset Drift Audit)
对照选定的心境卡，评估叙事声音是否出现声轨漂移：
*   在青春阶段 (Phase-02) 审计：是否存在过于抽离、冷酷、透视历史结局的老年小夏腔调？
*   在晚年回溯 (Phase-01) 审计：是否存在过于年轻粘稠、撒娇、或廉价的小资产阶级抒情？

```
⚠️ 心境漂移警告：[具体段落位置]
心境类型：[当前应遵循的Phase]
漂移描述：[指出声音中混入了何种冲突的声音频率]
```

### Step 3：语言纯净度审计 (Linguistic Purity Audit)
*   检查是否存在任何现代网络用语、现代高频社交词汇，或严重破坏1985/晚年时空特有质感的生硬词汇。
*   检查是否存在脱离角色视角的、生硬塞入的全知学术概念与象征说教词汇。

```
⚠️ 词汇/时代干扰：「[具体词组]」[位置]
问题性质：现代网络用语/学术说教/全知视角干扰
```

## 输出报告格式

检验完毕后，直接输出极简的风格报告：

```
【风格心境检验报告】
检验段落：[章节与位置]
对照心境卡：[Phase-XX]

1. 心境合拍度 (Mindset Resonance)：✅ 契合 / ⚠️ 漂移如下
   [具体描述，指出其与目标心境的感官温差或态度漂移]

2. 语言纯净度 (Linguistic Purity)：✅ 纯净 / ⚠️ 干扰如下
   [列出破坏时代感或语感真实性的具体词汇]

💡 语感热身与微调方向：
[仅指出情感温度或叙事视线的微调朝向，绝不给出具体的改写文本]
```

## 禁止事项
- 严禁提供具体的改写替换文字。
- 严禁设立死板的字数比例或句法公式公式。
- 只做心境与语感对焦的协助，严绝对作者的创作风格进行价值评判。
