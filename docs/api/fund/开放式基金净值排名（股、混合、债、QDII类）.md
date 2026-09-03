# 开放式基金净值排名（股、混合、债、QDII类）

> 基金 / 基金统计 / 业绩与净值排名 / 开放式基金净值排名（股、混合、债、QDII类）

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | 开放式基金净值排名（股、混合、债、QDII类） |
| 所属市场 | 基金 |
| 本地路径 | `数据存放目录/all/jjsjzx/jjjz/{基金分类参数}` |

## 功能描述

根据【基金分类参数】（见下方"【基金分类参数】说明"）获取不同分类下的开放式基金的净值排名，根据净值日期倒序。

## 更新机制

- **更新频率**：每天20:30。
- **完成耗时**：约60分钟。

## 数据格式

```
[{},...]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| dm | string | 基金代码（如：000001（华夏成长混合）） |
| mc | string | 基金名称（如：华夏成长混合） |
| dwjz | number | 单位净值 |
| ljjz | number | 累计净值 |
| qyrjz | number | 前一日净值 |
| zde | number | 涨跌额 |
| zzl | number | 增长率（%） |
| sgzt | string | 申购状态 |
| jzrq | string | 净值日期 |
| glr | string | 基金管理人 |
| jjlx | string | 基金类型 |

## 示例

```json
[{"dm":"000008","mc":"嘉实中证500ETF联接A","dwjz":1.9013,"ljjz":1.9673,"qyrjz":1.902,"zde":0.0000,"zzl":-0.04,"sgzt":"开放","jzrq":"2021-07-16","glr":"何如、陈正宪","jjlx":"偏股型基金"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/jijinHq_jijin-paiming.html?maodian=jijin-jingzhi-kaifang-title](https://ig50.com/jijinHq_jijin-paiming.html?maodian=jijin-jingzhi-kaifang-title)

---

← [返回接口列表](README.md)