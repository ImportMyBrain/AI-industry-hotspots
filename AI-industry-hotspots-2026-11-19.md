# 今日 AI 行业热点（2026-11-19）

> 整理自 11 月 18–19 日（北京时间）的公开报道。今天的主线是“把 AI 塞进更硬的壳里”：谷歌把旗舰级能力打到三折价，OpenAI 让模型去改写 AMD 的 GPU 电路，苹果则被曝要让自家助手学会开电脑。资本侧，德国电信拿 1 亿欧元买了一张 Mistral 的“主权 AI”船票。

## 1. Gemini 4 Neon 突袭：61 分、三美元、现货开卖

11 月 18 日（美西时间），谷歌发布 Gemini 4 家族新成员 Neon，距离上一款 Carbon 只隔三周。定价为每百万输入 token 3 美元（缓存输入 0.15 美元，约 95% 折扣）、输出 15 美元，标配 100 万 token 上下文，并首次开放名为 xhigh 的极限思考档；发布即上线 AI Studio、Gemini 应用、企业 API 和 Antigravity，不搞排队申请那套期货玩法。

跑分上，Neon 在 Artificial Analysis 综合智能指数拿到 61 分、排名第三，仅次于 Claude Fable 5.2 和 GPT-6.2 Astra，还以 1 分反超自家大哥 Carbon；编码 Agent 指数排名第一，256K–1M 长上下文检索的 GraphWalks 拿到 95.2%，把 Opus 5.5 的 66.8% 和 GPT-6.2 Sol 的 80.1% 甩开一个身位。同期 Genie 4 世界模型向 Google AI Ultra 订阅用户开放，支持中途用文本修改环境、并首次配上实时原生音频。

翻译一下：谷歌这轮不比“谁最聪明”，比的是“够聪明且便宜到可以随便调用”。代价是 Antigravity 被挤爆、出现限流排队——便宜也是有代价的，至少第一天的算力账单由用户先垫。

