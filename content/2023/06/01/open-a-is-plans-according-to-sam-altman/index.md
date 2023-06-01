---
title: "根据 Sam Altman 的 OpenAI 计划"
date: 2023-06-01T22:01:48+08:00
updated: 2023-06-01T22:01:48+08:00
taxonomies:
  tags: []
extra:
  source: https://humanloop.com/blog/openai-plans
  hostname: humanloop.com
  author: Raza Habib
  original_title: "OpenAI's plans according to Sam Altman"
  original_lang: zh
---

## OpenAI’s plans according to Sam Altman  

根据 Sam Altman 的说法，OpenAI 的计划

Last week I had the privilege to sit down with Sam Altman and 20 other developers to discuss OpenAI’s APIs and their product plans. Sam was remarkably open.  

上周，我有幸与 Sam Altman 和其他 20 位开发人员坐下来讨论 OpenAI 的 API 及其产品计划。萨姆非常开放。  

The discussion touched on practical developer issues as well as bigger-picture questions related to OpenAI’s mission and the societal impact of AI. Here are the key takeaways:  

讨论涉及实际的开发人员问题以及与 OpenAI 的使命和人工智能的社会影响相关的更宏观的问题。以下是要点：

## 1\. OpenAI is heavily GPU limited at present  

1\. OpenAI 目前严重受 GPU 限制

A common theme that came up throughout the discussion was that currently OpenAI is extremely GPU-limited and this is delaying a lot of their short-term plans.  

整个讨论中出现的一个共同主题是，目前 OpenAI 非常受 GPU 限制，这推迟了他们的许多短期计划。  

The biggest customer complaint was about the reliability and speed of the API. Sam acknowledged their concern and explained that most of the issue was a result of GPU shortages.  

最大的客户抱怨是关于 API 的可靠性和速度。 Sam 承认他们的担忧，并解释说大部分问题是 GPU 短缺造成的。

**The longer 32k context can’t yet be rolled out to more people**.  

更长的 32k 上下文还不能推广给更多人。  

OpenAI haven’t overcome the O(n^2) scaling of attention and so whilst it seemed plausible they would have 100k - 1M token context windows soon (this year) anything bigger would require a research breakthrough.  

OpenAI 还没有克服 O(n^2) 的注意力扩展，因此尽管他们很快就会有 100k - 1M 令牌上下文窗口（今年）似乎有道理，但任何更大的东西都需要研究突破。

