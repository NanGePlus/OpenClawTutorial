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

## 本节文件一览


| 文件                                 | 作用                                                                                                                 |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **[AGENTS.md](./AGENTS.md)**       | 工作区「总规」：首次运行读 `BOOTSTRAP.md`、每次会话启动要读哪些文件、`MEMORY.md` 与 `memory/日期.md` 的分工、红线、群聊策略等。**具体怎么干活、优先级、操作规则**优先写在这里。     |
| **[SOUL.md](./SOUL.md)**           | **气质与边界**：口吻、是否简短、有没有观点、幽默尺度、私域与群聊边界等。                                                                             |
| **[USER.md](./USER.md)**           | **为谁服务**：称呼、时区、备注等。                                                                                                |
| **[IDENTITY.md](./IDENTITY.md)**   | **智能体自称是谁**：名字、身份标签、气质、表情符号等。与 SOUL 互补——IDENTITY 偏「名片」，SOUL 偏「怎么说话、底线在哪」。                                          |
| **[BOOTSTRAP.md](./BOOTSTRAP.md)** | **首次开机引导**：和用户一起定名字、气质、写进 `IDENTITY.md` / `USER.md`、再一起打磨 `SOUL.md`。按 [AGENTS.md](./AGENTS.md) 约定，用完后可删除，避免长期重复执行。 |
| **[TOOLS.md](./TOOLS.md)**         | **环境与工具备忘**：SSH 别名、TTS 偏好等「只属于你的现场信息」；与可共享的 Skill 区分开。                                                             |
| **[HEARTBEAT.md](./HEARTBEAT.md)** | **周期性任务占位**：保持为空或仅注释可跳过 heartbeat；需要定期检查的事项可写在模板里。                                                                 |
| **[MEMORY.md](./MEMORY.md)**       | 长期记忆主文件一般由智能体或你在工作区中**按需创建**。加载策略见 [AGENTS.md](./AGENTS.md)。                                                       |
| **memory/YYYY-MM-DD.md**           | **按日流水**：同样通常在工作区里**按需创建** `memory/` 后写入；与 `MEMORY.md` 搭配，详见 [AGENTS.md](./AGENTS.md)。                             |


### 推荐阅读顺序

1. **新工作区第一次用**：先看 **[首次上手.md](./首次上手.md)**（你怎么开场、说完后应落哪些文件），再按需打开 **[BOOTSTRAP.md](./BOOTSTRAP.md)** 与智能体对齐流程。
2. 通读 **[AGENTS.md](./AGENTS.md)**，建立对工作区规则的整体印象。
3. 看 **[IDENTITY.md](./IDENTITY.md)**、**[SOUL.md](./SOUL.md)**、**[USER.md](./USER.md)**，理解「智能体是谁 / 怎么说话 / 用户是谁」。
4. 与智能体对话定稿后，把约定写回上述文件；BOOTSTRAP.md用毕可删。
5. 有固定设备或别名：往 **[TOOLS.md](./TOOLS.md)** 记一笔。
6. 需要周期巡检：再动 **[HEARTBEAT.md](./HEARTBEAT.md)**。

---

## 位置对照


| 位置                                    | 用途                                                                                          |
| ------------------------------------- | ------------------------------------------------------------------------------------------- |
| **工作区**（默认多为 `~/.openclaw/workspace`） | `AGENTS.md`、`SOUL.md`、`USER.md`、`IDENTITY.md`、`MEMORY.md`、`memory/`、`TOOLS.md` 等，可被智能体按策略读写 |
| `~/.openclaw/`                        | `openclaw.json`、会话、凭证等；**不要**把人设长文当笔记全堆在这里                                                  |


---

## 实践建议

1. **先写「最小可用」**：SOUL 控语气，USER 写清称呼与时区，MEMORY 只收「以后每次都可能要用」的事实。
2. **对话里定下的规则，回写到文件**；不要只留在某次 prompt。
3. **定期裁剪**：`MEMORY.md` 与每日笔记里过时内容删掉或合并；SOUL 越精炼往往越稳。
4. **私库备份**：工作区常含隐私，可用**私有 Git** 备份；**不要**把密钥、token 写进这些 Markdown。

---

## 小结

- **首次上手.md** → 你第一次怎么开场、开场白示例、写回哪些文件。  
- **AGENTS.md** → 工作区怎么启动、记忆怎么用、红线与群聊。  
- **SOUL.md** → 怎么说话、性格与边界。  
- **USER.md** → 为谁服务、如何称呼、背景上下文。  
- **IDENTITY.md** → 智能体对外「我是谁」的固定名片信息。  
- **BOOTSTRAP.md** → 首次和用户一起把上面几样填实（用完可删）。  
- **MEMORY.md** + **memory/日期.md** → 长期沉淀与流水（在工作区中创建与维护）。  
- **TOOLS.md** / **HEARTBEAT.md** → 环境与周期任务备忘。

