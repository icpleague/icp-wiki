# 操作方法：创建NNS议案与提案  

本文介绍了通过使用一些命令行工具和自托管神经元来提交 NNS议案与提案的方法。

## 1 背景
为了准确理解正在发生的事情，有几点需要强调：

### 1.1 只有神经元可以提交NNS提案
具有至少一个ICP和6个月溶解延迟的神经元才可以提交NNS提案。所以，第一步是创建这样一个神经元。

### 1.2 NNS治理容器接受议案提案
治理容器与其他容器一样，有一个 Candid 文件，可以接受消息等......本文介绍的方法是，你用本地计算机向治理容器发送消息（代表一个神经元签名），这其中包含一个议案提案。（motion proposal不确定到底该怎么翻译）

## 2 一次性设置
### 2.1 安装工具
#### 2.1.1 安装dfx
* dfx是容器SDK，它用于将消息从您的计算机发送到 NNS
* [smartcontracts.org](https://smartcontracts.org/)   

    `$ dfx [OPTIONS] <SUBCOMMAND> ` 

#### 2.1.2 安装keysmith  
* keysmith 将用于为IC生成私钥/公钥对  
* https://github.com/dfinity/keysmith 
* 本文假设你通过运行以下代码在本地计算机上执行quill

   ` $ keysmith [OPTIONS] <SUBCOMMAND>   `


#### 2.1.3 安装quill  
* quill是一个极简主义的“治理工具包”。它是用于制作& 向NNS发送消息以及管理神经元的包装器。
* https://github.com/dfinity/quill 
* 本文假设你通过运行以下代码在本地计算机上执行quill： 

    `$ target/release/quill [OPTIONS] <SUBCOMMAND>  `

### 2.2 通过命令行工具创建神经元
#### 2.2.1 创建<kbd>private.pem</kbd>（私钥/公钥对）和账本<kbd>account id</kbd>

在开始之前，他们需要一个私钥/公钥对。

    // Create seed phrase
    $ keysmith generate -o seed.txt

    //Create private.pem
    $ keysmith private-key -o private.pem

    //Derive Ledger account from private key
    $ keysmith account -i 0

完成后，你的 <kbd>account id</kbd> 应该看起来像这样 <kbd>612ec300g9ec990da900d6ec45919e7d5dbb9fa0dd8e69c54d374df93aa28d57</kbd>.

#### 2.2.2 将这个私钥/公钥对链接到 <kbd>dfx</kbd> 以便你将其用作“身份”
在这种情况下，新身份被称为“提案”

    $ dfx identity import proposals private.pem    

* 如果你在终端中看到“创建身份：提案”，这意味着它有效
* 关于dfx身份的进一步阅读：[dfx 身份](https://smartcontracts.org/docs/developers-guide/cli-reference/dfx-identity.html)  

#### 2.2.3 将ICP发送到步骤2.2.1生成的 <kbd>account id</kbd>  

你应该发送至少1.001 以获得足够的 ICP 来创建神经元并支付账本交易费用。  

要将 ICP 发送到帐户，你只需将 <kbd>account id</kbd> 输入到你选择的钱包中。

#### 2.2.4 现在账户有了所需的ICP，生成一个神经元  

注意：本节假定您已正确安装了 *quill*。

    // Craft a message to "stake a the neuron by choosing a 8-character $NAME and an $AMOUNT to stake"
    $ target/release/quill --pem-file private.pem neuron-stake --name $NAME --amount $AMOUNT > message.json

    //Send the message crafted above.
    $ target/release/quill send message.json




* 您应该会看到一条带有神经元 ID 的消息
* 如果成功，响应将返回 <kbd>neuron ID: 9_218_890_096_040_352_708</kbd>。这意味着神经元ID是 <kbd>9218890096040352708</kbd>。    


#### 2.2.5 增加神经元溶解到至少六个月
* 时间在 NNS 中以秒为单位
* 以秒计的一年：31557600 秒    


` 


    // Craft message to increase dissolve delay of neuron to 1 year
    $ target/release/quill --pem-file private.pem neuron-manage 9218890096040352708 --additional-dissolve-delay-seconds 31557600 > message.json

    //send message created above to the NNS
    $ target/release/quill send message.json



## 3 如何发送提案

在本节，我们将尝试创建一个与此类似的提案：https://dashboard.internetcomputer.org/proposal/42626 

### 3.1 在 Markdown 中制作提案
IC Dashboard 和 NNS frontend dapp 都渲染了 <kbd>summary</kbd> 字段的 markdown。建议使用标准markdown来写提案。

NNS 提案的markdown示例： 

    ## Objective

    Service nervous systems (SNSs) are algorithmic DAOs that allow developers to create decentralized, token-based governance systems for their dapps. The proposed governance canister design is similar to the  governance canister of the Network Nervous System (NNS) but simpler and more flexible, allowing each SNS community to choose the configurations according to their needs. This design is also presented and discussed in this forum: https://forum.dfinity.org/t/open-governance-canister-for-sns-design-proposal/10224 .

    ## Background

    ### Relation to the original SNS design & overall approach
    DFINITY Foundation presented a first proposed [SNS design](https://www.youtube.com/watch?v=L4443aaAP5A) in October 2021. 

    ## Community conversation & Timeline
    The NNS team is ready to work on this feature!
    To get the design approved by the community, we followed the following schedule:

    * Jan 11-18th: Design discussion on the forum thread
    * Jan 18th: Community conversation about the topic
    * Jan 20th: Developer discussion on Discord
    * today: motion proposal submission proposing the above design

    ## What we are asking the community:

    * Vote accept or reject on NNS Motion
    * Participate in technical discussions as the motion moves forward


### 3.2通过dfx发送提案  
发送NNS提案的结构示例：

请注意，**rrkah-fqaaa-aaaaa-aaaaq-cai**是 NNS上治理容器的ID，因此这个命令正在向NNS的治理容器的**manage_neuron**方法发送消息。  

    dfx --identity proposals canister --network ic --no-wallet call rrkah-fqaaa-aaaaa-aaaaq-cai manage_neuron '(record {id = null; command=opt variant {MakeProposal=record {url=""; title="$TITLE";action=opt variant {Motion=record {motion_text="$MOTION_TEXT"}}; summary="

    $SUMMARY

    "}}; neuron_id_or_subaccount=opt variant {NeuronId=record {id=$NEURON_ID:nat64}}})'

用<kbd>$TITLE</kbd>，<kbd>$MOTION_TEXT</kbd>，<kbd>$SUMMARY</kbd> 以及 <kbd>$NEURON_ID</kbd> 填写的NNS提案范例：

    dfx --identity proposals canister --network ic --no-wallet call rrkah-fqaaa-aaaaa-aaaaq-cai manage_neuron '(record {id = null; command=opt variant {MakeProposal=record {url=""; title="Open Governance canister for SNS | Design proposal";action=opt variant {Motion=record {motion_text="Present design proposal for Open Governance canister"}}; summary="

    ## Objective

    Service nervous systems (SNSs) are algorithmic DAOs that allow developers to create decentralized, token-based governance systems for their dapps. The proposed governance canister design is similar to the  governance canister of the Network Nervous System (NNS) but simpler and more flexible, allowing each SNS community to choose the configurations according to their needs. This design is also presented and discussed in this forum: https://forum.dfinity.org/t/open-governance-canister-for-sns-design-proposal/10224 .

    ## Background

    ### Relation to the original SNS design & overall approach
    DFINITY Foundation presented a first proposed [SNS design](https://www.youtube.com/watch?v=L4443aaAP5A) in October 2021. 

    ## Community conversation & Timeline
    The NNS team is ready to work on this feature!
    To get the design approved by the community, we followed the following schedule:

    * Jan 11-18th: Design discussion on the forum thread
    * Jan 18th: Community conversation about the topic
    * Jan 20th: Developer discussion on Discord
    * today: motion proposal submission proposing the above design

    ## What we are asking the community:

    * Vote accept or reject on NNS Motion
    * Participate in technical discussions as the motion moves forward

    "}}; neuron_id_or_subaccount=opt variant {NeuronId=record {id=9218890096040352708:nat64}}})'


### 3.3 检查仪表板以查看提案是否成功 

如果成功，dfx 将返回如下内容：

    (
      record {
        2_171_433_291 = opt variant {
          3_217_030_240 = record {
           2_744_746_248 = opt record { 23_515 = 42_626 : nat64 };
          }
        };
      },
    )


其中**42_626**或<kbd>42626</kbd>是提案的 ID。你的提案将具有不同的ID。

你可以在此处查看提案：https://dashboard.internetcomputer.org/proposal/42626 

## 4 提案的最佳实践
### 4.1 撰写提案
该提案接受任何自由格式的文本。下面是一个推荐的起始模板，以供所有准备编写提案的人使用：

    # 运动项目提案示例

    ## 1. 目标
    文本

    ## 2. 背景
    文本

    ## 3. 为什么这很重要
    文本

    ## 4. 优点
    文本

    ## 5. 缺点
    文本

    ## 6. 关键里程碑（如果有）
    文本

    ## 7. 讨论的领导者（如果有）
    爱丽丝、鲍勃等……

    ## 8. 安全问题（如果有）
    文本

    ## 11. 我们向社区提出的问题

    *查看评论，提出问题，提供反馈

    *投票接受或拒绝NNS提案

    开发者论坛：https://forum.dfinity.org/t/long-term-rd-tokenomics-proposal/9392/3  

### 4.2 传达提案
提案生效后，将开放4天的投票，如果有很多选票竞争，截止日期将再自动延长4天。

提案通常需要大量的沟通和推广（就像在任何组织中一样）以确保有足够的人投票支持。提案在提交“之前”就被宣传是很常见的，这样它的目标选民才会注意到这个提案。

## 5 另请参阅
* [网络神经系统]
* [质押和投票和奖励]()
* [互联网计算机治理]()
* [ICP代币](ICP代币.md)