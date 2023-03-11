---
title: "人工智能内容生成第四部分：下一步是什么"
date: 2023-03-09T08:52:48+08:00
updated: 2023-03-09T08:52:48+08:00
taxonomies:
  tags: []
extra:
  source: https://www.jonstokes.com/p/ai-content-generation-part-4-whats
  hostname: www.jonstokes.com
  author: Jon Stokes
  original_title: "AI Content Generation, Part 4: What’s next"
  original_lang: en
---

_This is Part 4 of a multi-part series on AI content generation. If you haven’t caught up on the series, you may want to do so before continuing. Part 1 covers [machine learning basics](https://www.jonstokes.com/p/ai-content-generation-part-1-machine), [Part 2 covers ML tasks](https://www.jonstokes.com/p/ai-content-generation-part-2-tasks) and gives an overview of different models, and Part 3 is a [deep dive into Stable Diffusion](https://www.jonstokes.com/p/getting-started-with-stable-diffusion).  

这是关于人工智能内容生成的多部分系列中的第四部分。如果你还没有赶上这个系列，你可能想在继续之前这样做。第一部分涵盖了机器学习的基础知识，第二部分涵盖了ML任务并对不同的模型进行了概述，第三部分是对稳定扩散的深入研究。_

_If you’re building any of the stuff I describe in this piece or that I cover in this Substack, then you can [use this form to tell me about it](https://airtable.com/shrypue3MSXxsZEDS) and I may be able to help you get connected with funding.  

如果你正在建造我在这篇文章中描述的任何东西，或者我在这个Substack中涉及的东西，那么你可以使用这个表格告诉我，我可能会帮助你与资金联系。_

[![](https3A2F2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com2Fpublic2Fimages2F4aaaedbe-6b85-454f-91a7-19c9c34b8ffa_768x512.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4aaaedbe-6b85-454f-91a7-19c9c34b8ffa_768x512.png)

**Prompt:** Robots building the city of the future, trees, bushes, intricate detail, illustration, façade, baroque, golden ratio, unreal engine 5, fake detail, trending pixiv fanbox, style of makoto shinkai studio ghibli genshin impact james gilleard greg rutkowski chiho aoshima. **Seed:** 913501555  

提示。机器人建造未来的城市，树木，灌木，复杂的细节，插图，外墙，巴洛克风格，黄金比例，虚幻引擎5，假的细节，趋势pixiv粉丝盒，风格makoto shinkai studio ghibli genshin impact james gilleard greg rutkowski chiho aoshima。种子：913501555

“A new primitive” — that’s how OpenAI’s Sam Altman referred to machine learning in a [recent chat](https://www.youtube.com/watch?v=WHoWGNQRXb0) with Reid Hoffman. This “new primitive” has recently been applied to web3 tech like NFTs, and loosely translated it means something like:  

"一种新的原始手段"--这是OpenAI的Sam Altman在最近与Reid Hoffman的聊天中提到的机器学习。这种 "新的基本原理 "最近被应用于像NFT这样的web3技术，粗略地翻译一下，它的意思是这样的。

> _A new capability we didn’t have before, and that we can build new things with. Not a technology most of us will use in isolation, like social media, but more of an enabling tech — like hypertext, the OSI network stack, or distributed ledger technology (a.k.a. cryptocurrencies) — that will support a combinatorial explosion of new user experiences and businesses.  
> 
> 一种我们以前没有的新能力，我们可以用它来构建新事物。这不是我们大多数人将孤立使用的技术，如社交媒体，而是更多的使能技术--如超文本、OSI网络栈或分布式账本技术（又称加密货币）--将支持新用户体验和业务的组合爆炸。_

I’ve now spent some time with this new primitive and with the communities that are rapidly growing up around it — Discords, Github pages, Google Colab notebooks, academic papers, YouTube — and I have some thoughts about what it is and what’s next.  

我现在已经花了一些时间来研究这个新的原始概念和围绕它迅速成长起来的社区--Discords、Github页面、Google Colab笔记本、学术论文、YouTube--我对它是什么和下一步有了一些想法。

This article is divided into two main sections:  

本文分为两个主要部分。

1.  **Macro trends**, i.e., things that are happening at the layer of models and tasks that will drive changes in the application layer.  
    
    宏观趋势，即发生在模型和任务层的事情，将推动应用层的变化。
    
2.  **Application trends**, i.e., concrete applications that we’ll start seeing very soon.  
    
    应用趋势，即我们将很快开始看到的具体应用。
    

The idea is to give a high-level overview of a handful of the forces that are shaping the machine learning space, and then try to game out how those forces will impact hardware and software in the near to medium term.  

我们的想法是对塑造机器学习领域的少数力量做一个高层次的概述，然后试图找出这些力量在近期和中期内将如何影响硬件和软件。

**Contents:  

内容。**

-   Macro trends  
    
    宏观趋势
    
    -   Decentralized AI  
        
        去中心化的人工智能
        
    -   Personalized models  
        
        个性化的模式
        
        -   Alternate realities  
            
            替代现实
            
        -   Neoauthorship and text generation  
            
            新作者身份和文本生成
            
    -   Prompt inference  
        
        提示性推断
        
    -   Core improvements  
        
        核心改进
        
        -   Continual learning  
            
            持续的学习
            
        -   Multimodal models  
            
            多模态模型
            
        -   Optimization and tuning  
            
            优化和调整
            
-   Application trends  
    
    应用趋势
    
    -   Co-creation  
        
        共同创造
        
    -   Text-to-task  
        
        文本到任务
        
    -   Infinite remastering  
        
        无限的重制版
        
    -   Digital prosthetics and real-time, full-spectrum anonymity  
        
        数字假肢和实时、全谱系的匿名性
        
    -   On-demand, personalized retail  
        
        按需、个性化的零售
        
-   Conclusions  
    
    结论
    

This list of macro trends that are driving big changes in AI is very incomplete and doesn’t even include many of the things ML researchers are talking about right now. But I selected these to cover because these are the trends that keep coming up for me as I think about user-facing applications and platforms.  

这份推动人工智能大变革的宏观趋势清单是非常不完整的，甚至不包括ML研究人员现在正在讨论的许多事情。但我选择了这些内容，因为这些是我在思考面向用户的应用程序和平台时不断出现的趋势。

The term “decentralized AI” can mean a few things, but I’m partial to the definition that Balaji Srinivasan and StablilityAI’s Emad Mostaque both use, which is: _AI that’s open-source, collaborative, and not controlled by any one entity_.  

"去中心化的人工智能 "一词可以有几种含义，但我偏向于Balaji Srinivasan和StablilityAI的Emad Mostaque都使用的定义，即：开源的、协作的、不受任何一个实体控制的AI。

In a world of decentralized AI, the middle part of this diagram from Part 2 of this series will blow up, as models and variants of models proliferate:  

在一个去中心化的人工智能世界里，本系列第二部分中的这张图的中间部分将会爆炸，因为模型和模型的变体会激增。

[![](https3A2F2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com2Fpublic2Fimages2F1c030ba7-2462-4100-84fe-f3bc47bc76b7_1244x693.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1c030ba7-2462-4100-84fe-f3bc47bc76b7_1244x693.png)

Yes, large companies are still going to keep their most state-of-the-art models either totally private (like Google’s Imagen) or walled off behind an API and a license agreement (like DALL-E from OpenAI). But we’ll start to see more models, like Stable Diffusion, that are open-source and freely available to modify and use.  

是的，大公司仍然会将他们最先进的模型完全保密（如谷歌的Imagen），或者将其封锁在API和许可协议后面（如OpenAI的DALL-E）。但我们将开始看到更多的模型，比如稳定扩散，是开源的，可以自由修改和使用。

The shift towards decentralized AI will ultimately have three main drivers:  

向去中心化人工智能的转变最终将有三个主要驱动因素。

1.  Open-source-first companies and collectives (maybe DAOs) whose mission is to keep AI in the public’s hands.  
    
    开源优先的公司和集体（也许是DAO），其使命是将人工智能掌握在公众手中。
    
2.  Closed companies that release their trailing-edge models into the public domain.  
    
    关闭的公司，将他们的前沿模型发布到公共领域。
    
3.  Optimizations and innovations that combine with Moore’s Law and open datasets to make powerful models far cheaper to train, bringing customized models in reach of ever smaller businesses.  
    
    优化和创新与摩尔定律和开放数据集相结合，使强大的模型训练成本大大降低，使越来越多的小型企业能够接触到定制的模型。
    

On this last point, we’re currently entering the era of the sub-$500K GPT-3 competitor, and the cost will continue to drop rapidly:  

关于最后一点，我们目前正在进入50万美元以下的GPT-3竞争对手的时代，而且成本将继续迅速下降。

So the future of AI probably looks a bit like the past of relational databases, where even the biggest commercial users at this point are happily running either Postgresql or MySQL (both of them free and open-source), and Oracle is still making money selling proprietary databases via lock-in and value adds.  

因此，人工智能的未来可能看起来有点像关系型数据库的过去，即使是目前最大的商业用户也在愉快地运行Postgresql或MySQL（两者都是免费和开源的），而甲骨文仍在通过锁定和增值销售专有数据库赚钱。

I’ve spent a fair amount of time in the weeds of how to customize Stable Diffusion by adding my own face to it, so that I can prompt it to generate pictures of “Jon Stokes, a person” in various styles. (I was going to write a how-to on this, but the tools are in such a state of flux that it’s best to wait until things settle down a bit.)  

我花了相当多的时间研究如何通过添加我自己的脸来定制稳定扩散，这样我就可以促使它生成各种风格的 "Jon Stokes，一个人 "的照片。(我本来想写一篇关于这个问题的文章，但这些工具正处于变化之中，最好等到事情稳定下来再写）。

But this time has given me a glimpse of what’s coming really soon: generative models that know me, my family and pets, and my corpus of written work, and can spit out brand new family photos in different locations or new written works in my voice.   

但这段时间让我看到了真正即将到来的东西：了解我、我的家人和宠物以及我的文字作品库的生成模型，并能在不同的地点吐出全新的家庭照片或用我的声音写出新的文字作品。

The kind of **alternate reality image generation** described above is already possible, but the tooling isn’t there to make it widely accessible, yet. The tooling situation will change, though, as any big tech company that hosts photo albums where users are tagged in the photos — Apple, FB, Google — will be able to take all of those tagged photos and offer us customized models where we can take all our friends, relatives, and pets, and put them into new and interesting contexts. Or, we could [subtly tweak](https://petapixel.com/2022/08/01/quantum-mirror-sony-camera-app-uses-dall-e-2-to-reimagine-photos/) a photo by changing the angle or who’s in it. The possibilities are endless.  

上面描述的那种另类现实图像的生成已经是可能的了，但还没有工具来使其广泛使用。不过，工具情况将发生变化，因为任何托管用户在照片中被标记的相册的大型科技公司--苹果、FB、谷歌--将能够采用所有这些被标记的照片，并为我们提供定制模型，我们可以把我们所有的朋友、亲戚和宠物，放到新的和有趣的背景中。或者，我们可以通过改变角度或谁在里面来巧妙地调整一张照片。这种可能性是无穷无尽的。

The alternate reality wave definitely won’t be limited to people and pets. Think about product photography for small-batch and handcrafted items, like Etsy shops and the like. Anyone who makes and sells things online will be able to generate an **infinitely varied library of product photographs** in a range of styles and contexts from a handful of awkward iPhone photos. (The reverse is also true — an Etsy seller will be able to generate photography for a product that doesn’t yet exist, then post it for sale to gauge demand, and then fill orders if enough customers buy it. More on this in the section on retail, below.)  

替代现实的浪潮肯定不会局限于人和宠物。想想小批量和手工制品的产品摄影，比如Etsy商店之类的。任何在网上制造和销售东西的人都能从少量笨拙的iPhone照片中生成一个风格和背景各异的产品照片库。(反之亦然--Etsy卖家将能够为尚不存在的产品生成照片，然后发布销售以衡量需求，如果有足够多的客户购买，再填补订单。关于这一点，请看下面关于零售的部分）。

Text will work similarly to the personalized image generation described in this section. Google’s NLP-based writing suggestions are a small taste of what’s to come, but there’s more in the works. A lot more. Writers like myself, who have a large volume of work online (I’ve archived most of mine with a [paid service called Authory.com](https://authory.com/)) will be able to dump that corpus into a model and get a **customized text generation engine** that sounds like us.  

文字的工作方式与本节所述的个性化图片生成类似。谷歌基于NLP的写作建议是未来的一小部分，但还有更多的工作在进行。还有很多。像我这样在网上有大量作品的作家（我用一个叫Authory.com的付费服务将我的大部分作品归档），将能够把这些语料转入一个模型，得到听起来像我们的定制文本生成引擎。

For a writer like myself, this **AI-powered neoauthorship** might look something like the following:  

对于像我这样的作家来说，这种由人工智能驱动的新作者制度可能看起来像下面这样。

I dump all my research notes on a topic into an app that turns them into an article that reads and sounds like it was written by me because the generative model was trained on my work. And in fact, we could meaningfully argue that generated text will have _actually_ been written by me. What I mean is, if the model was trained on my “voice,” and I personally use it to produce more work under my own name (which I then edit and prepare for publication), then it’s _my work_, right?  

我把所有关于某个主题的研究笔记倒入一个应用程序，该应用程序将它们变成一篇文章，读起来和听起来都像是我写的，因为生成模型是在我的工作上训练的。事实上，我们可以有意义地论证，生成的文本实际上是由我写的。我的意思是，如果这个模型是根据我的 "声音 "训练出来的，而且我亲自用它来产生更多以我的名字命名的作品（然后我编辑并准备出版），那么它就是我的作品，对吗？

Authorship has always been kind of weird — unnamed editors often contribute quite materially to a published article, yet the byline doesn’t reflect that. So neoauthorship is going to be sort of like that, but even weirder.  

作者身份一直都很奇怪--不具名的编辑往往对发表的文章有相当大的贡献，但署名却不能反映这一点。因此，新作者制度将与此类似，但更加奇怪。

There’s more to personalization in AI than just models that are trained on my personal data (images, text, audio, music, etc.). To understand what’s coming, consider how Google currently uses machine learning in the context of personalized search.  

人工智能的个性化不仅仅是在我的个人数据（图像、文本、音频、音乐等）上训练出来的模型。为了了解即将到来的情况，考虑一下谷歌目前如何在个性化搜索的背景下使用机器学习。

Google pulls in a ton of data about me and my interests in order to **infer intent**, so that the search results it offers me are tailored to my geography, past search history, purchase history, email archives, and so on. (At least, that’s how it’s supposed to work. Search quality has degraded so much lately that I’m not sure what the heck they’re actually doing right now.)  

谷歌收集了大量关于我和我的兴趣的数据，以便推断出我的意图，这样它为我提供的搜索结果就会根据我的地理环境、过去的搜索历史、购买历史、电子邮件档案等进行调整。(至少，它应该是这样工作的。最近，搜索质量下降了很多，我不知道他们现在到底在做什么）。

Now imagine this kind of personalization and intent inference, _but for searches of latent space_.  

现在想象一下这种个性化和意图推断，但用于搜索潜在的空间。

An app like [PlaygroundAI](https://playgroundai.com/), which not only has a history of my prompts but also a map of my social graph, can and probably will be tweaked to infer intent from a natural language text input (not an engineered prompt, but a more casual description of what I’m looking for) and offer me a set of results that reflect what I _meant_ (if not what I literally said).   

像PlaygroundAI这样的应用程序，不仅有我的提示历史，还有我的社交图谱，可以而且可能会被调整为从自然语言文本输入（不是工程提示，而是对我正在寻找的东西的更随意的描述）中推断出意图，并为我提供一套反映我的意思的结果（如果不是我字面上说的）。

Imagine an online writing app that knows I like certain styles and subjects, and maybe it also has some data on my purchase history and location — in fact, maybe it knows even more about how I think than Google does because I’ve been curating training data for it by diligently labeling my photos and so on. Let’s say I’ve used this writing app to write most this essay of mine on **[The Can Opener Problem](https://www.jonstokes.com/p/the-can-opener-problem)**.  

想象一下，一个在线写作应用程序知道我喜欢某些风格和主题，也许它还拥有一些关于我的购买历史和位置的数据--事实上，也许它比谷歌更了解我的想法，因为我一直在通过勤奋地标记我的照片等来为它策划训练数据。比方说，我用这个写作软件写了我的这篇关于开罐器问题的文章。

1.  I click the “Add Image” button, and instead of an upload dialog box, I get a prompt window.  
    
    我点击 "添加图片 "按钮，得到的不是一个上传对话框，而是一个提示窗口。
    
2.  I start typing, “Can opener…, “ and it uses the article context to begin autocompleting “…by Leonardo DaVinci, hand drawing, mechanical, detailed…”  
    
    我开始输入 "开罐器......"，它就利用文章的上下文开始自动完成"......达芬奇的作品，手绘，机械，详细......"
    
3.  I hit `tab` to accept the autocompletion, and it generates four different hand-drawn diagrams of a can opener in the style of one of Da Vinci’s mechanical drawings.  
    
    我按下 `tab` 接受自动完成，它生成了四种不同的手绘开罐器图，其风格是达芬奇的机械图之一。
    
4.  I click the one I like best and it inserts it into the page…  
    
    我点击我最喜欢的那个，它就把它插入到页面中...
    

…except it doesn’t _actually_ insert the image into the page. Rather, it just inserts the prompt and seed combination into the page using an image tag like `<img prompt=“A drawing of a can opener by Leonardo Da Vinci, mechanical, detailed, trending on arstation” seed=“45523043” />`, and then the browser uses an optimized image generation model to generate the image on the client side on page load. (See the section below on optimization for more on how this would work.)  

......只是它没有把图片插入到页面中。相反，它只是使用像 `<img prompt=“A drawing of a can opener by Leonardo Da Vinci, mechanical, detailed, trending on arstation” seed=“45523043” />` 这样的图像标签将提示和种子组合插入到页面中，然后浏览器使用优化的图像生成模型，在页面加载时在客户端生成图像。(参见下面关于优化的部分，了解更多关于如何工作的信息）。

There are a number of core improvements to machine learning that will unlock new levels of power and functionality for this class of software. The short list below is by no means comprehensive, and I invite knowledgeable readers to submit more examples in the comments.  

机器学习有许多核心改进，将为这一类软件释放新的力量和功能水平。下面的简短清单绝非全面，我邀请知识渊博的读者在评论中提交更多的例子。

Current machine learning models are run in two separate phases, which take place in this order:  

目前的机器学习模型是在两个独立的阶段运行的，这两个阶段是按照这个顺序进行的。

1.  **Training**: This is where the model is exposed to training data and where it does all its actual learning.  
    
    训练。这是模型接触训练数据的地方，也是它进行所有实际学习的地方。
    
2.  **Inference**: This is the phase where we, the end-users, are actually using the fully trained model to [perform tasks](https://www.jonstokes.com/p/ai-content-generation-part-2-tasks) like classification and content generation.  
    
    推理。这是一个阶段，我们，最终用户，实际上是在使用经过充分训练的模型来执行分类和内容生成等任务。
    

But of course, learning in the real world isn’t a one-off affair like this. Humans and animals are constantly alternating between “training” and “inference” phases, or maybe sometimes we’re essentially in both phases simultaneously.  

但当然，现实世界中的学习并不是像这样一次性的事情。人类和动物不断地在 "训练 "和 "推理 "阶段之间交替进行，也许有时我们基本上是同时处于这两个阶段。

At some point, machine learning models will move to **continual learning**, where they’re constantly going back and updating their impressions of the world as we use them in different contexts.  

在某些时候，机器学习模型将转向持续学习，当我们在不同的环境中使用它们时，它们会不断地回去并更新它们对世界的印象。

This is a lot harder than it sounds, as the current generation of models is so malleable that it’s easy to completely overwrite old information with new information — this is called **[catastrophic forgetting](https://en.wikipedia.org/wiki/Catastrophic_interference)**, and it’s a long-standing, fiendishly difficult problem in neural networks.  

这比听起来要难得多，因为目前这一代的模型可塑性很强，很容易用新的信息完全覆盖旧的信息--这就是所谓的灾难性遗忘，这也是神经网络中一个长期存在的、棘手的问题。

But at some point, we’re going to need models that can continuously learn new concepts and update old concepts with new information while still remembering everything they’ve ever learned.  

但在某些时候，我们将需要能够不断学习新概念和用新信息更新旧概念的模型，同时还能记住他们曾经学过的一切。

Just to unpack this a bit more: not only can I update my mental model of the world, but I can also remember what my mental model was prior to the update. In other words, the history of the evolution of many of my internal concepts is accessible to me and often useful. Machine learning models don’t yet have anything like this kind of meta-cognition, or the ability to access and reason about prior but currently deprecated versions of concepts. We will need a combination of continual learning and meta-cognitive abilities if we’re ever going to get to AGI.  

只是要更多地解开这个问题：我不仅可以更新我对世界的心理模型，而且我还可以记住我的心理模型在更新之前是什么。换句话说，我的许多内部概念的演变历史对我来说是可以访问的，而且往往很有用。机器学习模型还没有任何类似于这种元认知的东西，也没有能力访问和推理先前但目前已被废弃的概念版本。如果我们要实现AGI，我们将需要持续的学习和元认知能力的结合。

**Read more:  

阅读更多。**

-   [Catastrophic interference  
    
    灾难性的干扰](https://en.wikipedia.org/wiki/Catastrophic_interference)
    
-   [Towards Adaptive AI with Continual Learning  
    
    实现持续学习的适应性人工智能](https://ai.kuleuven.be/stories/post/2021-05-10-continual-learning/)
    
-   [Why Continual Learning is the key towards Machine Intelligence  
    
    为什么持续学习是实现机器智能的关键？](https://medium.com/continual-ai/why-continuous-learning-is-the-key-towards-machine-intelligence-1851cb57c308)
    

A multimodal model is a machine learning model that relates different types of input — text, images, video, audio, 3D models, gestures, physiological signals, LIDAR data, etc. — to one another, so that it can understand concepts across different domains.  

多模态模型是一种机器学习模型，它将不同类型的输入--文本、图像、视频、音频、三维模型、手势、生理信号、激光雷达数据等--相互联系起来，从而使它能够理解不同领域的概念。

If you’re using text-to-image generators, then you’re already using multimodal models. But there’s a lot more going on in the research space with these kinds of models.  

如果你正在使用文本-图像生成器，那么你已经在使用多模态模型。但是，在研究领域还有很多关于这类模型的事情在进行。

Multimodal is good for more than things like text-to-image, voice-to-text, or voice-to-video. By combining different types of sensory input, models will be able to do things like detect emotions (see the diagram above). Combine this with the model personalization discussion above, and the implications for hyper-personalized computing experience are amazing and also kinda scary.  

多模态的好处不仅仅是文本到图像，语音到文本，或语音到视频这样的事情。通过结合不同类型的感官输入，模型将能够做一些事情，如检测情绪（见上图）。将此与上面的模型个性化讨论结合起来，对超个性化计算体验的影响是惊人的，也是有点可怕的。

Since Stable Diffusion was released I’ve been watching local execution times drop as new tweaks and optimizations come out from the community. This kind of focused optimization of specific models will continue driving execution times down and bringing locally run models within reach of ever more compute-constrained platforms (tablets, phones, lower-end laptops, etc.).  

自从Stable Diffusion发布以来，我一直看到本地执行时间随着社区的新调整和优化的出现而下降。这种对特定模型的集中优化将继续推动执行时间的下降，并将本地运行的模型带到越来越多的计算受限的平台（平板电脑、手机、低端笔记本电脑等）上。

There will also be fundamental advances in model design and algorithms that will give even more dramatic speedups. For instance, the new optimization below enables diffusion models to generate high-quality images with just 1-4 diffusion steps (as opposed to the 25-50 currently recommended for Stable Diffusion):  

在模型设计和算法方面也会有根本性的进步，这将使速度得到更大幅度的提高。例如，下面的新优化使扩散模型只需1-4个扩散步骤就能生成高质量的图像（而目前稳定扩散模型推荐的步骤为25-50个）。

This would mean no more waiting around for a model to generate an image from a prompt — instead, it would happen instantaneously. This kind of speed has immediate implications far beyond just less time staring at a loading spinner:  

这将意味着不再需要等待模型从提示中生成图像--相反，它将瞬间发生。这种速度的直接影响远远超过了盯着加载旋钮的时间。

-   Imagine a real-time version of Stable Diffusion that can generate a stream of images from a stream of prompt + seed combinations. This would be amazing for text-to-video applications, augmented reality, and virtual reality.  
    
    想象一下，稳定扩散的实时版本可以从提示+种子的组合流中生成图像流。这对于文本到视频的应用、增强现实和虚拟现实来说将是惊人的。
    
-   The diffusion steps are expensive in terms of computation and dollar cost on cloud platforms, so a 1-4 step diffusion model gives you two options:  
    
    扩散步骤在云平台上的计算和美元成本方面都很昂贵，所以1-4步的扩散模型给了你两个选择。
    
    -   A free (or nearly free) image generation service  
        
        一个免费（或几乎免费）的图像生成服务
        
    -   A paid image generation service that gives you a page of results for a prompt, instead of the current standard of one to four results.  
        
        一个付费的图像生成服务，为你的提示提供一页的结果，而不是目前标准的一至四个结果。
        
-   A browser that renders images on-the-fly from a prompt and seed combination given in a simple image tag (see the section above on “Prompt inference” for a hypothetical example of such a tag).  
    
    一个浏览器可以根据简单的图像标签中给出的提示和种子组合来即时渲染图像（关于这种标签的假设性例子，见上文 "提示推理 "一节）。
    
-   A multimodal voice-to-image model that changes its renders interactively in real time in response to voice commands.  
    
    一个多模态的语音-图像模型，可以根据语音指令实时交互地改变其渲染效果。
    

The above are just some random examples I thought of in a few minutes. A global marketplace of millions of active ML developers will come up with tens of thousands of such ideas every day, and then hundreds of millions of software developers downstream of them will iterate on every layer of the stack — from the open models up to the user interfaces. Wild times are ahead.  

以上只是我在几分钟内随机想到的一些例子。一个由数百万活跃的ML开发者组成的全球市场，每天都会提出数以万计的这样的想法，然后他们下游的数以亿计的软件开发者会对堆栈的每一层进行迭代--从开放模型直到用户界面。狂野的时代正在到来。

The model- and task-level developments described above are already giving rise to new classes of applications and to dramatic enhancements of existing applications. The brief survey that follows is by no means comprehensive but should give you a good feel for what to look out for in the next 12-24 months.  

上面描述的模型和任务层面的发展已经产生了新的应用类别和现有应用的巨大增强。下面的简要调查绝不是全面的，但应该让你对未来12-24个月的发展有一个良好的感觉。

**Here’s the bottom line for everything in this section:** what I describe below is a world in which every creative job is essentially a product management job, where you manage and steer a suite of ML-powered tools to produce stunning finished products that would’ve taken teams of humans just a few years before.  

以下是本节所有内容的底线：我下面描述的是一个世界，在这个世界里，每一个创造性的工作本质上都是一个产品管理的工作，你管理和指导一套由ML驱动的工具，以产生令人惊叹的成品，而这些产品在几年前还需要人类的团队。

Machine learning will bring about **the PMification of work** in whatever area it touches.  

机器学习将在它所涉及的任何领域带来工作的PM化。

The first category of apps to emerge in the AI content generation space have been what I’ll refer to as **co-creation apps**: these are apps where the model augments some creative activity that the user is already engaged in.  

在人工智能内容生成领域出现的第一类应用是我所说的合作创造应用：这些应用的模型增强了用户已经参与的一些创造性活动。

Many of us are already using ML-powered co-creation in Gmail, where the company’s models auto-suggest the rest of whatever sentence you start typing:  

我们中的许多人已经在Gmail中使用由ML驱动的共同创作，该公司的模型自动建议你开始输入的任何句子的其余部分。

[![](https3A2F2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com2Fpublic2Fimages2F45cda56f-455f-4a6c-9a8d-833777454861_1206x1236.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F45cda56f-455f-4a6c-9a8d-833777454861_1206x1236.gif)

An even more powerful example of co-creation is AI-powered code generation. [GitHub Copilot](https://github.com/features/copilot) and [Replit’s Generate Code](https://blog.replit.com/generate-code) are two popular code generators that use a specially tuned version of OpenAI’s GPT-3 text generation model to auto-suggest entire blocks of code.  

一个更强大的共同创造的例子是AI驱动的代码生成。 GitHub Copilot和Replit的Generate Code是两个流行的代码生成器，它们使用OpenAI的GPT-3文本生成模型的特别调整版本来自动建议整个代码块。

Code generators eliminate a lot of the copypasta coding and boilerplate generation takes up so much of a developer’s time, allowing coders to focus on solving higher-value problems. These will get a lot more powerful and move well beyond the elimination of boilerplate, but that’s a topic for a future post.  

代码生成器消除了许多复制的编码和模板的生成，占用了开发人员的大量时间，使编码人员能够专注于解决更有价值的问题。这些将变得更加强大，并远远超出消除模板的范围，但这是一个未来文章的主题。

As generative models get more accessible, this kind of co-creation will be low-hanging fruit for many categories of apps, and we’ll start seeing even more of it shortly in some of the following forms:  

随着生成模型越来越容易获得，这种共同创造将成为许多类别的应用程序的低垂果实，我们很快就会开始看到更多这样的形式。

-   APIs that enable any text editor at all (even vi and emacs) to offer Google-style suggestions, longer blocks of generated text, text transformation (e.g., notes and bullet points to polished paragraphs), and code completion.  
    
    使任何文本编辑器（甚至是vi和emacs）都能提供谷歌式的建议、更长的生成文本块、文本转换（例如将注释和子弹头改为精炼的段落）和代码完成的API。
    
-   Plug-ins for popular image editors and drawing tools, so that you can do in-painting, out-painting, image-to-image generation, and maybe even text-to-image generation from within apps like Photoshop, Procreate, Pixelmator, etc.  
    
    流行的图像编辑器和绘图工具的插件，这样你就可以在Photoshop、Procreate、Pixelmator等应用程序中进行画中画、画外画、图像到图像的生成，甚至可能是文本到图像的生成。
    
-   Plug-ins for **[digital audio workstations](https://en.wikipedia.org/wiki/Digital_audio_workstation)** that do generate and transform audio from within the tool.  
    
    数字音频工作站的插件，可以从工具中生成和转换音频。
    

One recently floated concept for how all these might come together is the $1000 blockbuster. We live in a world where Satoshi and others have launched global currencies from their laptops, so it’s not at all wild to speculate that a creative person could use the tools described in this article to produce an entire Hollywood-style movie from their laptop, without a single trained actor, musician, or writer in the mix anywhere.  

最近流传的一个概念是，所有这些可能结合起来的概念是1000美元的大片。我们生活在一个中本聪和其他人从他们的笔记本电脑中推出全球货币的世界里，所以推测一个有创造力的人可以使用本文描述的工具，从他们的笔记本电脑中制作整个好莱坞风格的电影，而没有一个受过训练的演员、音乐家或作家在任何地方。

The bigger picture here is an impending total collapse in the cost of many kinds of artistic and intellectual labor. But much more on this and its implications in a later piece.  

这里的大背景是许多种类的艺术和智力劳动的成本即将全面崩溃。但关于这一点及其影响，在以后的文章中会有更多的介绍。

The Twitter thread above shows a fascinating example of something we’re going to see a lot more of in the coming weeks and months: **text-to-task**. What I mean by this term is, “I type a prompt that describes some desired work product, and the model responds with a prototype that that work product.”  

上面的Twitter线程显示了一个迷人的例子，我们将在未来几周和几个月内看到更多的东西：文本到任务。我对这个术语的意思是，"我输入一个提示，描述一些所需的工作成果，而模型则以该工作成果的原型作为回应。"

Software is the first place this is happening, but advances in [instruction following](https://openai.com/blog/instruction-following/) will bring text-to-task into many other realms. Imagine giving Alexa not just voice commands, but actual high-level instructions. Examples of such prompts might be:  

软件是这种情况发生的第一个地方，但指令跟踪方面的进展将使文本到任务进入许多其他领域。想象一下，给Alexa的不仅仅是语音命令，还有实际的高级指令。这种提示的例子可能是。

-   Alexa, I’m entertaining here at the house on Saturday. I’ll be hosting about fifteen people, and I need vegetarian options for the main course and the sides. The preparation time should be low, and ideally, I should be using up some of the rice I bought last week and still have plenty of.   
    
    Alexa，我周六要在家里招待客人。我将接待大约15个人，我需要主菜和配菜的素食选择。准备时间应该不长，最理想的是，我应该用掉一些我上周买的米，而且还有很多。
    
-   Alexa, I need a new playlist for my car trip. It should be about three hours long and have a lot of deep cuts from the 90s bands I like.   
    
    Alexa，我需要一个新的播放列表，用于我的汽车旅行。它应该有三个小时的长度，并且有很多我喜欢的90年代乐队的深度剪辑。
    
-   Alexa, I just emailed you a web page with plans for a backyard chicken coop. I need you to add all the materials to my Amazon cart.  
    
    Alexa，我刚刚给你发了一个网页，里面有一个后院鸡舍的计划。我需要你把所有的材料加到我的亚马逊购物车里。
    

The general trend will be away from voice or text commands and prompts for carrying out discrete task steps and towards natural language descriptions of finished products where the model can then carry out the steps needed to make the product.  

总的趋势将是从执行离散任务步骤的语音或文本命令和提示，转向对成品的自然语言描述，然后模型可以执行制造产品所需的步骤。

At first, this capability will be limited to work where the sequence of steps is known and can be represented in the training data somehow. This is because hierarchically arranging novel tasks in order of importance, and related reasoning about multi-step processes, is still a hard problem in AI. So we’ll go as far as we can with text-to-task without needing the model to reason on its own about how different steps fit together. But that will be pretty far, especially for repetitive, solved problems that we can pretty easily script in software.  

起初，这种能力将被限制在步骤的顺序是已知的并且可以在训练数据中以某种方式表示的工作。这是因为按重要程度分层安排新任务，以及对多步骤过程进行相关推理，仍然是人工智能中的一个难题。因此，我们将在不需要模型自己推理不同步骤如何配合的情况下，尽可能地使用文本到任务。但这将是相当远的，特别是对于重复的、已解决的问题，我们可以很容易地在软件中编写脚本。

Eventually, models will be able to problem-solve in more unstructured and dynamic ways. But this starts to get into the realm of AGI, so we’ll save that for another day.  

最终，模型将能够以更加非结构化和动态的方式解决问题。但这开始进入AGI的领域，所以我们将把它留到下一天。

Ubiquitous machine learning will make even the highest quality, most elaborate digital artifacts — books, movies, TV shows, and music — easily and cheaply modifiable. We will soon be in the age of the infinite remaster.  

无处不在的机器学习将使即使是最高质量、最精致的数字艺术品--书籍、电影、电视节目和音乐--也可以轻松而廉价地进行修改。我们将很快进入无限重制的时代。

Did you ever want to hear Johnny Cash cover John Prine’s classic, “Angel From Montgomery,” but you can’t find where this was ever recorded? No problem. Which era of Johnny Cash did you have in mind for this? A generative audio model will be able to synthesize a cover in the same way that Stable Diffusion can currently render Gandalf in the style of Studio Ghibli.   

你是否曾经想听约翰尼-卡什翻唱约翰-普林的经典作品《蒙哥马利的天使》，但你找不到这个作品在哪里录制过？没问题。你想到的是哪个时代的Johnny Cash？一个生成性音频模型将能够合成一个翻唱，就像稳定扩散目前能够以吉卜力工作室的风格渲染甘道夫一样。

The culture wars will get even crazier when both studio and high-quality fan remasters of touchstone cultural properties start to emerge. Have you heard any of the [media complaints](https://people.com/tv/friends-creators-shows-lack-of-diversity/) about the lack of diversity in the _Friends_ cast? I expect whoever owns it might eventually release a “patched” version on all the streaming services with the races of the cast altered.  

当工作室和高质量的粉丝重制试金石文化财产开始出现时，文化战争将变得更加疯狂。你听说过媒体对《朋友》广播中缺乏多样性的抱怨吗？我预计不管谁拥有它，最终都可能在所有流媒体服务上发布一个 "补丁 "版本，改变演员的种族。

This kind of remastering will cut the other way, as well. Get ready for a remaster of the new Amazon “Rings of Power” series that makes all the elves and hobbits white. Or a remaster of the upcoming “Little Mermaid” with a white AI-generated character subbed in for black actress Halle Bailey. (Someone on Twitter claimed to have already started on this and even had screencaps, but the account was deleted.)  

这种重制也会从另一个方面切入。准备好迎接亚马逊新的 "力量之环 "系列的重制版，使所有的精灵和霍比特人成为白人。或者即将推出的 "小美人鱼 "的重制版，用一个由人工智能生成的白人角色代替黑人演员哈莉-贝利。(推特上有人声称已经开始做这件事，甚至还有截图，但该账户已被删除）。

I can easily imagine a world where Disney’s entire back catalog gets retroactively scrubbed of its heteronormativity, while trads with laptops not only preserve and redistribute the old stuff but scrub any and all hints of homosexuality from its current and future productions.  

我可以很容易地想象这样一个世界：迪斯尼的整个早期目录被追溯性地清除了它的异性恋，而有笔记本电脑的传统人士不仅保留和重新分配旧的东西，而且从其目前和未来的制作中清除任何和所有的同性恋暗示。

Some kids will read woke Dr. Seuss books that Theodore Geisel never wrote. Other kids will watch keklord8297’s trad remasters of the Netflix She-Ra cartoon. And on and on it’ll go.  

有些孩子会阅读西奥多-盖泽尔从未写过的苏斯博士的醒目书籍。其他孩子会看eklord8297的传统重制版Netflix She-Ra动画片。这一切都将继续下去。

It won’t all be culture wars, though. There’s a massive backlog of cultural materials that can be neutrally restored, colorized, and remastered to better suit the aesthetics and technology of the present times.  

不过，这并不全是文化战争。有大量积压的文化材料可以被中立地修复、着色和重制，以更好地适应当今时代的美学和技术。

For instance, video games will be one of the earliest places to feel an immediate impact from AI models. Users are already using Stable Diffusion to [upgrade the pixel art](https://gameworldobserver.com/2022/09/28/fallout-2-stable-diffusion-reimagined-characters-remake) in older games to a modern, 3D-rendered-looking style.  

例如，视频游戏将是最早感受到AI模型带来的直接影响的地方之一。用户已经在使用稳定扩散技术将旧游戏中的像素艺术升级为现代的、3D渲染的风格。

There are so many classic games that could be redone this way very cheaply. In fact, if you think about the optimizations mentioned above, it’s quite realistic to imagine a world where such visual upgrades of in-game assets are done on the fly by a model embedded in a modified version of the game code — or even by a graphics driver that just works on the data from the frame buffer.  

有很多经典游戏都可以用这种方式重新制作，而且非常便宜。事实上，如果你考虑到上面提到的优化，想象一下这样一个世界是很现实的：游戏中资产的这种视觉升级是由一个嵌入到游戏代码修改版中的模型来完成的--甚至是由一个只在帧缓冲器的数据上工作的图形驱动来完成的。

Instagram filters are a tiny little peek at a much bigger trend that will take hold in the age of ubiquitous AI: **real-time, full-spectrum pseudonymity**.   

Instagram滤镜是对一个更大的趋势的小小窥视，这个趋势将在无处不在的人工智能时代占据一席之地：实时、全光谱的假名。

-   It’s **real-time** because you’ll be using Zoom, FaceTime, or some other video app to communicate, but your voice and appearance will be radically altered in a way that’s not visibly detectable by those on the other end of the link.  
    
    它是实时的，因为你将使用Zoom、FaceTime或其他一些视频应用程序进行交流，但你的声音和外表将以一种链接另一端的人无法明显察觉的方式被彻底改变。
    
-   It’s **full-spectrum** because whatever **digital prosthetic** you produce can be used in every online venue where you show yourself to an audience — from Instagram, to Zoom, to Facebook, to TikTok.  
    
    它是全方位的，因为无论你制作什么样的数字假肢，都可以用在你向观众展示自己的每一个在线场所--从Instagram、Zoom、Facebook到TikTok。
    

To bring this back to the culture wars, again, think about DEI-driven hiring decisions in the era of 100% remote work and pseudonymity. Is your new colleague _really_ a Chinese woman with slightly accented English? If you’ve never seen her outside of remote work, how can you know?  

再把这个问题带回文化战争，想想在100%远程工作和假名的时代，DEI驱动的招聘决定。你的新同事真的是一个有轻微英语口音的中国女人吗？如果你在远程工作之外从未见过她，你怎么能知道？

This kind of tech will obviously be used for psyops, and probably already is because it’s certainly accessible right now to sophisticated enough actors. (Innovation will bring the cost of the tools way down and make the workflows easy enough for even the least technical to master.) Are you _sure_ that the Iranian woman TikToker who’s chronicling the present protests for your feed isn’t a Saudi man wearing digital makeup?  

这种技术显然会被用于心理战术，而且可能已经在使用了，因为现在肯定有足够成熟的演员可以使用这种技术。(创新将使工具的成本大大降低，并使工作流程变得足够简单，即使是技术水平最低的人也能掌握）。你确定那个为你记录当前抗议活动的伊朗妇女TikToker不是一个化了数字妆的沙特人吗？

Of course, what technology takes away, tech can give back:  

当然，技术带走的东西，技术也可以回馈。

So at least we can hope that such manipulation will be flagged when it’s happening.  

因此，至少我们可以希望，这种操纵行为在发生时将被标记出来。

(In case you’re wondering, I plan on using this tech to remain my 27-year-old self in perpetuity. Not only was I in really good shape then, but this will also make me immune to Silicon Valley ageism.)  

(如果你想知道，我打算用这项技术来永久保持27岁的自己。不仅那时我的状态非常好，而且这也会使我对硅谷的年龄歧视有免疫力）。

The legacy retail workflow has been something like: design => build => sell => ship. The ML-driven workflow, in contrast, will look like: design => sell => build => ship.   

传统的零售工作流程是这样的：设计=>建造=>销售=>发货。相比之下，ML驱动的工作流程将看起来像：设计=>销售=>建造=>发货。

The “sell” and “build” steps will swap places, as retailers sell a product first — complete with glossy product photos of the item being used and lavishly displayed — and then build it and ship it once the orders start coming in.  

销售 "和 "建造 "的步骤将互换位置，因为零售商首先销售产品--配有使用和豪华展示的光鲜产品照片--然后建造它，一旦订单开始进入，就发货。

Of course, this “sell first, build later” thing has been going on for a long time in one form or another. But it will become the norm in more retail verticals as it gets easier for both retailers and their customers to do the design step with ML.  

当然，这种 "先销售，后建设 "的事情已经以这种或那种形式持续了很长时间。但是，随着零售商和他们的客户越来越容易通过ML完成设计步骤，它将成为更多零售垂直行业的规范。

Imagine an interactive retail flow that goes as follows:  

想象一下，一个互动的零售流程是这样的。

1.  Alice clicks on a Facebook ad for Super Rad Hoodies.  
    
    爱丽丝点击了Facebook上的 "Super Rad Hoodies "广告。
    
2.  She finds a hoodie with a style she likes, but she doesn’t like any of the colors or prints.  
    
    她发现一件有她喜欢的款式的连帽衫，但她不喜欢任何颜色或印花。
    
3.  She customizes the hoodie by typing in a prompt, e.g., “Cartoon sunflower pattern.”  
    
    她通过输入提示信息来定制连帽衫，例如，"卡通向日葵图案"。
    
4.  She selects the rendered version of the hoodie that most closely matches what she wants, and then with one clicks gets a gallery of the site’s model wearing the hoodie she just designed.  
    
    她选择与她想要的东西最接近的连帽衫的渲染版本，然后只需点击一下，就能得到网站模特穿着她刚刚设计的连帽衫的图片。
    
5.  She uploads about ten pictures of herself from different angles and views a generated gallery of herself in different poses, lighting conditions, and environments wearing the hoodie.  
    
    她从不同角度上传了大约10张自己的照片，并查看了生成的自己在不同姿势、照明条件和环境下穿着连帽衫的照片库。
    
6.  She adds the hoodie to the cart and checks out.  
    
    她把连帽衫加入购物车并结账。
    
7.  Alice’s hoodie design is sent to a garment factory to be manufactured. (The design file includes the prompt and seed Alice used so that the factory can use a model to generate a higher-resolution version of the cartoon sunflower texture.)  
    
    Alice的连帽衫设计被送到一家服装厂进行生产。(设计文件包括Alice使用的提示和种子，这样工厂就可以使用一个模型来生成更高分辨率的卡通向日葵纹理)。
    
8.  She gets the hoodie in the mail.  
    
    她收到了邮寄的连帽衫。
    

All of the hard problems in the flow above have been solved, and all that remains is for someone to build it. (If I don’t finish this article quickly enough, something like the above will be live before this newsletter hits your inbox.)  

上述流程中的所有困难问题都已解决，剩下的就是有人来建造它。(如果我不尽快写完这篇文章，在这篇简讯到达你的收件箱之前，类似上述的东西就会上线）。

We’ll also do this for entire homes, where you work with a set of ML-powered tools to design your home, and then the parts are 3D printed and it’s assembled for you.  

我们也会为整个住宅做这件事，你用一套ML-powered工具来设计你的住宅，然后零件被3D打印出来，为你组装。

This article has been kind of a grab-bag of trends, predictions, and suggestions, and I could’ve easily kept going but at some point, one has to start breaking things up into separate pieces.  

这篇文章有点像对趋势、预测和建议的抓取，我本可以轻松地继续下去，但在某些时候，人们必须开始把事情分成不同的部分。

There are so many things in this piece that I want to go deeper into, and even more things I haven’t touched on here but will cover in future installments. So here’s a quick look at what’s next for my “What’s Next” articles:  

这篇文章中有很多东西我想深入了解，甚至有更多的东西我在这里没有触及，但会在未来的文章中涉及。因此，这里是我的 "下一步 "文章的一个快速浏览。

-   The growing [text-to-3D-model scene](https://dreamfusion3d.github.io/) is blowing my mind and is going to power a revolution in VR and gaming realism.  
    
    不断增长的文字转3D模型场景让我大吃一惊，并将推动VR和游戏现实主义的革命。
    
-   When it comes to code generation, I have many questions about how the models are currently being trained, and a ton of ideas for where in the social coding process we might use them (code review, TDD, transforming unidiomatic code into idiomatic code, etc.).  
    
    谈到代码生成，我有很多关于目前如何训练模型的问题，以及一大堆关于在社会编码过程中我们可能使用它们的想法（代码审查、TDD、将非习惯性代码转化为习惯性代码，等等）。
    
-   I’ve written previously about how [machine learning is a form of compression](https://www.jonstokes.com/p/googles-colosseum), but I’ve yet to explore the technical and economic implications of a sudden, massive change in the “compute vs. storage” tradeoff dynamic across the entire computing ecosystem.   
    
    我以前写过关于机器学习是一种压缩形式的文章，但我还没有探讨整个计算生态系统的 "计算与存储 "权衡动态突然发生巨大变化的技术和经济影响。
    
-   Following on the compression point, generative models will have a massive impact on the capabilities of blockchains where block space is at a premium.   
    
    在压缩点之后，生成模型将对区块空间很重要的区块链的能力产生巨大的影响。
    

I’ll be covering all of the above and a lot more in future posts, and I’ll also be doing interviews with content creators and those working in the field of ML. So if you haven’t subscribed, do it now so you don’t miss out.  

我将在未来的文章中涵盖上述所有内容和更多内容，我还将对内容创作者和在ML领域工作的人进行采访。所以，如果你还没有订阅，现在就订阅吧，这样你就不会错过了。
