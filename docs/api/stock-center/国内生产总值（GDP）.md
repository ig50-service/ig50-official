# 国内生产总值（GDP）

> 沪深数据中心 / 宏观数据 / 宏观经济 / 国内生产总值（GDP）

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 国内生产总值（GDP） |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/time/hongguan/gdp` |

## 功能描述

获取国内生产总值（GDP），按统计时间倒序。

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
| tjyf | string | 统计季度（如"2026年第1-2季度"） |
| zcz | number | 国内生产总值绝对值（亿元） |
| ycz | number | 第一产业绝对值（亿元） |
| ecz | number | 第二产业绝对值（亿元） |
| scz | number | 第三产业绝对值（亿元） |
| zztb | number | 国内生产总值同比增长（%） |
| yztb | number | 第一产业同比增长（%） |
| eztb | number | 第二产业同比增长（%） |
| sztb | number | 第三产业同比增长（%） |

## 示例

```json
[{"tjsj":"2026-06-01","tjyf":"2026年第1-2季度","zcz":695704.000,"ycz":31521.800,"ecz":250472.900,"scz":413709.200,"zztb":4.70,"yztb":3.70,"eztb":3.90,"sztb":5.20},{"tjsj":"2026-03-01","tjyf":"2026年第1季度","zcz":334192.900,"ycz":11940.800,"ecz":116134.900,"scz":206117.200,"zztb":5.00,"yztb":3.80,"eztb":4.90,"sztb":5.20}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-gdp-title](https://ig50.com/sjzx_hongguan-jingji.html?maodian=hongguan-gdp-title)

---

← [返回接口列表](README.md)