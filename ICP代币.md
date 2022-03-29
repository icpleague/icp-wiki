# ICP代币

互联网计算机协议 (ICP) 实用代币在 IC 中扮演着多管齐下的角色。ICP 代币持有者可以参与互联网计算机的治理，ICP 代币用于奖励节点提供者，并且（间接）用于支付运行在 IC 上的智能合约所使用的资源。ICP 代币在许多加密交易所[[1\]](https://coinmarketcap.com/currencies/internet-computer/)[[2\]](https://www.coingecko.com/en/coins/internet-computer)上进行交易。

## ICP代币和治理

要参与互联网计算机的治理，必须将 ICP 代币锁定在股份中。在 IC 上，赌注被称为神经元，并允许参与由[网络神经系统](https://wiki.internetcomputer.org/wiki/Network_Nervous_System)(NNS) 在 IC 上实施的算法治理系统。神经元所有者可以提交提案并对指导 IC 演进的提案进行投票。每隔一定时间，（目前是每 24 小时），对上一时期解决的提案进行投票的神经元获得与神经元的投票权成正比的奖励。该 wiki 还提供了有关[如何质押 ICP 代币](https://wiki.internetcomputer.org/w/index.php?title=How_to_stake_on_the_Internet_computer&action=edit&redlink=1)以及[神经元如何参与治理的](https://wiki.internetcomputer.org/wiki/Governance_of_the_Internet_Computer)更多信息。

## ICP 代币和容器（dapps/智能合约）

ICP代币可以转换为Cycles。Cycles 是 IC 的第二个原生实用代币，其主要目的是为构建在 IC 平台上的智能合约生态系统提供动力。特别是，Cycles用于支付创建容器和容器使用的资源（存储、计算和带宽）的费用。

将 ICP 转换为Cycles是 NNS 的内置功能：NNS 会燃烧 ICP 代币和铸币Cycles。转换过程将Cycles成本与称为特别提款权 (SDR) 的一篮子货币的价值[挂钩](https://www.imf.org/external/np/fin/data/rms_sdrv.aspx)。更详细地说，IC 获取有关最新 ICP 到 SDR 转换率的信息，然后将 ICP 设置为Cycles转换率，因此 1 万亿个Cycles花费 0.8 SDR。在转换过程中，ICP 代币被有效地烧毁并铸造相应的Cycles。

## ICP 代币和节点提供者

ICP 代币用于支付节点提供商——这些是拥有构成 IC 的计算节点的实体。NNS 定期（目前每月）决定每个节点提供者获得的代币数量，铸造相应的代币，并将代币发送到节点提供者的账户。

## ICP代币获取方式

您可以通过多种方式获取 ICP 代币：

- 通过列出可供交易的 ICP 代币的交易所直接购买 ICP 代币。Coinmarketcap 维护着一份相当完整的能交易 ICP代币的[交易所列表](https://coinmarketcap.com/currencies/internet-computer/markets/)
- [参与](https://wiki.internetcomputer.org/wiki/Governance_of_the_Internet_Computer)互联网计算机治理获得代币作为投票奖励
- 从将 ICP 代币发送到您创建的帐户的人那里接收 ICP 代币
- 通过互联网计算机协会 (ICA) 或 DFINITY 基金会获得[开发者代币赠款](https://dfinity.org/grants/)
- 作为节点提供者提供计算能力而获得代币作为报酬

## ICP账户和交易的分类账

在 IC 上，有关 ICP 代币的信息保存在 Ledger 容器中，该容器是网络神经系统的一个组件。Ledger 容器维护帐户标识符和 (ICP) 代币数量之间的映射。Ledger 提供了一个 API，允许控制帐户的委托人（例如用户或容器）将 ICP 代币转移到任何其他帐户。所有转账都被记录为交易分类账中的交易。账本还记录了 ICP 代币的铸造和燃烧。

对用户的 ICP 帐户和神经元的控制与唯一的主体相关联。委托人标识可用于涉及委托人账户和神经元的操作的授权机制。用户主体源自公共签名密钥的散列，并且为了授权用户在其上创建数字签名的交易。不用说，用户的私人签名密钥应该被安全地生成（例如，具有足够的熵），应该被安全地存储并且应该被备份。根据密钥控制的 ICP 代币（或神经元）的值，用户可以在密钥的安全性和使用密钥所需的摩擦级别之间做出权衡。可以在[此处](https://wiki.internetcomputer.org/wiki/Managing_ICP_holdings)找到管理 ICP 持有量的用户指南。