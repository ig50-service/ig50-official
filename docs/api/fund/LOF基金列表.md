# LOF基金列表

> 基金 / 基金档案 / 基金列表 / LOF基金列表

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | LOF基金列表 |
| 所属市场 | 基金 |
| 本地路径 | `数据存放目录/base/lofjj` |

## 功能描述

获取LOF基金的代码和名称，用于下方接口的参数传入。

## 更新机制

- **更新频率**：每天16:00。
- **完成耗时**：约1分钟。

## 数据格式

```
[{},...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| dm | string | 基金代码（如：sz169201） |
| mc | string | 基金名称（如：浙商鼎盈LOF） |

## 示例

```json
[{"mc":"科创板长城","dm":"sh506008"},{"mc":"汇添富科创板","dm":"sh506006"},{"mc":"科创板博时","dm":"sh506005"},{"mc":"富国科创板","dm":"sh506003"},{"mc":"易方达科创板","dm":"sh506002"},{"mc":"万家科创板","dm":"sh506001"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/jijinHq_jijin-liebiao.html?maodian=jijin-lofjj-list-title](https://ig50.com/jijinHq_jijin-liebiao.html?maodian=jijin-lofjj-list-title)

---

← [返回接口列表](README.md)