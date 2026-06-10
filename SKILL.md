---
name: bazi-ziwei-reading
description: Create or run a Chinese metaphysics consultation workflow using BaZi and Zi Wei Dou Shu. Use when the user wants prompts, analysis structure, or staged questions based on an accurate BaZi chart screenshot from 八字问真 app or https://pcbz.iwzwh.com/#/paipan/index, plus gender and birthplace, including cross-validation, 用神/忌神, 格局, 大运, career, wealth, romance, health, and 2026 离火年 questions.
---

# BaZi And Zi Wei Reading

## Purpose

Help the user turn an accurate 八字问真排盘 screenshot plus gender and birthplace into a staged AI consultation workflow. Keep the tone plain, practical, and framed as traditional culture research or hobby discussion rather than deterministic fortune-telling, medical, legal, or financial advice.

## Required Inputs

Ask for or confirm these before analysis:

- Accurate BaZi chart from 八字问真 app or `https://pcbz.iwzwh.com/#/paipan/index`.
- Screenshot of the chart, preferably including solar/lunar birth time, four pillars, ten gods, hidden stems, luck cycles, and relevant Zi Wei chart if available.
- Gender.
- Birthplace.
- Any known uncertainty: birth time range, daylight saving/timezone concern, adopted calendar conversion, or unclear screenshot text.

If the user only wants reusable prompts, generate the prompts without asking for personal details.

## Workflow

### 1. Chart Preparation

When the user invokes this skill without a chart screenshot, immediately give the online chart link as a clickable Markdown link and ask them to finish the chart first:

```markdown
先去这里排盘：[八字问真网页版](https://pcbz.iwzwh.com/#/paipan/index)

排好后把截图发给我，再补充：
- 性别
- 出生地
- 出生时间是否确定

我会先帮你核对命盘读取信息和性格特征匹配度，再进入用神、忌神、格局、大运和 2026 离火年分析。
```

If the user already provided a screenshot, do not repeat the link unless the screenshot is incomplete. If the screenshot is incomplete or blurry, ask for a clearer screenshot or typed chart data before making specific claims.

Use this intake prompt:

```text
你是精通八字、紫微斗数的传统文化研究者。我以命理爱好者身份咨询。
请结合我的【八字排盘截图 + 性别 + 出生地】，从家庭、事业、姻缘、财富、个人特质、健康六个维度，用大白话做综合分析。
请先说明你从截图中读取到的关键信息，如四柱、日主、十神、藏干、大运或紫微信息；如果截图有看不清的地方，请先指出，不要硬编。
```

### 2. Cross-Validation First

Always run an accuracy check before deep analysis. Ask for personality and feature matching first, then let the user confirm or correct.

Use this prompt:

```text
先不要直接下结论。请先根据命盘描述我的性格、行为模式、家庭氛围、学习/工作习惯、人际关系风格和容易反复出现的状态。
请把每一点写成“可能表现为……”的形式，并标注你依据的是命盘里的哪类信息。
我会逐条核对匹配度；如果我反馈不准，请根据反馈修正后再继续分析。
```

### 3. Basic Output

After validation, ask the model to find the core variables:

```text
在前面核对基础上，请回答：
1. 我的用神和忌神是什么？它们对应到事业、财富、情感上可能有哪些表现？请给具体、可执行的调整建议。
2. 这个命盘算不算成格？如果成格，是什么格局？如果不成格，核心结构是什么？核心优势和短板在哪里？
3. 请按年龄段或年份排一下我的大运走势。哪些阶段适合激进突破？哪些阶段必须稳扎稳打？每个判断请说明依据。
```

### 4. Advanced Questions

Use these after the basic output:

```text
继续从命理结构出发，用通俗语言回答：
1. 命盘里藏着哪些我可能还没发现的天赋？适合往哪个方向发力？
2. 从命理角度看，我现阶段的人生课题是什么？
3. 哪些场景、城市气质、人群、行业或工作方式能让我更容易遇到好运？需要避开哪些坑？
4. 我更适合上班、创业还是搞副业？请推荐几个匹配领域，并说明为什么。
5. 生活中有哪些容易忽略，但能长期改善状态和运势的小细节？
```

### 5. 2026 离火年 Questions

Use these when the user asks about 2026, 离火年, 火运, or借势:

```text
结合我的命盘和当前大运，专门分析 2026 离火年的影响：
1. 今年我该怎么借势搞事业、攒钱、拓展社交？
2. 火运对我的核心影响是什么？需要注意哪些和“火”相关的事，例如情绪、表达、曝光、互联网、电子产品、心火、炎症、冲动消费等？
3. 今年有什么适合我尝试的方向？哪些事情适合主动推进，哪些事情需要保守处理？
请把建议分成“适合做”“谨慎做”“尽量避免”三类。
```

## Output Style

- Use plain Chinese, concrete examples, and practical advice.
- Distinguish “命理推演” from verified fact.
- Avoid absolute claims such as 一定、必然、注定.
- For health topics, give only lifestyle-level observations and advise professional medical help for symptoms or decisions.
- For money, career, marriage, and major life decisions, present ideas as reflection prompts rather than guarantees.
- If screenshot data conflicts with user feedback, prioritize correcting the interpretation instead of forcing the chart to fit.

## Deliverables

Depending on the request, produce one of:

- A copy-ready prompt pack for DeepSeek/Gemini/ChatGPT.
- A staged consultation script with intake, validation, basic output, and advanced questions.
- A cautious interpretation based on the supplied screenshot and user details.
- A refined follow-up prompt based on the user's validation feedback.
