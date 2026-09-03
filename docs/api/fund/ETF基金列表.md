# ETF基金列表

> 基金 / 基金档案 / 基金列表 / ETF基金列表

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | ETF基金列表 |
| 所属市场 | 基金 |
| 本地路径 | `数据存放目录/base/etfjj` |

## 功能描述

获取ETF基金的代码和名称，用于下方接口的参数传入。

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
| dm | string | 基金代码（如：sz159999） |
| mc | string | 基金名称（如：永赢中证500ETF） |

## 示例

```json
[{"mc":"科创综指ETF华泰柏瑞","dm":"sh589990"},{"mc":"科创100ETF汇添富","dm":"sh589980"},{"mc":"科创新能源ETF易方达","dm":"sh589960"},{"mc":"科创100ETF富国","dm":"sh589950"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/jijinHq_jijin-liebiao.html?maodian=jijin-etfjj-list-title](https://ig50.com/jijinHq_jijin-liebiao.html?maodian=jijin-etfjj-list-title)

---

← [返回接口列表](README.md)