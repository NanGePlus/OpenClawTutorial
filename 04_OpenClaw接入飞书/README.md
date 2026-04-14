# 04 接入飞书 OpenClaw 官方插件

飞书（Feishu）是国内主流的团队协作与 IM 平台，广泛应用于企业沟通、文档协作、日历管理等场景，支持丰富的开放平台能力。其国际版对应 **Lark**，两者插件用法一致。[OpenClaw 接入飞书](https://bytedance.larkoffice.com/docx/MFK7dDFLFoVlOGxWCv5cTXKmnMh)

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

- 学会在已部署 OpenClaw Gateway 的前提下，安装并配置飞书官方插件 `@larksuite/openclaw-lark`。
- 成功将 OpenClaw 与飞书（含 Lark 国际版）机器人集成，实现消息互通与自动回复。
- 理解插件授权、安全边界、数据访问范围，并掌握基础合规注意事项。
- 能通过飞书对话及命令，如 `/feishu start`、`/feishu auth` 验证插件功能可用性。
- 了解插件的能力覆盖范围（消息、文档、表格、日历等）及主要使用场景。

---

待更新
