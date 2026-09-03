# 接口文档

> IG50 共提供 **331 个数据集**，覆盖沪深京A股、沪深数据中心、基金、港股、美股五大板块。所有数据以 JSON 文本文件落盘到本地，直接读取即可使用。

> ⚠ **最新接口更新以 [官网接口文档](https://ig50.com/dataset-overview.html) 为准**。本仓库为镜像文档，可能滞后于官网，如需查阅最新接口、字段、路径，请访问 [官网接口文档](https://ig50.com/dataset-overview.html) 或 [官网数据检索](https://ig50.com/search.html)。

## 数据存放说明

数据默认存放目录：`/ig50-data`（可在 `ig50_user_config.properties` 的 `server.data.dir` 中修改）

路径模式：
- `base/xxx` — 基础列表类数据，每日整体更新
- `all/xxx` — 全市场汇总数据，按日期/参数更新
- `time/{股票代码}/xxx` — 按标的分目录的时序数据

## 数据格式

所有数据均为 JSON 格式：
- `[{}, ...]` — JSON 数组，每个元素为一条记录
- `{}` — JSON 对象
- `{"key": {}, ...}` — 带分类 key 的对象

---

## 沪深京A股

> 135个数据集 · 实时行情(3秒)、L2五档盘口、逐笔交易、历史K线、F10全档案

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 1 | [沪深京A股列表](stock-a/沪深京A股列表.md) | `base/gplist` | 每天16点更新。 |
| 2 | [新股日历](stock-a/新股日历.md) | `all/xgrl` | 每天16点更新。 |
| 3 | [指数、行业、概念树](stock-a/指数、行业、概念树.md) | `base/it` | 每周六凌晨3点更新。 |
| 4 | [根据指数、行业、概念找股票](stock-a/根据指数、行业、概念找股票.md) | `time/indextree/{指数、行业、概念代码}` | 每周六凌晨3点更新。 |
| 5 | [根据股票找指数、行业、概念](stock-a/根据股票找指数、行业、概念.md) | `time/iii/{股票代码}` | 每周六凌晨3点更新。 |
| 6 | [涨停股池](stock-a/涨停股池.md) | `time/zdtgc/ztgc/{日期}` | 交易时间段每10分钟更新。 |
| 7 | [跌停股池](stock-a/跌停股池.md) | `time/zdtgc/dtgc/{日期}` | 交易时间段每10分钟更新。 |
| 8 | [强势股池](stock-a/强势股池.md) | `time/zdtgc/qsgc/{日期}` | 交易时间段每10分钟更新。 |
| 9 | [次新股池](stock-a/次新股池.md) | `time/zdtgc/cxgc/{日期}` | 交易时间段每10分钟更新。 |
| 10 | [炸板股池](stock-a/炸板股池.md) | `time/zdtgc/zbgc/{日期}` | 交易时间段每10分钟更新。 |
| 11 | [公司简介](stock-a/公司简介.md) | `time/f10/info/{股票代码}` | 每天17:30更新。 |
| 12 | [所属指数](stock-a/所属指数.md) | `time/f10/index/{股票代码}` | 每天17:30更新。 |
| 13 | [所属板块](stock-a/所属板块.md) | `time/f10/ssbk/{股票代码}` | 每天17:30更新。 |
| 14 | [经营范围](stock-a/经营范围.md) | `time/f10/jyfw/{股票代码}` | 每天17:30更新。 |
| 15 | [主营业务](stock-a/主营业务.md) | `time/f10/zyyw/{股票代码}` | 每天17:30更新。 |
| 16 | [行业背景](stock-a/行业背景.md) | `time/f10/hybj/{股票代码}` | 每天17:30更新。 |
| 17 | [核心竞争力](stock-a/核心竞争力.md) | `time/f10/hxjzl/{股票代码}` | 每天17:30更新。 |
| 18 | [概念题材板块](stock-a/概念题材板块.md) | `time/f10/hxtc/{股票代码}` | 每天17:30更新。 |
| 19 | [题材详情](stock-a/题材详情.md) | `time/f10/tcxq/{股票代码}` | 每天17:30更新。 |
| 20 | [名称变动](stock-a/名称变动.md) | `time/f10/mcbg/{股票代码}` | 每天17:30更新。 |
| 21 | [并购重组](stock-a/并购重组.md) | `time/f10/bgcz/{股票代码}` | 每天17:30更新。 |
| 22 | [参股控股](stock-a/参股控股.md) | `time/f10/cgkg/{股票代码}` | 每天17:30更新。 |
| 23 | [主营构成](stock-a/主营构成.md) | `time/f10/maincompose/{股票代码}` | 每天17:30更新。 |
| 24 | [经营评述](stock-a/经营评述.md) | `time/f10/bizreview/{股票代码}` | 每天17:30更新。 |
| 25 | [员工竞争力](stock-a/员工竞争力.md) | `time/f10/employee/{股票代码}` | 每天17:30更新。 |
| 26 | [业务竞争力](stock-a/业务竞争力.md) | `time/f10/businesscomp/{股票代码}` | 每天17:30更新。 |
| 27 | [研发投入](stock-a/研发投入.md) | `time/f10/rdinput/{股票代码}` | 每天17:30更新。 |
| 28 | [研发人员](stock-a/研发人员.md) | `time/f10/rdstaff/{股票代码}` | 每天17:30更新。 |
| 29 | [客户及供应商](stock-a/客户及供应商.md) | `time/f10/custsupp/{股票代码}` | 每天17:30更新。 |
| 30 | [十大股东](stock-a/十大股东.md) | `time/f10/zygd/{股票代码}` | 每天17:30更新。 |
| 31 | [十大股东（详）](stock-a/十大股东（详）.md) | `time/f10/sdgd/{股票代码}` | 每天17:30更新。 |
| 32 | [十大流通股东](stock-a/十大流通股东.md) | `time/f10/zygdlt/{股票代码}` | 每天17:30更新。 |
| 33 | [十大流通股东（详）](stock-a/十大流通股东（详）.md) | `time/f10/sdhltgd/{股票代码}` | 每天17:30更新。 |
| 34 | [股东变化趋势](stock-a/股东变化趋势.md) | `time/f10/gdbh/{股票代码}` | 每天17:30更新。 |
| 35 | [基金持股](stock-a/基金持股.md) | `time/f10/jjcg/{股票代码}` | 每周六9点更新。 |
| 36 | [股东人数](stock-a/股东人数.md) | `time/f10/gdrs/{股票代码}` | 每天17:30更新。 |
| 37 | [机构持仓](stock-a/机构持仓.md) | `time/f10/jgcc/{股票代码}` | 每天17:30更新。 |
| 38 | [机构明细](stock-a/机构明细.md) | `time/f10/jgmx/{股票代码}` | 每天17:30更新。 |
| 39 | [沪深港通持股](stock-a/沪深港通持股.md) | `time/f10/hsgtcg/{股票代码}` | 每天17:30更新。 |
| 40 | [解禁限售](stock-a/解禁限售.md) | `time/f10/jjxs/{股票代码}` | 每天17:30更新。 |
| 41 | [股本结构](stock-a/股本结构.md) | `time/f10/gbjg/{股票代码}` | 每天17:30更新。 |
| 42 | [历届高管成员](stock-a/历届高管成员.md) | `time/f10/gg/{股票代码}` | 每天17:30更新。 |
| 43 | [高管列表](stock-a/高管列表.md) | `time/f10/gsgg/{股票代码}` | 每天17:30更新。 |
| 44 | [管理层简介](stock-a/管理层简介.md) | `time/f10/glcjj/{股票代码}` | 每天17:30更新。 |
| 45 | [高管持股变动](stock-a/高管持股变动.md) | `time/f10/ggcgbd/{股票代码}` | 每天17:30更新。 |
| 46 | [高管持股交易](stock-a/高管持股交易.md) | `time/f10/ggcgbdtrade/{股票代码}` | 每天17:30更新。 |
| 47 | [历届董事会成员](stock-a/历届董事会成员.md) | `time/f10/ds/{股票代码}` | 每天17:30更新。 |
| 48 | [历届监事会成员](stock-a/历届监事会成员.md) | `time/f10/js/{股票代码}` | 每天17:30更新。 |
| 49 | [财务指标](stock-a/财务指标.md) | `time/f10/fi/{股票代码}` | 每天17:30更新。 |
| 50 | [近一年各季度利润](stock-a/近一年各季度利润.md) | `time/f10/pf/{股票代码}` | 每天17:30更新。 |
| 51 | [近一年各季度现金流](stock-a/近一年各季度现金流.md) | `time/f10/cf/{股票代码}` | 每天17:30更新。 |
| 52 | [资产负债表](stock-a/资产负债表.md) | `time/f10/balance/{股票代码}` | 每天17:30更新。 |
| 53 | [利润表](stock-a/利润表.md) | `time/f10/income/{股票代码}` | 每天17:30更新。 |
| 54 | [现金流量表](stock-a/现金流量表.md) | `time/f10/cashflow/{股票代码}` | 每天17:30更新。 |
| 55 | [资产负债与利润占比](stock-a/资产负债与利润占比.md) | `time/f10/finratio/{股票代码}` | 每天17:30更新。 |
| 56 | [每股收益](stock-a/每股收益.md) | `time/f10/mainindexps/{股票代码}` | 每天17:30更新。 |
| 57 | [成长能力](stock-a/成长能力.md) | `time/f10/mainindexgrowth/{股票代码}` | 每天17:30更新。 |
| 58 | [盈利能力](stock-a/盈利能力.md) | `time/f10/mainindexprofit/{股票代码}` | 每天17:30更新。 |
| 59 | [营运能力](stock-a/营运能力.md) | `time/f10/mainindexop/{股票代码}` | 每天17:30更新。 |
| 60 | [现金质量](stock-a/现金质量.md) | `time/f10/mainindexquality/{股票代码}` | 每天17:30更新。 |
| 61 | [风险指标](stock-a/风险指标.md) | `time/f10/mainindexrisk/{股票代码}` | 每天17:30更新。 |
| 62 | [杜邦分析（核心指标）](stock-a/杜邦分析（核心指标）.md) | `time/f10/dupontcore/{股票代码}` | 每天17:30更新。 |
| 63 | [杜邦分析（资产负债）](stock-a/杜邦分析（资产负债）.md) | `time/f10/dupontbs/{股票代码}` | 每天17:30更新。 |
| 64 | [杜邦分析（利润）](stock-a/杜邦分析（利润）.md) | `time/f10/dupontis/{股票代码}` | 每天17:30更新。 |
| 65 | [杜邦比较](stock-a/杜邦比较.md) | `time/f10/dbfx/{股票代码}` | 每天17:30更新。 |
| 66 | [评级统计](stock-a/评级统计.md) | `time/f10/pjtj/{股票代码}` | 每天17:30更新。 |
| 67 | [机构预测](stock-a/机构预测.md) | `time/f10/jgyc/{股票代码}` | 每天17:30更新。 |
| 68 | [预测统计](stock-a/预测统计.md) | `time/f10/yctj/{股票代码}` | 每天17:30更新。 |
| 69 | [预测明细](stock-a/预测明细.md) | `time/f10/ycmx/{股票代码}` | 每天17:30更新。 |
| 70 | [近年分红](stock-a/近年分红.md) | `time/f10/share/{股票代码}` | 每天17:30更新。 |
| 71 | [近年增发](stock-a/近年增发.md) | `time/f10/zf/{股票代码}` | 每天17:30更新。 |
| 72 | [融资融券标的股](stock-a/融资融券标的股.md) | `base/rzrqGpList` | 每天上午8:50更新。 |
| 73 | [融资融券历史走势](stock-a/融资融券历史走势.md) | `time/rzrq/{股票代码}` | 每天上午8:50更新。 |
| 74 | [派现与募资对比](stock-a/派现与募资对比.md) | `time/pxymz/{股票代码}` | 每天20:30更新。 |
| 75 | [质押明细](stock-a/质押明细.md) | `time/zhiya/{股票代码}` | 每天20:30更新。 |
| 76 | [回购数据全览](stock-a/回购数据全览.md) | `time/hgzl/{股票代码}` | 每天20:30更新。 |
| 77 | [并购重组一览](stock-a/并购重组一览.md) | `time/bgcz/{股票代码}` | 每天20:30更新。 |
| 78 | [分红影响](stock-a/分红影响.md) | `time/f10/dividend/{股票代码}` | 每天17:30更新。 |
| 79 | [历年分红融资](stock-a/历年分红融资.md) | `time/f10/dividendcompre/{股票代码}` | 每天17:30更新。 |
| 80 | [分红排名](stock-a/分红排名.md) | `time/f10/dividendrank/{股票代码}` | 每天17:30更新。 |
| 81 | [增发明细](stock-a/增发明细.md) | `time/f10/dividendseo/{股票代码}` | 每天17:30更新。 |
| 82 | [配股](stock-a/配股.md) | `time/f10/pgmx/{股票代码}` | 每天17:30更新。 |
| 83 | [优先股](stock-a/优先股.md) | `time/f10/yxgxm/{股票代码}` | 每天17:30更新。 |
| 84 | [债券](stock-a/债券.md) | `time/f10/zqmx/{股票代码}` | 每天17:30更新。 |
| 85 | [募集资金来源](stock-a/募集资金来源.md) | `time/f10/zbyzcjsjly/{股票代码}` | 每天17:30更新。 |
| 86 | [股权质押](stock-a/股权质押.md) | `time/f10/gqzy/{股票代码}` | 每天17:30更新。 |
| 87 | [对外担保](stock-a/对外担保.md) | `time/f10/wdb/{股票代码}` | 每天17:30更新。 |
| 88 | [诉讼仲裁](stock-a/诉讼仲裁.md) | `time/f10/sszc/{股票代码}` | 每天17:30更新。 |
| 89 | [监管措施](stock-a/监管措施.md) | `time/f10/jgcs/{股票代码}` | 每天17:30更新。 |
| 90 | [成长性比较](stock-a/成长性比较.md) | `time/f10/cz/{股票代码}` | 每天17:30更新。 |
| 91 | [估值比较](stock-a/估值比较.md) | `time/f10/gz/{股票代码}` | 每天17:30更新。 |
| 92 | [股价表现](stock-a/股价表现.md) | `time/f10/gjbx/{股票代码}` | 每天17:30更新。 |
| 93 | [公司规模](stock-a/公司规模.md) | `time/f10/gsgm/{股票代码}` | 每天17:30更新。 |
| 94 | [同行业个股排名](stock-a/同行业个股排名.md) | `time/f10/glgghyggpm/{股票代码}` | 每天17:30更新。 |
| 95 | [同行业涨幅排名](stock-a/同行业涨幅排名.md) | `time/f10/glgghyzfpm/{股票代码}` | 每天17:30更新。 |
| 96 | [同地域个股排名](stock-a/同地域个股排名.md) | `time/f10/glggtdyggpm/{股票代码}` | 每天17:30更新。 |
| 97 | [同地域涨幅排名](stock-a/同地域涨幅排名.md) | `time/f10/glggtdyzfpm/{股票代码}` | 每天17:30更新。 |
| 98 | [个股龙虎榜](stock-a/个股龙虎榜.md) | `time/f10/lhb/{股票代码}` | 每天17:30更新。 |
| 99 | [营业部买卖统计](stock-a/营业部买卖统计.md) | `time/f10/lhbyyb/{股票代码}` | 每天17:30更新。 |
| 100 | [机构买卖统计](stock-a/机构买卖统计.md) | `time/f10/lhbjg/{股票代码}` | 每天17:30更新。 |
| 101 | [机构评级](stock-a/机构评级.md) | `time/f10/jgpj/{股票代码}` | 每天17:30更新。 |
| 102 | [资金走势对照](stock-a/资金走势对照.md) | `time/zijin/zlzjzs/{股票代码}` | 每天20:00更新。 |
| 103 | [资金流入趋势](stock-a/资金流入趋势.md) | `time/zijin/zjlrqs/{股票代码}` | 每天20:00更新。 |
| 104 | [阶段主力动向](stock-a/阶段主力动向.md) | `time/zijin/jdzldx/{股票代码}` | 每天20:00更新。 |
| 105 | [历史成交分布](stock-a/历史成交分布.md) | `time/zijin/lscjfb/{股票代码}` | 每天20:00更新。 |
| 106 | [近年业绩预告](stock-a/近年业绩预告.md) | `time/f10/ep/{股票代码}` | 每天17:30更新。 |
| 107 | [重大事项公告](stock-a/重大事项公告.md) | `time/gonggao/zdsx/{股票代码}` | 每天20:00更新。 |
| 108 | [财务报告公告](stock-a/财务报告公告.md) | `time/gonggao/cwbg/{股票代码}` | 每天20:00更新。 |
| 109 | [融资公告](stock-a/融资公告.md) | `time/gonggao/rzgg/{股票代码}` | 每天20:00更新。 |
| 110 | [风险提示公告](stock-a/风险提示公告.md) | `time/gonggao/fxts/{股票代码}` | 每天20:00更新。 |
| 111 | [资产重组公告](stock-a/资产重组公告.md) | `time/gonggao/zccz/{股票代码}` | 每天20:00更新。 |
| 112 | [信息变更公告](stock-a/信息变更公告.md) | `time/gonggao/xxbg/{股票代码}` | 每天20:00更新。 |
| 113 | [持股变动公告](stock-a/持股变动公告.md) | `time/gonggao/cgbd/{股票代码}` | 每天20:00更新。 |
| 114 | [所有公告](stock-a/所有公告.md) | `time/history/gonggao/{股票代码}` | 每天20:00更新。 |
| 115 | [项目进度](stock-a/项目进度.md) | `time/f10/zbyzxmjd/{股票代码}` | 每天17:30更新。 |
| 116 | [实时行情数据（3秒落盘）](stock-a/实时行情数据（3秒落盘）.md) | `time/real/{股票代码}` | 交易时间段每10秒。 |
| 117 | [买卖五档盘口（3秒落盘）](stock-a/买卖五档盘口（3秒落盘）.md) | `time/real/trace/level5/{股票代码}` | 交易时间段每10秒。 |
| 118 | [L2行情指标（3秒落盘）](stock-a/L2行情指标（3秒落盘）.md) | `time/real/trace/l2sign/{股票代码}` | 交易时间段每10秒。 |
| 119 | [当天逐笔交易](stock-a/当天逐笔交易.md) | `time/real/trace/onebyone/{股票代码}` | 交易时间段每2分钟。 |
| 120 | [集合竞价](stock-a/集合竞价.md) | `time/real/trace/jhjj/{股票代码}` | 集合竞价时间段（时间段：9:15~9:30，14:47~15:30）每1分钟。 |
| 121 | [盘中异动](stock-a/盘中异动.md) | `all/pzyd` | 交易时间段每1分钟。 |
| 122 | [当天分时成交](stock-a/当天分时成交.md) | `time/real/trace/timedeal/{股票代码}` | 交易时间段每2分钟。 |
| 123 | [当天分价成交占比](stock-a/当天分价成交占比.md) | `time/real/trace/realpercent/{股票代码}` | 每天20:00。 |
| 124 | [当天大单交易](stock-a/当天大单交易.md) | `time/real/trace/bigdeal/{股票代码}` | 每天20:00。 |
| 125 | [最新K线](stock-a/最新K线.md) | `time/real/time/{股票代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新。 |
| 126 | [历史K线（数据范围：短分时两年，日线及以上所有）](stock-a/历史K线（数据范围：短分时两年，日线及以上所有）.md) | `time/history/trade/{股票代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新。 |
| 127 | [沪深主要指数](stock-a/沪深主要指数.md) | `base/shsz` | 每天15:35点。 |
| 128 | [上证系列指数](stock-a/上证系列指数.md) | `base/sh` | 每天15:35点。 |
| 129 | [深证系列指数](stock-a/深证系列指数.md) | `base/sz` | 每天15:35点。 |
| 130 | [中证系列指数](stock-a/中证系列指数.md) | `base/zzzs` | 每天15:35点。 |
| 131 | [指数成分](stock-a/指数成分.md) | `base/zscf` | 每天15:35点。 |
| 132 | [指数实时数据](stock-a/指数实时数据.md) | `time/real/{指数代码（包含sh/sz前缀，如：sh000001）}` | 交易时间段每1分钟。 |
| 133 | [沪深两市上涨下跌数概览](stock-a/沪深两市上涨下跌数概览.md) | `time/real/shszzdbl` | 交易时间段每1分钟。 |
| 134 | [最新K线](stock-a/最新K线-2.md) | `time/real/time/{指数代码（包含sh/sz前缀，如：sh000001）}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新。 |
| 135 | [历史K线（数据范围：短分时两年，日线及以上所有）](stock-a/历史K线（数据范围：短分时两年，日线及以上所有）-2.md) | `time/history/trade/{指数代码（包含sh/sz前缀，如：sh000001）}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新。 |

## 沪深数据中心

> 69个数据集 · 龙虎榜、南北向资金、市场异动、财务五维分析、机构持股

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 1 | [今日交易提示](stock-center/今日交易提示.md) | `all/tt` | 每天15:30。 |
| 2 | [融资融券交易总量](stock-center/融资融券交易总量.md) | `all/rzrqtt` | 每天15:30。 |
| 3 | [融资融券交易明细](stock-center/融资融券交易明细.md) | `all/rzrqdt` | 每天15:30。 |
| 4 | [大宗交易](stock-center/大宗交易.md) | `all/bt` | 每天15:30。 |
| 5 | [解禁限售](stock-center/解禁限售.md) | `all/rb` | 每天15:30。 |
| 6 | [打新收益](stock-center/打新收益.md) | `all/ne` | 每天15:30。 |
| 7 | [历史累计分红](stock-center/历史累计分红.md) | `all/fh` | 每天15:30。 |
| 8 | [每日详情](stock-center/每日详情.md) | `all/ld` | 每天20:00。 |
| 9 | [个股上榜统计](stock-center/个股上榜统计.md) | `all/gg/{近n日}` | 每天15:30。 |
| 10 | [营业部上榜统计](stock-center/营业部上榜统计.md) | `all/yyb/{近n日}` | 每天15:30。 |
| 11 | [机构席位追踪](stock-center/机构席位追踪.md) | `all/jgzz/{近n日}` | 每天15:30。 |
| 12 | [机构席位成交明细](stock-center/机构席位成交明细.md) | `all/jgcj` | 每天15:30。 |
| 13 | [阶段最高最低](stock-center/阶段最高最低.md) | `all/jdgd` | 每天20:00。 |
| 14 | [盘中创新高个股](stock-center/盘中创新高个股.md) | `all/cxg` | 每天20:00。 |
| 15 | [盘中创新低个股](stock-center/盘中创新低个股.md) | `all/cxd` | 每天20:00。 |
| 16 | [成交骤增个股](stock-center/成交骤增个股.md) | `all/cjzz` | 每天20:00。 |
| 17 | [成交骤减个股](stock-center/成交骤减个股.md) | `all/cjzj` | 每天20:00。 |
| 18 | [连续放量个股](stock-center/连续放量个股.md) | `all/lxfl` | 每天20:00。 |
| 19 | [连续缩量个股](stock-center/连续缩量个股.md) | `all/lxsl` | 每天20:00。 |
| 20 | [连续上涨个股](stock-center/连续上涨个股.md) | `all/lxsz` | 每天20:00。 |
| 21 | [连续下跌个股](stock-center/连续下跌个股.md) | `all/lxxd` | 每天20:00。 |
| 22 | [周涨跌排名](stock-center/周涨跌排名.md) | `all/zzdpm` | 每天20:00。 |
| 23 | [月涨跌排名](stock-center/月涨跌排名.md) | `all/yzdpm` | 每天20:00。 |
| 24 | [本周强势股](stock-center/本周强势股.md) | `all/bzqsg` | 每天20:00。 |
| 25 | [本月强势股](stock-center/本月强势股.md) | `all/byqsg` | 每天20:00。 |
| 26 | [流通市值排行](stock-center/流通市值排行.md) | `all/ltsz` | 每天20:00。 |
| 27 | [市盈率排行](stock-center/市盈率排行.md) | `all/syl` | 每天20:00。 |
| 28 | [市净率排行](stock-center/市净率排行.md) | `all/sjl` | 每天20:00。 |
| 29 | [ROE排行](stock-center/ROE排行.md) | `all/roe` | 每天16:30。 |
| 30 | [盈利能力](stock-center/盈利能力.md) | `all/finyl/{年份_季度}` | 每天20:00。 |
| 31 | [运营能力](stock-center/运营能力.md) | `all/finyynl/{年份_季度}` | 每天20:00。 |
| 32 | [成长能力](stock-center/成长能力.md) | `all/fincznl/{年份_季度}` | 每天20:00。 |
| 33 | [偿债能力](stock-center/偿债能力.md) | `all/finchzhainl/{年份_季度}` | 每天20:00。 |
| 34 | [现金流量](stock-center/现金流量.md) | `all/finxjll/{年份_季度}` | 每天20:00。 |
| 35 | [业绩报表](stock-center/业绩报表.md) | `all/finyjbb/{年份_季度}` | 每天20:00。 |
| 36 | [业绩预告](stock-center/业绩预告.md) | `all/finyjyg/{年份_季度}` | 每天20:00。 |
| 37 | [业绩快报](stock-center/业绩快报.md) | `all/finyjkb/{年份_季度}` | 每天20:00。 |
| 38 | [利润细分](stock-center/利润细分.md) | `all/finlrxf` | 每天20:00。 |
| 39 | [机构持股汇总](stock-center/机构持股汇总.md) | `all/orgcghz/{年份_季度}` | 每周六上午9点。 |
| 40 | [基金重仓](stock-center/基金重仓.md) | `all/orgjjzc/{年份_季度}` | 每周六上午9点。 |
| 41 | [社保重仓](stock-center/社保重仓.md) | `all/orgsbzc/{年份_季度}` | 每周六上午9点。 |
| 42 | [QFII重仓股](stock-center/QFII重仓股.md) | `all/orgqfiizc/{年份_季度}` | 每周六上午9点。 |
| 43 | [证监会行业](stock-center/证监会行业.md) | `all/zjlx/zjhhy` | 每天15:30。 |
| 44 | [概念板块](stock-center/概念板块.md) | `all/zjlx/gnbk` | 每天15:30。 |
| 45 | [净流入额排名](stock-center/净流入额排名.md) | `all/zjlx/jlrepm` | 每天15:30。 |
| 46 | [净流入率排名](stock-center/净流入率排名.md) | `all/zjlx/jlrlpm` | 每天15:30。 |
| 47 | [主力净流入额排名](stock-center/主力净流入额排名.md) | `all/zjlx/zljlrepm` | 每天15:30。 |
| 48 | [主力净流入率排名](stock-center/主力净流入率排名.md) | `all/zjlx/zljlrlpm` | 每天15:30。 |
| 49 | [散户净流入额排名](stock-center/散户净流入额排名.md) | `all/zjlx/shjlrepm` | 每天15:30。 |
| 50 | [散户净流入率排名](stock-center/散户净流入率排名.md) | `all/zjlx/shjlrlpm` | 每天15:30。 |
| 51 | [证监会行业资金路线图](stock-center/证监会行业资金路线图.md) | `all/zjlx/zjhhyzjlx` | 每天15:30。 |
| 52 | [概念板块资金路线图](stock-center/概念板块资金路线图.md) | `all/zjlx/gnbklx` | 每天15:30。 |
| 53 | [个股阶段统计总览](stock-center/个股阶段统计总览.md) | `all/zjlx/ggjdtjzl` | 每天15:30。 |
| 54 | [个股阶段统计](stock-center/个股阶段统计.md) | `all/zjlx/{ggjdtj_阶段}` | 每天15:30。 |
| 55 | [主力连续净流入/流出](stock-center/主力连续净流入_流出.md) | `all/zjlx/zllxjlr` | 每天15:30。 |
| 56 | [最新资金流向概览](stock-center/最新资金流向概览.md) | `all/nxbx/zjgl` | 每天20:00。 |
| 57 | [沪股通历史数据](stock-center/沪股通历史数据.md) | `all/nxbx/hgtlssj` | 每天20:00。 |
| 58 | [深股通历史数据](stock-center/深股通历史数据.md) | `all/nxbx/sgtlssj` | 每天20:00。 |
| 59 | [港股通（沪）历史数据](stock-center/港股通（沪）历史数据.md) | `all/nxbx/ggthlssj` | 每天20:00。 |
| 60 | [港股通（深）历史数据](stock-center/港股通（深）历史数据.md) | `all/nxbx/ggtslssj` | 每天20:00。 |
| 61 | [沪股通成分股行情](stock-center/沪股通成分股行情.md) | `all/nxbx/hgthq` | 每天20:00。 |
| 62 | [深股通成分股行情](stock-center/深股通成分股行情.md) | `all/nxbx/sgthq` | 每天20:00。 |
| 63 | [港股通（沪）成分股行情](stock-center/港股通（沪）成分股行情.md) | `all/nxbx/ggthhq` | 每天20:00。 |
| 64 | [港股通（深）成分股行情](stock-center/港股通（深）成分股行情.md) | `all/nxbx/ggtshq` | 每天20:00。 |
| 65 | [AH股比价](stock-center/AH股比价.md) | `all/nxbx/ahgbj` | 每天20:00。 |
| 66 | [沪股通十大成交股](stock-center/沪股通十大成交股.md) | `all/nxbx/hgtsdcj/{交易日}` | 每天20:00。 |
| 67 | [深股通十大成交股](stock-center/深股通十大成交股.md) | `all/nxbx/sgtsdcj/{交易日}` | 每天20:00。 |
| 68 | [港股通（沪）十大成交股](stock-center/港股通（沪）十大成交股.md) | `all/nxbx/ggthsdcj/{交易日}` | 每天20:00。 |
| 69 | [港股通（深）十大成交股](stock-center/港股通（深）十大成交股.md) | `all/nxbx/ggtssdcj/{交易日}` | 每天20:00。 |

## 基金

> 71个数据集 · 基金估值净值、业绩分红、基金经理、持仓分析、五大评级体系、基金重仓股

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 1 | [所有基金列表](fund/所有基金列表.md) | `base/jjdm` | 每天20:00。 |
| 2 | [估值基金列表](fund/估值基金列表.md) | `base/jjdm_pzgz` | 每天16:00。 |
| 3 | [封闭式基金列表](fund/封闭式基金列表.md) | `base/fbsjj` | 每天16:00。 |
| 4 | [ETF基金列表](fund/ETF基金列表.md) | `base/etfjj` | 每天16:00。 |
| 5 | [LOF基金列表](fund/LOF基金列表.md) | `base/lofjj` | 每天16:00。 |
| 6 | [基金概况](fund/基金概况.md) | `time/jjf10/info/{基金代码}` | 每周六早上6点更新。 |
| 7 | [基金经理变动一览](fund/基金经理变动一览.md) | `time/jjf10/jjjlbd/{基金代码}` | 每周六早上6点更新。 |
| 8 | [在任基金经理列表](fund/在任基金经理列表.md) | `all/jjsjzx/jjjl/zr` | 每周六早上6点更新。 |
| 9 | [在任基金经理简介](fund/在任基金经理简介.md) | `time/jjf10/jjjl/info/{基金经理代码}` | 每周六早上6点更新。 |
| 10 | [管理过的基金一览](fund/管理过的基金一览.md) | `time/jjf10/jjjl/his/{基金经理代码}` | 每周六早上6点更新。 |
| 11 | [现任基金业绩与排名详情](fund/现任基金业绩与排名详情.md) | `time/jjf10/jjjl/curr/{基金经理代码}` | 每周六早上6点更新。 |
| 12 | [收入分析](fund/收入分析.md) | `time/jjf10/cwbb/srfx/{基金代码}` | 每周六早上6点更新。 |
| 13 | [费用分析](fund/费用分析.md) | `time/jjf10/cwbb/fyfx/{基金代码}` | 每周六早上6点更新。 |
| 14 | [主要财务指标](fund/主要财务指标.md) | `time/jjf10/cwbb/zycwzb/{基金代码}` | 每周六早上6点更新。 |
| 15 | [利润表](fund/利润表.md) | `time/jjf10/cwbb/lrb/{基金代码}` | 每周六早上6点更新。 |
| 16 | [资产负债表](fund/资产负债表.md) | `time/jjf10/cwbb/zcfzb/{基金代码}` | 每周六早上6点更新。 |
| 17 | [规模变动](fund/规模变动.md) | `time/jjf10/gmfe/gmbd/{基金代码}` | 每周六早上6点更新。 |
| 18 | [持有人结构](fund/持有人结构.md) | `time/jjf10/gmfe/cyrjg/{基金代码}` | 每周六早上6点更新。 |
| 19 | [股票持仓](fund/股票持仓.md) | `time/jjf10/tzzh/jjcc/{基金代码}` | 每周六早上6点更新。 |
| 20 | [债券持仓](fund/债券持仓.md) | `time/jjf10/tzzh/zqcc/{基金代码}` | 每周六早上6点更新。 |
| 21 | [行业配置](fund/行业配置.md) | `time/jjf10/tzzh/hypz/{基金代码}` | 每周六早上6点更新。 |
| 22 | [资产配置](fund/资产配置.md) | `time/jjf10/tzzh/zcpz/{基金代码}` | 每周六早上6点更新。 |
| 23 | [基金重仓股](fund/基金重仓股.md) | `all/jjsjzx/jjcc/jjzcg/{年份_季度}` | 每天20:30。 |
| 24 | [基金重仓股变动](fund/基金重仓股变动.md) | `all/jjsjzx/jjcc/jjzcgbd/{年份_季度}` | 每天20:30。 |
| 25 | [基金业绩](fund/基金业绩.md) | `time/jjhq/jjyj/{基金代码}` | 每天20:00。 |
| 26 | [基金分红](fund/基金分红.md) | `time/jjhq/jjfh/{基金代码}` | 每天20:00。 |
| 27 | [基金规模](fund/基金规模.md) | `time/jjhq/jjgm/{基金代码}` | 每天20:00。 |
| 28 | [封闭式基金行情](fund/封闭式基金行情.md) | `time/jjhq/fbsjj/{基金代码}` | 交易时间段每10分钟。 |
| 29 | [ETF基金行情](fund/ETF基金行情.md) | `time/jjhq/etfjj/{基金代码}` | 交易时间段每10分钟。 |
| 30 | [LOF基金行情](fund/LOF基金行情.md) | `time/jjhq/lofjj/{基金代码}` | 交易时间段每10分钟。 |
| 31 | [盘中最新估值](fund/盘中最新估值.md) | `time/jjhq/pzgz/{基金代码}` | 交易时间段每10分钟。 |
| 32 | [最新K线](fund/最新K线.md) | `time/real/time/{基金代码}/{分时级别}` | 每日16点更新。 |
| 33 | [历史K线](fund/历史K线.md) | `time/history/trade/{基金代码}/{分时级别}` | 每日16点更新。 |
| 34 | [开放式基金净值](fund/开放式基金净值.md) | `time/jjhq/jjjzkfs/{基金代码}` | 每天20:00。 |
| 35 | [封闭式基金净值](fund/封闭式基金净值.md) | `time/jjhq/jjjzfbs/{基金代码}` | 每天20:00。 |
| 36 | [分级子基金净值](fund/分级子基金净值.md) | `time/jjhq/jjjzfjzjj/{基金代码}` | 每天20:00。 |
| 37 | [历史净值](fund/历史净值.md) | `time/jjf10/jzhb/jjlsjz/{基金代码}` | 每周六早上6点更新。 |
| 38 | [分红送配](fund/分红送配.md) | `time/jjf10/jzhb/jjfhsp/{基金代码}` | 每周六早上6点更新。 |
| 39 | [阶段统计](fund/阶段统计.md) | `time/jjf10/jzhb/jjjdtj/{基金代码}` | 每周六早上6点更新。 |
| 40 | [季度涨幅明细](fund/季度涨幅明细.md) | `time/jjf10/jzhb/jjjdzfmx/{基金代码}` | 每周六早上6点更新。 |
| 41 | [产品特性](fund/产品特性.md) | `all/jjsjzx/fjjj/jcxx/cptx` | 每天20:30。 |
| 42 | [份额类型](fund/份额类型.md) | `all/jjsjzx/fjjj/jcxx/fexl` | 每天20:30。 |
| 43 | [价格透视](fund/价格透视.md) | `all/jjsjzx/fjjj/jgts` | 每天20:30。 |
| 44 | [预期收益](fund/预期收益.md) | `all/jjsjzx/fjjj/yqsy` | 每天20:30。 |
| 45 | [折溢价套利](fund/折溢价套利.md) | `all/jjsjzx/fjjj/zyjtl` | 每天20:30。 |
| 46 | [成交情况](fund/成交情况.md) | `all/jjsjzx/fjjj/ldx/cjqk` | 每天20:30。 |
| 47 | [份额变动](fund/份额变动.md) | `all/jjsjzx/fjjj/ldx/febd/{参数}` | 每天20:30。 |
| 48 | [定期折算](fund/定期折算.md) | `all/jjsjzx/fjjj/zsxx/dqzs` | 每天20:30。 |
| 49 | [不定期折算](fund/不定期折算.md) | `all/jjsjzx/fjjj/zsxx/bdqzs` | 每天20:30。 |
| 50 | [股票型、混合型、债券型、国内其他](fund/股票型、混合型、债券型、国内其他.md) | `all/jjsjzx/cesy/{基金分类参数}` | 每天20:30。 |
| 51 | [开放式基金业绩排行（股、混合、债、QDII类）](fund/开放式基金业绩排行（股、混合、债、QDII类）.md) | `all/jjsjzx/yjph/{基金分类参数}` | 每天20:30。 |
| 52 | [封闭式基金业绩排行](fund/封闭式基金业绩排行.md) | `all/jjsjzx/yjph/{基金分类参数}` | 每天20:30。 |
| 53 | [分级子基金业绩排行](fund/分级子基金业绩排行.md) | `all/jjsjzx/yjph/{基金分类参数}` | 每天20:30。 |
| 54 | [开放式基金净值排名（股、混合、债、QDII类）](fund/开放式基金净值排名（股、混合、债、QDII类）.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30。 |
| 55 | [开放式基金净值排名（货币类）](fund/开放式基金净值排名（货币类）.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30。 |
| 56 | [封闭式基金净值排名](fund/封闭式基金净值排名.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30。 |
| 57 | [分级子基金净值排名](fund/分级子基金净值排名.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30。 |
| 58 | [开放式基金基金分红](fund/开放式基金基金分红.md) | `all/jjsjzx/jjfh/{基金分类参数}` | 每天20:30。 |
| 59 | [封闭式基金基金分红](fund/封闭式基金基金分红.md) | `all/jjsjzx/jjfh/{基金分类参数}` | 每天20:30。 |
| 60 | [分级子基金基金分红](fund/分级子基金基金分红.md) | `all/jjsjzx/jjfh/{基金分类参数}` | 每天20:30。 |
| 61 | [开放式基金基金规模](fund/开放式基金基金规模.md) | `all/jjsjzx/jjgm/{基金分类参数}` | 每天20:30。 |
| 62 | [封闭式基金基金规模](fund/封闭式基金基金规模.md) | `all/jjsjzx/jjgm/{基金分类参数}` | 每天20:30。 |
| 63 | [分级子基金基金规模](fund/分级子基金基金规模.md) | `all/jjsjzx/jjgm/{基金分类参数}` | 每天20:30。 |
| 64 | [晨星评级](fund/晨星评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30。 |
| 65 | [海通证券评级](fund/海通证券评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30。 |
| 66 | [银河证券评级](fund/银河证券评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30。 |
| 67 | [招商证券评级](fund/招商证券评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30。 |
| 68 | [济安金信评级](fund/济安金信评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30。 |
| 69 | [基金公司](fund/基金公司.md) | `all/jjsjzx/jjgs` | 每天20:30。 |
| 70 | [托管银行](fund/托管银行.md) | `all/jjsjzx/tgyh` | 每天20:30。 |
| 71 | [代销机构](fund/代销机构.md) | `all/jjsjzx/dxjg/{参数}` | 每天20:30。 |

## 港股

> 31个数据集 · 港股列表、实时行情(2秒)、F10全档案、财务分析、K线19种级别

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 1 | [港股列表](hk-stock/港股列表.md) | `base/gphk` | 每天0点。 |
| 2 | [证券资料](hk-stock/证券资料.md) | `time/hk/f10/secinfo/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 3 | [公司资料](hk-stock/公司资料.md) | `time/hk/f10/orgprofile/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 4 | [首发资料](hk-stock/首发资料.md) | `time/hk/f10/ipo/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 5 | [窝轮](hk-stock/窝轮.md) | `time/hk/f10/warrant/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 6 | [熊牛证](hk-stock/熊牛证.md) | `time/hk/f10/cbbc/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 7 | [董事会成员](hk-stock/董事会成员.md) | `time/hk/f10/board/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 8 | [管理层成员](hk-stock/管理层成员.md) | `time/hk/f10/manager/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 9 | [业务展望](hk-stock/业务展望.md) | `time/hk/f10/businessexpectation/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 10 | [主要指标](hk-stock/主要指标.md) | `time/hk/f10/finmainindex/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 11 | [资产负债表](hk-stock/资产负债表.md) | `time/hk/f10/balance/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 12 | [利润表](hk-stock/利润表.md) | `time/hk/f10/profit/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 13 | [现金流量表](hk-stock/现金流量表.md) | `time/hk/f10/cashflow/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 14 | [历史股本变化](hk-stock/历史股本变化.md) | `time/hk/f10/equitychange/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 15 | [董事及股东权益](hk-stock/董事及股东权益.md) | `time/hk/f10/holder/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 16 | [历史股权变动（董事增减持）](hk-stock/历史股权变动（董事增减持）.md) | `time/hk/f10/shequitychg/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 17 | [投资评级](hk-stock/投资评级.md) | `time/hk/f10/rating/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 18 | [市场表现对比](hk-stock/市场表现对比.md) | `time/hk/f10/industrymarket/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 19 | [成长性对比](hk-stock/成长性对比.md) | `time/hk/f10/industrygrowth/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 20 | [估值对比](hk-stock/估值对比.md) | `time/hk/f10/industryvaluation/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 21 | [规模对比](hk-stock/规模对比.md) | `time/hk/f10/industryscale/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 22 | [大事提醒](hk-stock/大事提醒.md) | `time/hk/f10/corporateevent/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 23 | [分红派息](hk-stock/分红派息.md) | `time/hk/f10/dividend/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 24 | [股票回购](hk-stock/股票回购.md) | `time/hk/f10/repo/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 25 | [拆股合并](hk-stock/拆股合并.md) | `time/hk/f10/splitmerge/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 26 | [相关公告](hk-stock/相关公告.md) | `time/hk/f10/notice/{股票代码}` | 每天17:30，耗时约10个小时。 |
| 27 | [实时行情数据（2秒落盘）](hk-stock/实时行情数据（2秒落盘）.md) | `time/hk/real/{股票或指数代码}` | 交易时间段每10秒。 |
| 28 | [当天分时成交](hk-stock/当天分时成交.md) | `time/hk/real/trace/timedeal/{股票代码}` | 交易时间段每2分钟。 |
| 29 | [当天逐笔交易](hk-stock/当天逐笔交易.md) | `time/hk/real/trace/onebyone/{股票代码}` | 交易时间段每2分钟。 |
| 30 | [最新K线](hk-stock/最新K线.md) | `time/hk/real/time/{股票或指数代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后16:30更新。 |
| 31 | [历史K线（数据范围：短分时4万根，日线及以上所有）](hk-stock/历史K线（数据范围：短分时4万根，日线及以上所有）.md) | `time/hk/history/trade/{股票或指数代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别每天16:30更新。 |

## 美股

> 25个数据集 · 美股列表、实时行情、F10全档案、财务分析、K线

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 1 | [美股列表](us-stock/美股列表.md) | `base/gpus` | 美东时间每天0点。 |
| 2 | [证券资料](us-stock/证券资料.md) | `time/us/f10/secinfo/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 3 | [公司资料](us-stock/公司资料.md) | `time/us/f10/orgprofile/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 4 | [主营构成](us-stock/主营构成.md) | `time/us/f10/maincompose/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 5 | [高管研究](us-stock/高管研究.md) | `time/us/f10/executive/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 6 | [卖空明细](us-stock/卖空明细.md) | `time/us/f10/short/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 7 | [机构评级](us-stock/机构评级.md) | `time/us/f10/rating/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 8 | [主要指标](us-stock/主要指标.md) | `time/us/f10/finmainindex/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 9 | [资产负债表](us-stock/资产负债表.md) | `time/us/f10/balance/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 10 | [综合损益表](us-stock/综合损益表.md) | `time/us/f10/income/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 11 | [现金流量表](us-stock/现金流量表.md) | `time/us/f10/cashflow/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 12 | [股本变动](us-stock/股本变动.md) | `time/us/f10/equitychange/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 13 | [拆股并股](us-stock/拆股并股.md) | `time/us/f10/stocksplit/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 14 | [董事及股东权益](us-stock/董事及股东权益.md) | `time/us/f10/holder/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 15 | [机构持股](us-stock/机构持股.md) | `time/us/f10/orghold/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 16 | [基金持股](us-stock/基金持股.md) | `time/us/f10/fundhold/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 17 | [高管持股](us-stock/高管持股.md) | `time/us/f10/leaderhold/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 18 | [机构明细](us-stock/机构明细.md) | `time/us/f10/orgdetail/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 19 | [大事提醒](us-stock/大事提醒.md) | `time/us/f10/gsds/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 20 | [分红派息](us-stock/分红派息.md) | `time/us/f10/dividend/{股票代码}` | 每天美东时间18:00，耗时约10个小时。 |
| 21 | [实时行情数据（3秒落盘）](us-stock/实时行情数据（3秒落盘）.md) | `time/us/real/us_{代码}` | 交易时间段（美东时间）每10秒。 |
| 22 | [当天分时成交](us-stock/当天分时成交.md) | `time/us/real/trace/timedeal/us_{代码}` | 交易时间段每2分钟。 |
| 23 | [当天逐笔交易](us-stock/当天逐笔交易.md) | `time/us/real/trace/onebyone/us_{代码}` | 交易时间段每2分钟。 |
| 24 | [最新K线](us-stock/最新K线.md) | `time/us/real/time/us_{代码}/{级别}` | 分钟级别盘中（美东时间）每5分钟更新，日线及以上级别盘后16:30（美东时间）更新。 |
| 25 | [历史K线（数据范围：短分时4万根，日线及以上所有）](us-stock/历史K线（数据范围：短分时4万根，日线及以上所有）.md) | `time/us/history/trade/us_{代码}/{级别}` | 分钟级别盘中（美东时间）每5分钟更新，日线及以上级别每天16:30（美东时间）更新。 |


---

## 相关文档

- [安装指引](../install.md)
- [示例代码](../examples.md)
- [关于 IG50](../about.md)
- [官网接口文档（最新）](https://ig50.com/dataset-overview.html) ← **最新接口以此为准**
- [官网数据检索](https://ig50.com/search.html)
