---
name: hana-card-templates
description: "70 个视觉风格空壳模板。骨架保留、内容可替换，快速生成风格化卡片。"
profile: card-skill
default-enabled: true
---

# Hana Card Templates

70 个视觉风格空壳模板。骨架保留、内容可替换。

## 字段契约（已逐张实测，70/70 生效）

| 字段 | 必填 | 落点 |
|---|---|---|
| `title` | 是 | 各卡的**主标题位**。有些卡原字段叫 `heading` / `label` / `header_title`，已全部改为接受 `title` |
| `body` | 是 | 各卡的**正文本位**。部分卡落在副标题槽或新追加的正文容器上 |
| 其余字段 | 否 | 保持各卡原有专用字段（`items` / `logos` / `rows` / `reels` 等），不影响 title/body |

`body` 接受：
- 字符串：用 `\n\n` 分段，渲染为多段
- 字符串数组：直接渲染为多段

传 `body` 时会覆盖同名可选字段（如 `subtitle` / `note` / `desc`），因为契约里 `body` 是必填主内容、可选字段是补充。

> 注意：本契约是用 headless Chrome 逐张渲染、比对 DOM 可见文本是否含标记串而验收的（70/70 通过），
> 不是靠读源码推断的。如果你改了任何一张卡的渲染脚本，请重新验收——否则失败会被 `catch` 吞掉，页面照常显示默认样张内容。

## Templates

- `assets/abstract-editorial-blank.card.html` — 抽象编辑海报（P-27）。深黑底、青/品红几何块 + 硬边投影黄块、超大双行标题、四色 chip 条。
  - Required: `title`（大标主行）, `body`（正文段落）
  - Optional: `subtitle`（大标副行）, `kicker`（eyebrow 标签）, `palette`（4 色 hex）, `meta`（右下小字）, `credit`（左下小字）
  - `body` 支持字符串（`\n\n` 分段）或数组

- `assets/airport-blank.card.html` — 机场信息板（L-05）。航班信息风格、等宽字体、时间戳。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/animal-island-blank.card.html` — 动物岛（G-01）。可爱卡通、鲜艳色彩、圆润造型。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/apple-glass-blank.card.html` — Apple 玻璃拟态（B-04）。暗色 backdrop-filter、荧光笔划线动画、四色 chip、蓝色主按钮。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4，Apple 系统四色）, `caption`
  - `body` 可用 `==文字==` 做荧光笔划线高亮

- `assets/blue-blank.card.html` — 深蓝商务渐变（M-01）。蓝色渐变头、白色面板（4 行数据 + 4 色 chip + 描述）、Consolas 页脚。
  - Required: `title`, `body`
  - Optional: `subtitle`, `kicker`, `rows`（≤4 `{label, value}`）, `swatches`（≤4 hex）, `credit`
  - `body` 支持字符串或数组

- `assets/blueprint-blank.card.html` — 蓝图设计图（P-24）。工程蓝图风格、网格线、技术标注。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/brass-balance-blank.card.html` — 黄铜天平（E-04）。学术对比、天平元素、金属质感。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/bulletin-blank.card.html` — 公告栏（P-09）。校园公告栏、纸张排列、钉图元素。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/certificate-blank.card.html` — 成绩证书（P-18）。金色边框、绶带、印章、签名区、GOLD RIPPLE 页脚。
  - Required: `title`, `body`
  - Optional: `titleAccent`, `kicker`, `subline`, `name`, `ribbonLeft`, `ribbonRight`, `certNo`, `date`, `issue`, `sealGrade`, `sealNumber`, `signerLine`, `verifierLine`
  - `body` 富文本可含 `<b>`

- `assets/class-notes-blank.card.html` — 课堂笔记本（P-12）。活页纸 + 装订孔、左侧红批注、右侧横线格、评分圆圈。
  - Required: `title`, `body`（≤4 项）
  - Optional: `date`, `grade`, `annots`（`{title, lines[]}`）, `hints`
  - `body` 每项可含 `<span class="kw">` / `<span class="red">`

- `assets/clean-white-blank.card.html` — 极简白（L-01）。纯白底、极简排版、黑色文字。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/clipping-blank.card.html` — 剪报风（P-04）。报纸剪报、手写标注、胶带装饰。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/comic-blank.card.html` — 漫画风格（G-06）。美漫、对话框、分镜、动感线条。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/cork-board-blank.card.html` — 审讯室软木板（P-22）。棕色软木板、红图钉、3 张便签、红线串联。
  - Required: `title`, `body`（3 张便签）
  - Optional: `footer`
  - `body` 每项可为 `{label, text}` 或字符串；text 支持 `#red 文字 #` 高亮

