 手机实名认证验证服务

  


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

  


 手机实名认证验证服务，提供手机实名认证验证接口服务，接口鉴权由驭信平台进行。

  


  


\#\#3.接口地址

  


\#\#\#3.1测试地址

  




  


\#\#4.身份验证接口调用

  


\#\#\#4.1.接口

  


 \| 接口

\| 请求方式

\| 请求参数类型\|

返回结果类型

  


 \| - \| :-: \| -: \|

  


 \| api/personalInfo/verifyMobile\| post\| - \|josn

  


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

  


 logon\|String\|是\|json类型加密后生成

  


  


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

  


 loginphone \| String \|

手机号

\| 是

  


  


  


\#\#\#4.3.返回结果

  


\#\#\#\#4.3.1.返回数据为Json格式的字符串，字段描述如下：

  


  


  


  


 参数名 \| 类型 \| 备注

  


 -----------\|---------\|---------------

  


 errorCode \| Number \| 请求响应代码

  


 errorDetail \| String \| 请求响应描述

  


 returnCode\| Number \| 业务执行结果代码

  


 returnDesc\| String\| 业务执行结果描述

  


  


  


 errorCode

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

  


  


  


  


 returnCode

业务返回码描述

  


  


 状态码 \|描述

  


 -----------\|---------

  


 10000 \|

一致的

  


 10001 \|

不一致的

  


 10002 \|

未知的

  


  


  


 返回数据示例：

  


  


 账号不存在

  


  


{

  


"

errorCode

"

: 

"

302

"

,

  


"

errorDetail

"

: 

"

请求账号不存在

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

0

"

,

  


"

returnDesc

"

: null

  


}

  


  


 参数不正确

  


  


{

  


"

errorCode

"

: 

"

306

"

,

  


"

errorDetail

"

: 

"

请求参数logon为空或格式错误

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

0

"

,

  


"

returnDesc

"

: null

  


}

  


  


 未配置任何服务

  


  


{

  


"

errorCode

"

: 

"

311

"

,

  


"

errorDetail

"

: 

"

权限不足

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

0

"

,

  


"

returnDesc

"

: null

  


}

  


  


 未配置待访问的服务

  


  


{

  


"

errorCode

"

: 

"

305

"

,

  


"

errorDetail

"

: 

"

帐号没有此接口访问权限

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

0

"

,

  


"

returnDesc

"

: null

  


}

  


  


 成功返回

  


{

  


"

errorCode

"

: 

"

200

"

,

  


"

errorDetail

"

: 

"

查询成功

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

10000

"

,

  


"

returnDesc

"

: 

"

一致的

"

  


}

  


 {

  


"

errorCode

"

: 

"

200

"

,

  


"

errorDetail

"

: 

"

查询成功

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

10001

"

,

  


"

returnDesc

"

: 

"

不一致的

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

  


  


