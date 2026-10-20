# 影视镜头AI提示词专家 · 全球前十 LLM｜12 秒 Remotion 动画

日期：2026-10-20　｜　数据快照：2026-10-20　｜　方向：数据动画（代码驱动）  
时长：12s / 360 帧　｜　30fps　｜　1920×1080

> **文件名说明**：文件名里的 `10s` 是 v1 遗留（最初定 10 秒），v3 起已改为 12 秒 / 360 帧——因为说明区四行在 10 秒内读不完。实际工程按 360 帧建。

> **v3 修订（2026-10-20 16:35）**：新增第 3 节「上屏文案与口径声明」，把评测类型、统计口径、取数原因做成常驻字幕与片尾说明区，并重新分配版面空间防止文字挤压。  
> **v2 修订**：补入 DeepSeek-V4.1-Flash-1017（10-17 静默发布，10-19/20 才被收录）；修正条长映射表述（原「压缩映射」实为从 0 起算的线性映射）。

---

## 0. 先定一件事：你要的「提示词」是哪一种

Remotion 是**代码驱动的动画框架**（React + TypeScript），不是文生视频工具。所以「Remotion 的提示词」= **一段交给 AI 编程助手（Claude Code / Cursor / Copilot）执行的工程级指令**，而不是给 Sora 的镜头描述。

> ⚠️ 若你要的是「让可灵/即梦/Sora 生成一段 LLM 排行榜视频」——那类工具做不了准确的数据排版（数字会糊、文字会变形），不推荐。文末附了降级方案。

---

## 1. 关于 DeepSeek：它到底在不在前十？

**结论：按「厂商旗舰去重」算，它在第 9 位；按「原始榜（同厂商可重复）」算，它进不了前十。**

DeepSeek-V4.1-Flash-1017 于 **2026-10-17** 发布，是以 changelog 形式推的静默更新（沿用同一 API 模型串 `deepseek-flash`），10-19~20 才被 Arena 正式收录。所以 10-15 之前导出的任何榜单快照里都没有它——v1 用的就是那份快照，这是漏项的原因。

### 它的真实战绩

| 指标                  | 数值                                | 说明                                      |
| ------------------- | --------------------------------- | --------------------------------------- |
| AA 智能指数 v4.3.2      | **45**                            | 上一版 39，单次 checkpoint 涨 6 分              |
| 开源权重排名              | **并列第 2**                         | 与 GLM-5.3 同为 45，落后 MiMo-V2.6-Pro（46）1 分 |
| Code Arena WebDev   | **1670**                          | **开源第一**，总榜第 12，距 GPT-6 Sol Max 仅 12 分  |
| Agent Arena         | 开源第一，总榜 11                        | 中位任务成本 $0.18–0.20                       |
| Vals Index v2.2     | 总榜第 8，开源第一                        |                                         |
| 架构                  | 552B 总参 / 16B 激活 MoE，1M 上下文，MIT   |                                         |
| 价格                  | $0.30/$1.20 每百万 token，缓存命中 $0.006 | 约为 Kimi K3 的 1/10                       |
| AA-Omniscience 非幻觉率 | 4% → **33%**                      | 提升幅度比智商分更夸张                             |

### 但必须诚实的两点

1. **它没有进综合智能前五。** 45 分只排到第 7–9（三模型并列）。它的「第一」全部是**开源权重范围内**或**特定子榜**的第一，不是全球总榜第一。片子里若说「DeepSeek 全球第一」，属于错误陈述。
2. **原始榜前十的门槛是 52 分。** 因为 Anthropic 一家占了 6 个版本席位（Opus 5.5 / Sonnet 5.5 / Fable 5.1 / Opus 5 …），原始榜前十被它刷屏，DeepSeek 在原始榜里大约第 20 位。

---

## 2. 数据表（最终版 · 厂商旗舰去重）

**来源**：Artificial Analysis Intelligence Index v4.3.2，2026-10-20 快照。分数区间 44–58。

