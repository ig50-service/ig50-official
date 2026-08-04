# 最新K线

> 基金行情档案 / 基金行情 / 基金K线 / 最新K线

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 基金行情档案-基金行情-基金K线-最新K线 |
| 所属市场 | 基金行情档案 |
| 本地路径 | `数据存放目录/time/real/time/{基金代码}/{分时级别}` |

## 功能描述

根据基金代码（《封闭式基金列表》、《ETF基金列表》、《LOF基金列表》接口获取的基金代码）获取最新K线数据。目前分时级别支持日、周、月、季、年级别，对应的参数分别是Day、Week、Month、Quarter、Year

## 更新机制

- **更新频率**：每日16点更新
- **完成耗时**：耗时约30分钟

## 数据格式

```
{}
```

## 字段说明

交易时间，yyyy-MM-dd, 开盘价（元）, 最高价（元）, 最低价（元）, 收盘价（元）, 成交量（股）, 涨跌额（元）, 涨跌幅（%）, 振幅（%）

## 官网文档

完整字段说明与示例数据：[https://ig50.com/jijinHq_jijin-kline.html?maodian=jijin-kline-new-title](https://ig50.com/jijinHq_jijin-kline.html?maodian=jijin-kline-new-title)

---

← [返回接口列表](README.md)
