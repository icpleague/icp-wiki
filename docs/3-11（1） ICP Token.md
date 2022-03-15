# ICP代币  

互联网计算机协议 (ICP) 效用型代币在IC中扮演着多方面的角色。ICP代币持有者可以参与互联网计算机的治理，ICP代币用于奖励节点提供者，并（间接地）用于支付IC上运行的智能合约所使用的资源。ICP代币在许多加密交易所的公开市场[[1]](https://coinmarketcap.com/currencies/internet-computer/)[[2]](https://www.coingecko.com/en/coins/internet-computer)上进行交易。

## ICP代币与治理  
要参与互联网计算机的治理，必须锁定ICP代币作为押金。这个押金(stake)被称为神经元（neurons)，可以参与由[网络神经系统](https://wiki.internetcomputer.org/wiki/Network_Nervous_System)在IC上实施的算法治理系统。神经元所有者可以提交提案，并对指导IC的演进的提案进行投票。每隔一段时间（目前是每24小时），给前一阶段已解决的提案投了票的神经元将获得与其投票权成正比的奖励。这个维基百科也提供了还提供了更多关于[如何质押ICP代币](https://wiki.internetcomputer.org/w/index.php?title=How_to_stake_on_the_Internet_computer&action=edit&redlink=1)以及[神经元如何参与治理](https://wiki.internetcomputer.org/wiki/Governance_of_the_Internet_Computer)的信息。
 
## ICP代币和容器（dapps/智能合约）  
ICP代币可以转换为Cycles。Cycles是IC的第二个原生实效用型代币，其主要目的是驱动建立在IC平台上的智能合约生态系统，被用来支付创建容器的费用以及容器使用的资源（存储、计算和带宽）的费用。

将ICP转换为cycles是NNS的内置功能：NNS会消耗ICP代币来制造cycles。转换过程将cycles的成本与一篮子货币的价值挂钩（[特别提款权（SDR）](https://www.imf.org/external/np/fin/data/rms_sdrv.aspx) ，更详细地说，IC获取关于ICP到SDR的转换率的最新信息，然后设置ICP到cycles的转换率，因此1万亿个cycles的价格为0.8 SDR。在转换过程中，ICP代币被实际燃烧并铸造出相应的cycles。  

## ICP 代币和节点提供者  
ICP代币被用于支付给节点提供者——他们拥有构成IC的计算节点。每隔一定时间(目前是每月一次)，NNS决定每个节点提供者获得的代币数量，铸造代币，并发到节点提供者的帐户上。

## ICP代币获取方式  
您可以通过多种方式获取ICP代币：

* 直接通过交易所购买ICP代币。Coinmarketcap提供了一个相当完整的可以买卖ICP代币的[交易所列表](https://coinmarketcap.com/currencies/internet-computer/markets/)。
* 参与互联网计算机治理获得代币作为投票奖励。
* 别人将ICP代币发到您创建的账户上。
* 从互联网计算机协会（ICA）或 DFINITY基金会获得[授予给开发者](https://dfinity.org/grants/)的代币。
* 作为节点提供者，因提供计算能力而获得代币作为报酬。  

## ICP账户和账本和交易  
ICP代币的相关信息被保存在账本容器中。账本容器是网络神经系统的一个组件，记载了帐户标识符和 (ICP) 代币数量之间的映射。账本提供了一个API，允许着控制帐户的主体(principal)（例如一个用户，或一个容器）将ICP代币转给其他帐户。所有转账都会被记录在交易账本上。账本还记录了ICP代币的铸造和燃烧。

用户的ICP帐户和神经元都是由一个唯一的主体(principal)所控制的。由主体来识别授权机制，用以授权帐户和神经元的相关操作。用户主体（user principals)来自于公共签名密钥的哈希(hash)，用户需要创建数字签名来授权交易。用户的私人签名密钥应该安全地生成(比如有足够的熵)、存储并备份。

根据密钥控制的ICP代币（或神经元）的价值，用户可以在密钥的安全性和使用密钥所要求的复杂程度之间做出权衡。关于管理所持ICP的用户指南可以参考[此处](https://wiki.internetcomputer.org/wiki/Managing_ICP_holdings)。