| #  | 模型                           | 厂商        | 指数     | 条长比       | 备注                         |
| -- | ---------------------------- | --------- | ------ | --------- | -------------------------- |
| 1  | Claude Opus 5.5              | Anthropic | 58     | 100%      |                            |
| 2  | Muse Wonder Full             | Meta      | 56     | 96.6%     | 2026-10-12 发布              |
| 3  | GPT-6 Astra                  | OpenAI    | 53     | 91.4%     | 与 #4 同分                    |
| 4  | Gemini 4 Argon               | Google    | 53     | 91.4%     |                            |
| 5  | Grok 4.7                     | xAI       | 46     | 79.3%     | 部分来源记作 SpaceXAI            |
| 6  | MiMo-V2.6-Pro                | 小米        | 46     | 79.3%     | 开源权重第一                     |
| 7  | Qwen3.8 Max                  | 阿里        | 45     | 77.6%     |                            |
| 8  | GLM-5.3                      | 智谱 Z.ai   | 45     | 77.6%     |                            |
| 9  | **DeepSeek V4.1 Flash 1017** | **深度求索**  | **45** | **77.6%** | **开源第一（Code/Agent Arena）** |
| 10 | Step 5 Preview               | 阶跃星辰      | 44     | 75.9%     | 与 Kimi K3 同分，按榜序优先         |

**掉出榜单**：Kimi K3（Moonshot，44 分）——被 DeepSeek 挤到第 11。

**同分并列**：#3/#4 都是 53，#7/#8/#9 都是 45。**必须按上面这个顺序渲染**，不要自己重排。

### 关于条长

条长 = `score / 58`，从 0 起算的线性映射，范围自然落在 75.9%–100%。

代价是：**后 6 名的条长只差 3.4%，肉眼几乎一样长**——因为数据本身就这么接近（第 5 到第 10 只差 2 分）。

**不要去"修"**。人为拉开间距就是造假。处理办法：条长照实画，读数交给数字标签，叙事交给副标题。

---

## 3. ★ 上屏文案与口径声明（本版重点）

### 3.1 为什么必须做这件事

「全球前十 LLM」这个标题本身有歧义，不写清口径，观众会拿自己看到的任何一个榜来对，然后得出「你这个是假的」的结论。三种最常见的误读：

| 误读            | 观众会怎么想                     | 用哪句话挡掉                   |
| ------------- | -------------------------- | ------------------------ |
| 以为是「跑分平均分」    | 「GPT 明明更强，你怎么排第三」          | 写明是 AA 智能指数的加权综合分，不是单项跑分 |
| 以为是「全球所有模型排名」 | 「Claude 4.6 凭什么不在」「Kimi 呢」 | 写明每厂商只取旗舰，同厂其他版本不入榜      |
| 以为是「绝对能力排序」   | 「差 1 分就差一名，太武断」            | 写明同分按榜序、代表该口径不代表绝对能力     |

所以上屏文案要分四块：**评测类型 → 统计口径 → 取数原因 → 数据来源**。

### 3.2 上屏文案（逐字，直接写进代码）

**① 主标题**（12–42 帧逐字升起，之后缩小常驻，不消失）

```
全球前十 LLM
```

**② 副标题第一行 · 说明「是什么评测」**（22–50 帧淡入，5.5 秒）

```
Artificial Analysis 智能指数 v4.3.2
```

**③ 副标题第二行 · 说明「测的是什么」**（46–72 帧淡入，20px / opacity 0.5）

```
10 项基准加权综合分 · 推理 / 知识 / 编程 / 智能体
```

**④ 口径标签 · 说明「怎么算的」**（60–78 帧淡入，18px / opacity 0.45，前面加一个 4px 圆点）

```
口径：每厂商仅取旗舰模型
```

> ②③④ 从出现后**常驻到第 300 帧，绝对不要做退场动画**。这是防误解的核心——观众在任何一帧暂停都能看到口径。

**⑤ 片尾说明区 · 说明「为什么这么算」**（10s 版 252–300 帧；12s 版 300–360 帧，推荐后者）

