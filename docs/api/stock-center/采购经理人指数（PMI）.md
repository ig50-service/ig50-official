# 采购经理人指数（PMI）

> 沪深数据中心 / 宏观数据 / 宏观经济 / 采购经理人指数（PMI）

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 采购经理人指数（PMI） |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/pmi` |

## 功能描述

获取采购经理人指数（PMI），按统计时间倒序，制造业与非制造业同表。

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
| zzy | number | 制造业指数 |
| zztb | number | 制造业指数同比增长（%） |
| fzzy | number | 非制造业指数 |
| fzztb | number | 非制造业指数同比增长（%） |

## 示例

```json
[{"tjsj":"2026-08-01","tjyf":"2026年08月份","zzy":49.80,"zztb":0.81,"fzzy":49.00,"fzztb":-2.58},{"tjsj":"2026-07-01","tjyf":"2026年07月份","zzy":49.20,"zztb":-0.20,"fzzy":49.00,"fzztb":-2.20}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-pmi-title](https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-pmi-title)

---

← [返回接口列表](README.md)