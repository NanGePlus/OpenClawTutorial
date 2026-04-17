# Windows 上安装 WSL2 与 Ubuntu

本指南适用于面向在 **Windows** 上准备安装部署 OpenClaw 或其它 Linux 终端类工具的用户

---

## 适用场景

- 希望在 Windows 上使用与 macOS/Linux 相近的 **Bash、包管理器与路径习惯**。
- 计划按官方文档在 **WSL2 内** 用一键脚本安装 OpenClaw（`curl … install.sh`），而不是仅依赖原生 PowerShell 安装路径。

---

## 前置条件（建议先确认）


| 项目   | 说明                                                                 |
| ---- | ------------------------------------------------------------------ |
| 系统版本 | 建议使用 **Windows 10（版本 2004 及以上）** 或 **Windows 11**。                 |
| 虚拟化  | BIOS/UEFI 中开启 **CPU 虚拟化**；Windows 功能中通常需启用「**虚拟机平台**」等（具体以微软文档为准）。 |
| 权限   | 安装 WSL2 需要 **管理员权限**。                                              |


若 `wsl --install` 提示不满足条件，请按微软文档排查后再继续。

---

## 安装步骤

### 1. 以管理员打开 PowerShell

在 Windows 中搜索 **PowerShell**，选择 **以管理员身份运行**。

> 注意：是 **Windows PowerShell** 或 **终端（管理员）** 均可，但必须具备管理员权限。

### 2. 安装 WSL2 与默认 Ubuntu

在管理员 PowerShell 中执行：

```powershell
wsl --install
```

默认行为一般为：安装 **WSL2** 并安装 **Ubuntu** 发行版（具体以当前 Windows 版本输出为准）。

- 若系统提示**需要重启**，请保存工作后重启，再继续后续步骤。
- 系统安装完成后会自动启动，则提示创建 **Linux 用户名与密码**（输入密码时屏幕不显示字符，属正常现象）。
- 若已安装过旧版 WSL，微软文档提供 `wsl --install` 的升级与组件说明，可按提示补充安装 **WSL2** 内核。

### 3. 首次进入 Ubuntu 并更新系统

进入系统后建议先更新软件索引，例如：

```bash
sudo apt-get update
```

可选安装编辑器：

```bash
sudo apt-get install vim
```

---

## 安装结果自检

在 **PowerShell（普通或管理员均可）** 中执行：

```powershell
wsl --version
wsl --list --verbose
```

预期大致包括：

- `wsl --version` 能显示 WSL 版本信息。
- `wsl --list --verbose` 中 Ubuntu 一行的 **VERSION** 为 **2**（表示 WSL2）。

若 VERSION 为 1，可将该发行版设为默认使用 WSL2（发行版名称以你机器上 `wsl -l -v` 为准）：

```powershell
wsl --set-version Ubuntu 2
```

---

## 常用命令备忘


| 目的                     | 命令示例                      |
| ---------------------- | ------------------------- |
| 查看 WSL 版本              | `wsl --version`           |
| 查看已安装发行版及 WSL 版本       | `wsl --list --verbose`    |
| 进入默认发行版                | `wsl`                     |
| 进入指定发行版                | `wsl -d Ubuntu`           |
| 卸载某发行版（**数据会删除且不可恢复**） | `wsl --unregister Ubuntu` |


卸载前请确认该发行版内**无未备份的重要数据**。

---

## 常见错误处理：`Wsl/WININET_E_NAME_NOT_RESOLVED`

在安装或列出发行版时若出现类似错误：

> 无法从“[https://raw.githubusercontent.com/microsoft/WSL/master/distributions/DistributionInfo.json”提取列表分发。操作超时](https://raw.githubusercontent.com/microsoft/WSL/master/distributions/DistributionInfo.json”提取列表分发。操作超时)
> 错误代码: Wsl/InstallDistro/0x80072ee2

多为**无法解析** `raw.githubusercontent.com`（DNS 或网络限制）。可尝试在**本机 hosts** 中为该域名指定解析（**IP 可能随时间变化**，若失效请自行查询最新 IP）。

### 操作步骤

1. 在资源管理器中打开：`C:\Windows\System32\drivers\etc\`。
2. 用 **管理员权限** 编辑 `hosts` 文件（可用记事本「以管理员身份运行」后再打开该文件）。
3. 在文件 **末尾** 新增一行（任选下方列表中一个 IP，或与当时可用的 IP 一致）：

```text
185.199.108.133 raw.githubusercontent.com
```

可选 IP（GitHub Pages 常用段，**不保证长期不变**）：

- `185.199.108.133`
- `185.199.109.133`
- `185.199.110.133`
- `185.199.111.133`

可自行在 [ipaddress.com 上查询 `raw.githubusercontent.com](https://www.ipaddress.com/website/raw.githubusercontent.com/)` 当前解析结果，替换为页面显示的地址。

1. 保存 `hosts` 后，在管理员 PowerShell 中重试：

```powershell
wsl --install
```

若仍失败，还需排查：代理/VPN、公司防火墙、DoH/自定义 DNS 等是否拦截了对 GitHub 的访问。

---

## 小结

1. **管理员 PowerShell** 执行 `wsl --install`，按提示完成用户创建。
2. 打开 **Ubuntu**，执行 `sudo apt-get update`（及可选 `vim`）。
3. 用 `wsl -l -v` 确认 **VERSION 为 2**。
4. 遇 **NAME_NOT_RESOLVED** 时，再按上文修改 **hosts** 并重试。
5. 遇 **关机重启后** `openclaw gateway start` **报 systemd 用户服务错误** 时，按上文「常见错误处理：关机重启后 …」一节逐步执行。

