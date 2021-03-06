# NodeQuant量化交易框架

![](https://raw.githubusercontent.com/zhangshuiyong/Img/master/nodequant/nodequant%E6%9E%B6%E6%9E%84.png?ynotemdtimestamp=1533340007285)

1. **策略层**：策略层代表各种量化策略实例。策略实例负责运行交易算法，集成了交易事件响应函数，有OnTick、OnNewBar、OnCloseBar、OnOrder、OnTrade等事件响应函数，驱动量化策略的运行。
2. **策略引擎层:** NodeQuant系统运行会唯一创建一个策略引擎实例，策略引擎层代表的就是这个策略引擎。策略引擎开始运行会根据用户的策略配置创建策略实例，也可以停止策略实例。响应策略的下单命令，推送策略订阅的合约行情，保存策略运行的仓位、订单、成交、结算信息等状态信息，接收交易Client的订单回报，成交回报。
3. **主引擎层:** NodeQuant系统运行会唯一创建一个主引擎实例，主引擎层代表的就是这个主引擎。主引擎负责启动上层策略引擎和连接底层的各个交易Client，接收来自底层交易Cient的行情信息，并且响应上层策略引擎的下单命令。
4. **交易客户端层:** 交易客户端层集成多个交易客户端。连接交易所，接收来自交易所的信息，响应上层主引擎的在各个交易客户端的下单命令。NodeQuant 未来将会集成上期CTP、飞鼠Sgit 、富途证券、盈透证券IB的程序化API交易客户端，未来可在多市场中交易和套利。**目前已经集成上期CTP API客户端。**

