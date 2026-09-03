# ROE排行

> 沪深数据中心 / 数据中心 / 市场表现 / ROE排行

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | ROE排行 |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/all/roe` |

## 功能描述

沪深京A股ROE排名，根据roe倒序。

## 更新机制

- **更新频率**：每天16:30。
- **完成耗时**：约2分钟。

## 数据格式

```
[{}...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| dm | string | 股票代码 |
| mc | string | 股票名称 |
| roe | number | ROE（%） |
| zsz | number | 总市值（元） |
| jzc | number | 净资产（元） |
| jlr | number | 净利润（元） |
| syld | number | 市盈率（动） |
| sjl | number | 市净率 |
| mll | number | 毛利率（%） |
| jll | number | 净利率（%） |
| hyroe | number | 行业平均ROE（%） |
| hyzsz | number | 行业平均总市值（元） |
| hyjzc | number | 行业平均净资产（元） |
| hyjlr | number | 行业平均净利润（元） |
| hysyld | number | 行业平均市盈率（动） |
| hysjl | number | 行业平均市净率 |
| hymll | number | 行业平均毛利率（%） |
| hyjll | number | 行业平均净利率（%） |
| roepm | number | ROE行业排名 |
| zszpm | number | 总市值行业排名 |
| jzcpm | number | 净资产行业排名 |
| jlrpm | number | 净利润行业排名 |
| syldpm | number | 市盈率行业排名 |
| sjlpm | number | 市净率行业排名 |
| mllpm | number | 毛利率行业排名 |
| jllpm | number | 净利率行业排名 |
| hym | string | 行业名 |
| hygpzs | number | 同行业股票总数量 |

## 示例

```json
[{"dm":"000001","mc":"平安银行","zsz":601169,"jzc":2.33152E+11,"jlr":0,"syld":3.85,"sjl":0.44,"mll":0.0,"jll":36.811763051599996,"roe":11.34,"hym":"银行","hyzsz":237030692482.74,"hyjzc":465348529679.55,"hyjlr":37953741650.74,"hysyld":6.47,"hysjl":0.72,"hymll":0.0,"hyjll":33.74,"hyroe":10.44,"hygpzs":42,"zszpm":17,"jzcpm":16,"jlrpm":18,"syldpm":4,"sjlpm":6,"mllpm":21,"jllpm":15,"roepm":13}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_data-market-per.html?maodian=data-market-per-roe](https://ig50.com/sjzx_data-market-per.html?maodian=data-market-per-roe)

---

← [返回接口列表](README.md)