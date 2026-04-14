# 05 让 OpenClaw 更懂你

OpenClaw 把智能体的**人设、对用户的了解、可持久化的记忆**，以及**怎么干活**，拆到 Agent **工作区（workspace）** 根目录的 **Markdown** 里。模型不会凭空记住你没写下来的东西——**写进工作区文件的内容，才会在后续会话里稳定参与加载**。

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

- 理解 OpenClaw 如何通过工作区 Markdown 文件（如 AGENTS.md、SOUL.md、USER.md、IDENTITY.md、MEMORY.md 等）管理智能体人设、用户信息与长期记忆。
- 掌握各配置、记忆、引导文件的作用及推荐组织方法，学会根据实际需求补充、裁剪内容。
- 能根据工作区范式优化人设书写与信息持久化，提升对话稳定性与定制化体验。
- 学会为助手和自己“定人设”：用一段话交代“助手是谁、你是谁、协作内容、不能自作主的事”，然后要求写入对应 Markdown 文件（IDENTITY.md、USER.md、SOUL.md等），实现长期记忆与约束落盘。
- 明白首次使用的最佳实践：主动补齐智能体与用户信息、协作边界和风格、常用设备等，并指导如何回写并维护这些信息。
- 理解「成长飞轮」：先真实试用，再发现和纠正偏差，把反馈写入规则/记忆文件，持续优化助手与用户的匹配度。
- 能参考自检清单，检查各文件内容是否充分反映出人设、用户、范围、红线等关键信息，并定期维护和更新。

---

待更新

