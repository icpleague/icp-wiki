# 投票和 NNS 奖励最大化
本文为希望最大限度地参与IC治理并获得NNS奖励的用户展示了常见的最佳实践。

## 背景
NNS是由互联网计算机社区控制的大脑。它是一个链上治理系统，在这里社区成员可以提交提案并投票。社区成员的投票权与ICP的数量成正比，他们质押了多长时间，质押了多长时间等......投了票的社区成员会得到ICP代币作为奖励（称为“NNS奖励”）。

本文为希望在网络中最大限度地参与（以及质押）的社区成员提供了最佳实践。

## 如何质押ICP和投票
最大化参与（以及获得NNS奖励）的最佳方式是投票，因此关键是了解如何投票。

要知道如何投票，请参阅选项[ICP投票选项](https://wiki.internetcomputer.org/wiki/ICP_voting_options)。

## 对于业余参与者
NNS是一种流动的民主，这意味着神经元可以将他们的投票权委托给其他神经元。这在两个方面对质押者有帮助：1.许多人只在业余时间参与，无法关注每一个讨论、主题、论坛或提案，几乎没有最佳实践 2.即使是全职参与的人也可能不具备他们关注的每个话题的专业知识。

因此，用户可以利用“流动民主”来追随你信任的、代表他们利益的神经元。例如，如果Alice的神经元跟随Bob的神经元，那么当Bob投票“接受”提案投票时，Alice的神经元也会投票。这有两个后果：

* Alice将获得投票奖励（即使她没有手动投票） 。
* 有效地为Bob的神经元赋予了Alice的投票权（可以随时撤销）。 

关于如何设置跟随神经元的分步说明，请参阅操作方法：[设置你的神经元跟随另一个神经元](https://wiki.internetcomputer.org/wiki/How-To:_Set_your_neuron_to_follow_another_neuron)。

以下关于跟随的三个需要注意的重要事项：

### 1. 用户选择他们的神经元应该跟随的主题  

**当用户选择跟随一个或多个神经元时，用户必须选择在哪些主题上跟随他们。** 例如，Alice可以在“网络经济学”主题上跟随Bob的神经元，在“节点管理”主题上跟随Charlie。如果用户在所有可能的主题上都信任一个神经元，那么这个用户可以使用NNS Frontend dapp在两个设置上跟随该神经元：

* “除治理外的所有主题”
* “治理”  

请注意，跟随并**不**保证完全参与。被跟随的神经元有时可能没投票，因此用户在选择要跟随的神经元时需要注意这种风险。

### 2.治理被视为一个特殊主题
如上所述，**治理被视为一个特殊主题，因此用户需要特意选择它作为要跟随的主题。** 这很重要，因为对于NNS奖励，为NNS提案中治理提案投票比参与其他任何话题的投票的影响更大[[1]](https://forum.dfinity.org/t/changes-to-governance-proposals-and-voting-reward-weights-proposal/9172)。要让奖励最大化，手动或跟随神经元来为治理投票很重要。

### 3.用户可以选择多个神经元跟随
如果一个神经元有多个跟随者，它的投票就代表了跟随者们的共识。关于跟随的规则在下文【跟随多个神经元】一节中。

## 可跟随的神经元
用户可以选择任何要跟随的神经元。用户所要做的就是输入神经元ID。为方便起见，NNS  Frontend dapp中列出了一些神经元。  

* **DFINITY 基金会**  
  * 神经元id：27
  * https://dashboard.internetcomputer.org/neuron/27
  * https://dfinity.org  

* **互联网计算机协会**
  * 神经元id：28  
  * https://dashboard.internetcomputer.org/neuron/28
  * https://internetcomputer.org/

* **cycle_dao**
  * 神经元id：5967494994762486275  
  * https://dashboard.internetcomputer.org/neuron/5967494994762486275
  * https://cycledao.xyz/blog

* **ICPMN**
  * 神经元id：4966884161088437903  
  * https://dashboard.internetcomputer.org/neuron/4966884161088437903
  * https://www.ic.community/followee-neuron-for-icp-maximalist-network/  

请注意，可以通过社区参与在NNS Frontend dapp中添加或删除神经元。例如，ICPMN是通过最近的提案添加的：https://dashboard.internetcomputer.org/proposal/38982  


## 跟随多个神经元
当在一个主题上跟随了多个神经元时，如果一半以上的神经元投票拒绝，则神经元也投票拒绝，如果超过一半投接受，则神经元也投接受。如果有足够多的神经元弃权——也就是说既没有一半投反对票，也没有超过一半投赞成票——神经元也将弃权。

例如，假设Alice跟随了四个神经元：神经元1、神经元2、神经元3、神经元4。



|  案子      | 神经元1  |  神经元2  | 神经元3 | 神经元4 | 结果投票 |  原因  |
|  --  |  -- |  --  | -- | -- | -- | -- |  
|简单多数接受 |	接受 |	接受 | 	接受	| 拒绝 |	接受 |	大多数选票被接受 |
| 简单多数拒绝 |	接受 |	拒绝	| 拒绝 |	拒绝	| 拒绝	| 大多数投票被拒绝 |
| 平局 |	接受	| 接受	| 拒绝	| 拒绝	| 拒绝	| 默认结果是拒绝，所以需要超过半数的接受。 |  
| 简单多数弃权 | 弃权	| 弃权	| 弃权	| 接受	| 弃权	| 需要至少一半的神经元投票 | 
| 简单多数弃权 |	弃权	| 弃权	| 弃权	| 拒绝	| 弃权	| 需要至少一半的神经元投票 |

## 选择溶解延迟
对于那些投票的神经元，NNS奖励的日常分配与神经元的溶解延迟年龄成正比。年龄自然而然地随着时间而来，但溶解延迟是可以配置的。

溶解延迟越长，奖励比例越高。要根据溶解延迟估算APY，请参阅计算器：[奖励估算](https://dashboard.internetcomputer.org/governance)。

## 另请参阅：
* [ICP代币](ICP代币.md)
* [管理持有的ICP](管理持有的ICP.md)
* [质押、投票和奖励](https://wiki.internetcomputer.org/wiki/Staking,_voting_and_rewards)
* [互联网计算机治理](https://wiki.internetcomputer.org/wiki/Governance_of_the_Internet_Computer)
* [网络神经系统](https://wiki.internetcomputer.org/wiki/Network_Nervous_System)
* [治理提案和投票奖励权重的变化（提案）](https://forum.dfinity.org/t/changes-to-governance-proposals-and-voting-reward-weights-proposal/9172)  
* [社区主导的互联网计算机治理](https://medium.com/dfinity/the-community-led-governance-of-the-internet-computer-b863cd2975ba)  
      1.  https://forum.dfinity.org/t/changes-to-governance-proposals-and-voting-reward-weights-proposal/9172
