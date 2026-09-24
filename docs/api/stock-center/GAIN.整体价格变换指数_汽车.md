# GAIN.整体价格变换指数:汽车

> 沪深数据中心 / 行业指数 / 制造与建材 / GAIN.整体价格变换指数:汽车

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | GAIN.整体价格变换指数:汽车 |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/hyzs/gain` |

## 功能描述

获取GAIN.整体价格变换指数:汽车历史走势数据，按统计时间倒序。

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
{"ud":"2026-09-24 17:00:38","gps":"000572,000625,002594,600104,600733,601127,601238,601633","zs":[{"tjsj":"2026-07-01","zbz":-6.72,"zdf":-2.60,"bl3m":-12.94,"bl6m":-2484.62,"bl1n":-175.41,"bl2n":-522.64,"bl3n":-373.17},{"tjsj":"2026-06-01","zbz":-6.55,"zdf":-11.97,"bl3m":-19.53,"bl6m":-235.33,"bl1n":-207.51,"bl2n":-273.74,"bl3n":-376.37}]}
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hyzs-zzjc.html?maodian=hyzs-gain-title](https://ig50.com/sjzx_hyzs-zzjc.html?maodian=hyzs-gain-title)

---

← [返回接口列表](README.md)