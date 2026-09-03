# LOF基金行情

> 基金 / 基金行情 / 行情与K线 / LOF基金行情

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | LOF基金行情 |
| 所属市场 | 基金 |
| 本地路径 | `数据存放目录/time/jjhq/lofjj/{基金代码}` |

## 功能描述

根据《LOF基金列表》得到的基金代码作为参数获取基金的盘中行情。

## 更新机制

- **更新频率**：交易时间段每10分钟。
- **完成耗时**：约1分钟。

## 数据格式

```
{}
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| dm | string | 基金代码（如：sz169201） |
| mc | string | 基金名称（如：浙商鼎盈LOF） |
| zxj | number | 最新价 |
| zde | number | 涨跌额 |
| zdf | number | 涨跌幅（%） |
| b | number | 买入 |
| s | number | 卖出 |
| zs | number | 昨收 |
| jk | number | 今开 |
| zg | number | 最高 |
| zd | number | 最低 |
| cjl | number | 成交量（股） |
| cje | number | 成交额（元） |
| t | string | 时间（HH:mm:ss） |

## 示例

```json
{"dm":"sz169201","mc":"浙商鼎盈LOF","zxj":2.074,"zde":-0.002,"zdf":-0.096,"b":2.031,"s":2.074,"zs":2.078,"jk":2.015,"zg":2.078,"zd":2.015,"cjl":102625,"cje":206957,"t":"15:00:03"}
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/jijinHq_jijin-hangqing.html?maodian=jijin-lofjj-hq-title](https://ig50.com/jijinHq_jijin-hangqing.html?maodian=jijin-lofjj-hq-title)

---

← [返回接口列表](README.md)