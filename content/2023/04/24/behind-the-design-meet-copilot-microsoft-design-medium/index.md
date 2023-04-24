---
title: "设计的背后：认识Copilot"
date: 2023-04-24T09:51:49+08:00
updated: 2023-04-24T09:51:49+08:00
taxonomies:
  tags: []
extra:
  source: https://medium.com/microsoft-design/behind-the-design-meet-copilot-2c68182a0e70
  hostname: medium.com
  author: Microsoft Design
  original_title: "Behind-the-Design: Meet Copilot - Microsoft Design - Medium"
  original_lang: en
---

Microsoft最近推出了一款名为Copilot的AI代码编辑器，它可以与开发人员一起编写代码。Copilot使用了OpenAI的GPT模型，可以根据上下文和注释生成代码。这篇文章介绍了Copilot的设计过程和背后的思想。

关键点：
- Copilot是一款AI代码编辑器，可以与开发人员一起编写代码。
- Copilot使用了OpenAI的GPT模型，可以根据上下文和注释生成代码。
- 设计团队的目标是让Copilot成为一个有用的工具，而不是完全取代开发人员。
- Copilot的设计灵感来自于开发人员的日常工作和他们的需求。
- 设计团队采用了用户中心的设计方法，与开发人员合作，以确保Copilot能够满足他们的需求。
- Copilot的设计重点是简单性、可靠性和可用性。

---

_When the system is the product; on crafting the next generation of user experiences  

当系统就是产品时；打造下一代的用户体验_

By Jon Friedman and Kurtis Beavers  

作者：Jon Friedman和Kurtis Beavers

