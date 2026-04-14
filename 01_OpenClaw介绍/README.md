# 01 OpenClaw 介绍

本期视频对 OpenClaw 的定位、能力和上手路径做概览，便于大家在安装与接渠道前建立整体认识。更完整的说明、各渠道分步教程与排错入口，请以 **[OpenClaw 官方文档](https://docs.openclaw.ai/)** 为准。

### 本系列仓库位置

以下仓库存储我在YouTube频道和B站频道关于零基础上手 OpenClaw 实战相关分享所有源文件，均开源免费  

- GitHub地址: [https://github.com/NanGePlus/OpenClawTutorial](https://github.com/NanGePlus/OpenClawTutorial)
- Gitee地址: [https://gitee.com/NanGePlus/OpenClawTutorial](https://gitee.com/NanGePlus/OpenClawTutorial)

### 我的个人信息

- YouTube频道(@南哥AGI研习社)：[https://www.youtube.com/channel/UChKJGiX5ddrIpJG-rBNVZ5g](https://www.youtube.com/channel/UChKJGiX5ddrIpJG-rBNVZ5g)
- B站频道(@南哥AGI研习社)：[https://space.bilibili.com/509246474](https://space.bilibili.com/509246474)
- GitHub地址：[https://github.com/NanGePlus](https://github.com/NanGePlus)
- Gitee地址：[https://gitee.com/NanGePlus](https://gitee.com/NanGePlus)
- 大模型代理平台: [https://nangeai.top/](https://nangeai.top/)

### 其他开源分享推荐

- **LangChain系列**：最新V1.x版本全家桶LangChain+LangGraph+DeepAgents  
B站视频链接：[https://www.bilibili.com/video/BV17c6mBbEHv/](https://www.bilibili.com/video/BV17c6mBbEHv/)
YouTube视频链接：[https://www.youtube.com/playlist?list=PL8zBXedQ0ufld2C7nB28fGw9U6nTbagp1](https://www.youtube.com/playlist?list=PL8zBXedQ0ufld2C7nB28fGw9U6nTbagp1)
GitHub地址：[https://github.com/NanGePlus/LangChain_V1_Test](https://github.com/NanGePlus/LangChain_V1_Test)  
Gitee地址：[https://gitee.com/NanGePlus/LangChain_V1_Test](https://gitee.com/NanGePlus/LangChain_V1_Test)
- **n8n系列**：最新n8n自动化工作流平台
B站视频链接：[https://www.bilibili.com/video/BV1Aq1NBYELp/](https://www.bilibili.com/video/BV1Aq1NBYELp/)
YouTube视频链接：[https://www.youtube.com/playlist?list=PL8zBXedQ0uflhkZBwlQNAp7H57CJFgfgV](https://www.youtube.com/playlist?list=PL8zBXedQ0uflhkZBwlQNAp7H57CJFgfgV)  
GitHub地址：[https://github.com/NanGePlus/N8NWorkflowsTest](https://github.com/NanGePlus/N8NWorkflowsTest)
Gitee地址：[https://gitee.com/NanGePlus/N8NWorkflowsTest](https://gitee.com/NanGePlus/N8NWorkflowsTest)                
- **Cursor系列**：专为提升开发生产力而设计的一款AI提效工具
B站视频链接：[https://www.bilibili.com/video/BV1HEABzvEdo/](https://www.bilibili.com/video/BV1HEABzvEdo/)
YouTube视频链接：[https://www.youtube.com/playlist?list=PL8zBXedQ0ufkcPJWHVKFTFzS8yNCkfM5b](https://www.youtube.com/playlist?list=PL8zBXedQ0ufkcPJWHVKFTFzS8yNCkfM5b)
- **更多开源项目**
GitHub地址：[https://github.com/NanGePlus](https://github.com/NanGePlus)
Gitee地址：[https://gitee.com/NanGePlus](https://gitee.com/NanGePlus)

---

## 本节目标

- 帮助你建立对 OpenClaw 的整体理解，把它作为“数字员工”而不仅仅是工具来认知。
- 理解 OpenClaw 的核心原理，包括自托管、支持多渠道接入以及智能体的长期协作与记忆。
- 通过具体场景和分工逻辑，认识 OpenClaw 在自动化、定时任务等方面的优势，以及它与 Cursor、Claude Code 等工具的互补关系。
- 打好基础，为后续环境部署、渠道对接等环节做好心理和操作准备。

## OpenClaw 是什么

### 偏通俗点理解

**不要把 OpenClaw 讲成“一个 AI 软件”，而要讲成：它更像一个可以长期协作、可以接工具、可以被训练、可以安排定时工作、可以沉淀工作方法的数字员工。**

这里有一个观念，大家一定要扭转过来：**把 OpenClaw 当成一个人去用，而不是当成一个工具去用。**

大家可以想一想，在你我的身边，对于一个刚入职的新人，是如何去带他的？肯定不会只给他下命令，对吧？你会培养他、教育他、给他反馈、帮他纠偏、给他明确分工、设好工作边界。对 OpenClaw，大家也得这么干。

如果只是临时丢一句话，让他“帮我弄一下”，那他就只能像一个临时工，干完就忘，下次还得从头教。但如果你长期告诉他你的偏好、你的标准、你的习惯、你的工作方式，让他记住、复用、迭代，他才会越来越像一个熟悉你的老助手。

OpenClaw 特别适合做这个常驻型数字员工。因为他不是一个单纯聊天的网页，而是可以真正接工具、读写文件、调浏览器、执行命令、保存长期记忆、跑定时任务。也正因为如此，这里有个重要经验：**OpenClaw 最好不要和你自己的主力工作电脑混在一起用。**

最好给他一台独立的机器，比如云主机，或者家里的闲置电脑。不建议和自己的主力工作电脑放在一起，因为他会吃内存、吃资源，而且还会长期运行。建议至少 4G 内存，6G 以上更好。

大家要理解这背后的经营逻辑：这不是为了折腾技术架构，而是因为你在给一个数字员工准备工作环境。**给 OpenClaw 配机器，不是在装软件，而是在给数字员工安排工位。**

再讲大模型配置，直接告诉大家：如果你真的把 OpenClaw 当成长期高频使用的数字员工，那么按 API 调用次数付费，很多时候成本会很高。因为它不是偶尔回答一两个问题，而是可能每天都在跑任务、整理资料、读写上下文、做定时巡检、接收你的追问。

所以，在高频使用的场景下，包月套餐通常更合适，**包月更像给员工发固定薪水**。

### 偏官方点理解

OpenClaw 是一个 **自托管的网关（Gateway）**：在自己的电脑或服务器上运行 **一个** Gateway 进程，把常用的 **聊天与协作入口**（如飞书、Telegram、WhatsApp等）接到**支持工具调用、会话与记忆的 AI 智能体**上。

你可以把它理解成：**消息从各渠道（飞书）进来 → 由 Gateway 统一管理会话与路由 → 再调用大模型与工具给出回复**。数据与规则留在你的机器上，而不是依赖某家全托管聊天机器人（如Cursor）。

### 关于 OpenClaw 与 Cursor / Claude Code / Codex 的关系

**它们不是替代关系，而是分工关系。** 大家千万别想着用一个去替代另一个。正确的做法是，让 OpenClaw 把杂活都干了，把你的注意力解放出来，然后你才能有整块的时间，去和 Cursor、Claude Code 或 Codex 一起攻坚大活。

分工逻辑如下：

- **OpenClaw**：负责杂活、巡检、定时任务、资料流。它像一个常驻办公室的助理。
- **Cursor / Claude Code / Codex**：负责大活、重活、深度思考、方案设计。它们像你请来的专家顾问，陪你一起攻坚。

---

## 适合谁

- 希望在**手机或常用 IM 里**就能唤起个人助手，同时**不把对话与配置完全交给第三方托管**的开发者与重度用户。  
- 需要**多渠道共用同一套智能体能力**（工具、记忆、多会话隔离），并愿意自己维护一台常在线或可唤醒的宿主。

---

## 与其它方案相比，大致特点


| 维度        | 说明                                           |
| --------- | -------------------------------------------- |
| **自托管**   | 在你指定的硬件上运行，策略与数据边界由你控制。                      |
| **多渠道**   | 单一 Gateway 可同时对接内置渠道、捆绑插件渠道或外部渠道插件（以官方列表为准）。 |
| **面向智能体** | 为「会调工具、有多轮会话、可做多智能体路由」的场景设计，而非仅单轮问答。         |
| **开源**    | 项目以 MIT 协议开源，社区可参与扩展。                        |


官方文档还强调：为获得更好的效果与安全边界，在能力范围内宜选用**能力较强的新一代模型**；具体模型与供应商需在提供商侧申请**API 密钥**等凭证。

---

## 工作原理（简化理解）

**Gateway** 是会话、路由与各渠道连接的**中心节点**：渠道只负责「收发信息」，会话怎么延续、走哪个智能体、是否隔离工作区，由 Gateway 统一协调。这样你可以在多个入口发消息，却共享或按需隔离同一套后端能力。

---

## 主要能力概览

- **多渠道网关**：用同一 Gateway 进程对接多种聊天渠道（含 Web 端对话等能力）。  
- **插件型渠道**：通过插件扩展更多平台（如 Matrix、Nostr、Twitch、Zalo 等，随版本变化）。  
- **多智能体与会话路由**：可按智能体、工作区或发送方等维度做会话隔离。  
- **媒体**：支持收发图片、音频、文档等（具体上限与渠道能力以文档为准）。  
- **Web 控制界面**：浏览器内管理对话、配置与会话。  
- **移动端节点**：可配对 iOS / Android 节点，用于画布、相机、语音等延伸场景。

---

## 小结

OpenClaw 是一个自托管、可扩展的智能体网关，支持多渠道、工具和个性化自动化，适合追求数据可控与能力灵活结合的用户。