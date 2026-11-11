# 贡献指南 / Contributing

欢迎补充 Seedream 5.5 的公开、可核验玩法与案例。Please add public Seedream 5.5 cases.

## 提交要求

1. 必须与 **Seedream 5.5** 直接相关，并附上原始来源 URL（官方产品页/博文、作者原帖、可核验的新闻且能追溯到一手来源）。
2. 不要编造姓名、引言、数字、链接或日期。数字与评价请按来源原样转述，并标明那是官方或作者自述，不要写成我们已经独立验证。
3. 一条案例 = 一个来源中实际展示过的独立演示、实测或工作流，不要把同一段能力介绍改写后重复提交。如果社区文章只是复述官方演示，请引用官方页面为来源（可在说明里提及该文章）。作者自己跑的测试，以该文章为 `source_url`。
4. 请同时更新 `README.md`、`README.en.md` 和 `cases.json`。`cases.json` 字段：`id`, `title_zh`, `title_en`, `category`, `summary`（中文，忠实转述）, `source_url`, `author`, `date`（ISO `YYYY-MM-DD`，未知则 `null`）, `source_type`；必要时可用 `notes`。可选字段：`image_url`（自定义图床上的完整 `https://` 地址，须能明确对应本条案例的演示图，拿不准就留空，不要猜测配对），`prompt`（仅当官方页面或所引文章原文给出提示词 / 提示语时照录，不要改写或补写）。不要在本仓库托管或复制媒体文件；预览图请上传到图床后再写入 `image_url`。
5. 分类建议：`official-demo`、`multi-round-edit`、`transparent-assets`、`typography-layout`、`photorealism`、`layer-decomposition`、`reference-fusion`、`workflows`。如需新分类，请在 PR 里说明。
6. `source_type` 请尽量准确：`official`、`wechat`、`personal-blog`、`company-post`、`news`、`community`。

## 修改方式

事实勘误、失效链接、错误署名和版权问题可以直接开 Issue 或 Pull Request。小修正也可直接提交 PR。

This project is licensed under the MIT License. Linked case material stays with its original authors; see NOTICE.md.
