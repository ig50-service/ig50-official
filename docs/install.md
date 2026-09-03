# 安装指引

> 从获取授权到完成部署，全程指引

## 1. 获取授权

使用前请先获取授权。新用户可申请2周免费试用，满意后再付费。

→ [查看授权套餐](pricing.md)

## 2. 部署环境要求（最佳实践）

> - 建议使用干净的服务器部署，而非个人电脑（除非临时验证可行性），以获取最佳体验。
> - 数据更新是连续不间断的，请尽量保证服务器网络和供电的连续性，因此推荐部署在云服务器上。
> - 实在出现不可抗力情况，程序在服务器重启后，也会每天凌晨自动检查、修正所有数据，用户不需要过分担心。
> - 由于数据服务器集群都在国内，为保证最低延迟，不推荐海外服务器部署。
> - 每个独立的授权，需部署在独立的服务器上，因为每个市场至少几千只股票同时更新。

### 最低服务器配置

- **CPU**：8 核心
- **内存**：16 GB
- **硬盘**：200 GB
- **指令集架构**：x86 64 位

### 公版程序已适配系统

| 类型 | 系列 | 适配明细 | glibc 版本 |
|------|------|---------|-----------|
| Linux | Debian | Debian 11+、Ubuntu 22.04+（及 Linux Mint、Deepin、Kali 等） | ≥ 2.31（`ldd --version`） |
| Linux | CentOS | CentOS 9（及 RHEL 9、Rocky Linux 9、AlmaLinux 9、Fedora 等） | ≥ 2.34（`rpm -q glibc`） |
| Linux | SUSE | openSUSE 15.5+ | ≥ 2.31 |
| Windows | - | Windows 10（兼容 Windows 11 及 Windows Server 2016+） | - |

## 3. 自动脚本安装

> **警告**：Linux 系统请确保在 root 用户或有 sudo 权限的用户下执行。Windows 系统则以管理员身份运行脚本。

### Linux 安装

**安装脚本**（在服务器任意目录下执行，此命令同时会下载更新脚本 `ig50_update.sh` 和卸载脚本 `ig50_uninstall.sh`）：

```bash
wget -qO ig50_shell.tar https://gitee.com/igtrade/ighub/releases/download/last/ig50_shell.tar && tar xf ig50_shell.tar && rm -f ig50_shell.tar && sed -i 's/\r$//' ./ig50_install.sh && chmod +x ./ig50_install.sh && ./ig50_install.sh
```

**更新脚本**：

```bash
sed -i 's/\r$//' ./ig50_update.sh && chmod +x ./ig50_update.sh && ./ig50_update.sh
```

**卸载脚本**：

```bash
sed -i 's/\r$//' ./ig50_uninstall.sh && chmod +x ./ig50_uninstall.sh && ./ig50_uninstall.sh
```

### Windows 安装

1. 下载 [ig50_bat.zip](https://gitee.com/igtrade/ighub/releases/download/last/ig50_bat.zip)
2. 解压到系统任意目录
3. 以管理员身份运行

| 脚本 | 用途 |
|------|------|
| `ig50_install.bat` | 安装脚本 |
| `ig50_update.bat` | 更新脚本 |
| `ig50_uninstall.bat` | 卸载脚本 |

## 4. 程序关键文件与参数说明

> 程序参数极简，尽可能做到开箱即用，所有参数皆有缺省值，且满足绝大部分用户。

### 目录结构

```
/opt/ig50
  ├─appbak                                  # 更新脚本自动创建的程序备份目录
  ├─config                                  # 程序配置目录
  │  ├─ig50.license                         # 授权文件，联系 service@ig50.com 获取
  │  │   ├─user                             # 授权用户id
  │  │   └─market                           # 授权市场
  │  ├─ig50_user_config.properties          # 用户配置（绝大部分用户保持默认即可）
  │  │   ├─server.data.dir                  # 数据存放目录。缺省：/ig50-data
  │  │   └─server.connect.timeout           # 服务器连接超时时间(毫秒)。缺省：100
  │  └─ig50_system.ini                      # 程序配置（请勿人为改动）
  ├──ig50                                   # 主程序
  ├──logs                                   # 程序日志
  └──tools                                  # 程序依赖的第三方工具
```

### 关键参数

| 参数 | 位置 | 缺省值 | 说明 |
|------|------|--------|------|
| `server.data.dir` | `ig50_user_config.properties` | `/ig50-data` | 数据存放目录 |
| `server.connect.timeout` | `ig50_user_config.properties` | `100` | 服务器连接超时时间（毫秒） |
| `user` | `ig50.license` | - | 授权用户id |
| `market` | `ig50.license` | - | 授权市场 |

授权文件 `ig50.license` 请联系 `service@ig50.com` 获取，整个文件覆盖即可。

---

下一步：[查看接口文档](api/README.md) ｜ [查看示例代码](examples.md) ｜ [官网接口文档（最新）](https://ig50.com/index.html)

> 最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准。
