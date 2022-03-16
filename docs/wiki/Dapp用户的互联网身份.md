# Dapp 用户的互联网身份

众所周知，用户名和密码一直是个人网络安全的薄弱环节。 为了解决这个问题并为互联网计算机（IC）上的用户提供更高的安全性，互联网身份（II）区块链验证系统被开发出来。 互联网身份使您能够使用您的设备对互联网计算机上的 Dapp 进行身份验证和匿名登录。 任何拥有传统 HSM 设备（例如 YubiKey）或包含 TPM 芯片的移动设备（例如笔记本电脑或手机）的人都可以生成互联网身份并开始在 IC 上使用 Dapp。

## 入门

<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Welcome.png/200px-Welcome.png" align="right" width="200"/>假设您想与互联网计算机上运行的 Dapp 进行交互。 通常情况下，您需要进行身份验证或登录才能访问和使用 Dapp 的功能。 目前，最简单的身份验证方法是使用从互联网身份获得的身份锚。

互联网身份将每个身份锚与唯一的用户编号相关联。 Dapp用户登录不知道这个用户号。 相反，互联网身份为每个用户、每个 Dapp 创建一个化名标识符。 Dapp 可以看到它是之前登录的同一用户，但不知道它是谁，也不知道该用户是否还使用其他 Dapp。

