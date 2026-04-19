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

- 掌握通过公众号 RSS 获取当日新发文章的全流程，包括验证采集能力、提供数据源、限定当天范围与字段格式，确保拉取内容准确。
- 学会根据规范对每篇文章进行结构化整理，输出包括标题、摘要、原始链接、来源名称、发布时间、机器标签等关键字段，方便后续归档与自动化处理。
- 能够将采集结果通过 OpenClaw 自动写入飞书多维表格，并掌握表格新建、指定、字段匹配及数据回传的方式。
- 理解定时任务配置，实现每日固定时间自动采集与写入，满足资讯留存与日常运营需求。
- 熟悉与飞书权限、插件配置的联动注意事项，为不同环境下稳定采集与落库打下基础。

---

## 你能得到什么


| 能力        | 说明                                                    |
| --------- | ----------------------------------------------------- |
| **多轮对齐**  | 先确认「能否用 RSS 采集」、再给出 RSS、再约定「仅当天」与字段格式，降低一次性说漏的风险。     |
| **结构化简报** | 每篇文章输出固定字段（标题、摘要、正文、链接、来源、时间、标签等），便于归档与二次自动化。         |
| **飞书落库**  | 新建或指定「微信公众号文章采集库」类多维表格，把当天文章**逐条写入**，并回传表格链接。         |
| **定时采集**  | 例如每天 **16:00** 自动拉取指定公众号 RSS、过滤当天、生成同样结构并推送 + 写入同一张表。 |


---

## 结构化字段规范（与多维表格列一致）

下列字段在「对话里输出的简报」与「飞书多维表格」中应保持一致；**摘要**与**机器标签**须基于**完整正文**理解后生成，禁止简单截断正文或抄袭标题。


| 字段       | 类型 / 格式 | 要求                                                              |
| -------- | ------- | --------------------------------------------------------------- |
| **标题**   | 文本      | 使用文章原标题。                                                        |
| **摘要**   | 文本      | 阅读全文后高度概括核心信息，简明准确。                                             |
| **原始链接** | 文本      | 可访问的原文 URL。                                                     |
| **来源名称** | 文本      | 公众号名称（如「量子位」），不可遗漏。                                             |
| **发布时间** | 日期      | 实际发布时间，建议统一为 `2026-04-12 16:00` 这种**精确到分钟**的格式。                 |
| **机器标签** | 文本      | 基于全文归纳 **1～3 个**主题标签，英文逗号分隔（例：`AI, 量子计算, 行业动态`）；禁止抄标题/摘要或堆砌无关词。 |
| **创建时间** | 创建时间    | 仅在多维表格中由系统自动记录「写入时间」；对话简报可无此项或由模型说明。                            |


**当天过滤：** 仅处理 RSS 中**发布日为当天**的条目，不重复处理历史文章（「当天」以你与智能体约定的时区为准）。

---

## 场景一：即时采集并写入多维表格

适合第一次跑通流程：确认能力 → 给 RSS → 拉当天文章 → 建表 / 选表 → 写入。

### 轮次 1：确认是否具备采集能力

> 一白，你有获取指定微信公众号当日发布文章内容的能力吗？

### 轮次 2：确认使用 RSS 作为数据源

> 我待会给你公众号对应的 RSS 源，通过这个 RSS 源来进行获取，有没有问题？

### 轮次 3：提供 RSS，并要求只抓「今天」且按字段输出简报

> 下面是量子位微信公众号的 RSS 源地址：  
> `http://rss.jintiankansha.me/rss/GEYDQOJYPQYTEZDDGAYTMM3DMYYDIY3BMY2DINRQMQYDMOJUHAYGEN3EMQZTCM3CGYZTKNBTMM======`  
> 请你通过该 RSS 源获取「今天」（即获取当天发布）的所有文章。对于每一篇文章，请都按照下述格式，整理出一份结构化的文章简报，具体字段及要求如下：
>
> - **标题**：文章标题  
> - **摘要**：你需要阅读文章原文后自动生成简洁明了的摘要（高度概括文章核心内容，非简单截取正文）    
> - **原始链接**：文章的原始网址  
> - **来源名称**：该文章所属的微信公众号名称（如「量子位」）  
> - **发布时间**：文章实际的发布时间，格式保持为「2026-04-12 16:00」  
> - **机器标签**：请根据原文自动总结生成文章的主题标签，标签可有多个，最多 3 个，标签间用英文逗号分隔（例：AI, 量子计算, 行业动态）
>
> 注意事项：  
>
> 1. 摘要与机器标签均应基于文章完整内容自动生成，保证内容准确、精炼。
> 2. 机器标签需精准提炼文章主题，禁止直接抄袭标题或摘要。
> 3. 「来源名称」请填写对应的公众号名称，不要遗漏。
>
> 仅获取当天新发布的内容，无需处理历史文章。

### 轮次 4：查看自己可操作的多维表格

> 我可以操作的多维表格有哪些？

### 轮次 5：新建「微信公众号文章采集库」