- `assets/credits-blank.card.html` — 片尾字幕（E-03）。电影片尾、滚动字幕、暗黑背景。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/cyber-blank.card.html` — 黑底霓虹（M-02）。透视网格、扫描线、三色霓虹 chip（青/品红/酸绿）、荧光发光标题。
  - Required: `title`, `body`
  - Optional: `subtitle`, `footer`
  - `body` 数组（≤4）→ 霓虹标签条；字符串 → 发光正文段落

- `assets/cyber-red-blank.card.html` — 赛博红（B-02）。赛博朋克、红色霓虹、城市夜景。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/dark-tech-blank.card.html` — 暗黑科技（B-01）。深色科技、霓虹元素、HUD 界面。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/desk-night-blank.card.html` — 深夜书桌（B-10）。深蓝夜色、暖色台灯、5 个桌面物件、彩色标签。
  - Required: `title`, `body`（5 个物件）
  - Optional: `num`, `subtitle`, `tags`（≤4）, `footL`, `footR`
  - `body` 每项可为 `{label, text}` 或字符串

- `assets/dossier-blank.card.html` — 对决档案墙（P-19）。皮质档案板、A/B 双侧文件卡（红/蓝）、中央 VS、双印章。
  - Required: `title`, `body`（两方观点）
  - Optional: `eyebrow`, `subtitle`, `page`, `caseId`, `duel`, `a`/`b`（`{quote, tag, tagId, evidence, status}`）
  - `body` 富文本：`**文字**` 高亮加粗

- `assets/exam-blank.card.html` — 考卷批改（P-11）。横线纸、红色装订线、4 道题、红印章 + 手写批注。
  - Required: `title`, `body`（4 项）
  - Optional: `subtitle`, `student`, `marks`（`+6`/`-4` 自动切换）, `score`
  - `body` 每项可含 `<span class="ans">` / `<span class="wrong">` / `<span class="correction">`

- `assets/fight-poster-blank.card.html` — 格斗海报（G-07）。格斗游戏海报、对战元素、动态构图。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/filmstrip-blank.card.html` — 电影胶片（E-02）。胶片风格、格状排列、暗房色调。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/freeze-screen-blank.card.html` — 冻结屏幕（B-07）。错误屏幕、蓝色代码、故障感。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/github-dark-blank.card.html` — GitHub Dark 代码窗（M-03）。暗底编辑器、红黄绿信号灯、7 色语法高亮。
  - Required: `title`（文件名）, `body`（代码行）
  - Optional: `subtitle`（主题标签）, `footer`
  - `body` 字符串用 `\n` 分行或数组（≤12 行）；每行支持 `<span class="k|v|s|fn|cm|g|o">` 高亮

- `assets/gradient-dark-blank.card.html` — 深色渐变（B-03）。深色渐变背景、现代简约、优雅排版。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/gray-blank.card.html` — 简约灰阶（M-04）。四阶灰调色带、MONOCHROME 标签、极简排版。
  - Required: `title`, `body`
  - Optional: `subtitle`, `footer`
  - `body` 数组（≤4）→ 色带标签；字符串 → 保留色带 + 下方正文

- `assets/green-blank.card.html` — 森林绿渐变（M-05）。叶片图标、四阶绿调色带、白底描边面板。
  - Required: `title`, `body`
  - Optional: `subtitle`, `footer`
  - `body` 数组（≤4）→ 色带标签；字符串 → 保留色带 + 面板内正文

- `assets/handdrawn-blank.card.html` — 手绘涂鸦（M-06）。米黄纸、手绘线条、彩色涂鸦、手写字体。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/holo-foil-blank.card.html` — 全息收藏卡（B-11）。CSS-3D 透视、星空背景、四种激光面切换、鼠标跟随光谱。
  - Required: `title`
  - Optional: `subtitle`, `tech`, `edition`, `fn`
  - 交互：光标跟随光谱、4 种激光面切换