```
评测类型   Artificial Analysis 智能指数 v4.3.2 —— 10 项基准加权综合分，覆盖推理、知识、编程、智能体
统计口径   每厂商仅取旗舰模型。原榜按模型版本排名，同厂多版本会重复占位，去重后才能横向对比厂商
取数说明   同分按榜序排列；排名仅代表该评测口径，不代表模型绝对能力；本片无任何厂商标注
数据来源   Artificial Analysis · 快照 2026.10.20 · 每厂商取旗舰 · 共 10 家实验室
```

排版：四行，等宽标签列（88px 右对齐）+ 内容列左对齐；行高 1.7；16px；整体 opacity 0.42。  
不用逐行 stagger，整块淡入（252–276 帧），留 24 帧静置供暂停截图。

### 3.3 版面空间分配（防止文字挤压，必须给死数值）

v2 的版面装不下四行说明区，会溢出。改成：

| 区域  | Y 范围      | 高度  | 内容                                |
| --- | --------- | --- | --------------------------------- |
| 上边距 | 0–48      | 48  | 无                                 |
| 标题区 | 48–208    | 160 | 主标题 44px + 副标题 20px×2 + 口径标签 18px |
| 榜单区 | 208–858   | 650 | 10 条 × 条高 56 + 间距 10×9            |
| 说明区 | 858–1000  | 142 | 四行 16px，行高 1.7                    |
| 下边距 | 1000–1080 | 80  | 无                                 |

**因此条高从 v2 的 64px 改成 56px、条间距从 12px 改成 10px、左右边距从 120px 改成 96px。** 这三处不改就一定会溢出。

### 3.4 竖版（9:16）的特殊处理

1080×1920 装不下四行 16px 说明区（在手机上会糊成一片）。竖版改成：

- 说明区拆成 **2 张卡**，在第 240–300 帧依次淡入（每张 30 帧）
- 字号放大到 22px（竖版 16px 相当于横版的 9px，不可读）
- ②③④ 三行仍然常驻，但字号升到 24px

### 3.5 10 秒装不下怎么办（我的建议）

**四行说明区在 10 秒里只有 1.6 秒，读不完。** 两个选择：

| 方案                  | 做法                                                        | 适合                  |
| ------------------- | --------------------------------------------------------- | ------------------- |
| **A · 12 秒发布版（推荐）** | 榜单节奏完全不变（0–300 帧），300–360 帧榜单压到 opacity 0.2 做背景，说明区居中放大淡入 | 视频号 / B站 / 抖音都吃 12s |
| **B · 10 秒严格版**     | 说明区只保留「统计口径」+「数据来源」两行，另两行移到发布文案                           | 有硬性时长限制             |

用户说「10s 左右」，所以 **A 方案（12s）不超范围**，而且能让口径真正被读到。默认给 A。

---

## 4. 主提示词 · 中文版（粘给 AI 编程助手）

