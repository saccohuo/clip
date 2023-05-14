---
title: "使用ChatGPT作为技术写作助手"
date: 2023-04-27T15:00:08+08:00
updated: 2023-04-27T15:00:08+08:00
taxonomies:
  tags: []
extra:
  source: https://martinfowler.com/articles/2023-chatgpt-tech-writing.html
  hostname: martinfowler.com
  author: Mike Mason
  original_title: "Using ChatGPT as a technical writing assistant"
  original_lang: en
---

本文介绍了作者在使用 ChatGPT 作为写作助手时的目标和期望，以及在撰写 Thoughtworks 技术雷达时的具体应用。同时，文章还探讨了网络钩子的安全问题和应对措施。

Key points:
1. 作者使用 ChatGPT 作为写作助手，希望能够更高效地撰写技术文章。
2. 作者在撰写 Thoughtworks 技术雷达时，使用 ChatGPT 来协助完成 “blips” 和文章。
3. 文章探讨了网络钩子的安全问题，提出了应对措施。
4. 文章介绍了 ChatOps 和 webhooks 的相关概念。
5. 作者希望通过使用 ChatGPT 和其他技术手段，提高技术文章的质量和效率。

Keywords: ChatGPT、技术文章、Thoughtworks 技术雷达、网络钩子、ChatOps、安全问题。

---

In recent weeks, I’ve been exploring the use of ChatGPT within a professional context. As a consultant I write extensively about technology and software, advise clients, and collaborate with internal teams. To avoid any potential intellectual property issues, I consulted both my boss and one of the company lawyers.  

最近几周，我一直在探索ChatGPT在专业背景下的使用。作为一名顾问，我写了大量关于技术和软件的文章，为客户提供建议，并与内部团队合作。为了避免任何潜在的知识产权问题，我同时咨询了我的老板和公司的一位律师。  

I specifically avoiding using ChatGPT in any client-related context. Instead, I focused on employing ChatGPT for technical writing intended for public consumption, thereby minimizing the possibility of inadvertently exposing proprietary information to the AI.  

我特别避免在任何与客户有关的情况下使用ChatGPT。相反，我专注于将ChatGPT用于供公众消费的技术写作，从而将无意中向AI暴露专有信息的可能性降到最低。

![](card.png)

We like to include an image for our twitter card, for this one, we naturally went to Stable Diffusion.  

我们喜欢为我们的twitter卡片附上一张图片，对于这张卡片，我们很自然地选择了稳定扩散。  

We used the prompt “concept art of a human and an ai facing each other, collaborating using an advanced holographic display, close up, mid-length framing” (Stable Diffusion v2-1\_768-ema-pruned, model hash ad2a33c361, seed 564306172)  

我们使用的提示是 "人类和AI面对面，使用先进的全息显示器进行合作的概念艺术，近距离，中长框"（稳定扩散v2-1\_768-ema-pruned，模型哈希ad2a33c361，种子564306172）。

## Goals and expectations 目标和期望

