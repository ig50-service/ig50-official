---
layout: default
title: IG50 · 专业的本地化股票数据引擎
---

<div style="text-align:center; padding:40px 0 30px; border-bottom:1px solid #e1e4e8; margin-bottom:30px;">

<img src="assets/ig50-site-logo.png" alt="IG50" width="100">

# IG50 · 专业的本地化股票数据引擎

<p style="font-size:18px; color:#586069;">数据本地落盘，策略再无牵绊</p>

<p style="color:#586069;">331个高密度数据集覆盖A股（含基金）、港股、美股 ｜ 实测3秒完成全市场行情更新 ｜ 数据自主可控，策略无需离开本地</p>

<p>
<a href="https://ig50.com/home.html" style="color:#01AAED;">官网首页</a> ｜
<a href="https://ig50.com/index.html" style="color:#01AAED;">官网接口文档</a> ｜
<a href="docs/install.html" style="color:#01AAED;">安装指引</a> ｜
<a href="docs/examples.html" style="color:#01AAED;">示例代码</a> ｜
<a href="docs/pricing.html" style="color:#01AAED;">授权说明</a>
</p>

</div>

> ⚠ **最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准**。本页面为 GitHub Pages 镜像，可能滞后于官网。

## 数据直达本地，随取随用

从行情源到您的本地磁盘，IG50 打通最后一公里：数据（交易所全市场行情）→ IG50（本地数据引擎）→ 用户本地（JSON 文本直接落盘）。

## 为什么选择 IG50

- **数据主权在您手中** — 所有行情、K线、财务数据直接写入您的本地磁盘，断网也可正常读取和回测
- **本地读取，零延迟** — 数据已在本地，回测万支股票秒级完成，比任何在线API都快一个数量级
- **解除数据枷锁** — 不限调用次数、不限并发数、无需考虑带宽，大规模批量回测畅通无阻
- **策略零泄露** — 策略代码、交易逻辑、回测行为完全在本地，不存在任何外部暴露风险
- **AI Agent 量化基础设施** — 大模型读取数据集文档，用自然语言即可驱动回测，AI量化的天然基础设施
- **24小时自动更新** — 安装一次永不停歇，无需维护采集链路，无需处理异常缺失，即开即用

## 丰富的市场数据覆盖

| 市场 | 数据集 | 覆盖内容 |
|------|--------|---------|
| 沪深京A股 | 135 个 | 实时行情(3秒)、L2五档盘口、逐笔交易、历史K线、F10全档案 |
| 沪深数据中心 | 69 个 | 龙虎榜、南北向资金、市场异动、财务五维分析、机构持股 |
| 基金 | 71 个 | 基金估值净值、业绩分红、基金经理、持仓分析、五大评级体系、基金重仓股 |
| 港股 | 31 个 | 港股列表、实时行情(2秒)、F10全档案、财务分析、K线19种级别 |
| 美股 | 25 个 | 美股列表、实时行情、F10全档案、财务分析、K线 |

**数据集总数：331 个**

## 与在线API平台有什么不同

| 在线API平台 | IG50 本地引擎 |
|-------------|--------------|
| QPS 限制，并发受限，批量回测频繁超限 | 无限制，无并发限制，批量回测畅通无阻 |
| 网络延迟，频繁网络请求，回测耗时漫长 | 极低延迟，本地读取，批量回测提升一个数量级 |
| 数据经云端，策略逻辑与交易有暴露风险 | 完全本地，数据和策略不离开本地，零泄露 |
| 低复用率，数据即取即弃，数据复用低 | 完全复用，数据全量本地持久化，可离线回测 |
| 数据维护困难，一致性连续性需开发维护 | 数据零维护，自动全量落盘，自我校对与修正 |
| 不可对外服务，数据局部更新，无对外服务可用性 | 可对外服务，天然数据中间层，您的数据长期资产 |

## 极速上手

```
1. 获取授权        →  访问官网授权页面（新用户可申请2周免费试用）
2. 脚本安装        →  一行命令自动部署，适配 Linux / Windows
3. 数据就绪        →  程序自动拉取并更新数据到本地，直接读取使用
```

### Linux 一键安装

```bash
wget -qO ig50_shell.tar https://gitee.com/igtrade/ighub/releases/download/last/ig50_shell.tar && tar xf ig50_shell.tar && rm -f ig50_shell.tar && sed -i 's/\r$//' ./ig50_install.sh && chmod +x ./ig50_install.sh && ./ig50_install.sh
```

### Windows 安装

下载 [ig50_bat.zip](https://gitee.com/igtrade/ighub/releases/download/last/ig50_bat.zip) 后，解压到系统任意目录，以管理员身份运行 `ig50_install.bat`。

## 灵活定价，按需选择

| 市场 | 数据集 | 价格 |
|------|--------|------|
| A股（推荐） | 沪深京A股135 + 沪深数据中心69 + 基金71 | 1998 元/月起 |
| 港股 | 港股列表（约3200只标的）+ F10全档案 + 财务分析 | 798 元/月起 |
| 美股 | 美股列表（约1.3w只标的）+ F10全档案 + 财务分析 | 798 元/月起 |

新用户可申请2周免费试用，季付、年付方案详见 [官网授权页面](https://ig50.com/license.html)。

## 文档导航

- [关于 IG50](docs/about.html) — 产品定位、设计目标、隐私承诺
- [安装指引](docs/install.html) — 环境要求、脚本安装、参数说明
- [示例代码](docs/examples.html) — Python 调用示例
- [授权说明](docs/pricing.html) — 授权方案与获取方式
- [免责声明](docs/disclaimer.html) — 使用条款

> 完整接口文档请访问 [官网接口文档](https://ig50.com/index.html)。

## 联系

- 官网首页：[https://ig50.com/home.html](https://ig50.com/home.html)
- 官网接口文档：[https://ig50.com/index.html](https://ig50.com/index.html) ← **最新接口以此为准**
- 官网数据检索：[https://ig50.com/search.html](https://ig50.com/search.html)
- 官网授权页面：[https://ig50.com/license.html](https://ig50.com/license.html)
- 邮箱：`service@ig50.com`

---

© 2026 ig50.com · 数据本地落盘，策略再无牵绊
