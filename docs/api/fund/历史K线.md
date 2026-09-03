# 历史K线

> 基金 / 基金行情 / 行情与K线 / 历史K线

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 历史K线 |
| 所属市场 | 基金 |
| 本地路径 | `数据存放目录/time/history/trade/{基金代码}/{分时级别}` |

## 功能描述

根据基金代码（《封闭式基金列表》、《ETF基金列表》、《LOF基金列表》接口获取的基金代码）获取历史日K数据。交易时间升序。目前分时级别支持日、周、月、季、年级别，对应的参数分别是Day、Week、Month、Quarter、Year

## 更新机制

- **更新频率**：每日16点更新。
- **完成耗时**：耗时约30分钟。

## 数据格式

```
[{},..]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| d | string | 交易时间（yyyy-MM-dd） |
| o | number | 开盘价（元） |
| h | number | 最高价（元） |
| l | number | 最低价（元） |
| c | number | 收盘价（元） |
| v | number | 成交量（股） |
| zde | number | 涨跌额（元） |
| zd | number | 涨跌幅（%） |
| zf | number | 振幅（%） |
| zs | number | 昨收（元） |

## 示例

```json
[{"d":"2021-10-15","o":4.283,"h":4.288,"l":4.276,"c":4.287,"v":2510820,"zf":0.28,"zd":0.12,"zde":0.005,"zs":3.044,"ud":"2026-05-03 23:45:50"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/jijinHq_jijin-hangqing.html?maodian=jijin-kline-his-title](https://ig50.com/jijinHq_jijin-hangqing.html?maodian=jijin-kline-his-title)

---

← [返回接口列表](README.md)