```text
你是 Remotion 工程师。用 Remotion 4.x + React + TypeScript 做一个 12 秒、1920×1080、30fps 的
排行榜动画，主题「全球前十 LLM」。数据我写在下面，一个字都不要改，也不要联网抓取。
这个片子的首要目标是「不被误读」，所以字幕和口径说明是硬需求，不许为了画面好看删掉或缩小。

【硬性技术约束】
1. 初始化用 blank 模板：npx create-video@latest（选 blank / TypeScript 最小模板）。
   Remotion >= 4.0，React 18，TypeScript strict。
2. 只允许新增 @remotion/google-fonts 一个依赖。禁止引入 d3、framer-motion、tailwind、gsap、
   任何动画库或图表库——所有动效必须用 remotion 的 spring / interpolate / Sequence 手写。
3. 不使用任何外部图片、视频、音频、Lottie。画面全部由 CSS + SVG + 文字构成。
4. 禁止 Math.random()。需要随机必须用 remotion 的 random(seed) 保证确定性。
5. 禁止 window / document / fetch / Date.now() / setTimeout。渲染必须完全可复现。
6. 在 src/Root.tsx 注册 Composition：id="Top10LLM"，durationInFrames=360，fps=30，
   width=1920，height=1080。
7. 文件拆分：src/Root.tsx、src/Top10LLM.tsx（主时间轴）、src/components/Bar.tsx、
   src/components/Header.tsx（标题+副标题+口径标签）、src/components/Footnote.tsx（片尾说明区）、
   src/data.ts、src/copy.ts（所有文案字符串集中放这里）。
8. 所有 spring / interpolate 都要显式写参数，并给 extrapolateLeft:'clamp'、extrapolateRight:'clamp'。
9. 不留 any、不留 TODO、不留注释掉的废代码。

【数据 · src/data.ts —— 顺序就是排名，不要重排，不要按分数 sort】
const DATA = [
  { rank: 1,  model: "Claude Opus 5.5",        vendor: "Anthropic", score: 58 },
  { rank: 2,  model: "Muse Wonder Full",      vendor: "Meta",      score: 56 },
  { rank: 3,  model: "GPT-6 Astra",           vendor: "OpenAI",    score: 53 },
  { rank: 4,  model: "Gemini 4 Argon",        vendor: "Google",    score: 53 },
  { rank: 5,  model: "Grok 4.7",              vendor: "xAI",       score: 46 },
  { rank: 6,  model: "MiMo-V2.6-Pro",         vendor: "Xiaomi",    score: 46 },
  { rank: 7,  model: "Qwen3.8 Max",           vendor: "Alibaba",   score: 45 },
  { rank: 8,  model: "GLM-5.3",               vendor: "Z.ai",      score: 45 },
  { rank: 9,  model: "DeepSeek V4.1 Flash",   vendor: "DeepSeek",  score: 45 },
  { rank: 10, model: "Step 5 Preview",        vendor: "StepFun",   score: 44 },
];

条长：ratio = score / 58（从 0 起算的线性映射，结果落在 0.759–1.0）。
不要放大差异、不要做分段映射、不要用 rank 反推长度。数据就是这么接近，照实画。

【文案 · src/copy.ts —— 逐字照抄，不许改写、不许省略、不许缩短】
TITLE      = "全球前十 LLM"
SUB_1      = "Artificial Analysis 智能指数 v4.3.2"
SUB_2      = "10 项基准加权综合分 · 推理 / 知识 / 编程 / 智能体"
SCOPE_TAG  = "口径：每厂商仅取旗舰模型"
FOOT_LINES = [
  ["评测类型", "Artificial Analysis 智能指数 v4.3.2 —— 10 项基准加权综合分，覆盖推理、知识、编程、智能体"],
  ["统计口径", "每厂商仅取旗舰模型。原榜按模型版本排名，同厂多版本会重复占位，去重后才能横向对比厂商"],
  ["取数说明", "同分按榜序排列；排名仅代表该评测口径，不代表模型绝对能力；本片无任何厂商标注"],
  ["数据来源", "Artificial Analysis · 快照 2026.10.20 · 每厂商取旗舰 · 共 10 家实验室"],
]

【版面空间 · 必须按这个数值，否则会溢出】
上边距 0–48｜标题区 48–208（高 160）｜榜单区 208–858（高 650）｜说明区 858–1000（高 142）｜下边距 80
条高 56px，条间距 10px，左右边距 96px。
主标题 44px / weight 700；副标题两行 20px / opacity 0.5；口径标签 18px / opacity 0.45（前缀 4px 圆点）
说明区四行 16px / opacity 0.42 / 行高 1.7，标签列宽 88px 右对齐，内容列左对齐。

【时间轴 · 360 帧 = 12 秒，严格按帧号】
- 0–24 帧：背景 #0B0E14 淡入；横向细网格线（#FFFFFF / 8%、1px、间距 96px）opacity 0 → 0.4
- 12–42 帧：TITLE 逐字升起。每字延迟 2 帧，translateY 40→0，opacity 0→1，
  spring({damping:200, mass:0.6, stiffness:120})
- 22–50 帧：SUB_1 淡入
- 40–62 帧：标题块整体缩小到 0.86 并上移到标题区（让出榜单区）
- 46–72 帧：SUB_2 淡入（20px / opacity 0.5）
- 60–78 帧：SCOPE_TAG 淡入（18px / opacity 0.45）
  【重要】SUB_1 / SUB_2 / SCOPE_TAG 从出现后一直保留到第 360 帧，任何一帧都不许退场或变透明
- 60–80 帧：10 条空槽位从画布下方依次滑入（stagger 1.5 帧，translateY 90→0，opacity 0→1），
  空槽底色 #1A1F2B
- 78–258 帧：10 条依次生长，从 rank 10 长到 rank 1（倒序揭晓），每档间隔 18 帧。
  单条用 spring({damping:26, mass:0.9, stiffness:90})。
  生长用 clipPath: inset(0 (100-p)% 0 0) 逐帧裁切，禁止改 width（会导致文字重排抖动）。
  条内模型名、厂商名、条尾分数跟随同一个 spring 进度淡入。
- 180–270 帧：rank 1 条尾加一道 1px 白色扫光（opacity 0.5），从左到右扫过，只扫一次
- 252–276 帧：说明区四行整块淡入（opacity 0 → 0.42），不做逐行 stagger
- 300–330 帧：榜单整体压到 opacity 0.2 并轻微 scale 到 0.96，退为背景
- 300–330 帧：说明区整体放大到 1.35 倍并移到画面正中（字号视觉等效 21.6px），成为主体
- 330–360 帧：完全静止。不许有任何动画、不许有闪烁、不许有扫光
  —— 这 1 秒是留给观众暂停截图的

【视觉规范 · 严格照做】
背景 #0B0E14；主文字 #F2F5FA；次文字 rgba(242,245,250,0.55)
条色：rank 1 唯一强调色 #FF5A1F；rank 2–3 #3B4A66；rank 4–10 #232B3B
字体：Inter（@remotion/google-fonts/Inter），标题 weight 700，条目 weight 500，
      数字 weight 700 + fontVariantNumeric:'tabular-nums'
禁止：渐变、阴影、玻璃拟态、发光、超过 2 个强调色、任何 emoji
禁止：给 DeepSeek 额外加色或额外动效——所有 rank 4–10 视觉一律平等
禁止：把说明区做成滚动字幕或跑马灯——必须定帧可读

【验收标准】
1. npx remotion render Top10LLM out/top10.mp4 一次跑通，无报错、无警告。
2. 在 Studio 里检查第 0 / 60 / 120 / 200 / 300 / 340 帧：
   - 第 340 帧必须能完整读到四行说明区，无溢出、无遮挡、无截断
   - SUB_1 / SUB_2 / SCOPE_TAG 在第 60 / 120 / 200 / 300 帧均可见
   - 同分三条（rank 7/8/9）长度完全一致
   - 第一名颜色唯一
3. 汇报：创建了哪些文件、渲染耗时、有没有任何为了跑通而做的降级。
   特别说明：文案有没有被缩短过。
```

