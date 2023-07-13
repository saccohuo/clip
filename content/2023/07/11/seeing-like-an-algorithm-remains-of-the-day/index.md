---
title: "像算法一样看待"
date: 2023-07-11T15:34:43+08:00
updated: 2023-07-11T15:34:43+08:00
taxonomies:
  tags: []
extra:
  source: https://www.eugenewei.com/blog/2020/9/18/seeing-like-an-algorithm
  hostname: www.eugenewei.com
  author: 
  original_title: "Seeing Like an Algorithm — Remains of the Day"
  original_lang: zh
---

In my [previous post on TikTok](https://www.eugenewei.com/blog/2020/8/3/tiktok-and-the-sorting-hat) I discussed why its For You Page algorithm is the connective tissue that makes TikTok work. It is the bus on its motherboard that connects and closes all its feedback loops.  

在我之前关于 TikTok 的文章中，我讨论了为什么它的 For You Page 算法是使 TikTok 发挥作用的结缔组织。主板上的总线连接并关闭所有反馈回路。

But in the breathless rush to understand why companies might want to acquire TikTok, should ByteDance be forced to divest itself of the popular short video app, the hype around its algorithm has taken on a bit of exoticization that often characterizes Western analysis of the Chinese tech scene these days.  

但在急于了解为什么公司可能想要收购 TikTok 的过程中，如果字节跳动被迫剥离这款流行的短视频应用程序，围绕其算法的炒作已经带有一点异国情调，这通常是西方对中国科技分析的特征。这几天的场景。I kept holding off on publishing this piece because every day seemed to bring some new development in the possible ban of TikTok in the U.S. And instead of writing any introduction that would become instantly outdated, I'll just leave this sidenote here to say that as of publishing this entry, it seems Oracle will take over the TikTok cloud computing deal while also joining Wal-Mart and some VCs in assuming some ownership stake in TikTok Global.  

我一直推迟发表这篇文章，因为似乎每天都会有关于 TikTok 在美国可能被禁止的新进展。我不想写任何会立即过时的介绍，我只是在这里留下这个旁注，说的是在发布这篇文章后，甲骨文似乎将接管 TikTok 云计算交易，同时加入沃尔玛和一些风险投资公司的行列，持有 TikTok Global 的部分股权。  

But it won't surprise me one bit if we find out even more bizarre details over the next week.  

但如果我们在下周发现更多奇怪的细节，我一点也不会感到惊讶。  

This is the type of deal that I would have thought could only happen in Succession, but even in that satire it would seem hyperbolic. The 2020 Writer's Room is undefeated.  

我原以为这种交易只会发生在《继承之战》中，但即使在那部讽刺作品中，它也显得夸张。 2020年作家室保持不败。

In this post, I want to discuss exactly how the design of TikTok helps its algorithm work as well as it does.  

在这篇文章中，我想具体讨论 TikTok 的设计如何帮助其算法发挥作用。  

Last time I discussed why the FYP algorithm is at the heart of TikTok’s flywheel, but if the algorithm wasn’t effective then the whole feedback loop would collapse.  

上次我讨论了为什么 FYP 算法是 TikTok 飞轮的核心，但如果该算法无效，那么整个反馈循环就会崩溃。  

Understanding how the algorithm achieves its accuracy matters even if you’re not interested in TikTok or the short video space because more and more, companies in all industries will be running up against a competitor whose advantage centers around a machine learning algorithm.  

即使您对 TikTok 或短视频领域不感兴趣，了解算法如何实现其准确性也很重要，因为越来越多的各行业的公司都会遇到以机器学习算法为优势的竞争对手。

What I want to discuss is how TikTok’s design helps its algorithm “see.”  

我想讨论的是TikTok的设计如何帮助其算法“看到”。

___

[Seeing Like a State](https://amzn.to/2FDQEsj) by James C. Scott is one of those books that turns you into one of those Silicon Valley types that use (abuse?) the term legibility.  

詹姆斯·C·斯科特（James C. Scott）的《Seeing Like a State》是其中一本将你变成使用（滥用？）易读性一词的硅谷类型之一的书。  

I first heard about it after reading Venkatesh Rao’s [summary of its main themes](https://www.ribbonfarm.com/2010/07/26/a-big-little-idea-called-legibility/), and that piece remains a good tldr primer on the book if you don’t plan to read the text ([Scott Alexander's review of the book](https://slatestarcodex.com/2017/03/16/book-review-seeing-like-a-state/) is also good though is long enough that it could almost justify its own tldr). However, I recommend that you do.  

我第一次听说这本书是在阅读了 Venkatesh Rao 对其主题的总结之后，如果你不打算阅读正文，那篇文章仍然是这本书的一个很好的 tldr 入门读物（斯科特·亚历山大对这本书的评论也很好，尽管足够长）它几乎可以证明自己的 tldr 是合理的）。不过，我建议您这样做。

The subtitle of Scott’s book is “How Certain Schemes to Improve the Human Condition Have Failed.” In particular, Scott dissects a failure state that recurs across a number of domains, in which a governing body like the nation-state turns to what Scott terms high modernism in an effort to increase legibility of whatever it is they are trying to exert control over, whether for the purposes of taxation or conscription or any number of goals.  

斯科特这本书的副标题是“某些改善人类状况的计划是如何失败的”。特别是，斯科特剖析了在多个领域反复出现的失败国家，其中像民族国家这样的管理机构转向斯科特所说的高度现代主义，以努力提高他们试图控制的任何事物的可读性，无论是出于税收或征兵的目的还是任何数量的目标。  

In doing so, they impose a false sense of order on a reality more complex than they can imagine.  

在这样做的过程中，他们对比他们想象的更复杂的现实强加了一种错误的秩序感。It would really be fascinating to hear from Scott on the case of modern China, under CCP rule, with modern technology for surveillance, and whether he thinks they will prove or violate his thesis in the fullness of time.  

听到斯科特讲述在中共统治下的现代中国的情况，以及他是否认为他们会在时间成熟时证明或违反他的论点，这真的很有趣。

It’s a book that raises one’s awareness of all sorts of examples of unintended consequences in day-to-day life.  

这本书提高了人们对日常生活中各种意外后果例子的认识。  

We all could use a healthier does of humility when we are too flush with great man hubris. The world is richer and more complicated than we give it credit for.  

当我们过于狂妄自大时，我们都可以采取更健康的谦逊态度。世界比我们想象的更丰富、更复杂。

As an example, much of what Scott discusses has relevance to some of the hubris of our modern social networking giants.  

举个例子，斯科特讨论的大部分内容都与我们现代社交网络巨头的一些傲慢有关。  

These dominant apps are designed to increase legibility of their user bases for, among other things, driving engagement, preventing churn, and ultimately, serving targeted advertisements.  

这些占主导地位的应用程序旨在提高用户群的易读性，除其他外，还可以提高用户参与度、防止用户流失，并最终提供有针对性的广告。  

That, in turn, has led their parent companies into a thicket of problems which they’re grappling with constantly now.  

这反过来又导致他们的母公司陷入了他们现在不断努力解决的一系列问题。

But that is a topic for another post, another day.  

但这是另一篇文章的主题，改天再讲。  

Whereas Scott focuses in on how the nation-state uses simplifying abstractions to “see” its citizens at a synoptic level, I want to discuss how TikTok’s application design allows its algorithm to “see” all the detail it needs to perform its matchmaking job efficiently and accurately.  

Scott 重点关注民族国家如何使用简化的抽象概念在概要层面“查看”其公民，而我想讨论 TikTok 的应用程序设计如何允许其算法“查看”高效执行匹配工作所需的所有细节并准确地。  

If Seeing Like a State is about a common failure state, this post is about a new model for getting the most leverage from machine learning algorithms in the design of applications and services.  

如果“Seeing Like a State”是关于一种常见的故障状态，那么这篇文章是关于一种在应用程序和服务设计中充分利用机器学习算法的新模型。I’m aware of the irony that the controversy around TikTok was the potential of user data being accessed by the CCP, or being “seen by that state.” Or that one of the sticking points of this new Cold War is the Chinese Firewall, which selects what the citizens of China “see.” And which most U.S. tech companies sit outside of, looking in.  

我知道讽刺的是，围绕 TikTok 的争议在于用户数据可能被中共访问，或者“被那个国家看到”。或者说，这场新冷战的症结之一是中国防火墙，它选择了中国公民“看到”的内容。大多数美国科技公司都坐在外面，向内看。

___

In recent years, one of the realizations in machine learning, at least to an outsider to the subject like myself, is just how much progress was possible just by increasing the volume of training data by several orders of magnitude.  

近年来，至少对于像我这样的外行来说，机器学习的一个认识是，只要将训练数据量增加几个数量级，就可以取得多大的进步。  

That is, even if the algorithms themselves aren’t that different than they were a few years ago, just by training them on a much larger datasets, AI researchers have achieved breakthroughs like [GPT-3](https://openai.com/blog/openai-api/) (which temporarily gave tech Twitter a tantric orgasm).  

也就是说，即使算法本身与几年前没有太大不同，只要在更大的数据集上进行训练，人工智能研究人员就已经取得了像 GPT-3 这样的突破（它暂时给科技 Twitter 带来了密宗高潮） 。

When people say that TikTok’s algorithms are key to its success, many picture some magical block of code as being the secret sauce of the company.  

当人们说 TikTok 的算法是其成功的关键时，许多人将一些神奇的代码块视为该公司的秘密武器。  

The contemporary postmodernist Russian writer Viktor Pelevin has said that the protagonist of all modern cinema is a briefcase full of money.  

俄罗斯当代后现代主义作家维克托·佩莱文曾说过，所有现代电影的主角都是一个装满金钱的公文包。  

From the briefcase of radioactive material (I think that’s what it was?) in [Kiss Me Deadly](https://amzn.to/35NQsS8) to the briefcase of similarly glowing who knows what (Marcellus Wallace’s soul?) in [Pulp Fiction](https://amzn.to/2ZN7IDr), from the Genesis equation in [The Formula](https://amzn.to/3kzc2OJ) to the secret financial process in David Mamet’s [The Spanish Prisoner](https://amzn.to/35I0YKS), we’ve long been obsessed in cinema with the magical McGuffin.  

从《致命之吻》中装有放射性物质的公文包（我想这就是它？），到《低俗小说》中同样发光的谁知道什么（马塞勒斯·华莱士的灵魂？）的公文包，从《公式》中的创世方程到秘密的财务流程在大卫·马梅特的《西班牙囚徒》中，我们长期以来一直对神奇的麦高芬着迷。  

In recent weeks, discussion of TikTok’s algorithm has elevated it into something similar, akin to one of those mystical archaeological artifacts in one of the Indiana Jones films, like the Ark of the Covenant, the Holy Grail, or the lingam Shivling.  

最近几周，对 TikTok 算法的讨论已将其提升为类似的东西，类似于《夺宝奇兵》电影中的神秘考古文物之一，比如《约柜》、《圣杯》或《lingam Shivling》。

But most experts in the field doubt that TikTok has made some hitherto unknown advance in machine learning recommendations algorithms. In fact, most of them would say that TikTok is likely building off of the same standard approaches to the problem that others are.  

但该领域的大多数专家怀疑 TikTok 在机器学习推荐算法方面取得了一些迄今为止未知的进步。事实上，他们中的大多数人会说，TikTok 很可能采用与其他公司相同的标准方法来解决问题。

But recall that the effectiveness of a machine learning algorithm isn’t a function of the algorithm alone but of the algorithm after _trained on some dataset_. GPT-3 may not be novel, but trained on an enormous volume of data, and with a massive number of parameters, its output is often astonishing.  

但请记住，机器学习算法的有效性不仅仅是算法本身的函数，而是在某些数据集上训练后的算法的函数。 GPT-3可能并不新颖，但经过海量数据和大量参数的训练，其输出往往令人惊讶。

Likewise, the TikTok FYP algorithm, trained on its dataset, is remarkably accurate and efficient at matching videos with those who will find them entertaining (and, just as importantly, at suppressing the distribution of videos to those who won’t find them entertaining).  

同样，在其数据集上训练的 TikTok FYP 算法在将视频与那些觉得它们有趣的人匹配方面非常准确和高效（同样重要的是，在抑制视频向那些不觉得它们有趣的人分发方面） 。

For some domains, like text, good training data is readily available in large volumes.  

对于某些领域（例如文本），可以轻松获得大量良好的训练数据。  

For example, to train an AI model like GPT-3, you can turn to the vast corpus of text already available on the internet, in books, and so on.  

例如，要训练像 GPT-3 这样的 AI 模型，您可以求助于互联网、书籍等中已有的大量文本语料库。  

If you want to train a visual AI, you can turn to the vast supply of photos online and in various databases. The training is still [expensive](https://lambdalabs.com/blog/demystifying-gpt-3/), but at least copious training data is readily at hand.  

如果你想训练视觉人工智能，你可以求助于在线和各种数据库中的大量照片。培训仍然很昂贵，但至少大量的培训数据唾手可得。

But for TikTok (or Douyin, its Chinese clone), who needed an algorithm that would excel at recommending short videos to viewers, no such massive publicly available training dataset existed.  

但对于需要一种擅长向观众推荐短视频的算法的 TikTok（或其中国克隆版抖音）来说，不存在如此庞大的公开训练数据集。  

Where could you find short videos of memes, kids dancing and lip synching, pets looking adorable, influencers pushing brands, soldiers running through obstacle courses, kids impersonating brands, and on and on?  

您在哪里可以找到模因、孩子们跳舞和假唱、可爱的宠物、推动品牌的影响者、士兵跑过障碍训练场、孩子们模仿品牌等等的短视频？  

Even if you had such videos, where could you find comparable data on how the general population felt about such videos?  

即使您有这样的视频，您在哪里可以找到有关普通大众对此类视频的感受的可比数据？  

Outside of Musical.ly’s dataset, which consisted mostly of teen girls in the U.S. lip synching to each other, such data didn’t exist.  

Musical.ly 的数据集主要由美国少女对口型表演组成，而在 Musical.ly 的数据集之外，此类数据并不存在。

In a unique sort of chicken and egg problem, the very types of video that TikTok’s algorithm needed to train on weren’t easy to create without the app’s camera tools and filters, licensed music clips, etc.  

在一种独特的先有鸡还是先有蛋的问题中，如果没有应用程序的相机工具和滤镜、授权的音乐剪辑等，TikTok 算法需要训练的视频类型并不容易创建。

This, then, is the magic of the design of TikTok: it is a closed loop of feedback which inspires and enables the creation and viewing of videos on which its algorithm can be trained.  

这就是 TikTok 设计的魔力：它是一个反馈闭环，可以激发并实现视频的创建和观看，从而可以训练其算法。

**For its algorithm to become as effective as it has, TikTok became its own source of training data**.  

为了使其算法变得如此有效，TikTok 成为了自己的训练数据源。

___

To understand how TikTok’s created such a potent flywheel of learning, we need to delve into its design.  

要了解 TikTok 如何创建如此强大的学习飞轮，我们需要深入研究它的设计。

The dominant school of thought when it comes to UI design in tech, at least that I’ve grown up with the past two decades, has centered around removing friction for users in accomplishing whatever it is they’re trying to do while delighting them in the process.  

当谈到科技领域的 UI 设计时，至少在我过去二十年成长过程中，主流思想流派的中心思想是消除用户在完成他们想要做的任何事情时的摩擦，同时让他们感到高兴。的过程。  

The goal has been design that is elegant, in every sense of the word: intuitive, ingenious, even stylish.  

我们的目标是设计优雅，体现在各个方面：直观、巧妙，甚至时尚。

Perhaps no company has more embodied this school of design than Apple.  

也许没有一家公司比苹果公司更能体现这种设计流派。  

At its best, Apple makes hardware and software that is pleasingly elegant—“it just works”—but also sexy in a way that makes its users feel tasteful.  

在最好的情况下，苹果制造的硬件和软件既优雅又令人愉悦——“它就是好用”——同时又性感，让用户感到有品味。Apple’s infamous controlling style—no replaceable batteries for its phones and laptops, the current debate over its App Store rules—put the company squarely in the camp of what Scott in Seeing Like a State refers to as high modernism.  

苹果公司臭名昭著的控制风格——手机和笔记本电脑不可更换电池，当前关于其应用程序商店规则的争论——使该公司完全陷入了斯科特在《像国家一样看待》中所说的高度现代主义阵营。 Is there any reason to show a video of how the new MacBook Pro body is crafted from one solid block of aluminum (besides the fact that Jony Ive cooing “a-loo-MIN-eee-um” is ASMR to Apple fans) when unveiling it at an Apple keynote?  

有没有理由在揭幕时展示新款 MacBook Pro 机身是如何由一整块铝材制成的视频（除了 Jony Ive 咕咕叫“a-loo-MIN-eee-um”对苹果粉丝来说就是 ASMR）在苹果的主题演讲中？  

How about because it’s sexy AF to see industrial lasers carving that unibody out of a solid chunk of aluminum?  

怎么样，因为看到工业激光用一块实心铝雕刻出一体式机身是很性感的自动对焦？  

And later, when you’re cranking out an email at a coffee shop on said laptop, some residual memory of that video in your unconscious will give you just the slightest hit of dopamine?  

后来，当你在咖啡店用笔记本电脑写一封电子邮件时，你无意识中对该视频的一些残留记忆会让你产生轻微的多巴胺吗？

There’s a reason this user-centric design model has been so dominant for so long, especially in consumer tech. First, it works.  

这种以用户为中心的设计模式长期以来一直占据主导地位是有原因的，尤其是在消费技术领域。首先，它有效。  

Apple’s market cap was, at last check, over 2 trillion dollars.  

据最新统计，苹果公司的市值超过 2 万亿美元。Remember when fake Sean Parker said a billion dollars was cool? That was just a decade ago and a billion dollars is no longer S-Tier. The wealth meta moves fast.  

还记得假肖恩·帕克说过十亿美元很酷吗？那只是十年前的事，十亿美元不再是 S 级。财富元变化很快。 Furthermore, we live in the era of massive network effects, where tech giants who apply Ben Thompson’s [aggregation theory](https://stratechery.com/aggregation-theory/) and acquire a massive base of users can exert unbelievable leverage on the markets they participate in.  

此外，我们生活在一个巨大网络效应的时代，应用本·汤普森聚合理论并获得大量用户的科技巨头可以对他们参与的市场发挥令人难以置信的影响力。  

One of the best ways to do that is to design products and services that do what users want better than your competitors.  

做到这一点的最佳方法之一就是设计比竞争对手更好地满足用户需求的产品和服务。

This school of design has been so dominant for so long that I’ve almost managed to forget some of the brutal software design that used to the norm in a bygone era.  

这种设计流派长期以来一直占据主导地位，以至于我几乎忘记了过去时代的一些残酷的软件设计。Not to be confused with [brutalist design](https://brutalistwebsites.com/), which can be quite beautiful in its own respect, like its [architectural cousins](https://theculturetrip.com/asia/japan/articles/tokyos-intriguing-brutalist-architecture/).  

不要与野兽派设计相混淆，野兽派设计本身就非常美丽，就像它的建筑表亲一样。

But what if the key to serving your users best depends in large part upon training a machine learning algorithm? What if that ML algorithm needs a massive training dataset?  

但是，如果为用户提供最佳服务的关键在很大程度上取决于机器学习算法的训练呢？如果机器学习算法需要大量训练数据集怎么办？  

In an age when machine learning is in its ascendancy, this is increasingly a critical design objective.  

在机器学习方兴未艾的时代，这越来越成为一个关键的设计目标。

More and more, when considering how to design an app, you have to consider how best to help an algorithm “see.” To serve your users best, first serve the algorithm.  

越来越多地，在考虑如何设计应用程序时，您必须考虑如何最好地帮助算法“看到”。为了最好地为用户服务，首先要服务算法。

TikTok fascinates me because it is an example of a modern app whose design, whether by accident or, uhh, design, is optimized to feed its algorithm as much useful signal as possible.  

TikTok 令我着迷，因为它是现代应用程序的一个例子，其设计，无论是偶然还是，呃，设计，都经过优化，以向其算法提供尽可能多的有用信号。  

It is an exemplar of what I call **algorithm-friendly design**.  

这是我所说的算法友好设计的一个范例。I thought about calling it algorithm-centric design but felt it went too far.  

我想过将其称为“以算法为中心的设计”，但觉得它太过分了。  

Ultimately, a design that helps an algorithm see is still doing so in service of providing the user with the best possible experience.  

最终，帮助算法视觉的设计仍然是为了为用户提供最佳的体验。 This might still be considered just a variant of user-centric design, but for those teams working on products with a heavy machine learning algorithm component, it may be useful to acknowledge explicitly.  

这可能仍然被认为只是以用户为中心的设计的一种变体，但对于那些致力于使用大量机器学习算法组件的产品的团队来说，明确承认可能会很有用。  

After all, when a product manager, designer, and engineer meet to design an app, the algorithm isn't in attendance. Yet its training needs must be represented.  

毕竟，当产品经理、设计师和工程师开会设计应用程序时，算法并不在场。但其培训需求必须得到体现。

James Scott speaks of “seeing like a state,” of massive shifts in fields like urban design that made quantities like plots of land and their respective owners “legible” to tax collectors.  

詹姆斯·斯科特谈到“像一个国家一样看待”，谈到城市设计等领域的巨大转变，这些转变使得诸如土地及其各自所有者之类的数量对税务人员来说“清晰可辨”。  

TikTok’s design makes its videos, users, and user preferences legible to its For You Page algorithm.  

TikTok 的设计使其视频、用户和用户偏好能够通过其 For You Page 算法清晰可见。  

The app design fulfills one of its primary responsibilities: “seeing like an algorithm.”  

该应用程序的设计履行了其主要职责之一：“像算法一样看待”。

Let’s take a closer look. TikTok opens into the For You Page and goes right into a video. This is what it looks like.  

让我们仔细看看。 TikTok 打开“为你推荐”页面，然后直接进入视频。这就是它的样子。

[This](https://www.tiktok.com/@bellapoarch/video/6862153058223197445?lang=en) is, as of right now, the most popular TikTok ever. By the time I publish this post, its 34.1M likes will likely be outdated. You can read [the story of how this TikTok even came to be](https://www.stereogum.com/2097845/remember-blackpool-grime-it-now-soundtracks-the-most-popular-tiktok-of-all-time/news/) and it will still feel like a cultural conundrum wrapped in a riddle stuffed in a paradox, and you love to see it.  

截至目前，这是有史以来最受欢迎的 TikTok。当我发布这篇文章时，它的 3410 万个赞可能已经过时了。你可以读一下这个 TikTok 的诞生故事，但它仍然感觉像是一个文化难题，包裹在一个充满悖论的谜语中，你喜欢看到它。  

I showed this to my niece, we looped it a few dozen times, then we started chanting “M to the B, M to the B” and laughing our asses off and it was one of the only times in this pandemic I’ve truly felt anything other than despair.  

我把这个给我侄女看，我们循环了几十遍，然后我们开始高喊“M to the B，M to the B”，然后笑得前仰后合，这是在这场大流行中我真正感受到的唯一一次。除了绝望之外，还有什么感觉。

The entire screen is filled with one video. Just one. It is displayed fullscreen, in vertical orientation. This is not a scrolling feed. It’s paginated, effectively.  

整个屏幕都充满了一个视频。只有一个。它以垂直方向全屏显示。这不是滚动提要。它有效地分页。  

The video autoplays almost immediately (and the next few videos are loaded in the background so that they, too, can play quickly when it’s their turn on stage).  

视频几乎立即自动播放（接下来的几个视频会在后台加载，以便轮到他们上台时也可以快速播放）。

This design puts the user to an immediate question: how do you feel about this short video and this short video alone?  

这样的设计给用户提出了一个直接的问题：你对这个短视频以及单独的这个短视频感觉如何？

Everything you do from the moment the video begins playing is signal as to your sentiment towards that video. Do you swipe up to the next video before it has even finished playing?  

从视频开始播放那一刻起，您所做的一切都表明了您对该视频的看法。您是否会在下一个视频播放完毕之前向上滑动到下一个视频？  

An implicit (though borderline explicit) signal of disinterest.  

一种隐含的（尽管接近明确的）不感兴趣的信号。

Did you watch it more than once, letting it loop a few times? Seems that something about it appealed to you. Did you share the video through the built-in share pane?  

您是否观看过多次并循环播放了几次？似乎其中的某些内容吸引了您。您是否通过内置共享窗格共享了视频？  

Another strong indicator of positive sentiment.  

积极情绪的另一个有力指标。  

If you tap the bottom right spinning LP icon and watch more videos with that same soundtrack, that is additional signal as to your tastes.  

如果您点击右下角旋转的 LP 图标并观看更多具有相同配乐的视频，这就是您的品味的额外信号。  

Often the music cue is synonymous with a meme, and now TikTok has another axis on which to recommend videos for you. Did you tap into the video creator’s profile page?  

通常，音乐提示就是模因的代名词，而现在 TikTok 有了另一个轴来为你推荐视频。您是否点击了视频创作者的个人资料页面？  

Did you watch other videos of theirs, and did you then follow them? In addition to enjoying the video, perhaps you appreciate them in particular.  

您看过他们的其他视频，然后关注他们吗？除了欣赏视频之外，也许您还特别欣赏它们。

But let’s step back even earlier, before you’re even watching the video, and understand how the TikTok algorithm “sees” the video itself.  

但让我们更早地退一步，在你观看视频之前，了解 TikTok 算法如何“看到”视频本身。  

Before the video is even sent down to your phone by the FYP algorithm, some human on TikTok’s operations team has already watched the video and added lots of relevant tags or labels.  

在 FYP 算法将视频发送到您的手机之前，TikTok 运营团队的一些人员已经观看了该视频并添加了许多相关标签或标签。

Is the video about dancing? Lip synching? Video games? A kitten? A chipmunk? Is it comedic? Is the subject a male or female? What age, roughly? Is it a group video? Where is it set?  

视频是关于跳舞的吗？口型同步？视频游戏？一只小猫？花栗鼠？是喜剧吗？对象是男性还是女性？大概几岁？这是集体视频吗？是在哪里设置的呢？  

What filters or visual effects are used? If there’s food involved, what kind? And so on. All of these labels become features that the algorithm can now see.  

使用什么滤镜或视觉效果？如果涉及食物，是什么种类的？等等。所有这些标签都成为算法现在可以看到的特征。

Vision AI also does a pass on the video, and to the extent it can, contributes what it sees.  

视觉 AI 还会对视频进行传递，并在力所能及的范围内贡献它所看到的内容。  

Some of TikTok’s camera filters are designed to track human faces or hands or gestures so vision AI is often invoked even earlier, at the point of creation.  

TikTok 的一些相机滤镜旨在跟踪人脸、手或手势，因此视觉人工智能通常在创建时更早地被调用。

The algorithm can also see what TikTok already knows about you. What types of videos have you enjoyed in the past? What demographic or psychographic information is known about you?  

该算法还可以了解 TikTok 已经了解的有关您的信息。您过去喜欢什么类型的视频？关于您的人口统计或心理信息有哪些已知？  

Where are you watching the video? What type of device do you have? And so on. Beyond that, what other users are similar to you?  

你在哪里看视频？您有什么类型的设备？等等。除此之外，还有哪些用户与您相似？

Let's jump back to the moment you watch that video on your phone in TikTok. The FYP algorithm can now close all the feedback loops.  

让我们回到您在手机上观看 TikTok 视频的那一刻。 FYP 算法现在可以关闭所有反馈循环。  

It takes every one of the actions you take on the video and can guess how you, with all your tastes, feels about this video, with all its attributes.  

它会记录您在视频中执行的每一项操作，并根据您的喜好猜测您对该视频及其所有属性的感受。

None of these individual steps sounds like rocket science, especially to anyone who works on any algorithmic social feed today.  

这些单独的步骤听起来都不像火箭科学，尤其是对于当今从事任何算法社交提要工作的人来说。In my previous piece I noted that TikTok doesn’t really have a strong social graph.  

在我之前的文章中，我指出 TikTok 并没有真正强大的社交图谱。  

One of the reasons the app is as effective as it is is that it doesn’t try to pretend to be what it isn’t.  

该应用程序如此有效的原因之一是它不会试图假装不是。  

That is, people already have a gazillion other social graphs and ways to share with people they know.  

也就是说，人们已经拥有无数其他社交图谱和与认识的人分享的方式。  

Rather than force people to do so within the TikTok app, they make it dead simple to download videos or share them through those external channels.  

他们并没有强迫人们在 TikTok 应用程序内这样做，而是让下载视频或通过这些外部渠道分享视频变得非常简单。  

What TikTok keeps, however, is the signal that you chose to share that video. That data feeds their algorithm and their algorithm alone.  

然而，TikTok 保留的是您选择分享该视频的信号。这些数据为他们的算法提供数据，并且只为他们的算法提供数据。  

Since the videos are watermarked, they also get a nice hit of free publicity from the share.  

由于这些视频带有水印，因此它们还可以从共享中获得免费宣传的良好效果。 In fact, TikTok has published a [blog post](https://newsroom.tiktok.com/en-us/how-tiktok-recommends-videos-for-you) describing essentially how their FYP algorithm works, and I doubt anyone in tech will find the description anything but obvious.  

事实上，TikTok 已经发表了一篇博客文章，基本上描述了他们的 FYP 算法是如何工作的，我怀疑科技界的任何人都会觉得这个描述不那么明显。

But contrast what TikTok's FYP algorithm sees with what a comparable recommendation algorithm sees on most other social networking feeds.  

但将 TikTok 的 FYP 算法所看到的结果与类似的推荐算法在大多数其他社交网络源上所看到的结果进行对比。

The default UI of our largest social networks today is the infinite vertically scrolling feed (I could have easily used a screenshot of Facebook above, for example).  

当今最大的社交网络的默认 UI 是无限垂直滚动的 feed（例如，我可以轻松地使用上面 Facebook 的屏幕截图）。  

Instead of serving you one story at a time, these apps display multiple items on screen at once.  

这些应用程序不是一次为您提供一个故事，而是一次在屏幕上显示多个项目。  

As you scroll up and past many stories, the algorithm can’t “see” which story your eyes rest on.  

当您向上滚动并浏览许多故事时，算法无法“看到”您的眼睛停留在哪个故事上。  

Even if it could, if the user doesn’t press any of the feedback buttons like the Like button, is their sentiment towards that story positive or negative?  

即使可以，如果用户没有按下任何反馈按钮（例如“喜欢”按钮），他们对该故事的看法是积极的还是消极的？  

The signal of user sentiment isn’t clean.  

用户情绪的信号并不明确。

If you subscribe to the idea that UI's should remove friction, the infinite scrolling feed is ideal. It offers a sense of uninhibited control of the pace of consumption.  

如果您同意 UI 应该消除摩擦的想法，那么无限滚动提要是理想的选择。它给人一种不受约束地控制消费节奏的感觉。  

The simulated physics that result from flicking a feed with your thumb and seeing it scroll up like the drum of the Big Wheel from the Price is Right Showcase Showdown with the exact rotational velocity implied by the speed of your initial gesture, seeing that software wheel gradually slow down exactly as it would if encountering constant physical friction, it’s one of the most delightful user interactions of the touchscreen era.  

模拟物理效果是用拇指轻弹提要，然后看到它像“价格是正确的展示摊牌”中的大轮子的鼓一样向上滚动，并通过初始手势的速度暗示精确的旋转速度，逐渐看到软件轮子就像遇到持续的物理摩擦一样减慢速度，这是触摸屏时代最令人愉快的用户交互之一。  

You can scroll past a half dozen tweets or Facebook feed items in no time. Wheeeeeeee!  

您可以立即滚动浏览六条推文或 Facebook 提要项目。呼呼呼！

A paginated design, in which you could only see one story at a time, where each flick of the finger would only advance the feed one item at a time, would be a literal and metaphoric drag.  

在分页设计中，您一次只能看到一个故事，每次手指轻弹一次只能将提要前进一个项目，这将是一种字面上和隐喻上的拖累。

On the other hand, maybe you wouldn’t mind reading one tweet at a time if they were better targeted, and maybe they would be better targeted if Twitter knew more about which types of tweets really interest you.  

另一方面，如果推文更有针对性，你也许不介意一次阅读一条推文，而且如果 Twitter 更多地了解你真正感兴趣的推文类型，也许它们会更有针对性。  

And maybe Twitter would know more about what really interested you if you had to give explicit and implicit positive or negative signals on every tweet.  

如果你必须在每条推文中给出明确和隐含的积极或消极信号，那么 Twitter 可能会更多地了解你真正感兴趣的内容。

Even on a story a user does engage with, judging sentiment is a challenge. Most apps only have positive feedback mechanisms, most typically some form of a like button.  

即使对于用户确实参与的故事，判断情绪也是一个挑战。大多数应用程序只有积极的反馈机制，最典型的是某种形式的“喜欢”按钮。  

Since apps like Facebook, Instagram, and Twitter are built around social graphs, it’s obvious why they might opt not to offer dislike buttons.  

由于 Facebook、Instagram 和 Twitter 等应用程序是围绕社交图谱构建的，因此很明显它们可能会选择不提供不喜欢按钮。

But, as Stephen King wrote in [On Writing](https://amzn.to/2RGcXAb), "If you expect to succeed as a writer, rudeness should be the second-to-least of your concerns. The least of all should be polite society and what it expects.  

但是，正如史蒂芬·金在《论写作》中所写的那样，“如果你希望成为一名成功的作家，那么粗鲁应该是你最不关心的问题。最不重要的应该是礼貌的社会及其期望。  

If you intend to write as truthfully as you can, your days as a member of polite society are numbered, anyway."  

如果你打算尽可能真实地写作，无论如何，你作为上流社会成员的日子已经屈指可数了。”

By relying on a long scrolling feed with mostly explicit positive feedback mechanisms, social networks like Facebook, Twitter, and Instagram have made a tradeoff in favor of lower friction scanning for users at the expense of a more accurate read on negative signal.  

通过依赖长滚动提要和大多数明确的积极反馈机制，Facebook、Twitter 和 Instagram 等社交网络做出了权衡，以牺牲对负面信号的更准确读取为代价，支持用户较低的摩擦扫描。You see another variant of this tradeoff at longstanding companies with the same founding CEO.  

在拥有同一位创始首席执行官的历史悠久的公司中，您会看到这种权衡的另一种变体。  

That person tends to surround themselves with a C-Suite that follows their lead, works well with them.  

这个人倾向于让自己身边的高管都听从他们的领导，与他们合作良好。  

The danger of being surrounded by yes-men is not having anyone to challenge the blindspots in your thinking.  

被唯唯诺诺的人包围的危险在于没有人挑战你思维中的盲点。  

It's always worth asking who the people are who are powerful enough to actually change the minds of people like Bezos, Cook, Zuckerberg, Musk.  

始终值得一问的是，谁有足够的权力来真正改变贝佐斯、库克、扎克伯格、马斯克等人的想法。  

Often the answer is no one, so their blindspots become the blindspots of the company.  

通常答案是没有人，因此他们的盲点就成为公司的盲点。  

Networks that are built around interest graphs, like Reddit, do tend to incorporate down voting mechanisms because their prime directive to keep users from churning is to serve them the most interesting content.  

围绕兴趣图构建的网络（例如 Reddit）确实倾向于采用否决投票机制，因为它们防止用户流失的主要指令是为他们提供最有趣的内容。  

That means weeding out uninteresting content as much as it does surfacing appealing content.  

这意味着要清除无趣的内容，就像显示有吸引力的内容一样。

TikTok doesn’t have an explicit downvote button, but by serving you just one video at a time, they can infer your lack of interest in any single video based on whether you churn out of that video quickly  

TikTok 没有明确的否决按钮，但通过一次只向您提供一个视频，他们可以根据您是否快速浏览该视频来推断您对任何单个视频缺乏兴趣 A quick swipe up before a video has completed is like swiping left on Tinder. The best TikTokers have an intuitive sense of the narrative pace that is appropriate for that platform.  

在视频播放完毕之前快速向上滑动就像在 Tinder 上向左滑动一样。最好的 TikTok 用户对适合该平台的叙事节奏有直观的感觉。  

How long can you drag out the punching or payoff without losing the viewer, how do you have a set up that keeps the user involved.  

你能在不失去观众的情况下将打孔或支付拖多久，你如何设置让用户参与其中。  

Using a music cue that has already been co-opted into a meme helps because the bass drop or musical payoff foreshadows when the punchline of the video will drop; a viewer knows how much longer before they reach the payoff.  

使用已经被纳入模因的音乐提示会有所帮助，因为低音下降或音乐回报预示着视频的笑点将会下降；观众知道他们需要多长时间才能获得回报。  

Also viewers may stick around just for the pleasure of hearing that musical resolution.  

此外，观众可能只是为了听到音乐分辨率的乐趣而留下来。  

and by which positive actions you _don’t take_.  

以及您不采取的积极行动。

If you click into a text post by someone on Facebook but don’t comment or like the post, how can Facebook judge your sentiment toward that post?  

如果您点击 Facebook 上某人的文本帖子，但没有评论或点赞该帖子，Facebook 如何判断您对该帖子的看法？  

Maybe you thought about disagreeing violently in comments, but the person is a coworker or friend of a friend and you decided the better of it.  

也许你想过在评论中强烈反对，但这个人是同事或朋友的朋友，你决定这样做更好。  

That negative sentiment is difficult to capture; the algorithm can’t “see” your feelings.  

这种负面情绪很难捕捉；算法无法“看到”你的感受。Most social networks have explicit reporting features for reporting offensive and/or abusive content, but those features are buried and most users don’t resort to them.  

大多数社交网络都有明确的报告功能来报告攻击性和/或辱骂性内容，但这些功能被隐藏起来，大多数用户不会求助于它们。  

By the time someone does use a feature like that, you’ve usually already made a grave mistake far upstream and it’s too late to salvage most of the damage that’s been done.  

当有人确实使用这样的功能时，您通常已经在上游犯了一个严重的错误，并且已经来不及挽回大部分已造成的损害了。  

It’s the content that’s boring or causes mild displeasure that is the slow killer.  

无聊或引起轻微不满的内容才是慢杀手。  

In my previous post, I noted that content derived from a social graph can drift away from a user’s true interests because of the mismatch between your own interests and those of people you know.  

在我之前的文章中，我指出，由于您自己的兴趣与您认识的人的兴趣不匹配，源自社交图谱的内容可能会偏离用户的真实兴趣。  

The switch from a chronological to algorithmic feed is often the default defensive move against such drift.  

从时间顺序到算法提要的转变通常是针对这种漂移的默认防御措施。

But if the algorithm isn’t "seeing" signals of a user’s growing disinterest, if only positive engagement is visible, some amount of divergence is unavoidable.  

但如果算法没有“看到”用户日益不感兴趣的信号，如果只有积极的参与是可见的，那么一定程度的分歧是不可避免的。  

You might see that a user is slowly losing interest, not liking as many items, not opening your app as often, but precisely which stories are driving them away may be unclear.  

您可能会发现用户正在慢慢失去兴趣，不喜欢那么多的项目，不经常打开您的应用程序，但到底是哪些故事正在赶走他们可能还不清楚。  

By the time they're starting to exhibit those signs of churn, it's often too late to reverse the bleeding.  

当他们开始表现出这些流失迹象时，扭转局面往往为时已晚。

Algorithm-friendly design need not be user-hostile. It simply takes a different approach as to how to best serve the user’s interests.  

算法友好的设计不必对用户不利。它只是采用不同的方法来最好地满足用户的利益。  

Pagination may insert some level of friction to the user, but in doing so, it may provide the algorithm with cleaner signal that safeguards the quality of the feed in the long run.  

分页可能会给用户带来一定程度的摩擦，但这样做可以为算法提供更清晰的信号，从长远来看可以保障提要的质量。

Minimizing friction is merely one means to a great user experience. The goal of any design is not to minimize friction, it’s to help the user achieve some end.  

最大限度地减少摩擦只是获得良好用户体验的一种手段。任何设计的目标都不是最小化摩擦，而是帮助用户实现某种目的。  

Reducing friction is often consistent with that end, but not always.  

减少摩擦通常与这一目标一致，但并非总是如此。  

You might say that the quote tweet reduces the friction of manually copying someone else’s tweet, but reducing friction to organizing a mob to pile on someone might not be a core mechanic you want to encourage if your goal is civil public discourse.  

你可能会说引用推文减少了手动复制别人推文的摩擦，但如果你的目标是公民公共话语，那么减少组织暴民攻击某人的摩擦可能不是你想要鼓励的核心机制。  

Some forms of friction are good.  

某些形式的摩擦是有益的。

You'll hear many power Twitter users counseling others to make use of muting and blocking early and often.  

你会听到许多 Twitter 的高级用户建议其他人尽早并经常使用静音和屏蔽功能。Some users even make liberal use of [soft blocking](https://www.urbandictionary.com/define.php?term=Soft%20Block) to surreptitiously remove followers.  

一些用户甚至随意使用软屏蔽来暗中删除关注者。  

Users proudly tweet screenshots of words they've muted as a sign of their displeasure with some popular topic of discussion (or their intellectual superiority to said topic).  

用户自豪地在推特上发布他们静音的单词的屏幕截图，以表达他们对某些流行讨论话题（或他们对所述话题的智力优势）的不满。  

Non sports fans tweet about "sportsball," others tweet "I'll bite, what's X?" where X is something everyone is discussing.  

非体育迷在推特上谈论“运动球”，其他人在推特上说“我会咬，X是什么？”其中 X 是每个人都在讨论的东西。  

Some people have gone so far as to unfollow everyone and start their following from scratch again.  

有些人甚至取消了所有人的关注，并重新从头开始关注。At some point, and likely because it A/B tested well, Twitter started showing users tweets that people they followed had liked, even from people that user didn't follow themselves.  

在某个时候，可能是因为 A/B 测试良好，Twitter 开始向用户显示他们所关注的人喜欢的推文，甚至是用户没有关注自己的人的推文。  

This does occasionally show me tweets of interest, but what it also does is increase, on an absolute basis, the number of tweets I have no interest in and have to scroll past.  

这确实偶尔会向我显示感兴趣的推文，但从绝对意义上讲，它也会增加我不感兴趣且必须滚动过去的推文数量。  

I'm a broken record on this: no two people have the exact same interests.  

我在这方面打破了记录：没有两个人有完全相同的兴趣。  

The launch of this feature has me really considering unfollowing everyone and starting from scratch, but I also worry about hurting people's feelings, because I'm a softie.  

这个功能的推出让我真的考虑取消关注所有人并从头开始，但我也担心伤害人们的感情，因为我是一个软弱的人。  

If Twitter were structured differently this wouldn't be an issue.  

如果 Twitter 的结构不同，这就不成问题了。  

I sometimes think about adopting some or all of these strategies myself, but for Twitter, the necessity of these is itself a failure of the service.  

我有时会考虑自己采用部分或全部策略，但对于 Twitter 来说，这些策略的必要性本身就是服务的失败。  

If the algorithm were smarter about what interested you, it should take care of muting topics or blocking people on your behalf, without you having to do that work yourself.  

如果算法对您感兴趣的内容更聪明，它应该代表您处理静音主题或阻止人员，而无需您自己做这些工作。  

As I wrote last time, that you have to follow people at all on Twitter to get interesting content is, one could argue, a design flaw for what could be a powerful interest graph.  

正如我上次写的，你必须在 Twitter 上关注人们才能获得有趣的内容，有人可能会说，这是一个强大的兴趣图的设计缺陷。

Not only does TikTok capture very clean signals of sentiment from its users, it also gathers a tremendous volume of them per session.  

TikTok 不仅从用户那里捕获了非常清晰的情绪信号，而且每次会话都会收集大量的信号。  

Videos on TikTok are so short that even in a brief session, TikTok can gather a lot of feedback on your tastes.  

TikTok 上的视频非常短，即使在简短的会话中，TikTok 也可以收集大量有关您品味的反馈。

The process is relatively painless, too.  

这个过程也相对无痛。  

At worst, a few videos might bore you, but swiping them away makes for relatively painless work, and since the algorithm listens closely to your feedback, you may even enjoy dismissing videos knowing that the app will register your displeasure and act on it.  

在最坏的情况下，一些视频可能会让你感到厌烦，但将它们刷掉可以相对轻松地完成工作，而且由于算法会仔细聆听你的反馈，你甚至可能会喜欢忽略视频，因为知道应用程序会记录你的不满并采取行动。Short video happens to be a category quite suited to this type of machine learning-driven recommendation. By no means would I imply that it would work for every type of category.  

短视频恰好是非常适合这种机器学习驱动推荐的类别。我绝不意味着它适用于所有类型的类别。  

Music works well. It is short in duration so the sampling cost is low, and the repeat consumption value is high. Musical similarities tend to be mathematically detectable.  

音乐效果很好。周期短，采样成本低，重复消费价值高。音乐相似性往往可以通过数学方法检测出来。  

My Spotify Radio recommendations are solid. On the other hand, algorithmic movie recommendations have never really felt magical to me.  

我对 Spotify Radio 的推荐很可靠。另一方面，算法电影推荐对我来说从来没有真正感到神奇。  

Movies are very long, the sampling cost is very high. The corpus is small, and only something like 500 or so movies come out each year, of which most people only see a handful.  

电影很长，采样成本很高。语料库很小，每年上映的电影大约只有 500 部左右，而大多数人只看过其中的一小部分。  

This entire subject is worth a separate post.  

整个主题值得单独写一篇文章。  

By the way, TikTok isn’t the only app with an interface that is optimized for the task of matching, with an interface that shows you one entity at a time so as to be more clear on how you feel.  

顺便说一句，TikTok 并不是唯一一个界面针对匹配任务进行优化的应用程序，它的界面一次向您显示一个实体，以便更清楚地了解您的感受。  

Before TikTok, we had a whole category in which the one-item-at-a-time audition-style UI was dominant.  

在 TikTok 之前，我们有一整个类别，其中一次一项试听风格的 UI 占主导地位。

![1_Suggested.png](1_Suggested.png)

![Tinder - Card Stack.png](Tinder+-+Card+Stack.png)

There’s a reason swipe right and swipe left have become shorthand slang for signaling approval and disapproval, generally.  

一般来说，向右滑动和向左滑动已成为表示批准和不批准的简写俚语，这是有原因的。  

Tinder came up with what feels like a design primitive on a touchscreen UI for binary voting.  

Tinder 在触摸屏 UI 上提出了一种感觉像是用于二元投票的设计原语。

In this software era, true competitive advantages, or moats, are increasingly illusory.  

在这个软件时代，真正的竞争优势或护城河越来越虚幻。  

Most software features or UI designs can be copied easily by an incumbent or competitor overnight. All you will have done is test the impact of the design for them.  

大多数软件功能或 UI 设计都可以在一夜之间被现任者或竞争对手轻松复制。您所要做的就是测试设计对他们的影响。On one of my trips to China, I was at a dinner with a large group of Chinese entrepreneurs, and I mentioned the hubbub over Instagram copying Stories from Snapchat.  

在我的一次中国之行中，我与一大群中国企业家共进晚餐，我提到了 Instagram 复制 Snapchat 故事的喧嚣。  

One of the chief product officers of one of China’s top companies laughed and remarked, “In China, if your competitor doesn’t copy one of your successful features inside of two weeks, they must be incompetent.” In many ways, the Chinese tech scene is the true Darwinian marketplace of ideas that Silicon Valley thinks of itself as.  

中国一家顶级公司的首席产品官笑着说道：“在中国，如果你的竞争对手没有在两周内复制你的一项成功功能，他们一定是无能的。”在很多方面，中国科技界都是硅谷所认为的真正的达尔文思想市场。  

This bodes poorly for the relative output of Silicon Valley because the rate of idea spread and mutation occurs more quickly in China.  

这对硅谷的相对产出来说是个坏兆头，因为中国的思想传播和突变速度更快。  

Silicon Valley is often said to have taken over as the geographic center of technology innovation from Boston’s Route 128 in part because Silicon Valley’s more open labor markets allowed ideas to move freely among companies.  

人们常说，硅谷已经取代波士顿 128 号公路成为技术创新的地理中心，部分原因是硅谷更加开放的劳动力市场允许创意在公司之间自由流动。  

China has taken that playbook and pushed it even further.  

中国已经采用了这一策略，并将其进一步推进。  

Surviving the competitive landscape of the Chinese tech scene is like trying to climb out of that pit in The Dark Knight Rises. Terrifying.  

在中国科技界的竞争格局中生存下来就像试图从《黑暗骑士崛起》中的深坑中爬出来一样。太可怕了。

But if you can create a flywheel, like TikTok’s, it becomes much harder for a competitor like Reels or Triller to catch up.  

但如果你能创造一个像 TikTok 那样的飞轮，那么像 Reels 或 Triller 这样的竞争对手就更难追赶。  

Triller may pay some influencers from TikTok to come over and make videos there, Reels might try to draft off of existing Instagram traffic, but what makes TikTok work is the entire positive feedback loop connecting creators, videos, and viewers via the FYP algorithm.  

Triller 可能会付钱给 TikTok 的一些有影响力的人过来在那里制作视频，Reels 可能会尝试吸收现有的 Instagram 流量，但 TikTok 的成功之处在于通过 FYP 算法连接创作者、视频和观众的整个正反馈循环。

In tech, an industry that epitomizes Brian Arthur’s [Increasing Returns and Path Dependence in the Economy](https://amzn.to/2REGqdO) perhaps more than any other, the first competitor to achieve product-market fit can run away from the pack.  

在科技行业，这个行业也许比其他任何行业都更能体现布莱恩·阿瑟（Brian Arthur）的递增回报和经济路径依赖，第一个实现产品与市场契合的竞争对手可能会脱颖而出。  

If more and more markets feel like they are winner-take-all, or winners-take-all, that is because in an increasingly interconnected world, they are.  

如果越来越多的市场感觉自己是赢家通吃或赢家通吃，那是因为在一个日益互联的世界中，它们确实如此。

Bytedance is often described as the algorithm company, and TikTok has been described over the past few weeks as powered by just such algorithmic black magic.  

字节跳动经常被描述为算法公司，而 TikTok 在过去几周被描述为正是由这种算法黑魔法提供支持。  

Many have gone so far as to say that TikTok wouldn’t be worth purchasing if the algorithm weren’t included.  

许多人甚至表示，如果不包含该算法，TikTok 就不值得购买。

That’s a mistake, in my opinion. Yes, retraining the FYP recommendations algorithm might take so long that some users would churn. I don’t mean to trivialize that task.  

在我看来，这是一个错误。是的，重新训练 FYP 推荐算法可能需要很长时间，以至于一些用户会流失。我并不是要轻视这项任务。  

But the actual magic is how every element of TikTok's design and processes connect with each other to create a dataset with which the algorithm trains itself into peak performance.  

但真正的魔力在于 TikTok 设计和流程的每个元素如何相互连接以创建一个数据集，算法用该数据集自我训练以达到最佳性能。  

No single step in that loop is beyond the capabilities of any of the many U.S. suitors.  

在这个循环中，任何一步都超出了众多美国追求者的能力范围。  

All that’s needed is an understanding of how the flywheel works and a commitment to keep every element and process in it functioning.  

所需要的只是了解飞轮的工作原理，并致力于保持其中的每个元件和流程正常运行。

All around me, I encounter products or services that seem to have hit a ceiling in the quality of their algorithmic recommendations: Yelp, OpenTable, Amazon, Google, Netflix, and on and on.  

在我周围，我遇到的产品或服务的算法推荐质量似乎已经达到了上限：Yelp、OpenTable、亚马逊、谷歌、Netflix 等等。  

Don't get me wrong, some of them are at rest in a good place.  

别误会我的意思，他们中的一些人在一个好地方休息。  

But I can't help but feel there is another leap to be made in some of these, and that perhaps more algorithm-friendly design might be one of the possible solutions.  

但我不禁觉得其中一些方面还有另一个飞跃，也许更加算法友好的设计可能是可能的解决方案之一。

To recap, in part one of my series on TikTok, I discussed how the algorithm acts as an matching mechanism that makes TikTok such a scalable entertainment network.  

回顾一下，在我的 TikTok 系列文章的一部分中，我讨论了算法如何充当匹配机制，使 TikTok 成为一个可扩展的娱乐网络。  

In comparison, social networks have to approximate an interest graph using a social graph, with all the problems that come with that.  

相比之下，社交网络必须使用社交图来近似兴趣图，这会带来随之而来的所有问题。  

In this second piece on TikTok, I’ve focused on how its design helps its machine learning FYP algorithm “see” what it needs to see to do its job so effectively.  

在关于 TikTok 的第二篇文章中，我重点介绍了它的设计如何帮助其机器学习 FYP 算法“看到”它需要看到的内容，以便有效地完成工作。  

An algorithm-friendly design ethos may become a model of how other companies in other verticals might achieve an edge in the age of machine learning.  

算法友好的设计精神可能会成为其他垂直领域的其他公司如何在机器学习时代取得优势的典范。

But there’s one final reason I find TikTok such a fascinating and anomalous case study.  

但我认为 TikTok 是一个如此引人入胜且反常的案例研究，还有最后一个原因。  

It has to do less with software and algorithms and more with something that the cultural determinist in me will never tire of studying: the network effects of creativity.  

它与软件和算法的关系不大，而与我内心的文化决定论者永远不会厌倦研究的东西有关：创造力的网络效应。  

That will be the subject of my third and final part of this series on TikTok.  

这将是我的 TikTok 系列文章的第三部分，也是最后一部分的主题。
