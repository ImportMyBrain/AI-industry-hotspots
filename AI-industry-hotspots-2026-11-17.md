# 今日 AI 行业热点（2026-11-17）

> 整理自 11 月 16–17 日（北京时间）的公开报道。当天主线：钱和算力继续往头部挤——Anthropic 路演材料自曝"3 天把模型搬上 AMD"，英伟达 Rubin 首秀横扫 MLPerf，阿里则把 Qwen4-Max 的单价又往下按了一截。另一头，华为开源具身世界模型、微软把 138B 编码模型塞进本地，澳洲干脆准备把 AI 安全写成法定义务。

## 1. Anthropic 路演材料自曝：Claude 用 3 天完成 AMD MI355X 适配

Anthropic 在 IPO 路演视频中披露，Claude Mythos Preview 仅用约 3 天、几乎无人工干预，就完成了把一个模型跑在 AMD MI355X GPU 上所需的软件工作，而同类工作过去需要 6–12 个月、几十名工程师。联合创始人 Tom Brown 在 11 月 10 日的路演视频中给出这一对比，同日修订的招股书也写明公司能以"过去零头的时间"接入新芯片平台。

需要看清口径：这 3 天覆盖的是单个模型在 MI355X 上的 prefill（提示处理）达到"可用性能"，decode 未涉及，也没有与英伟达硬件的速度对比；"6–12 个月"是 Anthropic 自己的历史估算。但 Anthropic 是买芯片的一方，不是卖芯片的一方，这个说法对投资者的分量不一样。背景是它同时运行英伟达、AMD、Google TPU 和 AWS Trainium，并与 AMD 签了最高 2GW 的协议，首批 MI450 Helios 机架预计 2027 年上半年到位——3 天能不能在新硅上复现，才是真正的考试。

