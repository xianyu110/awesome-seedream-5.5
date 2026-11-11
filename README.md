# Awesome Seedream 5.5

> 社区整理的 [Seedream 5.5](https://seed.bytedance.com/zh/seedream5_5) 玩法与公开案例清单。本仓库不是字节跳动、Seed、即梦、豆包或火山引擎的官方项目，也不代表其背书。

[简体中文](README.md) | [English](README.en.md)

当前收录 **80** 条已核验案例（截至 2026-11-11，Asia/Shanghai）。本清单宁缺毋滥：每条都有实际打开过的来源链接，不编造名称、数字或网址。数字与评价均按原文转述，并标明那是官方或作者自述，不是本仓库的独立验证结论。结构化数据见 [`cases.json`](cases.json)。

## 这是什么模型

**Seedream 5.5** 是字节跳动 Seed 团队于 2026-11-09 发布的图像创作模型。官方称有三项核心能力升级：

1. **更稳定的多轮编辑**：非编辑区域像素级保持，消除色彩偏移，降低连续修改中的细节丢失与画质衰减；官方称支持围绕同一作品展开多达 100 轮的持续创作。
2. **原生 RGBA 透明素材生成**：直接输出带 Alpha 通道的透明或半透明图像，精细处理轮廓边缘与透明区域。
3. **质感更自然，文字更清晰**：进一步改善光照、材质与皮肤纹理，减少过度油亮、过曝；对复杂字形与密集小字的还原更加准确。

官方还预告，Seedream 5.5 系列后续将推出 Pro 版本。

官方评测（均来自 2026-11-09 发布博文，不是本仓库的独立验证）：在 MagicArena 上围绕电商、营销、影视、游戏、办公与服装设计六类场景，对比 Seedream 5.0 Pro，官方称生成效果评分与可用率均有提升，其中影视与办公两个场景的可用率达到上一版本的两倍以上。文字结构与真实感的 GSB（Good/Same/Bad）评测中，官方称相对上一版本在文生图、图生图共四项对比中均为正向偏好，其中真实感图生图的 GSB 达 +55.62%；并称在文字结构和文生图真实感方面领先 GPT Image 2.5 Sunburst、Nano Banana 2.1。官方还称，在覆盖中英文及密集小字的评测中，严重文字崩坏率降至 0.4%，轻微文字崩坏率降至 1.7%。社区文章里的 A/B 对照是作者观感，与上述官方数字分开看待。

## 官方链接

| 资源 | 说明 |
| --- | --- |
| [产品页](https://seed.bytedance.com/zh/seedream5_5) | Seedream 5.5 产品与官方演示 |
| [发布博文（2026-11-09）](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5) | 「生成更真实，百轮编辑更稳定｜Seedream 5.5 发布」 |
| [English blog（2026-11-09）](https://seed.bytedance.com/en/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5/) | 同一篇发布文的英文版 |

## 在哪里用

官方给出的体验入口：

1. 即梦网页版-创作-生成/画布-选择Seedream 5.5
2. 豆包App/网页版-图像生成-选择模型Seedream 5.5
3. 豆包工作-技能-Seedream5.5（APPSO 还写到：在对话框输入 `/seed`，再选择 Skill 技能 Seedream 5.5）
4. 火山方舟体验中心-视觉模型-图片生成-Doubao-Seedream-5.5

社区文章（卡尔的AI沃茨、夕小瑶编辑部、向阳乔木等）提到火山引擎 / 火山方舟 API 将于发布当周上线。本仓库未核验公开 API 地址，也不把尚未确认的接口写成已经可用。

价格方面，卡尔的AI沃茨引述当时看到的火山引擎 API 标价：延续输入图加输出图的两段计费，文本 Token 免费；改一张 2K 方图约两毛八，不到上一代 5.0 Pro 的一半，大约是 GPT Image 2.5 High 的三分之一。夕小瑶编辑部也写到编辑一张 2K 图约两毛八，含输入图和输出图。以上均为文章引述，不是本仓库核实过的官方长期定价，具体以火山引擎正式价目为准。

冷逸文中还描述了当时即梦针对新模型的限时福利（例如全员 7 天无限用、会员时长以及同文提到的双十一活动）。那是文章发表时的宣传，本清单不把它当作长期有效的政策。

## 玩法口诀与提示词骨架

下面这些写法来自官方演示习惯和社区文章，尤其是冷逸《即梦Seedream 5.5来了，分享13个超实用的玩法》。标题虽写「13 个玩法」，正文是按能力分组，并没有给出 1 到 13 的命名清单，因此这里不编造 13 条玩法名。

- **编辑句式**：将图中 XX 改成 XX，其他部分保持不变。可以用框选、红圈或编号定位，例如冷逸给出的编辑骨架：将图中（红圈内 / 左上角 / 第 3 个对象）的原状态改为目标状态，其他部分（主体、构图、光影、背景、文字排版）保持不变。
- **透明素材**：即梦可将「透明背景」开关打开（显式）；也可在提示词里写「透明背景」「半透明」「PNG透明底」「无背景」「alpha通道」来唤醒（冷逸文中的隐式写法）。
- **真实感**：先定体裁和整体调性，再写谁在什么场景做什么，以及镜头手法与质感。冷逸强调先写任务再写风格，先定海报、信息图、主视觉等视觉体裁，再补细节。
- **文字**：要把要出现的字放进引号，逐字给全，并写清层级、位置、字体倾向、字重、颜色、对齐和行数。
- **结构优先**：写清位置、层级、构图和模块关系，而不是只堆「高级感」「氛围感」（冷逸）。

冷逸推荐的提示词骨架（原文）：

```
【任务】生成 / 编辑：<一句话目标>
【主体】<谁 / 什么 / 数量 / 状态>
【场景】<环境 / 时间 / 天气 / 空间关系>
【构图】<画面比例 / 版式分区 / 视角 / 景别>
【光影与风格】<光源方向 / 色调 / 质感 / 参考风格词>
【文字】"<逐字内容>" — 位置 / 字体倾向 / 字重 / 颜色 / 对齐 / 行数
【保持项】<不要改变的部分，明确列出>
【排除项】<不要出现的东西>
```

短句式示例（冷逸）：生成一张【体裁】，用于【载体/用途】，【版面结构】，主体是【……】，【光影风格】，文字“【逐字】”放在【位置】。他举的封面例子是：生成一张小红书竖版封面（3:4），用于美妆笔记，上 1/3 纯色留白放标题、下 2/3 为手持产品的手部特写，柔光、浅米色背景，标题“早八不脱妆”。

冷逸还写到目前不支持 4K，在极宽、极高比例的图像里仍会有部分小字模糊。向阳乔木在李清照信息图里也指出，放大 3 倍后「戚戚」「舴艋」等字仍不够清晰。这些是来源中的限制说明，不是「完全无错字」的成功案例。

## 分类一览

| 分类 | 条数 |
| --- | ---: |
| 官方演示 | 26 |
| 多轮编辑 | 9 |
| 透明素材 | 6 |
| 文字与排版 | 14 |
| 真实质感 | 11 |
| 图层拆分 | 2 |
| 参考图融合 | 8 |
| 工作流 | 4 |
| **合计** | **80** |

## 目录

- [官方演示](#official-demo)（26）
- [多轮编辑](#multi-round-edit)（9）
- [透明素材](#transparent-assets)（6）
- [文字与排版](#typography-layout)（14）
- [真实质感](#photorealism)（11）
- [图层拆分](#layer-decomposition)（2）
- [参考图融合](#reference-fusion)（8）
- [工作流](#workflows)（4）
- [如何贡献](#contributing)

<a id="official-demo"></a>

## 官方演示

### 1. 多轮增换室内家具、灯具与装饰，并调整配色摆放

官方产品页在「多轮编辑，始终如一」中展示：逐步添加和替换家具、灯具与装饰，调整配色与摆放，并保持空间透视和光影协调。这是产品页官方演示，不是社区实测。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 2. 多轮调整人物发型、眼镜、服装、背景与桌面道具

官方产品页展示围绕同一人物，多轮调整发型、眼镜、服装、背景与桌面道具，逐步呈现不同造型。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 3. 逐轮调整显示器里贪吃蛇的位置、长度与分数

官方产品页展示：逐轮调整游戏画面中蛇的位置、长度与分数，同时保持显示器和界面布局一致。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 4. 多轮为静物添加水果、花器与花枝

官方产品页展示：逐步添加水果、花器与花枝以丰富静物构图，并保持场景光影协调。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 5. 多轮调整人物发型、妆容与头部装饰

官方产品页另有一组人物演示：多轮调整发型、妆容与头部装饰，逐步呈现不同造型。这是与「服装/背景/桌面道具」并列的产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 6. 多轮调整国画中的花器、枝叶与点缀

官方产品页展示：逐步调整花器、枝叶与画面点缀，以丰富国画构图。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 7. 逐轮更新表盘时间、运动数据与图表

官方产品页展示：逐轮更新表盘上的时间、运动数据与图表，并保持表盘布局和外观一致。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 8. 同一人物连续编辑 100 轮，仍能改戒指与镜框等细小对象

官方发布博文称，围绕同一人物进行了 100 轮连续编辑，每一轮都以前一轮结果为基础。经过服装、配饰与桌面物件的多轮变化后，官方称模型仍能精细修改戒指、镜框等细小对象，并根据人物当前姿态处理配饰与皮肤的接触、遮挡和光影衔接。此为官方演示与官方表述。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 9. 向右奔跑的连续动作图，每张独立透明底

官方产品页在「透明素材，一步生成」中展示：生成一组女孩向右奔跑的连续动作图，每张为独立的透明底图层。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 10. 提取画面中的火烈鸟，输出为独立 RGBA 透明图层

官方产品页展示：提取画面中的火烈鸟，输出为独立的 RGBA 透明图层。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 11. 两组卡通贴纸，元素以外区域均为透明背景

官方产品页展示生成两组卡通贴纸：一组由海洋元素和卡通小猫组成，另一组由动物和植物组成；两组贴纸元素以外的区域均为透明背景。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 12. 毛线缠绕的 “Seedream 5.5” 字标，16:9，字外透明

官方产品页展示：参考图中的质感和写法，生成 “Seedream 5.5”——圆润饱满的无衬线字母，以宝蓝与湖蓝毛线交替缠绕，呈现纤维、绒毛和侧向投影；输出 16:9 横幅，文字以外的区域透明。这是产品页官方演示。官方博文还概括了把参考图中的笔触、色彩与材质用到指定文字、并直接生成透明视觉素材的能力，本条以产品页这一具体示例为准，不另拆一条。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`
- 说明：官方博文中的「文字与材质融合的透明素材」与产品页这一字标示例同属一类能力，不重复建条。

### 13. 蓝色毛绒 3D 角色及三个变体，分别输出为透明底素材

官方产品页展示：先生成一个圆润、大眼睛、短四肢、表情俏皮的蓝色毛绒 3D 卡通角色，再延续这一风格设计三个造型和表情各异的角色，将四个角色分别输出为透明底图片，以便像拼图一样拆分、组合。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 14. 雪鸮羽毛与脚部圆形微距特写，细边框外透明

官方产品页展示：生成雪鸮白色细密羽毛与积雪接触处的圆形微距特写；再放大参考图右侧较小的雪鸮脚，生成浅灰底的圆形微距特写。两张图均配 3 像素深灰细边框，圆外透明。这是产品页官方演示。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 15. 展开双翼的雪鸮透明素材，保留羽间空隙与爪部轮廓

官方发布博文另有一段雪鸮演示：雪鸮展开双翼，层叠的羽毛纹理清晰可见；官方称模型可细致处理翅尖羽毛、羽间微小空隙与爪部轮廓，保留复杂结构，省去后续抠图与边缘修整。这与产品页的圆形微距特写不是同一组画面。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 16. 同一组透明角色素材，在不同场景中做系列画面

官方发布博文称，设计师可以同一组透明角色素材为参考，快速创作这些角色在不同场景中的系列画面；官方称模型会延续原有角色特征与质感，同时支持动作、组合与构图的调整。这是官方演示对「透明素材跨场景复用」的说明。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 17. 夜晚酒吧里坐在酒瓶与玻璃杯之间的白猫

官方产品页「真实质感，细节入微」展示：夜晚酒吧里的白猫坐在酒瓶与玻璃杯之间，采用低机位仰拍与倾斜构图，并以闪光灯、富士 Provia 胶片色彩和颗粒质感呈现斑驳光影。这是产品页官方示例，此处只概括构图与拍摄设定，不照抄整段宣传文案。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 18. 窗边柔光下，父亲抱着熟睡婴儿靠在沙发上

官方产品页展示一组家庭纪实场景：年轻父亲斜靠在深紫灰色布艺沙发上，怀抱安睡的婴儿，右侧窗户透入暖金色自然光。官方博文也提到父亲抱着熟睡婴儿靠在沙发上、窗边柔光落在面部与手臂、暗部仍保留皮肤与织物细节。本条以产品页与博文共同出现的这一官方示例为准。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 19. 南欧街角柠檬黄墙、深紫木门与金属桶中的金黄花朵

官方产品页展示 3:4 竖幅街头摄影：南欧街角的柠檬黄石灰墙、深紫色旧木门与垂落的皇家紫色亚麻布形成几何构图，右下方旧金属桶中盛放金黄色花朵，并写明强烈午后阳光与紫黄互补色。这是产品页官方示例。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 20. 强风中低头看手机的女子，画面整体倾斜约 25 度

官方产品页展示横幅城市街头随拍：一位穿酒红色上衣、浅棕色外套的长发女子低头看手机，强风吹起发丝；整个画面顺时针倾斜约 25 度，人物、建筑、灯杆与路面保持一致的倾斜透视。这是产品页官方示例。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 21. 夏夜小酒馆里两位中老年顾客用餐的纪实快照

官方产品页展示夏夜欧洲社区小酒馆的横幅纪实快照：两位中老年顾客在铺着米白亚麻桌布的餐桌旁自然用餐、不看镜头，玻璃杯、餐具、面包屑与旧木家具保留使用痕迹，暖色吊灯与少量冷色夜光交织。这是产品页官方示例。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 22. 雨后湿润石砖与水洼中的建筑倒影，画面不出现完整建筑本体

官方产品页展示 3:4 竖幅雨后街头摄影：低机位向下拍摄湿润石砖与不规则水洼，古建筑的金色雕花、窗框与柱廊倒映在水中，并写明画面不出现完整建筑本体、人物或车辆。这是产品页官方示例。

- 来源：[https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 23. 回眸看向镜头的女孩人像，逆光中可见发丝与皮肤纹理

官方发布博文在讨论人像质感时展示：女孩回眸看向镜头，面部皮肤纹理清楚可见，肩部高光到暗部过渡自然，散落的发丝在逆光中显现。这是发布博文中的官方示例，与产品页那组酒吧白猫、父亲抱婴等画面分开收录。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 24. 雨中赛车驶过湿润赛道，车后弥漫轮胎扬起的水雾

官方发布博文在场景质感部分写道：雨中赛车驶过赛道，车身与湿润路面映出不同的反光，轮胎扬起的水雾在车后弥漫，远处车辆若隐若现。这是发布博文中的官方示例。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 25. 蓝闪蝶形态结构图解，八组小字中文说明仍可辨认

官方发布博文以一张蓝闪蝶图解展示较小字号下的中文生成：八组图文分别介绍触角、翅脉、翅鳞等细节，官方称局部放大图旁的中文说明字号虽小，笔画较多的汉字依然清楚可辨。这是官方示例；卡尔的AI沃茨后来也自己写过闪蝶图解测试，那一条按作者实测另列。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

### 26. 莎士比亚主题报纸版面，肖像与插图之间穿插英文小字

官方发布博文展示一张以莎士比亚为主题的报纸版面：人物肖像与剧场插图之间穿插着多段英文小字，官方称排布紧凑、清晰易读。这是发布博文中的官方示例。

- 来源：[https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- 作者/机构：字节跳动 Seed 团队
- 日期：2026-11-09
- 来源类型：`official`

<a id="multi-round-edit"></a>

## 多轮编辑

### 1. 复古黑胶咖啡馆真人照连续改 30 轮，并与 GPT Image 2.6 对照

卡尔的AI沃茨以一张细节密集的复古黑胶咖啡馆真人照为底，把 Seedream 5.5 与 GPT Image 2.6 放在同一张图上连续改了 30 轮。演变包括换灯芯绒外套、加金丝眼镜、戴祖母绿戒指与酒红冷帽，再改到桌面换抹茶拿铁、拿钢笔写字、加草莓华夫饼、扎双麻花辫，以及窗外暴雨和鹅毛大雪，最后在第 28 到 30 轮把冷帽、眼镜摘掉，并把头发和工装夹克换回最初状态。作者称，5.5 在整个 30 轮里「改哪只动哪」，例如把冰美式换成抹茶拿铁时几乎只变杯子那一块；Image 2.6 则在未要求修改的区域也跟着晃，到第 17 轮改成雨天后画面越来越油，越来越像厚涂油画。上述对比均为作者观感。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 人和建筑冻结，连续 6 轮只推演时间线与全局光影

同一篇文章里，作者规定画面中的人和街景建筑全部不准动，连续 6 轮只推演时间线与全局光影：清晨 7 点柔光，再到正午 12 点烈日顶光、傍晚 17 点夕阳逆光、19 点雷雨湿地反光、深夜 23 点霓虹灯，最后到凌晨 5 点破晓蓝调薄雾。作者称，5.5 处理暴雨积水里的暖光倒影和深夜霓虹打在侧脸上的冷暖过渡，更接近真实相机的光学质感；Image 2.6 越到后面越像「廉价的卡通游戏滤镜」，湿地反光与人物受光割裂。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 3. 生日猫蛋糕数字从 1 改到 18，只改数字、其余固定

夕小瑶编辑部试了 18 轮：给一只过生日的猫换蛋糕正面的数字，从 1 一直改到 18，下一轮在上一轮结果上接着改；猫咪花色、捧脸姿势、珍珠饰品以及桌上的蜡烛和酒杯都不允许修改。作者称 18 轮下来数字都改对了，双爪、珍珠头饰和项链都没跑。作为对照，作者用 Image 2.6 跑了同样的 18 轮，称数字仍能辨认，但后半段猫脸、毛发和桌布开始出现块状重绘，原本偏暗的烛光场景也越来越亮、越来越暖。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 4. 模特图连改 12 轮试穿，左侧搭配卡小图同步换色

夕小瑶编辑部挑了一张与自己身材比例较接近的模特图做试搭底稿，图左边已有商品搭配卡。上传后先固定人物身份、身形、站姿、手机、房间陈设和光影，每轮只写这次要改的衣物，并在上一轮结果上接着改：先把打底衫换成柔雾蓝、焦糖棕和豆沙粉，同时要求左侧「圆领打底衫」小图换成同款颜色，再试长袖开衫、不同长裤，最后改包的材质和颜色，共 12 轮。作者称上衣、开衫和裤装变化时左侧小图也能跟着更新，人物背后的布局纹丝不动。同样 12 轮里，作者称 GPT Image 2.6 改到开衫后细节开始松动，眼镜大小和开衫版型不稳定；Nano Banana 2 更早出现镜框花纹变化，且左侧搭配卡与身上衣服对不上。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 5. 蒙娜丽莎多轮换装换职业，姿态与纹理几乎不动

APPSO 让蒙娜丽莎肖像画里不断换衣服、换职业，文中列举了程序员、外卖骑手、医生、厨师、宇航员、电竞选手等。作者称整个人物姿态、画面纹理几乎没有改变，只有服装在变化。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 6. 毛坯房一轮轮加地板、电视、空调和茶几，窗外风景与阳光角度保持不变

APPSO 经过一轮轮编辑，将一个都是水泥的毛坯房一点点加上地板、电视机、空调和茶几等，同时要求窗外风景完全不改变，以及阳光从窗外进来的角度保持不变。作者称这些非编辑区域做到了像素级保持。此为作者对其测试的表述。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 7. 店铺照片改中英招牌、清走车辆立牌，并把门上 OPEN 改成 CLOSE

APPSO 用网上找到的一张店铺照片做多轮修改：把招牌翻译成中文、英语，再逐渐移除画面里的自行车、电动车和商品立牌等，并把挂在门上的 OPEN 改成 CLOSE。作者称图片的渐变色背景和商店门廊上的其他元素都没有被改掉；把垃圾桶移除之后，地面上还多出了商店顶部照射过来的灯光。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 8. 即梦画布里北京摇滚圈女孩电梯自拍，再多轮换装且形态/主体不动

向阳乔木按小互建议在即梦画布里先生成「一个长黑发的年轻漂亮北京摇滚圈妹子，在电梯镜子前自拍……右手举手机挡着半张脸」等提示词下的照片，再选第一张继续输入「形态不动，换一套衣服」和「主体不动，换一套差异大的衣服」。作者把结果合成 GIF，称除个别服装画面抖动外，人脸和背景几乎不动。提示词原文见该文。此为作者实测。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 9. 用广为流传的「老黄」皮衣形象做多轮换装测试

向阳乔木写道，「老黄」最近在风口浪尖，一提到就想到皮衣形象，于是也给他换几套衣服，看看不同装扮会不会比一直穿皮衣更帅。这是作者用该公众形象做的换装测试，文中并未声称当事人或相关机构参与或授权。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`
- 说明：作者对广为流传公众形象的换装测试，不代表当事人或机构参与。

<a id="transparent-assets"></a>

## 透明素材

### 1. 3×3 橘猫打工人贴纸，带磨砂玻璃对话框和果冻质感透明素材

卡尔的AI沃茨直接让 Seedream 5.5 生成一套 3×3 排列的橘猫打工人表情包贴纸，还带半透明磨砂玻璃对话框，以及有点 3D 果冻质感的贴图素材。作者称生出来就是带透明通道的 PNG，可直接使用，而不必再另找抠图工具。此为作者实测。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 即梦画布里把 10 张猫照片提取为独立透明图层

夕小瑶编辑部在即梦画布里放入 10 张原图作为同一个生成节点的参考，模型选 Seedream 5.5、分辨率选 2K，把输入框下方的背景选项切成「透明背景」，并提示「分别提取10张照片中的猫咪，生成独立图层，主体之外为透明图层」。作者称猫咪从原来的环境中分离出来，黄色小帽、围兜和各自花色都保留下来；不过黑白猫下方还带着一小截猫爬架横板，作者注明不影响大局，后期排版可以再处理。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 3. 把抽出的猫咪透明素材做成收藏票框页和迷你杂志封面

拿到上一组猫咪透明素材后，夕小瑶编辑部把它们放进不同背景：给每只猫一个票框，加上票齿、面值和邮戳，底色统一成奶油色纸张，看起来像一本小收藏册；再把同一批素材做成迷你杂志封面，每只猫一张，加上刊名、不同底色和栏目文字，再拼成合集。作者称两套版式风格不同，但小帽、衣饰这些识别点都保留了下来。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 4. 参考动作精灵图为角色出 4×4、16 帧透明格子，再切帧做成 GIF

夕小瑶编辑部把一张战斗动作精灵图作为图 1、想做的角色作为图 2 放进画布，背景仍选「透明背景」，提示「参考图1的动作安排，为图2的角色制作128px简化像素风精灵图，4×4排列、共16帧。准备、出拳、踢腿和受击各占4帧，背景透明。」作者称 Seedream 5.5 按 4 列 × 4 行出了 16 个透明背景动作格，到这一步生图模型的工作就做完了。随后作者把切帧和合成交给本地安装的 DeepSeek Harness 跑 Python：切成 16 张 PNG，再按每帧 100 毫秒、共 1.6 秒无限循环合成透明底 GIF。GIF 这一步不是 Seedream 完成的。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`
- 说明：切帧与 GIF 合成为本地 DeepSeek Harness 跑 Python，不是 Seedream 本身。

### 5. 合拍照片转 chibi 粗白边透明贴纸，作者称约 62% 区域完全透明

APPSO 上传一张合拍照片，把人物转成 chibi 贴纸风格，得到带粗白描边、真透明背景的 RGBA PNG。作者称约 62% 区域完全透明，尺寸合适，可直接当贴纸或叠加到其他画面上，并演示把贴纸贴到 T 恤上；同样的方法也适用于宠物，拍一张宠物照转成可爱 chibi 风格透明贴纸。约 62% 这一数字是作者对其生成结果的表述。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 6. 显式开关或提示词唤醒，生成并提取透明素材再与场景合成

冷逸说明 RGBA 支持显式和隐式两种用法：显式是在即梦对话框旁打开「透明背景」；隐式是在提示词中提及「透明背景、半透明、PNG透明底、无背景、alpha通道」，就会生成带 alpha 通道的全透明或半透明图像。作者称 Logo、图标、UI、商品、物品、人物和表情包都可以生成，半透明（玻璃杯、透明包装、薄纱）是更难的情况；除了文生图生成，也可以图生图提取，并录屏演示把透明素材与其他场景结合。文中配图均由作者用 Seedream 5.5 生成。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

<a id="typography-layout"></a>

## 文字与排版

### 1. 手持精粹水海报改 6 轮，表盘英文与瓶身「澄光焕肤精粹水100ML」对照

卡尔的AI沃茨用手持精粹水海报做了 6 轮迭代，重点看瓶身纸质标签上的英文 LUMIÈRE 和一行很小的中文「澄光焕肤精粹水100ML」，并对照手表上一直保留到第五轮的英文小字。作者称，Seedream 5.5 的表盘样式和表盘下方一行文字基本与原图一致、没有出现模糊，Image 2.6 的表盘细微图案和下方文字已经模糊；到第 6 轮加完水珠后，Image 2.6 瓶身上的小字几乎糊到看不出是什么字，而 5.5 隔着阳光折射和瓶身水珠，这几个小字依然端正。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 苏打汽水电商品报与 Image 2.6 对照字体和卖点气泡

卡尔的AI沃茨用同一份提示语分别让 Seedream 5.5 和 Image 2.6 跑苏打汽水电商海报。作者更看好 5.5：称它不会整张海报只用一种字体，还会自己添加一些 logo 和小标题，半透明卖点气泡也更有光泽感；而 2.6 的卖点部分又用上「标准 AI 粗体」，还把卖点分成两行，不对称感让作者觉得难受。此为作者审美判断。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 3. 带手撕纸和 8 个手绘打卡点的游园地图海报

卡尔的AI沃茨单用 Seedream 5.5 跑活动海报，其中一张是带手撕纸和 8 个手绘打卡点的游园地图。作者称松弛感拉满，每个气泡框里的小字都清清楚楚。此为作者对其生成结果的描述。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 4. 美术馆特展冷感网格海报，含红蓝丝网错版套印细节

同一组活动海报里，作者还跑了一张美术馆特展的冷感网格排版，称纸张纤维、红蓝丝网错版套印和斑驳宋体字的细节都很对味。此为作者对其生成结果的描述，与游园地图是两张不同的海报。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 5. 作者自写的闪蝶形态结构图解科普图

卡尔的AI沃茨自己写了一张闪蝶的形态结构图解科普图，作为高密度文字测试的一部分。作者称出来后挨个字查过，整体排版没有乱成一坨，层级清楚。这是作者自己的测试，与官方发布博文中的蓝闪蝶图解示例分开收录。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 6. 约 500 字的《中国六大茶类工艺与冲泡全图鉴》

卡尔的AI沃茨又写了一段将近五百个汉字的《中国六大茶类工艺与冲泡全图鉴》提示语，把画布塞满标题、导语、六个茶类的发酵度、工艺流程、代表名茶、水温茶水比，以及底部的选器与存茶口诀。作者称几百个字没有乱成一坨，标题、六宫格卡片和底部三栏层级清楚；放大看「萎凋」「渥堆」「碧螺春」「铁观音」这类笔画多、字号还小的汉字，横平竖直居然全保持住了。此为作者核字后的表述，不是本仓库的独立校对。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 7. 冬季竖版奶茶海报，品牌名「桂馥茶集」，并与两家对照排版

夕小瑶编辑部选了「桂馥茶集」这个稍有点笔画、又不至于太生僻的简体名字，给 Seedream 5.5 一份冬季竖版奶茶海报需求：主视觉要有热饮暖意，三款产品分别介绍茶底、原料、口味、容量和示例价格，杯身、纸袋和周边还要反复出现同一个品牌名。作者称冬季气氛明显、布局舒服，品牌大标题、三款品名以及 450mL、24／26／28 元这些主要信息都能读清。同一份提示词下，作者称 GPT Image 2.6 的版面塞得很满、有点挤，Nano Banana 2 排得规矩，但没有给每款茶配上对应的产品图。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 8. 受《后会友期》「画地为牢」梗启发的叙事拼贴海报

夕小瑶编辑部受《后会友期》里文艺青年许飞较火的梗「画地为牢」启发，做一张带叙事的海报，并提供了一些背景资料。创意方向是纸感拼贴：上面放舞台背影和日常回忆，中间用文字点出主题，下面再留给雪山、小屋和两个人。作者称第一版直出就让人意外：暖色回忆与蓝灰雪山分开了两个时间层次，石墙围出距离，底部的门把视线引向远处；大标题、引语和旁边的小段文字也各有位置，没有一起压到人物身上。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 9. 长图「2026 我的年度 AI 使用报告」，再套用同一风格做更多尺寸海报

APPSO 展示长图《2026 我的年度 AI 使用报告》。作者称长图的文字渲染能做到基本没有问题，于是继续套用这一风格，做出更多常规尺寸的海报风格图片。此为作者对其文字渲染测试的表述。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 10. 高信息密度中文信息图介绍李清照，并与 Image 2.6、Nano Banana 2.1 对照

向阳乔木用提示词「生成一张高信息密度的中文信息图，介绍李清照」，把 Seedream 5.5 与 GPT Image 2.6 Sunburst、谷歌 Nano Banana 2.1 对照。作者称 5.5 信息密度更高、版式 AI 味更小；2.6 Sunburst 中文字偏大，只有「凄凄惨惨戚戚」里的「戚戚」看起来不是很清楚；而 5.5 放大 3 倍查看，除「戚戚」不是很清晰外，「只恐双溪舴艋舟」中的「舴艋」也不清楚。作者写「能达到这种质量已经相当不易」，并提醒不要把 5.5 理解成完全没有错字。对 Nano Banana 2.1，作者认为一眼看去文本就不行。这些都是作者观感。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 11. 英文信息图中出现被回译为 “Be a hero in life, a mighty soul in death.” 的句子

向阳乔木修改提示词生成英文信息图，左为 Seedream 5.5，右为 GPT Image 2.6 Sunburst。作者称 GPT Image 的文本内容更少了；把 5.5 生图放大后，让谷歌翻译得到 “Be a hero in life, a mighty soul in death.”，并确认对应的是「生当为人杰，死亦为鬼雄。」此为作者对其对照和回译的记述。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 12. 把约万字模型卡片做成接近最大尺寸的大字报海报

冷逸称自己测了一个最复杂的案例：把自己整理的万字 Model card 发给模型，让它根据参考资料设计一张大字报海报，尺寸和分辨率几乎选的是模型能支持的最大的。作者称最终效果确实还不错，并欢迎读者纠错、查看海报中的文字有没有错。此为作者自评，本仓库未逐字校对该海报。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

### 13. 把常写错的「垠」和「逸」设计进海报

冷逸称，在 GPT 那边经常出错的中文字里，自己的「垠」和「逸」十有五回都是错的。这次他让 Seedream 5.5 把这两个字都设计进来，称完成得还挺不错，海报设计也很有水准。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

### 14. 户外封面「在沃垠 新生活」「冷逸的懒人文案」，并对照 Image 2.5 写错「懒」

冷逸又试了一张户外生活方式主题封面，主文案「在沃垠 新生活」，辅文案「冷逸的懒人文案」，场景为户外草坪上一位年轻东亚男性。作者称海报质量还不错，「懒」字也写对了；让 Image 2.5 跑了一遍，抽卡两次，两次的「懒」都写错了。此为作者对照。同一段里作者还写到目前不支持 4K，在极宽、极高比例的图像里仍会有部分小字模糊——这一限制写在 README 正文，不作为成功案例。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

<a id="photorealism"></a>

## 真实质感

### 1. 国内八九十年代古早老照片风格的人物真实感测试

卡尔的AI沃茨专门测了两个国内八九十年代的古早老照片。作者称效果非常真实，「就是当年拍那种老照片的感觉」，甚至会让人以为是翻出的家里旧照。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 人物加风景的手机随拍：雪山公路裂缝与渡轮栏杆锈点

同一篇文章里，作者还测了两张人物和风景在一起的手机随拍照。作者称人和后面的大风景没有抠图割裂感，雪山公路的路面裂缝、渡轮铁栏杆上的掉漆锈点都很自然。此为作者观感，与老照片测试分开收录。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 3. 银杏树下蹲着摸猫的秋季生活照，并与两家对照光影和接触

夕小瑶编辑部写了一张秋天的生活照：女生蹲在银杏树下摸猫。提示词要求 4:5 写实生活摄影，保留微小毛孔、细绒毛、轻微眼下纹理和真实不均匀肤色，午后侧逆光方向一致，文中完整提示词可见。作者称 5.5 这张侧逆光把头发、针织衫和猫毛边缘照亮，脸上仍留着自然明暗，手搭在猫头上、人与猫的接触基本自然。对照里，作者称 Image 2.6 生成的猫咪没有尾巴，人物也没有侧逆光；Nano Banana 2 的人与猫接触不是很自然，整体更没有光的效果。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 4. 16:9 远景雪山里的牦牛群，作者称 5.5 能辨认出 7 头且镜头没有推近

夕小瑶编辑部改用 16:9 横图，要求雪山、河道和针叶林成为主要画面，牦牛只在远处保留小小一群，看模型会不会为了画清动物擅自把镜头推近。作者称三家都保住了远景的小主体；Seedream 5.5 这张能辨认出 7 头牦牛，雪坡、树林和远山仍占着主要画面，但牛群略有列队，少了一点自然散开。Image 2.6 把兽群放得更远、更小，Nano Banana 2 的前景山石更突出。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- 作者/机构：夕小瑶编辑部
- 日期：2026-11-10
- 来源类型：`wechat`

### 5. 带方向光、使用痕迹和反光的手机屏幕截图质感图

APPSO 用 Seedream 5.5 生成一张手机屏幕截图，作者称光线会有方向和衰减，屏幕的使用痕迹、反光以及文字的渲染都接近相机摄影的质感。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 6. 三分之二侧脸黄金时刻肖像，背景为夕阳雪山与虚化经幡

APPSO 让模型生成一张人物的三分之二侧脸近景特写、直视镜头，黄金时刻的光影色彩，以及金色夕阳雪山与虚化的彩色经幡构成环境。作者称这些共同把照片里女孩的真实感和故事感刻画了出来，并觉得对比之前的人物生成更加细腻、真实。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 7. 模拟 iPhone 随手一拍的照片

APPSO 还展示了模拟 iPhone 随手一拍的照片，作者称 Seedream 5.5 生成的图片也非常真实。此为作者观感，与黄金时刻侧脸肖像分开收录。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 8. 手机随手拍风格的北京胡同雪景

向阳乔木用提示词「手机随手拍，超真实，北京一个胡同，下雪了」生成老北京胡同雪景。作者称能看到细碎的正在下落的雪花，以及北京常见的塑料垃圾桶、老旧房外加装的管道、摆在外面的凳子，相当逼真，并特别提到垃圾桶「演的好」。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 9. 北京五环外环卫工人扫雪的超真实随拍

向阳乔木再用提示词「手机随手拍，北京五环外，环卫工人在扫雪，超真实」。作者称远处看不清的公司招牌、下雪后车辆压过的路面、扬起来的雪都很像新闻照片，「不说的话，还以为是北京电视台拍的」。此为作者观感。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 10. 只写「天津海河边」的雪景里出现天津之眼，作者对照维基百科实拍

向阳乔木用「手机随手拍，超真实，天津海河边，下雪了」生成海河雪景。作者称只说海河边，Seedream 5.5 竟给画面加上了天津标志建筑之一「天津之眼」；担心被骗，又从维基百科找了一张实拍照片，发现造型跟真的几乎完全一样。这是作者的对照结论，不是本仓库的独立核对。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 11. 人像修图与造型变体：去皱、去痣、补妆、西江苗装自拍和发型方案

冷逸在图生编辑里给出一组短提示：去掉脸上和颈部的皱纹；去掉她脸上的小痣；把女生的嘴唇变厚一点，涂上淡淡的口红；让她穿着苗族服装，在西江苗寨自拍；并根据脸型设计不同发型、发色的效果示意图。作者称以前很多模型美颜修图会在细微处悄悄改变容貌，修完不像自己；Seedream 5.5 是他第一次觉得 AI 美颜修图这么丝滑，脸型收窄、去痣、去痘、去皱纹、双眼皮、补妆都可以做到，身份保持比以前更好。此为作者观感，本条将同一节里的系列修图测试收在一起，不拆成近重复条目。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

<a id="layer-decomposition"></a>

## 图层拆分

### 1. 把复杂时尚杂志拼贴海报拆成 27 层，被遮挡物体补全而非留洞

卡尔的AI沃茨挑了一张极其复杂的先锋时尚杂志拼贴海报来测图层分离，图中有黑白人像剪报、手撕色块、胶片条、干花标本、回形针、火漆印、立体金属星芒和标题字等互相压在一起的元素。作者称 Seedream 5.5 一口气拆出了整整 27 个图层，并且能把每一个被遮挡在底下的素材自动补全，再单独拆出来；这 27 个图层里随便拎出任何一个往旁边拖，都是边缘完整、没有破洞的独立素材。此为作者对其测试的表述。文章前面提到的「最多可以分离出 100 个图层」是对产品能力的转述，不是这次 27 层测试本身的结果。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 生成海报拆成约 100 层可复用图层，文字层返回结构化识别并可重新排布

APPSO 写道，图层拆分能力让一张生成的图片最多可拆成约 100 层可复用的背景、元素和文字图层，文字图层还会返回结构化识别结果，方便后续本地化或模板复用；并配图说明一张生成的海报可以把上面的元素分成多个图层进行重新排布。约 100 层是文章转述的产品能力上限，配图展示的是对生成海报做图层拆分与重排。此条按该文的产品说明与演示收录，不是本仓库的独立计数。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

<a id="reference-fusion"></a>

## 参考图融合

### 1. 4 人、2 宠、露营车和多件道具融进黄昏雪山草甸

卡尔的AI沃茨准备了 7 张图，包括 4 个人物、2 个宠物、多件道具、1 辆车和一个场景，要求他们自然出现在图 7 的黄昏雪山湖畔开阔草甸里。文中给出了很长的 16:9 提示词，指定谁坐哪、谁戴哪顶帽子、谁抱吉他、猫趴在谁腿上，并要求酒瓶标签「江湖夜雨」四个字清晰不变，把白底素材的光线重算为黄昏雪山的清冷蓝调和桌上火光。作者称跨图连线一个不落都对上了号，酒瓶上那么小的「江湖夜雨」都没糊，而且没有拼贴抠图感。此为作者观感；本清单只概括提示词要点，不整段照抄。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 以李清照画像为参考生成正面真人图，并与《持械入宋》角色李清棠对照

向阳乔木以一张李清照画像为参考，输入提示词「生成正面真人图」，再和 AI 短剧《持械入宋》中参考李清照画像加工的角色「李清棠」剧照对比，称果然有几分神似。这是作者的参考图测试与观感，并不表示该剧使用了 Seedream 5.5。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 3. 按姿势参考生成剧中角色杀青合照，人一多面部出现飘移

向阳乔木搜罗《持械入宋》剧中角色不同分辨率形象，让模型参考姿势图生成一张杀青合照。作者称姿势参考到位，但是人物形象多了以后，面部多少还是有一些飘移，并建议如果做 AI 短剧，还是要尽量控制场景中的主角数量，避免过多依赖参考生图。此为作者对其测试的限制说明。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

### 4. 两个人手挽着手在陌生街道合影，作者称一次直出

在讨论单/多轮编辑之后，冷逸列举自己实测且都是 one shot 直出的案例，其中之一是让两个人手挽着手在陌生的街道合影。此为作者对其测试的表述。文中提到的「官方 37 轮、提示词只有将图中 XX 改为 XX、其他部分保持不变」是作者展示的官方案例，本仓库未在官方产品页或发布博文中核到「37 轮」这一表述，故不把那一段算作冷逸的原创实测，也不单列官方案例。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`
- 说明：文中「37 轮」官方示例未在本仓库打开的官方页面中核到，不另建官方案例。

### 5. 让九个人按固定姿势（草图）合照，作者称一次直出

冷逸同一组 one shot 实测里，还包括让九个人按固定姿势合照。此为作者对其测试的表述。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

### 6. 让模特「住进」新家，作者称一次直出

冷逸同一组 one shot 实测里，还包括让模特住进新家。此为作者对其测试的表述。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`

### 7. 用「银光」网站色卡给 OpenAI 官网重新配色和 UI

冷逸同一组 one shot 实测里，还用自己「银光」网站的色卡，重新给 OpenAI 官网做了配色和 UI。此为作者的界面配色测试，并不表示 OpenAI 参与或背书。

- 来源：[https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- 作者/机构：冷逸
- 日期：2026-11-09
- 来源类型：`wechat`
- 说明：作者用自有色卡做的界面配色测试，不代表 OpenAI 参与。

### 8. 为录屏软件 Capwise 探索图标：有参考 10 款、从零 10 款，再透明拆层和扩图

向阳乔木介绍自己开发的录屏软件 Capwise，先上传原 Logo，提示「为我们录屏软件设计 10 种不同风格的 icon」；为增加选择，不给参考图再生成 10 个，提示是「为一款名叫 Capwise 的录屏软件设计 10 种不同风格的 icon，扁平风格，顶级水平」，并提到像素风和透明玻璃风格看起来都很有趣。作者给出的技巧包括：在即梦选择「透明背景」直接生成透明图；对图标集做图层分离，把每个 icon 拆成透明图层；如果觉得图标不够大，再用扩图。此为作者围绕同一套图标需求的探索，收为一条。

- 来源：[https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- 作者/机构：向阳乔木
- 日期：2026-11-10
- 来源类型：`wechat`

<a id="workflows"></a>

## 工作流

### 1. 豆包工作读取飞书 AI 新闻，做成早报信息图、拆层存 PSD，并做同款月度 PPT

卡尔的AI沃茨在飞书里养着一个 AI 热点机器人。作者让豆包工作读取飞书里的消息，先把最近 12 个小时最重要的 AI 新闻浓缩总结出来，再在同一个对话框里调用 Seedream 5.5，把这批资讯做成一张能发朋友圈的 AI 早报信息图；若要微调，可在豆包工作里点进这张图的画布，一键拆分图层挪动位置，还能一键存成本地分层 PSD。作者还会基于最近一个月的新闻，继续调 Seedream 5.5 做成一套同款视觉风格的 PPT。这是同一条日常设计流里的多个交付物，收为一条工作流案例。

- 来源：[https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- 作者/机构：卡尔的AI沃茨 / 卡尔 & 阿汤
- 日期：2026-11-10
- 来源类型：`wechat`

### 2. 授权后读取飞书群聊或文档，梳理需求并调用 Seedream 5.5 出品牌视觉

APPSO 写道，在获得相应授权后，可以让豆包工作直接读取飞书群聊，自动梳理团队讨论过的设计需求，再调用 Seedream 5.5 生成符合要求的品牌视觉方案；也可以直接发送一个飞书文档给豆包工作，使用 Seedream 5.5 的 Skill，同时调用与飞书文档打通的能力和生图能力来交付。作者还提到生成结果可以连接到本地电脑，进入 Photoshop 等专业软件继续精修。这是该文对「读飞书、出生图」工作流的演示与说明，群聊与文档两条路径收在同一条。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 3. 先生成台灯透明背景图，再据此生成对应的 3D 资产文件

APPSO 在豆包工作内生成了一张台灯的透明背景图片，接着让它根据这张图片生成对应的 3D 资产文件。这是该文展示的独立交付步骤。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`

### 4. 虚构气泡水品牌：主视觉多轮衍生三口味，拆层做视差并组装成网页

APPSO 试着让一个虚构的气泡水品牌从一张产品图走到完整的新品页面：Seedream 5.5 先生成主视觉，再通过多轮编辑衍生出三种口味，尽量保持罐身设计和品牌文字不变；透明背景的产品图进入口味卡片，拆分出的罐身、水果和背景图层被用来做滚动视差；最后豆包工作把这些素材组织成一个完整网页。文中还提到，若需社媒宣传，可以使用「社媒营销配图」Skill，或调用「风格海报」Skill 围绕同一套视觉继续做不同风格海报。后两项在文中是顺带说明的可用技能，不是另外单独展开的实测，本条只把气泡水从主视觉到网页这一叙事收为案例，并在此注明。

- 来源：[https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- 作者/机构：APPSO
- 日期：2026-11-09
- 来源类型：`wechat`
- 说明：「社媒营销配图」「风格海报」在原文中为可用技能说明，未单独展开为另一套实测，故不另建条。

<a id="contributing"></a>

## 如何贡献

欢迎补充可核验的公开玩法与案例，请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。提交时请同时更新 `README.md`、`README.en.md` 和 `cases.json`。

## 许可与声明

清单文字以 [MIT License](LICENSE) 发布。第三方作品、商标和媒体仍归原权利人。本仓库只保存索引文字和链接，不转载媒体文件。详见 [NOTICE.md](NOTICE.md)。实际打开过的页面见 [docs/SOURCES.md](docs/SOURCES.md)。
