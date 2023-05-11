---
title: "免信任协议优于信任协议"
date: 2023-05-11T17:48:19+08:00
updated: 2023-05-11T17:48:19+08:00
taxonomies:
  tags: []
extra:
  source: https://subconscious.substack.com/p/trustless-protocols-are-better-than
  hostname: subconscious.substack.com
  author: Gordon Brander
  original_title: "Trustless protocols are better than trustful ones"
  original_lang: zh
---

本文讨论了自我主权密钥和无信任协议的重要性，以实现去中心化、用户所有权和可信退出。文章指出，无信任协议优于信任协议，即使您将密钥保管放在最上面，但使用非托管密钥恢复的无信任是最好的。文章还探讨了可信协议和无信任协议之间的显着差异，以及大多数互联网建立在可信协议之上的原因。

文章要点:
1. 自我主权密钥和无信任协议是实现去中心化、用户所有权和可信退出的关键。
2. 无信任协议优于信任协议，即使您将密钥保管放在最上面，但使用非托管密钥恢复的无信任是最好的。
3. 可信协议和无信任协议之间存在显着差异，最重要的是，无信任协议支持无信任和有信任的使用。
4. 大多数互联网建立在可信协议之上，这导致中心化和锁定很常见。
5. 无信任身份验证是一种不同的方法，它不需要权威机构来授权，而是使用普通的加密密钥。

Keywords: 自我主权密钥、无信任协议、可信协议、去中心化、用户所有权、可信退出。

---

