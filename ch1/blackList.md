 黑名单服务

  


 ===================

  


  


  


  


  


\#\# 1.变更记录

  


  


  


 版本

\| 作者

\|

备注

\|日期

  


 ------\|------\| ---------------\| ---------

  


 v1.0

\|

AOREO\| 初版

\| 2017-10-10

  


  


  


\#\#2.文档说明

  


 黑名单服务，提供黑名单接口服务，接口鉴权由驭信平台进行。

  


  


\#\#3.接口地址

  


\#\#\#3.1测试地址

  




  


\#\#4.黑名单接口调用

  


\#\#\#4.1.接口

  


 \| 接口

\| 请求方式

\| 请求参数类型\|

返回结果类型

  


 \| - \| :-: \| -: \|

  


 \| api/blackList/queryBlackList\| post\| - \|josn

  


\#\#\#4.2.接口参数

  


\#\#\#\#4.2.1.系统参数

  


 参数名

\| 类型

\| 是否必填 \| 说明

  


 ----------\|-------

\|-----

  


 token\|String\|是\|驭信开放接口token

  


 iv\|String \|是\|对应授权服务的iv参数，logon参数加密偏移变量

  


\#\#\#\#4.2.2.业务参数

  


  


 参数名

\| 类型

\| 是否必填 \| 说明

  


 ----------\|-------

\|-----

  


 logon\|String\|是\| json类型字段加密后生成

  


  


 业务参数是json加密后的字符串，加密时使用加密秘钥和加密偏移变量参数，加密秘钥由驭信平台提供，加密偏移变量，由调用方生成并传入。

  


\#\#\#\#\#logon字段描述

  


 参数名

\| 类型

\| 备注

\| 是否必填

  


 ----------\|------- \|----------

\|-----

  


 idCard

\|String \|

身份证号码

\|

是

  


 userName

\|String \| 客户姓名

\| 是

  


 cardNo

\|String\| 银行卡账户 \| 否

  


 loginphone\|String \|

手机号码

\| 否

  


  


\#\#\#4.3.返回结果

  


\#\#\#\#4.3.1.返回数据为Json格式的字符串，字段描述如下：

  


  


 参数名 \| 类型 \| 父节点 \| 备注

  


 -----------\|----------\|---------\|---------------

  


 blackList \| Boolean \| Null \|

是否黑名单

  


 finalDecision \| Number \| Null \| 最终决策建议

  


 hitRules\| Array \| Null \| 命中规则

  


 decision\| Number \| hitRules \| 决策建议

  


 memo\| String \| hitRules \| 备注

  


 ruleId\| String \| hitRules \| 规则代码

  


 ruleName\| String \| hitRules \| 规则名称

  


 ruleType\| Number \| hitRules \| 规则类型

  


 score \| Number \| hitRules \| 权重数值

  


 info \| String \| Null \| 数据对象

  


 message \| String \| Null \| 命中说明

  


 result \| Boolean \| Null \| 请求是否成功

  


 statusCode \| Number \| Null \| 请求返回码

  


  


\#\#\#\#4.3.2.决策建议代码表

  


  


 状态码\|描述

  


 -----------\|---------

  


 1 \| 通过

  


 2 \| 人工审核

  


 3 \| 拒绝

  


  


\#\#\#\#4.3.3.规则类型代码表

  


  


 状态码\|描述

  


 -----------\|---------

  


 1

\| 信贷灰名单

  


 2

\| 信贷黑名单

  


 3

\| 多头借贷

  


 4

\| 多头申请

  


 5

\| 失信灰名单

  


 6

\| 失信黑名单

  


 7

\| 欺诈灰名单

  


 8

\| 欺诈黑名单

  


 9

\| 逾期灰名单

  


 10 \| 逾期黑名单

  


 11 \| 网络灰名单

  


  


