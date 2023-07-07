---
title: "如何写科学论文?"
date: 2023-07-05T17:51:57+08:00
updated: 2023-07-05T17:51:57+08:00
taxonomies:
  tags: []
extra:
  source: https://bastian.rieck.me/blog/posts/2023/writing/
  hostname: bastian.rieck.me
  author: 
  original_title: "How to Write a Scientific Paper"
  original_lang: zh
---

When I started my Ph.D., I found writing papers to be a somewhat daunting task. With this guide, I want to offer a brief perspective on the most relevant aspects of writing.  

当我开始攻读博士学位时，我发现写论文是一项有点令人畏惧的任务。通过本指南，我想对写作最相关的方面提供一个简短的看法。

## Structure 结构

The standard—one could almost say ‘canonical’—structure of a paper looks like this:  

论文的标准结构（几乎可以说是“规范的”）如下所示：

1.  Abstract 抽象的
2.  Introduction 介绍
3.  Background 背景
4.  Related Work 相关工作
5.  Methods 方法
6.  Experiments 实验
7.  Discussion 讨论

Let us look at all of these!  

让我们看看所有这些！

**Caveat lector**: most of what is about to follow should be treated as a guideline, laced with my personal preferences. Develop your own style and always feel free to deviate.  

警告讲师：接下来的大部分内容应该被视为指导方针，并结合我的个人喜好。发展自己的风格，并且随时可以偏离。  

Remember: writing should also be fun!  

请记住：写作也应该是有趣的！

## 1\. Abstract 1\. 摘要

The abstract provides a short, succinct, pithy summary of your work. While the length of abstracts can vary, I find 4–6 sentences to be a good length to aim for.  

摘要对您的工作进行了简短、简洁、精辟的总结。虽然摘要的长度可能有所不同，但我发现 4-6 个句子是比较合适的长度。  

This is short enough to read quickly while long enough to provide some details about your work.  

这篇文章足够短，可以快速阅读，同时又足够长，可以提供有关您工作的一些详细信息。

The _purpose_ of the abstract is to state what you are doing (or trying to do) and why this is relevant. When possible, add both qualitative and quantitative information about the solution (i.e.  

摘要的目的是说明你正在做什么（或试图做什么）以及为什么这是相关的。如果可能，添加有关解决方案的定性和定量信息（即  

mention what method(s) you used, potentially outlining some of the gains and observations).  

提及您使用的方法，可能概述一些收获和观察结果）。

An abstract is _great_ if it helps someone without prior exposure to your paper to at least briefly understand what is going on there and, moreover, makes that person want to read your paper.  

如果摘要能够帮助那些之前没有接触过你的论文的人至少简要地了解其中发生的事情，并且让那个人想要阅读你的论文，那么它就是很棒的。  