来源：[AI Daily Digest（引 Tom's Hardware）](https://dev.to/hiroki-ii-ai/ai-daily-digest-november-17-2026-claude-onboards-amd-gpus-in-3-days-vera-rubin-sweeps-mlperf-482n)、[Anthropic 招股书](https://ipo.anthropic.com/documents/us/prospectus.pdf)

## 2. 英伟达 Vera Rubin 首秀横扫 MLPerf Training v6.1

11 月 16 日发布的 MLPerf Training v6.1 结果里，Vera Rubin NVL72 在全部基准上均位列第一，是唯一覆盖大语言模型、图像生成、推荐系统和强化学习后训练全集的平台；单 GPU 性能最高达到高度优化后的 GB300 NVL72 的 2 倍。扩展性数据更扎眼：在 DeepSeek-V3 训练基准上，从 256 卡扩到 1024 卡仍保持约 97% 效率，训练时间从 16 分钟压到约 4 分钟。

英伟达还首次向 MLPerf Endpoints 提交结果。这个基准测的是"智能体推理"的每瓦吞吐，并检查智能体是否真的把任务干完；在 Kimi K3 的暂定结果上，Vera Rubin NVL72 在同响应速度下每瓦吞吐超过 GB300 的 10 倍。翻译一下：benchmark 也开始按"任务完成度"而不是"吐了多少 token"打分了，这对靠堆 token 讲故事的厂商不太友好。

来源：[NVIDIA Blog](https://blogs.nvidia.com/blog/mlperf-training-endpoints-vera-rubin/)、[NVIDIA 技术博客](https://developer.nvidia.com/blog/nvidia-vera-rubin-nvl72-achieves-up-to-2x-blackwell-ultra-performance-in-mlperf-training-v6-1)

## 3. 阿里正式发布 Qwen4-Max：2.4T 参数、原生视觉、单任务成本降六成

11 月 16 日，阿里巴巴发布新一代基座模型 Qwen4-Max，总参数 2.4T，具备原生视觉能力，支持百万级上下文。官方给出的卖点不是跑分而是账本：缓存命中时每百万 tokens 低至 0.5 元，完成单任务的平均费用较上代下降六成。模型已上线千问 AI 平台提供 API，也可通过 Token Plan、千问办公、Qoder 和千问 App 使用。

从 11 月 11 日的"预览版只给 1M 上下文、不给参数"到今天正式亮参数，阿里的节奏很明确：先用可用性占位，再用价格战收口。Qwen4 系列的中小尺寸模型后续会陆续开源，这意味着开源侧的压力还会继续往下传。

来源：[每日经济新闻](http://m.toutiao.com/group/7708908356072686107/)、[阿里云百炼文档](https://help.aliyun.com/zh/model-studio/qwen4-max-preview)

## 4. AMD 完成收购 World Labs，李飞飞出任执行副总裁兼首席科学家

11 月 16 日，AMD 宣布完成对 AI 研究公司 World Labs 的收购。World Labs 专注可创建和模拟交互式 3D 环境的模型，以及机器人学习与仿真技术；创始人李飞飞加入 AMD，担任执行副总裁兼首席科学家，直接向董事长兼 CEO 苏姿丰汇报。

这笔交易的信号很清楚：AMD 不想只卖"能跑大模型的卡"，还想往模型和空间智能的上游走。对英伟达来说，对手开始补软件与模型生态的短板；对具身智能创业公司来说，又多了一个"被芯片厂收编"的退出样板。

来源：[界面新闻 AI 早报](http://m.163.com/dy/article/LBU3EL6D0534A4SC.html)

## 5. 华为云开源昇腾原生具身世界模型 CloudRobo-WM1.2

11 月 16 日，华为云在具身世界模型发布会上推出并开源 CloudRobo-WM1.2，称其为首款昇腾原生具身世界模型。模型采用共享世界模型骨干实现预测增强的世界表征，基于原生 DualAct 架构做动作生成，在 RoboTwin 2.0 和 LIBERO-Pro 2.0 评测中均位列第一；华为云同时宣布开源权重、推理和代码。

"昇腾原生 + 开源"的组合，指向的是生态而不是单点模型：把训练和推理都放在国产算力上，再用开源换开发者。具身智能目前最缺的是可复现的数据与仿真闭环，世界模型能不能真的降低真机试错成本，比榜单第一更有说服力。

来源：[IT之家](https://www.ithome.com/1/027/837.htm)、[科创板日报](https://www.cls.cn/detail/2535409)

## 6. 微软发布 138B 本地编码模型 MAI-Code-1.1-Flash

微软的 MAI-Code-1.1-Flash 已通过 Microsoft Foundry 提供 53.0 GiB 混合精度权重，并作为 GitHub Copilot 的本地模型运行。这是一个 137.9B 参数的 MoE 编码模型，官方给出的实测环境是 128GB 统一内存、64GB GPU 分配的 RTX Spark：投机解码让 120K 输入下的中位吞吐从 25.81 提升到 51.12 tokens/s，滑动窗口注意力把 262K 上下文下的草稿注意力缓存从 5,120 MiB 降到 1,156 MiB，且无需重训。

配套的 Windows ML Runtime API 也进入预览，支持本地 GGUF、OpenAI 兼容端点和零拷贝输入。微软的赌注是：日常编码会拆成"云端前沿模型 + 本地即时模型"两层，隐私代码不必每次都上云。当然，官方也提醒这些数字只对应一种服务配置，别拿回家当通用承诺。

来源：[AI Daily Digest（引 Microsoft Foundry）](https://dev.to/hiroki-ii-ai/ai-daily-digest-november-17-2026-claude-onboards-amd-gpus-in-3-days-vera-rubin-sweeps-mlperf-482n)

## 7. 一天三笔融资：Noeri 1.1 亿美元、Corma 估值破 10 亿、Plural 募资 10 亿欧元

由斯坦福教授 Yejin Choi 和 Carlos Guestrin 创办的 Noeri 于 11 月 16 日亮相，获 Menlo Ventures 领投的 1.1 亿美元，Madrona、Kindred、Wing、NEA 参与，英伟达、Snowflake、思科战略投资，估值未披露。它的主张与"单一超级模型"相反：智能应分布在多个企业自有、专门化的系统里，系统从任务、失败和纠错中持续自我改进，客户保留数据和模型所有权。

同一天，防御性安全公司 Corma 以 10 亿美元估值完成 1.25 亿美元 A 轮，NEA 领投，红杉、Khosla、Coatue 跟投，距其 6000 万美元种子轮仅三个月；伦敦基金 Plural 则关闭了 10 亿欧元新基金，约为其首期基金的近四倍，继续押注欧洲深科技。资本的口味很一致：安全、自我改进、欧洲深科技，都是"故事能讲十年"的方向。

来源：[Unite.AI](https://www.unite.ai/noeri-raises-110m-to-build-self-improving-ai-for-enterprises/)、[新浪财经](https://finance.sina.com.cn/stock/estate/integration/2026-11-17/doc-iniyyvsp5554567.shtml)、[AI Daily Digest](https://dev.to/hiroki-ii-ai/ai-daily-digest-november-17-2026-claude-onboards-amd-gpus-in-3-days-vera-rubin-sweeps-mlperf-482n)

## 8. 澳大利亚拟立法对前沿 AI 企业设强制性安全要求

澳大利亚总理阿尔巴尼斯 11 月 10 日宣布，政府将通过立法设立专门监管机构，对所有在澳运营的前沿 AI 企业制定严格安全标准：企业须接受独立模型评估，在开发和部署各阶段采取安全管控，并在发生安全事件后迅速向政府报告；监管机构有权对未履行义务的企业处罚。

这不是孤例。美国中期选举后，分析人士把联邦前沿 AI 安全法的通过窗口指向 2027 年初，纽约州已签署限制 AI 聊天机器人的法案；韩国隐私监管机构就设立 AI 隐私团队征求意见，英国则计划为生物识别和人脸识别建立新法定框架。AI 合规正在从"自愿承诺"变成"持证上岗"。

来源：[新华网](https://www2.xinhuanet.com/20261110/58df2577380a46deba8c2f6704bb0fbc/c.html)、[Simmons & Simmons](https://www.simmons-simmons.com/en/publications/cmw9h5dpz00siu48szeyphr1p/ai-view---november-2026)、[AI Governance Dashboard](https://aigov.solutions/)

## 其他快讯

- **DeepSeek 因算力不足限额**：11 月 16 日起，App/网页版不再支持超过 7 天不活跃的长对话，单次输入上限缩至约 4 万字，并限制每日对话额度；用量触顶后提示"服务器繁忙"。
- **OpenAI 与 TensorWave 签 6 年算力协议**：后者将在美国多个数据中心提供总计 457MW 的 AMD Instinct MI455X 算力，采用 Helios 机架级系统，2027 年上半年开始交付，2028 年初完成部署。
- **腾讯混元 Hy4 flash 发布**：总参数 224B（含 64B Engram 参数），激活 12B，支持多模态和 1M 上下文，输入 0.5 元、输出 2 元每百万 tokens，缓存命中 0.02 元。
- **豆包工作上线"工作台"**：首批覆盖金融、医疗、教育、创意设计等 21 个专业场景，已上线电脑版。

来源：[界面新闻 AI 早报](http://m.163.com/dy/article/LBU3EL6D0534A4SC.html)

## 今日趋势点评

今天所有新闻其实在说同一件事：资本和算力正在同时向头部集中。Anthropic 用"3 天适配 AMD"给 IPO 估值递投名状，英伟达用 Rubin 的 MLPerf 横扫证明自己还坐在牌桌中央，AMD 则直接买下 World Labs 补模型生态——三家都在为"万亿美元级别的 AI 基础设施"讲同一个故事。产品侧的竞争焦点则已经从"参数多大"变成"单位任务多便宜、能不能落到端侧和真机"：Qwen4-Max 降价六成、微软把 138B 模型塞进本地、华为开源具身世界模型，都是这个逻辑。监管端，澳大利亚的强制立法和美欧的立法预期说明，前沿 AI 的合规成本正在从"自愿承诺"转为"法定义务"，这笔账迟早要算进模型公司的单位经济里。
