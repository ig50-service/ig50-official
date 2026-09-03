# 示例代码

> 数据落盘为 JSON 文本文件，使用 Python 标准库即可读取，无需安装额外依赖。
>
> 以下示例基于官网真实字段名称和本地路径编写。

## 1. 读取沪深京A股列表

**本地路径**：`base/gplist`

```python
import json
import os

data_dir = "/ig50-data"
stock_list_path = os.path.join(data_dir, "base/gplist")

with open(stock_list_path, "r", encoding="utf-8") as f:
    stocks = json.load(f)

print(f"共 {len(stocks)} 只股票")
for stock in stocks[:5]:
    print(f"{stock.get('dm')} {stock.get('mc')} 交易所={stock.get('jys')}")
```

**字段说明**：
- `dm`：股票代码，如：000001
- `mc`：股票名称，如：平安银行
- `jys`：交易所，"sh"表示上证，"sz"表示深证，"bj"表示北证
- `isCyb`：是否属于创业板。0：否，1：是
- `isKcb`：是否属于科创板。0：否，1：是
- `isSt`：是否ST。0：否，1：是
- `isNew`：是否是新股。0：否，1：是

## 2. 读取实时行情（3秒落盘）

**本地路径**：`time/real/{股票代码}`

```python
import json
import os

data_dir = "/ig50-data"
realtime_path = os.path.join(data_dir, "time/real/000001")

with open(realtime_path, "r", encoding="utf-8") as f:
    quote = json.load(f)

print(f"代码：{quote.get('dm')}")
print(f"名称：{quote.get('mc')}")
print(f"当前价：{quote.get('p')} 元")
print(f"涨跌幅：{quote.get('pc')}%")
print(f"成交量：{quote.get('v')} 股")
print(f"成交额：{quote.get('cje')} 元")
print(f"换手率：{quote.get('hs')}%")
print(f"市盈率TTM：{quote.get('pettm')}")
```

**常用字段说明**：
- `dm`：代码
- `mc`：名称
- `t`：更新时间（yyyy-MM-dd HH:mm:ss）
- `p`：当前价格（元）
- `o`：开盘价（元）
- `h`：最高价（元）
- `l`：最低价（元）
- `yc`：昨收价（元）
- `pc`：涨跌幅（%）
- `v`：成交量（股）
- `cje`：成交额（元）
- `hs`：换手率（%）
- `lb`：量比
- `sz`：总市值（元）
- `lt`：流通市值（元）
- `pettm`：市盈率TTM

## 3. 读取最新K线

**本地路径**：`time/real/time/{股票代码}/{分时级别}`

**支持的分时级别**：`5`, `15`, `30`, `60`, `Day`, `Day_qfq`, `Day_hfq`, `Week`, `Week_qfq`, `Week_hfq`, `Month`, `Month_qfq`, `Month_hfq`, `Quarter`, `Quarter_qfq`, `Quarter_hfq`, `Year`, `Year_qfq`, `Year_hfq`

```python
import json
import os

data_dir = "/ig50-data"
# 读取平安银行日K线（不复权）
kline_path = os.path.join(data_dir, "time/real/time/000001/Day")

with open(kline_path, "r", encoding="utf-8") as f:
    kline = json.load(f)

print(f"交易时间：{kline.get('d')}")
print(f"开盘：{kline.get('o')} 元")
print(f"最高：{kline.get('h')} 元")
print(f"最低：{kline.get('l')} 元")
print(f"收盘：{kline.get('c')} 元")
print(f"成交量：{kline.get('v')} 股")
print(f"成交额：{kline.get('e')} 元")
print(f"涨跌幅：{kline.get('zd')}%")
```

**字段说明**：
- `d`：交易时间（短分时格式为yyyy-MM-dd HH:mm:ss，日线及以上为yyyy-MM-dd）
- `o`：开盘价（元）
- `h`：最高价（元）
- `l`：最低价（元）
- `c`：收盘价（元）
- `v`：成交量（股）
- `e`：成交额（元）
- `zf`：振幅（%）
- `hs`：换手率（%）
- `zd`：涨跌幅（%）
- `zde`：涨跌额（元）
- `sz`：昨收价（元）
- `ud`：更新时间

## 4. 读取资金流向排名

**本地路径**：`all/zjlx/jlrepm`（净流入额排名）

```python
import json
import os

data_dir = "/ig50-data"
rank_path = os.path.join(data_dir, "all/zjlx/jlrepm")

with open(rank_path, "r", encoding="utf-8") as f:
    ranking = json.load(f)

print("净流入额前10：")
for r in ranking[:10]:
    print(f"{r.get('dm')} {r.get('mc')} 净流入={r.get('jlre')} 涨跌幅={r.get('pc')}%")
```

## 5. 结合 Pandas 分析

```python
import json
import pandas as pd

data_dir = "/ig50-data"

# 读取股票列表
with open(os.path.join(data_dir, "base/gplist"), "r", encoding="utf-8") as f:
    stocks = json.load(f)

df = pd.DataFrame(stocks)

# 按交易所统计
print(df["jys"].value_counts())

# 筛选科创板股票
kcb = df[df["isKcb"] == 1]
print(f"科创板股票共 {len(kcb)} 只")

# 筛选非ST股票
non_st = df[df["isSt"] == 0]
print(f"非ST股票共 {len(non_st)} 只")
```

## 6. 批量回测示例

```python
import json
import os
import time

data_dir = "/ig50-data"

def load_kline(code, level="Day"):
    """读取某只股票的K线"""
    path = os.path.join(data_dir, f"time/real/time/{code}/{level}")
    if not os.path.exists(path):
        return {}
    with open(path, "r", encoding="utf-8") as f:
        return json.load(f)

# 读取股票列表
with open(os.path.join(data_dir, "base/gplist"), "r", encoding="utf-8") as f:
    stocks = json.load(f)

# 批量计算所有股票的近20日均价
start = time.time()
results = []
for stock in stocks:
    code = stock.get("dm")
    kline = load_kline(code, "Day")
    if not kline:
        continue
    close = kline.get("c", 0)
    results.append({"dm": code, "mc": stock.get("mc"), "close": close})

elapsed = time.time() - start
print(f"回测 {len(results)} 只股票，耗时 {elapsed:.2f} 秒")
```

本地文件读取的效率优势在这里非常明显——同样的操作如果走在线 API，受 QPS 限制可能需要几十分钟甚至几小时。

---

更多接口详见 [接口文档](api/README.md)。

> 最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准，本仓库示例可能滞后于官网。
