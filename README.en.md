# Awesome Seedream 5.5

> A community catalog of [Seedream 5.5](https://seed.bytedance.com/zh/seedream5_5) play methods and public cases. This repository is not an official ByteDance, Seed, 即梦 (Jimeng), 豆包 (Doubao), or Volcengine project, and is not endorsed by them.

[简体中文](README.md) | [English](README.en.md)

Browse the [GitHub Pages catalog](https://xianyu110.github.io/awesome-seedream-5.5/). Preview images are hosted on a custom image bed. Prompts appear on the catalog page when a source provided them; we do not invent missing prompts.

This list currently has **80** verified cases (as of 2026-11-11, Asia/Shanghai). The catalog prefers fewer, better-sourced entries: every item has a source URL that was actually opened. We do not invent names, numbers, or URLs. Figures and judgments are restated from the sources and labeled as official or author claims, not as independent verification by this repository. Structured data: [`cases.json`](cases.json).

## What the model is

**Seedream 5.5** is an image-creation model released on 2026-11-09 by ByteDance's Seed team. The official post describes three core upgrades:

1. **More stable multi-round editing.** Unedited regions are preserved at the pixel level, with color shift in those areas eliminated and less detail loss or degradation across successive edits. Officially, this supports continued work on the same image across as many as 100 rounds.
2. **Native RGBA transparent assets.** The model can directly output images with an alpha channel, including full and partial transparency, with careful treatment of edges and transparent regions.
3. **More natural materials and clearer text.** Lighting, materials, and skin texture are described as more natural, with less excessive gloss and overexposure; complex glyphs and densely arranged small text are said to render more accurately.

The official post also previews a later Pro version in the Seedream 5.5 series.

Official evaluations (all from the 2026-11-09 launch blog, not independently verified here): on MagicArena, across e-commerce, marketing, film and television, gaming, office, and fashion design, the official post says quality scores and usability rates both improved versus Seedream 5.0 Pro, with usability in film/TV and office more than twice the previous version. In GSB (Good/Same/Bad) tests of text structure and realism, the official post says all four comparisons against the previous version (text-to-image and image-to-image) were positive, with realism image-to-image GSB at +55.62%, and says the model leads GPT Image 2.5 Sunburst and Nano Banana 2.1 on text structure and text-to-image realism. Official text-corruption rates in evaluations covering Chinese and English, including dense small text, are given as 0.4% severe and 1.7% minor. Community A/B tests in the articles below are author impressions and should be read separately from these official figures.

## Official links

| Resource | Notes |
| --- | --- |
| [Product page](https://seed.bytedance.com/zh/seedream5_5) | Seedream 5.5 product page and official demos |
| [Launch blog (2026-11-09)](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5) | Chinese launch post |
| [English blog (2026-11-09)](https://seed.bytedance.com/en/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5/) | English version of the same post |

## Where to use it

Official entry points:

1. 即梦 web — Create — Generate / Canvas — choose Seedream 5.5
2. 豆包 app or web — image generation — choose the Seedream 5.5 model
3. 豆包工作 — Skills — Seedream5.5 (APPSO also writes: type `/seed` in the chat, then choose the Seedream 5.5 skill)
4. Volcengine Ark / 火山方舟 experience center — visual models — image generation — Doubao-Seedream-5.5

Community articles (卡尔的AI沃茨, 夕小瑶编辑部, 向阳乔木, and others) said a Volcengine API would go live in the week of launch. This catalog has not verified a public API URL and does not treat an unconfirmed endpoint as already available.

On pricing, 卡尔的AI沃茨 cites Volcengine API rates then on display: billing on input and output images, with text tokens free; editing a 2K square image about 0.28 RMB, less than half of 5.0 Pro, and about one-third of GPT Image 2.5 High. 夕小瑶编辑部 also writes that editing a 2K image is about 0.28 RMB, including the input and output images. These are citations from the articles, not official long-term pricing verified by this catalog; treat the official Volcengine price list as authoritative when it is published.

冷逸's article also described a then-current 即梦 promotion for the new model (for example, seven-day unlimited access for everyone, longer membership windows, and a Double 11 campaign mentioned in the same piece). That was time-limited marketing at the time of publication, and this catalog does not treat it as standing policy.

## Play methods and prompt recipes

The recipes below come from official demo phrasing and community articles, especially 冷逸's WeChat post “即梦Seedream 5.5来了，分享13个超实用的玩法.” The title says “13 plays,” but the body is grouped by capability and does not give a numbered list of 13 named plays, so this catalog does not invent those names.

- **Edit phrasing:** Change XX in the image to XX, and keep everything else unchanged. You can locate the target with a selection box, a red circle, or a number. 冷逸's edit skeleton: change the original state of (the area inside the red circle / the upper left / the 3rd object) to the target state, and keep the rest (subject, composition, lighting, background, typography) unchanged.
- **Transparent assets:** In 即梦 you can turn on the explicit 「透明背景」 toggle (冷逸). You can also trigger RGBA with words such as 透明背景, 半透明, PNG透明底, 无背景, and alpha通道 (implicit phrasing from the same article).
- **Realism:** Start with the genre and overall tone, then who is doing what in which scene, plus lens and material qualities. 冷逸 stresses stating the task before style, and fixing the visual genre (poster, infographic, key visual, and so on) before details.
- **Text:** Put the exact copy in quotation marks, give every character, and describe hierarchy, position, type style, weight, color, alignment, and line count.
- **Structure over adjectives:** Specify position, hierarchy, composition, and module relationships instead of only stacking words like “premium” or “atmospheric” (冷逸).

冷逸's recommended prompt skeleton (from the article):

```
[Task] generate / edit: <one-sentence goal>
[Subject] <who / what / count / state>
[Scene] <environment / time / weather / spatial relations>
[Composition] <aspect ratio / layout zones / camera / shot size>
[Light and style] <light direction / palette / materials / reference style>
[Text] "<verbatim copy>" — position / type style / weight / color / alignment / lines
[Keep] <what must not change, listed explicitly>
[Exclude] <what must not appear>
```

A shorter pattern from the same article: Generate a [genre] for [use / channel], [layout], the subject is […], [lighting/style], and place the text “[verbatim]” at [position]. His cover example: generate a Xiaohongshu vertical cover (3:4) for a beauty note, the top third a solid-color field for the title and the bottom two-thirds a close-up of a hand holding the product, soft light, a light beige background, title “早八不脱妆.”

冷逸 also writes that 4K is not supported yet, and that some small text still blurs in extremely wide or tall aspect ratios. 向阳乔木, in a Li Qingzhao infographic, notes that 戚戚 and 舴艋 were still unclear when zoomed 3×. Those are limitations stated in the sources, not success cases claiming error-free text.

## Category overview

| Category | Count |
| --- | ---: |
| Official demos | 26 |
| Multi-round editing | 9 |
| Transparent assets | 6 |
| Typography and layout | 14 |
| Photorealism | 11 |
| Layer decomposition | 2 |
| Reference fusion | 8 |
| Workflows | 4 |
| **Total** | **80** |

## Contents

- [Official demos](#official-demo) (26)
- [Multi-round editing](#multi-round-edit) (9)
- [Transparent assets](#transparent-assets) (6)
- [Typography and layout](#typography-layout) (14)
- [Photorealism](#photorealism) (11)
- [Layer decomposition](#layer-decomposition) (2)
- [Reference fusion](#reference-fusion) (8)
- [Workflows](#workflows) (4)
- [Contributing](#contributing)

<a id="official-demo"></a>

## Official demos

### 1. Multi-round interior furniture, lighting, and décor edits

The official product page, under “multi-round editing that stays consistent,” shows furniture, lamps, and décor being added or replaced step by step, with colors and placement adjusted while spatial perspective and lighting stay coordinated. This is an official product-page demo, not a community test.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 2. Multi-round edits to a person's hair, glasses, clothes, background, and table props

The official product page shows multi-round changes to the same person's hairstyle, glasses, clothing, background, and tabletop props, gradually presenting different looks. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 3. Multi-round snake-game edits on a monitor: position, length, and score

The official product page shows the snake's position, length, and score being updated round by round, while the monitor and UI layout stay consistent. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 4. Multi-round still-life additions of fruit, vases, and branches

The official product page shows fruit, vases, and branches being added gradually to enrich a still-life composition, while the scene's lighting stays coordinated. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 5. Multi-round hairstyle, makeup, and head-accessory edits

A separate official product-page demo shows multi-round changes to a person's hairstyle, makeup, and head accessories, gradually presenting different looks. It is listed alongside the clothing/background/table-prop sequence.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 6. Multi-round traditional Chinese painting florals

The official product page shows vases, foliage, and decorative accents being adjusted step by step to enrich a traditional Chinese painting composition. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 7. Multi-round watch-face updates to time, activity data, and charts

The official product page shows the time, activity data, and charts on a watch face being updated round by round, while the layout and appearance of the face stay consistent. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 8. 100 successive edits on the same person, still refining rings and eyeglass frames

The official launch blog says the team performed 100 successive edits on an image of the same person, using each round's output as the next input. After repeated changes to clothing, accessories, and tabletop objects, the official account says the model can still make precise edits to small objects such as rings and eyeglass frames, and can render contact, occlusion, and lighting between accessories and skin according to the current pose. This is an official demo and official claim.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 9. Running-girl sequence with each frame as a separate transparent layer

The official product page, under “transparent assets in one step,” shows a sequence of a girl running to the right, with each frame output as an independent layer on a transparent background. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 10. Flamingo extracted as a standalone RGBA transparent layer

The official product page shows a flamingo extracted from a scene and output as a standalone RGBA layer with a transparent background. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 11. Two cartoon sticker sheets with transparent backgrounds outside the elements

The official product page shows two cartoon sticker sheets: one made of ocean elements and a cartoon kitten, the other of animals and plants. Areas outside the sticker elements are a transparent background. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 12. Yarn-wrapped “Seedream 5.5” lettering, 16:9, transparent outside the letters

The official product page shows “Seedream 5.5” rendered as rounded sans-serif letters wrapped in alternating royal-blue and lake-blue yarn, with fiber, fuzz, and a side-cast shadow, following the texture and lettering in a reference image. The output is a 16:9 banner with transparency outside the letters. This is an official product-page demo. The launch blog also describes applying a reference image's brushwork, color, and material to specified text and emitting a transparent asset; that general capability is not split into a second case here.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`
- Notes: 官方博文中的「文字与材质融合的透明素材」与产品页这一字标示例同属一类能力，不重复建条。

### 13. Blue plush 3D characters output as separate transparent assets

The official product page shows a round, large-eyed, short-limbed blue plush 3D cartoon character with a playful expression, then three more characters in the same style with different poses and expressions. The four characters are each output as transparent-background images so they can be separated and combined like puzzle pieces. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 14. Circular snowy-owl feather and foot close-ups, transparent outside a thin frame

The official product page shows a circular macro close-up of a snowy owl's fine white feathers meeting snow, then a second circular macro of the smaller owl foot on the right of a reference image, on a light-gray ground. Both images have a 3-pixel dark-gray thin frame, with transparency outside the circle. This is an official product-page demo.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 15. Snowy owl with spread wings as an RGBA asset, including feather gaps and claw outlines

The official launch blog includes a separate snowy-owl demo: the owl spreads its wings, with clearly defined layers of feathers. The official account says the model carefully renders feathers at the wingtips, tiny gaps between them, and claw outlines, preserving complex structure without later background removal or edge cleanup. This is not the same sequence as the product page's circular macro close-ups.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 16. The same transparent character assets reused across a series of scenes

The official launch blog says a designer can use the same set of transparent character assets as references to quickly create a series of images of those characters in different settings. The official account says the model retains the characters' defining features and textures while allowing changes to poses, groupings, and composition. This is the official demo of reusing transparent assets across scenes.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 17. White cat in a night bar, seated among bottles and glasses

The official product page, under “more realistic textures,” shows a white cat seated among bottles and glasses in a night bar, shot from a low, upward, tilted angle, with flash, Fujifilm Provia film color, and grain. This is an official product-page example; the wording here only restates the setup, not the full marketing paragraph.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 18. Father holding a sleeping baby on a sofa in soft window light

The official product page shows a young father reclining on a dark plum-gray fabric sofa, holding a sleeping baby, with warm golden window light from the right. The launch blog also describes this scene, noting soft window light on the face and arms and visible skin and fabric detail in shadow. This entry catalogs that shared official example.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 19. South-European street corner with a lemon-yellow wall, deep-purple door, and gold flowers

The official product page shows a 3:4 street photograph: a lemon-yellow lime-washed wall, an old deep-purple wooden door, and hanging royal-purple linen in a geometric composition, with golden flowers in an old metal bucket at lower right, in strong afternoon sun and a purple-yellow complementary palette. This is an official product-page example.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 20. Woman looking at a phone in strong wind, with the whole frame tilted about 25 degrees

The official product page shows a wide street snapshot of a long-haired woman in a burgundy top and light-brown coat looking down at a phone, with hair blown by a strong wind. The entire frame is tilted about 25 degrees clockwise, and the person, buildings, lamp post, and pavement share the same tilted perspective. This is an official product-page example.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 21. Documentary snapshot of two middle-aged customers dining in a summer-night tavern

The official product page shows a wide documentary snapshot of a European neighborhood tavern on a summer night: two middle-aged customers eating naturally at a table with an off-white linen cloth, not looking at the camera, with glasses, cutlery, breadcrumbs, and worn wooden furniture, under warm hanging lights mixed with a little cool night light. This is an official product-page example.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 22. Rain-wet stone and puddle reflections, without showing a complete building

The official product page shows a 3:4 after-rain street photograph, shot from a low angle looking down at wet stone bricks and irregular puddles, with gold carved details, window frames, and colonnades of an old building reflected in the water. The page specifies that the frame should not include a complete building, people, or vehicles. This is an official product-page example.

- Source: [https://seed.bytedance.com/zh/seedream5_5](https://seed.bytedance.com/zh/seedream5_5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 23. Portrait of a girl looking back toward the camera, with backlight on hair and visible skin texture

In its discussion of portrait quality, the official launch blog shows a girl looking back toward the camera, with clearly visible facial skin texture, a natural highlight-to-shadow transition on the shoulder, and loose strands of hair catching the backlight. This official blog example is catalogued separately from the product-page photoreal scenes.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 24. Race car on a rain-soaked track, with spray from the tires spreading behind it

In its section on scene texture, the official launch blog describes a race car on a rain-soaked track, with the bodywork and wet road reflecting light differently, spray from the tires spreading behind the car, and distant vehicles partly obscured. This is an official blog example.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 25. Blue morpho structure diagram with eight groups of small-size Chinese captions

The official launch blog uses a blue morpho infographic to illustrate Chinese text at small sizes: eight illustrated notes describe features such as the antennae, wing veins, and scales. The official account says that even in the small captions beside the close-ups, characters with many strokes remain easy to read. This is an official example. A later morpho-diagram test by 卡尔的AI沃茨 is catalogued separately as that author's own run.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

### 26. Shakespeare-themed newspaper page with passages of small English text

The official launch blog shows a newspaper-style page about Shakespeare, with several passages of small English text between a portrait and a theater illustration. The official account says the text remains easy to read in this compact layout. This is an official blog example.

- Source: [https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5)
- Author / org: 字节跳动 Seed 团队
- Date: 2026-11-09
- Source type: `official`

<a id="multi-round-edit"></a>

## Multi-round editing

### 1. 30-round relay on a vintage vinyl-cafe photo, compared with GPT Image 2.6

卡尔的AI沃茨 used a detailed vintage vinyl-cafe photograph as the base and ran Seedream 5.5 and GPT Image 2.6 through 30 successive edits on the same image. The sequence included a corduroy coat, gold-wire glasses, an emerald ring, a burgundy bucket hat, a matcha latte, writing with a fountain pen, a strawberry waffle, double braids, a rainstorm and heavy snow outside the window, then, in rounds 28–30, removing the hat and glasses and returning the hair and work jacket to the original look. The author says 5.5 changed only the requested region across all 30 rounds—for example, almost only the cup when swapping an iced Americano for a matcha latte—while Image 2.6 also drifted in unrequested areas and, after the rain edit at round 17, became increasingly oily and painterly. These comparisons are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. Six rounds of time-of-day lighting only, with people and architecture frozen

In the same article, the author froze the people and street architecture and ran six rounds that only advanced the time of day and global lighting: 7:00 soft morning light, 12:00 harsh overhead sun, 17:00 sunset backlight, 19:00 storm-wet reflections, 23:00 neon, and 5:00 blue-hour mist. The author says 5.5's warm reflections in storm puddles and the cool-warm neon light on a profile felt closer to real-camera optics, while Image 2.6 looked increasingly like a cheap cartoon-game filter, with wet-ground reflections disconnected from the light on the figures. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 3. Birthday-cat cake numerals changed from 1 to 18, with only the number edited

夕小瑶编辑部 ran 18 rounds that changed only the numeral on the front of a birthday-cat cake, from 1 through 18, each time using the previous result; the cat's coat, face-holding pose, pearl accessories, and the candles and glasses on the table were not allowed to change. The author says all 18 numerals were correct and the paws, pearl headpiece, and necklace stayed put. In the same 18-round test on Image 2.6, the author says the numbers remained legible, but later rounds brought blocky redraws on the cat's face, fur, and tablecloth, and the originally dim candlelit scene grew brighter and warmer. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 4. 12-round clothing try-on on a model photo, with left-side product-card thumbnails updating too

夕小瑶编辑部 used a model photo close to the author's own proportions as a try-on base; a product-combination card was already on the left. Identity, body shape, stance, phone, room, and lighting were held fixed, and each of 12 rounds named only that round's garment change, building on the previous result: the base shirt was changed to soft mist blue, caramel brown, and bean-paste pink, with the left “crew-neck base shirt” thumbnail required to match, then a long-sleeve cardigan, different trousers, and finally the bag's material and color. The author says the left thumbnails updated with the tops, cardigan, and trousers, while the background stayed still. In the same 12 rounds, the author says GPT Image 2.6 started to slip after the cardigan (inconsistent glasses size and cardigan cut) and Nano Banana 2 showed earlier frame-pattern drift, with the left card not matching the clothes on the body. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 5. Multi-round Mona Lisa costume and job changes, with pose and texture almost unchanged

APPSO repeatedly changed the clothing and occupation in a Mona Lisa portrait; the article lists roles such as programmer, delivery rider, doctor, chef, astronaut, and esports player. The author says the pose and image texture barely changed, and only the clothing varied. This is the author's impression.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 6. A bare apartment furnished floor by floor, with the window view and sunlight angle held still

APPSO furnished a bare, all-concrete apartment across successive edits, adding a floor, television, air conditioner, and coffee table while requiring the view outside the window and the angle of incoming sunlight to stay unchanged. The author says those unedited regions were preserved at the pixel level. This is the author's account of the test.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 7. Shop photo: bilingual sign, removal of bikes and stands, and OPEN changed to CLOSE

APPSO ran multi-round edits on a shop photograph found online: translating the signboard into Chinese and English, gradually removing bicycles, e-bikes, and product stands, and changing the OPEN sign on the door to CLOSE. The author says the gradient background and other porch elements were left alone, and that after a trash can was removed, light from the store's overhead fixture appeared on the ground. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 8. Elevator-mirror selfie of a Beijing rock-circle girl, then multi-round outfit changes with the subject held still

Following a tip to use 即梦 canvas, 向阳乔木 first generated a selfie of “a young, pretty long-haired Beijing rock-circle girl in front of an elevator mirror… right hand holding a phone that covers half her face,” then continued from the first image with prompts such as “keep the pose, change the outfit” and “keep the subject, change into a very different outfit.” The author compiled a GIF and says that, aside from jitter in a few clothing frames, the face and background barely moved. The full prompt is in the article. This is the author's own test.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 9. Multi-round outfit changes on a widely circulated “老黄” leather-jacket likeness

向阳乔木 writes that “老黄” had been in the headlines and is widely associated with a leather-jacket look, so the author also tried several outfit changes to see whether other looks would appear sharper than the usual leather jacket. This is the author's test of that public likeness; the article does not claim involvement or endorsement by the person or any organization.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`
- Notes: 作者对广为流传公众形象的换装测试，不代表当事人或机构参与。

<a id="transparent-assets"></a>

## Transparent assets

### 1. 3×3 orange-cat office-worker stickers with frosted-glass speech bubbles and jelly-like RGBA assets

卡尔的AI沃茨 asked Seedream 5.5 to generate a 3×3 sheet of orange-cat office-worker stickers, including frosted-glass speech bubbles and a somewhat 3D, jelly-like graphic asset. The author says the output was a PNG with an alpha channel that could be used directly, without a separate background-removal step. This is the author's own test.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. Ten cat photos extracted as independent transparent layers in 即梦 canvas

夕小瑶编辑部 placed ten original photos on the 即梦 canvas as references for one generation node, chose Seedream 5.5 at 2K, switched the background option under the input box to “transparent background,” and prompted the model to extract the cat from each photo as an independent layer with transparency outside the subject. The author says the cats were separated from their original environments, keeping yellow caps, bibs, and coat patterns; a leftover sliver of cat-tree board remained under a bicolor cat, which the author flags as minor and fixable in later layout.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 3. Reused extracted cat assets as a stamp-album page and mini magazine covers

After obtaining the previous set of transparent cat assets, 夕小瑶编辑部 placed them in new layouts: each cat in a ticket-style frame with perforated edges, a face value, and a postmark on cream paper, like a small stamp album; and the same assets as mini magazine covers, one cat per cover, with a title, different background colors, and column text, then assembled into a sheet. The author says the two layouts differ in style, but identifying details such as caps and accessories were preserved.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 4. A 4×4, 16-frame transparent sprite sheet from an action reference, then sliced into a GIF

夕小瑶编辑部 put a combat action sprite sheet in as figure 1 and the desired character as figure 2, kept “transparent background” on, and prompted: follow figure 1's action layout to make a 128px simplified pixel-art sprite sheet for figure 2, 4×4, 16 frames, with prepare, punch, kick, and hit taking four frames each, on a transparent background. The author says Seedream 5.5 produced 16 transparent action cells in four columns and four rows, and that the image model's work ended there. Slicing and compositing were then handed to a locally installed DeepSeek Harness running Python: 16 PNGs, then a looping transparent GIF at 100 ms per frame (1.6 seconds total). The GIF step was not done by Seedream.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`
- Notes: 切帧与 GIF 合成为本地 DeepSeek Harness 跑 Python，不是 Seedream 本身。

### 5. A group photo turned into a chibi sticker with a thick white outline; author says about 62% fully transparent

APPSO uploaded a group photo and turned the people into a chibi sticker style, getting an RGBA PNG with a thick white outline and a truly transparent background. The author says about 62% of the area was fully transparent, the size was usable as a sticker or overlay, and shows the sticker placed on a T-shirt; the same method is also applied to pets, turning a pet photo into a cute chibi transparent sticker. The “about 62%” figure is the author's description of that result.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 6. Explicit toggle or trigger words to generate and extract transparent assets, then composite them

冷逸 describes two ways to get RGBA output: an explicit 「透明背景」 toggle beside the 即梦 input box, or implicit trigger words in the prompt—透明背景, 半透明, PNG透明底, 无背景, alpha通道—to generate fully or partially transparent images with an alpha channel. The author says logos, icons, UI, products, objects, people, and stickers can be generated this way, with semi-transparent glass, packaging, and tulle as the harder cases; assets can also be extracted via image-to-image, and the author screen-records compositing them into other scenes. The article's illustrations were generated by the author with Seedream 5.5.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

<a id="typography-layout"></a>

## Typography and layout

### 1. Six-round handheld essence-water poster, checking watch English and the bottle's Chinese label

卡尔的AI沃茨 ran a six-round test on a handheld essence-water poster, focusing on the English LUMIÈRE and a line of very small Chinese, “澄光焕肤精粹水100ML,” on the paper bottle label, and on the small English text on a watch that remained in frame through round five. The author says Seedream 5.5 kept the watch face and the line of text below it consistent with the original and unblurred, while Image 2.6 already blurred the fine dial pattern and the text below it; after water drops were added in round 6, Image 2.6's bottle lettering was almost unreadable, whereas 5.5 still held those characters upright through sunlight refraction and droplets. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. Soda e-commerce poster typography compared with Image 2.6

卡尔的AI沃茨 ran the same prompt for a soda e-commerce poster on Seedream 5.5 and Image 2.6. The author prefers 5.5, saying it does not use one typeface across the whole poster, adds logos and small headings on its own, and gives the translucent selling-point bubbles more gloss, while 2.6 again used what the author calls default AI heavy bold and split the selling points across two lines in an awkward asymmetry. This is the author's aesthetic judgment.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 3. Garden-map poster with torn paper and eight hand-drawn checkpoints

卡尔的AI沃茨 ran event posters with Seedream 5.5 alone; one is a garden map with torn paper and eight hand-drawn checkpoints. The author describes it as relaxed in tone, with the small text in each bubble clearly legible. This is the author's description of that result.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 4. Art-exhibition silkscreen poster in a cool grid layout, with misregistered red-and-blue printing

In the same set of event posters, the author also ran a cool, grid-based art-exhibition layout, and says details such as paper fiber, misregistered red-and-blue silkscreen printing, and mottled Song-style type felt on-brief. This is the author's description of a second, distinct poster from the garden map.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 5. Author-written morpho butterfly structure diagram

卡尔的AI沃茨 wrote their own morpho-butterfly morphology diagram as part of a dense-text test. The author says they checked the characters one by one, and that the overall layout did not collapse into a heap and the hierarchy stayed clear. This is the author's own test, catalogued separately from the official launch-blog blue morpho example.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 6. An about-500-character infographic, “中国六大茶类工艺与冲泡全图鉴”

卡尔的AI沃茨 also wrote a prompt of nearly five hundred Chinese characters for “中国六大茶类工艺与冲泡全图鉴,” filling the canvas with a title, intro, fermentation levels, process steps, representative teas, water temperature and tea-to-water ratios for six tea types, plus a closing mnemonic on teaware and storage. The author says the hundreds of characters did not collapse, and that the title, six-cell cards, and three-column footer stayed clearly layered; close-ups of dense, small characters such as 萎凋, 渥堆, 碧螺春, and 铁观音 are said to have kept their strokes intact. This is the author's after-the-fact character check, not an independent proofread by this catalog.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 7. Winter vertical milk-tea poster branded 桂馥茶集, with layout compared against two other models

夕小瑶编辑部 chose the slightly stroke-heavy but not obscure name 桂馥茶集 and briefed Seedream 5.5 on a winter vertical milk-tea poster: a warm hot-drink hero, three products each describing tea base, ingredients, flavor, volume, and sample prices, with the brand name repeating on cups, paper bags, and merch. The author says the winter mood and layout worked, and that the main title, three product names, and details such as 450mL and 24/26/28 yuan were readable. On the same prompt, the author says GPT Image 2.6 packed the layout too tightly, and Nano Banana 2 was orderly but did not give each tea a matching product shot. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 8. Narrative collage poster inspired by the 《后会友期》 “画地为牢” meme

Inspired by the then-popular “画地为牢” meme around 许飞 in 《后会友期》, 夕小瑶编辑部 made a narrative poster and supplied some background material. The idea was a paper-collage layout: a stage back view and everyday memories on top, typography stating the theme in the middle, and snow mountains, a cabin, and two people below. The author says the first direct output was surprisingly effective: warm memories and blue-gray mountains formed two time layers, a stone wall created distance, and a door at the bottom led the eye into the distance; the main title, quotation, and side text each had their own place and did not pile onto the figures. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 9. A long typography piece, “2026 我的年度 AI 使用报告,” then the same style on more poster sizes

APPSO shows a long typography piece titled “2026 我的年度 AI 使用报告.” The author says text rendering on the long image was basically fine, and then applied the same style to more posters in regular sizes. This is the author's account of that typography test.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 10. High-density Chinese infographic on Li Qingzhao, compared with Image 2.6 and Nano Banana 2.1

向阳乔木 prompted “generate a high-information-density Chinese infographic introducing Li Qingzhao,” and compared Seedream 5.5 with GPT Image 2.6 Sunburst and Google Nano Banana 2.1. The author says 5.5 had higher information density and less of an “AI layout” feel; 2.6 Sunburst used larger Chinese type, with only 戚戚 in “凄凄惨惨戚戚” looking unclear; zooming 5.5 by 3×, the author still found 戚戚 unclear, and also 舴艋 in “只恐双溪舴艋舟.” The author calls this quality already hard-won and should not be read as a claim that 5.5 is error-free. The author also says Nano Banana 2.1's text looked poor at a glance. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 11. English infographic containing a line the author translated back as “Be a hero in life, a mighty soul in death.”

向阳乔木 changed the prompt to generate an English infographic, with Seedream 5.5 on the left and GPT Image 2.6 Sunburst on the right. The author says the GPT Image version contained less text; after zooming the 5.5 image, a Google translation produced “Be a hero in life, a mighty soul in death,” which the author confirms corresponds to “生当为人杰，死亦为鬼雄.” This is the author's account of that comparison and back-translation.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 12. A roughly 10,000-character model card turned into a near-maximum-size big-character poster

冷逸 describes what he calls his most complex typography test: he sent a 10,000-character model card he had compiled and asked the model to design a big-character poster from that reference, at nearly the largest size and resolution the model supports. The author says the result was quite good and invites readers to proofread the poster for errors. That is the author's own assessment; this catalog did not proofread the poster character by character.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

### 13. Posters that feature the often-mistrendered characters 垠 and 逸

冷逸 says that among Chinese characters GPT often gets wrong, his own 垠 and 逸 were wrong about five times in ten. This time he asked Seedream 5.5 to design both characters into posters, and says the result was quite good, with a strong poster design. This is the author's impression.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

### 14. Outdoor cover “在沃垠 新生活” / “冷逸的懒人文案,” vs Image 2.5 misspelling 懒

冷逸 also tried an outdoor lifestyle cover with the main line “在沃垠 新生活” and the secondary line “冷逸的懒人文案,” showing a young East Asian man on an outdoor lawn. The author says the poster quality was solid and 懒 was written correctly; running Image 2.5 twice, the author says 懒 was wrong both times. This is the author's comparison. In the same section he also notes that 4K is not supported yet and that some small text still blurs in extremely wide or tall aspect ratios—that limitation is stated in the README body, not as a success case.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

<a id="photorealism"></a>

## Photorealism

### 1. Photoreal tests in the style of 1980s–90s Chinese old photographs

卡尔的AI沃茨 specifically tested two images in the style of Chinese family photographs from the 1980s and 1990s. The author says the results felt very real, “the way those old photos actually looked,” even like something pulled from a family album. This is the author's impression.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. Candid phone photos of people in landscapes, including cracks in a snow road and rust on a ferry rail

In the same article, the author also tested two candid phone photos that combine a person with a large landscape. The author says there was no cut-out disconnect between the person and the scenery behind, and that cracks in a snow-road surface and peeling rust on a ferry rail looked natural. These are the author's impressions, catalogued separately from the old-photo test.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 3. Autumn photo of a girl crouching under ginkgo trees and touching a cat, compared with two other models

夕小瑶编辑部 wrote an autumn candid: a girl crouching under ginkgo trees and touching a cat. The prompt asks for 4:5 realistic lifestyle photography, keeping pores, fine vellus hair, slight under-eye texture, and uneven skin, with consistent afternoon rim light; the full prompt is in the article. The author says 5.5's rim light caught the hair, knit cardigan, and cat fur, the face kept natural light and shade, and the hand-on-head contact looked basically natural. In the comparison, the author says Image 2.6's cat had no tail and the person lacked rim light, while Nano Banana 2 had weaker contact and less of a lighting effect. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 4. 16:9 distant yaks in snow mountains; the author says 5.5 shows seven yaks without pushing in

夕小瑶编辑部 switched to a 16:9 wide frame, asking for snow mountains, a river, and conifer forest as the main picture, with only a small herd of yaks kept in the distance, to see whether the model would push the camera in to make the animals clearer. The author says all three models kept the distant small subjects; on the 5.5 image the author can make out seven yaks, with the snow slope, woods, and far mountains still dominating, though the herd is a bit too lined up and less naturally scattered. Image 2.6 placed the animals farther and smaller; Nano Banana 2 made the foreground rocks more prominent. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg](https://mp.weixin.qq.com/s/GmoNPBe0uD72jSUWHZnFGg)
- Author / org: 夕小瑶编辑部
- Date: 2026-11-10
- Source type: `wechat`

### 5. Photoreal phone-screen image with directional light, smudges, and reflections

APPSO used Seedream 5.5 to generate a phone-screen image. The author says the light has direction and falloff, and that smudges, reflections, and the rendering of text on the screen come close to camera-photograph quality. This is the author's impression.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 6. Two-thirds side-face golden-hour portrait with sunset mountains and blurred prayer flags

APPSO asked for a close, two-thirds side-face portrait looking at the camera, in golden-hour color, with golden sunset snow mountains and blurred colorful prayer flags in the environment. The author says these elements together gave the girl a sense of realism and story, and felt more refined and real than earlier portrait generation. This is the author's impression.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 7. A photo in a casual iPhone-snapshot style

APPSO also shows a photo meant to look like a casual iPhone snapshot, and says the Seedream 5.5 result looks very real. This is the author's impression, catalogued separately from the golden-hour side portrait.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 8. A casual phone-photo of snow in a Beijing hutong

向阳乔木 used the prompt “casual phone photo, hyper-real, a Beijing hutong, it is snowing” to generate a snowy old-Beijing alley. The author says you can see fine falling flakes, plus common Beijing details such as a plastic trash bin, pipes added to an old facade, and stools left outside, and specifically praises the trash bin as especially convincing. These are the author's impressions.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 9. Hyper-real candid of a sanitation worker sweeping snow outside Beijing's Fifth Ring

向阳乔木 then used the prompt “casual phone photo, outside Beijing's Fifth Ring, a sanitation worker sweeping snow, hyper-real.” The author points to a distant, unreadable company sign, tire-pressed snow on the road, and kicked-up snow, and says that without a caption it could be mistaken for a Beijing TV news still. This is the author's impression.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 10. A Tianjin Haihe snow scene that added Tianjin Eye; the author compared it with a Wikipedia photo

向阳乔木 used “casual phone photo, hyper-real, by the Haihe in Tianjin, it is snowing.” The author says that, given only “by the Haihe,” Seedream 5.5 added Tianjin Eye, one of the city's landmark structures; worried it might be faking the shape, the author compared it with a Wikipedia photograph and found the form almost exactly the same. That is the author's comparison, not an independent check by this catalog.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 11. Portrait retouch and look variants: wrinkle and mole removal, lipstick, a Miao costume selfie, and hairstyle options

冷逸 gives a series of short image-to-image prompts: remove wrinkles on the face and neck; remove a small mole; make the lips a bit fuller and add light lipstick; have her take a selfie in Miao dress in Xijiang; and, based on her face shape, design different hairstyle and hair-color options. The author says earlier retouch models often quietly changed identity in small ways; Seedream 5.5 is the first time he has found AI retouching this smooth, covering slimming, mole and acne removal, wrinkle removal, double eyelids, and makeup, with identity held better than before. These are the author's impressions. The series in that section is kept as one case rather than split into near-duplicates.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

<a id="layer-decomposition"></a>

## Layer decomposition

### 1. A complex fashion-magazine collage split into 27 layers, with occluded objects completed rather than left as holes

卡尔的AI沃茨 tested layer separation on a very complex avant-garde fashion-magazine collage, with overlapping elements such as black-and-white portrait clippings, torn color blocks, film strips, dried flowers, paper clips, a wax seal, three-dimensional metal starbursts, and title lettering. The author says Seedream 5.5 split the image into a full 27 layers and automatically completed each occluded object rather than leaving holes, so any of the 27 layers could be dragged aside as a complete, uncut asset. This is the author's account of that test. The article's earlier remark that an image can be split into as many as 100 layers is a restatement of a product capability, not the result of this 27-layer run.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. A generated poster split into about 100 reusable layers, with structured text recognition and rearrangement

APPSO writes that layer splitting can turn a generated image into as many as about 100 reusable background, element, and text layers, and that text layers also return structured recognition results for later localization or templates; a figure shows a generated poster whose elements were split into layers and rearranged. “About 100 layers” is the product ceiling as stated in the article; the figure demonstrates splitting and rearranging a generated poster. This entry follows that article's product description and demo, and is not an independent count by this catalog.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

<a id="reference-fusion"></a>

## Reference fusion

### 1. Four people, two pets, a camper van, and many props fused into a dusk snow-mountain meadow

卡尔的AI沃茨 prepared seven references—four people, two pets, many props, a van, and a scene—and asked that they appear naturally in figure 7's dusk meadow by a snow-mountain lake. The article includes a long 16:9 prompt that specifies who sits where, who wears which hat, who holds the guitar, and which lap the cat lies on, and requires the bottle label 江湖夜雨 to stay legible while relighting the originally white-background assets into cold dusk mountain light and warm tabletop firelight. The author says every cross-image assignment landed, the small 江湖夜雨 characters stayed clear, and it did not look like a cut-and-paste collage. These are the author's impressions; this catalog summarizes the prompt rather than reprinting it in full.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. A front-facing photoreal person from a Li Qingzhao painting, compared with 李清棠 in 《持械入宋》

向阳乔木 used a Li Qingzhao portrait as a reference, prompted “generate a front-facing real-person image,” and compared the result with stills of 李清棠, a character in the AI series 《持械入宋》 that was itself art-directed from Li Qingzhao portraits. The author says there is some resemblance. This is the author's reference-image test and impression, and does not mean the series was made with Seedream 5.5.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 3. A group “wrap photo” of a show's characters from pose references; faces drifted when many people shared one frame

向阳乔木 collected stills of characters from 《持械入宋》 at various resolutions and asked the model to generate a wrap-style group photo from pose references. The author says the poses landed, but once many characters were in one frame, faces drifted to some degree, and advises anyone making AI shorts to limit how many leads share a scene and not rely too heavily on reference generation. This is the author's limitation note from that test.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

### 4. Two people arm-in-arm on an unfamiliar street; the author says it was a one-shot result

After discussing single- and multi-round editing, 冷逸 lists tests he says were all one-shot results, including two people walking arm-in-arm for a photo on an unfamiliar street. This is the author's account of that test. The “official 37-round” example he shows, using only the prompt pattern “change XX in the image to XX, keep everything else unchanged,” is attributed by him to an official case; this catalog did not find the phrase “37 rounds” on the official product page or launch blog, so that clip is not counted as 冷逸's original test or as a separate official case.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`
- Notes: 文中「37 轮」官方示例未在本仓库打开的官方页面中核到，不另建官方案例。

### 5. Nine people posed from a sketch; the author says it was a one-shot result

In the same set of one-shot tests, 冷逸 also had nine people pose for a group photo according to fixed poses (shown as a sketch in the article). This is the author's account of that test.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

### 6. A model “moving into” a new home; the author says it was a one-shot result

In the same set of one-shot tests, 冷逸 also had a model “move into” a new home. This is the author's account of that test.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`

### 7. Recoloring the OpenAI website UI with the author's 「银光」 site color card

In the same set of one-shot tests, 冷逸 also used the color card from his own 「银光」 website to recolor and restyle the OpenAI website UI. This is the author's interface-recolor test and does not imply involvement or endorsement by OpenAI.

- Source: [https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA](https://mp.weixin.qq.com/s/UfFhq6zns58lG9n8D7nuZA)
- Author / org: 冷逸
- Date: 2026-11-09
- Source type: `wechat`
- Notes: 作者用自有色卡做的界面配色测试，不代表 OpenAI 参与。

### 8. Capwise icon exploration: 10 styles from an existing logo, 10 from scratch, then transparent split and outpainting

向阳乔木, describing the screen recorder Capwise he developed, first uploaded the existing logo and prompted “design 10 different icon styles for our screen-recording app,” then, for more options, generated 10 more from scratch: “design 10 different icon styles for a screen-recording app named Capwise, flat style, top tier,” noting that the pixel and frosted-glass looks were especially interesting. The author's tips include turning on 即梦's “transparent background,” splitting an icon sheet into transparent layers, and outpainting if an icon is too small. This icon-exploration thread is kept as one case.

- Source: [https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A](https://mp.weixin.qq.com/s/CdSI7mcHw5ALU5LXzRNp0A)
- Author / org: 向阳乔木
- Date: 2026-11-10
- Source type: `wechat`

<a id="workflows"></a>

## Workflows

### 1. 豆包工作 reads a Feishu AI-news bot, makes a morning-briefing infographic, splits layers to PSD, and builds a matching monthly PPT

卡尔的AI沃茨 keeps an AI-news bot in Feishu. The author has 豆包工作 read those messages, summarize the most important AI news of the last 12 hours, then call Seedream 5.5 in the same chat to turn the digest into a shareable morning-briefing infographic; for tweaks, the image can be opened on the canvas inside 豆包工作, split into layers, rearranged, and saved as a layered PSD. The author also has Seedream 5.5 make a matching-style PPT from a month of the same news. These deliverables belong to one daily design flow and are kept as a single workflow case.

- Source: [https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw](https://mp.weixin.qq.com/s/XBIkbitBBnapXzcXfRbuvw)
- Author / org: 卡尔的AI沃茨 / 卡尔 & 阿汤
- Date: 2026-11-10
- Source type: `wechat`

### 2. After authorization, read a Feishu group or doc, extract the brief, and call Seedream 5.5 for a brand visual

APPSO writes that, after the relevant authorization, 豆包工作 can read a Feishu group chat, automatically sort the team's design discussion, and call Seedream 5.5 to produce a brand visual that matches the brief; alternatively, a Feishu document can be sent to 豆包工作 with the Seedream 5.5 skill, using both the Feishu-doc integration and the image model for delivery. The author also notes that results can be passed to a local computer for further work in tools such as Photoshop. The chat and document paths in this “read Feishu, generate visuals” workflow are kept as one case.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 3. Generate a lamp with a transparent background, then a corresponding 3D asset file

APPSO generated a transparent-background image of a lamp inside 豆包工作, then had it produce a corresponding 3D asset file from that image. This is a distinct deliverable shown in the article.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`

### 4. A fictional sparkling-water brand: a hero shot, three flavors via multi-round edits, layered parallax, and a webpage

APPSO walked a fictional sparkling-water brand from one product image to a full new-product page: Seedream 5.5 first generated a hero shot, then derived three flavors through multi-round edits while trying to keep the can design and brand lettering unchanged; transparent product shots went into flavor cards, and split layers of the can, fruit, and background were used for scroll parallax; 豆包工作 then assembled the assets into a complete webpage. The article also mentions a “social marketing image” skill and a “styled poster” skill for further merch from the same visual system. Those last two are described as available follow-on skills, not separately expanded tests, so this case keeps the sparkling-water hero-to-webpage narrative and only notes them here.

- Source: [https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw](https://mp.weixin.qq.com/s/aynuHlmLl6eWJPPkMNp_hw)
- Author / org: APPSO
- Date: 2026-11-09
- Source type: `wechat`
- Notes: 「社媒营销配图」「风格海报」在原文中为可用技能说明，未单独展开为另一套实测，故不另建条。

<a id="contributing"></a>

## Contributing

Public, checkable play methods and cases are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first, and update `README.md`, `README.en.md`, and `cases.json` together.

## License and notice

The catalog text is released under the [MIT License](LICENSE). Third-party works, trademarks, and media remain with their owners. This repository keeps only index text and links; it does not host or copy media files. See [NOTICE.md](NOTICE.md). Pages actually opened are listed in [docs/SOURCES.md](docs/SOURCES.md).