When I first considered using ChatGPT as a writing assistant, I had a few specific goals in mind. One of the main tasks I hoped it would help me with was crafting ‘blips’ for the Thoughtworks [Technology Radar](https://www.thoughtworks.com/radar). The radar covers over 100 individual technologies, and while our team engages in detailed discussions about each of them, translating those notes into a coherent paragraph can be challenging.  

当我第一次考虑使用ChatGPT作为写作助手时，我有几个具体的目标。我希望它能帮助我完成的主要任务之一是为Thoughtworks技术雷达制作 "提示"。该雷达涵盖了100多项单独的技术，虽然我们的团队对每项技术都进行了详细的讨论，但将这些笔记翻译成一个连贯的段落可能是一个挑战。  

I was hopeful that ChatGPT could streamline this process and make it more efficient.  

我希望ChatGPT能够简化这一过程，使其更有效率。

In addition to the blips, I write an accompanying article called “[Macro Trends in the Technology Industry](https://www.thoughtworks.com/insights/blog/technology-strategy/macro-trends-tech-industry-april-2023)” that delves into the broader themes and patterns we observe in the field. I was curious to see if ChatGPT could play a role in shaping this piece, providing insights or even contributing content.  

除了这些片段，我还写了一篇名为《技术行业的宏观趋势》的文章，深入探讨我们在该领域观察到的更广泛的主题和模式。我很想知道ChatGPT是否能在这篇文章中发挥作用，提供见解或甚至贡献内容。

Lastly, we also adapt the Technology Radar for a business context, aiming to make its high-level themes more accessible to a non-technical audience. This often involves simplifying complex concepts and presenting them in a more digestible format.  

最后，我们还为商业环境调整了技术雷达，旨在使其高层次的主题更容易被非技术性的受众所接受。这通常涉及到简化复杂的概念，并以更容易消化的形式呈现出来。  

I wanted to explore the potential of ChatGPT in assisting with this task, helping us create content that effectively communicates our ideas to a wider readership.  

我想探索ChatGPT在协助完成这项任务方面的潜力，帮助我们创建内容，将我们的想法有效地传达给更多的读者。

## Radar Blip: Casual management of webhooks - Hold  

Radar Blip：网络钩子的休闲管理 - Hold

Mike

Hello. Please help me write a 'blip' in the style of the Thoughtworks technology radar, about the dangers of "Casual Management of Webhooks". Summarize the notes and discussion below:  

你好。请帮我按照Thoughtworks技术雷达的风格写一篇关于 "Webhooks的随意管理 "的危险的 "爆料"。总结一下下面的笔记和讨论：

With the rise of remote working we are continuing to see growing adoption of chat collaboration platforms (e.g. Slack, Google Chat, Microsoft Teams) and with it a rise in "ChatOps".  

随着远程工作的兴起，我们继续看到聊天协作平台（如Slack、Google Chat、Microsoft Teams）被越来越多的人采用，随之而来的是 "ChatOps "的崛起。  

Most chat collaboration platforms offer webhooks as a simple way to automate sending messages and notifications to channels, and much developer platform tooling (e.g.  

大多数聊天协作平台都提供webhooks，作为自动向频道发送消息和通知的简单方法，而且许多开发者平台工具（如  

CI/CD software, monitoring software, etc) is building out first class support for utilising these webhooks. However there is a tendency to treat these webhooks as configuration, rather than as a secret/credential.  

CI/CD软件、监控软件等）正在为利用这些webhooks建立一流的支持。然而，有一种趋势是将这些网络钩子作为配置，而不是作为一种秘密/证书。  

We see this tendency manifesting in how chat tools present webhooks, how teams treat and store webhooks (e.g. committing them in plain text to a repo), and how integrated tooling treats webhooks (e.g. exposing them in plain text).  

我们看到这种趋势表现在聊天工具如何展示网络钩子，团队如何对待和存储网络钩子（例如以纯文本形式提交到 repo），以及集成工具如何对待网络钩子（例如以纯文本形式公开）。  

This is a security smell that can open up an organisation to phishing attacks.  

这是一个安全问题，可能会使一个组织受到网络钓鱼攻击。

ChatOps webhooks are a credential: they offer privileged access to an internal space. In some cases, they directly contain API keys that can be extracted and utilised directly.  

ChatOps webhooks是一种凭证：它们提供对内部空间的特权访问。在某些情况下，它们直接包含API密钥，可以直接提取和利用。  

Not treating them as secrets opens up the possibility that they can be used for phishing, and that phishing is more likely to be successful because of the lack of awareness of this type of attack.  

不把它们当作秘密，就有可能被用来进行网络钓鱼，而网络钓鱼更有可能成功，因为人们对这种类型的攻击缺乏认识。  

Webhooks in git repos can easily be extracted and used to craft and send a fraudulent payload, which the user may have no reason to doubt and no way to authenticate.  

git repos中的Webhooks很容易被提取并用于制作和发送欺诈性的有效载荷，用户可能没有理由怀疑，也没有办法进行认证。  

There has not been major reported incidents of this type in the wild which only adds to the complacency.  

在野外还没有关于这类事件的重大报道，这只会增加人们的自满情绪。  

In order to mitigate this threat we need to see a shift, both in the culture of teams who are handling these webhooks, and in the culture of software developers who are building integrations with ChatOps platforms.  

为了减轻这种威胁，我们需要看到一种转变，既包括处理这些webhooks的团队的文化，也包括与ChatOps平台建立集成的软件开发商的文化。

ChatGPT

Here’s a blip in the style of the Thoughtworks technology radar:  

这里有一个Thoughtworks技术雷达风格的小插曲：

Dangers of Casual Management of Webhooks: A Security Smell  

偶然管理Webhooks的危险：安全嗅觉

As remote work continues to rise, so does the adoption of chat collaboration platforms and ChatOps.  

随着远程工作的不断增加，对聊天协作平台和ChatOps的采用也在不断增加。  

These platforms often offer webhooks as a simple way to automate sending messages and notifications, but we are noticing a concerning trend of treating webhooks as configuration, rather than as a secret/credential.  

这些平台通常提供webhooks作为自动发送消息和通知的简单方法，但我们注意到一种令人担忧的趋势，即把webhooks当作配置，而不是当作一种秘密/证书。  

This can lead to phishing attacks and compromised internal spaces.  

这可能导致网络钓鱼攻击和内部空间被破坏。

Webhooks are credentials that offer privileged access to an internal space and may contain API keys that can be easily extracted and utilized directly. Not treating them as secrets opens up the possibility of successful phishing attacks.  

Webhooks是提供对内部空间的特权访问的凭证，可能包含可以轻松提取和直接利用的API密钥。不把它们当作秘密来对待，就会为成功的网络钓鱼攻击提供可能。  

Webhooks in git repos can easily be extracted and used to send fraudulent payloads, which the user may not have any way to authenticate.  

git仓库中的Webhooks可以很容易地被提取并用于发送欺诈性的有效载荷，而用户可能没有任何方法来验证。

To mitigate this threat, teams handling webhooks need to shift their culture and treat webhooks as sensitive credentials.  

为了减轻这种威胁，处理网络钩子的团队需要转变他们的文化，将网络钩子视为敏感的凭证。  

Software developers building integrations with ChatOps platforms must also be mindful of this risk and ensure that webhooks are handled with proper security measures. Let’s not wait for a major incident to occur before taking action.  

构建与ChatOps平台集成的软件开发商也必须注意这种风险，并确保以适当的安全措施处理Webhooks。我们不要等到发生重大事件时才采取行动。

**Discussion**

This output was pretty good, especially the first paragraph that justifies the rise of ChatOps and explains how webhooks are related.  

这个输出相当不错，尤其是第一段，证明了ChatOps的兴起，并解释了webhooks的关系。  

The final paragraph is some kind of “call to action” which isn’t really right for a Radar blip, but it was easy enough to remove.  

最后一段是某种 "行动呼吁"，这对于雷达突发事件来说其实并不合适，但很容易就能删除。  

Thoughtworks has published the Technology Radar for more than ten years now, so simply asking for output “in the style of the Thoughtworks Technology Radar” creates text that has more or less the right kind of style for a Radar blip.  

Thoughtworks出版《技术雷达》已经有十多年了，所以只要要求输出 "Thoughtworks技术雷达的风格"，就能创造出或多或少符合雷达提示风格的文本。  

If I wanted something in a different style I would have needed to be more specific in my prompt. You can see the final [casual management of webhooks](https://www.thoughtworks.com/radar/techniques/casual-management-of-webhooks) text on the Radar site, to see where we ended up after editing, including a round of company-wide feedback.  

如果我想要不同风格的东西，我就需要在我的提示中更加具体。你可以在雷达网站上看到最终的网络钩子文本的随意管理，看看我们在编辑后的结果，包括一轮全公司的反馈。

## Radar Blip: Giskard - Assess 雷达突发事件：Giskard - 评估

In the style of the thoughtworks technology radar, write a 'blip' for "Giskard". Incorporate the following notes, and keep the resulting write up to two paragraphs.  

按照思想工作技术雷达的风格，为 "Giskard "写一个 "blip"。纳入以下说明，并将所写内容保持在两段以内。

Giskard is Quality Assurance for AI models, e.g. helps find biases  

Giskard是人工智能模型的质量保证，例如，帮助发现偏见。

why

Seems like a new kind of tool, makes collaboration between data scientists and business stakeholders / SMEs easy. No real experience with the tool yet.  

似乎是一种新的工具，使数据科学家和商业利益相关者/中小企业之间的合作变得容易。目前还没有使用该工具的实际经验。

Person A: People I talked to highlighted the quality assurance part, you can write a variety of tests for it  

人A：与我交谈的人强调了质量保证部分，你可以为它编写各种测试。

Person B: The "why" here is copied from website, but what IS it actually that makes the collab easier?  

B君：这里的 "为什么 "是从网站上复制的，但实际上是什么让合作更容易？

Person C: When we are reasoning about models, lots of business implications involved, so bias avoidance can be quality metrics for a model; you can codify acceptance criteria for your models, together with business  

C君：当我们对模型进行推理时，涉及到很多商业影响，所以避免偏见可以成为模型的质量指标；你可以将模型的验收标准与商业标准一起编入法典。

This one is most about data quality compared to other tools  

与其他工具相比，这个最关乎数据质量

Giskard emerges as a novel Quality Assurance solution for AI models, specifically designed to identify and mitigate biases. By focusing on data quality, Giskard distinguishes itself from other tools in the market.  

Giskard作为一种新颖的人工智能模型质量保证解决方案出现，专门用于识别和减轻偏见。通过专注于数据质量，Giskard区别于市场上的其他工具。  

It fosters collaboration between data scientists and business stakeholders, enabling them to jointly establish acceptance criteria for AI models based on bias avoidance and other essential quality metrics.  

它促进了数据科学家和商业利益相关者之间的合作，使他们能够共同建立基于避免偏差和其他基本质量指标的人工智能模型的验收标准。  

This ensures that the model outcomes are better aligned with business objectives, while also minimizing the risks associated with biased predictions.  

这确保了模型结果与业务目标更好地保持一致，同时也将有偏差的预测所带来的风险降到最低。

Though we have limited hands-on experience with Giskard, conversations with users have emphasized its ability to support a wide range of tests for quality assurance.  

尽管我们对Giskard的实践经验有限，但在与用户的交谈中，我们强调它有能力支持广泛的质量保证的测试。  

The tool’s unique value proposition lies in facilitating seamless collaboration between technical and non-technical stakeholders, making it easier to reason about models and their business implications.  

该工具的独特价值主张在于促进技术和非技术利益相关者之间的无缝协作，使其更容易推理模型及其业务影响。  

By allowing teams to codify their criteria, Giskard promotes transparency, streamlines the development process, and helps organizations build more robust and ethical AI models.  

通过允许团队编纂他们的标准，Giskard促进了透明度，简化了开发过程，并帮助组织建立更强大和道德的AI模型。

**Discussion**

The text is clearly way too optimistic for an ‘assess’ blip on the Radar. The fact that ChatGPT has been trained on tons of marketing pages on the Internet, as well as fine tuned using human feedback, has led to the bot saying things that we never would.  

对于雷达上的 "评估 "小插曲来说，这些文字显然太乐观了。事实上，ChatGPT已经在互联网上的大量营销页面上进行了训练，并利用人类的反馈进行了微调，这导致机器人说了一些我们永远不会说的话。  

Words like ‘novel’ and ‘unique’ are something I’d edit and remove.  

像 "新颖 "和 "独特 "这样的词，我都会编辑并删除。

What was very interesting here though is the response from one of our machine learning experts in Finland.  

不过，这里非常有趣的是我们在芬兰的一位机器学习专家的回应。  

She said it sounded like the blip had been written by a junior person with very little understanding of the typical ML workflow, and she made some quite significant changes before the blip text was ready for publication.  

她说，这听起来像是由一个对典型的ML工作流程了解甚少的初级人员写的，她在Blip文本准备出版前做了一些相当大的修改。  

I’m not an expert in this particular tool — although I’ve used a few ML tool chains — and this critical feedback highlights the fact that ChatGPT output generally requires quite skilled experts to review and edit. Here's the [Giskard blip on the Radar](https://www.thoughtworks.com/radar/tools/giskard) after human review and editing.  

我不是这个特定工具的专家--虽然我用过一些ML工具链--而这个批评性的反馈突出了这样一个事实：ChatGPT的输出一般需要相当熟练的专家来审查和编辑。这是经过人工审查和编辑后的Giskard在雷达上的闪光点。

## Macro trends article 宏观趋势文章

I'm the author of the Thoughtworks "macro trends" series of articles. Are you familiar with those? Can you tell me what they are about?  

我是Thoughtworks的 "宏观趋势 "系列文章的作者。你对这些文章熟悉吗？你能告诉我它们是关于什么的吗？

As an AI language model, I'm familiar with a wide range of topics, including the Thoughtworks "macro trends" series of articles. The series aims to identify and analyze the significant macro-level trends that are shaping technology, business, and society.  

作为一个人工智能语言模型，我熟悉广泛的主题，包括Thoughtworks的 "宏观趋势 "系列文章。该系列旨在识别和分析影响技术、商业和社会的重大宏观趋势。  

These trends often have a global impact and are driven by factors such as technological advancements, changes in consumer behavior, economic shifts, and global events.  

这些趋势往往具有全球影响，并由技术进步、消费者行为变化、经济转变和全球事件等因素驱动。  

By understanding these macro trends, organizations and individuals can better adapt to change and capitalize on emerging opportunities.  

通过了解这些宏观趋势，组织和个人可以更好地适应变化并利用新出现的机会。

Some of the key topics covered in these articles may include (but are not limited to):  

这些文章中涉及的一些关键主题可能包括（但不限于）：

The rise of artificial intelligence and machine learning  

人工智能和机器学习的崛起

The increasing importance of data privacy and security  

数据隐私和安全的重要性日益增加

The role of digital transformation in businesses  

数字化转型在企业中的作用

The growing impact of climate change and sustainability efforts  

气候变化和可持续性努力的影响越来越大

The expansion of the Internet of Things (IoT) and connected devices  

物联网（IoT）和连接设备的扩展

The evolution of the workforce and the future of work  

劳动力的演变和工作的未来

The development of new technologies, such as blockchain and quantum computing  

新技术的发展，如区块链和量子计算

The specifics of each article may vary depending on the time they were written and the trends relevant at that time.  

每篇文章的具体内容可能有所不同，这取决于它们的写作时间和当时的相关趋势。

OK, I think you have the idea. I would say it's not really about society, though, it's more of a tech industry focus.  

好吧，我想你有这个想法。我想说的是，这并不是真正的社会问题，但它更像是一个科技行业的焦点。

I have made some notes on new trends for a new article. I'd like you to help me express my notes as sections of a macro trends article.  

我为一篇新的文章做了一些关于新趋势的笔记。我希望你能帮助我把我的笔记表达成宏观趋势文章的章节。

The first trend is around knowledge management for teams. We discussed interesting tools Logseq and Obsidian, and we wrote blips about them. For logseq we wrote:  

第一个趋势是围绕团队的知识管理。我们讨论了有趣的工具Logseq和Obsidian，并写了关于它们的短文。对于Logseq，我们写道：

Team knowledge management is a familiar concept with teams using tools such as wikis to store information and onboard new team members. Some of our teams now prefer to use logseq as a team knowledge base.  

团队知识管理是一个熟悉的概念，团队使用维基等工具来存储信息和加入新的团队成员。我们的一些团队现在更喜欢使用logseq作为团队知识库。  

An open-source knowledge-management system, loqsec is powered by a graph database, helps users organize thoughts, notes and ideas and can be adapted for team use with Git-based storage.  

loqsec是一个开源的知识管理系统，由一个图形数据库驱动，帮助用户组织思想、笔记和想法，并可以通过基于Git的存储方式适应团队使用。  

Logseq allows teams to build a democratic and accessible knowledge base, providing each member with a personalized learning journey and facilitating efficient onboarding.  

Logseq允许团队建立一个民主和可访问的知识库，为每个成员提供一个个性化的学习之旅，并促进高效的入职培训。  

However, as with any knowledge management tool, teams will need to apply good curation and management of their knowledge base to avoid information overload or disorganization.  

然而，与任何知识管理工具一样，团队将需要对其知识库进行良好的整理和管理，以避免信息过载或混乱。

While similar functionality is available in tools like Obsidian, the key difference lies in Logseq's focus on consumption, with paragraph-based linking enabling team members to quickly find the relevant context without having to read an entire article.  

虽然像Obsidian这样的工具也有类似的功能，但关键的区别在于Logseq对消费的关注，基于段落的链接使团队成员能够快速找到相关的背景，而不必阅读整篇文章。

Can you turn this into a macro trends article section about knowledge management tools for teams? It should be about 3 paragraphs long.  

你能把它变成一篇关于团队知识管理工具的宏观趋势文章部分吗？它应该是3段左右的长度。

Emerging Trend: Next-Generation Knowledge Management Tools for Teams  

新兴趋势：新一代的团队知识管理工具

In today's fast-paced technology landscape, effective knowledge management is more crucial than ever for teams to stay competitive and agile.  

在当今快节奏的技术环境中，有效的知识管理对于团队保持竞争力和敏捷性比以往任何时候都更加关键。  

Traditional tools like wikis have been commonly used to store and share information, but recently there has been a surge of interest in more advanced and versatile knowledge management systems. These new tools, such as Logseq and Obsidian, offer innovative features that are transforming the way teams manage, access, and engage with their collective knowledge.  

像维基这样的传统工具通常被用来存储和分享信息，但最近，人们对更先进、更多功能的知识管理系统的兴趣激增。这些新工具，如Logseq和Obsidian，提供了创新的功能，正在改变团队管理、访问和参与集体知识的方式。

Logseq, an open-source knowledge-management system, is a prime example of this shift. Powered by a graph database, it helps users organize thoughts, notes, and ideas and can be adapted for team use with Git-based storage.  

Logseq，一个开源的知识管理系统，是这种转变的一个典型例子。它由一个图形数据库提供动力，帮助用户组织思想、笔记和想法，并且可以通过基于Git的存储来适应团队使用。  

Logseq's unique approach enables teams to build a democratic and accessible knowledge base, providing each member with a personalized learning journey and facilitating efficient onboarding.  

Logseq的独特方法使团队能够建立一个民主和可访问的知识库，为每个成员提供一个个性化的学习旅程，并促进高效的入职培训。  

Its paragraph-based linking feature allows team members to quickly find the relevant context without having to read an entire article, emphasizing its focus on consumption.  

其基于段落的链接功能使团队成员能够迅速找到相关的背景，而不必阅读整篇文章，强调了其对消费的关注。  

However, as with any knowledge management tool, teams will need to apply good curation and management practices to avoid information overload or disorganization.  

然而，与任何知识管理工具一样，团队将需要应用良好的策划和管理实践，以避免信息过载或混乱。

Similarly, Obsidian offers robust knowledge management capabilities, but with a stronger emphasis on content creation.  

同样，黑曜石提供了强大的知识管理能力，但更强调内容的创造。  

While both tools provide valuable features for managing and accessing information, their differences highlight the evolving nature of team knowledge management. As these tools continue to develop and gain traction, they are set to redefine the way teams collaborate and learn, ultimately driving innovation and productivity in the tech industry.  

虽然这两种工具都为管理和访问信息提供了有价值的功能，但它们的差异突出了团队知识管理不断发展的本质。随着这些工具的不断发展和普及，它们将重新定义团队的合作和学习方式，最终推动科技行业的创新和生产力。

**Discussion**

Similar to the Radar blips drafted by ChatGPT, this text is overly ‘bubbly.’ Phrases like “more crucial than ever” just sound a little too hyperbolic.  

与ChatGPT起草的Radar blips类似，这段文字也过于 "冒泡 "了。像 "比以往任何时候都更关键 "这样的短语，听起来有点太夸张了。  

I found this was a common theme – ChatGPT is just way too optimistic and happy sounding, and almost ends up a little bit ‘bland’ because of this.  

我发现这是一个共同的主题--ChatGPT只是听起来太过乐观和快乐，并且几乎因为这个而最终有点 "平淡"。  

But a quick edit pass can fix this and introduce words that are more like the ones I would really use to describe this trend.  

但快速的编辑通过可以解决这个问题，并引入更像我真正用来描述这种趋势的词语。

Additionally, ChatGPT seems to always structure its responses as introduction, information, summary. It seems to do this whether you have asked an open-ended question or are asking it to help you create a section of an article.  

此外，ChatGPT似乎总是以介绍、信息、总结的方式来安排其答复。无论你是问了一个开放式的问题，还是要求它帮助你创建文章的一个部分，它似乎都会这样做。  

I found I repeatedly needed to discard or condense the opening and closing paragraphs of ChatGPT’s output.  

我发现我多次需要舍弃或浓缩ChatGPT输出的开头和结尾段落。

You can find the [finished macro trends article](https://www.thoughtworks.com/insights/blog/technology-strategy/macro-trends-tech-industry-april-2023) on the Thoughtworks website.  

你可以在Thoughtworks网站上找到完成的宏观趋势文章。

## Adapting the radar for a less-technical audience  

为技术含量较低的受众改编雷达

I need to rewrite some stories that are told in a technical context, but for a less technical business audience.  

我需要重写一些在技术背景下讲述的故事，但要为技术性不强的商业听众服务。

Accessibility has been an important consideration for organizations for many years.  

多年来，无障碍环境一直是各组织的一个重要考虑因素。  

Recently, we've highlighted the experiences of our teams with the ever-growing set of tools and techniques that add improved accessibility to development, and several regions our teams highlighted awareness of these techniques via awareness campaigns.  

最近，我们强调了我们的团队对不断增长的工具和技术的经验，这些工具和技术为开发增加了改进的可及性，我们的几个地区的团队通过宣传活动强调了对这些技术的认识。  

We've featured accessibility-related blips on continuous integration pipeline development, \[design playbooks\](/radar/techniques/accessibility-annotations-in-designs), \[intelligent guided accessibility testing\](/radar/techniques/intelligent-guided-accessibility-tests), \[linting\](/radar/tools/axe-linter) and \[unit testing\](/radar/tools/ibm-equal-access-accessibility-checker).  

我们在持续集成管道开发、\[设计手册\](/radar/techniques/accessibility-annotations-in-designs)、\[智能引导的无障碍测试\](/radar/techniques/intelligent-guided-accessibility-tests)、\[提示\](/radar/tools/ax-linter)和\[单元测试\](/radar/tools/ibm-equal-accessibility-checker)方面介绍过与无障碍性相关的亮点。  

Growing awareness around this important topic is welcome; techniques that give more people access to functionality in improved ways can only be a good thing.  

围绕这一重要议题的认识不断提高是值得欢迎的；让更多人以改进的方式获得功能的技术只能是一件好事。

Can you rewrite this in the form "what is it" (one or two sentences) and "business context" (one paragraph) ?  

你能以 "是什么"（一两句话）和 "商业背景"（一段）的形式重写吗？

What is it? 它是什么？

Accessibility has become increasingly important for organizations, with a growing set of tools and techniques available to improve it in development processes and awareness campaigns promoting its significance.  

可访问性对组织来说已经变得越来越重要，有越来越多的工具和技术可用于改善开发过程中的可访问性，以及宣传其重要性的意识活动。

Business context:

As businesses prioritize accessibility, they are adopting various tools and techniques that make their products and services more inclusive.  

随着企业优先考虑无障碍性，他们正在采用各种工具和技术，使其产品和服务更具包容性。  

These include continuous integration pipeline development, design playbooks, intelligent guided accessibility testing, linting, and unit testing.  

这些包括持续集成管道开发、设计游戏书、智能引导的无障碍测试、提示和单元测试。  

Embracing accessibility not only benefits a wider range of users but also enhances a company's reputation for being socially responsible and inclusive, ultimately fostering positive outcomes for both the organization and its customers.  

拥抱无障碍环境不仅使更多的用户受益，还能提高公司在社会责任和包容性方面的声誉，最终为组织和客户带来积极的结果。

Can you describe 'accessibility' in one sentence?  

你能用一句话来描述 "可及性 "吗？

Accessibility refers to the design of products, services, and environments that ensure people with disabilities can effectively and easily access, use, and interact with them.  

无障碍性是指产品、服务和环境的设计，以确保残疾人能够有效和方便地获取、使用和互动。

Based on this, what advice would you give businesses around accessibility?  

在此基础上，您对企业在无障碍环境方面有何建议？

Businesses should prioritize accessibility by designing and adapting their products, services, and environments to be inclusive and user-friendly for people with disabilities, thereby demonstrating social responsibility, enhancing their reputation, and reaching a broader customer base.  

企业应优先考虑无障碍环境，设计和改造其产品、服务和环境，使其对残疾人具有包容性和用户友好性，从而体现出社会责任，提高其声誉，并接触到更广泛的客户群。

**Discussion**

I was very happy with this output. ChatGPT provided a very good “business readable” version of the Radar theme and this definitely saved me some time. I thought the advice it generated was pretty good.  

我对这个产出非常满意。ChatGPT提供了一个非常好的 "商业可读 "版本的雷达主题，这无疑为我节省了一些时间。我认为它所产生的建议是相当好的。

## Strengths and weaknesses of ChatGPT in technical writing  

ChatGPT在技术写作中的优势和劣势

On balance, I’d say ChatGPT has proven to be a useful tool in the technical writing process, but it’s not without its foibles. Understanding its strengths and weaknesses can help you to get the most out of it.  

总的来说，我认为ChatGPT已被证明是技术写作过程中的一个有用工具，但它也不是没有缺点。了解它的优点和缺点可以帮助你最大限度地发挥它的作用。

Strengths:

-   **Knowledge:** ChatGPT excels at instant recall of similar situations, facts, and ways others have discussed a subject.  
    
    知识：ChatGPT擅长即时回忆类似的情况、事实和其他人讨论某个主题的方式。  
    
    This allows it to bring up additional points that might be relevant to the topic at hand, prompting me as an author to write more or cover additional related information.  
    
    这使得它能够提出可能与当前主题相关的其他观点，促使我作为作者写更多的内容或涵盖更多的相关信息。
-   **Time-savings:** Output from ChatGPT serves as a good starting point for writing, saving time by providing initial content that can be refined or expanded upon.  
    
    节约时间：ChatGPT的输出可以作为一个很好的写作起点，通过提供可以完善或扩展的初始内容来节省时间。
-   **Suggested additions:** ChatGPT can offer suggestions for additional content or sections, and they are generally quite useful.  
    
    建议添加的内容：ChatGPT可以提供额外内容或章节的建议，一般来说，这些建议是相当有用的。  
    
    I fed it an outline for this article and it proposed “goals and expectations” and “strategies for improving ChatGPT’s output” as additional sections, both of which I liked and included in my writing process.  
    
    我给它提供了这篇文章的大纲，它提出了 "目标和期望 "和 "改善ChatGPT产出的策略 "作为附加部分，这两个部分我都很喜欢，并纳入了我的写作过程。

Weaknesses:

-   **Accuracy and depth:** ChatGPT’s responses may not always be accurate or in-depth, requiring manual review and revision. It also has an “information cutoff” date, so recent events or updates won’t be reflected in its output.  
    
    准确性和深度：ChatGPT的回答不一定准确或深入，需要人工审查和修改。它也有一个 "信息截止日期"，所以最近的事件或更新不会反映在其输出中。
-   **Overly positive and optimistic:** The AI tends to produce content that is too positive and optimistic, which might not be suitable when a critical eye is needed, as with the Technology Radar blips.  
    
    过于积极和乐观：人工智能倾向于产生过于积极和乐观的内容，这在需要批判性眼光的时候可能不合适，比如技术雷达的突发事件。
-   **Context limitations:** Both GPT-3.5 and GPT-4 have context limits, with GPT-4 having significantly larger limits. This constraint can lead to issues where ChatGPT only considers its most recent output or forgets context from earlier in the process.  
    
    语境限制：GPT-3.5和GPT-4都有上下文限制，其中GPT-4的限制明显更大。这种限制可能会导致ChatGPT只考虑其最近的输出，或忘记流程中早期的上下文。
-   **Anchoring:** ChatGPT can sometimes get ‘stuck’ or ‘anchored’ at a local maximum. For example, I once asked it to expand some bullet point notes into a multi-paragraph article, which worked fine.  
    
    锚定：ChatGPT有时会被 "卡住 "或 "锚定 "在一个局部的最大值。例如，我曾经要求它把一些要点说明扩展成一篇多段的文章，这很正常。  
    
    I thought the output could use more detail and asked it to expand on what it had written, but it produced essentially the same content again without actually adding detail as I had asked. In such cases, it might be necessary to start a new chat using the best output so far to overcome this issue.  
    
    我认为输出可以使用更多的细节，并要求它扩展它所写的内容，但它又产生了基本相同的内容，实际上没有按照我的要求增加细节。在这种情况下，可能有必要使用到目前为止最好的输出开始一个新的聊天，以克服这个问题。

## Strategies for improving ChatGPT’s output  

提高ChatGPT产出的策略

ChatGPT can be a useful technical writing assistant, but the quality of the output depends heavily on how you use it. Here are some tips for refining ChatGPT’s responses:  

ChatGPT可以是一个有用的技术写作助手，但输出的质量很大程度上取决于你如何使用它。这里有一些完善ChatGPT答复的提示：

-   **Use a context-setting prompt:** Create, tweak, and reuse a context-setting prompt that outlines the style of writing, context, and target audience.  
    
    使用情境设置提示：创建、调整并重复使用设定情境的提示，概述写作风格、背景和目标受众。  
    
    This helps ensure that subsequent content has a consistent tone and is tailored to your requirements, even if you need to break up your work across multiple chat sessions.  
    
    这有助于确保后续内容具有一致的语气，并根据您的要求进行定制，即使您需要在多个聊天会话中分割工作。
-   **Work iteratively:** Just like working with a human writer, it’s important to remember that ChatGPT might not get everything right on the first try. Be patient and take the time to steer the AI in the right direction, refining its output through iteration.  
    
    迭代工作：就像与人类作家合作一样，重要的是要记住，ChatGPT可能不会在第一次尝试时就得到所有的东西。要有耐心，花时间引导人工智能向正确的方向发展，通过迭代完善其输出。  
    
    If you find a particular instruction useful, incorporate it into your context-setting prompt.  
    
    如果你发现某条指令很有用，就把它纳入你的情境设置提示中。
-   **Focus on smaller content:** GPT-3.5 works better with smaller content, such as individual sections of an article.  
    
    专注于较小的内容：GPT-3.5对较小的内容效果更好，如文章的个别章节。  
    
    GPT-4 is more adept at handling longer pieces, but it’s generally better to use separate conversations with the AI to create an outline and then tackle each major section individually.  
    
    GPT-4更善于处理较长的作品，但一般来说，使用与人工智能的单独对话来创建一个大纲，然后单独处理每个主要部分会更好。
-   **Use a collaborative approach:** Treat ChatGPT as a valuable peer rather than a subordinate. Large language models tend to respond to users at their apparent level, so providing professional-looking prompts will increase your chances of receiving professional-looking output.  
    
    使用合作的方法：把ChatGPT当作一个有价值的同行而不是下属。大型语言模型倾向于在用户的明显水平上做出反应，所以提供专业的提示会增加你收到专业的输出的机会。

## Avoiding over-reliance on AI-generated content  

避免过度依赖AI生成的内容

I’ve also been experimenting with ChatGPT for coding purposes, specifically to assist me in learning new technology stacks (a subject I plan to explore in a future article).  

我也一直在尝试使用ChatGPT进行编码，特别是协助我学习新的技术栈（我计划在未来的文章中探讨这一主题）。  

On a few occasions, GPT-4 had downtime during a session, which left me feeling somewhat at a loss—my AI “companion” had suddenly vanished! GPT-3.5 was still online but it isn’t quite as good; I much preferred to use GPT-4. This highlights the fact that it’s surprisingly easy to become dependent on these AI tools.  

有几次，GPT-4在会议期间出现了停机，这让我感到有些不知所措--我的人工智能 "伙伴 "突然消失了!GPT-3.5仍然在线，但它并不那么好；我更喜欢使用GPT-4。这凸显了一个事实，那就是对这些人工智能工具的依赖程度之高令人惊讶。  

Here are some tips to maintain a critical perspective and ensure high-quality output:  

这里有一些保持批判性视角和确保高质量产出的提示：

-   **Evaluate AI-generated content:** Always scrutinize the AI’s output for accuracy and relevance. Consider whether you agree with the content, if there are any factual errors, or if there are implications you might not endorse.  
    
    评估人工智能生成的内容：始终仔细检查人工智能的输出是否准确和相关。考虑你是否同意这些内容，是否有任何事实错误，或者是否有你可能不赞同的影响。
-   **Identify what’s missing:** Analyze the output for any missing nuances or specific points you would have made if you were writing the piece yourself.  
    
    找出缺少的东西：分析产出，找出任何遗漏的细微差别，或如果你自己写这篇文章，你会提出的具体观点。  
    
    It can be challenging to spot these gaps once you have a seemingly complete piece of writing, but it’s an essential step in maintaining the quality of your work.  
    
    一旦你有了一篇看似完整的文章，发现这些差距可能很有挑战性，但这是保持你工作质量的一个重要步骤。
-   **Invest enough time:** Keep in mind that critically editing ChatGPT’s output will take time. The “AI productivity boost” might not be as substantial as one might initially think. If you’re unable to invest the necessary effort, the content might not meet your standards.  
    
    投入足够的时间：请记住，批判性地编辑ChatGPT的输出将需要时间。AI生产力的提升 "可能并不像人们最初想象的那样可观。如果你无法投入必要的精力，内容可能不符合你的标准。
-   **Take ownership:** Remember that, ultimately, it’s your content and your name on the article. Treat ChatGPT as a helpful tool, but don’t forget your responsibility for the final output.  
    
    掌握所有权：记住，最终是你的内容和你的名字出现在文章中。把ChatGPT当作一个有用的工具，但不要忘记你对最终产出的责任。

I would say my experiments with ChatGPT as a writing assistant were a success.  

我想说我用ChatGPT作为写作助手的实验是成功的。  

I don’t think I saved time, overall, more that I was able to make steady progress by using the AI’s output as a starting point. I think this style of using LLMs—to create first drafts and to suggest additions—will work for a variety of tasks in the software world, from story writing, to acceptance testing, to documentation. I don’t think the AIs are here to take our jobs—you still need a human expert working with the output—but I do expect these kinds of tools will help humans produce higher quality results.  

我不认为我总体上节省了时间，更多的是我能够通过使用人工智能的输出作为一个起点来取得稳定的进展。我认为这种使用LLMs的方式--创建初稿并提出补充建议--将适用于软件世界中的各种任务，从故事写作到验收测试，再到文档。我不认为人工智能是来取代我们的工作的--你仍然需要一个人类专家来处理输出，但我确实期望这些类型的工具将帮助人类产生更高质量的结果。  

Working effectively with AI tools has become a key skill for knowledge workers, starting right now.  

从现在开始，有效利用人工智能工具工作已经成为知识工作者的一项关键技能。

___
