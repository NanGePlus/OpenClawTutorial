# 02 准备工作

本期视频安排在正式安装部署之前，目的是**先把决策做对**，减少后续反复拆装、改方案的成本。建议大家在动手前，依次想清楚：**硬件与系统**、**网络如何访问大模型服务**、**凭证与消息入口**三件事是否已有结论。

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

- 理清不同操作系统环境下部署 OpenClaw 的最佳实践，助力设备与系统选型。
- 明确如何规划与准备宿主设备，权衡主力机、备用机、云主机等多种场景。
- 系统梳理模型服务的访问方案与网络要求，保障后续连通性。
- 搞懂模型选型、API Key 获取、消息入口准备等核心环节。
- Windows 下通过 WSL2+Ubuntu 达成与主流教程一致的部署路径（具体实践）。
- 总结常见准备过程中的坑点与误区，为顺利部署排除隐患。

---

## 操作系统怎么选

OpenClaw 的特点是**后台常驻运行、支持脚本化操作以及能够对接外部系统**，因此相比单台机器的算力，它对**环境一致性、日志可追溯和可重复部署**的要求更高。


| 你的情况           | 参考取向                            |
| -------------- | ------------------------------- |
| 苹果桌面系统 Mac     | 与多数教程的终端、路径习惯较一致，适合边查文档边验证。     |
| 通用 Linux（含云主机） | 适合 7×24 在线；需一并规划进程守护、端口与公网访问方式。 |
| 微软桌面系统 Windows | 更稳妥的做法是在 **WSL2** 内完成环境与依赖。     |


### 零基础时的折中默认


| 维度   | 倾向                                      |
| ---- | --------------------------------------- |
| 硬件   | 闲置电脑、低功耗常开设备，往往比每天携带的笔记本更适合当第一台宿主。      |
| 推理   | 首选用**供应商提供的 HTTP API**，减少本地显卡与环境变量上的变量。 |
| 阶段目标 | 先验证**「能连上模型 + 能执行一条自动化」**，再考虑成本与性能优化。   |


---

## 宿主机器放在哪里

按**风险与维护成本**大致可这样排序（越靠前通常越省心）：

1. 专用或半专用的旧设备、低功耗盒子
2. 设计为长期开机的桌面小型主机
3. 云厂商虚拟机（需熟悉 SSH、防火墙与账单）
4. 日常办公主力机（文档、隐私、误操作风险集中，仅作备选）

主力机上调试时，误触文件、权限放大的概率更高；在备用设备上把流程摸熟，再迁移或并行，一般更稳。

---

## 网络与模型访问

在安装部署之前，先确认**从这台机器出发**，能否稳定访问你计划使用的大模型服务。


| 网络画像            | 建议                                    |
| --------------- | ------------------------------------- |
| 可稳定访问境内/外大模型服务商 | 可直接按供应商文档申请密钥并做连通性测试。                 |
| 以国内出口为主         | 提前确认是否需合规的转发或企业网关；避免全部装完才做第一次才做连通性测试。 |
| 仅使用机房内或本机推理     | 先独立拉起推理进程，确认监听地址与鉴权，再让 OpenClaw 去连。   |


若 HTTP 请求到不了大模型端，应用层配置再正确也无法工作；细节配置可在后续视频展开，但 **连通性结论** 应在本节有答案。

### 模型形态怎么定


| 取向        | 说明                          |
| --------- | --------------------------- |
| 远程 API 为主 | 宿主更多承担编排与存储，对本地算力要求相对低。     |
| 本地推理为主    | 先核对显存 / 内存与推理框架是否真能启动，再谈集成。 |


---

## 消息入口与安全边界

提前想好：自动化消息从哪个**官方机器人 / 应用**进入；读写范围是否限制在指定文件夹；是否禁止对支付、人事等目录做批量操作等。本期视频只需**心里有数**，具体参数在后续视频中设置。

---

## 动手前的检查清单

### 建议完成的核对项

- 已选定：MAC / WSL2 / Linux 中的一条具体路径。  
- 已明确：大模型请求从本机发出的**可达性**（含是否需要代理或内网地址）。  
- 已约定：**源码、配置、日志、临时文件**分目录存放（见下表）。  
- 若在主力机上操作：已完成**备份**，或已决定改到备用机。

### 数据与权限

- 安装与试错前备份关键资料。  
- 对不确定的目录不要授予全局读写；先用**够用即可**的权限跑通。

### 目录示例（可按个人习惯替换路径，保持分类即可）


| 类型      | 示例路径                   |
| ------- | ---------------------- |
| 项目 / 源码 | `~/dev/openclaw/`      |
| 应用配置    | `~/.openclaw/`         |
| 运行日志    | `~/dev/openclaw/logs/` |
| 临时生成物   | `~/dev/openclaw/tmp/`  |


---

## 小结

本节主要聚焦于在正式安装和配置 OpenClaw 之前，需要提前明确模型部署形态、消息入口、安全边界与数据目录等关键问题。建议提前做路径和连通性核查、备份敏感数据，并按类型规范目录与权限设置。良好的前期准备有助于后续高效、稳定且安全地运行 OpenClaw。
