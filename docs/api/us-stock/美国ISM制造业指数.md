# 美国ISM制造业指数

> 美股 / 其它数据 / 宏观数据 / 美国ISM制造业指数

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 美国ISM制造业指数 |
| 所属市场 | 美股 |
| 本地路径 | `数据存放目录/time/us/hongguan/ism` |

## 功能描述

获取美国ISM制造业指数，按统计时间倒序。

## 更新机制

- **更新频率**：每天美东时间18:00。
- **完成耗时**：耗时约1个小时。

## 数据格式

```
[{},...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| tjsj | string | 统计时间（yyyy-MM-dd） |
| tjyf | string | 统计月份（中文，如“2026年09月”） |
| qz | number | 前值（指数，50为荣枯线） |
| xz | number | 现值（指数，50为荣枯线，最新期未发布时为null） |
| gbsj | string | 发布日期（yyyy-MM-dd） |

## 示例

```json
[{"tjsj":"2026-09-01","tjyf":"2026年09月","qz":54.60,"xz":null,"gbsj":"2026-10-01"},{"tjsj":"2026-08-01","tjyf":"2026年08月","qz":55.60,"xz":54.60,"gbsj":"2026-09-01"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/indexUs_us-hongguan.html?maodian=us-hongguan-ism-title](https://ig50.com/indexUs_us-hongguan.html?maodian=us-hongguan-ism-title)

---

← [返回接口列表](README.md)