---

## 5. 主提示词 · 英文版（给英文模型 / Cursor 用）

```text
Build a 12-second LLM leaderboard animation with Remotion 4.x + React + TypeScript.
Canvas 1920x1080 @ 30fps, durationInFrames = 360. Composition id "Top10LLM".

The primary goal is that the video CANNOT be misread. On-screen copy and the scope
disclaimer are hard requirements — never delete, shorten or shrink them for aesthetics.

HARD CONSTRAINTS
- Start from the blank template. Remotion >= 4, React 18, TS strict.
- Only one extra dependency: @remotion/google-fonts. No d3 / framer-motion / gsap /
  tailwind / chart libs. Every motion hand-authored with spring / interpolate / Sequence.
- No images, video, audio or Lottie. CSS + SVG + text only.
- No Math.random (use remotion random(seed)), no window/document/fetch/Date.now.
- Files: src/Root.tsx, src/Top10LLM.tsx, src/components/Bar.tsx,
  src/components/Header.tsx, src/components/Footnote.tsx, src/data.ts, src/copy.ts.
- Every interpolate gets extrapolateLeft/Right: 'clamp'. No `any`, no TODOs.

DATA (hardcode in this exact order — it IS the ranking, do not re-sort)
1  Claude Opus 5.5        / Anthropic / 58
2  Muse Wonder Full      / Meta      / 56
3  GPT-6 Astra           / OpenAI    / 53
4  Gemini 4 Argon        / Google    / 53
5  Grok 4.7              / xAI       / 46
6  MiMo-V2.6-Pro         / Xiaomi    / 46
7  Qwen3.8 Max           / Alibaba   / 45
8  GLM-5.3               / Z.ai      / 45
9  DeepSeek V4.1 Flash   / DeepSeek  / 45
10 Step 5 Preview        / StepFun   / 44

Bar length: ratio = score / 58 (plain linear mapping from zero, lands in 0.759-1.0).
Do NOT amplify differences, do NOT use a segmented scale, do NOT derive length from rank.

COPY (verbatim, do not paraphrase or shorten)
TITLE     = "TOP 10 LLMs worldwide"
SUB_1     = "Artificial Analysis Intelligence Index v4.3.2"
SUB_2     = "10-benchmark weighted composite · reasoning / knowledge / coding / agents"
SCOPE_TAG = "Scope: one flagship model per vendor"
FOOT_LINES = [
  ["Evaluation", "AA Intelligence Index v4.3.2 — a 10-benchmark weighted composite covering reasoning, knowledge, coding and agentic tasks"],
  ["Scope",      "One flagship model per vendor. The raw board ranks model versions, so multiple releases from one lab would occupy several slots; de-duplication is what makes a vendor-vs-vendor comparison possible"],
  ["Caveats",    "Ties follow leaderboard order; the ranking reflects this evaluation only, not absolute capability; no vendor branding in this video"],
  ["Source",     "Artificial Analysis · snapshot 2026-10-20 · one flagship per vendor · 10 labs"],
]

LAYOUT (use these numbers or it overflows)
top margin 0-48 | header 48-208 (h 160) | list 208-858 (h 650) | footnote 858-1000 (h 142) | bottom 80
row height 56, gap 10, side margin 96
title 44px/700; sub lines 20px at 0.5 opacity; scope tag 18px at 0.45 (4px dot prefix)
footnote 4 rows, 16px, opacity 0.42, line-height 1.7, label column 88px right-aligned

TIMELINE (360 frames)
0-24    Background #0B0E14 fades in; hairlines (white 8%, 1px, 96px apart) opacity 0 -> 0.4
12-42   TITLE rises character by character, 2-frame stagger, translateY 40->0,
        spring(damping 200, mass 0.6, stiffness 120)
22-50   SUB_1 fades in
40-62   Header block scales to 0.86 and moves up into the header zone
46-72   SUB_2 fades in
60-78   SCOPE_TAG fades in
        IMPORTANT: SUB_1, SUB_2 and SCOPE_TAG stay visible until frame 360.
        Never fade them out, never animate them away.
60-80   10 empty row slots slide up from below, 1.5-frame stagger, fill #1A1F2B
78-258  Rows grow from rank 10 up to rank 1, 18-frame interval,
        spring(damping 26, mass 0.9, stiffness 90), clipPath inset(0 (100-p)% 0 0).
        Never animate width.
180-270 A single 1px white sweep across the rank-1 bar, once
252-276 Footnote block fades in as one block (no per-row stagger)
300-330 List dims to opacity 0.2 and scales to 0.96, becomes background
300-330 Footnote block scales to 1.35x and centres in frame
330-360 Completely static. No animation, no flicker. This second is for pausing
        and screenshotting.

VISUAL SPEC
bg #0B0E14, text #F2F5FA, secondary rgba(242,245,250,0.55)
rank 1 only accent #FF5A1F; ranks 2-3 #3B4A66; ranks 4-10 #232B3B
Inter via @remotion/google-fonts. tabular-nums on all scores.
No gradients, shadows, glassmorphism, glows, emoji. Max 2 accent colors.
No special treatment for DeepSeek. Never turn the footnote into a marquee —
it must be readable on a single frozen frame.

ACCEPTANCE
Frame 340 must show all four footnote rows fully, unclipped and unobstructed.
SUB_1/SUB_2/SCOPE_TAG visible at frames 60/120/200/300.
Rows 7/8/9 identical in length. Report files created, render time, any downgrade,
and explicitly confirm that no copy string was shortened.
```


