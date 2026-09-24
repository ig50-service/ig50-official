# LPR数据

> 沪深数据中心 / 宏观数据 / 金融货币 / LPR数据

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | LPR数据 |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/lpr` |

## 功能描述

获取LPR数据，按交易日期倒序。

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
| tjsj | string | 交易日期（yyyy-MM-dd） |
| lpr1y | number | 1年期LPR（%） |
| lpr5y | number | 5年期以上LPR（%） |
| dqll | number | 短期贷款利率：6个月至1年（含）（%） |
| cqll | number | 中长期贷款利率：5年以上（%） |

## 示例

```json
[{"tjsj":"2026-09-20","lpr1y":3.00,"lpr5y":3.50,"dqll":4.35,"cqll":4.90},{"tjsj":"2026-08-20","lpr1y":3.00,"lpr5y":3.50,"dqll":4.35,"cqll":4.90}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hongguan-jinrong.html?maodian=hongguan-lpr-title](https://ig50.com/sjzx_hongguan-jinrong.html?maodian=hongguan-lpr-title)

---

← [返回接口列表](README.md)