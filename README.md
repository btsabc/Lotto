  Lotto项目的目标是设计出一套 在EOS去中心平台上可靠运行 的乐透系统，让用户的账户成为不受任何机构控制的私人所属，基于EOS的智能合约实现的投注和开奖让乐透透明化，解决抽奖公平公正性的争议，解决领奖难以及限制购买等现存的问题。

Lotto具体技术实现：
 
1.实现EOS链上的随机数生成合约
  随机数有很多的应用场景，而随机数的生成是一个由来已久的问题。一个基本的原则是随机数的生成不能被任何个体所控制，从比特币的未来某区块的数据来获取随机性的方式是有风险的，当做假的利益大于正当做区块的利益时，这个相关人就有可能作恶。
Lotto采用的是一种分布式自治的随机数生成算法，构建一个EOS的随机数合约，提供在链的随机数生成机制，在链的随机数生成机制是每轮由n个以上 参与者 提供随机数种子，并分享代币奖励，参与者作弊的会受到惩罚。 参与者 提供随机数种子方法是，每个参与者每轮会先提供出下一轮随机数种子的校验和，每轮的随机数种子会与上轮的校验和验证，确保参与者不能作弊。
合约还提供随机数接口供其他合约使用，随机数消费者需要用代币支付费用，形成一个随机数生产消费链，自治工作。该合约生产的随机数供应给乐透合约随机公平地生成开奖号。
 
2.实现EOS链上的乐透合约
  不同于现实世界的彩票，LOT的乐透合约是一个自治的博弈系统，采用概率发奖金，总体上看奖池金额会全部返还投注人，系统没有赢余。为了鼓励前期投注人参与，系统还会设置一个固定的年通胀率，按照投注代币锁定的时间长度，给参与人予一定的代币补偿，还会有一个推荐人制度，补偿由参与者和其推荐人分享。
乐透合约的中奖号码是根据前面提到的随机数生成合约提供的随机数开奖，确保结果是随机公正的。系统也会设置一些与外部乐透的相同规则的品种，通过引入外部开奖数据进行开奖（EOS链通过Oracle功能，可以将外部数据可靠的引入区块链来实现链内链外的数据互通，参考欧链项目http://oraclechain.io/)。

3.实现博彩的UI界面
  定制一个实用的美观又大方的博彩交互界面，这样才能吸引更多的人参与进来
