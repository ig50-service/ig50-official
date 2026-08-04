<!-- IG50 官方文档镜像 -->

<div align="center">

# IG50 · 本地股票数据引擎

**数据本地落盘，策略再无牵绊**

217个数据集覆盖 A股 · 港股 · 基金全市场 ｜ 3秒级实时行情 + L2深度数据本地落盘 ｜ 零延迟读取 · 无并发限制 · 策略零泄露

![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue)
![Datasets](https://img.shields.io/badge/Datasets-217-green)
![Update](https://img.shields.io/badge/Realtime-3s%20落盘-orange)
![Market](https://img.shields.io/badge/Market-A股%20%7C%20基金%20%7C%20港股%20%7C%20美股-red)

[官网首页](https://ig50.com/home.html) · [官网接口文档](https://ig50.com/index.html) · [数据文档](docs/api/README.md) · [安装指引](docs/install.md) · [关于IG50](docs/about.md)

</div>

> ⚠ **最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准**。本仓库与 Wiki 不会经常维护，如需查阅最新接口、字段、路径，请访问 [官网接口文档](https://ig50.com/index.html) 或 [官网数据检索](https://ig50.com/search.html)。

---

## 这是什么

IG50 是一个**本地运行的股票数据引擎**。它把交易所全市场行情数据持续稳定地写入您本地磁盘，数据以 JSON 文本文件落盘，读取零延迟、并发无上限、策略零泄露。

简单说就是：**您不用再维护任何数据采集链路，数据自动到本地，直接读取就能用。**

## 为什么需要它

做量化和策略研究的人都知道，真正消耗时间的往往不是策略本身，而是数据获取、清洗、维护过程的不确定性。在线 API 平台普遍存在：

- **QPS 限制** — 并发受限，批量回测频繁超限
- **网络延迟** — 每次读取 50-500ms，大规模回测耗时漫长
- **数据经云端** — 策略逻辑和交易信号暴露在网络上
- **结构不稳定** — 接口变更、字段缺失需要持续适配维护
- **L2 数据少** — 极少提供五档盘口、逐笔交易等深度数据

IG50 把这些一次性解决掉。

## 核心特性

| 特性 | 说明 |
|------|------|
| 🔒 数据主权在您手中 | 所有数据直接写入本地磁盘，不经过任何云端中转，断网也可正常读取和回测 |
| ⚡ 本地读取零延迟 | 数据已在本地，无需网络请求，回测万只股票秒级完成 |
| ♾ 解除数据枷锁 | 不限调用次数、不限并发数、无需考虑带宽 |
| 🛡 策略零泄露 | 无账号注册，不采集用户数据，策略代码完全在本地 |
| 🤖 AI Agent 基础设施 | 大模型读取数据文档，用自然语言即可驱动回测 |
| 🔄 24小时自动更新 | 部署一次永不停歇，无需维护采集链路 |

## 数据覆盖

| 市场 | 数据集 | 覆盖内容 |
|------|--------|---------|
| 沪深京A股 | 73 个 | 实时行情(3秒)、L2五档盘口、逐笔交易、历史K线、F10全档案 |
| 沪深数据中心 | 70 个 | 龙虎榜、南北向资金、市场异动、财务五维分析、机构持股 |
| 基金行情档案 | 38 个 | 基金估值净值、业绩分红规模、基金经理、持仓分析、财务报表 |
| 基金数据中心 | 32 个 | 五大评级体系、净值业绩排行、分级基金、基金重仓股 |
| 港股 | 4 个 | 港股列表、实时行情(2秒)、K线(19种级别)、短分时十年 |

**数据集总数：217 个** ｜ 完整接口文档见 [docs/api/](docs/api/README.md) ｜ [官网接口文档](https://ig50.com/index.html)（最新）

## 极速上手

```
1. 获取授权        →  联系 service@ig50.com（新用户可申请一个月免费试用）
2. 脚本安装        →  一行命令自动部署，适配 Linux / Windows
3. 数据就绪        →  程序自动拉取并更新数据到本地，直接读取使用
```

详细步骤见 [安装指引](docs/install.md)。

### Linux 一键安装

```bash
wget -qO ig50_shell.tar https://gitee.com/igtrade/ighub/releases/download/last/ig50_shell.tar && tar xf ig50_shell.tar && rm -f ig50_shell.tar && sed -i 's/\r$//' ./ig50_install.sh && chmod +x ./ig50_install.sh && ./ig50_install.sh
```

### Windows 安装

下载 [ig50_bat.zip](https://gitee.com/igtrade/ighub/releases/download/last/ig50_bat.zip) 后，解压到系统任意目录，以管理员身份运行 `ig50_install.bat`。

## 快速读取示例

数据落盘为 JSON 文本文件，直接读取即可：

```python
import json
import os

# 读取沪深京A股列表
data_dir = "/ig50-data"  # 数据存放目录（默认值）
stock_list_path = os.path.join(data_dir, "base/gplist")

with open(stock_list_path, "r", encoding="utf-8") as f:
    stocks = json.load(f)

# 打印前5只股票
for stock in stocks[:5]:
    print(f"{stock.get('dm')} {stock.get('mc')}")

# 读取某只股票的最新K线（不复权）
kline_path = os.path.join(data_dir, f"time/real/time/000001/Day")
with open(kline_path, "r", encoding="utf-8") as f:
    kline = json.load(f)
print(f"交易时间：{kline.get('d')} 开盘：{kline.get('o')} 收盘：{kline.get('c')}")
```

更多示例见 [示例代码](docs/examples.md)。

## 授权

IG50 提供灵活的授权方案，按市场（A股 / 港股）开通，新用户可申请一个月免费试用。

- 程序部署在用户本地，数据直接落到用户本地
- 一次授权包含软件持续免费升级、工单支持、专人服务
- 季付、年付享更多优惠

如需了解具体方案与价格，请访问 [官网授权页面](https://ig50.com/license.html) 或联系 `service@ig50.com`。

## 文档导航

- [关于 IG50](docs/about.md) — 产品定位、设计目标、隐私承诺
- [安装指引](docs/install.md) — 环境要求、脚本安装、参数说明
- [接口文档](docs/api/README.md) — 217个数据集完整说明
- [示例代码](docs/examples.md) — Python 调用示例
- [授权说明](docs/pricing.md) — 授权方案与获取方式
- [免责声明](docs/disclaimer.md) — 使用条款

> 以上为本仓库镜像文档，**最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 谁在用

- **量化策略研究员** — 快速验证策略想法，万只股票秒级回测
- **私募量化团队** — 策略零泄露，数据和回测完全在本地闭环
- **AI Agent 开发者** — 大模型直接读取本地文档，自然语言驱动回测
- **金融数据分析师** — 无需维护采集系统，专注数据分析和建模

## 选择 IG50 你可以获得什么

- **每年节省 600+ 小时** — 自建数据采集系统维护时间归零
- **策略开发提速 10 倍** — 本地 I/O 读取 vs 网络请求
- **零维护数据基础设施** — 一次部署持续运行
- **零数据泄露风险** — 本地闭环，数据策略都不离开服务器

## 联系

- 官网首页：[https://ig50.com/home.html](https://ig50.com/home.html)
- 官网接口文档：[https://ig50.com/index.html](https://ig50.com/index.html) ← **最新接口以此为准**
- 官网数据检索：[https://ig50.com/search.html](https://ig50.com/search.html)
- 官网授权页面：[https://ig50.com/license.html](https://ig50.com/license.html)
- 邮箱：service@ig50.com
- 代码托管：[Gitee](https://gitee.com/igtrade/ighub/)

## 许可

本仓库内容（文档、示例代码）采用 CC BY-NC-SA 4.0 许可。IG50 软件本身的许可请参考 [授权说明](docs/pricing.md)。

---

<div align="center">

© 2026 ig50.com · 数据本地落盘，策略再无牵绊

</div>
