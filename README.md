# 零基础上手 OpenClaw 实战：从零打造智能体驱动的商业自动化闭环

## 本系列视频定位

会先帮助大家建立对 OpenClaw **自托管 Gateway** 的整体认识，接着完成**环境准备、安装部署、飞书接入**，再用 **工作区 Markdown** 固化人设与记忆，最后通过**资讯简报、公众号采集、对话装 Skill** 三个场景完成能力跑通。后续还会持续更新，让大家在能力跑通之后也能获得最新内容。

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

## 本系列视频链接地址速查

**【整体介绍】零基础上手 OpenClaw 实战：从零打造智能体驱动的商业自动化闭环。跟着南哥一起养龙虾，一起调教你的专属常驻型数字员工。**

- YouTube频道对应视频: [https://youtu.be/T5bvvEnvXgI](https://youtu.be/T5bvvEnvXgI)     
- B站频道对应视频: [https://www.bilibili.com/video/BV1svQGBBERQ/](https://www.bilibili.com/video/BV1svQGBBERQ/)        

**（1）【EP01_OpenClaw介绍】零基础上手 OpenClaw 实战：从零打造智能体驱动的商业自动化闭环。跟着南哥一起养龙虾，一起调教你的专属常驻型数字员工。**        
- YouTube频道对应视频: [https://youtu.be/zfoB5dbj0Ag](https://youtu.be/zfoB5dbj0Ag)      
- B站频道对应视频: [https://www.bilibili.com/video/BV1QvQnB6EBR/](https://www.bilibili.com/video/BV1QvQnB6EBR/)
- 资料在 01_*** 文件夹，下载即可          

**（2）【EP02_准备工作】零基础上手 OpenClaw 实战：从零打造智能体驱动的商业自动化闭环。实操Windows安装WSL2及Ubuntu，大模型服务选型。**          
- YouTube频道对应视频: [https://youtu.be/c2DTfUjd-lI](https://youtu.be/c2DTfUjd-lI)       
- B站频道对应视频: [https://www.bilibili.com/video/BV17td4B5EXx/](https://www.bilibili.com/video/BV17td4B5EXx/)         
- 资料在 02_*** 文件夹，下载即可             

---

## 适合的小伙伴

- 希望用 **飞书（含 Lark，其他也类似）** 作为入口，驱动 **带工具与记忆的智能体** 的开发者、运营与重度个人用户。  
- 已具备基础 AI 对话能力，愿意按后续文档完成 **Node 环境、API Key、插件配置** 等的动手型小伙伴。  
- 能接受「先跑通再优化」：先让 Gateway 与飞书绿通，再迭代工作区与定时任务，最后渐进式迭代。

---

## 开始前准备（视频中也会带着大家一起做的）

- 可联网电脑；能使用终端（macOS / Linux / **Windows 下 WSL2+Ubuntu** 与教程更一致）。  
- **Node.js**：以 03 安装部署 为准（推荐 Node 24）。  
- 已选定 **模型供应商** 并准备 **API Key**（引导 `openclaw onboard` 会用到）。  
- **飞书 / Lark 账号**（个人或企业），用于 04 插件接入；阅读安全与合规提示后再开权限。  
- 能阅读、编辑 **Markdown**（工作区规则与人设文件均为 Markdown）。

---

## 学完后你能做什么


| 能力域           | 对应章节                    | 能力描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------- | ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **整体认知**      | `01_OpenClaw介绍`         | （1）帮助你建立对 OpenClaw 的整体理解，把它作为“数字员工”而不仅仅是工具来认知。（2）理解 OpenClaw 的核心原理，包括自托管、支持多渠道接入以及智能体的长期协作与记忆。（3）通过具体场景和分工逻辑，认识 OpenClaw 在自动化、定时任务等方面的优势，以及它与 Cursor、Claude Code 等工具的互补关系。（4）打好基础，为后续环境部署、渠道对接等环节做好心理和操作准备。                                                                                                                                                                                                                                                                |
| **部署决策**      | `02_准备工作`               | （1）理清不同操作系统环境下部署 OpenClaw 的最佳实践，助力设备与系统选型。（2）明确如何规划与准备宿主设备，权衡主力机、备用机、云主机等多种场景。（3）系统梳理模型服务的访问方案与网络要求，保障后续连通性。（4）搞懂模型选型、API Key 获取、消息入口准备等核心环节。（5）Windows 下通过 WSL2+Ubuntu 达成与主流教程一致的部署路径具体实践。（6）总结常见准备过程中的坑点与误区，为顺利部署排除隐患。                                                                                                                                                                                                                                                   |
| **安装运行**      | `03_OpenClaw安装部署`       | （1）完成 OpenClaw CLI 的标准安装、验证与卸载流程，并确保 openclaw 命令可用。（2）成功运行 onboarding 引导，配置好所需大模型供应商及其 API Key。（3）Gateway 启动无误，可以通过控制面板发送消息并从模型获得回复，验证基本功能正常。                                                                                                                                                                                                                                                                                                                              |
| **飞书互通**      | `04_OpenClaw接入飞书`       | （1）学会在已部署 OpenClaw Gateway 的前提下，安装并配置飞书官方插件 `@larksuite/openclaw-lark`。（2）成功将 OpenClaw 与飞书（含 Lark 国际版）机器人集成，实现消息互通与自动回复。（3）理解插件授权、安全边界、数据访问范围，并掌握基础合规注意事项。（4）能通过飞书对话及命令，如 `/feishu start`、`/feishu auth` 验证插件功能可用性。（5）了解插件的能力覆盖范围（消息、文档、表格、日历等）及主要使用场景。                                                                                                                                                                                                                    |
| **人格与记忆**     | `05_让OpenClaw更懂你`       | （1）理解 OpenClaw 如何通过工作区 Markdown 文件（如 AGENTS.md、SOUL.md、USER.md、IDENTITY.md、MEMORY.md 等）管理智能体人设、用户信息与长期记忆。（2）掌握各配置、记忆、引导文件的作用及推荐组织方法，学会根据实际需求补充、裁剪内容。（3）能根据工作区范式优化人设书写与信息持久化，提升对话稳定性与定制化体验。（4）学会为助手和自己“定人设”：用一段话交代“助手是谁、你是谁、协作内容、不能自作主的事”，然后要求写入对应 Markdown 文件（IDENTITY.md、USER.md、SOUL.md等），实现长期记忆与约束落盘。（5）明白首次使用的最佳实践：主动补齐智能体与用户信息、协作边界和风格、常用设备等，并指导如何回写并维护这些信息。（6）理解「成长飞轮」：先真实试用，再发现和纠正偏差，把反馈写入规则/记忆文件，持续优化助手与用户的匹配度。（7）能参考自检清单，检查各文件内容是否充分反映出人设、用户、范围、红线等关键信息，并定期维护和更新。 |
| **定时资讯简报**    | `06_资讯简报助手`             | （1）学会 OpenClaw OpenClaw 为你省下第一波时间的第一个自动化场景应用，生成并推送「AI Agent 领域」的结构化资讯简报，包括即时检索与定时任务两种场景。（2）掌握「结构化简报」的内容框架与整理要求，包括多渠道汇总、信息摘要、可执行建议及出处规范。（3）理解如何自定义简报推送方式（如飞书群）、设置推送时机，并根据需求灵活调整任务模板与推送目标。                                                                                                                                                                                                                                                                                   |
| **公众号采集落库**   | `07_公众号文章采集助手`          | （1）掌握通过公众号 RSS 获取当日新发文章的全流程，包括验证采集能力、提供数据源、限定当天范围与字段格式，确保拉取内容准确。（2）学会根据规范对每篇文章进行结构化整理，输出包括标题、摘要、原始链接、来源名称、发布时间、机器标签等关键字段，方便后续归档与自动化处理。（3）能够将采集结果通过 OpenClaw 自动写入飞书多维表格，并掌握表格新建、指定、字段匹配及数据回传的方式。（4）理解定时任务配置，实现每日固定时间自动采集与写入，满足资讯留存与日常运营需求。（5）熟悉与飞书权限、插件配置的联动注意事项，为不同环境下稳定采集与落库打下基础。                                                                                                                                                                                         |
| **对话装 Skill** | `08_给OpenClaw加技能Skills` | （1）理解什么是 Skill，以及 Skill 与插件/大模型的区别和定位，掌握 Skill 的核心价值与作用。（2）学会在 OpenClaw 对话中动态查看、安装和使用 Skill，让助理按规范和流程处理日历/日程等任务，显著提升效率与稳定性。（3）能够通过一句话“注入新能力”，让个人助理自动获得并执行特定技能，实现更省描述、精准触发的工作流。（4）熟悉 Skill 的典型适用场景、安装步骤及常见问题应对方法，为后续灵活扩展助理能力打下基础。                                                                                                                                                                                                                                           |


---

## 学习建议

1. **顺序尽量不打乱**：04 依赖 03；06～08 依赖 04 与 05 的基本就绪（推送、表格、日历等视插件权限而定）。
2. **合规与预览**：飞书写入、代发消息多不可撤销；重要操作先预览，企业账号遵守内控。
3. **工作区可备份**：用私有 Git 管理 workspace，勿将 API Key、token 写入 Markdown。
4. **记录排错笔记**：现象 + 日志关键词 + 解决办法，便于下次秒定位。

