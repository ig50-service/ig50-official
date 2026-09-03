# AH股比价

> 沪深数据中心 / 资金流向 / 南向、北向资金 / AH股比价

> 本页为镜像文档，**最新接口、字段、路径以 [官网接口文档](https://ig50.com/index.html) 为准**。

## 接口说明

| 项目 | 内容 |
|------|------|
| 数据名称 | AH股比价 |
| 所属市场 | 沪深数据中心 |
| 本地路径 | `数据存放目录/all/nxbx/ahgbj` |

## 功能描述

AH股比价，按涨跌幅降序。

## 更新机制

- **更新频率**：每天20:00。
- **完成耗时**：约10分钟。

## 数据格式

```
[{}]
```

## 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| mc | string | 名称 |
| hdm | string | H股代码 |
| hzxj | number | H股最新价（HKD） |
| hzdf | number | H股涨跌幅（%） |
| adm | string | A股代码 |
| azxj | number | A股最新价（RMB） |
| azdf | number | A股涨跌幅（%） |
| ahbj | number | 比价（A/H） |
| ahyj | number | 溢价（A/H）% |
| t | string | 更新时间（yyyy-MM-ddHH:mm:ss） |

## 示例

```json
[{"hdm":"00107","ahbj":2.49,"t":"2022-04-22 00:10:19","hzxj":2.01,"hzdf":3.08,"ahyj":149.48,"mc":"四川成渝","azxj":4.12,"azdf":-5.72,"adm":"601107"}]
```

## 官网文档

完整字段说明与示例数据：[https://ig50.com/sjzx_zjlx-nxbx.html?maodian=zjlx-nxbx-ahgbj](https://ig50.com/sjzx_zjlx-nxbx.html?maodian=zjlx-nxbx-ahgbj)

---

← [返回接口列表](README.md)