**The finetuning API is also currently bottlenecked by GPU availability.** They don’t yet use efficient finetuning methods like [Adapters](https://arxiv.org/abs/2304.01933) or [LoRa](https://arxiv.org/abs/2106.09685) and so finetuning is very compute-intensive to run and manage. Better support for finetuning will come in the future.  

微调 API 目前也受到 GPU 可用性的瓶颈。他们还没有使用适配器或 LoRa 等高效的微调方法，因此微调的运行和管理需要大量计算。将来会更好地支持微调。  

They may even host a marketplace of community contributed models.  

他们甚至可能举办社区贡献模型的市场。

**Dedicated capacity offering is limited by GPU availability.** OpenAI also offers dedicated capacity, which provides customers with a private copy of the model.  

专用容量产品受 GPU 可用性的限制。 OpenAI 还提供专用容量，为客户提供模型的私有副本。  

To access this service, customers must be willing to commit to a $100k spend upfront.  

要获得这项服务，客户必须愿意预先支付 10 万美元。

## 2\. OpenAI’s near-term roadmap 2\. OpenAI 的近期路线图

Sam shared what he saw as OpenAI’s provisional near-term roadmap for the API.  

Sam 分享了他所看到的 OpenAI 的 API 临时近期路线图。

**2023:**

-   **Cheaper and faster GPT-4 —** This is their top priority.  
    
    更便宜更快的 GPT-4——这是他们的首要任务。  
    
    In general, OpenAI’s aim is to drive “the cost of intelligence” down as far as possible and so they will work hard to continue to reduce the cost of the APIs over time.  
    
    总的来说，OpenAI 的目标是尽可能降低“智能成本”，因此随着时间的推移，他们将努力继续降低 API 的成本。
-   **Longer context windows —** Context windows as high as 1 million tokens are plausible in the near future.  
    
    更长的上下文窗口——在不久的将来，上下文窗口可能高达 100 万个令牌。
-   **Finetuning API —** The finetuning API will be extended to the latest models but the exact form for this will be shaped by what developers indicate they really want.  
    
    Finetuning API——微调 API 将扩展到最新的模型，但具体形式将取决于开发人员表示他们真正想要的东西。
-   **A stateful API —** When you call the chat API today, you have to repeatedly pass through the same conversation history and pay for the same tokens again and again.  
    
    一个有状态的 API——当你今天调用聊天 API 时，你必须反复传递相同的对话历史并一次又一次地为相同的令牌付费。  
    
    In the future there will be a version of the API that remembers the conversation history.  
    
    将来会有一个记住对话历史记录的 API 版本。

**2024:**

-   **Multimodality —** This was demoed as part of the GPT-4 release but can’t be extended to everyone until after more GPUs come online.  
    
    多模态——这是作为 GPT-4 版本的一部分进行演示的，但在更多 GPU 上线之前不能扩展到所有人。

## 3\. Plugins “don’t have PMF” and are probably not coming to the API anytime soon  

3\. 插件“没有 PMF”并且可能不会很快出现在 API 中

A lot of developers are interested in getting access to ChatGPT plugins via the API but Sam said he didn’t think they’d be released any time soon.  

许多开发人员对通过 API 访问 ChatGPT 插件很感兴趣，但 Sam 表示他认为这些插件不会很快发布。  

The usage of plugins, other than browsing, suggests that they don’t have PMF yet.  

除了浏览之外，插件的使用表明他们还没有 PMF。  

He suggested that a lot of people thought they wanted their apps to be inside ChatGPT but what they really wanted was ChatGPT in their apps.  

他建议很多人认为他们希望他们的应用程序在 ChatGPT 中，但他们真正想要的是他们应用程序中的 ChatGPT。

## 4\. OpenAI will avoid competing with their customers — other than with ChatGPT  

4\. OpenAI 将避免与他们的客户竞争——除了 ChatGPT

Quite a few developers said they were nervous about building with the OpenAI APIs when OpenAI might end up releasing products that are competitive to them.  

不少开发人员表示，当 OpenAI 可能最终发布对他们具有竞争力的产品时，他们对使用 OpenAI API 进行构建感到紧张。  

Sam said that OpenAI would not release more products beyond ChatGPT.  

Sam 表示 OpenAI 不会发布 ChatGPT 以外的更多产品。  

He said there was a history of great platform companies having a killer app and that ChatGPT would allow them to make the APIs better by being customers of their own product.  

他说，伟大的平台公司拥有杀手级应用程序的历史由来已久，而 ChatGPT 将允许他们通过成为自己产品的客户来改进 API。  

The vision for ChatGPT is to be a super smart assistant for work but there will be a lot of other GPT use-cases that OpenAI won’t touch.  

ChatGPT 的愿景是成为工作的超级智能助手，但还有许多 OpenAI 不会触及的其他 GPT 用例。

## 5\. Regulation is needed but so is open source  

5\. 需要监管，但也需要开源

While Sam is calling for regulation of future models, he didn’t think existing models were dangerous and thought it would be a big mistake to regulate or ban them.  

虽然 Sam 呼吁对未来的模型进行监管，但他认为现有模型并不危险，并认为监管或禁止它们将是一个大错误。  

He reiterated his belief in the importance of open source and said that OpenAI was considering open-sourcing GPT-3. Part of the reason they hadn’t open-sourced yet was that he was skeptical of how many individuals and companies would have the capability to host and serve large LLMs.  

他重申了他对开源重要性的信念，并表示 OpenAI 正在考虑开源 GPT-3。他们还没有开源的部分原因是他怀疑有多少个人和公司有能力托管和服务大型 LLM。

## 6\. The scaling laws still hold  

6\. 比例定律仍然成立

Recently many articles have claimed that “[the age of giant AI Models is already over](https://www.wired.com/story/openai-ceo-sam-altman-the-age-of-giant-ai-models-is-already-over/)”. This wasn’t an accurate representation of what was meant.  

最近很多文章声称“巨型AI模型时代已经结束”。这不是对意思的准确表述。

OpenAI’s internal data suggests the scaling laws for model performance continue to hold and making models larger will continue to yield performance.  

OpenAI 的内部数据表明，模型性能的比例定律继续存在，使模型变大将继续产生性能。  

The rate of scaling can’t be maintained because OpenAI had made models millions of times bigger in just a few years and doing that going forward won’t be sustainable.  

扩展的速度无法维持，因为 OpenAI 在短短几年内就将模型放大了数百万倍，而这种做法在未来将无法持续。  

That doesn’t mean that OpenAI won't continue to try to make the models bigger, it just means they will likely double or triple in size each year rather than increasing by many orders of magnitude.  

这并不意味着 OpenAI 不会继续尝试让模型变得更大，这只是意味着它们的规模每年可能会增加一倍或三倍，而不是增加许多数量级。

The fact that scaling continues to work has significant implications for the timelines of AGI development.  

缩放继续起作用的事实对 AGI 开发的时间表具有重大影响。  

The scaling hypothesis is the idea that we may have most of the pieces in place needed to build AGI and that most of the remaining work will be taking existing methods and scaling them up to larger models and bigger datasets.  

扩展假设是这样一种想法，即我们可能拥有构建 AGI 所需的大部分内容，并且大部分剩余工作将采用现有方法并将它们扩展到更大的模型和更大的数据集。  

If the era of scaling was over then we should probably expect AGI to be much further away. The fact the scaling laws continue to hold is [strongly suggestive of shorter timelines.](https://www.metaculus.com/questions/5121/date-of-artificial-general-intelligence/)  

如果扩展时代已经结束，那么我们或许应该期望 AGI 离我们更远。缩放定律继续成立的事实强烈暗示了更短的时间表。