[![A 3D render image with a soft color palette from periwinkle to lavender. The image itself depicts multiple laptop screens with various productivity user interfaces from Microsoft 365 experiences. Each interface depicts  UX for the new conversation box that houses Copilot. In the background of the image, instead of just a white wall, there are luscious light blue and pink hills.](14K3TN5q79-008dmelFfUNg.jpeg)](https://dribbble.com/shots/21084900-1)

A look at the new Copilot experience across Microsoft 365 apps  

看一下微软365应用程序的新Copilot体验

After years of steady but incremental innovation, technologies are emerging that will generate true sea change.  

经过多年稳定但渐进的创新，正在出现的技术将产生真正的巨变。  

At first glance, large language models — the technology behind next-generation AI like OpenAI’s ChatGPT or DALL-E — seem like the missing piece for the possibility of user interfaces that finally adapt themselves to humans.  

乍一看，大型语言模型--像OpenAI的ChatGPT或DALL-E这样的下一代人工智能背后的技术--似乎是最终适应人类的用户界面的可能性所缺少的一块。  

It’s amazing, nascent, and full of possibilities.  

它是惊人的，初生的，充满了可能性。  

But, unlike the AI that we’re used to where autocomplete is used everywhere from custom news feeds to email, this new technology moves us from AI on autopilot to AI as _copilot_. It’s a very different mental model requiring wholly new methods of interaction and our design and research community has been diving deep to learn and understand as much as we can at this junction.  

但是，与我们习惯的人工智能不同的是，从自定义新闻源到电子邮件，自动完成的功能无处不在，这项新技术使我们从自动驾驶的人工智能转向作为副驾驶的人工智能。这是一个非常不同的心理模式，需要全新的互动方法，我们的设计和研究团体一直在深入学习，并尽可能多地了解这个阶段的情况。

For Microsoft Design, we knew we had to have a perspective on how to create a design system that helps the technology to be used in a way that serves humanity, and furthers human agency and collaboration.  

对于微软设计公司来说，我们知道我们必须有一个观点，即如何创建一个设计系统，帮助技术以服务于人类的方式被使用，并促进人类的代理和协作。  

We also knew we needed to create agile, flexible design and engineering processes because with technology this new, constant iteration is needed as customer feedback comes in and we continue learning_._  

我们还知道，我们需要创建敏捷、灵活的设计和工程流程，因为对于这种新技术，随着客户反馈的到来和我们的不断学习，需要不断地进行迭代。

On March 16, we announced [Microsoft 365 Copilot](https://blogs.microsoft.com/blog/2023/03/16/introducing-microsoft-365-copilot-your-copilot-for-work/) — your copilot for work.  

3月16日，我们宣布了Microsoft 365 Copilot--你的工作副驾驶。  

Copilot combines the power of large language models (LLMs) with your data in the Microsoft Graph and Microsoft 365 apps — your calendar, emails, chats, documents, meetings, and more — to turn your words into the most powerful productivity tool on the planet.  

Copilot将大型语言模型（LLMs）的力量与你在Microsoft Graph和Microsoft 365应用程序中的数据--你的日历、电子邮件、聊天记录、文档、会议等--结合起来，将你的话语变成这个星球上最强大的生产力工具。

Copilot is a pioneer in conversational UX, a new frontier of user interface design as paradigm changing as the first touchscreen devices.  

Copilot是对话式用户体验的先驱，这是用户界面设计的一个新领域，就像第一个触屏设备一样改变了范式。  

We believe it has the potential to transform how people interact with and use technology, making things easier and opening new possibilities.  

我们相信它有可能改变人们与技术互动和使用技术的方式，使事情变得更容易，并开启新的可能性。  

Its power, however, must be framed by simple, powerful UX that’s rooted in ethical considerations.  

然而，它的力量必须以简单、强大的用户体验为框架，并以道德考虑为根基。  

With Copilot, we rethought everything from visual identity to interaction design as we aimed to create a truly valuable user experience.  

对于Copilot，我们重新思考了从视觉识别到交互设计的一切，因为我们旨在创造一个真正有价值的用户体验。

[![In this image, layered renderings of UI depict the conversation box that houses Copilot in various different Microsoft 365 apps. Gradients of light purples and oranges are in the background, as well as an undulating 3D ribbon that changes from cobalt blue to lavender to pink.](1_RD5bbP7z25iPtViaITvXg.jpeg)](https://dribbble.com/shots/21084910-2)

Copilot’s UX across various Microsoft 365 experiences  

Copilot在各种Microsoft 365体验中的用户体验

To truly unlock this technology’s potential, we must challenge our current perceptions of technology. Many of our subconscious ideas about AI have been shaped by movies and books.  

为了真正释放这项技术的潜力，我们必须挑战我们目前对技术的看法。我们对人工智能的许多潜意识想法都是由电影和书籍塑造的。  

They often present a binary choice between humans _or_ machines, promoting notions of total automation where machines do everything for us. But the true power of next-generation AI lies in its ability to _augment_ human potential — essentially moving us from AI as autopilot to AI as copilot This is a driving principle of our Copilot experience, where collaborative back-and-forth interactions with the AI ensure you’re always in control, steering Copilot toward your personal goals.  

他们经常提出人类或机器之间的二元选择，提倡完全自动化的概念，让机器为我们做一切。但是，下一代人工智能的真正力量在于其增强人类潜力的能力--本质上是将我们从人工智能作为自动驾驶转变为人工智能作为副驾驶。这是我们Copilot体验的一个驱动原则，在这里，与人工智能的协作性来回互动确保你始终处于控制状态，引导Copilot实现你的个人目标。  

As designers, the UX we craft must foster an understanding of this relationship, helping people adopt new mental models that will move everyone forward in positive, productive, and ethical ways.  

作为设计师，我们设计的用户体验必须促进对这种关系的理解，帮助人们采用新的心理模式，以积极的、富有成效的和道德的方式推动每个人的发展。

These new mental models must be rooted in what we call “appropriate trust,” which is when people understand the technology’s limitations and capabilities and are empowered to use it in responsible ways.  

这些新的心智模式必须植根于我们所说的 "适当的信任"，即人们了解技术的限制和能力，并被授权以负责任的方式使用它。  

While Copilot can be amazing at helping with tasks like generating content or facilitating group collaboration, it may also generate answers that are imperfect or need refining.  

虽然Copilot在帮助生成内容或促进小组合作等任务方面表现出色，但它也可能生成不完善或需要改进的答案。  

The more people understand things like this, the better they’ll get at using it.  

人们对这样的事情了解得越多，他们就会越善于使用它。

On a personal note, I’ve found that Copilot doesn’t just help me communicate more clearly, but through the collaborative process of appropriately working with it, it’s also taught me _how_ to better communicate. It’s helped me grow and, as a designer, it also rekindled my creative spirit because of how dynamic a medium it is. Even when it gets things wrong — which it _does_ and it’s critical to convey that — the process of reading and refining the output can spark fresh ideas, inspiring and affirming what _I_ know to be right. That’s why we’re striving to ensure people always feel empowered and in control.  

就个人而言，我发现Copilot不仅帮助我更清晰地沟通，而且通过与它适当的合作过程，它也教会我如何更好地沟通。它帮助我成长，作为一个设计师，它也重新点燃了我的创造精神，因为它是一个多么充满活力的媒介。即使在它出错的时候--它确实出错了，传达这一点至关重要--阅读和完善输出的过程可以激发新的想法，启发和肯定我知道的正确的东西。这就是为什么我们要努力确保人们始终感到有能力和有控制力。

We often talk about designing in the open here at Microsoft, and it’s hard to think of a more profound context within which to do this.  

在微软，我们经常谈论开放式设计，很难想象有什么更深刻的背景可以做到这一点。  

With this new technology, new capabilities and uses are still emerging; as product makers industry-wide begin building with it, we felt it vital to share the process and frameworks underpinning Copilot so that we can collectively learn, grow, and evolve.  

随着这项新技术的出现，新的能力和用途仍在不断涌现；随着整个行业的产品制造商开始使用这项技术，我们认为分享Copilot的流程和框架至关重要，这样我们就可以共同学习、成长和发展。

## **AI for All Altitudes  

适用于所有海拔高度的人工智能**

Productivity unfolds at multiple altitudes; sometimes you’re in the weeds working on nitty gritty details, while other times you need to see the big picture or strategize.  

生产力在多个高度展开；有时你在杂草丛中处理琐碎的细节，而其他时候你需要看到全局或制定战略。  

The demands of work and life today often surpass our cognitive abilities — creating stress, anxiety, and lost productivity — which is why Copilot’s ability to free people’s creativity, energy, and time is so promising.  

今天，工作和生活的需求常常超过我们的认知能力--造成压力、焦虑和生产力的损失--这就是为什么Copilot能够释放人们的创造力、精力和时间的原因，是非常有前途的。  

By mapping the abilities of LLMs to different human cognitive needs and abilities, we came up with a three-part framework to empower full-spectrum productivity across and within apps: immersive, assistive, and embedded experiences.  

通过将LLM的能力与人类不同的认知需求和能力相匹配，我们提出了一个由三部分组成的框架，以增强应用程序中的全谱系生产力：沉浸式、辅助性和嵌入式体验。

Immersive experiences are geared towards those times when work spans multiple tools, requires deep, contextual understanding, and likely combines the need to create, collaborate, and/or comprehend.  

沉浸式体验是针对那些工作跨越多种工具，需要深入的、有背景的理解，并可能结合创造、协作和/或理解的需要的时候。  

A full-screen experience free from the boundaries of pre-existing apps, the combined power of LLMs with your business data and context allows you to uplevel your skills and unlock productivity.  

全屏体验摆脱了原有应用程序的束缚，LLMs与你的业务数据和背景相结合的力量使你能够提高你的技能并释放生产力。  

From creating drafts of pitch decks or business proposals to helping you prepare for the week’s most important meetings, Copilot will adapt to your needs across work and life to span a wide range of contexts.  

从创建推销文件或商业提案的草稿到帮助你准备一周最重要的会议，Copilot将适应你在工作和生活中的需求，以跨越广泛的背景。

Assistive and embedded experiences, by contrast, are for those times when you want to accelerate the speed and quality of work needed to be done within specific apps, for specific reasons.  

相比之下，辅助性和嵌入式体验是为那些你想在特定的应用程序中为特定的原因加速完成工作的速度和质量的时候而设。  

Cognitively, this is when you’re looking to do more singular types of work and need focus and support to be more creative in Word, more analytical in Excel, more expressive in PowerPoint, more productive in Outlook, or more collaborative in Teams. These show up as adaptive components or modules that scale from embedded experiences within a specific app, to wholly immersive experiences where you’re conversing with Copilot.  

在认知方面，当你想做更多单一类型的工作时，需要专注和支持，以便在Word中更有创造力，在Excel中更有分析力，在PowerPoint中更有表现力，在Outlook中更有生产力，或在Teams中更有协作性。这些显示为自适应组件或模块，从特定应用中的嵌入式体验，到你与Copilot对话的完全沉浸式体验。  

From invocation to instruction, they bring consistency to the overall interaction of Copilot.  

从调用到指令，它们为Copilot的整体互动带来了一致性。  

They also always work within the flow of your current task by knowing the context of what’s on-screen and bringing familiar graphical capabilities to you.  

它们也总是在你当前任务的流程中工作，了解屏幕上的内容，并为你带来熟悉的图形功能。

In combination, these three altitudes of work support not just tasks but _workflows_ across apps and platforms — which are notoriously hard to achieve in digital environments and collaborative, multi-player contexts.  

结合起来，这三个工作高度不仅支持任务，而且支持跨应用程序和平台的工作流程--这在数字环境和协作、多人环境中是众所周知的难以实现。  

By meeting you wherever you’re at within the Microsoft 365 ecosystem, working across your business data to keep knowledge free-flowing across your organization, and automating mundane or repetitive tasks, you can stay in the flow far easier.  

通过在Microsoft 365生态系统中满足你的任何需要，在你的业务数据中工作以保持知识在你的组织中自由流动，并将平凡或重复的任务自动化，你可以更容易地保持流动。

## **A UX foundation designed to empower  

旨在增强用户体验的基础**

When designing Copilot experiences, rooting every design and engineering decision within an ethical framework that prioritized human agency was essential for us.  

在设计Copilot体验时，我们必须将每一个设计和工程决策扎根于以人的能动性为优先的道德框架中。  

From the UI patterns to Copilot’s visual identity, we wanted to express these values.  

从用户界面模式到Copilot的视觉识别，我们希望表达这些价值。  

While we could easily write an entire blog post about each of these, here is an overview of some of the core foundational elements.  

虽然我们可以很容易地写一整篇关于这些的博文，但这里是对一些核心基础要素的概述。

## **Putting the user in control  

将用户置于控制之下**

We had deep discussions about how much control versus how much guidance to give users. Do we completely obfuscate the AI and just give users a button that says “summarize”?  

我们深入讨论了给用户多少控制权和多少指导权的问题。我们是否要把人工智能完全模糊化，只给用户一个 "总结 "的按钮？  

Do we give them an open text field but with some suggestions?  

我们是否给他们一个开放的文本字段，但有一些建议？  

With a higher level of user control comes a higher level of user responsibility, so if we’re putting a customer behind the steering wheel, we can’t have the model hidden behind a button — it’s capabilities must be accessed and understood.  

随着用户控制水平的提高，用户的责任也随之提高，所以如果我们把客户放在方向盘后面，我们不能让模型隐藏在一个按钮后面--它的能力必须被访问和理解。  

That puts the onus on product makers to put sufficient boundaries on things like harmful use cases, but ultimately empowers customers far more than just, say, giving them a list of buttons that they can press that will perform certain capabilities.  

这使产品制造商有责任为有害的使用案例等事情设定足够的界限，但最终赋予客户的权力远远超过，比如说，给他们一个可以按下某些功能的按钮的列表。

In terms of the “how,” natural language is a great way to unlock the power of the model, but only if you grasp the nature and importance of turn-by-turn interactions.  

就 "如何 "而言，自然语言是释放模型力量的一个好方法，但前提是你要掌握逐次互动的性质和重要性。  

Until now, most tech products have been deterministic; the same core interactions happen in precise and repeatable ways. LLMs inch us toward _probabilistic_ products that are imprecise and non-repeatable. It’s not even possible to hardcode the model’s responses because they unfold anew with each interaction.  

到目前为止，大多数科技产品都是确定性的；同样的核心互动以精确和可重复的方式发生。LLMs使我们朝着不精确和不可重复的概率性产品前进。甚至不可能对模型的反应进行硬编码，因为它们在每次互动中都会重新展开。  

When designing conversational UX, we believe turn-by-turn interactions allow you to explore the model’s capabilities, while also steering it back toward intended use cases if needed.  

在设计对话式用户体验时，我们认为逐次的互动可以让你探索模型的能力，同时也可以在需要时引导它回到预定的用例。

## **Education is paramount  

教育是最重要的**

[![A 3D rendering of some of the UI screens used to help educate customers, set against a background of pink, purple, and orange gradients. The text shown invites you to provide feedback about Copilot, suggests that you include human oversight when reviewing results, and introduces and explains what Copilot is.](1fI2IqWXBXOIGMugGIEAd4w.png)](https://dribbble.com/shots/21084919-3)

Customer education is a critical when designing next-gen AI experiences, and we used everything from loading times to zero state design to explain the technology, request feedback, and suggest best practices.  

在设计下一代人工智能体验时，客户教育是一个关键，我们利用从加载时间到零状态设计的一切来解释技术，要求反馈，并建议最佳做法。

Zero state design, fallibility notices, sharing intended use cases, prompt suggestions — we’re optimizing our designs to prioritize and promote education.  

零状态设计、易错性通知、分享预期用例、提示建议--我们正在优化我们的设计，以优先考虑和促进教育。  

Interacting with an LLM is brand new, fairly novel, and potentially intimidating, so we want you to have a clear overview of its capabilities and limitations from the very first time you enter the experience.  

与法律硕士的互动是全新的、相当新颖的，而且有可能令人生畏，所以我们希望你在第一次进入体验时就对其能力和限制有一个清晰的概述。  

That’s a vital part of building responsibly with AI; ethical principles are moot if they’re not baked into the actual UI. So, with zero state design (i.e., what a person sees on screen before performing any kind of interaction), how do we use that real estate to teach people about mistakes the model might make and the need to fact-check outputs?  

这是用人工智能负责任地构建的一个重要部分；如果道德原则没有被纳入实际的用户界面，那么它们就没有意义。那么，通过零状态设计（即一个人在进行任何形式的互动之前在屏幕上看到的东西），我们如何利用这一空间来教导人们关于模型可能犯的错误以及需要对输出进行事实核查？  

We’re also exploring an “AI badge” to go alongside all Copilot outputs that would allow you to learn more about the underlying tech being used anytime you tap or click on it.  

我们还在探索一个 "人工智能徽章"，与所有Copilot的输出一起，让你在任何时候都能了解到所使用的底层技术的情况。

Similarly, what the model puts out is only as good as the prompt that you type in, and prompt writing is a new skill that will take time to master.  

同样，模型放出的东西只和你输入的提示一样好，而提示写作是一项新技能，需要时间来掌握。  

Longer, more detailed prompts tend to give you better results, which is why we created a prompt capabilities menu and include prompt suggestions with hints.  

更长、更详细的提示往往会给你带来更好的结果，这就是为什么我们创建了一个提示能力菜单并包括带有提示的提示建议。  

Over time, as people get more familiar and comfortable with this technology, our designs will likely shift to emphasize that less but, for now, it’s critical.  

随着时间的推移，随着人们对这项技术越来越熟悉和适应，我们的设计可能会转变为较少强调这一点，但是，现在，这一点至关重要。

## **Making it worth the wait  

使之值得等待**

Expectations around the speed of technology have changed since the days of doing the dial-up internet dance and today, we often expect immediacy or darn near close to it.  

自拨号上网的日子以来，人们对技术速度的期望已经发生了变化，今天，我们常常期望即时性或接近即时性。  

With LLMs, however, the sheer scale of the information being processed means that it sometimes takes longer to generate responses than we may expect.  

然而，对于LLM来说，正在处理的信息的庞大规模意味着有时需要比我们预期的更长的时间来产生反应。  

But if those extra seconds save you an hour, it’s worth it and designers can use this wait time as a moment to create transparency, like how we used zero state to educate.  

但是，如果这些额外的几秒钟为你节省了一个小时，那是值得的，设计师可以利用这个等待时间作为创造透明度的时刻，就像我们用零状态来教育一样。  

This could include anything from dialogue boxes reminding people to fact-check the response, to sharing information about how the model generates the answers it does.  

这可能包括任何东西，从提醒人们对回答进行事实核查的对话框，到分享关于模型如何产生答案的信息。  

We want to be thinking about how to use latency to reinforce learnings about the model’s limitations, in addition to ways to creatively infuse delight.  

我们要考虑如何利用延迟来加强对模型局限性的学习，此外还要考虑如何创造性地注入快乐。  

How could we turn a moment of simply waiting into eager anticipation?  

我们怎样才能把简单的等待变成热切的期待？

## **Creating intentional friction  

创造有意的摩擦**

When it comes to ensuring human agency, one of the biggest risks is creating over reliance on the model.  

当涉及到确保人的代理权时，最大的风险之一是造成对模型的过度依赖。  

Copilot isn’t an autopilot, it requires human oversight and collaboration because of its potential to generate inaccurate or wrong answers, but also because the most powerful results are created through back-and-forth interactions where tweaks are made during each turn.  

Copilot不是自动驾驶仪，它需要人类的监督和协作，因为它有可能产生不准确或错误的答案，但也因为最强大的结果是通过来回的互动创造的，在每一个回合中都会进行调整。  

This becomes particularly critical when sharing Copilot results with others (say, a summary of OKRs from a certain fiscal year, an onboarding document, or an event recap).  

在与他人分享Copilot结果时（例如，某个财政年度的OKRs总结、入职文件或活动回顾），这一点变得尤为关键。  

Copilot results link to citations and, in some cases, shares even more information on a source if you hover over it.  

Copilot结果链接到引文，在某些情况下，如果你将鼠标悬停在一个来源上，甚至会分享更多的信息。  

There should still be human review of these, however, and as designers we can create intentional points of friction to help with this.  

然而，这些仍然应该由人类来审查，作为设计师，我们可以创造有意的摩擦点来帮助实现这一点。  

Before someone goes to share something, for example, we can ask if you’ve fact checked it or whether there’s been any human oversight.  

例如，在有人去分享一些东西之前，我们可以问你是否已经检查过事实，或者是否有任何人为的疏忽。  

Content designers have a significant role to play in interactions like this because how we word something can make or break whether someone pays attention to what’s being asked of them.  

内容设计师在这样的互动中扮演着重要的角色，因为我们的措辞可以决定一个人是否注意到对他们的要求。

## **Communicating through a visual i**d**entity**  

通过视觉识别进行沟通

From a visual perspective, we wanted to use things like color and iconography to create and reinforce an understanding of the AI moments across Microsoft products.  

从视觉角度来看，我们希望使用颜色和图标等东西来创造和加强对微软产品的人工智能时刻的理解。  

Using product brand colors and vibrant accents makes the product come alive when specifically interacting with AI features, clearly indicating that the model is active during moments of latency and differentiating it from the surrounding UI.  

使用产品品牌的颜色和充满活力的口音，使产品在具体与人工智能功能互动时变得生动起来，清楚地表明模型在延迟的时刻是活跃的，并将其与周围的用户界面区分开。

The visual identity also clearly shows when Copilot is in use and/or has produced content, our aim being to build trust by allowing you to lean into your judgment insofar as critiquing the output.  

视觉形象也清楚地显示出Copilot在使用中和/或已经产生的内容，我们的目的是通过允许你在批评输出方面的判断来建立信任。

## **Moving forward with a learn-it-all mindset  

以一种学习的心态向前迈进**

Moments like the present are sacred spaces for product makers. There are only so many times when a technology comes along that truly changes the game and across _all_ disciplines, we’re keenly aware of the power and impact of LLMs. And with Copilot, it’s not just about LLMs as a medium, but the ecosystem it lives within.  

像现在这样的时刻是产品制造商的神圣空间。一个真正改变游戏规则的技术的出现只有那么几次，在所有学科中，我们都敏锐地意识到LLMs的力量和影响。对于Copilot来说，这不仅仅是关于LLMs作为一种媒介，而是它所处的生态系统。  

Microsoft 365 is one of the most powerful productivity suites in the world; the breadth of its abilities are why governments, hospitals, and schools alike run on it.  

微软365是世界上最强大的生产力套件之一；其能力的广泛性是政府、医院和学校都使用它的原因。  

When you then situate the power of LLMs within it, there’s unique and remarkable potential to up level human abilities and support human needs.  

当你把法律硕士的力量放在其中时，就会有独特和显著的潜力来提高人类的能力和支持人类的需求。

This is an exciting, humbling, and significant responsibility for the design community and the default settings, design tenets, and UX frameworks we choose matter deeply.  

对于设计界来说，这是一个令人兴奋的、谦卑的和重要的责任，我们选择的默认设置、设计原则和用户体验框架非常重要。  

Just as important are the processes we embrace around emergent technologies.  

同样重要的是我们围绕新兴技术所采取的程序。  

New models could arise within the next six months to a year, and we need agile, flexible design and engineering processes that leave ample room to incorporate new research insights and customer feedback.  

新模式可能在未来六个月到一年内出现，我们需要敏捷、灵活的设计和工程流程，为纳入新的研究见解和客户反馈留出充足的空间。  

That’s why we’re previewing these designs, as new as they are — to learn from enterprise customers in a safe preview environment.  

这就是为什么我们要预览这些设计，尽管它们是新的--在一个安全的预览环境中向企业客户学习。  

We can’t design behind closed doors, in a tech vacuum or bubble disconnected from everyday people.  

我们不能闭门造车，不能在技术真空或与日常人脱节的泡沫中进行设计。  

We must actively seek feedback, embrace a learn-it-all attitude, and share learnings by designing in the open.  

我们必须积极寻求反馈，抱着学习的态度，并通过公开设计来分享学习成果。  

We must also always seek to root our builds in ethical considerations and universal human needs; the tech itself may change, but those remain far more durable.  

我们还必须始终寻求将我们的建设植根于道德考虑和人类的普遍需求；技术本身可能会改变，但这些仍然更持久。

And as for Microsoft Design, we’ll continue to share our learnings, updates, and designs as the year progresses, so stay tuned and please share your feedback openly and often!  

至于微软设计，我们将继续分享我们的学习、更新和设计，随着这一年的进展，请继续关注，并请公开和经常分享您的反馈！

_To stay in the know with Microsoft Design, follow us on_ [_Twitter_](http://www.twitter.com/microsoftdesign) _and_ [_Instagram_](http://www.instagram.com/microsoft.design)_, or join our_ [_Windows_](http://insider.windows.com/) _or_ [_Office_](https://insider.office.com/) _Insider program. And if you are interested in working with us at Microsoft, head over to_ [_aka.ms/DesignCareers_](http://aka.ms/designcareers)_._  

要了解微软设计，请在Twitter和Instagram上关注我们，或加入我们的Windows或Office Insider计划。如果你有兴趣在微软工作，请访问 aka.ms/DesignCareers 。
