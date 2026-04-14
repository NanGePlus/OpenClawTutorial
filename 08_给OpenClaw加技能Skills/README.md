# 08 给 OpenClaw 加技能 Skills

本期视频的核心是：让 OpenClaw 具备**在对话中动态安装、使用 Skill** 的能力，把日历/日程等内容**稳定沉淀进你的工作流**。**用一句话把新能力注入个人助理**。

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

- 理解什么是 Skill，以及 Skill 与插件/大模型的区别和定位，掌握 Skill 的核心价值与作用。
- 学会在 OpenClaw 对话中动态查看、安装和使用 Skill，让助理按规范和流程处理日历/日程等任务，显著提升效率与稳定性。
- 能够通过一句话“注入新能力”，让个人助理自动获得并执行特定技能，实现更省描述、精准触发的工作流。
- 熟悉 Skill 的典型适用场景、安装步骤及常见问题应对方法，为后续灵活扩展助理能力打下基础。

---

## Skill 是什么，不是什么


| 说法     | 含义                                                                            |
| ------ | ----------------------------------------------------------------------------- |
| **不是** | Skill **不是**大模型本身，**不是**传统意义上的「插件」或「App 商店里的 App」。                            |
| **是**  | Skill 是一套让 AI **更稳定地完成某类任务**的「**操作说明书**」：流程、边界、输出格式写清楚后，同类任务会更准、更规范、更省你的描述成本。 |


**你现在只需要记住一件事：**

- **没有 Skill**：每次靠你口头描述需求，模型临场发挥，结果波动大。  
- **有了 Skill**：AI 按固定流程执行，你往往**一句话触发**，它按规范做完。

---

## 场景：**在对话中动态安装、使用**日历/日程 Skill

### 轮次 1：问 AI 查看当前有哪些 Skill 可用

直接说（把「日历/提醒/任务类」换成你选的类型）：

> 帮我看看当前可以用哪些 Skill？我对 **日历/提醒/任务类** 比较感兴趣。

AI 会列出当前环境里的可用 Skill；你在列表里找与目标类型匹配的一项，**记下准确名称**。

**常见情况怎么处理：**