[单击此处](https://www.youtube.com/watch?v=oxEr8UzGeBo)观看互联网身份的演示视频，下面介绍了开始使用您自己的互联网身份的步骤。

开始和生成身份锚的最快方法是直接导航到互联网身份 Dapp：https://identity.ic0.app/ 在这里，您将看到一个提示您输入身份锚的屏幕。 如果您刚刚开始，则需要通过选择**创建互联网身份锚**来创建身份锚。

或者，如果您尝试访问 Dapp，例如 NNS 前端 Dapp，您将看到系统提示您登录。 单击登录按钮时，您将被重定向到互联网身份屏幕（如右图所示），如果有身份锚，您可以登录，如果没有，您可以创建一个新的。

## 创建锚点

<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Ii_anchor_created.png/200px-Ii_anchor_created.png" align="right" width="200"/>当您选择要在 II 主页上创建互联网身份锚点时，您将被引导到一个屏幕，提示您提供要在其上生成锚点的设备的名称，例如 iPhone、笔记本电脑、Yubikey。

输入设备名称后，您的设备将提示您允许“identity.ic0.app”使用专用安全密钥或您正在使用的设备的身份验证方法（如果该选项可用）。 例如，如果您的设备启用了生物识别来解锁它，您可能会看到使用这些作为您的身份验证方法的选项。 您还可以使用解锁计算机的密码或解锁手机的 PIN，具体取决于您使用的设备。

授予访问权限后，您将被重定向获取验证码。 解决此问题后，系统将提示您选择一个帐户登录“identity.ic0.app”。 如果您是第一次注册，您可以选择使用密码（生成并存储在您的设备上）登录，否则您可以选择使用外部安全密钥登录。 之后，您将被重定向到显示您新创建的身份锚的屏幕！ 请注意，在此屏幕上建议记录您的身份锚号码。 这是您需要输入的数字，以对 IC 上运行的 Dapp 进行身份验证。

## 建立恢复方法

创建身份锚点后，您将被定向到允许添加恢复机制的页面，或跳过此步骤。 这里有一个警告，指出如果您的浏览器历史记录被清除，您的身份验证密钥将从该设备中删除。 因此，强烈建议分配多个设备或使用安全密钥或助记词作为恢复机制。 当您选择添加恢复机制时，您有两个选择； 要么生成一个你应该安全存储的助记词，要么使用额外的安全密钥。

### 助记词

<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Ii_setup_recovery.png/200px-Ii_setup_recovery.png" align="right" width="200"/>如果您以前使用过数字钱包，也许您习惯于安全地维护助记词，如果没有，那从现在开始就要好好记住助记词。 选择此选项会生成一个密码安全的助记词，您可以使用它来恢复身份锚。 确保将助记词存储在安全且只有您自己知道的地方，因为知道助记词的任何人都可以完全控制此身份锚。 请注意，助记词中的第一个字符串是身份锚。 您将需要此号码来开始恢复过程。

### 安全密钥
如果您选择不使用助记词作为恢复方法，您可以使用专用安全密钥来恢复身份锚，以防您无法访问授权设备。 此密钥必须不同于您使用给定身份锚主动用于对互联网身份进行身份验证的密钥。 将此密钥保存在安全的地方，并确保它仅供您使用。 如上所述，拥有此安全密钥的任何人都可以完全控制您的身份锚。 您需要知道身份锚才能开始恢复。

### 跳过此步骤

不建议跳过此步骤，除非您确定不需要记住此锚点。

## 添加第二个设备

<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Ii_newdevice.png/200px-Ii_newdevice.png" align="right" width="200"/>出于多种原因，添加第二个设备是一种很好的做法。

- 通常情况下，您需要从多个设备登录 dapp，例如。 从手机到笔记本电脑。
- 添加第二台设备可以更轻松地恢复您的锚或帐户，如果它从一个设备丢失。

添加第二个设备的最直接方法是导航到您要添加的设备上的 https://identity.ic0.app/。 到达那里后，您可以选择“已经有锚**但使用新设备**”选项。 单击此按钮后，您将被定向到一个页面，您可以在其中输入您现有的身份锚点。 输入您的锚号码并单击继续后，系统将提示您允许访问安全密钥或您当前的设备。 选择您的偏好（例如 Yubikey 或指纹扫描），然后您将被引导至显示 url（及其等效二维码）的屏幕。

<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Ii_newdeviceQR.png/200px-Ii_newdeviceQR.png" align="right" width="200"/>要添加新设备，您需要在您首次验证的原始设备上输入 url 或扫描 QR 码。 例如，如果您最初在手机上生成身份锚点，现在尝试将笔记本电脑添加为第二台设备，则应使用手机扫描笔记本电脑上生成的二维码。

使用原始设备扫描 QR 码后，您将被定向到应用程序，您可以在其中确认您正在尝试添加新设备。 确认后，系统会要求您为新设备命名（在上面的示例中，适当的名称是“笔记本电脑”）。 在此之后，两个设备都应该出现在 identity.ic0.app 的锚点管理页面中。

## 身份验证

当您创建了身份锚并添加了设备后，登录 Dapp 是一个简单的过程。 当您导航到支持使用互联网身份进行身份验证的 Dapp 时，只需单击登录按钮即可定向到 II 前端，您可以在其中输入您的锚编号并进行身份验证。

在此之后，您将被定向到要求您授权身份验证的页面。 选择**继续**后，您将完成身份验证过程并被重定向并登录到 Dapp。

## 找回丢失的身份
<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Ii_recover.png/200px-Ii_recover.png" align="right" width="200"/>如果您丢失了锚号码并且无法再访问您的授权设备，您可以使用助记词或初始设置过程中使用的安全密钥恢复丢失的身份。


<img src="https://mywikis-wiki-media.s3.us-central-1.wasabisys.com/internetcomputer/thumb/Ii_seedphrase.png/200px-Ii_seedphrase.png" align="right" width="200"/>要恢复您丢失的身份，首先导航到 https://identity.ic0.app/ 在页面底部选择丢失访问权限以及恢复链接。 在此之后，您将被引导到一个页面，要求输入丢失身份的锚号码。 请注意，助记词的第一个字符串是锚编号，因此您始终可以在那里找到它。 输入您要恢复的身份的锚号后，您将被定向到要求您输入助记词的页面。 复制助记词并单击继续后，您的身份将被恢复。


请注意，互联网身份 Dapp 上的恢复页面是您应该输入助记词的唯一页面。

## 主要特征

### 便于使用

互联网身份为用户提供了一种安全的方式来生成身份锚并对运行在互联网计算机上的应用程序进行身份验证，而无需记住和管理密码。

### 隐私
生成锚点不需要个人识别信息，并且由于互联网身份为不同的应用程序生成不同的化名，因此为用户提供了隐私，因为无法跟踪跨 dapp 的交互。

### 可用性
由于锚点的密钥材料是生成并存储在用户设备上的，因此特定服务或应用程序不会阻碍个人锚点作为身份验证方法的可用性。

## 快速链接
- 有关更多技术概述，请查看 [互联网身份技术概述](互联网身份技术概述.md)页面。
- [互联网身份媒体帖子](https://medium.com/dfinity/internet-identity-the-end-of-usernames-and-passwords-ff45e4861bf7)，概述了互联网身份以及如何开始。
- [Web 身份验证媒体帖子](https://medium.com/dfinity/web-authentication-and-identity-on-the-internet-computer-a9bd5754c547) ，Björn Tackmann 概述了 Web 身份验证的核心思想，并描述了互联网身份是如何形成的。
- [视频演示](https://www.youtube.com/watch?v=oxEr8UzGeBo)展示了互联网身份并展示了如何生成锚点。
- [开发者中心](https://smartcontracts.org/docs/ic-identity-guide/what-is-ic-identity.html)对互联网身份的介绍。

## 常问问题

### 我是否需要使用互联网身份才能使用 IC 上的所有 Dapp？
不，互联网身份是一个可供Dapp开发人员使用的身份验证选项。 开发人员可以选择他们不需要身份验证，或者如果他们确实需要身份验证，他们也可以选择其他解决方案。 互联网身份非常受欢迎，因为身份验证系统很难安全地构建，因此它对开发人员很有帮助，但他们有选择的自由。

例子：

[Motoko Playground](https://m7sm4-2iaaa-aaaab-qabra-cai.raw.ic0.app/)是 IC 上的 Dapp 示例，它不需要互联网身份，而是允许直接匿名使用。

### 如何从互联网身份中获取身份锚？
生成身份锚的唯一地方是访问 https://identity.ic0.app/。

访问 https://smartcontracts.org/docs/ic-identity-guide/auth-how-to.html 可以找到详细说明

### 我真的需要链接另一个设备或保存助记词吗？
尽管没有必要，但为了防止您无法访问特定设备上的身份锚，链接另一个设备或保存助记词确实很有用。 此外，由于您的身份锚可能用于为钱包或 Dapp 生成账户，因此如果您无法访问身份锚，也可能会失去对这些账户的访问权限。

### 如果我丢失了我的设备会怎样？
如果您丢失了设备并想要恢复，您可以单击 https://identity.ic0.app/ 上的“丢失访问权限并希望恢复”链接。

如果您的身份锚仅与一台设备绑定，而您丢失了该设备，您将被锁定。 我们建议您最好为每个身份锚添加多个设备和恢复机制。

### 如何添加更多设备？
如果您想添加其他设备，您可以点击“已经有锚但使用新设备？” 链接在 https://identity.ic0.app/

详细说明可以在这里找到：https://smartcontracts.org/docs/ic-identity-guide/auth-how-to.html#_add_a_device

### 当我进行身份验证时，互联网身份是否会与 dapp 共享我的个人信息？
不会。互联网身份对您使用互联网身份进行身份验证的每个 Dapp 使用不同的主体【principal】（“化名”）。 由于互联网身份为您生成的化名对于每个 Dapp 都不同，因此 Dapp 无法在其领域之外使用它们跟踪您。

### 互联网身份是否支持 Windows Hello？
支持！互联网身份支持通过 Windows Hello 进行身份验证。 如果您的 PC 上设置了 Windows Hello，则互联网身份将让您通过 Windows Hello 进行身份验证。

详细说明可以在这里找到：https://smartcontracts.org/docs/ic-identity-guide/hello-guide.html

### 为什么我无法使用新设备登录？
如果您无法使用现有的身份锚点登录，则可能是该锚点尚未添加到新设备中。 如果是这种情况，只需访问 https://identity.ic0.app/ ，点击“已经有锚但使用新设备？” 链接，添加设备，然后重试。

也可能是设备上未启用人脸 ID 或指纹系统。 确保这些已启用，然后尝试再次登录。

### 有没有办法撤销 Dapp 对我的身份锚的访问？
没有明确的撤销方法，但是对互联网身份的权限委托是有时间限制的，所以会过期。或者，只要关闭浏览器选项卡，委托就消失了。
