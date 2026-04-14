# 07 公众号内容采集助手：RSS 拉取 + 简报 + 飞书多维表格

本期视频说明 OpenClaw 为你省下第一波时间的第二个场景应用，完成两类需求：**通过公众号对应的 RSS 源**获取**当日新发**文章，按统一结构整理简报，并可选地**写入飞书多维表格**；以及把同一套流程做成**每天固定时间**的定时任务。

**说明：** 微信公众号正文在平台侧访问限制较多，实践中常用**第三方聚合 RSS** 作为数据源。能否稳定拉取全文、能否操作飞书多维表格，取决于你当前的 **OpenClaw 工具 / 飞书插件与权限** 配置，详见 [04 接入飞书](../04_OpenClaw接入飞书/README.md)。

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

- 掌握通过公众号 RSS 获取当日新发文章的全流程，包括验证采集能力、提供数据源、限定当天范围与字段格式，确保拉取内容准确。
- 学会根据规范对每篇文章进行结构化整理，输出包括标题、摘要、原始链接、来源名称、发布时间、机器标签等关键字段，方便后续归档与自动化处理。
- 能够将采集结果通过 OpenClaw 自动写入飞书多维表格，并掌握表格新建、指定、字段匹配及数据回传的方式。
- 理解定时任务配置，实现每日固定时间自动采集与写入，满足资讯留存与日常运营需求。
- 熟悉与飞书权限、插件配置的联动注意事项，为不同环境下稳定采集与落库打下基础。

---

待更新