| 情况                  | 建议话术 / 动作                                                                                                            |
| ------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **列表为空**            | 「帮我安装一个**日历/提醒/任务类**的 Skill，推荐一个社区常用的；也可以去 [clawhub.com](https://clawhub.com) 上搜。」装完后说：「帮我验证这个 Skill 装好了，能不能在列表里找到。」 |
| **有 Skill 但不知道选哪个** | 「我想做 **日历/提醒/任务类**，帮我推荐一个最合适的 Skill，并说明它能做什么。」                                                                       |


---

### 轮次 2：让 AI 说明该 Skill 的运行条件

把下面示例里的 `**<Skill 名称>`** 换成你在 轮次 1 记下的名字，例如 `feishu-calendar-manager`：

> 帮我看看 `**<Skill 名称>`** 这个 Skill 的详情，我这里能不能直接用？

AI 会说明依赖与前提，并判断当前环境是否满足。

**常见情况：**


| 情况          | 建议                               |
| ----------- | -------------------------------- |
| **满足，可直接试** | 进入 轮次 3。                         |
| **有条件不满足**  | 「这个条件我不满足，帮我一步步处理。」由 AI 引导授权或配置。 |
| **看不懂条件**   | 把 AI 的说明贴回去：「用大白话说一下，我需要做什么？」    |


---

### 轮次 3：在对话里实际触发 Skill

用**自然语言、最小输入**先试一次，确认能跑通，再扩大场景。

**触发示例：**

> 帮我设一个明天上午 10 点的提醒：跟进 XXX 项目进度。

**第一次试跑原则：**

1. 只用**最小输入**（一句话里关键信息尽量完整）。
2. **成功后再**加复杂场景。
3. **失败先排当前这个 Skill**，不要立刻换别的 Skill 逃避排错。

**若结果不理想：**


| 现象                    | 建议                                                           |
| --------------------- | ------------------------------------------------------------ |
| **运行报错**              | 把完整报错贴给 AI：「帮我看看这里出了什么问题。」                                   |
| **AI 理解意图但没调用 Skill** | 多半是触发词与 Skill 预设不一致。问：「这个 Skill 的触发条件是什么，我应该怎么说？」再换更接近的说法重试。 |
| **换了一个 Skill 也成功**    | 以**能稳定成功**的那个为准；并请 AI 把用法记入 `MEMORY.md`（见下文）。                |


---

### 轮次 4（闭环）：把用法写进 MEMORY.md

**Skill 装完建议立刻做的一件事：** 成功跑通后，对 AI 说（把 Skill 名与用途换成你的实际情况）：

> Skill 名称：这是给 AI 看的“身份证号”，防止它调错工具。
> 触发词：这是你习惯的口语，记录下来是为了让 AI 建立“你的语言”与“工具”之间的映射。
> 成功样例：这是最关键的“标准答案”。下次 AI 犹豫时，它会参考这个样例，确保输出格式和你上次满意的一模一样。
> 参考这个格式，把我刚才跑通的这个 Skill 记到 MEMORY.md 里。

### 在 MEMORY.md 里建议写什么？

核心目标：**让 AI 下次看到你的指令，能快速对应到正确的 Skill 与格式。**

**日历提醒（工具型 Skill）**

- **Skill 名称（示例）**：`feishu-calendar-manager`  
- **触发词（示例）**：帮我记一下、提醒我、预约会议、设个闹钟

记录样例：

```text
Skill: 飞书日历助手 (feishu-calendar-manager)
触发方式：包含时间、地点、事件的自然语言指令。
成功样例：「提醒我明天下午 2 点在 302 会议室开选题会。」
```

**为什么要写这三块？**


| 块            | 作用                              |
| ------------ | ------------------------------- |
| **Skill 名称** | 相当于「身份证号」，减少调错工具。               |
| **触发词**      | 把你习惯的口语和工具绑在一起。                 |
| **成功样例**     | 给 AI 一个「标准答案」，输出格式更容易与上次满意结果对齐。 |


---

## 有了 Skill 之后，如何用自然语言调用？

有了 `MEMORY.md` 里的记录，你不必背复杂指令，像吩咐数字员工一样说话即可。

> 帮我记一下，明天下午两点在南哥办公室开选题会。

1. **直接触发（最常用）**
  使用你在 `MEMORY.md` 里记下的触发词。后台大致是：接收指令 → 结合工作区记忆 → 匹配到对应 Skill → 抽取参数 → 执行。
2. **模糊触发（靠语义 + 样例）**
  触发词不完全一致也可以，模型可结合 `MEMORY.md` 里的成功样例做推理（仍可能失败，以实测为准）。
3. **补全触发（交互式）**
  若信息不全，AI 可能反问关键信息（时间、对象、存到哪里等），补全后再调用 Skill。

**核心逻辑（示意图）**

```mermaid
flowchart LR
  A[用户自然语言] --> B[结合工作区 / MEMORY.md]
  B --> C[匹配触发词与样例]
  C --> D[调用对应 Skill]
  D --> E[输出结果]
```



说明：在飞书、终端等入口输入一段话时，OpenClaw 侧通常会结合**工作区里的长期说明与记忆**（例如 `MEMORY.md`）再决定如何执行 Skill；把触发词与样例写清楚，能减少「每次从头想怎么做」的成本。

---

## 本节小结

Skill 是给 AI **加稳定能力**的一种方式：**查可用 → 看条件 → 对话触发 → 试完记下**。安装与验证尽量在对话里闭环，装完用 `MEMORY.md` 固化触发词与样例，下次一句话即可复用。**原则：少而精，装完必试，试完必记。**
