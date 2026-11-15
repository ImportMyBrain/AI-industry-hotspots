# 今日 AI 行业热点（2026-11-13）

> 整理自 11 月 12–13 日（北京时间）的公开报道。当天主线：黄仁勋毫无缓冲地辞任英伟达 CEO，Google 用 Gemini 4 Hydrogen 把"便宜快"打成新卖点，OpenAI 则让智能体学会了刷卡。另一边，四家非营利组织把五家 AI 巨头一起告上了法庭。

## 1. 黄仁勋辞任英伟达 CEO，CFO 科莱特·克雷斯临时接任

11 月 12 日，英伟达董事会宣布，联合创始人黄仁勋辞去总裁、CEO 及董事会成员职务，即刻生效。现任执行副总裁兼 CFO 科莱特·克雷斯（Colette Kress）出任临时 CEO，同时继续履行 CFO 职责；董事会同步启动正式 CEO 遴选，内部和外部候选人都看。哈维·C·琼斯（Harvey C. Jones）被任命为公司首位董事会主席。

市场反应很直接：英伟达市值单日蒸发超过 1.2 万亿元人民币。黄仁勋掌舵 33 年，偏偏选在云厂商自研芯片、竞争对手追赶、下一代产品切换的节点"闪辞"，留给继任者的不是一个安稳的摊子。11 月 17 日的财报，将是克雷斯的第一场公开考试。

