# 工业品出厂价格指数（PPI）

> 沪深数据中心 / 宏观数据 / 宏观经济 / 工业品出厂价格指数（PPI）

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 工业品出厂价格指数（PPI） |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/ppi` |

## 功能描述

获取工业品出厂价格指数（PPI），按统计时间倒序。

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
| dy | number | 当月（定基指数） |
| tb | number | 当月同比增长（%） |
| lj | number | 累计（定基指数） |

## 示例

```json
[{"tjsj":"2026-08-01","tjyf":"2026年08月份","dy":103.80,"tb":3.80,"lj":102.00},{"tjsj":"2026-07-01","tjyf":"2026年07月份","dy":103.50,"tb":3.50,"lj":101.80}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-ppi-title](https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-ppi-title)

---

← [返回接口列表](README.md)