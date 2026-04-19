# 06 资讯简报助手：AI Agent 领域日报 + 飞书推送

本期视频说明 OpenClaw 为你省下第一波时间的第一个自动化场景应用，完成两类需求：**即时检索并推送简报**，以及**每天固定时间自动执行同一套流程**（定时任务）。核心产出是一份**结构化简报**。

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

- **零基础上手 LangChain V1.x 实战： 学最主流Agent开发框架**：      
B站视频链接：[https://www.bilibili.com/video/BV17c6mBbEHv/](https://www.bilibili.com/video/BV17c6mBbEHv/)     
YouTube视频链接：[https://www.youtube.com/playlist?list=PL8zBXedQ0ufld2C7nB28fGw9U6nTbagp1](https://www.youtube.com/playlist?list=PL8zBXedQ0ufld2C7nB28fGw9U6nTbagp1)      
GitHub地址：[https://github.com/NanGePlus/LangChain_V1_Test](https://github.com/NanGePlus/LangChain_V1_Test)     
Gitee地址：[https://gitee.com/NanGePlus/LangChain_V1_Test](https://gitee.com/NanGePlus/LangChain_V1_Test)       
- **零基础上手 n8n v2.x 实战：打造n8n驱动的自动化生产线**：        
B站视频链接：[https://www.bilibili.com/video/BV1Aq1NBYELp/](https://www.bilibili.com/video/BV1Aq1NBYELp/)        
YouTube视频链接：[https://www.youtube.com/playlist?list=PL8zBXedQ0uflhkZBwlQNAp7H57CJFgfgV](https://www.youtube.com/playlist?list=PL8zBXedQ0uflhkZBwlQNAp7H57CJFgfgV)         
GitHub地址：[https://github.com/NanGePlus/N8NWorkflowsTest](https://github.com/NanGePlus/N8NWorkflowsTest)        
Gitee地址：[https://gitee.com/NanGePlus/N8NWorkflowsTest](https://gitee.com/NanGePlus/N8NWorkflowsTest)                  
- **2026 AI编程 Cursor：专为提升开发生产力而设计的一款AI提效工具**：         
B站视频链接：[https://www.bilibili.com/video/BV1HEABzvEdo/](https://www.bilibili.com/video/BV1HEABzvEdo/)       
YouTube视频链接：[https://www.youtube.com/playlist?list=PL8zBXedQ0ufkcPJWHVKFTFzS8yNCkfM5b](https://www.youtube.com/playlist?list=PL8zBXedQ0ufkcPJWHVKFTFzS8yNCkfM5b)       
- **更多开源项目**       
GitHub地址：[https://github.com/NanGePlus](https://github.com/NanGePlus)         
Gitee地址：[https://gitee.com/NanGePlus](https://gitee.com/NanGePlus)       

---

## 本节目标

- 学会 OpenClaw 为你省下第一波时间的第一个自动化场景应用，生成并推送「AI Agent 领域」的结构化资讯简报，包括即时检索与定时任务两种场景。
- 理解如何自定义简报推送方式（如飞书群）、设置推送时机，并根据需求灵活调整任务模板与推送目标。

---

## 你能得到什么


| 能力       | 说明                                                                |
| -------- | ----------------------------------------------------------------- |
| **即时简报** | 按需检索「今日 AI Agent 领域」动态，整理后发送给你或指定飞书群。                             |
| **定时简报** | 例如每天 **16:00** 自动跑同一套检索与整理，再推送到飞书。                                |
| **简报结构** | **3 条**最重要的信息摘要 + **1 条**面向行业实践者的可执行建议；内容需**准确、简明**，并附**可靠来源链接**。 |


---

## 场景一：**即时检索并推送简报**

适合「现在就想要一份今日简报」，并在对话里逐步约定接收方式。

**示例话术：**

> 请帮我自动检索今日 AI Agent 领域的最新动态资讯，内容需涵盖权威媒体、社区论坛及行业报告。请将检索结果整理为一份结构化简报：包括 3 条最重要的信息摘要及 1 条针对行业实践者的可执行建议。整理完成后，请将该简报自动发送至指定飞书群组，确保内容准确、简明，并附可靠来源。

**使用提示：**

- 首轮可写清领域（上例为 AI Agent）、渠道偏好与简报格式。
- **多轮对话**中可补充：发给自己、发到哪个飞书群、群名/机器人配置是否已就绪等；以你当前 OpenClaw 与工作区里对「飞书 / 通知」的约定为准。

---

## 场景二：**每天固定时间自动执行同一套流程**（定时任务）

适合「每天同一时间自动出报」，减少重复口述需求。

**示例话术：**

> 请帮我创建一个每天下午 16 点的定时任务，自动检索今日 AI Agent 领域的最新动态资讯，内容需涵盖权威媒体、社区论坛及行业报告。请将检索结果整理为一份结构化简报：包括 3 条最重要的信息摘要及 1 条针对行业实践者的可执行建议。整理完成后，请将该简报自动发送至指定飞书群组，确保内容准确、简明，并附可靠来源。

**使用提示：**

- 创建定时任务后，仍可通过后续对话**修改时间、推送目标或简报模板**（具体取决于你使用的调度与 Agent 能力）。
- 若工作区中有 **[HEARTBEAT.md](../05_让OpenClaw更懂你/HEARTBEAT.md)** 或与周期任务相关的约定，可与智能体对齐是否要把该日报写进工作区规则，避免与其它 heartbeat 冲突。

---

## 小结

本页介绍了如何通过 OpenClaw 实现「AI Agent 行业简报」的自动化推送，无论是主动请求还是定时每日生成，都可以自定义内容结构和推送目标。通过工作区相关约定与多轮对话，可灵活调整需求，确保日报准确、高效、落地到实际使用场景。