## 7. 变体矩阵

| 变体                   | 改动                                         | 适用场景              |
| -------------------- | ------------------------------------------ | ----------------- |
| **A · 竖版 9:16**      | 1080×1920、条高 48px、说明区拆成 2 张卡、字号放大到 22/24px | 抖音 / 视频号 / Reels  |
| **B · 卡片翻牌**         | 10 张全屏卡片依次翻入，每张 26 帧                       | 想要单条冲击力           |
| **C · 圆环占位**         | 10 个同心圆弧，中心放当前模型名                          | 发布会片头，读数较差        |
| **D · 竞速重排**         | 条先乱序进入再 swap 到正确位次                         | 需要上一期数据做对比        |
| **E · 棒棒糖图**         | 44–58 公共横轴 + 圆点定位 + 竖线连轴                   | 分数区间窄时唯一既诚实又易读的形态 |
| **F · DeepSeek 叙事版** | 第 240–270 帧给 rank 9 白光脉冲 + 角标「开源第一」        | 面向中文受众            |
| **G · 10 秒严格版**      | 说明区只保留「统计口径」+「数据来源」两行                      | 有硬性时长限制的平台        |

> **F 变体的文案红线**：角标只能写「开源权重第一」或「Code Arena 开源第一」，**不能写「全球第一」**。45 分只排第 7–9。

