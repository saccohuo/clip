---
title: "ChatGPT是如何建立的？"
date: 2023-03-21T18:23:56+08:00
updated: 2023-03-21T18:23:56+08:00
taxonomies:
  tags: []
extra:
  source: https://www.technologyreview.com/2023/03/03/1069311/inside-story-oral-history-how-chatgpt-built-openai/
  hostname: www.technologyreview.com
  author: Will Douglas Heaven
  original_title: "The inside story of how ChatGPT was built from the people who made it"
  original_lang: en
---

When _OpenAI_ launched _ChatGPT_, with zero fanfare, in late November 2022, the [San Francisco–based artificial-intelligence company](https://www.technologyreview.com/2020/02/17/844721/ai-openai-moonshot-elon-musk-sam-altman-greg-brockman-messy-secretive-reality/) had few expectations. Certainly, nobody inside _OpenAI_ was prepared for a [viral mega-hit](https://www.technologyreview.com/2023/02/08/1068068/chatgpt-is-everywhere-heres-where-it-came-from/). The firm has been scrambling to catch up—and capitalize on its success—ever since.  

2022年11月底，当_OpenAI_推出_ChatGPT_时，这家位于旧金山的人工智能公司没有什么期望。当然，_OpenAI_内部没有人准备好迎接一个病毒式的巨大冲击。 从那时起，该公司一直在争先恐后地追赶并利用其成功。

It was viewed in-house as a “research preview,” says Sandhini Agarwal, who works on policy at _OpenAI_: a tease of a more polished version of a [two-year-old technology](https://www.technologyreview.com/2020/07/20/1005454/openai-machine-learning-language-generator-gpt-3-nlp/) and, more important, an attempt to iron out some of its flaws by collecting feedback from the public. “We didn’t want to oversell it as a big fundamental advance,” says Liam Fedus, a scientist at _OpenAI_ who worked on _ChatGPT_.  

在_OpenAI_从事政策工作的桑迪尼-阿加瓦尔（Sandhini Agarwal）说，它在内部被视为 "研究预览"：对一项已有两年历史的技术的更完善版本进行预告，更重要的是，试图通过收集公众的反馈来消除其一些缺陷。曾参与_ChatGPT_的_OpenAI_的科学家Liam Fedus说："我们不想把它夸大为一个巨大的根本性进步"。

To get the inside story behind the chatbot—how it was made, how _OpenAI_ has been updating it since release, and how its makers feel about its success—I talked to four people who helped build what has become [one of the most popular internet apps ever](https://www.technologyreview.com/2023/02/08/1068068/chatgpt-is-everywhere-heres-where-it-came-from/). In addition to Agarwal and Fedus, I spoke to John Schulman, a cofounder of _OpenAI_, and Jan Leike, the leader of _OpenAI_’s alignment team, which works on the problem of making AI do what its users want it to do (and nothing more).  

为了了解这个聊天机器人背后的故事--它是如何被制造出来的，_OpenAI_自发布以来是如何更新它的，以及它的制造者对它的成功有何感想--我采访了四个帮助制造这个已经成为有史以来最受欢迎的互联网应用之一的人。 除了Agarwal和Fedus，我还采访了_OpenAI_的联合创始人John Schulman，以及_OpenAI_对准团队的负责人Jan Leike，该团队致力于解决让人工智能做用户想做的事（仅此而已）这一问题。

What I came away with was the sense that _OpenAI_ is still bemused by the success of its research preview, but has grabbed the opportunity to push this technology forward, watching how millions of people are using it and trying to fix the worst problems as they come up.  

我所得到的感觉是，_OpenAI_仍然对其研究预览的成功感到困惑，但已经抓住机会推动这项技术的发展，观察数百万人如何使用它，并试图在出现最糟糕的问题时加以解决。

Since November, _OpenAI_ has already updated _ChatGPT_ several times. The researchers are using a technique called [adversarial training](https://www.technologyreview.com/2020/07/10/1005048/ai-deep-learning-safe-from-hackers-adversarial-attacks/) to stop _ChatGPT_ from letting users [trick it into behaving badly](https://www.vice.com/en/article/n7zanw/people-are-jailbreaking-chatgpt-to-make-it-endorse-racism-conspiracies) (known as jailbreaking).  

自11月以来，_OpenAI_已经数次更新_ChatGPT_。研究人员正在使用一种被称为对抗性训练的技术来阻止_ChatGPT_让用户欺骗它的行为（被称为越狱）。  

This work pits multiple chatbots against each other: one chatbot plays the adversary and attacks another chatbot by generating text to force it to buck its usual constraints and produce unwanted responses.  

这项工作让多个聊天机器人相互对抗：一个聊天机器人扮演对手，通过生成文本攻击另一个聊天机器人，迫使它违背其通常的约束，产生不想要的回应。  

Successful attacks are added to _ChatGPT_’s training data in the hope that it learns to ignore them.         

成功的攻击被添加到_ChatGPT_的训练数据中，希望它能学会忽略这些攻击。

_OpenAI_ has also signed a [multibillion-dollar deal with Microsoft](https://www.technologyreview.com/2023/02/16/1068695/chatgpt-chatbot-battle-search-microsoft-bing-google/) and announced an [alliance with Bain](https://www.bain.com/vector-digital/partnerships-alliance-ecosystem/openai-alliance/), a global management consulting firm, which plans to use _OpenAI_’s generative AI models in marketing campaigns for its clients, including Coca-Cola. Outside _OpenAI_, the buzz about _ChatGPT_ has set off yet another gold rush around large language models, with companies and investors worldwide getting into the action.  

_OpenAI_还与_微软_签署了一项价值数十亿美元的协议，并宣布与全球管理咨询公司贝恩结盟，后者计划在为其客户（包括可口可乐）开展的营销活动中使用_OpenAI_的生成性人工智能模型。在_OpenAI_之外，关于_ChatGPT_的嗡嗡声已经掀起了围绕大型语言模型的又一次淘金热，全世界的公司和投资者都在参与这一行动。

That’s a lot of hype in three short months. Where did _ChatGPT_ come from? What steps did _OpenAI_ take to ensure it was ready to release? And where are they going next?    

在短短的三个月内，这是一个很大的炒作。_ChatGPT_是怎么来的？_OpenAI_采取了哪些措施来确保它可以发布？他们接下来要去哪里？

_The following has been edited for length and clarity.  

以下内容已被编辑，以保证长度和清晰度。_

**Jan Leike:** It’s been overwhelming, honestly. We’ve been surprised, and we’ve been trying to catch up.  

扬-雷克。老实说，它已经被淹没了。我们很惊讶，我们一直在努力追赶。

**John Schulman:** I was checking Twitter a lot in the days after release, and there was this crazy period where the feed was filling up with _ChatGPT_ screenshots. I expected it to be intuitive for people, and I expected it to gain a following, but I didn’t expect it to reach this level of mainstream popularity.  

约翰-舒尔曼：在发布后的几天里，我经常查看Twitter，有这么一个疯狂的时期，饲料中充满了_ChatGPT_的截图。我预计它对人们来说是很直观的，我也预计它能获得追随者，但我没有想到它会达到这种主流流行水平。

**Sandhini Agarwal:** I think it was definitely a surprise for all of us how much people began using it. We work on these models so much, we forget how surprising they can be for the outside world sometimes.  

Sandhini Agarwal:我认为对我们所有人来说，人们开始使用它绝对是一个惊喜。我们在这些模型上做了太多的工作，我们忘记了它们有时对外界来说是多么令人惊讶。

**Liam Fedus**: We were definitely surprised how well it was received. There have been so many prior attempts at a general-purpose chatbot that I knew the odds were stacked against us.  

利亚姆-费杜斯。我们对它的受欢迎程度绝对感到惊讶。之前已经有很多关于通用聊天机器人的尝试，我知道机会对我们很不利。  

However, our private beta had given us confidence that we had something that people might really enjoy.  

然而，我们的私人测试版给了我们信心，我们拥有人们可能真正喜欢的东西。

**Jan Leike:** I would love to understand better what’s driving all of this—what’s driving the virality. Like, honestly, we don’t understand. We don’t know.  

扬-雷克。我很想更好地了解是什么在推动这一切--是什么在推动病毒式传播。比如，说实话，我们不明白。我们不知道。

_Part of the team’s puzzlement comes from the fact that most of the technology inside _ChatGPT_ isn’t new. _ChatGPT_ is a fine-tuned version of GPT-3.5, a family of large language models that _OpenAI_ released months before the chatbot. GPT-3.5 is itself an updated version of [GPT-3](https://www.technologyreview.com/2021/02/24/1017797/gpt3-best-worst-ai-openai-natural-language/), which appeared in 2020.  

The company makes these models available on its website as application programming interfaces, or APIs, which make it easy for other software developers to plug models into their own code. _OpenAI_ also released a previous fine-tuned version of GPT-3.5, called [InstructGPT](https://www.technologyreview.com/2022/01/27/1044398/new-gpt3-openai-chatbot-language-model-ai-toxic-misinformation/), in January 2022. But none of these previous versions of the tech were pitched to the public.   

该团队的部分困惑来自于_ChatGPT_内部的大部分技术并不新鲜。_ChatGPT_是GPT-3.5的微调版本，GPT-3.5是_OpenAI_在聊天机器人之前几个月发布的一个大型语言模型系列。GPT-3.5本身就是GPT-3的更新版本，GPT-3出现于2020年。该公司在其网站上将这些模型作为应用程序接口（或称API）提供，这使得其他软件开发者可以很容易地将模型插入他们自己的代码中。_OpenAI_还在2022年1月发布了GPT-3.5的前一个微调版本，称为InstructGPT。但之前的这些技术版本都没有向公众推介。_

**Liam Fedus:** The _ChatGPT_ model is fine-tuned from the same language model as InstructGPT, and we used a similar methodology for fine-tuning it. We had added some conversational data and tuned the training process a bit.  

Liam Fedus:_ChatGPT_模型是由与InstructGPT相同的语言模型微调而来，我们使用了类似的方法对其进行微调。我们添加了一些对话数据，并对训练过程进行了一些调整。  

So we didn’t want to oversell it as a big fundamental advance. As it turned out, the conversational data had a big positive impact on _ChatGPT_.  

所以我们不想把它夸大为一个巨大的根本性进步。事实证明，对话数据对_ChatGPT_产生了很大的积极影响。

**John Schulman:** The raw technical capabilities, as assessed by standard benchmarks, don’t actually differ substantially between the models, but _ChatGPT_ is more accessible and usable.  

约翰-舒尔曼：根据标准基准评估的原始技术能力，这两种模型之间实际上并没有很大的差别，但_ChatGPT_更容易接近和使用。

**Jan Leike:** In one sense you can understand _ChatGPT_ as a version of an AI system that we’ve had for a while. It’s not a fundamentally more capable model than what we had previously.  

扬-雷克。在某种意义上，你可以把_ChatGPT_理解为我们已经有一段时间的人工智能系统的一个版本。这并不是一个从根本上比我们以前拥有的更有能力的模型。  

The same basic models had been available on the API for almost a year before _ChatGPT_ came out. In another sense, we made it more aligned with what humans want to do with it. It talks to you in dialogue, it’s easily accessible in a chat interface, it tries to be helpful.  

在_ChatGPT_出现之前，同样的基本模型已经在API上使用了将近一年。从另一个意义上说，我们使它更符合人类想用它做什么。它在对话中与你交谈，它很容易在聊天界面中被访问，它试图提供帮助。  

That’s amazing progress, and I think that’s what people are realizing.  

这是惊人的进步，我想这是人们正在意识到的。

**John Schulman:** It more readily infers intent. And users can get to what they want by going back and forth.  

约翰-舒尔曼：它更容易推断出意图。而用户可以通过来回走动来获得他们想要的东西。

__ChatGPT_ was trained in a very similar way to InstructGPT, using a technique called reinforcement learning from human feedback (RLHF). This is _ChatGPT_’s secret sauce. The basic idea is to take a large language model with a tendency to spit out anything it wants—in this case, GPT-3.  

5—and tune it by teaching it what kinds of responses human users actually prefer.  

_ChatGPT_的训练方式与InstructGPT非常相似，使用一种叫做从人类反馈中强化学习（RLHF）的技术。这就是_ChatGPT_的秘诀。其基本思想是，采用一个倾向于吐出任何它想要的东西的大型语言模型--本例是GPT-3。5，并通过教它人类用户实际喜欢什么样的反应来调整它。_

**Jan Leike:** We had a large group of people read _ChatGPT_ prompts and responses, and then say if one response was preferable to another response. All of this data then got merged into one training run.  

扬-雷克。我们让一大群人阅读_ChatGPT_的提示和回应，然后说一个回应是否比另一个回应更合适。然后所有这些数据都被合并到一个训练运行中。  

Much of it is the same kind of thing as what we did with InstructGPT. You want it to be helpful, you want it to be truthful, you want it to be—you know—nontoxic.  

它的大部分内容与我们对InstructGPT所做的相同。你希望它是有帮助的，你希望它是真实的，你希望它是--你知道--无毒的。  

And then there are things that are specific to producing dialogue and being an assistant: things like, if the user’s query isn’t clear, it should ask follow-up questions.  

然后还有一些专门用于产生对话和成为助手的事情：比如，如果用户的询问不清楚，它应该问后续问题。  

It should also clarify that it’s an AI system.  

它还应该澄清，这是一个人工智能系统。  

It should not assume an identity that it doesn’t have, it shouldn’t claim to have abilities that it doesn’t possess, and when a user asks it to do tasks that it’s not supposed to do, it has to write a refusal message.  

它不应该承担它不具备的身份，它不应该声称拥有它不具备的能力，当用户要求它做它不应该做的任务时，它必须写一个拒绝信息。  

One of the lines that emerged in this training was “As a language model trained by _OpenAI_ …” It wasn’t explicitly put in there, but it’s one of the things the human raters ranked highly.  

在这次培训中出现的一句话是："作为一个由_OpenAI_训练的语言模型......"这句话并没有明确地放在里面，但这是人类评分员高度评价的内容之一。

**Sandhini Agarwal:** Yeah, I think that’s what happened. There was a list of various criteria that the human raters had to rank the model on, like truthfulness.  

桑德希尼-阿加瓦尔。是的，我想这就是事情的真相。有一个列表，列出了人类评分员必须对模型进行排名的各种标准，比如真实性。  

But they also began preferring things that they considered good practice, like not pretending to be something that you’re not.   

但他们也开始喜欢那些他们认为是好的做法的东西，比如不要假装自己不是什么人。

_Because _ChatGPT_ had been built using the same techniques _OpenAI_ had used before, the team did not do anything different when preparing to release this model to the public. They felt the bar they’d set for previous models was sufficient.         

因为_ChatGPT_是用_OpenAI_以前使用过的技术建立的，所以团队在准备向公众发布这个模型时没有做任何不同的事情。他们认为他们为以前的模型设定的标准已经足够了。_

**Sandhini Agarwal:** When we were preparing for release, we didn’t think of this model as a completely new risk. GPT-3.5 had been out there in the world, and we know that it’s already safe enough. And through _ChatGPT_’s training on human preferences, the model just automatically learned refusal behavior, where it refuses a lot of requests.  

桑德希尼-阿加瓦尔。当我们准备发布时，我们并没有把这个模型当成一个全新的风险。GPT-3.5已经在世界上出现了，我们知道它已经足够安全了。而且通过_ChatGPT_对人类偏好的训练，这个模型只是自动学习了拒绝行为，它拒绝了很多请求。

**Jan Leike:** We did do some additional “red-teaming” for _ChatGPT_, where everybody at _OpenAI_ sat down and tried to break the model. And we had external groups doing the same kind of thing. We also had an early-access program with trusted users, who gave feedback.  

Jan Leike。我们确实为_ChatGPT_做了一些额外的 "红队"，_OpenAI_的每个人都坐下来，试图打破这个模型。我们也有外部团体做同样的事情。我们也有一个值得信赖的用户的早期访问计划，他们提供反馈。

**Sandhini Agarwal:** We did find that it generated certain unwanted outputs, but they were all things that GPT-3.5 also generates.  

Sandhini Agarwal:我们确实发现它产生了某些不需要的输出，但它们都是GPT-3.5也产生的东西。  

So in terms of risk, as a research preview—because that’s what it was initially intended to be—it felt fine.  

因此，就风险而言，作为研究预览--因为这就是它最初的目的--它感觉很好。

**John Schulman:** You can’t wait until your system is perfect to release it. We had been beta-testing the earlier versions for a few months, and the beta testers had positive impressions of the product.  

约翰-舒尔曼：你不能等到你的系统完美后再发布。我们已经对早期版本进行了几个月的测试，测试者对产品的印象很好。  

Our biggest concern was around factuality, because the model likes to fabricate things. But InstructGPT and other large language models are already out there, so we thought that as long as _ChatGPT_ is better than those in terms of factuality and other issues of safety, it should be good to go.  

我们最大的担忧是围绕事实性，因为模型喜欢捏造东西。但是InstructGPT和其他大型语言模型已经出现了，所以我们认为只要_ChatGPT_在事实性和其他安全问题上比这些模型好，它就应该可以使用。  

Before launch we confirmed that the models did seem a bit more factual and safe than other models, according to our limited evaluations, so we decided to go ahead with the release.  

在推出之前，我们确认，根据我们有限的评估，这些模型确实比其他模型看起来更有事实依据和安全性，所以我们决定继续发布。

__OpenAI_ has been watching how people use _ChatGPT_ since its launch, seeing for the first time how a large language model fares when put into the hands of tens of millions of users who may be looking to test its limits and find its flaws.  

The team has tried to jump on the most problematic examples of what _ChatGPT_ can produce—from_ [_songs about God’s love for rapist priests_](https://twitter.com/IrvingPeres/status/1599488357499011072) _to malware code that steals credit card numbers—and use them to rein in future versions of the model._    

自_ChatGPT_推出以来，_OpenAI_一直在观察人们如何使用它，第一次看到当一个大型语言模型被放在数以千万计的用户手中时，它的表现如何，这些用户可能想测试它的极限并发现它的缺陷。该团队试图抓住_ChatGPT_可能产生的最有问题的例子--从关于上帝对强奸犯牧师的爱的歌曲到窃取信用卡号码的恶意软件代码，并利用它们来控制该模型的未来版本。

**Sandhini Agarwal:** We have a lot of next steps. I definitely think how viral _ChatGPT_ has gotten has made a lot of issues that we knew existed really bubble up and become critical—things we want to solve as soon as possible. Like, we know the model is still very biased. And yes, _ChatGPT_ is very good at refusing bad requests, but it’s also quite easy to write prompts that make it not refuse what we wanted it to refuse.  

Sandhini Agarwal:我们有很多下一步的计划。我绝对认为_ChatGPT_的病毒式传播使很多我们知道存在的问题真正涌现出来，成为关键问题--我们想尽快解决的问题。比如，我们知道这个模型仍然非常有偏见。是的，_ChatGPT_在拒绝不良请求方面非常好，但也很容易写出提示，使它不拒绝我们希望它拒绝的东西。

**Liam Fedus:** It’s been thrilling to watch the diverse and creative applications from users, but we’re always focused on areas to improve upon.  

利亚姆-费杜斯：看着用户多样化和创造性的应用，我们感到很兴奋，但我们总是关注需要改进的地方。  

We think that through an iterative process where we deploy, get feedback, and refine, we can produce the most aligned and capable technology. As our technology evolves, new issues inevitably emerge.  

我们认为，通过一个反复的过程，我们部署、获得反馈和完善，我们可以产生最一致的、有能力的技术。随着我们技术的发展，新的问题不可避免地出现了。

**Sandhini Agarwal:** In the weeks after launch, we looked at some of the most terrible examples that people had found, the worst things people were seeing in the wild.  

Sandhini Agarwal。在推出后的几周内，我们看了一些人们发现的最糟糕的例子，人们在野外看到的最糟糕的事情。  

We kind of assessed each of them and talked about how we should fix it.  

我们对他们每个人进行了评估，并讨论了我们应该如何解决这个问题。

**Jan Leike:** Sometimes it’s something that’s gone viral on Twitter, but we have some people who actually reach out quietly.  

扬-雷克。有时是在推特上疯传的东西，但我们有一些人实际上是悄悄地联系的。

**Sandhini Agarwal:** A lot of things that we found were jailbreaks, which is definitely a problem we need to fix.  

Sandhini Agarwal。我们发现的很多东西都是越狱的，这绝对是我们需要解决的问题。  

But because users have to try these convoluted methods to get the model to say something bad, it isn’t like this was something that we completely missed, or something that was very surprising for us.  

但是，由于用户必须尝试这些复杂的方法来让模型说一些不好的东西，这并不是说这是我们完全错过的东西，或者是让我们非常惊讶的东西。  

Still, that’s something we’re actively working on right now. When we find jailbreaks, we add them to our training and testing data. All of the data that we’re seeing feeds into a future model.  

不过，这也是我们现在正在积极努力的事情。当我们发现越狱时，我们将它们加入我们的训练和测试数据。我们看到的所有数据都会被纳入未来的模型。

**Jan Leike:**  Every time we have a better model, we want to put it out and test it. We’re very optimistic that some targeted adversarial training can improve the situation with jailbreaking a lot.  

Jan Leike:每当我们有一个更好的模型，我们就想把它拿出来测试。我们非常乐观地认为，一些有针对性的对抗性训练可以使越狱的情况得到很大的改善。  

It’s not clear whether these problems will go away entirely, but we think we can make a lot of the jailbreaking a lot more difficult.  

目前还不清楚这些问题是否会完全消失，但我们认为我们可以让很多越狱变得更加困难。  

Again, it’s not like we didn’t know that jailbreaking was possible before the release.  

同样，在发布之前，我们并不是不知道越狱是可能的。  

I think it’s very difficult to really anticipate what the real safety problems are going to be with these systems once you’ve deployed them.  

我认为，一旦你部署了这些系统，就很难真正预测到这些系统的真正安全问题是什么。  

So we are putting a lot of emphasis on monitoring what people are using the system for, seeing what happens, and then reacting to that.  

因此，我们非常重视监测人们使用该系统的目的，看看会发生什么，然后对其作出反应。  

This is not to say that we shouldn’t proactively mitigate safety problems when we do anticipate them.  

这并不是说我们不应该在预计到安全问题的时候积极主动地缓解这些问题。  

But yeah, it is very hard to foresee everything that will actually happen when a system hits the real world.  

但是，是的，当一个系统进入现实世界时，很难预见到实际发生的一切。

_In January, Microsoft revealed Bing Chat, a [search chatbot](https://www.technologyreview.com/2023/02/16/1068695/chatgpt-chatbot-battle-search-microsoft-bing-google/) that many assume to be a version of _OpenAI_’s officially unannounced _GPT-4_. (_OpenAI_ says: “Bing is powered by one of our next-generation models that Microsoft customized specifically for search. It incorporates advancements from _ChatGPT_ and GPT-3.5.”) The use of chatbots by tech giants with multibillion-dollar reputations to protect creates new challenges for those tasked with building the underlying models.  

1月，_微软_披露了Bing Chat，这是一个搜索聊天机器人，许多人认为它是_OpenAI_官方未宣布的_GPT-4_的一个版本。(_OpenAI_说："Bing是由我们的下一代模型驱动的，_微软_专门为搜索而定制。它融合了_ChatGPT_和GPT-3.5的进步。")拥有数十亿美元声誉的科技巨头使用聊天机器人，为那些负责建立基础模型的人带来了新的挑战。_

**Sandhini Agarwal:** The stakes right now are definitely a lot higher than they were, say, six months ago, but they’re still lower than where they might be a year from now.  

Sandhini Agarwal。现在的赌注肯定比六个月前要高得多，但仍比一年后的情况要低。  

One thing that obviously really matters with these models is the context they’re being used in.  

对于这些模型，有一件事显然真的很重要，那就是它们被使用的背景。  

Like with Google and Microsoft, even one thing not being factual became such a big issue because they’re meant to be search engines.  

就像谷歌和_微软_一样，即使有一件事不符合事实，也会成为如此大的问题，因为他们的目的是成为搜索引擎。  

The required behavior of a large language model for something like search is very different than for something that’s just meant to be a playful chatbot.  

对于像搜索这样的东西，大型语言模型所要求的行为与那些只是为了成为一个好玩的聊天机器人的东西是非常不同的。  

We need to figure out how we walk the line between all these different uses, creating something that’s useful for people across a range of contexts, where the desired behavior might really vary.  

我们需要弄清楚我们如何在所有这些不同的用途之间行走，创造一些对人们有用的东西，跨越一系列的背景，其中所需的行为可能真的不同。  

That adds more pressure. Because we now know that we are building these models so that they can be turned into products. _ChatGPT_ is a product now that we have the API. We’re building this general-purpose technology and we need to make sure that it works well across everything.  

这增加了更多的压力。因为我们现在知道，我们正在建立这些模型，以便它们可以转化为产品。_ChatGPT_是一个产品，现在我们有了API。我们正在建立这个通用技术，我们需要确保它在所有的东西上都能很好地工作。  

That is one of the key challenges that we face right now.  

这是我们现在面临的关键挑战之一。

**John Schulman**: I underestimated the extent to which people would probe and care about the politics of _ChatGPT_. We could have potentially made some better decisions when collecting training data, which would have lessened this issue. We’re working on it now.  

约翰-舒尔曼：我低估了人们探究和关心_ChatGPT_政治的程度。在收集训练数据时，我们有可能做出一些更好的决定，这样可以减少这个问题。我们现在正在努力解决这个问题。

**Jan Leike:** From my perspective, _ChatGPT_ fails a lot—there’s so much stuff to do. It doesn’t feel like we’ve solved these problems. We all have to be very clear to ourselves—and to others—about the limitations of the technology.  

扬-雷克。从我的角度来看，_ChatGPT_经常失败--有很多事情要做。感觉我们并没有解决这些问题。我们都必须对自己和他人非常清楚地认识到技术的局限性。  

I mean, language models have been around for a while now, but it’s still early days. We know about all the problems they have.  

我的意思是，语言模型已经存在了一段时间，但它仍然是早期的。我们知道他们存在的所有问题。  

I think we just have to be very up-front, and manage expectations, and make it clear this is not a finished product.  

我认为我们必须非常直接，管理好预期，并明确这不是一个完成的产品。