来源：[NVIDIA Newsroom](https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition)、[光明网](http://world.gmw.cn/2026-11/13/content_39099661.htm)

## 2. Google 发布 Gemini 4 Hydrogen：速度是上代 Flash 的 2.5 倍，价格更低

11 月 12 日，Google 推出 Gemini 4 Hydrogen，定位日常编码和智能体工作流。官方数据：完成速度是 Gemini 3.8 Flash 的 2.5 倍，Terminal-Bench 4.1 从 18.2% 提升到 57%，事实性幻觉率降到原来的五分之一以下；Artificial Analysis 智能指数默认 high 档 51 分、xhigh 档 54 分，超过 Argon 的 50 分。定价输入 1.5 美元、输出 7.5 美元每百万 tokens，100 万上下文全区间同价。

配套的 Antigravity Orchestrator 会在会话中自动分工：Carbon 负责看依赖、做计划，Hydrogen 负责改代码、跑测试，卡住再交回 Carbon。Google 称这套组合能省 24% 额度、提速 19%。一句话总结：旗舰负责想，便宜模型负责干。

来源：[Google 官方博客](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)、[36氪](https://36kr.com/p/4067541215400833)

## 3. OpenAI 推出 ChatGPT Wallet：智能体可以替你付钱了

11 月 13 日，OpenAI 发布 ChatGPT Wallet，允许 ChatGPT 的 AI 智能体代用户购物、订酒店。该功能与 American Express、Mastercard、Visa 合作，用网络令牌替代真实卡号，商家和智能体都看不到原始卡信息；每笔交易需用户用指纹或 Face ID 确认。首批仅面向美国 18 岁以上的 ChatGPT Pro 用户。

支付本身不是重点，重点是闭环：智能体此前能比价、填表、下单，最后一步总要人掏手机；现在这最后一步也被接走了。随之而来的是授权边界、退款责任和欺诈认定——当 Agent 能直接花钱，风控模型也得重写。

来源：[Digital News 360](https://thedigitalnews360.com/2026/11/14/openai-launches-chatgpt-wallet-allowing-ai-agents-to-shop-and-book-hotels/)、[industry.co.id](https://m.industry.co.id/read/159207/rangkuman-update-ai-global-15-november-2026-lab-ai-digugat)

## 4. 四家非营利组织起诉五家 AI 巨头，要求暂停下一代模型

11 月 13 日，Irreplaceable Education Fund、Public Citizen、Heat Initiative、Alliance for Secure AI 四家非营利组织联合向旧金山高等法院起诉 OpenAI、Anthropic、Google、Meta 以及 SpaceX 的 AI 部门。诉状依据加州不正当竞争法，主张五家公司开发前沿 AI 构成"公共妨害"，请求法院在被告能证明技术处于人类控制之下以前，暂停下一代模型的训练与部署。

原告不要赔偿，只要禁令。诉状还引用了各家高管自己关于网络攻击、生物武器风险的警告。需要强调：目前只是起诉阶段，法院没有裁决，开发也没有自动停止。但 AI 治理的战场，确实从议会和标准组织打到了法院。

来源：[腾讯新闻](https://news.qq.com/rain/a/20261115A07C4K00)、[21世纪经济报道](http://m.toutiao.com/group/7708236291925606912/)

## 5. Cursor 披露供应链攻击：Fireworks AI 泄露密钥，恶意 Claude Code 扩展混进市场

11 月 13 日，Cursor 更新了 10 月安全事件的调查结果。攻击者拿到 Cursor 签发给 Fireworks AI 的访问密钥（该密钥由 Fireworks 侧泄露），从共享存储桶复制了历史编码智能体轨迹，其中少量凭据未脱敏；随后横向进入 Cursor 内部 SaaS 工具，最终在 Cursor VS Code 扩展市场的缓存中投放了恶意 Claude Code 扩展（2.1.312 / 2.1.313）。最多约 5000 名用户在约 11 小时的窗口内可能拿到恶意版本。

Cursor 已将全部推理流量迁出 Fireworks，轮换所有暴露凭据，并重建扩展市场。这件事的警示很直接：AI 编码工具的供应链不只有模型和插件，还有推理服务商、共享存储和那些被默认信任的访问密钥。

来源：[Cursor 官方博客](https://cursor.com/blog/security-incident-update)

## 6. DeepSeek 开放"全家桶应用 API"，开发者可 1:1 复刻 DeepSeek App

11 月 13 日晚，DeepSeek 宣布开放全家桶应用 API，把 DeepSeek App 的交互能力整合进原有 API：开启对应参数后，工具调用与上下文拼接由服务端自动完成，开发者可以在自己的应用里实现联网搜索、文件输入、链接阅读、语音交互等完整对话功能，理论上可 1:1 复刻 DeepSeek App。除 Token 费用外，扩展工具按类计费：文字/图片搜索和网页抓取 5 元/千次，文字识别 1.5 元/千页，语音识别 0.39 元/小时。

这对开发者是好事——以前要自己接一堆外部工具、处理调用衔接，现在服务端打包好了。对 API 厂商来说，竞争点也从"模型多少钱"变成了"谁能把 Agent 的工具链一次给全"。

来源：[第一财经](https://www.yicai.com/news/103440926.html)

## 7. Black Forest Labs 开源 FLUX 3 Image Klein：5.6B 参数，支持最多 10 张参考图

11 月 13 日，Black Forest Labs 发布 FLUX 3 Image Klein，5.6B 参数、开源权重，支持文生图、图像编辑以及最多 10 张参考图输入。官方定位是给本地部署和批量视觉内容生产提供一个可落地的选择——不追求闭源旗舰的极限画质，而是把"可下载、可微调、可控成本"做成卖点。

图像模型的开源侧今年一直在卷"高分辨率 + 低延迟"，Klein 补的是"多参考图 + 本地部署"这一块。对需要批量出图又不愿把素材传到云端的团队，这类模型比榜单第一名更有用。

来源：[AI快讯](https://news.tuikar.cn/)

## 8. Google 与三星开放 Gemini 智能眼镜预售：395 美元起，12 月 10 日开售

Google 与三星宣布首批 Gemini 智能眼镜开启预售，Warby Parker 款 395 美元起，Gentle Monster 款 449 美元起，12 月 10 日在美国和韩国开售。硬件为 1200 万像素摄像头、约 9 小时续航、约 41 克，没有镜片内显示，主要靠语音与 Gemini 交互。

没有 AR 显示，意味着它更像是"戴在脸上的语音助手 + 摄像头"，而不是科幻片里的那副眼镜。395 美元的价格也不算便宜，但对 Google 来说，这是把 Gemini 从手机里拿出来、放进日常场景的第一步。

来源：[Google 官方博客](https://blog.google/innovation-and-ai/technology/xr-ar/google-intelligent-eyewear-collections-pre-order/)、[Samsung Mobile Press](https://samsungmobilepress.com/articles/samsung-intelligent-eyewear-december-release-smarter-way-see-world)

## 其他快讯

- **Claude Code 2.1.323 加入实验性 Code Mode**：Claude 不再逐个调用工具，而是写一段 JavaScript 一次调用多个工具，多步任务从十次往返压成一次；默认关闭，需手动开启。
- **Anthropic IPO 本周启动路演**：拟发行 8.25 亿股，价格区间 70–78 美元，最高募资约 644 亿美元；另计划向 Google、英伟达、AMD 等基石投资者私募配售约 260 亿美元。按流通股口径估值上限约 1.02 万亿美元，完全摊薄约 1.4 万亿美元，低于市场此前预期的 2 万亿美元。
- **OpenAI 三季度营收升至 100 亿美元**：经营亏损从上一季度的 101 亿美元扩大至 109 亿美元；同期 Anthropic 三季度营收约 170 亿美元，但两家统计口径不同。
- **张一鸣谈追赶前沿**：称字节有能力与 OpenAI、Anthropic 竞争，但真正追平"最早也要到 2029 或 2030 年"，并指出 Seed 系列预训练数据规模仍是短板。
- **llama.cpp 发布 v1.0.0**：为 libllama 和 ggml 引入语义化版本号，此后 API/ABI 破坏性变更将走大版本号。

来源：[Claude Code 文档](https://code.claude.com/docs/en/code-mode)、[第一财经](https://www.yicai.com/news/103440926.html)、[AI Weekly 11-14](https://aiweekly.co/ai-news-today/edition/2026-11-14)

## 今日趋势点评

黄仁勋的"闪辞"把英伟达的治理风险摆上了台面，而 Gemini 4 Hydrogen 和 ChatGPT Wallet 说明大厂正在同时压两方面成本：模型调用要更便宜，智能体要能直接完成交易。四家 NGO 的诉讼则提醒所有人，能力越强、闭环越完整，法律和监管的反作用力也会越快到来。接下来 11 月 17 日的英伟达财报，会是市场对这套新叙事的一次集中投票。