- `assets/house-blank.card.html` — 家风参考卡（P-29）。衬线中垂标题、3 项指标行、蓝色引文块、浅蓝徽章。
  - Required: `title`, `body`
  - Optional: `items`（≤3 `{label, text}`）, `note`, `caption`
  - `body` 分段用 `<br><br>` 分隔

- `assets/hyperos-lock-blank.card.html` — HyperOS 锁屏（B-06）。手机锁屏、时间显示、极简界面。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/ink-double-blank.card.html` — 墨迹双联（P-03）。黑底米白字与米白底黑字双栏、印章、首字下沉。
  - Required: `titleA`, `bodyA`, `titleB`, `bodyB`
  - Optional: `itemsA`, `itemsB`, `stampA`, `stampB`, `mastL`, `mastR`, `foot`
  - `bodyA`/`bodyB` 支持字符串或数组

- `assets/lecture-blank.card.html` — 讲义（P-08）。大学讲义、手写笔记、重点标注。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/mag-list-blank.card.html` — 杂志列表（P-05）。杂志目录、章节排列、优雅排版。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/magazine-ink-blank.card.html` — 杂志墨色（P-07）。杂志黑白、墨色排版、极简设计。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/magazine-spread-blank.card.html` — 杂志跨页（P-06）。图文混排、优雅排版、阅读感。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/memphis-blank.card.html` — 孟菲斯设计（G-03）。80 年代孟菲斯、几何图形、鲜艳色彩。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/metro-blank.card.html` — 地铁站牌（P-26）。简洁标识、信息层级、公共设计。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/mono-blank.card.html` — 极简黑白（M-07）。纯黑白、等宽字体、高对比度。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/morandi-blank.card.html` — 莫兰迪色系（M-08）。低饱和度配色、柔和渐变、优雅排版。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/news-headline-blank.card.html` — 复古报纸头条（P-01）。超大数字、双栏 headline、红色印章、Consolas 页脚。
  - Required: `title`（`\n` 分隔多行）, `num`（大数字）
  - Optional: `numSmall`, `desc`, `stamp`, `mastL`, `mastC`, `mastR`, `footDate`, `footR`

- `assets/noir-file-blank.card.html` — 黑色电影档案（P-20）。深色纸档、百叶窗投影、金色 accent、红色高亮。
  - Required: `title`, `body`
  - Optional: `subtitle`, `caseId`, `status`, `location`, `filedBy`, `stamp`
  - `body` 支持 `#red 文字 #` 内联高亮

