# 新造船价格指数:CNTPI指数

> 沪深数据中心 / 行业指数 / 制造与建材 / 新造船价格指数:CNTPI指数

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 新造船价格指数:CNTPI指数 |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/hyzs/xzc` |

## 功能描述

获取新造船价格指数:CNTPI指数历史走势数据，按统计时间倒序。

## 更新机制

- **更新频率**：每天21:00。
- **完成耗时**：约1小时。

## 数据格式

```
{}
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| ud | string | 更新时间（yyyy-MM-ddHH:mm:ss） |
| gps | string | 相关板块成分股纯股票代码，英文逗号分隔 |
| zs | array | 历史走势数组（元素字段如下） |
| tjsj | string | 统计时间（yyyy-MM-dd） |
| zbz | number | 指标值 |
| zdf | number | 最新涨跌幅（%，较上期） |
| bl3m | number | 3月涨跌幅（%） |
| bl6m | number | 6月涨跌幅（%） |
| bl1n | number | 1年涨跌幅（%） |
| bl2n | number | 2年涨跌幅（%） |
| bl3n | number | 3年涨跌幅（%） |

## 示例

```json
{"ud":"2026-09-24 17:00:37","gps":"300008,300065,300589,300600,300810,600150,600685,600764,601890,603268","zs":[{"tjsj":"2017-12-16","zbz":823.00,"zdf":0.12,"bl3m":0.12,"bl6m":0.00,"bl1n":-2.49,"bl2n":-12.91,"bl3n":-17.37},{"tjsj":"2017-11-30","zbz":822.00,"zdf":0.00,"bl3m":0.49,"bl6m":-0.36,"bl1n":-3.97,"bl2n":-13.75,"bl3n":-17.47}]}
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hyzs-zzjc.html?maodian=hyzs-xzc-title](https://ig50.com/sjzx_hyzs-zzjc.html?maodian=hyzs-xzc-title)

---

← [返回接口列表](README.md)