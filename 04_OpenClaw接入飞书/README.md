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

- 学会在已部署 OpenClaw 的前提下，安装并配置飞书官方插件 `@larksuite/openclaw-lark`。
- 成功将 OpenClaw 与飞书（含 Lark 国际版）机器人集成，实现消息互通与自动回复。
- 理解插件授权、安全边界、数据访问范围，并掌握基础合规注意事项。
- 能通过飞书对话及命令，如 `/feishu start`、`/feishu auth` 验证插件功能可用性。
- 了解插件的能力覆盖范围（消息、文档、表格、日历等）及主要使用场景。
- 要能够清楚并操作将创建的飞书机器人完全删除。

---

## 安全与合规（使用前必读）

- 插件通过飞书接口访问消息、文档、日历、联系人等；存在数据泄露与误操作风险，**无法保证绝对安全**。  
- 多人共用机器人或使用企业账号时，须遵守公司数据安全与隐私制度。  
- AI 可能产生幻觉；**代发消息、写入数据等操作通常不可撤销**，重要操作须人工预览与确认。  
- 建议先用**个人账号**熟悉能力，再考虑接入生产环境。

---

## 能力范围


| 类别   | 能力摘要                              |
| ---- | --------------------------------- |
| 消息   | 群/单聊历史、话题回复、发送与回复（含卡片）、搜索、图片/文件下载 |
| 云文档  | 创建、更新、读取                          |
| 多维表格 | Base/表/字段/记录的增删改查、批量与筛选、视图        |
| 电子表格 | 创建、编辑、查看                          |
| 日历日程 | 日程 CRUD、搜索、参会人、忙闲                 |
| 任务   | 任务与清单、子任务、评论                      |


**补充**：以**用户身份**发消息需在开放平台开通 `im:message.send_as_user`；部分企业不支持。

---

## 飞书初体验

访问飞书平台 [https://www.feishu.cn/](https://www.feishu.cn/)  注册飞书帐号，注册成功后可登陆到飞书管理后台进行管理，并下载飞书客户端（APP端和PC端）进行登陆。                              

使用你的飞书账号登录，访问飞书开放平台 [https://open.feishu.cn/](https://open.feishu.cn/)                       

大家也可以参考下面的视频：**【n8n实战经验小Tip】飞书服务使用前配置｜最小配置颗粒度拆解｜开源可抄作业**    

 [https://youtu.be/GKFtAamUMyQ](https://youtu.be/GKFtAamUMyQ)      

[https://www.bilibili.com/video/BV1Q7qQBpEF8/](https://www.bilibili.com/video/BV1Q7qQBpEF8/)       

## 安装与验收

插件对 OpenClaw 有最低版本要求（以飞书文档为准），Linux/macOS 不低于 **2026.2.26**、Windows 不低于 **2026.3.2。**

在终端执行如下命令安装，失败时可在行前加 `sudo` 重试。

```bash
# 默认安装当前最新版本
npx -y @larksuite/openclaw-lark install

# 安装指定版本，如2026.4.7
npx -y @larksuite/openclaw-lark@2026.4.7 install --version 2026.4.7 --tools-version 1.0.37
```

1. 运行成功后，会出现飞书二维码，使用飞书手机客户端进行扫码。
2. 选择 **新建机器人** 或 **关联已有机器人**。
3. 大家选择**创建机器人**，机器人的名称大家可以自定义，名称自定完成后点击创建按钮即可，此时OpenClaw服务会自动重启。
4. 等待创建完成后，并等待OpenClaw服务重启成功后，然后再在飞书中打开机器人，发任意消息开始对话。

**验收**：在飞书中发送 `/feishu start`，若返回版本等信息则插件工作正常。在飞书发送 `/feishu auth` 完成用户侧批量授权，便于以用户身份使用文档/日历等能力。

---

## 升级

版本号随飞书「更新日志」更新，运行如下命令进行升级。

```bash
npx -y @larksuite/openclaw-lark@2026.4.7 install --version 2026.4.7 --tools-version 1.0.37
```

---

## 常用运行时配置

在终端 Shell 中执行。


| 目的              | 命令                                                        |
| --------------- | --------------------------------------------------------- |
| 开启流式卡片(推荐开启一下)  | `openclaw config set channels.feishu.streaming true`      |
| 关闭流式            | `openclaw config set channels.feishu.streaming false`     |
| 卡片底部显示耗时        | `openclaw config set channels.feishu.footer.elapsed true` |
| 卡片底部显示状态        | `openclaw config set channels.feishu.footer.status true`  |
| 话题内独立会话/并行（话题群） | `openclaw config set channels.feishu.threadSession true`  |
| 关闭话题独立会话        | `openclaw config set channels.feishu.threadSession false` |


---

## 诊断与排错

### 飞书对话命令


| 命令               | 用途         |
| ---------------- | ---------- |
| `/feishu start`  | 确认插件是否安装成功 |
| `/feishu doctor` | 检查配置与健康状态  |
| `/feishu auth`   | 批量用户授权     |


权限类提示：按界面链接在开放平台**申请权限并发布**；用户侧未授权则用 `/feishu auth`。

---

## 小结

本节介绍了如何在 OpenClaw 已部署环境下，正确安装与升级飞书插件、进行常用运行时配置，并掌握基本的诊断与排错命令。请根据实际需求灵活调整配置，遇到功能异常时优先使用 `/feishu doctor` 与相关自检命令，确保 Gateway 与飞书互通顺畅，为后续智能体能力扩展打下坚实基础。
