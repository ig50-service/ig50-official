# QFII重仓股

> 沪深数据中心 / 数据中心 / 机构持股 / QFII重仓股

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | QFII重仓股 |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/all/orgqfiizc/{年份_季度}` |

## 功能描述

QFII重仓股，支持“年份_季度”查询，年份可选（1989~当前年份），季度可选（1:一季报，2：中报，3：三季报，4：年报），如“2021_1”，表示查询2021年一季度数据。

## 更新机制

- **更新频率**：每周六上午9点。
- **完成耗时**：约5小时。

## 数据格式

```
[{}...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| dm | string | 股票代码 |
| mc | string | 股票名称 |
| ed | string | 截止日期 |
| js | number | 机构数 |
| bq | number | 本期持股数（万股） |
| ltb | number | 持股占已流通A股比例（%） |
| szj | number | 同上期增减（万股） |
| cbl | number | 持股比例（%） |
| sjs | number | 上期机构数 |
| dt | array<object> | 机构明细（object对象属性详见下方） |
| y | number | 报告年份（如2021） |
| q | number | 报告季度（1:一季报，2：中报，3：三季报，4：年报） |
| yq | string | 报告年份季度含义（如“2021年一季报”） |
| c | string | 机构代码 |
| n | string | 机构全名 |
| bqcy | string | 本期持有（万股） |
| abl | string | 持股占已流通A股比例（%） |
| szj | string | 同上期增减（万股） |
| bzf | string | 持股比例增幅（%） |
| gbl | string | 上期持股比例（%） |

## 示例

```json
[{"dm":"600298","mc":"安琪酵母","ed":"2021-03-31","js":1,"bq":780.7949,"ltb":0.95,"szj":-49.8400,"cbl":1.01,"sjs":1,"dt":[{"c":"70304309","n":"科威特政府投资局－自有资金","bqcy":"780.7949","abl":"0.95","szj":"-49.8400","bzf":"-6.00","gbl":"1.01"}],"y":2021,"q":1,"yq":"2021年一季报"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_data-market-org.html?maodian=data-market-org-qfiizc](https://ig50.com/sjzx_data-market-org.html?maodian=data-market-org-qfiizc)

---

← [返回接口列表](README.md)