I’ve become pretty convinced that self-sovereign keys and trustless protocols are critical if you want to achieve decentralization, user ownership, or [credible exit](https://subconscious.substack.com/p/credible-exit).  

我已经非常相信，如果你想实现去中心化、用户所有权或可信退出，自我主权密钥和无信任协议是至关重要的。

-   Self-sovereign is just a fancy way of saying “it belongs to you”. Self-sovereign keys are keys that live on your device, usually in something like [Secure Enclave](https://support.apple.com/guide/security/secure-enclave-sec59b0b31ff/web).  
    
    自主权只是说“它属于你”的一种奇特方式。自主权密钥是存在于您设备上的密钥，通常位于 Secure Enclave 之类的东西中。
    
-   Trustless means “it works all by itself”. You don’t need permission from an authority for the protocol to work.  
    
    无信任意味着“它自己工作”。您不需要权威机构的许可即可使协议生效。
    

When I talk about this stuff, I am often met with a reasonable objection: people forget their passwords and lose their keys all the time!  

当我谈论这些东西时，我经常会遇到一个合理的反对意见：人们总是忘记密码并丢失他们的钥匙！  

They might need an authority to recover their account. So, I want to embrace this point, and respond with three claims:  

他们可能需要授权才能恢复他们的帐户。所以，我想接受这一点，并以三点回应：

1.  Trustless protocols are better than trustful ones  
    
    免信任协议优于信任协议
    
2.  Even when you layer key custody on top  
    
    即使您将密钥保管放在最上面
    
3.  But trustless with non-custodial key recovery is best of all  
    
    但是使用非托管密钥恢复的无信任是最好的
    

This might seem contradictory, but there are significant differences between a trustful protocol and a trustless one with custody.  

这可能看起来自相矛盾，但可信协议和有监管的无信任协议之间存在显着差异。  

The most important is that trustless protocols support both trustless and trustful use.  

最重要的是，无信任协议支持无信任和有信任的使用。

Most of the internet runs on trustful protocols. Any time you “log in” to an app using a username and password, you’re using a trustful protocol.  

大多数互联网都运行在可信赖的协议上。任何时候您使用用户名和密码“登录”到应用程序时，您都在使用可信协议。  

Under the hood, you’re asking an authority, such as Facebook, to authorize you to use a service. They own your account, you just access it.  

在幕后，您是在请求权威机构（例如 Facebook）授权您使用某项服务。他们拥有您的帐户，您只需访问它。  

Trustful protocols are trustful because you trust the authority to own your stuff.  

可信协议是可信的，因为你相信拥有你的东西的权力。

It’s reasonable to expect that when you create something, you should own it. But trustful protocols violate this expectation.  

The authority who manages your account ultimately owns your stuff, because they can revoke your access to it. This is a chokepoint that gives authorities [strong leverage for centralization and lock-in](https://subconscious.substack.com/p/aggregators-arent-open-ended).  

有理由期望当你创造了某样东西时，你应该拥有它。但是可信协议违背了这种期望。管理您帐户的权威最终拥有您的东西，因为他们可以撤销您对它的访问权限。这是一个瓶颈，为当局提供了强大的集权和锁定杠杆。

It’s also reasonable to expect that a private message is private, and there won’t be any eavesdroppers listening in. But trustful protocols violate this expectation as well.  

期望私人消息是私密的，并且不会有任何窃听者窃听也是合理的。但是可信协议也违反了这种期望。  

Any time you use a trustful protocol to communicate with a friend, there are three people in the chat: you, your friend, and the authority who controls your accounts.  

任何时候你使用可信协议与朋友交流时，聊天中都会有三个人：你、你的朋友和控制你账户的权威。

So why did most of the internet get built on top of trustful protocols?  

那么，为什么大多数互联网都建立在可信协议之上呢？

-   Partly for practical reasons. People need help recovering their accounts, from time to time. People lose passwords. That’s normal. An authority can help with that.  
    
    部分是出于实际原因。人们不时需要帮助来恢复他们的帐户。人们丢失密码。这是正常的。权威机构可以提供帮助。
    
-   Partly down to chance. In the beginning, the web didn’t have auth, so websites rolled their own, [resulting in the fundamentally feudal web we have today](https://subconscious.substack.com/i/41480831/the-landscape-of-tech-is-essentially-feudal).  
    
    部分取决于机会。一开始，网络没有授权，所以网站自行推出，导致我们今天拥有的基本上是封建的网络。
    

Either way, the bulk of the internet is built around trustful protocols. Very little of what we do online is actually private, very little actually belongs to us. [Centralization and lock-in are common](https://subconscious.substack.com/p/web2-has-a-bad-emperor-problem).  

无论哪种方式，大部分互联网都是围绕可信协议构建的。我们在网上所做的事情实际上很少是私人的，实际上属于我们的也很少。中心化和锁定很常见。

This has lead some decentralized projects to try a different approach: trustless authentication.  

这导致一些去中心化项目尝试了一种不同的方法：无信任身份验证。

When you use a trustless protocol, you don’t need an authority to authorize you. You can authorize yourself. How? By using [plain old cryptographic keys](https://subconscious.substack.com/i/114076486/sign-everything) at the protocol layer. No login, no password. Just keys.  

当您使用免信任协议时，您不需要授权给您。你可以给自己授权。如何？通过在协议层使用普通的旧加密密钥。没有登录名，没有密码。只是钥匙。

Crypto wallets are one example of a trustless protocol.  

加密钱包是一种无需信任的协议示例。  

Each secure wallet is just a keypair—a public key you share with others, and a private key that gives you access to move funds.  

每个安全钱包只是一个密钥对——一个您与他人共享的公钥，以及一个让您可以转移资金的私钥。

Note that trustless authentication has nothing to do with blockchains per se. This is just ordinary [public key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) we’re talking about. Using public keys for authentication has been around since [PGP](https://en.wikipedia.org/wiki/Pretty_Good_Privacy). Yet, for whatever reason, it took crypto to push the idea into the mainstream.  

请注意，无信任身份验证与区块链本身无关。这只是我们正在谈论的普通公钥密码术。自 PGP 以来就已经使用公钥进行身份验证。然而，无论出于何种原因，加密技术将这一想法推向了主流。

> One of the lessons from the theory of natural selection is that a degree of isolation can be a great help to a new strategy in gaining a foothold.  
> 
> 自然选择理论的一个教训是，一定程度的隔离可以极大地帮助新战略获得立足点。  
> 
> _(Cosma Shalizi, 1999. "What can emergence tell us about today's Eastern Europe?")  
> 
> （Cosma Shalizi，1999 年。“关于今天的东欧，涌现能告诉我们什么？”）_

Just use keys! While it may have crawled out of the hot primordial soup of crypto, this little idea has legs. It’s a simple and good idea, and is being [exapted to existing infrastructure](https://subconscious.substack.com/p/exapt-existing-infrastructure) in new web [standards proposals](https://w3c-ccg.github.io/universal-wallet-interop-spec/) and [drafts](https://w3c-ccg.github.io/did-method-key/).  

只需使用钥匙！虽然它可能是从加密货币的原始热汤中爬出来的，但这个小想法还是有道理的。这是一个简单而好的想法，并且正在扩展到新的 Web 标准提案和草案中的现有基础设施。

When your protocol is designed around self-sovereign keys, it becomes trustless, and this brings important benefits:  

当您的协议围绕自主权密钥设计时，它就变得无需信任，这带来了重要的好处：

-   You don’t need to ask an authority to access your stuff. Keys are [self-certifying](https://jaygraber.medium.com/web3-is-self-certifying-9dad77fd8d81).  
    
    您无需请求授权即可访问您的资料。密钥是自我认证的。
    
-   You can communicate privately person-to-person, without a man-in-the-middle.  
    
    您可以在没有中间人的情况下进行私下的人对人交流。
    
-   There is no central authority, so there is no auth chokepoint to leverage for lock-in.  
    
    没有中央权威，因此没有用于锁定的身份验证阻塞点。
    

Crypto people have a slogan for this: “not your keys not your coins”, and this is true, but it’s important to note that it also cuts both ways. We’ve all seen the stories of [crypto people misplacing their keys and losing millions](https://www.nytimes.com/2021/01/12/technology/bitcoin-passwords-wallets-fortunes.html). So, ownership is important, but it also comes with risks. If you lose your keys, no one can help you. That’s not great.  

加密货币人士对此有一句口号：“不是你的钥匙，不是你的代币”，这是事实，但重要的是要注意它也是双向的。我们都看过加密货币人士将密钥放错地方并损失数百万美元的故事。因此，所有权很重要，但也伴随着风险。如果您丢失了钥匙，没有人可以帮助您。那不是很好。

Luckily we have a way to deal with this IRL. We create a spare key.  

幸运的是，我们有办法处理这个 IRL。我们创建一个备用密钥。

Why would you do this? For the same reason you might give a friend a spare key to your apartment. If you lose your key, you can always call your friend to let you in.  

你为什么要这样做？出于同样的原因，您可能会给朋友一把您公寓的备用钥匙。如果您丢失了钥匙，您可以随时打电话给您的朋友让您进入。

Funnily enough, [custody is how most people use crypto](https://www.coindesk.com/learn/what-is-crypto-custody/). There are a few ways to do this. You can put a spare key in a [hardware wallet](https://shop.ledger.com/pages/ledger-stax), for example. But the most common is to use a service. A service like Coinbase acts as a custodian for your keys. You log in to Coinbase, they keep your spare.  

有趣的是，保管是大多数人使用加密货币的方式。有几种方法可以做到这一点。例如，您可以将备用钥匙放入硬件钱包中。但最常见的是使用服务。像 Coinbase 这样的服务充当你的密钥的保管人。你登录到 Coinbase，他们保留你的备用。

So wait, now we’re all the way back to trusting a third party, right? Well, yes, but…  

所以等等，现在我们又回到了信任第三方的状态，对吧？嗯，是的，但是……

There are significant strategic differences between the two.  

两者之间存在显着的战略差异。

**Trustless allows for both trustful and trustless use**. You can always implement key custody on top of user-owned keys. If you want key custody, you can have key custody. If you want a [cold wallet](https://www.ledger.com/academy/hardware-wallets-and-cold-wallets-whats-the-difference), you can have a cold wallet. Trustful protocols bake assumptions about authority directly into the infrastructure. Trustless protocols give you the choice.  

Trustless 允许信任和不信任的使用。您始终可以在用户拥有的密钥之上实施密钥保管。如果你想要钥匙保管，你可以拥有钥匙保管。如果你想要一个冷钱包，你可以有一个冷钱包。可信协议将关于权威的假设直接融入基础设施。无信任协议为您提供选择。

**You can choose your custodian**. Does Facebook Connect let you choose a different custodian? No. You’re locked in. Trustless protocols are different. Keys are keys. You get to choose who holds them… or doesn’t.  

The protocol doesn’t care.  

您可以选择您的托管人。 Facebook Connect 是否允许您选择不同的保管人？不，你被锁定了。去信任协议是不同的。钥匙就是钥匙。您可以选择谁持有它们……或不持有。协议不在乎。

**Keys are a lego dot**. Products are like lego sets. Protocols are like lego. Imagine if lego changed the shape of the dots. You would have to throw out all your old pieces!  

Protocol interfaces can’t change without breaking the ecosystem, so, it’s important to find the right “lego dot”.  

钥匙是乐高积木点。产品就像乐高套装。协议就像乐高积木。想象一下，如果乐高改变了圆点的形状。你将不得不扔掉你所有的旧作品！不破坏生态系统就无法改变协议接口，因此，找到合适的“乐高点”很重要。

A protocol interface should be both fundamental and universal. Something that can be used to build many different things. A dot. When you find the right dot, it allows for [layering, shearing](https://subconscious.substack.com/p/layered-protocols), and [open-ended evolution](https://subconscious.substack.com/p/open-ended-tools-for-infinite-games).  

协议接口应该是基础的和通用的。可以用来构建许多不同事物的东西。一个点。当您找到合适的点时，它允许分层、剪切和开放式演变。

> The goal of all theory is to make the basic elements as simple as possible without having to surrender the adequate representation of experience. _(Einstein)_  
> 
> 所有理论的目标都是使基本要素尽可能简单，而不必放弃对经验的充分表征。 （爱因斯坦）

Keys are the lego dot of authorization and authentication. They are the basic element of cryptography, [the simplest thing that could possibly work](https://subconscious.substack.com/i/70590299/do-simple-things). You need keys to [sign everything](https://subconscious.substack.com/p/llms-break-the-internet-signing-everything), you need keys to implement end-to-end encryption. Keys are both necessary and sufficient. Just use keys.  

密钥是授权和认证的乐高点。它们是密码学的基本元素，是可能起作用的最简单的东西。你需要密钥来签署一切，你需要密钥来实现端到端加密。密钥既是必要的也是充分的。只需使用键。

So trustless protocols enable trustless use, through cold wallets, or trustful use, through custody. But they can also enable a third thing: noncustodial key recovery.  

因此，无需信任的协议可以通过冷钱包实现无需信任的使用，或通过托管实现信任使用。但它们还可以实现第三件事：非托管密钥恢复。

Noncustodial key recovery has not been widely productized, because until recently, there weren’t widely deployed products that just used keys. That’s starting to change.  

非托管密钥恢复尚未广泛产品化，因为直到最近，还没有广泛部署的仅使用密钥的产品。这开始改变了。  

Some wallets offer new forms of recovery that don’t require trusting an authority. These include:  

一些钱包提供了不需要信任权威机构的新形式的恢复。这些包括：

-   **Social key recovery** [breaks your private key into pieces](https://en.wikipedia.org/wiki/Shamir%27s_secret_sharing). You can give these pieces to your friends as a backup. Alone, each piece does nothing, but combine enough of them together and you get your private key.  
    
    So, if you lose your key, you just hit up your friends, and voilà.  
    
    社会密钥恢复将您的私钥分解成碎片。您可以将这些作品作为备份送给您的朋友。单独使用时，每一部分什么都不做，但是将足够多的部分组合在一起，您就可以得到您的私钥。因此，如果您丢失了钥匙，您只需联系您的朋友，瞧瞧。
    
-   **ZK-based key recovery**. Further out, we can see [schemes to enable noncustodial key recovery](https://holonym.io/whitepaper.pdf) through [ZK-SNARKS](https://arxiv.org/pdf/1906.07221.pdf), a clever mathy way to prove that something is true, without revealing any other information.  
    
    This is new cryptographic magic that I won’t pretend to understand, but there are lots of smart people working on it, and my bet is that they will make a breakthrough.  
    
    基于 ZK 的密钥恢复。更进一步，我们可以看到通过 ZK-SNARKS 启用非托管密钥恢复的方案，这是一种聪明的数学方法，可以在不泄露任何其他信息的情况下证明某事是真实的。这是一种新的密码学魔法，我不会假装理解，但有很多聪明人正在研究它，我敢打赌他们会取得突破。
    

Here’s the thing—keys are a fundamental and universal interface, a lego dot.  

事情是这样的——按键是一个基本的通用界面，一个乐高圆点。  

When you build around a universal interface, you can swap out the old thing for the future better thing when it becomes available.  

当你围绕一个通用接口构建时，你可以在旧的东西可用时换成未来更好的东西。  

Take off the custodial brick, put on the noncustodial ZK magic brick. The lego dot stays the same, so you don’t have to throw out the pieces.  

把禁锢砖拿下来，换上非禁锢ZK魔砖。乐高圆点保持不变，因此您不必扔掉这些零件。

> A very little key will open a very heavy door. _(Charles Dickens)_  
> 
> 一把很小的钥匙就能打开一扇很重的门。 （查尔斯·狄更斯）

Just use keys. 只需使用键。
