# 接口文档

> IG50 共提供 **217 个数据集**，覆盖沪深京A股、沪深数据中心、基金行情档案、基金数据中心、港股五大板块。所有数据以 JSON 文本文件落盘到本地，直接读取即可使用。

> ⚠ **最新接口更新以 [官网接口文档](https://ig50.com/index.html) 为准**。本仓库为镜像文档，可能滞后于官网，如需查阅最新接口、字段、路径，请访问 [官网接口文档](https://ig50.com/index.html) 或 [官网数据检索](https://ig50.com/search.html)。

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

> 73个数据集 · 实时行情、L2深度、K线、F10全档案、资金流向

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 1 | [沪深京A股列表](stock-a/沪深京A股列表.md) | `base/gplist` | 每天16点 |
| 2 | [新股日历](stock-a/新股日历.md) | `all/xgrl` | 每天16点 |
| 3 | [风险警示股票列表](stock-a/风险警示股票列表.md) | `all/stgplist` | 每天16点 |
| 4 | [公司简介](stock-a/公司简介.md) | `time/f10/info/{股票代码}` | 每天15:30（更新完成约12小时） |
| 5 | [所属指数](stock-a/所属指数.md) | `time/f10/index/{股票代码}` | 每天15:30（更新完成约12小时） |
| 6 | [历届高管成员](stock-a/历届高管成员.md) | `time/f10/gg/{股票代码}` | 每天15:30（更新完成约12小时） |
| 7 | [历届董事会成员](stock-a/历届董事会成员.md) | `time/f10/ds/{股票代码}` | 每天15:30（更新完成约12小时） |
| 8 | [历届监事会成员](stock-a/历届监事会成员.md) | `time/f10/js/{股票代码}` | 每天15:30（更新完成约12小时） |
| 9 | [近年分红](stock-a/近年分红.md) | `time/f10/share/{股票代码}` | 每天15:30（更新完成约12小时） |
| 10 | [近年增发](stock-a/近年增发.md) | `time/f10/zf/{股票代码}` | 每天15:30（更新完成约12小时） |
| 11 | [解禁限售](stock-a/解禁限售.md) | `time/f10/jjxs/{股票代码}` | 每天15:30（更新完成约12小时） |
| 12 | [近一年各季度利润](stock-a/近一年各季度利润.md) | `time/f10/pf/{股票代码}` | 每天15:30（更新完成约12小时） |
| 13 | [近一年各季度现金流](stock-a/近一年各季度现金流.md) | `time/f10/cf/{股票代码}` | 每天15:30（更新完成约12小时） |
| 14 | [近年业绩预告](stock-a/近年业绩预告.md) | `time/f10/ep/{股票代码}` | 每天15:30（更新完成约12小时） |
| 15 | [财务指标](stock-a/财务指标.md) | `time/f10/fi/{股票代码}` | 每天15:30（更新完成约12小时） |
| 16 | [十大股东](stock-a/十大股东.md) | `time/f10/zygd/{股票代码}` | 每天15:30（更新完成约12小时） |
| 17 | [十大流通股东](stock-a/十大流通股东.md) | `time/f10/zygdlt/{股票代码}` | 每天15:30（更新完成约12小时） |
| 18 | [股东变化趋势](stock-a/股东变化趋势.md) | `time/f10/gdbh/{股票代码}` | 每天15:30（更新完成约12小时） |
| 19 | [基金持股](stock-a/基金持股.md) | `time/f10/jjcg/{股票代码}` | 每周六9点更新（耗时约9小时） |
| 20 | [所属板块](stock-a/所属板块.md) | `time/f10/ssbk/{股票代码}` | 每天20:30更新 |
| 21 | [经营范围](stock-a/经营范围.md) | `time/f10/jyfw/{股票代码}` | 每天20:30更新 |
| 22 | [主营业务](stock-a/主营业务.md) | `time/f10/zyyw/{股票代码}` | 每天20:30更新 |
| 23 | [行业背景](stock-a/行业背景.md) | `time/f10/hybj/{股票代码}` | 每天20:30更新 |
| 24 | [核心竞争力](stock-a/核心竞争力.md) | `time/f10/hxjzl/{股票代码}` | 每天20:30更新 |
| 25 | [指数、行业、概念树](stock-a/指数、行业、概念树.md) | `base/it` | 每周六凌晨3点 |
| 26 | [根据指数、行业、概念找相关股票](stock-a/根据指数、行业、概念找相关股票.md) | `time/indextree/{指数、行业、概念代码}` | 每周六凌晨3点 |
| 27 | [根据股票找相关指数、行业、概念](stock-a/根据股票找相关指数、行业、概念.md) | `time/iii/{股票代码}` | 每周六凌晨3点 |
| 28 | [资金走势对照](stock-a/资金走势对照.md) | `time/zijin/zlzjzs/{股票代码}` | 每天20:00 |
| 29 | [资金流入趋势](stock-a/资金流入趋势.md) | `time/zijin/zjlrqs/{股票代码}` | 每天20:00 |
| 30 | [最近10天资金流入趋势](stock-a/最近10天资金流入趋势.md) | `time/zijin/zjlrqs/last10/{股票代码}` | 每天20:00 |
| 31 | [阶段主力动向](stock-a/阶段主力动向.md) | `time/zijin/jdzldx/{股票代码}` | 每天20:00 |
| 32 | [最近10天阶段主力动向](stock-a/最近10天阶段主力动向.md) | `time/zijin/jdzldx/last10/{股票代码}` | 每天20:00 |
| 33 | [历史成交分布](stock-a/历史成交分布.md) | `time/zijin/lscjfb/{股票代码}` | 每天20:00 |
| 34 | [最近10天成交分布](stock-a/最近10天成交分布.md) | `time/zijin/lscjfb/last10/{股票代码}` | 每天20:00 |
| 35 | [涨停股池](stock-a/涨停股池.md) | `time/zdtgc/ztgc/{日期}` | 交易时间段每10分钟 |
| 36 | [跌停股池](stock-a/跌停股池.md) | `time/zdtgc/dtgc/{日期}` | 交易时间段每10分钟 |
| 37 | [强势股池](stock-a/强势股池.md) | `time/zdtgc/qsgc/{日期}` | 交易时间段每10分钟 |
| 38 | [次新股池](stock-a/次新股池.md) | `time/zdtgc/cxgc/{日期}` | 交易时间段每10分钟 |
| 39 | [炸板股池](stock-a/炸板股池.md) | `time/zdtgc/zbgc/{日期}` | 交易时间段每10分钟 |
| 40 | [融资融券标的股](stock-a/融资融券标的股.md) | `base/rzrqGpList` | 每天上午8:50 |
| 41 | [融资融券历史走势](stock-a/融资融券历史走势.md) | `time/rzrq/{股票代码}` | 每天上午8:50 |
| 42 | [派现与募资对比](stock-a/派现与募资对比.md) | `time/pxymz/{股票代码}` | 每天20:30 |
| 43 | [质押明细](stock-a/质押明细.md) | `time/zhiya/{股票代码}` | 每天20:30 |
| 44 | [回购数据全览](stock-a/回购数据全览.md) | `time/hgzl/{股票代码}` | 每天20:30 |
| 45 | [并购重组一览](stock-a/并购重组一览.md) | `time/bgcz/{股票代码}` | 每天20:30 |
| 46 | [重大事项](stock-a/重大事项.md) | `time/gonggao/zdsx/{股票代码}` | 每天下午8:00 |
| 47 | [财务报告](stock-a/财务报告.md) | `time/gonggao/cwbg/{股票代码}` | 每天下午8:00 |
| 48 | [融资公告](stock-a/融资公告.md) | `time/gonggao/rzgg/{股票代码}` | 每天下午8:00 |
| 49 | [风险提示](stock-a/风险提示.md) | `time/gonggao/fxts/{股票代码}` | 每天下午8:00 |
| 50 | [资产重组](stock-a/资产重组.md) | `time/gonggao/zccz/{股票代码}` | 每天下午8:00 |
| 51 | [信息变更](stock-a/信息变更.md) | `time/gonggao/xxbg/{股票代码}` | 每天下午8:00 |
| 52 | [持股变动](stock-a/持股变动.md) | `time/gonggao/cgbd/{股票代码}` | 每天下午8:00 |
| 53 | [所有公告](stock-a/所有公告.md) | `time/history/gonggao/{股票代码}` | 每天下午8:00 |
| 54 | [实时行情数据（3秒落盘）](stock-a/实时行情数据（3秒落盘）.md) | `time/real/{股票代码}` | 交易时间段每10秒 |
| 55 | [买卖五档盘口（3秒落盘）](stock-a/买卖五档盘口（3秒落盘）.md) | `time/real/trace/level5/{股票代码}` | 交易时间段每10秒 |
| 56 | [L2行情指标（3秒落盘）](stock-a/L2行情指标（3秒落盘）.md) | `time/real/trace/l2sign/{股票代码}` | 交易时间段每10秒 |
| 57 | [当天逐笔交易](stock-a/当天逐笔交易.md) | `time/real/trace/onebyone/{股票代码}` | 交易时间段每2分钟 |
| 58 | [集合竞价](stock-a/集合竞价.md) | `time/real/trace/jhjj/{股票代码}` | 集合竞价时间段（时间段：9:15~9:30，14:47~15:30）每1分钟 |
| 59 | [盘中异动](stock-a/盘中异动.md) | `all/pzyd` | 交易时间段每1分钟 |
| 60 | [当天分时成交](stock-a/当天分时成交.md) | `time/real/trace/timedeal/{股票代码}` | 交易时间段每2分钟 |
| 61 | [当天分价成交占比](stock-a/当天分价成交占比.md) | `time/real/trace/realpercent/{股票代码}` | 每天20:00 |
| 62 | [当天大单交易](stock-a/当天大单交易.md) | `time/real/trace/bigdeal/{股票代码}` | 每天20:00 |
| 63 | [最新K线](stock-a/最新K线.md) | `time/real/time/{股票代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新 |
| 64 | [历史K线（数据范围：短分时两年，日线及以上所有）](stock-a/历史K线（数据范围：短分时两年，日线及以上所有）.md) | `time/history/trade/{股票代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新 |
| 65 | [沪深主要指数](stock-a/沪深主要指数.md) | `base/shsz` | 每天15:35点 |
| 66 | [上证系列指数](stock-a/上证系列指数.md) | `base/sh` | 每天15:35点 |
| 67 | [深证系列指数](stock-a/深证系列指数.md) | `base/sz` | 每天15:35点 |
| 68 | [中证系列指数](stock-a/中证系列指数.md) | `base/zzzs` | 每天15:35点 |
| 69 | [指数成分](stock-a/指数成分.md) | `base/zscf` | 每天15:35点 |
| 70 | [指数实时数据](stock-a/指数实时数据.md) | `time/real/{指数代码（包含sh/sz前缀，如：sh000001）}` | 交易时间段每1分钟 |
| 71 | [沪深两市上涨下跌数概览](stock-a/沪深两市上涨下跌数概览.md) | `time/real/shszzdbl` | 交易时间段每1分钟 |
| 72 | [最新K线](stock-a/最新K线.md) | `time/real/time/{指数代码（包含sh/sz前缀，如：sh000001）}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新 |
| 73 | [历史K线（数据范围：短分时两年，日线及以上所有）](stock-a/历史K线（数据范围：短分时两年，日线及以上所有）.md) | `time/history/trade/{指数代码（包含sh/sz前缀，如：sh000001）}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后15:35更新 |

## 沪深数据中心

> 70个数据集 · 龙虎榜、南北向资金、市场异动、财务分析、机构持股

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 74 | [今日交易提示](stock-center/今日交易提示.md) | `all/tt` | 每天15:30 |
| 75 | [融资融券交易总量](stock-center/融资融券交易总量.md) | `all/rzrqtt` | 每天15:30 |
| 76 | [融资融券交易明细](stock-center/融资融券交易明细.md) | `all/rzrqdt` | 每天15:30 |
| 77 | [大宗交易](stock-center/大宗交易.md) | `all/bt` | 每天15:30 |
| 78 | [解禁限售](stock-center/解禁限售.md) | `all/rb` | 每天15:30 |
| 79 | [打新收益](stock-center/打新收益.md) | `all/ne` | 每天15:30 |
| 80 | [历史累计分红](stock-center/历史累计分红.md) | `all/fh` | 每天15:30 |
| 81 | [每日详情](stock-center/每日详情.md) | `all/ld` | 每天20:00 |
| 82 | [个股上榜统计](stock-center/个股上榜统计.md) | `all/gg/{近n日}` | 每天15:30 |
| 83 | [营业部上榜统计](stock-center/营业部上榜统计.md) | `all/yyb/{近n日}` | 每天15:30 |
| 84 | [机构席位追踪](stock-center/机构席位追踪.md) | `all/jgzz/{近n日}` | 每天15:30 |
| 85 | [机构席位成交明细](stock-center/机构席位成交明细.md) | `all/jgcj` | 每天15:30 |
| 86 | [阶段最高最低](stock-center/阶段最高最低.md) | `all/jdgd` | 每天20:00 |
| 87 | [盘中创新高个股](stock-center/盘中创新高个股.md) | `all/cxg` | 每天20:00 |
| 88 | [盘中创新低个股](stock-center/盘中创新低个股.md) | `all/cxd` | 每天20:00 |
| 89 | [成交骤增个股](stock-center/成交骤增个股.md) | `all/cjzz` | 每天20:00 |
| 90 | [成交骤减个股](stock-center/成交骤减个股.md) | `all/cjzj` | 每天20:00 |
| 91 | [连续放量个股](stock-center/连续放量个股.md) | `all/lxfl` | 每天20:00 |
| 92 | [连续缩量个股](stock-center/连续缩量个股.md) | `all/lxsl` | 每天20:00 |
| 93 | [连续上涨个股](stock-center/连续上涨个股.md) | `all/lxsz` | 每天20:00 |
| 94 | [连续下跌个股](stock-center/连续下跌个股.md) | `all/lxxd` | 每天20:00 |
| 95 | [周涨跌排名](stock-center/周涨跌排名.md) | `all/zzdpm` | 每天20:00 |
| 96 | [月涨跌排名](stock-center/月涨跌排名.md) | `all/yzdpm` | 每天20:00 |
| 97 | [本周强势股](stock-center/本周强势股.md) | `all/bzqsg` | 每天20:00 |
| 98 | [本月强势股](stock-center/本月强势股.md) | `all/byqsg` | 每天20:00 |
| 99 | [流通市值排行](stock-center/流通市值排行.md) | `all/ltsz` | 每天20:00 |
| 100 | [市盈率排行](stock-center/市盈率排行.md) | `all/syl` | 每天20:00 |
| 101 | [市净率排行](stock-center/市净率排行.md) | `all/sjl` | 每天20:00 |
| 102 | [ROE排行](stock-center/ROE排行.md) | `all/roe` | 每天16:30 |
| 103 | [盈利能力](stock-center/盈利能力.md) | `all/finyl/{年份_季度}` | 每天20:00 |
| 104 | [运营能力](stock-center/运营能力.md) | `all/finyynl/{年份_季度}` | 每天20:00 |
| 105 | [成长能力](stock-center/成长能力.md) | `all/fincznl/{年份_季度}` | 每天20:00 |
| 106 | [偿债能力](stock-center/偿债能力.md) | `all/finchzhainl/{年份_季度}` | 每天20:00 |
| 107 | [现金流量](stock-center/现金流量.md) | `all/finxjll/{年份_季度}` | 每天20:00 |
| 108 | [业绩报表](stock-center/业绩报表.md) | `all/finyjbb/{年份_季度}` | 每天20:00 |
| 109 | [业绩预告](stock-center/业绩预告.md) | `all/finyjyg/{年份_季度}` | 每天20:00 |
| 110 | [业绩快报](stock-center/业绩快报.md) | `all/finyjkb/{年份_季度}` | 每天20:00 |
| 111 | [利润细分](stock-center/利润细分.md) | `all/finlrxf` | 每天20:00 |
| 112 | [机构持股汇总](stock-center/机构持股汇总.md) | `all/orgcghz/{年份_季度}` | 每周六上午9点 |
| 113 | [基金重仓](stock-center/基金重仓.md) | `all/orgjjzc/{年份_季度}` | 每周六上午9点 |
| 114 | [社保重仓](stock-center/社保重仓.md) | `all/orgsbzc/{年份_季度}` | 每周六上午9点 |
| 115 | [QFII重仓股](stock-center/QFII重仓股.md) | `all/orgqfiizc/{年份_季度}` | 每周六上午9点 |
| 116 | [证监会行业](stock-center/证监会行业.md) | `all/zjlx/zjhhy` | 每天15:30 |
| 117 | [概念板块](stock-center/概念板块.md) | `all/zjlx/gnbk` | 每天15:30 |
| 118 | [净流入额排名](stock-center/净流入额排名.md) | `all/zjlx/jlrepm` | 每天15:30 |
| 119 | [净流入率排名](stock-center/净流入率排名.md) | `all/zjlx/jlrlpm` | 每天15:30 |
| 120 | [主力净流入额排名](stock-center/主力净流入额排名.md) | `all/zjlx/zljlrepm` | 每天15:30 |
| 121 | [主力净流入率排名](stock-center/主力净流入率排名.md) | `all/zjlx/zljlrlpm` | 每天15:30 |
| 122 | [散户净流入额排名](stock-center/散户净流入额排名.md) | `all/zjlx/shjlrepm` | 每天15:30 |
| 123 | [散户净流入率排名](stock-center/散户净流入率排名.md) | `all/zjlx/shjlrlpm` | 每天15:30 |
| 124 | [证监会行业资金路线图](stock-center/证监会行业资金路线图.md) | `all/zjlx/zjhhyzjlx` | 每天15:30 |
| 125 | [概念板块资金路线图](stock-center/概念板块资金路线图.md) | `all/zjlx/gnbklx` | 每天15:30 |
| 126 | [个股阶段统计总览](stock-center/个股阶段统计总览.md) | `all/zjlx/ggjdtjzl` | 每天15:30 |
| 127 | [个股阶段统计](stock-center/个股阶段统计.md) | `all/zjlx/{ggjdtj_阶段}` | 每天15:30 |
| 128 | [主力连续净流入/流出](stock-center/主力连续净流入_流出.md) | `all/zjlx/zllxjlr` | 每天15:30 |
| 129 | [最新资金流向概览](stock-center/最新资金流向概览.md) | `all/nxbx/zjgl` | 每天20:00 |
| 130 | [沪股通历史数据](stock-center/沪股通历史数据.md) | `all/nxbx/hgtlssj` | 每天20:00 |
| 131 | [深股通历史数据](stock-center/深股通历史数据.md) | `all/nxbx/sgtlssj` | 每天20:00 |
| 132 | [港股通（沪）历史数据](stock-center/港股通（沪）历史数据.md) | `all/nxbx/ggthlssj` | 每天20:00 |
| 133 | [港股通（深）历史数据](stock-center/港股通（深）历史数据.md) | `all/nxbx/ggtslssj` | 每天20:00 |
| 134 | [沪股通成分股行情](stock-center/沪股通成分股行情.md) | `all/nxbx/hgthq` | 每天20:00 |
| 135 | [深股通成分股行情](stock-center/深股通成分股行情.md) | `all/nxbx/sgthq` | 每天20:00 |
| 136 | [港股通（沪）成分股行情](stock-center/港股通（沪）成分股行情.md) | `all/nxbx/ggthhq` | 每天20:00 |
| 137 | [港股通（深）成分股行情](stock-center/港股通（深）成分股行情.md) | `all/nxbx/ggtshq` | 每天20:00 |
| 138 | [AH股比价](stock-center/AH股比价.md) | `all/nxbx/ahgbj` | 每天20:00 |
| 139 | [沪股通十大成交股](stock-center/沪股通十大成交股.md) | `all/nxbx/hgtsdcj/{交易日}` | 每天20:00 |
| 140 | [深股通十大成交股](stock-center/深股通十大成交股.md) | `all/nxbx/sgtsdcj/{交易日}` | 每天20:00 |
| 141 | [港股通（沪）十大成交股](stock-center/港股通（沪）十大成交股.md) | `all/nxbx/ggthsdcj/{交易日}` | 每天20:00 |
| 142 | [港股通（深）十大成交股](stock-center/港股通（深）十大成交股.md) | `all/nxbx/ggtssdcj/{交易日}` | 每天20:00 |

## 基金行情档案

> 38个数据集 · 基金估值净值、业绩分红、基金经理、持仓分析、财务报表

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 143 | [所有基金列表](fund-quote/所有基金列表.md) | `base/jjdm` | 每天20:00 |
| 144 | [估值基金列表](fund-quote/估值基金列表.md) | `base/jjdm_pzgz` | 每天16:00 |
| 145 | [盘中最新估值](fund-quote/盘中最新估值.md) | `time/jjhq/pzgz/{基金代码}` | 交易时间段每10分钟 |
| 146 | [开放式基金净值](fund-quote/开放式基金净值.md) | `time/jjhq/jjjzkfs/{基金代码}` | 每天20:00 |
| 147 | [封闭式基金净值](fund-quote/封闭式基金净值.md) | `time/jjhq/jjjzfbs/{基金代码}` | 每天20:00 |
| 148 | [分级子基金净值](fund-quote/分级子基金净值.md) | `time/jjhq/jjjzfjzjj/{基金代码}` | 每天20:00 |
| 149 | [基金业绩](fund-quote/基金业绩.md) | `time/jjhq/jjyj/{基金代码}` | 每天20:00 |
| 150 | [基金分红](fund-quote/基金分红.md) | `time/jjhq/jjfh/{基金代码}` | 每天20:00 |
| 151 | [基金规模](fund-quote/基金规模.md) | `time/jjhq/jjgm/{基金代码}` | 每天20:00 |
| 152 | [封闭式基金列表](fund-quote/封闭式基金列表.md) | `base/fbsjj` | 每天16:00 |
| 153 | [封闭式基金行情](fund-quote/封闭式基金行情.md) | `time/jjhq/fbsjj/{基金代码}` | 交易时间段每10分钟 |
| 154 | [ETF基金列表](fund-quote/ETF基金列表.md) | `base/etfjj` | 每天16:00 |
| 155 | [ETF基金行情](fund-quote/ETF基金行情.md) | `time/jjhq/etfjj/{基金代码}` | 交易时间段每10分钟 |
| 156 | [LOF基金列表](fund-quote/LOF基金列表.md) | `base/lofjj` | 每天16:00 |
| 157 | [LOF基金行情](fund-quote/LOF基金行情.md) | `time/jjhq/lofjj/{基金代码}` | 交易时间段每10分钟 |
| 158 | [最新K线](fund-quote/最新K线.md) | `time/real/time/{基金代码}/{分时级别}` | 每日16点更新 |
| 159 | [历史K线](fund-quote/历史K线.md) | `time/history/trade/{基金代码}/{分时级别}` | 每日16点更新 |
| 160 | [基金概况](fund-quote/基金概况.md) | `time/jjf10/info/{基金代码}` | 每周六早上6点更新 |
| 161 | [基金经理变动一览](fund-quote/基金经理变动一览.md) | `time/jjf10/jjjlbd/{基金代码}` | 每周六早上6点更新 |
| 162 | [在任基金经理列表](fund-quote/在任基金经理列表.md) | `all/jjsjzx/jjjl/zr` | 每周六早上6点更新 |
| 163 | [在任基金经理简介](fund-quote/在任基金经理简介.md) | `time/jjf10/jjjl/info/{基金经理代码}` | 每周六早上6点更新 |
| 164 | [管理过的基金一览](fund-quote/管理过的基金一览.md) | `time/jjf10/jjjl/his/{基金经理代码}` | 每周六早上6点更新 |
| 165 | [现任基金业绩与排名详情](fund-quote/现任基金业绩与排名详情.md) | `time/jjf10/jjjl/curr/{基金经理代码}` | 每周六早上6点更新 |
| 166 | [历史净值](fund-quote/历史净值.md) | `time/jjf10/jzhb/jjlsjz/{基金代码}` | 每周六早上6点更新 |
| 167 | [分红送配](fund-quote/分红送配.md) | `time/jjf10/jzhb/jjfhsp/{基金代码}` | 每周六早上6点更新 |
| 168 | [阶段统计](fund-quote/阶段统计.md) | `time/jjf10/jzhb/jjjdtj/{基金代码}` | 每周六早上6点更新 |
| 169 | [季度涨幅明细](fund-quote/季度涨幅明细.md) | `time/jjf10/jzhb/jjjdzfmx/{基金代码}` | 每周六早上6点更新 |
| 170 | [股票持仓](fund-quote/股票持仓.md) | `time/jjf10/tzzh/jjcc/{基金代码}` | 每周六早上6点更新 |
| 171 | [债券持仓](fund-quote/债券持仓.md) | `time/jjf10/tzzh/zqcc/{基金代码}` | 每周六早上6点更新 |
| 172 | [行业配置](fund-quote/行业配置.md) | `time/jjf10/tzzh/hypz/{基金代码}` | 每周六早上6点更新 |
| 173 | [资产配置](fund-quote/资产配置.md) | `time/jjf10/tzzh/zcpz/{基金代码}` | 每周六早上6点更新 |
| 174 | [规模变动](fund-quote/规模变动.md) | `time/jjf10/gmfe/gmbd/{基金代码}` | 每周六早上6点更新 |
| 175 | [持有人结构](fund-quote/持有人结构.md) | `time/jjf10/gmfe/cyrjg/{基金代码}` | 每周六早上6点更新 |
| 176 | [收入分析](fund-quote/收入分析.md) | `time/jjf10/cwbb/srfx/{基金代码}` | 每周六早上6点更新 |
| 177 | [费用分析](fund-quote/费用分析.md) | `time/jjf10/cwbb/fyfx/{基金代码}` | 每周六早上6点更新 |
| 178 | [主要财务指标](fund-quote/主要财务指标.md) | `time/jjf10/cwbb/zycwzb/{基金代码}` | 每周六早上6点更新 |
| 179 | [利润表](fund-quote/利润表.md) | `time/jjf10/cwbb/lrb/{基金代码}` | 每周六早上6点更新 |
| 180 | [资产负债表](fund-quote/资产负债表.md) | `time/jjf10/cwbb/zcfzb/{基金代码}` | 每周六早上6点更新 |

## 基金数据中心

> 32个数据集 · 五大评级体系、净值业绩排行、分级基金、基金重仓股

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 181 | [开放式基金净值排名（股、混合、债、QDII类）](fund-center/开放式基金净值排名（股、混合、债、QDII类）.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30 |
| 182 | [开放式基金净值排名（货币类）](fund-center/开放式基金净值排名（货币类）.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30 |
| 183 | [封闭式基金净值排名](fund-center/封闭式基金净值排名.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30 |
| 184 | [分级子基金净值排名](fund-center/分级子基金净值排名.md) | `all/jjsjzx/jjjz/{基金分类参数}` | 每天20:30 |
| 185 | [开放式基金业绩排行（股、混合、债、QDII类）](fund-center/开放式基金业绩排行（股、混合、债、QDII类）.md) | `all/jjsjzx/yjph/{基金分类参数}` | 每天20:30 |
| 186 | [封闭式基金业绩排行](fund-center/封闭式基金业绩排行.md) | `all/jjsjzx/yjph/{基金分类参数}` | 每天20:30 |
| 187 | [分级子基金业绩排行](fund-center/分级子基金业绩排行.md) | `all/jjsjzx/yjph/{基金分类参数}` | 每天20:30 |
| 188 | [开放式基金基金分红](fund-center/开放式基金基金分红.md) | `all/jjsjzx/jjfh/{基金分类参数}` | 每天20:30 |
| 189 | [封闭式基金基金分红](fund-center/封闭式基金基金分红.md) | `all/jjsjzx/jjfh/{基金分类参数}` | 每天20:30 |
| 190 | [分级子基金基金分红](fund-center/分级子基金基金分红.md) | `all/jjsjzx/jjfh/{基金分类参数}` | 每天20:30 |
| 191 | [开放式基金基金规模](fund-center/开放式基金基金规模.md) | `all/jjsjzx/jjgm/{基金分类参数}` | 每天20:30 |
| 192 | [封闭式基金基金规模](fund-center/封闭式基金基金规模.md) | `all/jjsjzx/jjgm/{基金分类参数}` | 每天20:30 |
| 193 | [分级子基金基金规模](fund-center/分级子基金基金规模.md) | `all/jjsjzx/jjgm/{基金分类参数}` | 每天20:30 |
| 194 | [晨星评级](fund-center/晨星评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30 |
| 195 | [海通证券评级](fund-center/海通证券评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30 |
| 196 | [银河证券评级](fund-center/银河证券评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30 |
| 197 | [招商证券评级](fund-center/招商证券评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30 |
| 198 | [济安金信评级](fund-center/济安金信评级.md) | `all/jjsjzx/jjpj/{基金分类参数}` | 每天20:30 |
| 199 | [基金重仓股](fund-center/基金重仓股.md) | `all/jjsjzx/jjcc/jjzcg/{年份_季度}` | 每天20:30 |
| 200 | [基金重仓股变动](fund-center/基金重仓股变动.md) | `all/jjsjzx/jjcc/jjzcgbd/{年份_季度}` | 每天20:30 |
| 201 | [价格透视](fund-center/价格透视.md) | `all/jjsjzx/fjjj/jgts` | 每天20:30 |
| 202 | [预期收益](fund-center/预期收益.md) | `all/jjsjzx/fjjj/yqsy` | 每天20:30 |
| 203 | [折溢价套利](fund-center/折溢价套利.md) | `all/jjsjzx/fjjj/zyjtl` | 每天20:30 |
| 204 | [成交情况](fund-center/成交情况.md) | `all/jjsjzx/fjjj/ldx/cjqk` | 每天20:30 |
| 205 | [份额变动](fund-center/份额变动.md) | `all/jjsjzx/fjjj/ldx/febd/{参数}` | 每天20:30 |
| 206 | [定期折算](fund-center/定期折算.md) | `all/jjsjzx/fjjj/zsxx/dqzs` | 每天20:30 |
| 207 | [不定期折算](fund-center/不定期折算.md) | `all/jjsjzx/fjjj/zsxx/bdqzs` | 每天20:30 |
| 208 | [产品特性](fund-center/产品特性.md) | `all/jjsjzx/fjjj/jcxx/cptx` | 每天20:30 |
| 209 | [份额类型](fund-center/份额类型.md) | `all/jjsjzx/fjjj/jcxx/fexl` | 每天20:30 |
| 210 | [股票型、混合型、债券型、国内其他](fund-center/股票型、混合型、债券型、国内其他.md) | `all/jjsjzx/cesy/{基金分类参数}` | 每天20:30 |
| 211 | [代销机构](fund-center/代销机构.md) | `all/jjsjzx/dxjg/{参数}` | 每天20:30 |
| 212 | [基金公司](fund-center/基金公司.md) | `all/jjsjzx/jjgs` | 每天20:30 |
| 213 | [托管银行](fund-center/托管银行.md) | `all/jjsjzx/tgyh` | 每天20:30 |

## 港股

> 4个数据集 · 港股列表、实时行情2秒落盘、K线19种级别、短分时十年

| # | 接口名称 | 本地路径 | 更新频率 |
|---|---------|---------|---------|
| 214 | [港股列表](hk-stock/港股列表.md) | `base/gphk` | 每天0点 |
| 215 | [行情数据（2秒落盘）](hk-stock/行情数据（2秒落盘）.md) | `time/hk/real/{股票或指数代码}` | 交易时间段每10秒 |
| 216 | [最新K线](hk-stock/最新K线.md) | `time/hk/real/time/{股票或指数代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别盘后16:30更新 |
| 217 | [历史K线（数据范围：短分时十年，日线及以上所有）](hk-stock/历史K线（数据范围：短分时十年，日线及以上所有）.md) | `time/hk/history/trade/{股票或指数代码}/{分时级别}` | 分钟级别盘中每5分钟更新，日线及以上级别每天16:30更新 |


---

## 相关文档

- [安装指引](../install.md)
- [示例代码](../examples.md)
- [关于 IG50](../about.md)
- [官网接口文档（最新）](https://ig50.com/index.html) ← **最新接口以此为准**
- [官网数据检索](https://ig50.com/search.html)
