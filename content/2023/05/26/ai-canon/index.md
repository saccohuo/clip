---
title: "AI Canon"
date: 2023-05-26T15:14:11+08:00
updated: 2023-05-26T15:14:11+08:00
taxonomies:
  tags: []
extra:
  source: https://a16z.com/2023/05/25/ai-canon/
  hostname: a16z.com
  author: Derrick Harris, Matt Bornstein, Guido Appenzeller
  original_title: "AI Canon"
  original_lang: zh
---

[![](stacks_of_books_and_GPU.png)](https://i1.wp.com/a16z.com/wp-content/uploads/2023/05/stacks_of_books_and_GPU.png?ssl=1)

Source: Midjourney 资料来源：中途

Research in artificial intelligence is increasing at an exponential rate.  

人工智能的研究正在以指数级的速度增长。  

It’s difficult for AI experts to keep up with everything new being published, and even harder for beginners to know where to start.  

人工智能专家很难跟上所有新发布的内容，初学者更难知道从哪里开始。

So, in this post, we’re sharing a curated list of resources we’ve relied on to get smarter about modern AI.  

因此，在这篇文章中，我们将分享一份精选的资源清单，这些资源是我们赖以提高现代 AI 智能水平所依赖的资源。  

We call it the “AI Canon” because these papers, blog posts, courses, and guides have had an outsized impact on the field over the past several years.  

我们将其称为“AI 经典”，因为这些论文、博客文章、课程和指南在过去几年中对该领域产生了巨大影响。

We start with a gentle introduction to _transformer_ and _latent diffusion_ models, which are fueling the current AI wave.  

Next, we go deep on technical learning resources; practical guides to building with large language models (LLMs); and analysis of the AI market.  

接下来，我们深入技术学习资源；使用大型语言模型 (LLM) 进行构建的实用指南；人工智能市场分析。  

Finally, we include a reference list of landmark research results, starting with “Attention is All You Need” — the 2017 paper by Google that introduced the world to transformer models and ushered in the age of generative AI.  

最后，我们提供了一份具有里程碑意义的研究成果的参考列表，首先是“Attention is All You Need”——谷歌 2017 年的论文，向世界介绍了 transformer 模型并开创了生成式 AI 的时代。  

我们首先简要介绍了正在推动当前 AI 浪潮的 Transformer 和潜在扩散模型。

## A gentle introduction… 温柔的介绍……

These articles require no specialized background and can help you get up to speed quickly on the most important parts of the modern AI wave.  

这些文章不需要专业背景，可以帮助您快速了解现代 AI 浪潮中最重要的部分。

-   **[Software 2.0](https://karpathy.medium.com/software-2-0-a64152b37c35)**: Andrej Karpathy was one of the first to clearly explain (in 2017!) why the new AI wave really matters. His argument is that AI is a new and powerful way to program computers.  
    
    As LLMs have improved rapidly, this thesis has proven prescient, and it gives a good mental model for how the AI market may progress.  
    
    随着 LLM 的快速发展，这篇论文被证明是有先见之明的，它为 AI 市场如何发展提供了一个很好的思维模型。  
    
    软件 2.0：Andrej Karpathy 是第一个清楚地解释（在 2017 年！）为什么新的 AI 浪潮真正重要的人之一。他的论点是，人工智能是一种新的、强大的计算机编程方式。
-   **[State of GPT](https://build.microsoft.com/en-US/sessions/db3f4859-cd30-4445-a0cd-553c3304f8e2)**: Also from Karpathy, this is a very approachable explanation of how ChatGPT / GPT models in general work, how to use them, and what directions R&D may take.  
    
    GPT 的状态：同样来自 Karpathy，这是一个非常平易近人的解释，解释了 ChatGPT/GPT 模型的一般工作原理、如何使用它们以及研发可能采取的方向。
-   [**What is ChatGPT doing … and why does it work?**](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/): Computer scientist and entrepreneur Stephen Wolfram gives a long but highly readable explanation, from first principles, of how modern AI models work.  
    
    He follows the timeline from early neural nets to today’s LLMs and ChatGPT.  
    
    他遵循从早期神经网络到今天的 LLM 和 ChatGPT 的时间表。  
    
    ChatGPT 在做什么……它为什么起作用？：计算机科学家兼企业家 Stephen Wolfram 从基本原理出发，对现代 AI 模型的工作原理进行了长篇但可读性很强的解释。
-   **[Transformers, explained](https://daleonai.com/transformers-explained)**: This post by Dale Markowitz is a shorter, more direct answer to the question “what is an LLM, and how does it work?” This is a great way to ease into the topic and develop intuition for the technology.  
    
    It was written about GPT-3 but still applies to newer models.  
    
    它是关于 GPT-3 的，但仍然适用于较新的模型。  
    
    变形金刚，解释说：Dale Markowitz 的这篇文章是对“什么是 LLM，它是如何工作的？”这个问题的更简短、更直接的回答。这是轻松进入主题并培养技术直觉的好方法。
-   **[How Stable Diffusion works](https://mccormickml.com/2022/12/21/how-stable-diffusion-works/)**: This is the computer vision analogue to the last post.  
    
    Chris McCormick gives a layperson’s explanation of how Stable Diffusion works and develops intuition around text-to-image models generally. For an even  
    
    稳定扩散的工作原理：这是与上一篇文章类似的计算机视觉。_gentler_ introduction, check out this [comic](https://www.reddit.com/r/StableDiffusion/comments/zs5dk5/i_made_an_infographic_to_explain_how_stable/) from r/StableDiffusion.  
    
    Chris McCormick 给出了外行人对 Stable Diffusion 如何工作的解释，并培养了对文本到图像模型的一般直觉。如需更温和的介绍，请查看 r/StableDiffusion 中的这部漫画。

___

## Foundational learning: neural networks, backpropagation, and embeddings  

基础学习：神经网络、反向传播和嵌入

These resources provide a base understanding of fundamental ideas in machine learning and AI, from the basics of deep learning to university-level courses from AI experts.  

这些资源提供了对机器学习和 AI 基本思想的基本理解，从深度学习的基础知识到 AI 专家的大学水平课程。

### Explainers

-   [**Deep learning in a nutshell: core concepts**](https://developer.nvidia.com/blog/deep-learning-nutshell-core-concepts/): This four-part series from Nvidia walks through the basics of deep learning as practiced in 2015, and is a good resource for anyone just learning about AI.  
    
    深度学习简述：核心概念：Nvidia 的这个由四部分组成的系列介绍了 2015 年实践的深度学习基础知识，对于任何刚刚了解 AI 的人来说都是一个很好的资源。
-   **[Practical deep learning for coders](https://course.fast.ai/)**: Comprehensive, free course on the fundamentals of AI, explained through practical examples and code.  
    
    面向程序员的实用深度学习：关于 AI 基础知识的综合免费课程，通过实际示例和代码进行解释。
-   **[Word2vec explained](https://towardsdatascience.com/word2vec-explained-49c52b4ccb71)**: Easy introduction to embeddings and tokens, which are building blocks of LLMs (and all language models).  
    
    Word2vec 解释：嵌入和标记的简单介绍，它们是 LLM（和所有语言模型）的构建块。
-   **[Yes you should understand backprop](https://karpathy.medium.com/yes-you-should-understand-backprop-e2f06eab496b)**: More in-depth post on back-propagation if you want to understand the details. If you want even more, try the [Stanford CS231n lecture](https://www.youtube.com/watch?v=i94OvYb6noo) on Youtube.  
    
    是的，您应该了解反向传播：如果您想了解详细信息，请阅读有关反向传播的更深入的文章。如果您想要更多，请尝试 Youtube 上的 Stanford CS231n 讲座。

### Courses

-   **[Stanford CS229](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU)**: Introduction to Machine Learning with Andrew Ng, covering the fundamentals of machine learning.  
    
    Stanford CS229：与 Andrew Ng 一起介绍机器学习，涵盖机器学习的基础知识。
-   **[Stanford CS224N](https://www.youtube.com/playlist?list=PLoROMvodv4rOSH4v6133s9LFPRHjEmbmJ)**: NLP with Deep Learning with Chris Manning, covering NLP basics through the first generation of LLMs.  
    
    Stanford CS224N：NLP with Deep Learning with Chris Manning，通过第一代 LLM 涵盖了 NLP 基础知识。

___

## Tech deep dive: understanding transformers and large models  

技术深入研究：了解变压器和大型模型

There are countless resources — some better than others — attempting to explain how LLMs work. Here are some of our favorites, targeting a wide range of readers/viewers.  

有无数的资源——有些比其他的更好——试图解释法学硕士是如何工作的。以下是我们的一些最爱，面向广泛的读者/观众。

### Explainers

-   [**The illustrated transformer**](https://jalammar.github.io/illustrated-transformer/): A more technical overview of the transformer architecture by Jay Alammar.  
    
    图示的变压器：Jay Alammar 对变压器架构的更多技术概述。
-   **[The annotated transformer](http://nlp.seas.harvard.edu/annotated-transformer/)**: In-depth post if you want to understand transformers at a source code level. Requires some knowledge of PyTorch.  
    
    The annotated transformer：如果您想在源代码级别了解转换器，请阅读这篇深度文章。需要 PyTorch 的一些知识。
-   [**Let’s build GPT: from scratch, in code, spelled out**](https://www.youtube.com/watch?v=kCc8FmEb1nY): For the engineers out there, Karpathy does a video walkthrough of how to build a GPT model.  
    
    让我们构建 GPT：从头开始，使用代码，详细说明：对于那里的工程师，Karpathy 制作了一个视频演练，介绍如何构建 GPT 模型。
-   **[The illustrated Stable Diffusion](https://jalammar.github.io/illustrated-stable-diffusion/)****:** Introduction to latent diffusion models, the most common type of generative AI model for images.  
    
    图示的稳定扩散：潜在扩散模型简介，最常见的图像生成 AI 模型类型。
-   **[RLHF: Reinforcement Learning from Human Feedback](https://huyenchip.com/2023/05/02/rlhf.html)**: Chip Huyen explains RLHF, which can make LLMs behave in more predictable and human-friendly ways.  
    
    RLHF：从人类反馈中强化学习：Chip Huyen 解释了 RLHF，它可以使 LLM 以更可预测和更人性化的方式行事。  
    
    This is one of the most important but least well-understood aspects of systems like ChatGPT.  
    
    这是 ChatGPT 等系统最重要但最不为人所知的方面之一。
-   [**Reinforcement learning from human feedback**](https://www.youtube.com/watch?v=hhiLw5Q_UFg): Computer scientist and OpenAI cofounder John Shulman goes deeper in this great talk on the current state, progress and limitations of LLMs with RLHF.  
    
    从人类反馈中强化学习：计算机科学家和 OpenAI 联合创始人 John Shulman 深入探讨了 RLHF 法学硕士的现状、进展和局限性。

### Courses

-   [**Stanford CS25**](https://www.youtube.com/watch?v=P127jhj-8-Y): Transformers United, an online seminar on Transformers.  
    
    Stanford CS25：Transformers United，关于变形金刚的在线研讨会。
-   **[Stanford CS324](https://stanford-cs324.github.io/winter2022/)**: Large Language Models with Percy Liang, Tatsu Hashimoto, and Chris Re, covering a wide range of technical and non-technical aspects of LLMs.  
    
    Stanford CS324：Percy Liang、Tatsu Hashimoto 和 Chris Re 的大型语言模型，涵盖 LLM 的广泛技术和非技术方面。

### Reference and commentary 参考和评论

-   **[Predictive learning, NIPS 2016](https://www.youtube.com/watch?v=Ount2Y4qxQo&t=1072s)**: In this early talk, Yann LeCun makes a strong case for unsupervised learning as a critical element of AI model architectures at scale. Skip to [19:20](https://youtu.be/Ount2Y4qxQo?t=1160) for the famous cake analogy, which is still one of the best mental models for modern AI.  
    
    预测学习，NIPS 2016：在这个早期的演讲中，Yann LeCun 有力地证明了无监督学习是大规模 AI 模型架构的关键要素。跳到 19:20 查看著名的蛋糕类比，它仍然是现代 AI 最好的心智模型之一。
-   [**AI for full-self driving at Tesla**](https://www.youtube.com/watch?v=hx7BXih7zx8): Another classic Karpathy talk, this time covering the Tesla data collection engine. Starting at [8:35](https://youtu.be/hx7BXih7zx8?t=515) is one of the great all-time AI rants, explaining why long-tailed problems (in this case stop sign detection) are so hard.  
    
    特斯拉全自动驾驶人工智能：另一个经典的 Karpathy 演讲，这次涉及特斯拉数据收集引擎。从 8:35 开始是有史以来最伟大的 AI 咆哮之一，解释了为什么长尾问题（在本例中为停车标志检测）如此困难。
-   **[The scaling hypothesis](https://gwern.net/scaling-hypothesis)**: One of the most surprising aspects of LLMs is that scaling — adding more data and compute — just keeps increasing accuracy.  
    
    GPT-3 was the first model to demonstrate this clearly, and Gwern’s post does a great job explaining the intuition behind it.  
    
    GPT-3 是第一个清楚地展示这一点的模型，Gwern 的帖子很好地解释了它背后的直觉。  
    
    扩展假设：LLM 最令人惊讶的方面之一是扩展——添加更多数据和计算——只会不断提高准确性。
-   [**Chinchilla’s wild implications**](https://www.lesswrong.com/posts/6Fpvch8RR29qLEWNH/chinchilla-s-wild-implications): Nominally an explainer of the important Chinchilla paper (see below), this post gets to the heart of the big question in LLM scaling: are we running out of data?  
    
    This builds on the post above and gives a refreshed view on scaling laws.  
    
    这建立在上面的帖子之上，并提供了关于缩放法则的更新视图。  
    
    Chinchilla 的广泛含义：名义上是重要的 Chinchilla 论文的解释者（见下文），这篇文章触及了 LLM 扩展中的大问题的核心：我们的数据用完了吗？
-   **[A survey of large language models](https://arxiv.org/pdf/2303.18223v4.pdf)**: Comprehensive breakdown of current LLMs, including development timeline, size, training strategies, training data, hardware, and more.  
    
    大型语言模型调查：当前 LLM 的全面细分，包括开发时间表、规模、训练策略、训练数据、硬件等。
-   [**Sparks of artificial general intelligence: Early experiments with GPT-4**](https://arxiv.org/abs/2303.12712): Early analysis from Microsoft Research on the capabilities of GPT-4, the current most advanced LLM, relative to human intelligence.  
    
    Sparks of artificial general intelligence: Early experiments with GPT-4：微软研究院对 GPT-4 能力的早期分析，GPT-4 是目前最先进的 LLM，与人类智能相关。
-   [**The AI revolution: How Auto-GPT unleashes a new era of automation and creativity**](https://pub.towardsai.net/the-ai-revolution-how-auto-gpt-unleashes-a-new-era-of-automation-and-creativity-2008aa2ca6ae): An introduction to Auto-GPT and AI agents in general.  
    
    This technology is very early but important to understand — it uses internet access and self-generated sub-tasks in order to solve specific, complex problems or goals.  
    
    这项技术很早，但理解起来很重要——它使用互联网访问和自我生成的子任务来解决特定的、复杂的问题或目标。  
    
    AI 革命：Auto-GPT 如何开启自动化和创造力的新时代：Auto-GPT 和 AI 代理的总体介绍。
-   **[The Waluigi Effect](https://www.lesswrong.com/posts/D7PumeYTDPfBTp3i7/the-waluigi-effect-mega-post)**: Nominally an explanation of the “Waluigi effect” (i.e., why “alter egos” emerge in LLM behavior), but interesting mostly for its deep dive on the theory of LLM prompting.  
    
    The Waluigi Effect：名义上是对“Waluigi 效应”的解释（即，为什么 LLM 行为中会出现“改变自我”），但有趣的主要是它对 LLM 提示理论的深入探讨。

___

## Practical guides to building with LLMs  

使用 LLM 进行构建的实用指南

A new application stack is emerging with LLMs at the core.  

以 LLM 为核心的新应用程序堆栈正在出现。  

While there isn’t a lot of formal education available on this topic yet, we pulled out some of the most useful resources we’ve found.  

虽然目前还没有很多关于这个主题的正规教育，但我们提取了一些我们发现的最有用的资源。

### Reference

-   [**Build a GitHub support bot with GPT3, LangChain, and Python**](https://dagster.io/blog/chatgpt-langchain): One of the earliest public explanations of the modern LLM app stack.  
    
    Some of the advice in here is dated, but in many ways it kicked off widespread adoption and experimentation of new AI apps.  
    
    这里的一些建议已经过时，但在许多方面它开启了新 AI 应用程序的广泛采用和试验。  
    
    使用 GPT3、LangChain 和 Python 构建 GitHub 支持机器人：现代 LLM 应用程序堆栈的最早公开解释之一。
-   **[Building LLM applications for production](https://huyenchip.com/2023/04/11/llm-engineering.html)**: Chip Huyen discusses many of the key challenges in building LLM apps, how to address them, and what types of use cases make the most sense.  
    
    为生产构建 LLM 应用程序：Chip Huyen 讨论了构建 LLM 应用程序的许多关键挑战、如何解决这些挑战以及哪些类型的用例最有意义。
-   **[Prompt Engineering Guide](https://www.promptingguide.ai/)**: For anyone writing LLM prompts — including app devs — this is the most comprehensive guide, with specific examples for a handful of popular models.  
    
    For a lighter, more conversational treatment, try  
    
    Prompt Engineering Guide：对于任何编写 LLM prompt 的人——包括应用程序开发者——这是最全面的指南，其中包含一些流行模型的具体示例。[Brex’s prompt engineering guide](https://github.com/brexhq/prompt-engineering).  
    
    如需更轻松、更对话的治疗，请尝试 Brex 的提示工程指南。
-   [**Prompt injection: What’s the worst that can happen?**](https://simonwillison.net/2023/Apr/14/worst-that-can-happen/) Prompt injection is a potentially serious security vulnerability lurking for LLM apps, with no perfect solution yet.  
    
    Simon Willison gives the definitive description of the problem in this post. Nearly everything Simon writes on AI is outstanding.  
    
    Simon Willison 在这篇文章中给出了问题的明确描述。 Simon 几乎所有关于 AI 的文章都非常出色。  
    
    及时注射：可能发生的最坏情况是什么？ Prompt injection 是 LLM 应用中潜在的严重安全漏洞，目前还没有完美的解决方案。
-   [**OpenAI cookbook**](https://github.com/openai/openai-cookbook/tree/main): For developers, this is the definitive collection of guides and code examples for working with the OpenAI API. It’s updated continually with new code examples.  
    
    OpenAI cookbook：对于开发人员来说，这是使用 OpenAI API 的指南和代码示例的权威集合。它会不断更新新的代码示例。
-   [**Pinecone learning center**](https://www.pinecone.io/learn/): Many LLM apps are based around a vector search paradigm.  
    
    Pinecone’s learning center — despite being branded vendor content — offers some of the most useful instruction on how to build in this pattern.  
    
    Pinecone 的学习中心——尽管是品牌供应商内容——提供了一些关于如何构建这种模式的最有用的指导。  
    
    Pinecone 学习中心：许多 LLM 应用程序都基于矢量搜索范式。
-   [**LangChain docs**](https://python.langchain.com/en/latest/index.html): As the default orchestration layer for LLM apps, LangChain connects to just about all other pieces of the stack.  
    
    So their docs are a real reference for the full stack and how the pieces fit together.  
    
    因此，他们的文档是完整堆栈以及各个部分如何组合在一起的真正参考。  
    
    LangChain 文档：作为 LLM 应用程序的默认编排层，LangChain 连接到堆栈的几乎所有其他部分。

### Courses

-   **[LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/)**: A practical course for building LLM-based applications with Charles Frye, Sergey Karayev, and Josh Tobin.  
    
    LLM 训练营：与 Charles Frye、Sergey Karayev 和 Josh Tobin 一起构建基于 LLM 的应用程序的实用课程。
-   **[Hugging Face Transformers](https://huggingface.co/learn/nlp-course/chapter1/1)**: Guide to using open-source LLMs in the Hugging Face transformers library.  
    
    Hugging Face Transformers：在 Hugging Face 转换器库中使用开源 LLM 的指南。

### LLM benchmarks

-   **[Chatbot Arena](https://lmsys.org/blog/2023-05-03-arena/)**: An Elo-style ranking system of popular LLMs, led by a team at UC Berkeley. Users can also participate by comparing models head to head.  
    
    Chatbot Arena：流行 LLM 的 Elo 风格排名系统，由加州大学伯克利分校的一个团队领导。用户还可以通过正面比较模型来参与。
-   **[Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard)**: A ranking by Hugging Face, comparing open source LLMs across a collection of standard benchmarks and tasks.  
    
    Open LLM Leaderboard：Hugging Face 的排名，在一系列标准基准和任务中比较开源 LLM。

___

## Market analysis

We’ve all marveled at what generative AI can produce, but there are still a lot of questions about _what it all means_. Which products and companies will survive and thrive? What happens to artists? How should companies use it? How will it affect literally jobs and society at large?  

Here are some attempts at answering these questions.  

以下是回答这些问题的一些尝试。  

我们都惊叹于生成式 AI 可以产生什么，但对于这一切意味着什么仍有很多疑问。哪些产品和公司将生存和发展？艺术家会怎样？企业应该如何使用它？它将如何影响就业和整个社会？

### a16z thinking

-   [**Who owns the generative AI platform?**](https://a16z.com/2023/01/19/who-owns-the-generative-ai-platform/): Our flagship assessment of where value is accruing, and might accrue, at the infrastructure, model, and application layers of generative AI.  
    
    谁拥有生成式 AI 平台？：我们对生成式 AI 的基础设施、模型和应用层的价值在哪里积累和可能积累的旗舰评估。
-   [**Navigating the high cost of AI compute**](https://a16z.com/2023/04/27/navigating-the-high-cost-of-ai-compute/): A detailed breakdown of why generative AI models require so many computing resources, and how to think about acquiring those resources (i.e., the right GPUs in the right quantity, at the right cost) in a high-demand market.  
    
    应对 AI 计算的高成本：详细分析生成 AI 模型为何需要如此多的计算资源，以及如何考虑以高成本获取这些资源（即以合适的数量、合适的成本获得合适的 GPU）需求市场。
-   **[Art isn’t dead, it’s just machine-generated](https://a16z.com/2022/11/16/creativity-as-an-app/)**: A look at how AI models were able to reshape creative fields — often assumed to be the last holdout against automation — much faster than fields such as software development.  
    
    艺术并没有死，它只是机器生成的：看看 AI 模型如何重塑创意领域——通常被认为是反对自动化的最后一道屏障——比软件开发等领域快得多。
-   **[The generative AI revolution in games](https://a16z.com/2022/11/17/the-generative-ai-revolution-in-games/)**: An in-depth analysis from our Games team at how the ability to easily create highly detailed graphics will change how game designers, studios, and the entire market function. [This follow-up piece](https://a16z.com/2023/03/17/the-generative-ai-revolution/) from our Games team looks specifically at the advent of AI-generated content vis à vis user-generated content.  
    
    游戏中的生成式 AI 革命：我们的游戏团队深入分析了轻松创建高度详细图形的能力将如何改变游戏设计师、工作室和整个市场运作的方式。我们游戏团队的这篇后续文章特别关注了人工智能生成内容与用户生成内容的对比。
-   [**For B2B generative AI apps, is less more?**](https://a16z.com/2023/03/30/b2b-generative-ai-synthai/): A prediction for how LLMs will evolve in the world of B2B enterprise applications, centered around the idea that summarizing information will ultimately be more valuable than producing text.  
    
    对于 B2B 生成式 AI 应用程序，少即是多？：预测 LLM 将如何在 B2B 企业应用程序的世界中发展，其中心思想是总结信息最终将比生成文本更有价值。
-   **[Financial services will embrace generative AI faster than you think](https://a16z.com/2023/04/19/financial-services-will-embrace-generative-ai-faster-than-you-think/)**: An argument that the financial services industry is poised to use generative AI for personalized consumer experiences, cost-efficient operations, better compliance, improved risk management, and dynamic forecasting and reporting.   
    
    金融服务将比您想象的更快地采用生成式人工智能：一种观点认为，金融服务业准备使用生成式人工智能来实现个性化的消费者体验、具有成本效益的运营、更好的合规性、改进的风险管理以及动态预测和报告。
-   [**Generative AI: The next consumer platform**](https://a16z.com/2023/02/07/everyday-ai-consumer/): A look at opportunities for generative AI to impact the consumer market across a range of sectors from therapy to ecommerce.  
    
    生成式 AI：下一个消费者平台：审视生成式 AI 影响从治疗到电子商务等一系列领域的消费市场的机会。
-   [**To make a real difference in health care, AI will need to learn like we do**](https://time.com/6274752/ai-health-care/): AI is poised to irrevocably change how we look to prevent and treat illness.  
    
    However, to truly transform drug discovery to care delivery, we should invest in creating an ecosystem of “specialist” AIs — that learn like our best physicians and drug developers do today.  
    
    然而，要真正将药物发现转化为医疗服务，我们应该投资创建一个“专业”人工智能生态系统——它们像当今最好的医生和药物开发人员一样学习。  
    
    为了真正改变医疗保健，人工智能需要像我们一样学习：人工智能有望不可逆转地改变我们预防和治疗疾病的方式。
-   [**The new industrial revolution: Bio x AI**](https://a16z.com/2023/05/17/the-new-industrial-revolution-bio-x-ai/): The next industrial revolution in human history will be biology powered by artificial intelligence.  
    
    新工业革命：Bio x AI：人类历史上的下一次工业革命将是人工智能驱动的生物学。

### Other perspectives 其他观点

-   **[On the opportunities and risks of foundation models](https://arxiv.org/abs/2108.07258)**: Stanford overview paper on Foundation Models. Long and opinionated, but this shaped the term.  
    
    On the opportunities and risks of foundation models：关于基础模型的斯坦福概述论文。冗长且自以为是，但这塑造了这个词。
-   [**State of AI Report**](https://www.stateof.ai/): An annual roundup of everything going on in AI, including technology breakthroughs, industry development, politics/regulation, economic implications, safety, and predictions for the future.  
    
    AI 现状报告：对 AI 中发生的一切的年度总结，包括技术突破、行业发展、政治/监管、经济影响、安全和对未来的预测。
-   [**GPTs are GPTs: An early look at the labor market impact potential of large language models**](https://arxiv.org/abs/2303.10130): This paper from researchers at OpenAI, OpenResearch, and the University of of Pennsylvania predicts that “around 80% of the U.S. workforce could have at least 10% of their work tasks affected by the introduction of LLMs, while approximately 19% of workers may see at least 50% of their tasks impacted.”  
    
    GPT 是 GPT：早期观察大型语言模型对劳动力市场的影响潜力：这篇来自 OpenAI、OpenResearch 和宾夕法尼亚大学的研究人员的论文预测，“大约 80% 的美国劳动力可能拥有至少 10% 的他们的工作任务受到 LLM 的引入的影响，而大约 19% 的工人可能会看到至少 50% 的任务受到影响。”
-   [**Deep medicine: How artificial intelligence can make healthcare human again**](https://www.amazon.com/Deep-Medicine-Eric-Topol-audiobook/dp/B07PJ21V5N/ref=sr_1_1?hvadid=580688888836&hvdev=c&hvlocphy=9031955&hvnetw=g&hvqmt=e&hvrand=13698160037271563598&hvtargid=kwd-646099228782&hydadcr=15524_13517408&keywords=eric+topol+deep+medicine&qid=1684965845&sr=8-1): Dr. Eric Topol reveals how artificial intelligence has the potential to free physicians from the time-consuming tasks that interfere with human connection.  
    
    The doctor-patient relationship is restored. (  
    
    深度医学：人工智能如何让医疗保健再次成为人类：Eric Topol 博士揭示了人工智能如何有可能将医生从干扰人际关系的耗时任务中解放出来。[a16z podcast](https://a16z.com/2019/06/13/ai-doctor-deep-medicine-topol/))  
    
    医患关系恢复。 （a16z 播客）

___

## Landmark research results 里程碑式的研究成果

Most of the amazing AI products we see today are the result of no-less-amazing research, carried out by experts inside large companies and leading universities.  

我们今天看到的大多数令人惊叹的 AI 产品都是同样令人惊叹的研究的结果，这些研究是由大公司和一流大学的专家进行的。  

Lately, we’ve also seen impressive work from individuals and the open source community taking popular projects into new directions, for example by creating automated agents or porting models onto smaller hardware footprints.   

最近，我们还看到个人和开源社区将热门项目带向新方向的令人印象深刻的工作，例如通过创建自动化代理或将模型移植到更小的硬件占用空间上。

Here’s a collection of many of these papers and projects, for folks who really want to dive deep into generative AI.  

这是许多此类论文和项目的集合，适合真正想深入研究生成式 AI 的人们。  

(For research papers and projects, we’ve also included links to the accompanying blog posts or websites, where available, which tend to explain things at a higher level.  

（对于研究论文和项目，我们还提供了指向随附博客文章或网站的链接，如果可用，它们往往会在更高层次上解释事物。  

And we’ve included original publication years so you can track foundational research over time.)  

我们还包括原始出版年份，因此您可以随着时间的推移跟踪基础研究。）

### **Large language models 大型语言模型**

**New models**

-   **[Attention is all you need](https://arxiv.org/abs/1706.03762)** (2017): The original transformer work and research paper from Google Brain that started it all. ([blog post](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html))  
    
    Attention is all you need (2017)：Google Brain 的原始 transformer 工作和研究论文开启了这一切。 （博客文章）
-   **[BERT: pre-training of deep bidirectional transformers for language understanding](https://arxiv.org/abs/1810.04805)** (2018): One of the first publicly available LLMs, with many variants still in use today. ([blog post](https://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html))  
    
    BERT：用于语言理解的深度双向转换器的预训练（2018 年）：首批公开可用的 LLM 之一，许多变体至今仍在使用。 （博客文章）
-   **[Improving language understanding by generative pre-training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf)** (2018): The first paper from OpenAI covering the GPT architecture, which has become the dominant development path in LLMs. ([blog post](https://openai.com/research/language-unsupervised))  
    
    Improving language understanding by generative pre-training (2018)：OpenAI 的第一篇论文，涵盖了 GPT 架构，该架构已成为 LLM 的主要发展路径。 （博客文章）
-   [**Language models are few-shot learners**](https://arxiv.org/abs/2005.14165) (2020): The OpenAI paper that describes GPT-3 and the decoder-only architecture of modern LLMs.  
    
    Language models are few-shot learners (2020)：描述 GPT-3 和现代 LLM 的仅解码器架构的 OpenAI 论文。
-   **[Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155)** (2022): OpenAI’s paper explaining InstructGPT, which utilizes humans in the loop to train models and, thus, better follow the instructions in prompts.  
    
    This was one of the key unlocks that made LLMs accessible to consumers (e.g., via ChatGPT). (  
    
    Training language models to follow instructions with human feedback (2022)：OpenAI 的论文解释了 InstructGPT，它利用循环中的人类来训练模型，从而更好地遵循提示中的说明。[blog post](https://openai.com/research/instruction-following))  
    
    这是使消费者可以访问 LLM 的关键解锁之一（例如，通过 ChatGPT）。 （博客文章）
-   [**LaMDA: language models for dialog applications**](https://arxiv.org/abs/2201.08239) (2022): A model form Google specifically designed for free-flowing dialog between a human and chatbot across a wide variety of topics. ([blog post](https://blog.google/technology/ai/lamda/))   
    
    LaMDA：对话应用程序的语言模型（2022 年）：Google 专门为人与聊天机器人之间的各种主题的自由对话而设计的模型。 （博客文章）
-   **[PaLM: Scaling language modeling with pathways](https://arxiv.org/abs/2204.02311)** (2022): PaLM, from Google, utilized a new system for training LLMs across thousands of chips and demonstrated larger-than-expected improvements for certain tasks as model size scaled up. ([blog post](https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html)). See also the [PaLM-2 technical report](https://arxiv.org/abs/2305.10403).  
    
    PaLM：使用路径扩展语言建模（2022 年）：来自 Google 的 PaLM 利用新系统在数千个芯片上训练 LLM，并证明随着模型规模的扩大，某些任务的改进超出预期。 （博客文章）。另见 PaLM-2 技术报告。
-   **[OPT: Open Pre-trained Transformer language models](https://arxiv.org/abs/2205.01068)** (2022): OPT is one of the top performing fully open source LLMs. The release for this 175-billion-parameter model comes with code and was trained on publicly available datasets. ([blog post](https://ai.facebook.com/blog/democratizing-access-to-large-scale-language-models-with-opt-175b/))  
    
    OPT：Open Pre-trained Transformer language models (2022)：OPT 是性能最好的完全开源 LLM 之一。这个 1750 亿参数模型的发布附带代码，并在公开可用的数据集上进行了训练。 （博客文章）
-   **[Training compute-optimal large language models](https://arxiv.org/abs/2203.15556)** (2022): The Chinchilla paper. It makes the case that most models are data limited, not compute limited, and changed the consensus on LLM scaling. ([blog post](https://www.deepmind.com/blog/an-empirical-analysis-of-compute-optimal-large-language-model-training))  
    
    训练计算最优的大型语言模型 (2022)：Chinchilla 论文。它证明大多数模型都是数据受限的，而不是计算受限的，并且改变了对 LLM 扩展的共识。 （博客文章）
-   [**GPT-4 technical report**](https://arxiv.org/abs/2303.08774) (2023): The latest and greatest paper from OpenAI, known mostly for how little it reveals! ([blog post](https://openai.com/research/gpt-4)). The [GPT-4 system card](https://cdn.openai.com/papers/gpt-4-system-card.pdf) sheds some light on how OpenAI treats hallucinations, privacy, security, and other issues.  
    
    GPT-4 技术报告（2023 年）：来自 OpenAI 的最新和最伟大的论文，主要以其揭示的内容少而闻名！ （博客文章）。 GPT-4 系统卡片揭示了 OpenAI 如何处理幻觉、隐私、安全和其他问题。
-   [**LLaMA: Open and efficient foundation language models**](https://arxiv.org/abs/2302.13971) (2023): The model from Meta that (almost) started an open-source LLM revolution.  
    
    Competitive with many of the best closed-source models but only opened up to researchers on a restricted license. (  
    
    LLaMA: Open and efficient foundation language models (2023)：来自 Meta 的模型（几乎）开启了开源 LLM 革命。[blog post](https://ai.facebook.com/blog/large-language-model-llama-meta-ai/))  
    
    与许多最好的封闭源代码模型竞争，但只对受限许可的研究人员开放。 （博客文章）
-   [**Alpaca: A strong, replicable instruction-following model**](https://crfm.stanford.edu/2023/03/13/alpaca.html) (2023): Out of Stanford, this model demonstrates the power of instruction tuning, especially in smaller open-source models, compared to pure scale.  
    
    Alpaca：一个强大的、可复制的指令跟随模型（2023 年）：在斯坦福大学之外，与纯规模相比，该模型展示了指令调整的力量，尤其是在较小的开源模型中。

**Model improvements (e.g. fine-tuning, retrieval, attention)  

模型改进（例如微调、检索、注意力）**

-   **[Deep reinforcement learning from human preferences](https://proceedings.neurips.cc/paper_files/paper/2017/file/d5e2c0adad503c91f91df240d0cd4e49-Paper.pdf)** (2017): Research on reinforcement learning in gaming and robotics contexts, that turned out to be a fantastic tool for LLMs.  
    
    Deep reinforcement learning from human preferences (2017)：关于游戏和机器人环境中强化学习的研究，结果证明这是 LLM 的绝佳工具。
-   **[Retrieval-augmented generation for knowledge-intensive NLP tasks](https://arxiv.org/abs/2005.11401)** (2020): Developed by Facebook, RAG is one of the two main research paths for improving LLM accuracy via information retrieval. ([blog post](https://ai.facebook.com/blog/retrieval-augmented-generation-streamlining-the-creation-of-intelligent-natural-language-processing-models/))  
    
    Retrieval-augmented generation for knowledge-intensive NLP tasks (2020)：由 Facebook 开发，RAG 是通过信息检索提高 LLM 准确性的两个主要研究路径之一。 （博客文章）
-   **[Improving language models by retrieving from trillions of tokens](https://arxiv.org/abs/2112.04426)** (2021): RETRO, for “Retrieval Enhanced TRansfOrmers,” is another approach — this one by DeepMind — to improve LLM accuracy by accessing information not included in their training data. ([blog post](https://www.deepmind.com/blog/improving-language-models-by-retrieving-from-trillions-of-tokens))  
    
    通过从数万亿个标记中检索来改进语言模型（2021 年）：RETRO，即“检索增强型 TRAnsfOrmers”，是 DeepMind 的另一种方法，通过访问未包含在其训练数据中的信息来提高 LLM 的准确性。 （博客文章）
-   [**LoRA: Low-rank adaptation of large language models**](https://arxiv.org/abs/2106.09685) (2021): This research out of Microsoft introduced a more efficient alternative to fine-tuning for training LLMs on new data.  
    
    It’s now become a standard for community fine-tuning, especially for image models.  
    
    它现在已经成为社区微调的标准，尤其是图像模型。  
    
    LoRA：Low-rank adaptation of large language models (2021)：Microsoft 的这项研究引入了一种更有效的替代方法来微调，用于在新数据上训练 LLM。
-   **[Constitutional AI (2022)](https://arxiv.org/abs/2212.08073)**: The Anthropic team introduces the concept of reinforcement learning from AI Feedback (RLAIF).  
    
    The main idea is that we can develop a harmless AI assistant with the supervision of other AIs.  
    
    主要思想是我们可以在其他 AI 的监督下开发一个无害的 AI 助手。  
    
    宪法 AI (2022)：Anthropic 团队引入了从 AI 反馈 (RLAIF) 强化学习的概念。
-   [**FlashAttention: Fast and memory-efficient exact attention with IO-awareness**](https://arxiv.org/abs/2205.14135) (2022): This research out of Stanford opened the door for state-of-the-art models to understand longer sequences of text (and higher-resolution images) without exorbitant training times and costs. ([blog post](https://ai.stanford.edu/blog/longer-sequences-next-leap-ai/))  
    
    FlashAttention：具有 IO 意识的快速且内存高效的精确注意力（2022）：斯坦福大学的这项研究为最先进的模型打开了大门，无需过多的训练即可理解更长的文本序列（和更高分辨率的图像）时间和成本。 （博客文章）
-   **[Hungry hungry hippos: Towards language modeling with state space models](https://arxiv.org/abs/2212.14052)** (2022): Again from Stanford, this paper describes one of the leading alternatives to attention in language modeling. This is a promising path to better scaling and training efficiency. ([blog post](https://hazyresearch.stanford.edu/blog/2023-01-20-h3))  
    
    Hungry hungry hippos: Towards language modeling with state space models (2022)：同样来自斯坦福大学，这篇论文描述了语言建模中注意力的主要替代方法之一。这是提高扩展和训练效率的有前途的途径。 （博文）

### **Image generation models 图像生成模型**

-   [**Learning transferable visual models from natural language supervision**](https://arxiv.org/abs/2103.00020) (2021): Paper that introduces a base model — CLIP — that links textual descriptions to images. One of the first effective, large-scale uses of foundation models in computer vision.  
    
    (  
    
    Learning transferable visual models from natural language supervision (2021)：介绍基本模型 CLIP 的论文，该模型将文本描述链接到图像。计算机视觉中基础模型的第一个有效、大规模使用之一。[blog post](https://openai.com/research/clip))
-   [**Zero-shot text-to-image generation**](https://arxiv.org/abs/2102.12092) (2021): This is the paper that introduced DALL-E, a model that combines the aforementioned CLIP and GPT-3 to automatically generate images based on text prompts.  
    
    Its successor, DALL-E 2, would kick off the image-based generative AI boom in 2022. (  
    
    Zero-shot text-to-image generation (2021)：这是介绍 DALL-E 的论文，DALL-E 是一种结合上述 CLIP 和 GPT-3 的模型，可以根据文本提示自动生成图像。[blog post](https://openai.com/research/dall-e))  
    
    它的继任者 DALL-E 2 将在 2022 年开启基于图像的生成人工智能热潮。（博客文章）
-   **[High-resolution image synthesis with latent diffusion models](https://arxiv.org/abs/2112.10752)** (2021): The paper that described Stable Diffusion (after the launch and explosive open source growth).  
    
    High-resolution image synthesis with latent diffusion models (2021)：描述稳定扩散的论文（在发布和爆炸性开源增长之后）。
-   **[Photorealistic text-to-image diffusion models with deep language understanding](https://arxiv.org/abs/2205.11487)** (2022): Imagen was Google’s foray into AI image generation. More than a year after its announcement, the model has yet to be released publicly as of the publish date of this piece.  
    
    (  
    
    具有深度语言理解的真实感文本到图像扩散模型（2022 年）：Imagen 是谷歌进军 AI 图像生成领域的尝试。在发布一年多后，截至本文发布之日，该模型尚未公开发布。[website](https://imagen.research.google/))
-   **[DreamBooth: Fine tuning text-to-image diffusion models for subject-driven generation](https://arxiv.org/abs/2208.12242)** (2022): DreamBooth is a system, developed at Google, for training models to recognize user-submitted subjects and apply them to the context of a prompt (e.g.  
    
    \[USER\] smiling at the Eiffel Tower). ([website](https://dreambooth.github.io/))  
    
    \[用户\] 对着艾菲尔铁塔微笑）。 （ 网站）  
    
    DreamBooth：Fine tuning text-to-image diffusion models for subject-driven generation (2022)：DreamBooth 是谷歌开发的一个系统，用于训练模型识别用户提交的主题并将它们应用于提示的上下文（例如
-   [**Adding conditional control to text-to-image diffusion models**](https://arxiv.org/abs/2302.05543) (2023): This paper from Stanford introduces ControlNet, a now very popular tool for exercising fine-grained control over image generation with latent diffusion models.  
    
    Adding conditional control to text-to-image diffusion models (2023)：斯坦福大学的这篇论文介绍了 ControlNet，这是一种现在非常流行的工具，用于使用潜在扩散模型对图像生成进行细粒度控制。

### **Agents**

-   [**A path towards autonomous machine intelligence**](https://openreview.net/pdf?id=BZ5a1r-kVsf) (2022): A proposal from Meta AI lead and NYU professor Yann LeCun on how to build autonomous and intelligent agents that truly understand the world around them.  
    
    A path to autonomous machine intelligence (2022)：Meta AI 负责人和纽约大学教授 Yann LeCun 关于如何构建真正了解周围世界的自主和智能代理的提案。
-   **[ReAct: Synergizing reasoning and acting in language models](https://arxiv.org/abs/2210.03629)** (2022): A project out of Princeton and Google to test and improve the reasoning and planning abilities of LLMs. ([blog post](https://ai.googleblog.com/2022/11/react-synergizing-reasoning-and-acting.html))  
    
    ReAct：Synergizing reasoning and acting in language models (2022)：普林斯顿大学和谷歌的一个项目，旨在测试和提高法学硕士的推理和规划能力。 （博文）
-   [**Generative agents: Interactive simulacra of human behavior**](https://arxiv.org/abs/2304.03442) (2023): Researchers at Stanford and Google used LLMs to power agents, in a setting akin to “The Sims,” whose interactions are emergent rather than programmed.  
    
    Generative agents: Interactive simulacra of human behavior (2023)：斯坦福大学和谷歌的研究人员在类似于“模拟人生”的环境中使用 LLM 为代理提供动力，其交互是紧急的而不是程序化的。
-   [**Reflexion: an autonomous agent with dynamic memory and self-reflection**](https://arxiv.org/abs/2303.11366) (2023): Work from researchers at Northeastern University and MIT on teaching LLMs to solve problems more reliably by learning from their mistakes and past experiences.  
    
    Reflexion: an autonomous agent with dynamic memory and self-reflection (2023)：东北大学和麻省理工学院的研究人员致力于教授 LLM，通过从他们的错误和过去的经验中学习来更可靠地解决问题。
-   **[Toolformer: Language models can teach themselves to use tools](https://arxiv.org/abs/2302.04761)** (2023): This project from Meta trained LLMs to use external tools (APIs, in this case, pointing to things like search engines and calculators) in order to improve accuracy without increasing model size.   
    
    Toolformer：Language models can teach themselves to use tools (2023)：这个项目来自 Meta 训练的 LLM 使用外部工具（API，在这种情况下，指向搜索引擎和计算器之类的东西），以便在不增加模型大小的情况下提高准确性。
-   **[Auto-GPT: An autonomous GPT-4 experiment](https://github.com/Significant-Gravitas/Auto-GPT)**: An open source experiment to expand on the capabilities of GPT-4 by giving it a collection of tools (internet access, file storage, etc.) and choosing which ones to use in order to solve a specific task.  
    
    Auto-GPT：一项自主的 GPT-4 实验：一项开源实验，通过为 GPT-4 提供一组工具（互联网访问、文件存储等）并选择要使用的工具来扩展 GPT-4 的功能解决一个特定的任务。
-   **[BabyAGI](https://github.com/yoheinakajima/babyagi)**: This Python script utilizes GPT-4 and vector databases (to store context) in order to plan and executes a series of tasks that solve a broader objective.  
    
    BabyAGI：这个 Python 脚本利用 GPT-4 和矢量数据库（存储上下文）来规划和执行一系列任务，以解决更广泛的目标。

### **Other data modalities 其他数据模式**

**Code generation**

-   **[Evaluating large language models trained on code](https://arxiv.org/abs/2107.03374)** (2021): This is OpenAI’s research paper for Codex, the code-generation model behind the GitHub Copilot product. ([blog post](https://openai.com/blog/openai-codex))  
    
    Evaluating large language models trained on code (2021)：这是 OpenAI 的 Codex 研究论文，Codex 是 GitHub Copilot 产品背后的代码生成模型。 （博客文章）
-   **[Competition-level code generation with AlphaCode](https://www.science.org/stoken/author-tokens/ST-905/full)** (2021): This research from DeepMind demonstrates a model capable of writing better code than human programmers. ([blog post](https://www.deepmind.com/blog/competitive-programming-with-alphacode))  
    
    使用 AlphaCode 进行竞争级代码生成（2021 年）：DeepMind 的这项研究展示了一种能够编写比人类程序员更好的代码的模型。 （博文）
-   **[CodeGen: An open large language model for code with multi-turn program synthesis](https://arxiv.org/abs/2203.13474)** (2022): CodeGen comes out of the AI research arm at Salesforce, and currently underpins the Replit Ghostwriter product for code generation. ([blog post](https://blog.salesforceairesearch.com/codegen/))  
    
    CodeGen：具有多轮程序合成的开放式大型代码语言模型（2022 年）：CodeGen 来自 Salesforce 的 AI 研究部门，目前支持用于代码生成的 Replit Ghostwriter 产品。 （博文）

**Video generation**

-   **[Make-A-Video: Text-to-video generation without text-video data](https://arxiv.org/abs/2209.14792)** (2022): A model from Meta that creates short videos from text prompts, but also adds motion to static photo inputs or creates variations of existing videos. ([blog post](https://makeavideo.studio/))  
    
    Make-A-Video：没有文本视频数据的文本到视频生成（2022）：Meta 的一个模型，可以根据文本提示创建短视频，还可以为静态照片输入添加动作或创建现有视频的变体。 （博客文章）
-   [**Imagen Video: High definition video generation with diffusion models**](https://arxiv.org/abs/2210.02303) (2022): Just what it sounds like: a version of Google’s image-based Imagen model optimized for producing short videos from text prompts. ([website](https://imagen.research.google/video/))  
    
    Imagen Video: High definition video generation with diffusion models (2022)：顾名思义：Google 基于图像的 Imagen 模型的一个版本，优化用于根据文本提示生成短视频。 （网站）

**Human biology and medical data 人类生物学和医学数据**

-   [**Strategies for pre-training graph neural networks**](https://arxiv.org/pdf/1905.12265.pdf) (2020): This publication laid the groundwork for effective pre-training methods useful for applications across drug discovery, such as molecular property prediction and protein function prediction. ([blog post](https://snap.stanford.edu/gnn-pretrain/))  
    
    Strategies for pre-training graph neural networks (2020)：该出版物为有效的预训练方法奠定了基础，这些方法可用于药物发现的应用，例如分子特性预测和蛋白质功能预测。 （博文）
-   [**Improved protein structure prediction using potentials from deep learning**](https://www.nature.com/articles/s41586-019-1923-7) (2020): DeepMind’s protein-centric transformer model, AlphaFold, made it possible to predict protein structure from sequence — a true breakthrough which has already had far-reaching implications for understanding biological processes and developing new treatments for diseases. ([blog post](https://www.deepmind.com/blog/alphafold-a-solution-to-a-50-year-old-grand-challenge-in-biology)) ([explainer](https://www.blopig.com/blog/2021/07/alphafold-2-is-here-whats-behind-the-structure-prediction-miracle/))  
    
    利用深度学习的潜力改进蛋白质结构预测（2020 年）：DeepMind 的以蛋白质为中心的转换器模型 AlphaFold 使从序列预测蛋白质结构成为可能——这是一个真正的突破，已经对理解生物过程和开发新的生物过程产生了深远的影响疾病的治疗。 （博客文章）（解释器）
-   [**Large language models encode clinical knowledge**](https://arxiv.org/abs/2212.13138) (2022): Med-PaLM is a LLM capable of correctly answering US Medical License Exam style questions.  
    
    The team has since published results on the performance of Med-PaLM2, which achieved a score on par with “expert” test takers. Other teams have performed similar experiments with  
    
    大型语言模型编码临床知识 (2022)：Med-PaLM 是一种能够正确回答美国医学执照考试风格问题的 LLM。[ChatGPT](https://www.medrxiv.org/content/10.1101/2022.12.19.22283643v2) and [GPT-4](https://arxiv.org/abs/2303.13375). ([video](https://www.youtube.com/watch?v=saWEFDRuNJc))  
    
    此后，该团队公布了 Med-PaLM2 的性能结果，其得分与“专家”测试者相当。其他团队已经用 ChatGPT 和 GPT-4 进行了类似的实验。 （ 视频）

**Audio generation**

-   [**Jukebox: A generative model for music**](https://arxiv.org/abs/2005.00341) (2020): OpenAI’s foray into music generation using transformers, capable of producing music, vocals, and lyrics with minimal training. ([blog post](https://openai.com/research/jukebox))  
    
    自动点唱机：音乐生成模型（2020 年）：OpenAI 使用变形金刚进军音乐生成领域，能够通过最少的训练生成音乐、人声和歌词。 （博客文章）
-   [**AudioLM: a language modeling approach to audio generation**](https://arxiv.org/pdf/2209.03143.pdf) (2022): AudioLM is a Google project for generating multiple types of audio, including speech and instrumentation. ([blog post](https://ai.googleblog.com/2022/10/audiolm-language-modeling-approach-to.html))  
    
    AudioLM: a language modeling approach to audio generation (2022)：AudioLM 是一个谷歌项目，用于生成多种类型的音频，包括语音和乐器。 （博客文章）
-   [**MusicLM: Generating nusic from text**](https://arxiv.org/abs/2301.11325) (2023): Current state of the art in AI-based music generation, showing higher quality and coherence than previous attempts. ([blog post](https://google-research.github.io/seanet/musiclm/examples/))  
    
    MusicLM: Generating nusic from text (2023)：基于 AI 的音乐生成的最新技术，显示出比以前的尝试更高的质量和连贯性。 （博客文章）

**Multi-dimensional image generation  

多维图像生成**

-   [**NeRF: Representing scenes as neural radiance fields for view synthesis**](https://arxiv.org/abs/2003.08934) (2020): Research from a UC-Berkeley-led team on “synthesizing novel views of complex scenes” using 5D coordinates. ([website](https://www.matthewtancik.com/nerf))  
    
    NeRF：Representing scenes as neural radiance fields for view synthesis (2020)：加州大学伯克利分校领导的团队使用 5D 坐标“合成复杂场景的新颖视图”的研究。 （网站）
-   **[DreamFusion: Text-to-3D using 2D diffusion](https://arxiv.org/pdf/2209.14988.pdf)** (2022): Work from researchers at Google and UC-Berkeley that builds on NeRF to generate 3D images from 2D inputs. ([website](https://dreamfusion3d.github.io/))  
    
    DreamFusion: Text-to-3D using 2D diffusion (2022)：谷歌和加州大学伯克利分校研究人员的工作，基于 NeRF 从 2D 输入生成 3D 图像。 （网站）

_Special thanks to_ [_Jack Soslow_](https://a16z.com/author/jack-soslow/)_,_ [_Jay Rughani_](https://a16z.com/author/jay-rughani/)_,_ [_Marco Mascorro_](https://a16z.com/author/marco-mascorro/)_, [Martin Casado](https://a16z.com/author/martin-casado/),_ [_Rajko Radovanovic_](https://a16z.com/author/rajko-radovanovic/)_, and_ [_Vijay Pande_](https://a16z.com/author/vijay-pande/) _for their contributions to this piece, and to the entire a16z team for an always informative discussion about the latest in AI. And thanks to_ [_Sonal Chokshi_](https://a16z.com/author/sonal-chokshi/) _and the crypto team for building a long series of canons at the firm._  

特别感谢 Jack Soslow、Jay Rughani、Marco Mascorro、Martin Casado、Rajko Radovanovic 和 Vijay Pande 对本文所做的贡献，并感谢整个 a16z 团队就 AI 的最新进展进行的信息丰富的讨论。还要感谢 Sonal Chokshi 和加密货币团队在公司建立了一系列经典。

\* \* \*

_The views expressed here are those of the individual AH Capital Management, L.L.C. (“a16z”) personnel quoted and are not the views of a16z or its affiliates.  

此处表达的观点是 AH Capital Management, L.L.C. 个人的观点。 (“a16z”) 人员引用但不代表 a16z 或其附属公司的观点。  

Certain information contained in here has been obtained from third-party sources, including from portfolio companies of funds managed by a16z.  

此处包含的某些信息是从第三方来源获得的，包括来自 a16z 管理的基金的投资组合公司。  

While taken from sources believed to be reliable, a16z has not independently verified such information and makes no representations about the enduring accuracy of the information or its appropriateness for a given situation.  

虽然取自被认为可靠的来源，但 a16z 并未独立核实此类信息，也不对信息的持久准确性或其对特定情况的适用性做出任何陈述。  

In addition, this content may include third-party advertisements; a16z has not reviewed such advertisements and does not endorse any advertising content contained therein.  

此外，此内容可能包含第三方广告； a16z 没有审查过此类广告，也不认可其中包含的任何广告内容。_

_This content is provided for informational purposes only, and should not be relied upon as legal, business, investment, or tax advice.  

此内容仅供参考，不应作为法律、商业、投资或税务建议。  

You should consult your own advisers as to those matters.  

您应该就这些事项咨询您自己的顾问。  

References to any securities or digital assets are for illustrative purposes only, and do not constitute an investment recommendation or offer to provide investment advisory services.  

对任何证券或数字资产的引用仅供说明之用，并不构成投资建议或提供投资咨询服务的要约。  

Furthermore, this content is not directed at nor intended for use by any investors or prospective investors, and may not under any circumstances be relied upon when making a decision to invest in any fund managed by a16z.  

此外，本内容不针对或旨在供任何投资者或潜在投资者使用，并且在任何情况下都不得在决定投资 a16z 管理的任何基金时予以依赖。_

_(An offering to invest in an a16z fund will be made only by the private placement memorandum, subscription agreement, and other relevant documentation of any such fund and should be read in their entirety.) Any investments or portfolio companies mentioned, referred to, or described are not representative of all investments in vehicles managed by a16z, and there can be no assurance that the investments will be profitable or that other investments made in the future will have similar characteristics or results._

_  

（投资 a16z 基金的要约只能通过私募备忘录、认购协议和任何此类基金的其他相关文件进行，并且应完整阅读。）提及、提及或提及的任何投资或投资组合公司所描述的并不代表对 a16z 管理的车辆的所有投资，并且不能保证这些投资将盈利或未来进行的其他投资将具有类似的特征或结果。  

A list of investments made by funds managed by Andreessen Horowitz (excluding investments for which the issuer has not provided permission for a16z to disclose publicly as well as unannounced investments in publicly traded digital assets) is available at https://a16z.com/investments/.  

由 Andreessen Horowitz 管理的基金进行的投资清单（不包括发行人未允许 a16z 公开披露的投资以及未宣布的公开交易数字资产投资）可在 https://a16z.com/investments 获取/._

_Charts and graphs provided within are for informational purposes solely and should not be relied upon when making any investment decision.  

其中提供的图表仅供参考，在做出任何投资决定时不应依赖。  

Past performance is not indicative of future results. The content speaks only as of the date indicated.  

过去的表现并不预示未来的结果。内容仅在指定日期有效。  

Any projections, estimates, forecasts, targets, prospects, and/or opinions expressed in these materials are subject to change without notice and may differ or be contrary to opinions expressed by others.  

这些材料中表达的任何预测、估计、预测、目标、前景和/或意见如有更改，恕不另行通知，并且可能与其他人表达的意见不同或相反。  

Please see https://a16z.com/disclosures for additional important information.  

请参阅 https://a16z.com/disclosures 了解更多重要信息。_
