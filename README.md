<!-- IG50 官方文档镜像 -->

<div align="center">

# IG50 · 专业的本地化股票数据引擎

**数据本地落盘，策略再无牵绊**

331个高密度数据集覆盖A股（含基金）、港股、美股 ｜ 实测3秒完成全市场行情更新 ｜ 数据自主可控，策略无需离开本地

![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue)
![Datasets](https://img.shields.io/badge/Datasets-331-green)
![Update](https://img.shields.io/badge/Realtime-3s%20落盘-orange)
![Market](https://img.shields.io/badge/Market-A股%20%7C%20基金%20%7C%20港股%20%7C%20美股-red)

[官网首页](https://ig50.com/home.html) · [官网接口文档](https://ig50.com/dataset-overview.html) · [数据文档](docs/api/README.md) · [安装指引](docs/install.md) · [关于IG50](docs/about.md)

</div>

> ⚠ **最新接口更新以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。本仓库与 Wiki 不会经常维护，如需查阅最新接口、字段、路径，请访问 [官网接口文档](https://ig50.com/dataset-overview.html) 或 [官网数据检索](https://ig50.com/search.html)。

---

## 数据直达本地，随取随用

从行情源到您的本地磁盘，IG50 打通最后一公里：

```
数据（交易所全市场行情）  →  IG50（本地数据引擎）  →  用户本地（JSON 文本直接落盘）
```

数据以 JSON 文本文件落盘，读取零延迟、并发无上限、策略零泄露。

## 为什么选择 IG50

| 特性 | 说明 |
|------|------|
| 🔒 数据主权在您手中 | 所有行情、K线、财务数据直接写入您的本地磁盘，断网也可正常读取和回测 |
| ⚡ 本地读取，零延迟 | 数据已在本地，回测万支股票秒级完成，比任何在线API都快一个数量级 |
| ♾ 解除数据枷锁 | 不限调用次数、不限并发数、无需考虑带宽，大规模批量回测畅通无阻 |
| 🛡 策略零泄露 | 策略代码、交易逻辑、回测行为完全在本地，不存在任何外部暴露风险 |
| 🤖 AI Agent 量化基础设施 | 大模型读取数据集文档，用自然语言即可驱动回测，AI量化的天然基础设施 |
| 🔄 24小时自动更新 | 安装一次永不停歇，无需维护采集链路，无需处理异常缺失，即开即用 |

## 丰富的市场数据覆盖

| 市场 | 数据集 | 覆盖内容 |
|------|--------|---------|
| 沪深京A股 | 135 个 | 实时行情(3秒)、L2五档盘口、逐笔交易、历史K线、F10全档案 |
| 沪深数据中心 | 69 个 | 龙虎榜、南北向资金、市场异动、财务五维分析、机构持股 |
| 基金 | 71 个 | 基金估值净值、业绩分红、基金经理、持仓分析、五大评级体系、基金重仓股 |
| 港股 | 31 个 | 港股列表、实时行情(2秒)、F10全档案、财务分析、K线19种级别 |
| 美股 | 25 个 | 美股列表、实时行情、F10全档案、财务分析、K线 |

**数据集总数：331 个** ｜ 完整接口文档见 [docs/api/](docs/api/README.md) ｜ [官网接口文档](https://ig50.com/dataset-overview.html)（最新）

## 与在线API平台有什么不同

当您的量化系统需要稳定、私密、高性能的数据供给：

| 在线API平台 | IG50 本地引擎 |
|-------------|--------------|
| QPS 限制，并发受限，批量回测频繁超限 | 无限制，无并发限制，批量回测畅通无阻 |
| 网络延迟，频繁网络请求，回测耗时漫长 | 极低延迟，本地读取，批量回测提升一个数量级 |
| 数据经云端，策略逻辑与交易有暴露风险 | 完全本地，数据和策略不离开本地，零泄露 |
| 低复用率，数据即取即弃，数据复用低 | 完全复用，数据全量本地持久化，可离线回测 |
| 数据维护困难，一致性连续性需开发维护 | 数据零维护，自动全量落盘，自我校对与修正 |
| 不可对外服务，数据局部更新，无对外服务可用性 | 可对外服务，天然数据中间层，您的数据长期资产 |

## 谁在使用 IG50

- **量化策略研究员** — 快速验证策略想法，万支股票秒级回测
- **私募量化团队** — 策略零泄露，数据和回测完全在本地闭环
- **AI Agent 开发者** — 大模型直接读取本地文档，自然语言驱动回测
- **金融数据分析师** — 无需维护采集系统，专注数据分析和建模

## 极速上手

```
1. 获取授权        →  联系 service@ig50.com（新用户可申请2周免费试用）
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

## 选择 IG50，您可以获得什么

把维护数据的精力还给策略本身，一年省下的时间就是竞争力：

- **每年节省 600+ 小时** — 自建数据采集系统需要专人维护接口、清洗异常、适配接口变更，IG50 自动更新，一个工程师一年至少省出 600 小时维护时间（按日均 2.4 小时 × 250 工作日计算）
- **策略开发提速 10 倍** — 本地文件读取比 API 调用快一个数量级，万支股票数据回测从分钟级降到秒级，策略迭代周期大幅缩短（本地 I/O 读取 vs 网络请求，性能差 10-100 倍）
- **零维护数据基础设施** — 采集、清洗、更新、存储全链路自动化，安装一次即可长期稳定运行，无需持续投入精力维护数据管道
- **零数据泄露风险** — 策略代码不依赖任何外部服务，没有 API Key 泄露风险，没有回测记录被第三方获取的可能，对于私募和量化团队，数据安全是底线

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

## 灵活授权，按需选择

按市场开通授权，新用户可申请2周免费试用。程序安装在用户本地，数据直接落到用户本地，用户需提供服务器。

| 市场 | 数据集 |
|------|--------|
| A股（推荐） | 沪深京A股135 + 沪深数据中心69 + 基金71 |
| 港股 | 港股列表（约3200只标的）+ F10全档案 + 财务分析 |
| 美股 | 美股列表（约1.3w只标的）+ F10全档案 + 财务分析 |

具体方案与季付、年付优惠详见 [官网授权页面](https://ig50.com/license.html)。

## 文档导航

- [关于 IG50](docs/about.md) — 产品定位、设计目标、隐私承诺
- [安装指引](docs/install.md) — 环境要求、脚本安装、参数说明
- [接口文档](docs/api/README.md) — 331个数据集完整说明
- [示例代码](docs/examples.md) — Python 调用示例
- [授权说明](docs/pricing.md) — 授权方案与获取方式
- [免责声明](docs/disclaimer.md) — 使用条款

> 以上为本仓库镜像文档，**最新接口更新以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 联系

- 官网首页：[https://ig50.com/home.html](https://ig50.com/home.html)
- 官网接口文档：[https://ig50.com/dataset-overview.html](https://ig50.com/dataset-overview.html) ← **最新接口以此为准**
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
