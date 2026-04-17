# 03 OpenClaw安装部署

本期视频为大家介绍和实操 OpenClaw 的安装部署。

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

- 完成 OpenClaw 的安装、验证、升级与卸载，并确保 `openclaw` 命令可用。
- 成功运行配置引导，配置好所需的大模型服务提供商的 API Key。
- Gateway 启动无误，可以登陆到浏览器控制面板，发送消息给大模型并能够获得回复，验证基本功能正常。

---

## 环境要求


| 项目              | 说明                              |
| --------------- | ------------------------------- |
| **Node.js**     | 推荐 **Node 24**。                 |
| **大模型 API Key** | 需自备大模型服务提供商API Key，在配置过程中会引导填写。 |


尚未安装 Node 时，执行如下指令进行安装。详情见官方：[Node setup](https://docs.openclaw.ai/install/node)。

```bash
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
sudo apt-get install -y nodejs
```

检查版本：

```bash
node -v
npm -v
```

---

## 安装 OpenClaw

### macOS / Linux/WSL2 一键脚本安装

```bash
# 默认安装当前最新版本
curl -fsSL https://openclaw.ai/install.sh | bash

# 安装指定版本，将 x.y.z 替换为真实版本号，如2026.4.15
curl -fsSL https://openclaw.ai/install.sh | bash -s -- --version x.y.z

# 安装后核对版本
openclaw --version
```

安装耗时每个人可能不一样，需要耐心等待。耗时取决于以下因素：

- **网络状况**：拉取安装脚本、依赖包（npm 包）时速度差异较大，带宽快慢影响明显。
- **机器性能**：解压缩、写入磁盘和 npm 安装过程依赖本地硬件配置。
- **代理设置**：在国内网络环境下，未配置代理时下载 npm 包可能显著变慢。

### Node 全局安装

```bash
# 默认安装当前最新版本
npm install -g openclaw@latest

# 安装指定版本，将 x.y.z 替换为真实版本号，如2026.4.15
npm install -g openclaw@x.y.z

# 安装后核对版本
openclaw --version
```

### 其它方式

Docker、Nix 全局安装等，见专门页面：**[Install](https://docs.openclaw.ai/install)**。

---

## 配置引导

默认安装时会进行大模型服务的配置，其他配置可通过执行如下命令进行参数配置。

```bash
openclaw onboard
```

---

## 查询 Gateway 运行状态

```bash
openclaw gateway status
```

正常情况下应能看到 Gateway 在监听 **端口 18789**。

---

## 打开浏览器控制面板

```bash
openclaw dashboard
```

浏览器会打开 **Control UI**。若能正常加载，说明基础链路已通。

- 本机默认地址一般为：`http://127.0.0.1:18789/`。

在控制界面的对话里输入一条消息，应能收到大模型的回复。

---

## 配置文件位置

默认配置路径通常为：

`~/.openclaw/openclaw.json`

---

## 停止OpenClaw

如果你只是暂时不用，建议先做「停止服务」，不必卸载。

### 关闭方式一：如果是前台运行

当你用 `openclaw gateway` 在当前终端前台运行时，直接按 `Ctrl+C` 结束进程即可。

### 关闭方式二：如果是以系统服务运行

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

## 升级 OpenClaw（需谨慎）

日常保持版本与 Gateway 一致，建议以官方 **[Updating](https://docs.openclaw.ai/install/updating)** 为准。以下为常用路径摘要。

### 推荐：`openclaw update`

一条命令会按你的安装类型（npm 或 git）拉取新版本、运行 `openclaw doctor`，并重启 Gateway：

```bash
openclaw update
```

### 其它方式

**重新运行官方安装脚本**

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

不想再走 onboarding 时，macOS/Linux 可对 `install.sh` 加 `--no-onboard`。

**手动用包管理器升级到 `latest`**：

```bash
npm i -g openclaw@latest
```

### 自动更新（不建议）

默认关闭。可在 `~/.openclaw/openclaw.json` 中启用 `update.auto`。

---

## 卸载 OpenClaw

这里给大家列举了两条路线：CLI 仍在时走「一键卸载」，CLI 已删但服务还在时走「脚本卸载」。

### 推荐：官方一键卸载（CLI 还在）

依次按照顺序运行如下指令进行卸载。

```bash
openclaw uninstall --all --yes --non-interactive
npm uninstall -g openclaw
openclaw --version
```

### openclaw-killer 脚本卸载

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
# 健康检查 + 安全提醒
openclaw doctor          
# 查看运行状态
openclaw status          
# 查看网关状态
openclaw gateway status  
# 浏览器控制面板
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

## 常见错误处理：Windows关机重启后或Ubuntu关机重启后 `openclaw gateway status` 报 systemd 用户服务错误

### 现象

在重新进入 Ubuntu（WSL）后执行 `openclaw gateway start` 时出现类似报错：

```text
systemd user services unavailable.
```

此时，可以使用如下命令进行验证

```text
systemctl --user status

# 返回的结果如下所示
Failed to connect to bus:No such file or directory 
```

### 处理方案（在 Ubuntu 终端内按顺序执行）

先验证是否缺user bus，在命令行终端中依次执行如下命令

```bash
id -u
echo "$XDG_RUNTIME_DIR"
ls -ld /run/user/$(id -u) || true
ls -l /run/user/$(id -u)/bus || true
```

如果最后一条指令提示不存在，那依次执行如下命令安装用户会话DBus

```bash
sudo apt update
sudo apt install -y dbus-user-session
```

安装完成后，在 Windows 的 PowerShell 命令行终端中执行

```bash
wsl --shutdown
```

然后重新打开 Ubuntu 进行验证

```bash
ls -l /run/user/$(id -u)/bus
systemctl --user status
```

如果装完还是没有 `/run/user/1000/bus`，再补一条（让 systemd 为该用户维持 user manager）

```bash
sudo loginctl enable-linger "$USER"
```

再 `wsl --shutdown` 重启一次即可。如果还是不行，继续往下执行如下两个指令。

```bash
loginctl show-user "$USER" -p RuntimePath -p Linger -p State --no-pager
ls -ld /run/user/$(id -u) /run/user/$(id -u)/bus || true
```

若 `RuntimePath` 有但 `bus` 没有，则继续执行如下指令

```bash
sudo systemctl restart user@1000.service
sudo systemctl restart user-runtime-dir@1000.service
```

然后重新再执行如下指令进行检查

```bash
ls -l /run/user/$(id -u)/bus
systemctl --user status
```

若正常输出相关内容，则在命令行终端中执行如下指令查看OpenClaw 的状态。状态若输出正常，则该问题解决

```bash
openclaw gateway status 
```

---

## 小结

本节简要介绍了 OpenClaw 的标准安装、指定版本、升级、验证与卸载流程，建议优先采用官方自动化脚本完成部署，日常升级优先使用 `openclaw update`。请根据自身系统环境检查准备条件，遇到问题及时参阅官方文档和辅助工具，确保顺利上手和后续维护。