\#\#\#\#4.3.4.规则代码表

  


  


 规则ID \| 规则名称 \| 规则类别\| 规则类别名称

  


 -----------\|---------\|---------\|---------

  


 XDG1001 \| 信贷逾期1-30天 \| 1 \| 信贷灰名单

  


 XDG1002 \| 信贷逾期1期 \| 1 \| 信贷灰名单

  


 XDG1003 \| 冒用风险名单 \| 1 \| 信贷灰名单

  


 XDG1004 \| 助学贷款逾期名单 \| 1 \| 信贷灰名单

  


 XDG1005 \| 失联名单 \| 1 \| 信贷灰名单

  


 XDG1006 \| 套现灰名单 \| 1 \| 信贷灰名单

  


 XDG1007 \| 曾经逾期30天内灰名单 \| 1 \| 信贷灰名单

  


 XDG1008 \| 曾经逾期未知期限灰名单 \| 1 \| 信贷灰名单

  


 XDG1009 \| 模型分值低灰名单 \| 1 \| 信贷灰名单

  


 XDG1010 \| 泄露风险名单 \| 1 \| 信贷灰名单

  


 XDG1011 \| 疑似虚假地址 \| 1 \| 信贷灰名单

  


 XDB1012 \| P2P黑名单 \| 2 \| 信贷黑名单

  


 XDB1013 \| 信用消费黑名单 \| 2 \| 信贷黑名单

  


 XDB1014 \| 信贷行业P2P黑名单 \| 2 \| 信贷黑名单

  


 XDB1015 \| 信贷行业失联黑名单 \| 2 \| 信贷黑名单

  


 XDB1016 \| 信贷行业套现黑名单 \| 2 \| 信贷黑名单

  


 XDB1017 \| 信贷行业欺诈黑名单 \| 2 \| 信贷黑名单

  


 XDB1018 \| 信贷行业黑名单 \| 2 \| 信贷黑名单

  


 XDB1019 \| 信贷逾期121-150天 \| 2 \| 信贷黑名单

  


 XDB1020 \| 信贷逾期151-180天 \| 2 \| 信贷黑名单

  


 XDB1021 \| 信贷逾期180天以上 \| 2 \| 信贷黑名单

  


 XDB1022 \| 信贷逾期2期 \| 2 \| 信贷黑名单

  


 XDB1023 \| 信贷逾期31-60天 \| 2 \| 信贷黑名单

  


 XDB1024 \| 信贷逾期3期 \| 2 \| 信贷黑名单

  


 XDB1025 \| 信贷逾期4期 \| 2 \| 信贷黑名单

  


 XDB1026 \| 信贷逾期5期 \| 2 \| 信贷黑名单

  


 XDB1027 \| 信贷逾期61-90天 \| 2 \| 信贷黑名单

  


 XDB1028 \| 信贷逾期6期 \| 2 \| 信贷黑名单

  


 XDB1029 \| 信贷逾期6期以上 \| 2 \| 信贷黑名单

  


 XDB1030 \| 信贷逾期91-120天 \| 2 \| 信贷黑名单

  


 XDB1031 \| 信贷黑名单 \| 2 \| 信贷黑名单

  


 XDB1032 \| 商户欺诈名单 \| 2 \| 信贷黑名单

  


 XDB1033 \| 欺诈名单 \| 2 \| 信贷黑名单

  


 XDB1034 \| 电商行业虚假交易黑名单 \| 2 \| 信贷黑名单

  


 XDB1035 \| 骗取补贴黑名单 \| 2 \| 信贷黑名单

  


 XDB1036 \| 黑中介名单 \| 2 \| 信贷黑名单

  


 DTL1037 \| 一个月内多头借贷 \| 3 \| 多头借贷

  


 DTL1038 \| 七天内多头借贷 \| 3 \| 多头借贷

  


 DTL1039 \| 三个月内多头借贷 \| 3 \| 多头借贷

  


 DTL1040 \| 三天内多头借贷 \| 3 \| 多头借贷

  


 DTA1041 \| 一个月内多头申请 \| 4 \| 多头申请

  


 DTA1042 \| 七天内多头申请 \| 4 \| 多头申请

  


 DTA1043 \| 三个月内多头申请 \| 4 \| 多头申请

  


 DTA1044 \| 三天内多头申请 \| 4 \| 多头申请

  


 DTA1045 \| 当天内多头申请 \| 4 \| 多头申请

  


 SXG1046 \| 屋内非法活动 \| 5 \| 失信灰名单

  


 SXG1047 \| 扰民被投诉 \| 5 \| 失信灰名单

  


 SXG1048 \| 拆改房屋结构 \| 5 \| 失信灰名单

  


 SXG1049 \| 擅自转租 \| 5 \| 失信灰名单

  


 SXG1050 \| 改变房屋用途 \| 5 \| 失信灰名单

  


 SXG1051 \| 法院结案名单 \| 5 \| 失信灰名单

  


 SXG1052 \| 电商卖家套现 \| 5 \| 失信灰名单

  


 SXG1053 \| 电商恶意差评 \| 5 \| 失信灰名单

  


 SXG1054 \| 电商涉嫌售假 \| 5 \| 失信灰名单

  


 SXG1055 \| 电商炒信 \| 5 \| 失信灰名单

  


 SXB1056 \| 失联被强制解约 \| 6 \| 失信黑名单

  


 SXB1057 \| 法院失信名单 \| 6 \| 失信黑名单

  


 SXB1058 \| 法院执行名单 \| 6 \| 失信黑名单

  


 SXB1059 \| 违约被清退 \| 6 \| 失信黑名单

  


 QZG1060 \| 三方支付盗用支出灰名单 \| 7 \| 欺诈灰名单

  


 QZG1061 \| 异常手机号码信息 \| 7 \| 欺诈灰名单

  


 QZG1062 \| 异常设备信息 \| 7 \| 欺诈灰名单

  


 QZG1063 \| 网络风险名单 \| 7 \| 欺诈灰名单

  


 QZB1064 \| 三方支付欺诈黑名单 \| 8 \| 欺诈黑名单

  


 QZB1065 \| 三方支付盗卡黑名单 \| 8 \| 欺诈黑名单

  


 QZB1066 \| 三方支付盗用操作黑名单 \| 8 \| 欺诈黑名单

  


 QZB1067 \| 三方支付盗用支出黑名单 \| 8 \| 欺诈黑名单

  


 QZB1068 \| 欺诈手机号码信息 \| 8 \| 欺诈黑名单

  


 QZB1069 \| 欺诈设备信息 \| 8 \| 欺诈黑名单

  


 QZB1070 \| 盗卡黑名单 \| 8 \| 欺诈黑名单

  


 QZB1071 \| 网络欺诈风险名单 \| 8 \| 欺诈黑名单

  


 QZB1072 \| 虚假号码黑名单 \| 8 \| 欺诈黑名单

  


 QZB1073 \| 通信小号黑名单 \| 8 \| 欺诈黑名单

  


 YQG1074 \| 出险逾期1-30天 \| 9 \| 逾期灰名单

  


 YQG1075 \| 租客房租逾期 \| 9 \| 逾期灰名单

  


 YQG1076 \| 租客杂费逾期 \| 9 \| 逾期灰名单

  


 YQG1077 \| 租车支付逾期1-7天 \| 9 \| 逾期灰名单

  


 YQG1078 \| 租车支付逾期15-30天 \| 9 \| 逾期灰名单

  


 YQG1079 \| 租车支付逾期8-14天 \| 9 \| 逾期灰名单

  


 YQG1080 \| 租车未还超期1-7天 \| 9 \| 逾期灰名单

  


 YQG1081 \| 租车未还超期15-30天 \| 9 \| 逾期灰名单

  


 YQG1082 \| 租车未还超期8-14天 \| 9 \| 逾期灰名单

  


 YQG1083 \| 运营商欠费1-30天 \| 9 \| 逾期灰名单

  


 YQG1084 \| 违章未处理超期1-7天 \| 9 \| 逾期灰名单

  


 YQG1085 \| 违章未处理超期15-30天 \| 9 \| 逾期灰名单

  


 YQG1086 \| 违章未处理超期8-14天 \| 9 \| 逾期灰名单

  


 YQG1087 \| 酒店未支付逾期1-7天 \| 9 \| 逾期灰名单

  


 YQG1088 \| 酒店未支付逾期15-30天 \| 9 \| 逾期灰名单

  


 YQG1089 \| 酒店未支付逾期8-14天 \| 9 \| 逾期灰名单

  


 YQB1090 \| 出险逾期121-150天 \| 10 \| 逾期黑名单

  


 YQB1091 \| 出险逾期151-180天 \| 10 \| 逾期黑名单

  


 YQB1092 \| 出险逾期180天以上 \| 10 \| 逾期黑名单

  


 YQB1093 \| 出险逾期31-60天 \| 10 \| 逾期黑名单

  


 YQB1094 \| 出险逾期61-90天 \| 10 \| 逾期黑名单

  


 YQB1095 \| 出险逾期91-120天 \| 10 \| 逾期黑名单

  


 YQB1096 \| 租客违约拒赔 \| 10 \| 逾期黑名单

  


 YQB1097 \| 租车支付逾期121-150天 \| 10 \| 逾期黑名单

  


 YQB1098 \| 租车支付逾期151-180天 \| 10 \| 逾期黑名单

  


 YQB1099 \| 租车支付逾期180天以上 \| 10 \| 逾期黑名单

  


 YQB1100 \| 租车支付逾期31-60天 \| 10 \| 逾期黑名单

  


 YQB1101 \| 租车支付逾期61-90天 \| 10 \| 逾期黑名单

  


 YQB1102 \| 租车支付逾期91-120天 \| 10 \| 逾期黑名单

  


 YQB1103 \| 租车未还超期121-150天 \| 10 \| 逾期黑名单

  


 YQB1104 \| 租车未还超期151-180天 \| 10 \| 逾期黑名单

  


 YQB1105 \| 租车未还超期180天以上 \| 10 \| 逾期黑名单

  


 YQB1106 \| 租车未还超期31-60天 \| 10 \| 逾期黑名单

  


 YQB1107 \| 租车未还超期61-90天 \| 10 \| 逾期黑名单

  


 YQB1108 \| 租车未还超期91-120天 \| 10 \| 逾期黑名单

  


 YQB1109 \| 租车行业逾期未支付黑名单 \| 10 \| 逾期黑名单

  


 YQB1110 \| 运营商欠费31-60天 \| 10 \| 逾期黑名单

  


 YQB1111 \| 运营商欠费61-90天 \| 10 \| 逾期黑名单

  


 YQB1112 \| 运营商欠费91天以上 \| 10 \| 逾期黑名单

  


 YQB1113 \| 违章未处理超期121-150天 \| 10 \| 逾期黑名单

  


 YQB1114 \| 违章未处理超期151-180天 \| 10 \| 逾期黑名单

  


 YQB1115 \| 违章未处理超期180天以上 \| 10 \| 逾期黑名单

  


 YQB1116 \| 违章未处理超期31-60天 \| 10 \| 逾期黑名单

  


 YQB1117 \| 违章未处理超期61-90天 \| 10 \| 逾期黑名单

  


 YQB1118 \| 违章未处理超期91-120天 \| 10 \| 逾期黑名单

  


 YQB1119 \| 酒店未支付逾期121-150天 \| 10 \| 逾期黑名单

  


 YQB1120 \| 酒店未支付逾期150-180天 \| 10 \| 逾期黑名单

  


 YQB1121 \| 酒店未支付逾期180天以上 \| 10 \| 逾期黑名单

  


 YQB1122 \| 酒店未支付逾期31-60天 \| 10 \| 逾期黑名单

  


 YQB1123 \| 酒店未支付逾期61-90天 \| 10 \| 逾期黑名单

  


 YQB1124 \| 酒店未支付逾期91-120天 \| 10 \| 逾期黑名单

  


 YQB1125 \| 酒店行业逾期未支付黑名单 \| 10 \| 逾期黑名单

  


 WLG1126 \| 欺诈行为黑名单 \| 11 \| 网络灰名单

  


 WLG1127 \| 赌博、吸毒名单 \| 11 \| 网络灰名单

  


 XDB1128 \| 金融机构黑名单 \| 2 \| 信贷黑名单

  


 XDG1129 \| 网络贷款信息 \| 1 \| 信贷灰名单

  


 SXB1130 \| 失信黑名单 \| 6 \| 失信黑名单

  


  


  