来源：[Google 官方博客](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/)、[36Kr](https://36kr.com/p/4075907868955785)、[腾讯新闻](https://news.qq.com/rain/a/20261119A03YWP00)

## 2. OpenAI 让模型改芯片：AMD 旗舰 GPU 最高 +14% PPA

11 月 19 日，OpenAI 公布“利用 OpenAI 模型推进芯片设计”的成果：模型通过重写描述电路的 SystemVerilog RTL 代码来重构架构，在 AMD 已经深度打磨过的旗舰 GPU 关键 IP 上，实现最高 14% 的 PPA（功耗、性能、面积）综合改善，把原本约一年的优化周期压缩到 5 个月以内。部分成果已被 AMD 纳入近期提交制造的设计。

自研侧同样有数字：OpenAI 的 AI 推理芯片 Jalapeño 借助模型优化后面积减少 13%。这套流程的核心不是让模型“画电路”，而是让它在既有 RTL 上做大规模、可验证的等价改写——换句话说，AI 开始参与设计给自己供算力的芯片。

这件事的象征意义大于 14% 本身：以前是“AI 用芯片”，现在变成“AI 改芯片”，而且改的是最上游、最缺人的环节。芯片设计的人力瓶颈如果真能被压缩，算力供给曲线会比市场预期更早变陡。

来源：[IT之家](http://m.toutiao.com/group/7709653460106609179/)、[新浪财经](https://cj.sina.com.cn/articles/view/1704103183/65928d0f0200bibqg)、[腾讯新闻](http://news.qq.com/rain/a/20261120A08W9Y00)

## 3. 苹果被曝自研自主智能体：会写代码、会控 App，最早 2027 年底

11 月 19 日，彭博社古尔曼爆料称，苹果正在开发一款能代表用户执行任务的自主 AI 智能体，加入 OpenAI、Anthropic、Meta 和谷歌的智能体竞赛。苹果官网 11 月 17–18 日挂出的招聘信息给出了细节：岗位名为“Agentic AI - Proactive”高级工程经理，描述中的智能体能浏览网页、跨应用操作、执行命令、编写和调试代码、调用服务，并根据每一步自行选择合适的工具。

苹果特别强调权限管理、沙盒隔离与操作透明度——一个能跑代码、用用户凭据、代用户行动的智能体，安全和隐私不能靠“相信 Siri”。项目仍处早期，古尔曼称公司内部讨论过最早 2027 年底推出。

问题是，2027 年底这个时间点，Meta 的 Muse、Anthropic 的 Duet、OpenAI 的 Dots 大概已经把用户的“代办习惯”养完了。苹果的优势是设备和入口，劣势是它过去十年在助手这件事上欠的债有点多。

来源：[IT之家](http://m.toutiao.com/group/7710020470715744802/)、[Apple 招聘页](https://jobs.apple.com/ja-jp/details/200695488-0836/senior-engineering-manager-agentic-ai-proactive)

## 4. 德国电信 1 亿欧元入股 Mistral，押注“主权 AI”

11 月 19 日，德国电信旗下投资机构 T.Capital 宣布向 Mistral AI 的 D 轮投入 1 亿欧元（约 1.09 亿美元），作为双方战略合作的第一步：把德国的主权基础设施、客户关系和集成能力，与 Mistral 的前沿模型、企业软件和部署能力绑在一起。Mistral 的 D 轮已于 9 月完成，总额 30 亿欧元，估值超过 210 亿欧元。

这是欧洲“主权 AI”叙事的标准动作：钱不一定最多，但必须让模型跑在自己的云、自己的合规框架和自己的语言数据上。对 Mistral 来说，拿电信运营商的单子比拿风投的钱更实在——至少收入是合同，不是故事。

值得对照的是同一天的另一条消息：Mistral 把亚太总部设到新加坡，计划 2027 年把区域团队翻倍到 200 人。欧洲讲主权，亚洲讲落地，两边都不想只当美国模型的转售商。

来源：[Deutsche Telekom](https://www.telekom.com/en/newsroom/latest-updates/media-information/2026/11/deutsche-telekom-advances-sovereign-ai-in-germany)、[新华社](https://english.news.cn/europe/20261120/8e800587c5c54afeb3b3682a4601bb13/c.html)

## 5. Gemini 4 Hydrogen 接入 Antigravity：用人话教机械臂干活

11 月 17 日谷歌机器人团队公布、19 日开始发酵的方案：在 Google Antigravity 中加入机器人插件，把 Gemini 4 Hydrogen 与硬件接入、MuJoCo 仿真和真机控制串起来。用户用自然语言描述任务，模型先在仿真里排练动作，再部署到真实机械臂；官方演示里，机械臂从传送带上分拣零食。

过去让一条机械臂学会新任务，要写标定脚本、搭仿真环境、调感知代码，动辄数周；现在被压缩成一次对话加一次仿真试跑。谷歌的算盘是把“机器人编程”从系统集成商的活，变成模型 API 的活——这比再发一个聊天模型性感多了。

当然，演示和产线之间还隔着节拍、良率和安全认证。但至少方向明确：具身智能的竞争，正在从“能不能动”转向“教它动要花多少工程人力”。

来源：[Innovation Essence](https://innovationessence.com/gemini-4-hydrogen-gives-robot-arms-a-faster-cheaper-brain/)、[Karmactive](https://www.karmactive.com/google-gemini-4-neon-hydrogen-coding-robotics/)

## 6. Model ML 拿 2.5 亿美元 B 轮，估值 15 亿美元

11 月 17 日，面向投行与咨询公司的 AI 智能体公司 Model ML 宣布完成 2.5 亿美元 B 轮，由 General Atlantic 和 QED Investors 联合领投，估值 15 亿美元；此时距它结束隐身仅 18 个月，累计融资达到 3.5 亿美元。它的智能体直接连接 Excel、PowerPoint 和客户系统，替分析师和顾问做建模、写材料、跑流程。

“给专业人士配一个会敲 Excel 的实习生”这个故事，今年已经卖出好几个 10 亿美元估值。区别在于，Model ML 卖的不是通用聊天，而是嵌进投行工作流的成品——客户买的不是模型，是少雇几个 analyst 的理由。

来源：[Model ML](https://modelml.com/articles/model-ml-raises-250-million-at-1.5-billion-valuation-18-months-after-launching-from-stealth)、[TipRanks](https://www.tipranks.com/news/private-companies/model-ml-raises-250-million-at-1-5-billion-valuation)

## 7. 西班牙发布公共部门 AI 伦理采用指南

11 月 19 日，西班牙数字化与公共职能部发布《公共行政部门 AI 伦理采用指南》，为公共机构落实欧盟《人工智能法案》提供操作指引，重点包括提升法律确定性、规范公共部门采购 AI 系统的流程，以及把伦理要求写进合同和技术规格。

这类文件看着枯燥，但它决定了一件事：政府买 AI 时，供应商要交什么材料、谁来做评估、出了问题谁负责。欧盟 AI 法案的原则已经写完了，接下来两三年拼的是这种“采购附件”级别的落地能力。

来源：[西班牙数字化与公共职能部](https://digital.gob.es/comunicacion/notas-prensa/secretaria-digitalizacion-e-inteligencia-artificial/2026/11/publicada-la--guia-para-la-adopcion-etica-de-la-inteligencia-art)

## 其他快讯

- **阿里巴巴季度资本开支 504.77 亿元**：截至 9 月底的季度资本性支出同比增长 60%，公司称主要用于扩大 AI 算力规模与芯片组件采购。
- **商汤 SenseNova U1 Pro 上榜**：在 Design Arena 双榜拿到中国第一、全球第六。
- **黄仁勋被传将创办新芯片公司**：有媒体转述称其可能从朋友和盟友处筹集 500 亿美元重返 AI 行业；目前仅为传闻，未见本人或公司确认。

来源：[CFM 闪存市场](https://www.chinaflashmarket.com/newsflash/semi)、[商汤新闻中心](https://www.sensetime.com/cn/news)、[微博转述](https://m.weibo.cn/detail/5367461680516168)

## 今日趋势点评

今天三条线其实在讲同一件事：AI 正在往“更硬的壳”里钻。谷歌用 3 美元/百万 token 把旗舰能力做成日用品，OpenAI 把模型塞进芯片设计的 RTL 层，谷歌机器人团队则把机械臂编程压成一次对话——软件层的边际改进越来越便宜，真正的溢价开始转移到能改造物理世界和上游供应链的地方。资本也在配合这个转向：德国电信买 Mistral 买的是“主权部署权”，Model ML 卖的是“少雇几个分析师”，都比单纯买 GPU 更接近收入。治理侧，西班牙把伦理指南写成采购规则，说明监管的主战场已经从“要不要管”变成“招标文件第 7 页怎么写”。
