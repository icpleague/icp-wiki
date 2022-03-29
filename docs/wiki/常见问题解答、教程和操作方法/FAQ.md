# FAQ
这是一个针对普通观众的，关于互联网计算机(IC)的常见问题集合。
## 1. 总体概括
### 1.1 什么是互联网计算机?
互联网计算机是一个“多功能的”区块链，它为存储代币和去中心化应用程序(dapps)提供了一个公共平台。它是一个完整的技术栈，这样系统和服务就可以完全在区块链上运行。它的主要特点是：
* 非常快
* 存储智能合约非常便宜（例如，比以太坊便宜数百万倍）
* 受到链上治理和升级的支配
* 强大的智能合约可以同时托管后端和前端，提供良好的用户体验
* 环保  

查看更多：
* [互联网计算机概述](互联网计算机概述.md)
* [互联网计算机愿景](互联网计算机愿景.md)   

### 1.2 什么类型的dapp可以在IC上运行?
 IC可以运行非常复杂的智能合约和dapp。最引入注目的是，IC上的智能合约和dapp与其他区块链的区别在于:
* 它们的维护成本很低；
* 它们足够快，能提供良好的用户体验；
* 由于采用了容器模型，它们很容易开发；
* 它们托管所有的状态、前端和后端代码(dapp的每个部分都在链上)。  

