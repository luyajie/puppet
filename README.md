扯线木偶（puppet）
==
Puppet是一个基于商业免费软件（同花顺、通达信）构建而成的闭环的A股实盘交易框架。“目前”是在建项目(WIP)。
--
项目进度：界面操控API ->> 预警交互API

构建流程：界面操控API ->> 预警交互API ->> 信号推送API ->> 策略中枢API ->> 历史数据API ->> 回测模块API
*********************************************************************************************************************************

工作流程：手动登录客户端 --> 运行扯线木偶 --> 自动搜索已登录的客户端 --> 交易前的预备 --> 自动获取持仓数据 --> 查询预警名单 --> 客户端待命状态

**推荐使用最新版的Anaconda3，或者Python 3.5+。系统要求：Windows平台，Win2000+；Linux平台，安装最新的WineHQ，环境设为WIN7。**

第三方库依赖：pyperclip(仅限于同花顺), pywinauto(仅限于通达信)

界面操控API
*********************************************************************************************************************************
* method: '买入': buy(), '卖出': sell(), '撤单': cancel(), '打新': raffle(), '下单': order()

* property: '可用余额': balance, '持仓': position, '成交': deals, '可撤委托': cancelable, '新股': new, '中签': bingo, '帐号': account
*********************************************************************************************************************************

* 招商证券只测试过最新版能独立交易模式登录使用！辣鸡定制版不会增加任何支持了。国金、中信通达信据反馈资金明细不兼容。
* 暂不支持融资融券！
* 同花顺交易端：无任何限制！官方统一版或老版、券商定制版（银河、国泰君安、华泰、广发、东方财富等）。
* 通达信交易端：无任何限制！目前不支持独立交易端。
* 多账户同时交易：完全支持！同一券商或多个券商。
* 注意：暂不支持一个交易端通过“添加”同一券商多个账户同时交易，只能交易当前的那一个账户。

### 更新

2017/4/6 更新至v0.4.7，改善raffle()的兼容性，可以支持银河官方的同花顺独立交易端打新。

2017/4/4 通达信版改一个控件代码，支持招商证券独立交易模式登录。

2017/4/2 更新至v0.4.6，增加bingo中签查询。

2017/4/1 更新至v0.4.5，修复了一个愚蠢的错误：symbol[0].startswith('')返回True，导致不打新股，一脸懵逼！

2017/3/28 更新至v0.4.4，支持buy()/sell()直接输数字下单，无需字符串。

2017/3/10 更新至v0.4.3，优化输出效果，更友好。

2017/3/10 更新至v0.4.2，raffle增加skip参数，跳过指定的市场新股。

2017/3/10 更新到v0.4.1，小幅修改，部分优化，默认改为单交易客户端模式。 

2017/3/9 v0.4版发布！增加一键打新(raffle)、查新股（new）功能。大幅度修改优化，强化拟人化操作逻辑。

2017/2/23 V0.3.5发布！小幅修改，改善操作流畅度。

2017/2/22 v0.3发布！优化模拟人手交易的流程。

2017/2/21 v0.2.5发布！增加撤单（指定股票代码）功能。

2017/2/14 v0.2版发布！提供后台获取持仓数据。鸣谢网友liuyukuan博文中提供的AHK代码“SendMessage,0x111,57634,0,CVirtualGridCtrl2,同花顺”。

Windows下不需要安装、配置。

Linux下需要安装最新版本的Wine，环境设为Windows 7，先安装同花顺交易客户端，能正常使用之后再安装Python for Windows。启动wineconsole，pip install pyperclip，之后就可以正常使用了。
