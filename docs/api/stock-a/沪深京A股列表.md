# 沪深京A股列表

> 沪深京A股 / 股票基础信息 / 股票板块概念 / 沪深京A股列表

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 沪深京A股列表 |
| 所属市场 | 沪深京A股 |
| 本地路径 | `数据存放目录/base/gplist` |

## 功能描述

获取基础的股票代码和名称，用于后续接口的参数传入。

## 更新机制

- **更新频率**：每天16点更新。
- **完成耗时**：约10分钟。

## 数据格式

```
[{},...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| dm | string | 股票代码（如：000001） |
| mc | string | 股票名称（如：平安银行） |
| jys | string | 交易所（"sh"表示上证/"sz"表示深证/"bj"表示北证） |
| isCyb | number | 是否属于创业板（0否/1是） |
| isKcb | number | 是否属于科创板（0否/1是） |
| isSt | number | 是否ST（0否/1是） |
| isNew | number | 是否是新股（0否/1是） |

## 示例

```json
[{"dm":"688300","mc":"联瑞新材","jys":"sh","isCyb":0,"isKcb":1,"isSt":0,"isNew":0}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/index_gplist.html?maodian=gupiao-gplbjk-title](https://ig50.com/index_gplist.html?maodian=gupiao-gplbjk-title)

---

← [返回接口列表](README.md)