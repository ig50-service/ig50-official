# Hibor人民币（3月）

> 沪深数据中心 / 宏观数据 / 拆借利率 / Hibor人民币（3月）

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | Hibor人民币（3月） |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/hibor/cnh3m` |

## 功能描述

获取香港银行同业拆借市场-Hibor人民币-3月数据，按日期倒序。

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
| tjsj | string | 统计日期（yyyy-MM-dd） |
| ll | number | 利率（%） |
| zd | number | 涨跌（BP） |

## 示例

```json
[{"tjsj":"2026-09-22","ll":1.62,"zd":-1.39},{"tjsj":"2026-09-21","ll":1.63,"zd":0.09}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hongguan-chajie.html?maodian=hongguan-hibor-cnh3m-title](https://ig50.com/sjzx_hongguan-chajie.html?maodian=hongguan-hibor-cnh3m-title)

---

← [返回接口列表](README.md)