\#\#\#\#4.3.5.statusCode

请求返回码描述

  


  


 状态码 \|描述

  


 -----------\|---------

  


 200

\| 成功

  


 201

\| 部分成功

  


 301

\| 参数不能为空

  


 302

\| 请求账号不存在

  


 303

\| 请求密码不正确

  


 304

\| 请求帐号被冻结

  


 305

\| 请求没有此接口访问权限

  


 306

\| 请求参数{$1}为空或格式错误

  


 307

\| 请求验签失败

  


 308

\| 请求没有查询到结果

  


 309

\| 请求重复的请求

  


 310

\| 请求参数中存在无效数据

  


 311

\| 权限不足

  


 312

\| 请求账号余额不足

  


 313

\| 剩余次数不足

  


 314

\| 合同时间过期

  


 315

\| 请求头信息错误

  


 500

\| 系统错误，服务器异常

  


 501

\| 查询超时

  


 502

\| 请求失败

  


 503

\| 接口未响应

  


 504

\| 外部数据源异常

  


  


  


  


  


  


  


\#\#\#4.4.返回数据示例：

  


  


  


{

  


"

blackList

"

: false,

  


"

finalDecision

"

: null,

  


"

hitRules

"

: null,

  


"

info

"

: null,

  


"

message

"

: 

"

参数-手机号码-错误

"

,

  


"

result

"

: true,

  


"

statusCode

"

: 

"

10007

"

  


}

  


  


 或

  


  