Think of it as a [TL;DR](https://en.wikipedia.org/wiki/TL;DR) for your work.  

将其视为您工作的 TL;DR。

## 2\. Introduction 2\. 简介

The introduction sets the stage for all the players in your paper: it introduces the methods, and provides the backdrop for the problem you set out to solve. Take some time to _motivate_ why this is a problem worth solving. Mention _how_ you solve it, i.e. what _contributions_ you make in the paper, and how you _know_ that it is a good solution (mentioning some overall improvements in experiments, for instance).  

引言为论文中的所有参与者奠定了基础：它介绍了方法，并为您要解决的问题提供了背景。花一些时间来激发为什么这是一个值得解决的问题。提及你是如何解决这个问题的，即你在论文中做出了哪些贡献，以及你如何知道这是一个很好的解决方案（例如，提及实验中的一些整体改进）。

Many ML papers use some kind of ‘Contributions’ list; my _personal preference_ is to use a `\paragraph` for this and expand on the individual items via an `inparaenum`, i.e. an enumeration that is set within a paragraph of text.<sup id="fnref:1"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:1" role="doc-noteref">1</a></sup>  

许多机器学习论文都使用某种“贡献”列表；我个人的偏好是为此使用 `\paragraph` 并通过 `inparaenum` 扩展各个项目，即在文本段落中设置的枚举。 <sup id="fnref:1"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:1" role="doc-noteref">1</a></sup>

In terms of length, I prefer to have the abstract and introduction together take up about 1 page of a single-column paper format or about 1 column of a double-column paper format.  

就长度而言，我更喜欢让摘要和引言一起占据单栏论文格式的约 1 页或双栏论文格式的约 1 栏。  

If you have more concepts or results to explain, aim for a longer introduction.  

如果您有更多概念或结果需要解释，请尝试更长的介绍。

A very nice trend is to have an ‘Overview’ or ‘Hero’ figure, i.e. some explanatory diagram or pipeline of what is going on in your paper on either the first or the second page.  

一个非常好的趋势是在第一页或第二页上有一个“概述”或“英雄”图，即一些解释性图表或流程，说明论文中正在发生的事情。  

This can make it much easier for readers to understand what you are doing in your paper.  

这可以使读者更容易理解您在论文中所做的事情。

## 3\. Background 三、背景

This section is all about laying down some notation as well as an explanation of most of the concepts.  

本节主要介绍一些符号以及对大多数概念的解释。  

Ideally, even if I am not an expert in the precise subject matter of your paper, I should at least get a rough idea of what you are doing later on, what your methods are relying on, and—potentially—what your theorems might be.  

理想情况下，即使我不是您论文具体主题的专家，我至少应该粗略地了解您稍后在做什么，您的方法依赖什么，以及您的定理可能是什么。  

Think of this section as the _foundation_ upon which your method is built.  

将此部分视为构建您的方法的基础。

There is no ideal length here, but I would aim for something that is at least _shorter_ than your ‘Methods’ section.  

这里没有理想的长度，但我的目标是至少比“方法”部分短。

This section is all about discussing the work of _others_, and—crucially–_contextualising_ it. It is not enough to just list as many papers as you can here, but you should also provide some details as to their relevance or their limitations.  

本节主要讨论其他人的工作，并且最重要的是将其置于背景中。在这里列出尽可能多的论文是不够的，你还应该提供一些关于它们的相关性或局限性的详细信息。  

Unfortunately, this section is often written _last_, and it shows. Avoid phrasal templates of the form ‘Smith et al. do _X_. Miller et al. do _Y_’. Rather tell your readers _why_ existing work is great but that does not solve your specific problem.  

不幸的是，这一部分通常是最后写的，这一点也表明了这一点。避免使用“Smith et al.”形式的短语模板。 X.米勒等人。做Y’。而是告诉你的读者为什么现有的工作很棒，但这并不能解决你的具体问题。  

A great ‘Related Work’ section helps readers a lot, in particular if they want to understand your specific research domain somewhat better.  

出色的“相关工作”部分对读者有很大帮助，特别是如果他们想更好地了解您的特定研究领域。

The ‘Related Work’ section is often positioned before describing your own method, even though that creates some logical inconsistencies.  

“相关工作”部分通常位于描述您自己的方法之前，尽管这会造成一些逻辑上的不一致。  

Try to follow the conventions of your field here.  

尝试遵循您所在领域的惯例。

As for length, aim for a full column in a double-column format, or for about three quarters of a page in a single-column format. That should be plenty.  

至于长度，目标是双栏格式的整栏，或单栏格式的大约四分之三页面。那应该足够了。  

Some papers manage to integrate this section into other sections; if you can pull it off—in particular if you are working in a new area—this can be very refreshing and make your paper stand out. Of course, you need to make sure that you give credit to those that came before you.  

有些论文设法将此部分整合到其他部分；如果你能成功——特别是如果你在一个新领域工作——这会让人耳目一新，让你的论文脱颖而出。当然，你需要确保你对那些在你之前的人给予了信任。

## 5\. Methods 5\. 方法

This is where you can have the most fun, and it is typically the section that is easiest to write.  

这是您可以获得最大乐趣的地方，并且通常是最容易编写的部分。  

If you are not experienced in writing papers, this is the perfect section to start with! Describe your model, your algorithms, your theoretical insights.  

如果您没有撰写论文的经验，那么这是一个完美的开始部分！描述你的模型、你的算法、你的理论见解。  

All jargon and technical terms that you use should be defined in the ‘Background’ section.  

您使用的所有行话和技术术语都应在“背景”部分中定义。  

If appropriate, you can conclude this section by a discussion of limitations of your method—it is clear that _any_ method has limitations, so do not be shy in pointing them out.  

如果合适的话，您可以通过讨论您的方法的局限性来结束本节——显然任何方法都有局限性，所以不要羞于指出它们。

Ideally, a skilled graduate student in your field should be able to build their own version of your method by just reading the ‘Methods’ section.  

理想情况下，您所在领域的熟练研究生应该能够通过阅读“方法”部分来构建自己的方法版本。  

Hence, make sure to describe any specific modifications that you did to standard methods (notice that specific pre-processing steps that pertain to your data should best be mentioned in another section, viz.  

因此，请确保描述您对标准方法所做的任何特定修改（请注意，最好在另一节中提及与您的数据相关的特定预处理步骤，即：  

the ‘Experiments’ section).  

“实验”部分）。

The ‘Methods’ section will be perused by expert readers and reviewers, so make sure that the descriptions are accessible, precise, and consistent.  

“方法”部分将由专家读者和审稿人仔细阅读，因此请确保描述易于理解、精确且一致。  

Get your colleagues involved, in particular those with more experience, to get an idea of whether the description in the section is sufficient to facilitate reproducibility.  

让您的同事参与进来，特别是那些经验丰富的同事，以了解本节中的描述是否足以促进可重复性。

The length of the ‘Methods’ section depends a lot on the type of paper that you are writing.  

“方法”部分的长度很大程度上取决于您所写论文的类型。  

With a mix of theory and experiments, you might have to use up to four full pages of content to describe algorithms and their properties.  

通过理论和实验的结合，您可能需要使用多达四页的内容来描述算法及其属性。  

In more applied papers, the ‘Methods’ section is typically shorter.  

在更多的应用论文中，“方法”部分通常较短。

## 6\. Experiments 6\. 实验

The bread and butter of machine learning research and many other disciplines, the ‘Experiments’ section is where you can describe what types of phenomena you can study with your new method, and what insights you obtained.  

“实验”部分是机器学习研究和许多其他学科的基础，您可以在其中描述可以使用新方法研究哪些类型的现象以及获得哪些见解。  

Typically, this section should have a subsection or paragraph in which you detail the experimental setup.  

通常，本节应该有一个小节或段落来详细说明实验设置。  

The setup includes any pre-processing steps and data sets you picked, as well as your choice of hyperparameters, data splits, and so on.  

该设置包括您选择的任何预处理步骤和数据集，以及您选择的超参数、数据分割等。

Afterwards, you should describe the individual experiments _in detail_. In machine learning papers, this commonly requires some tables or performance curves. Make sure to have the following aspects covered:  

之后，您应该详细描述各个实验。在机器学习论文中，这通常需要一些表格或性能曲线。确保涵盖以下几个方面：

-   A comparison with other methods (typically, if something is mentioned in the ‘Related Work’ section, you should compare to it).  
    
    与其他方法的比较（通常，如果“相关工作”部分中提到了某些内容，您应该与之进行比较）。
-   A description in terms of statistical measures of dispersion, such as standard deviations for performance plots or confidence intervals.  
    
    离散度统计度量的描述，例如性能图或置信区间的标准差。  
    
    In particular when comparing a large set of methods, you should all your inference tasks multiple times to ensure that you get an understanding of the performance.  
    
    特别是在比较大量方法时，您应该多次执行所有推理任务，以确保了解性能。
-   A set of _ablation studies_ where you analyse the performance of individual parts of your model.  
    
    一组消融研究，您可以在其中分析模型各个部分的性能。  
    
    The idea is to verify that each part of your method actually contributes something relevant to the overall performance; you do not want to find out later on that, say, a [_random projection_](https://en.wikipedia.org/wiki/Random_projection) would have worked just as well than your highly-trained neural network.  
    
    这个想法是验证方法的每个部分实际上都对整体性能做出了贡献；你不想稍后发现，比如说，随机投影会比你训练有素的神经网络同样有效。

The experiments can be followed by individual discussions of the ramifications, or you can collect them in a single ‘Discussion’ section at the end (see below).  

实验之后可以对后果进行单独讨论，或者您可以将它们收集在最后的单个“讨论”部分中（见下文）。  

If you have not already analysed the limitations of your method in the ‘Methods’ section, do it as a part of this section here.  

如果您尚未在“方法”部分中分析您的方法的局限性，请在此处将其作为本节的一部分进行分析。

Again, the length of the ‘Experiments’ section depends very much on the type of paper you are writing. I would suggest to have one full page as an _absolute minimum_ for most machine learning papers, with some papers having sections that rival the ‘Methods’ section in length.  

同样，“实验”部分的长度很大程度上取决于您所写论文的类型。我建议大多数机器学习论文至少有一整页，有些论文的章节长度可以与“方法”部分相媲美。  

This is probably one of these areas where the conference culture deviates the most from journals, since in journal papers—especially in the biomedical domain—most of the space is taken up by experiments and discussions, and methods are typically confined to supplementary materials.  

这可能是会议文化与期刊差异最大的领域之一，因为在期刊论文中，尤其是在生物医学领域，大部分空间都被实验和讨论占据，而方法通常仅限于补充材料。

## 7\. Discussion 7\. 讨论

Much like a great rug, the ‘Discussion’ section ties your paper together. Summarise and conclude why the problem you solved is relevant, why your method is useful, and so on.  

就像一块很棒的地毯一样，“讨论”部分将您的论文联系在一起。总结并总结为什么你解决的问题是相关的，为什么你的方法有用，等等。  

Try to give a succinct summary and contextualisation of the observations you made before.  

尝试对您之前所做的观察进行简洁的总结和情境化。  

It is also custom practice to discuss future work, so make sure to think about how your method could be extended.  

讨论未来的工作也是一种习惯做法，因此请务必考虑如何扩展您的方法。  

This is your opportunity to provide some new ideas for readers—use it!  

这是您为读者提供一些新想法的机会——利用它！

This section is typically half a page or approximately a full column, but much shorter and pithy ‘Discussion’ sections are often seen in the wild.  

这一部分通常是半页或大约一整栏，但更短、更简洁的“讨论”部分经常在野外看到。

## General Advice and Anti-Patterns to Avoid  

一般建议和要避免的反模式

Having been writing and reviewing papers for some time, I like to believe that I have picked up on some _anti-patterns_ or common mistakes. Again, these are geared towards a conference paper, but I will try to keep them as general as possible.  

撰写和审阅论文已经有一段时间了，我愿意相信我已经发现了一些反模式或常见错误。同样，这些内容是针对会议论文的，但我会尽力使它们尽可能笼统。

-   If you do not know where to start writing, draft the ‘Methods’ section first, and keep the ‘Introduction’ and ‘Conclusion’ until the very last moment.  
    
    如果你不知道从哪里开始写，请先起草“方法”部分，并将“引言”和“结论”保留到最后一刻。  
    
    Often, it is easier to describe the what and how, rather than the overall _why_.  
    
    通常，描述内容和方式比描述总体原因更容易。
-   Do not make the introduction just ‘rehash’ what you wrote in the abstract.  
    
    不要让引言只是“重复”你在摘要中所写的内容。
-   The introduction should avoid too much jargon or, if jargon needs to be used, provide a brief definition. Ideally, _every_ reader should get a good idea of what you are about to accomplish in the paper.  
    
    引言应避免太多行话，或者如果需要使用行话，请提供简短的定义。理想情况下，每个读者都应该很好地了解您将在论文中实现的目标。
-   Make sure to credit previous contributions correctly. We are all standing on the shoulders of giants, and it is part of our scientific commitment to honesty to _always_ acknowledge those who came before us.  
    
    确保正确记入以前的贡献。我们都站在巨人的肩膀上，始终承认那些走在我们前面的人是我们对诚实的科学承诺的一部分。
-   Do **not** overemphasise your contributions. Or, to put it more poetically, do not let your ego write cheques that your brain cannot cash.  
    
    不要过分强调你的贡献。或者，更诗意地说，不要让你的自我开出你的大脑无法兑现的支票。  
    
    We are all proud of our methods and achievements—and rightly so—but we should also operate with a large degree of humility. A particular bad anti-pattern that I am seeing is what I like to call the ’neglected baseline:’ essentially, you train your baseline methods _once_, namely at the start of the project, then you _never_ touch them again. By contrast, your own method is trained and re-trained all the time.  
    
    我们都为我们的方法和成就感到自豪——这是理所当然的——但我们也应该以高度谦逊的态度行事。我看到的一个特别糟糕的反模式是我喜欢称之为“被忽视的基线”：本质上，你训练你的基线方法一次，即在项目开始时，然后你就再也不会碰它们了。相比之下，你自己的方法一直在训练和重新训练。  
    
    Naturally, this will result in a large competitive advantage of your method, so make sure to train your baselines in the strongest fashion possible whenever you can!  
    
    当然，这将为您的方法带来巨大的竞争优势，因此请确保尽可能以最强的方式训练您的基线！
-   Make sure to have every section include at least something ‘intuitive’ to say to readers that might be lost in the details of your method.  
    
    确保每个部分至少包含一些“直观”的内容，以便读者可能会迷失在方法的细节中。  
    
    In particular when your paper is heavy on theory, it can be helpful to take a step back every once in a while and tell a reader why a certain result is important or what its ramifications are.  
    
    特别是当你的论文侧重于理论时，每隔一段时间后退一步并告诉读者为什么某个结果很重要或其后果是什么，会很有帮助。
-   Iterate, iterate, iterate. Nature abhors a vacuum, and human beings abhor an empty page. Just write _something_ in each section and improve it later on. A good method can also be to describe every section with a set of paragraphs, which you then subsequently extend and improve.  
    
    迭代，迭代，迭代。大自然厌恶真空，人类厌恶空白的页面。只需在每个部分写一些内容，然后再改进即可。一个好的方法还可以是用一组段落来描述每个部分，然后您可以对其进行扩展和改进。
-   Be consistent with the tenses you use, and aim for preferring the present tense when referring to the work at hand.  
    
    与您使用的时态保持一致，并在提及手头的工作时尽量使用现在时。
-   Omit needless words (but maybe not all of them, since the pacing of a text still matters). At the very least, avoid ‘weasel words’ such as ‘quite’ or ‘very’.<sup id="fnref:2"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:2" role="doc-noteref">2</a></sup>  
    
    省略不必要的单词（但也许不是全部，因为文本的节奏仍然很重要）。至少，避免使用“狡猾的词”，例如“相当”或“非常”。 <sup id="fnref:2"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:2" role="doc-noteref">2</a></sup>
-   Invest in the writing _early on_. We do not have to write literary masterpieces, even though, as evidenced by books like [The Oxford Book of Modern Science Writing](https://en.wikipedia.org/wiki/The_Oxford_Book_of_Modern_Science_Writing), papers do not have to be dry and boring.  
    
    尽早投资于写作。我们不必写文学杰作，尽管正如《牛津现代科学写作手册》等书籍所证明的那样，论文不必枯燥乏味。  
    
    However, it is my observation that our community tends to be a little bit lax when it comes to the writing part; this is problematic because a well-written paper will make it so much easier for your readers to understand and _use_ your method.  
    
    然而，据我观察，我们的社区在写作方面往往有点松懈；这是有问题的，因为一篇写得好的论文会让你的读者更容易理解和使用你的方法。
-   Be bold and _compress_ your paper. In line with omitting needless words, you may also find that you can reformulate and simplify certain sections.  
    
    大胆地压缩你的纸张。为了省略不必要的单词，您可能还会发现可以重新表述和简化某些部分。
-   Check your bibliography carefully. Always search for the right version of a paper. Google Scholar has a tendency to give you weirdly-formatted citations of arXiv paper.  
    
    仔细检查你的参考书目。始终寻找论文的正确版本。 Google Scholar 倾向于为您提供格式怪异的 arXiv 论文引文。  
    
    Do make an effort and find out whether a paper was actually published at a conference or in a journal and cite it appropriately.<sup id="fnref:3"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:3" role="doc-noteref">3</a></sup>  
    
    请努力查明一篇论文是否确实在会议或期刊上发表，并适当地引用它。 <sup id="fnref:3"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:3" role="doc-noteref">3</a></sup>

## Pet Peeves 讨厌的事

Here are some of my personal pet peeves.  

以下是我个人的一些烦恼。  

I cannot claim in good conscience that there a good reasons for any of them, but if we are co-authoring a paper, you can make me very happy by checking out this list.  

我不能凭良心声称其中任何一个都有充分的理由，但如果我们共同撰写一篇论文，你可以通过查看此列表让我感到非常高兴。

-   Prefer the active voice over the passive voice at all times.  
    
    任何时候都更喜欢主动语态而不是被动语态。
-   ‘On the other hand’ needs to be proceeded by ‘On the one hand.’ Consider using ‘By contrast’ instead.  
    
    “另一方面”需要由“一方面”继续。考虑使用“相比之下”。
-   Use simple words. Why write ‘utilise’ when ‘use’ would do?  
    
    使用简单的词语。既然“use”就可以了，为什么要写“utilise”呢？
-   [Methodology often does not mean what you think it means](http://bastian.rieck.me/blog/posts/2020/methodology/). Admittedly, language is changing and all that jazz, but I cannot shake the feeling that people are using this to make their method sound smarter.  
    
    方法论通常并不意味着你所认为的那样。诚然，语言正在发生变化，但我无法动摇人们正在利用它来使他们的方法听起来更聪明的感觉。  
    
    ‘No, sir, this paper does not contains methods. It contains methodologies!’  
    
    “不，先生，这篇论文不包含方法。它包含方法论！’
-   In general, it can pay off to write with a thesaurus or a dictionary if you are not a native speaker.  
    
    一般来说，如果您的母语不是英语，那么使用同义词库或词典进行写作是有好处的。  
    
    Make sure that you use the right words, and resist the ‘false friends’ of your native language.  
    
    确保使用正确的词语，并抵制母语的“假朋友”。
-   Please, please, please learn how to properly add citations. If you are using `natbib`, you can use `\citep` for parenthetical citations, and `\citet` for in-text citations. For `biblatex`, the commands are `\parentcite` and `\textcite`, respectively. Do _not_ use bracketed citations as nouns unless mandated by an editor. For instance, ‘This method is great for graphs \[1\].’ is acceptable, while ‘See \[1\] for more details’ is **not**. Why should you care?  
    
    请，请，请学习如何正确添加引用。如果您使用 `natbib` ，则可以使用 `\citep` 进行括号引用，使用 `\citet` 进行文本内引用。对于 `biblatex` ，命令分别是 `\parentcite` 和 `\textcite` 。除非编辑强制要求，否则请勿将括号内的引文用作名词。例如，“此方法非常适合图形 \[1\]。”是可以接受的，而“请参阅 \[1\] 了解更多详细信息”则不可接受。你为什么要关心？  
    
    I believe that the semantic intent of a citation matters; moreover, if you follow this rule, you can easily swap citation styles for different journals and never have to worry about your citations looking weird!  
    
    我相信引文的语义意图很重要；此外，如果您遵循此规则，您可以轻松地交换不同期刊的引文样式，而不必担心您的引文看起来很奇怪！
-   Always use the right type of quotes. It is easiest to just use the `csquotes` package and use the `\enquote` command. If you are quoting manually, use \`\`word'' or \`word' to ensure that the quotes are typeset correctly.<sup id="fnref:4"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:4" role="doc-noteref">4</a></sup>  
    
    始终使用正确的引号类型。最简单的方法是使用 `csquotes` 包并使用 `\enquote` 命令。如果您手动引用，请使用“word”或“word”以确保引号排版正确。 <sup id="fnref:4"><a href="https://bastian.rieck.me/blog/posts/2023/writing/#fn:4" role="doc-noteref">4</a></sup>

## Final Words of Advice  

最后的建议

All of this might seem daunting. Always ignore everything that makes no sense to you at a specific stage and focus on _having fun_. I really mean it—writing up your project should be a joyous experience!  

所有这一切似乎令人望而生畏。始终忽略特定阶段对你来说毫无意义的一切，专注于享受乐趣。我是认真的——写你的项目应该是一次愉快的经历！  

It is so rewarding to be able to share your view with a greater community. Keep on writing until you have found your own voice and your own style, and best of luck!  

能够与更大的社区分享您的观点是非常有意义的。继续写作，直到找到自己的声音和风格，祝你好运！