- `assets/ocean-blank.card.html` — 海洋蓝渐变（M-09）。深蓝渐变、波浪纹理、白色面板。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/orange-blank.card.html` — 暖橙商务渐变（M-10）。橙色渐变头、白色面板、4 行数据。
  - Required: `title`, `body`
  - Optional: `subtitle`, `kicker`, `rows`（≤4 `{label, value}`）, `swatches`（≤4 hex）, `credit`
  - `body` 支持字符串或数组

- `assets/photo-memory-blank.card.html` — 照片记忆（P-28）。上图下文、抽象母题 SVG、斜体衬线标题。
  - Required: `title`, `body`
  - Optional: `image`（URL 或 data URL）, `caption`
  - `body` 支持字符串或数组

- `assets/pixel-platform-blank.card.html` — 像素平台（G-04）。8-bit 风格、方块造型、怀旧色彩。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/pos-receipt-blank.card.html` — POS 小票（P-10）。收银小票、热敏纸、等宽字体。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/postcard-blank.card.html` — 明信片风（P-17）。米白纸、左右分栏、虚线分隔、齿孔邮票、圆形邮戳。
  - Required: `title`（TO 标注）, `body`（正文）
  - Optional: `salutation`, `signature`, `date`, `stamp`, `postmark`, `address`
  - `body` 支持字符串或数组

- `assets/purple-blank.card.html` — 深紫神秘渐变（M-11）。紫色渐变头、白色面板、4 行数据。
  - Required: `title`, `body`
  - Optional: `subtitle`, `kicker`, `rows`（≤4 `{label, value}`）, `swatches`（≤4 hex）, `credit`
  - `body` 支持字符串或数组

- `assets/riso-blank.card.html` — Risograph 印刷（P-25）。双色套印、错位效果、复古印刷。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/saas-blank.card.html` — SaaS 仪表盘（L-03）。现代 SaaS、卡片布局、数据可视化。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/scholar-a-blank.card.html` — 学霸笔记本 A（P-15）。米黄横线纸、荧光笔标题、4 色图标行。
  - Required: `title`, `body`（≤4 项）
  - `body` 每项可含 `<span class="k|warn|red|blue|green">`；对象 `{text, kind}`

- `assets/scholar-b-blank.card.html` — 学霸笔记本 B（P-16）。深棕皮革封面、毛笔标题、多色 SVG 行项。
  - Required: `title`, `body`（≤6 项）
  - Optional: `tag`, `subtitle`

- `assets/shelf-blank.card.html` — 书架陈列（L-04）。书架背景、书籍排列、温暖色调。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/signwall-blank.card.html` — 签名墙（E-06）。Logo 排列、金色装饰、仪式感。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/slot-blank.card.html` — 嘉年华老虎机（B-08）。深空底色、三转轮、红色拉杆、旋转动画。
  - Required: `title`, `body`
  - Optional: `subtitle`, `reels`（3 项符号）, `cta`, `coin`
  - `body` 支持字符串或数组

- `assets/spotlight-evidence-blank.card.html` — 审讯室证据聚光（B-09）。黑底金色聚光、径向光柱、虚线证物卡。
  - Required: `title`, `body`
  - Optional: `subtitle`, `evNum`, `tag`, `label`, `value`, `desc`, `footL`, `footR`
  - `body` 支持字符串（`\n` 分行）或数组

- `assets/sticky-blank.card.html` — 便签纸流程（P-14）。米黄板书板、彩色便签、弯曲箭头、S 型流程。
  - Required: `title`, `body`（4 个便签）
  - Optional: `titleAccent`, `titleTail`, `subtitle`, `hand`
  - `body` 每项支持 `{title, desc}` 或字符串

- `assets/swiss-blank.card.html` — 瑞士国际主义（L-02）。网格排版、Helvetica、高对比度。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/tailwind-blank.card.html` — Tailwind 渐变卡（M-12）。深色底、彩色渐变、4 色 chip、玻璃拟态。
  - Required: `title`, `body`
  - Optional: `subtitle`, `kicker`, `rows`（≤4 `{label, value}`）, `credit`
  - `body` 支持字符串或数组

- `assets/tcg-binder-blank.card.html` — TCG 卡牌册（G-05）。集换式卡牌、收藏册布局。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/theater-curtain-blank.card.html` — 剧场幕布（E-01）。红色幕布、舞台灯光、金色装饰。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/topo-blank.card.html` — 等高线地图（P-23）。地形图风格、等高线元素、自然色调。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/toy-blank.card.html` — 玩具盒（G-02）。儿童玩具、鲜艳色彩、卡通元素。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/warm-paper-blank.card.html` — 暖色报纸风（P-02）。双线报头、竖排栏标、两栏正文、首字下沉。
  - Required: `title`, `body`
  - Optional: `headline`, `subtitle`, `kicker`, `footer`（[left, right]）
  - `body` 支持字符串或数组

- `assets/washi-calendar-blank.card.html` — 手账拼贴日历（P-13）。米黄纸、胶带装饰、2×5 日历格、对勾页脚。
  - Required: `title`, `body`（≤10 项）
  - Optional: `accent`, `dateRange`, `note`
  - `body` 字符串用 `·` 分隔 `day`/`label`；对象 `{day, label, flag}`

- `assets/workshop-board-blank.card.html` — 工坊公告板（E-05）。木质公告板、挂牌元素、温暖色调。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

- `assets/wugong-blank.card.html` — 武功秘籍（P-21）。深蓝封面、麻线装订、竖排书法标题、朱批注解、红色印章。
  - Required: `title`, `body`（竖排）
  - Optional: `zhupi`, `seal`, `volume`
  - `body` 用 `\n` 分隔竖排句段

- `assets/zelda-sheikah-blank.card.html` — 塞尔达希卡（B-05）。希卡石元素、幻想色彩、游戏感。
  - Required: `title`, `body`
  - Optional: `subtitle`, `items`（≤4）, `footer`
  - `body` 支持字符串或数组

## How to cast

```js
show_card({
  template: "hana-card-templates/assets/warm-paper-blank.card.html",
  state: {
    title: "报头",
    headline: "主标",
    subtitle: "副标",
    kicker: "栏标",
    body: "第一段。\n\n第二段。",
    footer: ["左下", "右下"]
  }
})
```

## Design intent

Visuals from `style-atlas`; content fields stripped to generic minimum.
