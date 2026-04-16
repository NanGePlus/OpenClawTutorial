# 03 OpenClaw安装部署

本期视频为大家介绍和实操 OpenClaw 的标准安装步骤与部署流程，覆盖主流系统及常见环境自检要点。

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

- 完成 OpenClaw CLI 的标准安装、验证与卸载流程，并确保 `openclaw` 命令可用。
- 成功运行 onboarding 引导，配置好所需大模型供应商及其 API Key。
- Gateway 启动无误，可以通过控制面板发送消息并从模型获得回复，验证基本功能正常。

---

## 环境要求


| 项目          | 说明                                                             |
| ----------- | -------------------------------------------------------------- |
| **Node.js** | 推荐 **Node 24**。                                                |
| **模型 API**  | 需自备供应商密钥（如 Anthropic、OpenAI、Google 等）；**onboarding 过程中会引导填写**。 |


检查版本：

```bash
node -v
npm -v
```

尚未安装 Node 时，执行如下指令进行安装。详情见官方：[Node setup](https://docs.openclaw.ai/install/node)。

```bash
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
sudo apt-get install -y nodejs
```

---

## 安装 OpenClaw

### macOS / Linux/WSL2（官方一键脚本）

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

### Windows（PowerShell）

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

一般安装耗时为 2-15 分钟，多数人在 3-8 分钟内完成。耗时取决于以下因素：

- **网络状况**：拉取安装脚本、依赖包（npm 包）时速度差异较大，带宽快慢影响明显。
- **机器性能**：解压缩、写入磁盘和 npm 安装过程依赖本地硬件配置。
- **代理设置**：在国内网络环境下，未配置代理时下载 npm 包可能显著变慢。

### 其它方式

Docker、Nix、`npm` 全局安装等，见专门页面：**[Install](https://docs.openclaw.ai/install)**。  
（概览页中的 `npm install -g openclaw@latest` 亦为一种常见路径，具体以 Install 文档列举为准。）

---

## 运行引导（Onboarding）

执行：

```bash
openclaw onboard
```

向导会带你选择模型供应商、设置 API Key、配置 Gateway。

---

## 确认 Gateway 已运行

```bash
openclaw gateway status
```

正常情况下应能看到 Gateway 在监听 **端口 18789**。

---

## 打开控制界面（Dashboard）

```bash
openclaw dashboard
```

浏览器会打开 **Control UI**。若能正常加载，说明基础链路已通。

- 本机默认地址一般为：`http://127.0.0.1:18789/`。

在控制界面的对话里输入一条消息，应能收到 **AI 回复**。

---

## 配置文件位置

默认配置路径通常为：

`~/.openclaw/openclaw.json`

具体键名与高级项见文档 **Configuration** 部分。

---

## 关闭（停止）OpenClaw Gateway

如果你只是暂时不用，建议先做「停止服务」，不必卸载。

### 关闭方式一：如果是前台运行

当你用 `openclaw gateway` 在当前终端前台运行时，直接按 `Ctrl+C` 结束进程即可。

### 关闭方式二：如果安装为系统服务（推荐）

查看状态：

```bash
openclaw gateway status
```

停止服务：

```bash
openclaw gateway stop
```

需要时再启动/重启：

```bash
openclaw gateway start
openclaw gateway restart
```

---

## 卸载 OpenClaw（含清理服务与残留）

这里给大家列举了两条路线：CLI 仍在时走「一键卸载」，CLI 已删但服务还在时走「手动清理」。

### 一键卸载（CLI 还在）

```bash
openclaw uninstall
```

自动化/无人值守（谨慎使用，会清理更多内容）：

```bash
openclaw uninstall --all --yes --non-interactive
```

### 推荐：openclaw-killer 脚本卸载

你也可以使用openclaw-killer 脚本手动卸载，方式如下：

```bash
# Download script
curl -O https://raw.githubusercontent.com/orange2ai/openclaw-killer/main/openclaw-killer.sh

# Add execute permission
chmod +x openclaw-killer.sh

# Run
./openclaw-killer.sh
```

该脚本会自动完成全部清理工作，适用于 openclaw CLI 已经不可用或需强力移除的场景。  
更多说明详见 [openclaw-killer 项目主页](https://github.com/orange2ai/openclaw-killer?tab=readme-ov-file)。

---

## 常用命令速查

```bash
# 健康检查 + 安全提醒（必跑！）
openclaw doctor          
# 查看运行状态
openclaw status          
# 查看网关状态
openclaw gateway status  
# 浏览器控制面板（最快上手测试）
openclaw dashboard       

# 停止或启动后台服务
openclaw gateway stop/start  
# 添加社交平台
openclaw channels add    
# 查看实时运行日志（排查错误必看）
openclaw logs            
# 列出当前已安装的技能
openclaw skills list     

# 启动「新手引导」。它会带你一步步配置模型和权限
openclaw onboard         
```

---

## 常见问题（自检顺序）

1. **node 版本不符** → 升级到文档推荐版本后重试。
2. **openclaw 命令找不到** → 确认安装脚本或 npm 全局路径已加入 `PATH`，必要时新开终端。
3. **Gateway 未监听** → 查看 `openclaw gateway status` 与官方排错文档。
4. **无回复或报模型错误** → 检查 API Key、网络能否访问供应商、账户额度与地区策略。

---

## 小结

本节简要介绍了 OpenClaw 的标准安装、验证与卸载流程，建议优先采用官方自动化脚本，高效完成部署。请根据自身系统环境检查准备条件，遇到问题及时参阅官方文档和辅助工具，确保顺利上手和后续维护。