---

## 8. 失败模式对照表（生成后必查）

| 现象                          | 根因                            | 修法                                              |
| --------------------------- | ----------------------------- | ----------------------------------------------- |
| AI 把数据按分数重新 sort，排名全乱       | 自动加了 `.sort()`                | 明确要求「数组顺序即排名，禁止 sort」                           |
| 字幕被"优化"掉 / 缩短               | AI 觉得画面太满                     | 硬要求「逐字照抄，验收时确认无缩短」                              |
| 说明区溢出画布底部                   | 沿用 v2 的 64px 条高               | 条高改 56、间距 10，版面按 3.3 节给死                        |
| 说明区做成滚动字幕，暂停读不到             | AI 想省空间                       | 明确禁止跑马灯，必须定帧可读                                  |
| 字幕在片尾消失                     | 加了退场动画                        | 明确「常驻到最后一帧」                                     |
| 后 6 名条长几乎一样，以为渲染出错          | 数据只差 2 分                      | 不是 bug。靠数字标签 + 揭晓顺序承担读数                         |
| AI 自作主张放大差异                 | 觉得"不好看"就改映射                   | 禁止分段映射 / 幂函数 / rank 反推                          |
| 条生长时文字抖动 / 重排               | 动的是 `width`                   | 改成 `clipPath: inset()`                          |
| 数字宽度跳动（58→44 对齐歪）           | 缺 `tabular-nums`              | 加 `fontVariantNumeric: 'tabular-nums'`          |
| 渲染帧与预览不一致                   | 用了 `Math.random` / `Date.now` | 换 `random(seed)` + 固定帧计算                        |
| 首尾一闪而过的元素                   | interpolate 没 clamp           | 全部加 `extrapolateLeft/Right: 'clamp'`            |
| 渲染报 `window is not defined` | Node 侧访问了浏览器 API              | 删掉 window/document，字体走 `@remotion/google-fonts` |
| 前排并列被质疑排序                   | 同分按榜序，规则未声明                   | 上屏「取数说明」行已写，别删                                  |

---

## 9. 发布文案（视频下方文字 / 置顶评论，把"为什么"讲透）

屏幕里只能放短句，完整理由放在这里：