> 请帮我新建一个名为「微信公众号文章采集库」的多维表格，用于后续结构化存储和管理采集到的微信公众号文章数据。具体需求如下：
>
> 1. **表格字段设置**
>   - **标题**：文本类型，用于存储每篇微信公众号文章的标题  
>   - **摘要**：文本类型，根据原文完整内容自动生成简洁、准确的摘要  
>   - **原始链接**：文本类型，填入每篇文章的原始网页地址  
>   - **来源名称**：文本类型，填写文章来源的微信公众号名称（如「量子位」），确保不要遗漏  
>   - **发布时间**：日期类型，格式要求为「2026-04-12 16:00」，用于记录文章实际的发布时间，需精确到分钟  
>   - **机器标签**：文本类型，要求你基于原文内容自动提炼出主题标签（可多个，最多 3 个，标签间用英文逗号分隔），需体现文章的核心主题，禁止抄袭标题或摘要  
>   - **创建时间**：创建时间类型，自动记录每条数据进入表格的时间
> 2. **期望**
>   - 创建完成后，请将该多维表格的链接发我，用于后续的数据录入和查看。  
>   - 请确保字段类型设置准确，尤其是日期等类型，便于后续数据的规范整理和自动化处理。

### 轮次 6：将当天文章写入该表

> 请将获取到的微信公众号文章按要求写入新建的「微信公众号文章采集库」多维表格，每篇文章务必完整、准确填写所有字段。注意：
>
> 1. 「摘要」字段需根据文章的完整原文进行智能分析和高度概括，自动生成简明扼要、覆盖核心内容的摘要，严禁简单截取正文或抄袭标题。
> 2. 「机器标签」需要基于原文内容自动归纳主题关键词，每篇文章可填 1 至 3 个主题标签，用英文逗号分隔，标签需精准反映内容重点，禁止抄袭标题、摘要或使用无关标签。
> 3. 「来源名称」必须填写对应的微信公众号名称（如「量子位」），确保来源信息准确无误、不可遗漏。
> 4. 仅需处理当天新发布的文章（即过滤掉历史文章），其余字段请严格按照表格设置的数据类型和格式填写，确保后续规范化管理和自动化处理的便捷性。

**使用提示：**

- 将示例中的「量子位」与 RSS 地址换成你自己的公众号与订阅源即可复用同一话术骨架。RSS订阅可通过该平台进行订阅：[http://www.jintiankansha.me/account/signup?invite_code=PJIFQVLQKJ](http://www.jintiankansha.me/account/signup?invite_code=PJIFQVLQKJ) 
- 工作区若需长期记住「默认 RSS、默认表、字段映射」，可写在 [05 让 OpenClaw 更懂你](../05_让OpenClaw更懂你/README.md) 下的 `AGENTS.md` / `TOOLS.md` 等文件中。

---

## 场景二：**每天固定时间自动执行同一套流程**（定时任务）

适合已跑通「RSS → 简报 → 多维表格」后，固定每日自动执行。

> 请帮我创建一个每天下午 16 点自动运行的定时任务，专门用于采集「量子位」微信公众号的当日最新文章。数据来源为其官方 RSS 源地址：  
> `http://rss.jintiankansha.me/rss/GEYDQOJYPQYTEZDDGAYTMM3DMYYDIY3BMY2DINRQMQYDMOJUHAYGEN3EMQZTCM3CGYZTKNBTMM======`
>
> 具体任务要求如下：
>
> 1. 每天定时抓取该 RSS 源中当天发布的全部新文章（需自动过滤掉历史文章，只采集当天的新内容）。
> 2. 对每一篇文章，自动完成如下「结构化简报」输出，字段要求如下：
>   - **标题**：提取文章原文标题  
>   - **摘要**：基于文章完整正文进行智能内容理解后，由 AI 总结生成。要求高度概括文章核心信息，禁止简单截取正文或直接抄袭原文标题  
>   - **原始链接**：填写每篇文章的原始网页链接  
>   - **来源名称**：填写微信公众号名称，统一用「量子位」  
>   - **发布时间**：记录文章实际发布时间，格式要求「2026-04-12 16:00」，需精确到分钟  
>   - **机器标签**：基于文章完整内容自动提炼 1 至 3 个主题标签，准确反映文章核心主题，用英文逗号分隔（示例：AI, 量子计算, 行业动态），严禁抄袭标题、摘要或使用无关标签
> 3. 采集结果应每日整理为结构化简报，推送给我并录入「微信公众号文章采集库」多维表格，确保以下要点：
>   - 所有字段信息均需完整、准确，格式统一，便于后续的数据管理和自动化处理  
>   - 重点要求「摘要」及「机器标签」为基于原文内容智能生成，高度概括且避免冗余、重复  
>   - 来源名称不可遗漏，务必标注为「量子位」

**使用提示：**

- 定时任务的**时区**与「当天」的日历边界要与你的使用地区一致，避免漏抓或重复。  
- 若与 [06 资讯助手](../06_资讯助手/README.md) 等其它定时任务并存，建议在工作区中写明**互不冲突的调度说明**或合并到同一 heartbeat 策略。

---

## 小结