{

  


"

blackList

"

: true,

  


"

finalDecision

"

: 3,

  


"

hitRules

"

: \[

  


{

  


"

decision

"

: 3,

  


"

memo

"

: null,

  


"

ruleId

"

: 

"

QZB1071

"

,

  


"

ruleName

"

: 

"

网络欺诈风险名单

"

,

  


"

ruleType

"

: 8,

  


"

score

"

: 0

  


},

  


{

  


"

decision

"

: 2,

  


"

memo

"

: null,

  


"

ruleId

"

: 

"

XDG1011

"

,

  


"

ruleName

"

: 

"

疑似虚假地址

"

,

  


"

ruleType

"

: 1,

  


"

score

"

: 0

  


},

  


{

  


"

decision

"

: 3,

  


"

memo

"

: null,

  


"

ruleId

"

: 

"

XDB1021

"

,

  


"

ruleName

"

: 

"

信贷逾期180天以上

"

,

  


"

ruleType

"

: 2,

  


"

score

"

: 0

  


}

  


\],

  


"

info

"

: null,

  


"

message

"

: 

"

命中黑名单

"

,

  


"

result

"

: true,

  


"

statusCode

"

: 

"

200

"

  


}

  


\#\#5.其他

  


\#\#\#5.1.token鉴权

  


 token鉴权调用驭信鉴权接口，若鉴权不通过，将返回驭信鉴权接口返回数据，具体数据参照驭信token鉴权接口文档

  


\#\#\#5.2.鉴权失败返回示例

  


  


  


{

  


"

errorCode

"

: 

"

105

"

,

  


"

errorDetail

"

: 

"

无效token

"

,

  


"

errorReason

"

: null,

  


"

info

"

: null,

  


"

returnCode

"

: 

"

"

,

  


"

returnDesc

"

: 

"

"

  


}

  


  


 或

  


  


{

  


"

errorCode

"

: 

"

104

"

,

  


"

errorDetail

"

: 

"

账户余额不足

"

,

  


"

errorReason

"

: null,

  


"

info

"

: null,

  


"

returnCode

"

: 

"

"

,

  


"

returnDesc

"

: 

"

"

  


}

  


 或

  


  


  


{

  


"

errorCode

"

: 

"

103

"

,

  


"

errorDetail

"

: 

"

账户已下线

"

,

  


"

errorReason

"

: null,

  


"

info

"

: null,

  


"

returnCode

"

: 

"

"

,

  


"

returnDesc

"

: 

"

"

  


}

  


  


  


