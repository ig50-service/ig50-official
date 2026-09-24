# 居民消费价格指数（CPI）

> 沪深数据中心 / 宏观数据 / 宏观经济 / 居民消费价格指数（CPI）

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 居民消费价格指数（CPI） |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/cpi` |

## 功能描述

获取居民消费价格指数（CPI），按统计时间倒序。

## 更新机制

- **更新频率**：每天21:00。
- **完成耗时**：约1小时。

## 数据格式

```
[{},...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| tjsj | string | 统计时间（yyyy-MM-dd） |
| tjyf | string | 统计月份（如"2026年08月份"） |
| qgdy | number | 全国-当月（定基指数） |
| qgtb | number | 全国-同比增长（%） |
| qghb | number | 全国-环比增长（%） |
| qglj | number | 全国-累计（定基指数） |
| csdy | number | 城市-当月（定基指数） |
| cstb | number | 城市-同比增长（%） |
| cshb | number | 城市-环比增长（%） |
| cslj | number | 城市-累计（定基指数） |
| ncdy | number | 农村-当月（定基指数） |
| nctb | number | 农村-同比增长（%） |
| nchb | number | 农村-环比增长（%） |
| nclj | number | 农村-累计（定基指数） |

## 示例

```json
[{"tjsj":"2026-08-01","tjyf":"2026年08月份","qgdy":100.80,"qgtb":0.80,"qghb":0.40,"qglj":100.90,"csdy":100.80,"cstb":0.80,"cshb":0.40,"cslj":100.90,"ncdy":100.70,"nctb":0.70,"nchb":0.40,"nclj":100.70},{"tjsj":"2026-07-01","tjyf":"2026年07月份","qgdy":100.50,"qgtb":0.50,"qghb":-0.10,"qglj":100.90,"csdy":100.50,"cstb":0.50,"cshb":-0.10,"cslj":101.00,"ncdy":100.40,"nctb":0.40,"nchb":-0.20,"nclj":100.70}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-cpi-title](https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-cpi-title)

---

← [返回接口列表](README.md)