---
layout: default
title: IG50 · 本地股票数据引擎
---

<div style="text-align:center; padding:40px 0 30px; border-bottom:1px solid #e1e4e8; margin-bottom:30px;">

<img src="assets/logo.png" alt="IG50" width="100">

# IG50 · 本地股票数据引擎

<p style="font-size:18px; color:#586069;">数据本地落盘，策略再无牵绊</p>

<p style="color:#586069;">217个数据集覆盖 A股 · 港股 · 基金全市场 ｜ 3秒级实时行情 + L2深度数据本地落盘</p>

<p>
<a href="https://ig50.com/home.html" style="color:#01AAED;">官网首页</a> ｜ 
<a href="https://ig50.com/index.html" style="color:#01AAED;">官网接口文档</a> ｜ 
<a href="docs/install.html" style="color:#01AAED;">安装指引</a> ｜ 
<a href="docs/examples.html" style="color:#01AAED;">示例代码</a> ｜ 
<a href="docs/pricing.html" style="color:#01AAED;">授权说明</a>
</p>

</div>

> ⚠ **最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准**。本页面为 GitHub Pages 镜像，可能滞后于官网。

## 这是什么

IG50 是一个**本地运行的股票数据引擎**。它把交易所全市场行情数据持续稳定地写入您本地磁盘，数据以 JSON 文本文件落盘，读取零延迟、并发无上限、策略零泄露。

**您不用再维护任何数据采集链路，数据自动到本地，直接读取就能用。**

## 核心特性

- **数据主权在您手中** — 所有数据直接写入本地磁盘，不经过任何云端中转，断网也可正常读取和回测
- **本地读取零延迟** — 数据已在本地，无需网络请求，回测万只股票秒级完成
- **解除数据枷锁** — 不限调用次数、不限并发数、无需考虑带宽
- **策略零泄露** — 无账号注册，不采集用户数据，策略代码完全在本地
- **AI Agent 基础设施** — 大模型读取数据文档，用自然语言即可驱动回测
- **24小时自动更新** — 部署一次永不停歇，无需维护采集链路

## 数据覆盖

| 市场 | 数据集 | 覆盖内容 |
|------|--------|---------|
| 沪深京A股 | 73 个 | 实时行情(3秒)、L2五档盘口、逐笔交易、历史K线、F10全档案 |
| 沪深数据中心 | 70 个 | 龙虎榜、南北向资金、市场异动、财务五维分析、机构持股 |
| 基金行情档案 | 38 个 | 基金估值净值、业绩分红、基金经理、持仓分析、财务报表 |
| 基金数据中心 | 32 个 | 五大评级体系、净值业绩排行、分级基金、基金重仓股 |
| 港股 | 4 个 | 港股列表、实时行情(2秒)、K线(19种级别)、短分时十年 |

**数据集总数：217 个**

## 极速上手

```
1. 获取授权        →  访问官网授权页面（新用户可申请一个月免费试用）
2. 脚本安装        →  一行命令自动部署，适配 Linux / Windows
3. 数据就绪        →  程序自动拉取并更新数据到本地，直接读取使用
```

### Linux 一键安装

```bash
wget -qO ig50_shell.tar https://gitee.com/igtrade/ighub/releases/download/last/ig50_shell.tar && tar xf ig50_shell.tar && rm -f ig50_shell.tar && sed -i 's/\r$//' ./ig50_install.sh && chmod +x ./ig50_install.sh && ./ig50_install.sh
```

### Windows 安装

下载 [ig50_bat.zip](https://gitee.com/igtrade/ighub/releases/download/last/ig50_bat.zip) 后，解压到系统任意目录，以管理员身份运行 `ig50_install.bat`。

## 快速读取示例

```python
import json
import os

data_dir = "/ig50-data"

# 读取沪深京A股列表
with open(os.path.join(data_dir, "base/gplist"), "r", encoding="utf-8") as f:
    stocks = json.load(f)
for stock in stocks[:5]:
    print(f"{stock.get('dm')} {stock.get('mc')}")

# 读取最新K线
with open(os.path.join(data_dir, "time/real/time/000001/Day"), "r", encoding="utf-8") as f:
    kline = json.load(f)
print(f"{kline.get('d')} 开盘:{kline.get('o')} 收盘:{kline.get('c')}")
```

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