```
【前 10 按什么标准排的？】

评测类型：Artificial Analysis 智能指数 v4.3.2。它不是单项跑分，而是把 10 项基准
（推理 / 知识 / 编程 / 智能体）加权汇总成一个综合分，反映模型的整体可用性。
所以某家模型在某一项上更强，在这个榜上未必排名更高——这是加权综合的必然结果。

统计口径：每厂商只取旗舰模型，共 10 家实验室。

为什么这么做？因为原榜是按"模型版本"排的。Anthropic 一家就有 Opus 5.5、Sonnet 5.5、
Fable 5.1、Opus 5 等 6 个版本同时挤进前十，榜单会变成一家公司的内部版本对比，
完全看不出厂商之间的实力格局。按"每家只取最强旗舰"重新取数，才能得到真正的
十强横向对照。

几个可能被质疑的点，先说清楚：
· DeepSeek V4.1 Flash 1017 于 10 月 17 日静默发布（沿用旧 API 模型串，只在 changelog
  提了一句），10 月 19 日才被收录，本片已纳入，位列第 9。它的"第一"指开源权重范围
  第一（Code Arena WebDev 1670 / Agent Arena），不是全球总榜第一。
· Kimi K3 与 Step 5 Preview 同为 44 分，按榜序取 Step 5，Kimi K3 因此屈居第 11。
· 前三名中 GPT-6 Astra 与 Gemini 4 Argon 同为 53 分，按榜序排列。
· 第 5 到第 10 名只差 2 分，条长几乎一样长——这是真实差距，不是作图失误。

数据快照：2026.10.20。排名仅代表该评测口径，不代表模型绝对能力。
```

---

## 10. 生成后必须人工补的清单

- [ ] **文案零缩水校验**：渲染完逐字比对 copy.ts 与第 3.2 节，任何一句被删就返工。
- [ ] **第 340 帧暂停截图**：确认四行说明区完整可读，这是"防误解"的唯一证据。
- [ ] **数据校时**：AA 指数每周更新。DeepSeek 这类静默更新最容易漏，建议直接去 AA 官网按发布时间倒序看新增条目，别只信聚合站。
- [ ] **口径三要素**：榜单名 + 快照日期 + 每厂商取旗舰，缺一不可。
- [ ] **厂商中文名**：中文版用官方中文名（深度求索 / 智谱 / 阶跃星辰 / 小米 / 阿里），本版代码里保留英文避免编码问题，上屏前替换。
- [ ] **音频**：静音出片，BGM 后期叠，鼓点对齐第 78 帧。
- [ ] **平台封面**：另出 1080×1440 静态帧（取第 340 帧说明区，比榜单封面更有信息量）。
- [ ] **合规**：「不代表绝对能力」这句必须保留，这是免责核心。

---

## 11. 降级方案（如果你坚持要文生视频工具）

数据层必须留在 Remotion，只有背景层可以交给文生视频：

```text
Cinematic abstract data visualization background, 12 seconds, 16:9. Slow drifting
particles and thin light streaks over a deep navy-black void (#0B0E14). Subtle camera
push-in, shallow depth of field, film grain. Cool monochrome palette with a single warm
orange light source at the lower third. No text, no letters, no numbers, no logos,
no people, no UI elements. Loopable, seamless.
```

负向：`no text / no letters / no numbers / no watermark / no logo / no faces / no morphing / no flicker`

> 禁文字的原因是文生视频工具**必然会把文字画烂**——所有字必须留在 Remotion 层。

---

## 12. 数据来源与可信度分级

| 结论                            | 来源                             | 可信度               |
| ----------------------------- | ------------------------------ | ----------------- |
| DeepSeek 1017 AA 指数 45 分      | AA 官网 + 第三方复述一致                | 高                 |
| Code Arena WebDev 1670 / 开源第一 | Arena 官方 + 凤凰科技 / 搜狐 / 鞭牛士交叉验证 | 高                 |
| Agent Arena 开源第一 / 总榜 11      | Arena 官方 + IT之家                | 高                 |
| AA 指数为 10 项基准加权综合             | AA 方法论文档 + 多方复述                | 高                 |
| 各模型具体分值                       | AnyRank 聚合，2026-10-18          | 中（聚合站，需与 AA 官网复核） |
| 同分模型先后顺序                      | 榜单默认序                          | 低（榜单可能随时微调）       |

*本提示词面向 Remotion 4.x 通用口径，具体 API 名称以实际版本文档为准。榜单数据每周变动，发布前务必复核最新快照。*