参见示例列表：[Index_of_dapps_on_the_Internet_Computer_ecosystem](https://wiki.internetcomputer.org/wiki/Index_of_dapps_on_the_Internet_Computer_ecosystem)

## 2 加密和区块链问题
### 2.1 IC与比特币有何不同？
IC和比特币都是区块链。他们的不同点在于，比特币本质上只是一个账本，不能托管任何 dapp。它只能维护哪些帐户拥有哪些代币的状态。IC可以拥有极其复杂的智能合约和dapp，可以支持defi、游戏、社交、企业和其他类型的dapp。

更具体地说，由于比特币的限制，智能合约开发人员无法在比特币上构建智能合约。

在内部，IC 速度更快，效率更高，可以托管整个 dapp，等等……

## 3 现在的IC  
### 3.1 IC有多大？
互联网计算机的大小（阅读：拓扑[[1]](https://medium.com/dfinity/a-technical-overview-of-the-internet-computer-f57c62abc20f))可以通过以下几种方式测量：

* 智能合约数量
* 子网数量
* 节点数量
* 数据中心数量  

![网络构建区块的层次结构 Hierarchy of network building blocks](https://user-images.githubusercontent.com/64115203/158592581-914dda55-83df-440c-bc5e-bf2aef486990.png)


### 3.2 IC上有多少智能合约？
* 截至2022年2月3日，自2021年5月10日以来创建了30,100[[2]](https://dashboard.internetcomputer.org/)个智能合约。目标是在 10 年内达到数十亿。
* 截至2022年2月3日，互联网计算机中有30个子网[[3](https://dashboard.internetcomputer.org/)]。目标是在 10 年内达到数十万。
* 截至2022年2月3日，互联网计算机中有414个节点[[4]](https://dashboard.internetcomputer.org/)。目标是在 10 年内达到数百万。
* 截至2022年2月3日，互联网计算机中有21个节点[[5]](https://www.dfinityexplorer.org/#/datacenters/)。目标是在 10 年内达到数千个。  

### 3.3 有哪些在IC上的dapp和智能合约的例子?

## 4 互联网计算机有多快?
为深入了解，请参阅[互联网计算机的性能](互联网计算机的性能.md)。  

以下是高层次的概述: 

回答这个问题最有效的方法就是选择一个有利的角度。

### 4.1 从dapp用户的角度来看(例如:“dapps速度使之成为可能”)  

从dapp用户的角度来看，IC足够“快”，以至于用户不会知道它在幕后(或Azure、IBM或AWS)运行着一个区块链。它可以与中心化计算提供商相媲美。这意味着，尽管由于用户体验缓慢，“在(传统的)智能合约上创建一个Airbnb网络应用程序”非常麻烦，但开发者可以“在互联网计算机上创建Airbnb网络应用程序”。    

这就是[OpenChat](https://v2.oc.app/), LinkedUp, Distrikt这样的应用程序能够提供良好用户体验的原因。

### 4.2 从dapp开发者的视角来看 （例如：调用的执行时间（ latency ））

有两个相关因素:  
a. 在IC上，dapp从后端读取数据的速度有多快 -- 应用程序可以对容器(容器掌管状态)进行查询调用，因此它可以在不到一秒的时间内读取数据(目标在200毫秒以下，通常在250毫秒以下)。  
b. 在IC上，dapp写入数据到后端的速度有多快 --  应用程序可以进行更新调用。这些需要达成共识，所以需要更多的时间。目标目前是2秒(通过不断努力来进一步减少)。与BTC或ETH相比，这是数量级的更快。与中心化计算相比，这可能一开始看起来很慢，但实际上，如果考虑到大多数栈中服务器之间的复制量，这是意料之中的。

更多细节参考：[互联网计算机的性能](互联网计算机的性能.md)。

### 4.3 从区块链测量的视角来看（例如：“每秒的区块数& 每秒的交易数”）  
IC是“无界的”，这意味着与大多数其他协议不同，它可以通过增加更多的机器来提高执行时间（ latency ）和通量。粗略地说，如果IC的子网增多，它可以处理更多的更新调用。如果每个子网的节点数量增加，则可以处理更多查询。这是“IC是无界的”这句话中的关键点。截至2021年1月18日，互联网计算机每秒处理31.7区块: https://dashboard.internetcomputer.org/  。

## ICP代币

### 5.1 什么是ICP效用型代币？
ICP代币有多种使用方式。
#### 5.1.1 计算和存储  

ICP的第一种使用方式是用来支付cycles形式的计算。ICP的1个[SDR](https://en.wikipedia.org/wiki/Special_drawing_rights)可以转换一万亿cycles。SDR(特别提款权)是国际货币基金组织在跟进的一篮子稳定货币。在撰写本文时，其价格约为1.42美元。网页的计算、存储和服务都需要消耗cycles。随着越来越多的dapp托管在计算机互联网区块链上，越来越多的ICP代币被转换和烧毁。

#### 5.1.2 治理计算机互联网
 ICP的第二种使用方式是在NNS中。如果你想在NNS中投票并获得投票奖励，你必须将你的ICP代币投到一个神经元中。投完票，你将获得新发行的ICP代币作为投票奖励。  

#### 5.1.3 奖励节点所有者
最后，ICP代币也可以作为对节点所有者的奖励。一方面，ICP的总供应是通缩的的，因为代币被燃烧和转换成cycles。另一方面，它也是膨胀的，因为奖励是为节点所有者和神经元创造的。

### 5.2 什么是ICP代币的供应、流通、燃烧和铸造?  
ICP代币流通的相关信息可在网站主页看到:[ICP流通](https://dashboard.internetcomputer.org/circulation)。

ICP的燃烧和铸造由以下机制决定:
#### 5.2.1 铸造机制
* ICP的铸造被用于支付NNS奖励：
   * 每年10%的通货膨胀，线性下降到每年5%
* ICP的铸造被用于支付给节点提供者：
   * 这取决于系统中节点的数量
   * 这部分目前仅占不到1%的铸造

#### 5.2.2 燃烧机制
*  燃烧ICP以制造cycles(支付计算和存储费用)
   *  这取决于智能合约和dapp的计算和存储需求
*  ICP用于创建NNS提案

## 6 为什么互联网计算机可以做这些其他区块链做不到的事情?
技术原因超出了FAQ的范围，但一个高层次的回答是:
### 6.1 计算机互联网的独特之处
链钥加密技术(Chain key cryptography[[6]](https://medium.com/dfinity/chain-key-technology-one-public-key-for-the-internet-computer-6a3644901e28))是驱动互联网计算机运行的引擎。它允许:
* 增加新的节点以形成新的子网，从而无限扩展网络； 
* 用新的节点替换故障或崩溃的节点，使其从不停止；
* 恢复子网，即使子网中有很多节点出现故障；
* 无间断地升级互联网计算机协议，允许网络修复漏洞并添加新功能。

### 6.2 互联网计算机所用的现代技术
用WebAssembly作为互联网计算机的执行层[[7]](https://www.reddit.com/r/dfinity/comments/nrmvim/ama_we_are_akhi_alexandra_islam_and_dimitris_from/)，这为容器智能合约提供了一个支持非常强大的智能合约的执行环境。

## 7 ICP生态系统
### 7.1 我在哪能看到IC上的dapps列表?
#### 7.1.1 dapps范例
* [Internet Identity](https://identity.ic0.app/)
* [NNS dapp](https://nns.ic0.app/)
* [DSCVR](https://h5aet-waaaa-aaaab-qaamq-cai.raw.ic0.app/)
* [Distrikt](https://c7fao-laaaa-aaaae-aaa4q-cai.ic0.app/)
* [OpenChat](https://7e6iv-biaaa-aaaaf-aaada-cai.ic0.app/)  

#### 7.1.2 dapps列表
参阅：[Index_of_dapps_on_the_Internet_Computer_ecosystem](https://wiki.internetcomputer.org/wiki/Index_of_dapps_on_the_Internet_Computer_ecosystem)
 


