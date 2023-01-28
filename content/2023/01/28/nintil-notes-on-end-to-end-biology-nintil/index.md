---
title: "端到端生物学笔记"
date: 2023-01-28T12:29:12+08:00
updated: 2023-01-28T12:29:12+08:00
taxonomies:
  tags: []
extra:
  source: https://nintil.com/biology-llms/
  hostname: nintil.com
  author: Jose Luis Ricon
  original_title: "Nintil - Notes on end-to-end biology --- Nintil"
  original_lang: en
---

Initially I wanted to write a longer piece on the broad topic of "Bio and ML" but it started to grow too many threads, getting into predicting [ADME](https://en.wikipedia.org/wiki/ADME), reproducibility and translatability of animal research, and how optimistic should we be about organoids. Each of these could be its own post. Instead I'll make some high level points and point to a number of recent writings that collectively express what I wanted to say.  
最初我想写一篇关于“生物和 ML”这个广泛主题的长篇文章，但它开始增长了太多线索，开始涉及预测 ADME 、动物研究的可重复性和可翻译性，以及我们应该对类器官有多乐观。这些中的每一个都可以是它自己的帖子。相反，我将提出一些高层次的观点，并指出一些最近的著作，这些著作共同表达了我想说的话。

## We are far from understanding all of biology, but that's okay  
我们远未了解所有生物学，但这没关系

Biology is hard to understand. _Human_ biology is even harder because of ethical considerations around experimentation with human subjects. This makes drug development a really hard problem!  
生物学很难理解。由于围绕人类受试者进行实验的伦理考虑，人类生物学更加困难。这使得药物开发成为一个非常困难的问题！

Usually, the way we solve problems is first understanding the domain where the problem is and then thinking of a solution that makes use of that understanding. In drug development, it's understanding the function of genes, proteins, small molecules, and their interactions.  
通常，我们解决问题的方法是首先了解问题所在的领域，然后考虑利用这种理解的解决方案。在药物开发中，它了解基因、蛋白质、小分子的功能及其相互作用。  
Drug development tends to start with the assumption that some biological entity (the target, usually a protein) is involved in a disease, then trying to find ways to modulate that protein that are safe and that can be packaged in a pill.  
药物开发往往始于假设某些生物实体（目标，通常是蛋白质）与疾病有关，然后试图找到调节该蛋白质的方法，使其安全且可以包装在药丸中。  
But it doesn't have to be like that; one could in principle take cells (or ideally a whole organism that's diseased), compare them to healthy cells, try a million perturbations, then pick what works best. Not a new idea, this is what is known as phenotypic screening.  
但这不一定是那样；原则上可以取细胞（或理想情况下是患病的整个生物体），将它们与健康细胞进行比较，尝试一百万次扰动，然后选择最有效的。这不是一个新想法，这就是所谓的表型筛选。  
It may be harder to do but the result is cleaner: rather than asking "will molecule X bind to protein Y" one asks "will this perturbation make the cell healthier" which is closer to what we want (making an organism healthier). A recent commentary from [Scannell](https://www.nature.com/articles/s41573-022-00552-x) et al. (2022) is of the same opinion: better initial screening buys you a lot:  
这可能更难做，但结果更清晰：与其问“分子 X 是否会与蛋白质 Y 结合”，不如问“这种扰动是否会使细胞更健康”，这更接近我们想要的（使有机体更健康）。 Scannell 等人最近的评论。 (2022) 持相同观点：更好的初步筛选会给你带来很多好处：

> In parallel, we suspect that much of the pharmaceutical industry sometimes made the wrong technological trade-offs because it had not understood the quantitative power of predictive validity.  
> 同时，我们怀疑许多制药行业有时会做出错误的技术权衡，因为它不了解预测有效性的量化能力。  
> It sometimes embraced discovery methods with measurably high throughput and low unit costs, whose benefits were offset by less measurable falls in predictive validity. A clear example is antibacterial R&D. **In vivo phenotypic screens of a few hundred compounds, circa 1930, were more productive than target-based screens of ~10^7 compounds** in the late 1990s and early 2000s.  
> 它有时采用具有可测量的高吞吐量和低单位成本的发现方法，其好处被预测有效性的不可测量下降所抵消。一个明显的例子是抗菌研发。大约在 1930 年，数百种化合物的体内表型筛选比 1990 年代末和 2000 年代初约 10^7 种化合物的基于目标的筛选更有效率。

Once one buys into this one can take it to the next level: Why not train an ML model that predicts efficacy? In theory the triplet (healthy state, diseased state, perturbation) in enough numbers is all one needs. In theory.  
一旦购买了这个，就可以将其提升到一个新的水平：为什么不训练一个预测功效的 ML 模型？理论上，足够数量的三元组（健康状态、疾病状态、扰动）是一个人所需要的。理论上。

Of course, anytime one talks about ML for bio one is reminded of the [opinion](https://www.reddit.com/r/biotech/comments/wu2qy2/for_those_in_the_sector_what_is_a_controversial/) of industry veterans that have seen ML in bio hype for years (decades?) without much being delivered. Whenever there's a new seemingly breakthrough paper there are many "but-s" that get raised (Has AI [discovered](https://www.science.org/content/blog-post/has-ai-discovered-drug-now-guess) a drug? De novo computational generation of [antibodies](https://mobile.twitter.com/SurgeBiswas/status/1613232556673224705)? Protein [folding](https://www.chemistryworld.com/opinion/why-alphafold-wont-revolutionise-drug-discovery/4016051.article)?).  
当然，无论何时谈论 ML for bio one 都会想起行业资深人士的观点，他们已经看到 ML 在生物炒作中多年（几十年？）但没有太多交付。每当有一篇看似具有突破性的新论文出现时，就会出现许多“但是”（AI 发现了一种药物吗？抗体的从头计算生成？蛋白质折叠？）。

> For reflection, here’s a quote about computer-aided drug discovery (CADD), highlighting its importance and impact:  
> 为了反思，这里有一段关于计算机辅助药物发现 (CADD) 的引述，强调了它的重要性和影响：
> 
> > “Drug companies know they simply cannot be without these computer techniques. They make drug design more rational. How?  
> > “制药公司知道他们离不开这些计算机技术。它们使药物设计更加合理。如何？  
> > By helping scientists learn what is necessary, on the molecular level, to cure the body, then enabling them to tailor-make a drug to do the job… This whole approach is helping us avoid the blind alleys before we even step into the lab… Pharmaceutical firms are familiar with those alleys.  
> > 通过帮助科学家在分子水平上了解治愈身体的必要条件，然后使他们能够定制药物来完成这项工作……整个方法帮助我们在进入实验室之前避免走入死胡同……制药公司对这些小巷很熟悉。  
> > Out of every 8,000 compounds the companies screen for medicinal use, only one reaches the market.  
> > 在公司筛选的每 8,000 种药用化合物中，只有一种进入市场。  
> > The computer should help lower those odds … This means that chemists will not be tied up for weeks, sometimes months, painstakingly assembling test drugs that a computer could show to have little chance of working.  
> > 计算机应该有助于降低这些可能性……这意味着化学家不会被束缚数周，有时甚至数月，煞费苦心地组装计算机可能显示几乎没有工作机会的测试药物。  
> > The potential saving to the pharmaceutical industry: millions of dollars and thousands of man-hours”  
> > 制药行业的潜在节省：数百万美元和数千工时”
> 
> What’s great about this quote is that you can hear its echo in current Silicon Valley tech-solves-biotech pitches, but **it was from a _Discover_ magazine article in August 1981** called “[Designing Drugs With Computers](http://www.marciabartusiak.com/uploads/8/5/8/9/8589314/designing_drugs.pdf)”. (Four Decades Of Hacking Biotech And Yet Biology Still Consumes Everything, [2017](https://lifescivc.com/2017/04/four-decades-hacking-biotech-yet-biology-still-consumes-everything/))  
> 这句话的妙处在于，您可以在当前的硅谷技术-解决-生物技术宣传中听到它的回声，但它来自 1981 年 8 月 Discover 杂志的一篇名为“用计算机设计药物”的文章。 （四个十年的黑客攻击生物技术，但生物学仍然消耗着一切，2017 年）

Companies that make "Designing drugs with AI" their selling point like Atomwise (2012), Recursion (2013), Schrödinger (1990), or Exscientia (2012) have been around for a while. At least one of them (Schrödinger) have delivered _some_ approved drugs, but the vast majority of drugs developed and approve are still not coming from "throw data at a model and get drugs at the other end".  
将“用 AI 设计药物”作为卖点的公司已经存在了一段时间，例如 Atomwise (2012)、Recursion (2013)、Schrödinger (1990) 或 Exscientia (2012)。他们中至少有一个（薛定谔）已经交付了一些已获批的药物，但绝大多数开发和批准的药物仍然不是来自“将数据扔给模型并在另一端获得药物”。  
Good thinking and exhaustive experimentation continues to be, to this day, what gets drugs approved, not fancy computational modeling and data alone.  
直到今天，良好的思考和详尽的实验仍然是药物获得批准的原因，而不仅仅是花哨的计算模型和数据。

At the same time, at every moment in the history of a field, there is a recurring question: Is this time different? Or is this time like the previous 1000 times?  
同时，在一个领域历史的每一个时刻，都有一个反复出现的问题：这一次是否不同？或者这次和之前的1000次一样？

> There's a critique of current work on AI expressed as variations on the argument: "Look, some such systems are impressive as demos. But the people creating the systems have little detailed understanding of how they work or why.  
> 对当前人工智能工作的批评表达为论点的变体：“看，一些这样的系统作为演示令人印象深刻。但创建系统的人对它们的工作原理或原因知之甚少。  
> And until we have such an understanding we're not really making progress on AI." This argument is then sometimes accompanied by (often rather dogmatic) assertions about what characteristics science "must" have.  
> 在我们有这样的理解之前，我们并没有真正在人工智能方面取得进展。”然后，这种争论有时伴随着（通常是相当教条的）关于科学“必须”具有哪些特征的断言。
> 
> I have some instinctive sympathy for such arguments. **My original field of physics is full of detailed and often rather satisfying explanations of how things work**. So too, of course, are many other fields. And historically new technologies often _begin_ with tinkering and intuitive folk models, but technological progress is then enabled by greatly improved explanations of the underlying phenomena.  
> 对于这样的论点，我有一些本能的同情。我最初的物理学领域充满了对事物如何运作的详细且通常令人满意的解释。当然，许多其他领域也是如此。从历史上看，新技术通常始于修补和直观的民间模型，但随后通过对潜在现象的极大改进解释来实现技术进步。  
> You can build a sundial with a pretty hazy understanding of the solar system; to build an atomic clock requires a deep understanding of many phenomena.  
> 您可以在对太阳系有相当模糊的了解的情况下构建一个日晷；建造原子钟需要对许多现象有深刻的理解。
> 
> **Work on AI appears to be trying to violate this historic model of improvement.** Yes, we're developing what seem to be better and better systems in the tinkering mode. But progress in understanding how those systems work seems to lag far behind. \[...\]  
> 人工智能方面的工作似乎试图打破这种历史性的改进模式。是的，我们正在开发修补模式下看起来越来越好的系统。但在理解这些系统如何工作方面的进展似乎远远落后。 \[...\]
> 
> **The underlying thing that's changed is the ease of trying and evaluating systems**. If you wanted to develop improved clocks in the past you had to laboriously build actual systems, and then rigorously test them. A single new design might take months or years to build and test.  
> 改变的根本是尝试和评估系统的便利性。如果你想在过去开发改进的时钟，你必须费力地构建实际系统，然后对其进行严格测试。一个新的设计可能需要数月或数年的时间来构建和测试。  
> Detailed scientific understanding was important because it helped you figure out which part of the (technological) design space to search in. When each instance of a new technology is expensive, you need detailed explanations which tell you where to search.  
> 详细的科学理解很重要，因为它可以帮助您弄清楚要搜索的（技术）设计空间的哪一部分。当新技术的每个实例都很昂贵时，您需要详细的解释来告诉您在哪里搜索。
> 
> By contrast, much progress in AI takes a much more agnostic approach to search.  
> 相比之下，人工智能的许多进步都采用了更加不可知的搜索方法。  
> Instead, of using detailed explanations to guide the search it uses a combination of: (a) general architectures; (b) trying trillions (or more) of possibilities, guided by simple ideas (like gradient descent) for improvement; and (c) the ability to _recognize_ progress. This is a radically different mode of experimentation, only made possible by the advent of machines which can do extremely rapid symbol manipulation. (The role of explanation in AI, Michael Nielsen's [notes](https://michaelnotebook.com/ongoing/sporadica.html#role_of_explanation_in_AI))  
> 相反，它没有使用详细的解释来指导搜索，而是结合使用了：(a) 一般架构； (b) 尝试数万亿（或更多）的可能性，以简单的想法（如梯度下降）为指导进行改进； (c) 识别进步的能力。这是一种完全不同的实验模式，只有能够进行极快符号处理的机器的出现才可能实现。 （解释在 AI 中的作用，Michael Nielsen 的笔记）

I'm not the [first](https://twitter.com/ch402/status/1533164918886703104) to notice some similarity between the research aesthetics of studying neural networks and studying biology. Chris Olah is optimistic about some deeper level of understanding of neural networks.  
我不是第一个注意到研究神经网络和研究生物学的研究美学之间存在某些相似之处的人。 Chris Olah 对神经网络有更深层次的理解持乐观态度。  
I don't know how optimistic to be about that, but I am certainly more optimistic about that that about the interpretability of biological systems; a point made beautifully in _Can a [biologist](https://www.cell.com/cancer-cell/pdf/S1535-6108(02)00133-2.pdf) fix a radio_ and _Could a [neuroscientist](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005268) understand a microprocessor?_. In artificial neural networks one has very simple entities (neurons that obey simple functions, or layers that perform easy to understand operations), we have a perfectly defined wiring diagram for the network, and we can run all the experiments we want on the neural net itself.  
我不知道对此有多乐观，但我肯定对生物系统的可解释性更乐观；在生物学家能修好收音机和神经科学家能理解微处理器吗？在人工神经网络中，实体非常简单（服从简单功能的神经元，或执行易于理解的操作的层），我们有一个完美定义的网络接线图，我们可以在神经网络上运行我们想要的所有实验本身。  
Contrast to biology where we have aggregates of squishy bags of molecules (cells) bouncing against each other, and each different from the rest (hyaluronic acid is very different from collagen whereas all neurons in an ANN are basically the same), where the way they interact is not given and has to be studied, often indirectly as we can't easily inspect the state of as cell as we could in an artificial neural network.  
与生物学相比，在生物学中，我们有许多柔软的分子（细胞）袋聚集在一起，它们相互弹跳，并且每个都与其他分子不同（透明质酸与胶原蛋白非常不同，而 ANN 中的所有神经元基本相同），它们的方式interact 没有给出并且必须进行研究，通常是间接的，因为我们不能像在人工神经网络中那样轻松地检查细胞的状态。

And of course to make it even worse, the components of biological systems (cells) behave differently in isolation (in a petri dish) than the way they do when they exist in the context of an organ.  
当然，更糟糕的是，生物系统的组成部分（细胞）在孤立状态下（在培养皿中）的行为与它们存在于器官环境中时的行为方式不同。

So yes, I continue to be not super optimistic about understanding biology! I have written here and there about what does it mean to [understand](https://nintil.com/framework-biology/) something in [biology](https://nintil.com/darwin-level-insights/) and asked [this](https://twitter.com/ArtirKel/status/1458188399328694274) same question to my Twitter followers in 2021. Even [before](https://berthub.eu/articles/posts/biologists-physics-envy/) that, [Bert Hubert](https://berthub.eu/) already was writing in 2019 that maybe it is the case that biology will never be understood, and then our only hope would be to _Gather everything we learn into first-class quality databases that might enable computers to make sense of what we have learned._  
所以是的，我对理解生物学仍然不是超级乐观！我在这里和那里写过关于理解生物学中的某些东西意味着什么的文章，并在 2021 年向我的 Twitter 关注者提出了同样的问题。甚至在此之前，Bert Hubert 已经在 2019 年写道，也许生物学永远不会成为现实理解，那么我们唯一的希望就是将我们学到的一切都收集到一流质量的数据库中，这可能使计算机能够理解我们所学的知识。

We can debate what "understanding" means endlessly but I find more practical to discuss what experiment to do next or what kind of data to gather, and this is driven by what one thinks the road to solving the problems we care about look like.  
我们可以无休止地争论“理解”是什么意思，但我发现讨论下一步要做什么实验或收集什么样的数据更实际，这取决于人们认为解决我们关心的问题的道路是什么样子。  
From the point of view of the task "predicting protein structure from its sequence", one could do experiments where we isolate tiny bits of proteins and study how those fold, and attempt to derive rules to predict this, perhaps understanding some aspects of the process.  
从“从序列预测蛋白质结构”任务的角度来看，我们可以做实验，我们分离出微小的蛋白质并研究它们是如何折叠的，并试图推导出预测这一点的规则，或许可以理解这个过程的某些方面.  
This does work to some extent, we have learned that proteins do have smaller subcomponents ([motifs](https://en.wikipedia.org/wiki/Structural_motif), or [domains](https://en.wikipedia.org/wiki/Protein_domain)). We have also learned that there are different kinds of proteins (globular, disorganized, or fibrous), and one can make reasonable guesses about the electric charge [distribution](https://en.wikipedia.org/wiki/Chemical_polarity#Nonpolar_molecules) in a globular protein (apolar amino acids will be found near the center of the protein). But the road to solving protein folding did not involve eventually discovering some sort of [Navier Stokes](https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_equations) equations which can be derived from first principles and govern the behavior of the system reasonably well; no, what happened was that a lot of data and massive compute were thrown at the problem and, with some caveats, solved it.  
这在某种程度上确实有效，我们了解到蛋白质确实具有较小的子成分（基序或结构域）。我们还了解到存在不同种类的蛋白质（球状、杂乱无章或纤维状），并且可以对球状蛋白质中的电荷分布做出合理的猜测（在蛋白质中心附近会发现非极性氨基酸）。但是解决蛋白质折叠的道路并不涉及最终发现某种纳维斯托克斯方程，这些方程可以从第一性原理推导出来并合理地控制系统的行为；不，发生的事情是大量数据和大量计算被投入到这个问题上，并在有一些警告的情况下解决了它。  
Given the nature of the problem, it seems deeply unlikely that we will ever find such simple laws in biological systems except in toy examples.  
鉴于问题的性质，我们似乎极不可能在生物系统中找到如此简单的定律，除非是在玩具例子中。

If one believes this then instead of looking at the problem with our reductionism glasses on, we should take a pair of holistic glasses instead: black box the problem; collect data where we can and let ML figure out the complex pattern of relationships between inputs and outputs.  
如果有人相信这一点，那么与其戴上还原论的眼镜来看问题，不如戴上一副整体眼镜：把问题黑框化；尽可能地收集数据，让 ML 找出输入和输出之间复杂的关系模式。

If you happen to work in a domain that's not biology that's ML-heavy you'll probably be nodding along, but there are some issues with this approach which I'l discuss in a bit.  
如果你碰巧在一个非生物学的领域工作，但 ML-heavy 你可能会点头同意，但这种方法存在一些问题，我稍后会讨论一下。

## Protein folding prediction: how useful?  
蛋白质折叠预测：有用吗？

I think for people that are not working in the life sciences, AlphaFold might have changed their view on how optimistic they should be about radically accelerating drug development. For people working in drug discovery, the update might have been small.  
我认为对于那些不在生命科学领域工作的人来说，AlphaFold 可能已经改变了他们对从根本上加速药物开发应该有多乐观的看法。对于从事药物发现工作的人来说，更新可能很小。  
Both views have something to them: thinking in the short term, indeed solving protein folding doesn't do much to help the current process to find new drugs.  
这两种观点都有道理：从短期来看，解决蛋白质折叠问题确实对当前寻找新药的过程帮助不大。  
In the longer term (and people from outside an industry, and especially those working in tech, might be more likely to take the long/high level view), AlphaFold can indeed be taken as a harbinger of future transformational change.  
从长远来看（来自行业外的人，尤其是从事技术工作的人，可能更有可能采取长期/高层次的观点），AlphaFold 确实可以被视为未来转型变革的先兆。

[Mohammed AlQuraishi](https://moalquraishi.wordpress.com/2018/12/09/alphafold-casp13-what-just-happened/)'s commentary on AlphaFold's release back in 2018 continues to be the best summary of the reaction of the protein folding community to DeepMind's monumental achievement. It's a combination of amazement (_“What just happened?”_)  
Mohammed AlQuraishi 对 AlphaFold 在 2018 年发布的评论仍然是蛋白质折叠社区对 DeepMind 巨大成就反应的最佳总结。这是惊讶的结合（“刚刚发生了什么？”）

> I don’t think we would do ourselves a service by not recognizing that what just happened presents a serious indictment of academic science. There are dozens of academic groups, with researchers likely numbering in the (low) hundreds, working on protein structure prediction.  
> 我不认为我们不承认刚刚发生的事情是对学术科学的严重控诉，这对我们自己有好处。有几十个学术团体，研究人员可能有（低）数百人，致力于蛋白质结构预测。**We have been working on this problem for decades, with vast expertise built up on both sides of the Atlantic and Pacific, and not insignificant computational resources when measured collectively.  
> 几十年来，我们一直致力于解决这个问题，在大西洋和太平洋两岸积累了丰富的专业知识，而且在集体衡量时，计算资源也不是微不足道的。  
> For DeepMind’s group of ~10 researchers, with primarily (but certainly not exclusively) ML expertise, to so thoroughly route everyone surely demonstrates the structural inefficiency of academic science.  
> 对于 DeepMind 的约 10 名研究人员组成的团队，主要（但肯定不完全）具有 ML 专业知识，如此彻底地引导每个人肯定证明了学术科学的结构性低效。** This is not Go, which had a handful of researchers working on the problem, and which had no direct applications beyond the core problem itself. Protein folding is a central problem of biochemistry, with profound implications for the biological and chemical sciences.  
> 这不是围棋，它有少数研究人员正在研究这个问题，并且除了核心问题本身没有直接应用。蛋白质折叠是生物化学的核心问题，对生物和化学科学具有深远的影响。  
> How can a problem of such vital importance be so badly neglected? \[...\]  
> 一个如此重要的问题怎么会被如此严重地忽视呢？ \[...\]
> 
> What is worse than academic groups getting scooped by DeepMind?  
> 还有什么比学术团体被 DeepMind 抢走更糟糕的呢？**The fact that the collective powers of Novartis, Pfizer, etc, with their hundreds of thousands (~million?  
> 事实上，诺华、辉瑞等拥有数十万（~百万？  
> ) of employees, let an industrial lab that is a complete outsider to the field, with virtually no prior molecular sciences experience, come in and thoroughly beat them on a problem that is, quite frankly, of far greater importance to pharmaceuticals than it is to Alphabet.  
> ) 的员工，让一个完全是该领域局外人、几乎没有分子科学经验的工业实验室进来，并在一个问题上彻底击败他们，坦率地说，这个问题对制药业的重要性远大于对制药业的重要性字母。** It is an indictment of the laughable “basic research” groups of these companies, which pay lip service to fundamental science but focus myopically on target-driven research that they managed to so badly embarrass themselves in this episode.  
> 这是对这些公司可笑的“基础研究”团体的控诉，他们口头上说是基础科学，但目光短浅地专注于目标驱动的研究，以至于他们在这一集里让自己非常尴尬。

With measured [caution](https://moalquraishi.wordpress.com/2020/12/08/alphafold2-casp14-it-feels-like-ones-child-has-left-home/), even in his later commentary of the improved AlphaFold2 results:  
即使在他后来对改进的 AlphaFold2 结果的评论中，他也谨慎地说道：

> ##### Drug discovery? 药物发现？
> 
> I will end this section with the question that gets asked most often about protein structure prediction—will it change drug discovery? Truthfully, in the short term, the answer is most likely no. But it’s complicated.  
> 我将以关于蛋白质结构预测最常被问到的问题结束本节——它会改变药物发现吗？说实话，在短期内，答案很可能是否定的。但这很复杂。
> 
> One important thing to note is that, of the entire drug development pipeline, the early discovery stage is just that, an early stage.  
> 需要注意的一件重要事情是，在整个药物开发流程中，早期发现阶段只是早期阶段。  
> Even if crystallography were to become fast and routine, it would still not fundamentally alter the dynamics of drug discovery as it is practiced today, as most of the cost is in the later stages of drug development beyond medicinal chemistry and well into biology and physiology.  
> 即使晶体学变得快速和常规，它仍然不会从根本上改变药物发现的动态，因为它是今天实践的，因为大部分成本是在药物开发的后期阶段，超越了药物化学，进入了生物学和生理学。  
> Reliable protein structure prediction doesn’t change that.  
> 可靠的蛋白质结构预测不会改变这一点。

But at the end of that section there is one comment made which might not be noticed at first because it's almost a remark made in passing:  
但在那一节的末尾，有一条评论一开始可能不会被注意到，因为它几乎是顺便说一句：

> we can imagine a future in which drugs are _designed_ for their polypharmacology, _i.e._, to modulate multiple protein targets intentionally. This would very much be unlike conventional medicinal chemistry as practiced today where the emphasis is on minimizing off-targets and making highly selective small molecules. **Drugs with designed polypharmacology may be able to modulate entire signaling pathways instead of acting on one protein at a time. There have been many fits and starts in this space and there is no reason to believe that a change is imminent**, especially because the systems challenges of the equation remain formidable. Wide availability of structures may hasten progress however.  
> 我们可以想象一个未来，药物被设计用于多种药理学，即有意调节多个蛋白质靶标。这与当今实践的传统药物化学非常不同，传统药物化学的重点是最大限度地减少脱靶和制造高选择性的小分子。具有多重药理学设计的药物可能能够调节整个信号通路，而不是一次作用于一种蛋白质。这个领域经历了很多起伏，没有理由相信变化迫在眉睫，尤其是因为方程式的系统挑战仍然非常艰巨。然而，结构的广泛可用性可能会加速进展。

AlQuraishi's comment is a hint of where I think the future of drug discovery will look like: moving beyond the idea of the target to _drugging_ cell or organism state itself.  
AlQuraishi 的评论暗示了我认为药物发现的未来会是什么样子：超越目标的概念，对细胞或生物体状态本身进行药物治疗。

## Drug discovery and self-driving cars  
药物发现和自动驾驶汽车

The ultimate goal of the biomedical enterprise (academia, startups, and big pharmas) is the improvement of human health.  
生物医药企业（学术界、初创公司和大型制药公司）的最终目标是改善人类健康。  
The proxy goal for that goal is drug discovery (and development) and the proxy for "drug" is, historically, orally available single-target small molecule inhibitors of some protein (or agonist for some receptor).  
该目标的代理目标是药物发现（和开发），而“药物”的代理在历史上是某些蛋白质（或某些受体的激动剂）的口服单靶标小分子抑制剂。  
Or what is the same: Up until recently, the way of thinking if you want to address a disease is:  
或者相同之处：直到最近，如果你想解决一种疾病，思维方式是：

1.  Understand a disease: Have an idea of what's going on, find the pathways involved, examine human genetics to find correlations between genes and disease incidence.  
    了解疾病：了解正在发生的事情，找到相关途径，检查人类遗传学以发现基因与疾病发病率之间的相关性。
    
    1.  Example: Learning that the [mevalonate](https://en.wikipedia.org/wiki/Mevalonate_pathway) pathway is involved in LDL synthesis, and that [LDL cholesterol is a driver](https://academic.oup.com/eurheartj/article/41/24/2313/5735221) of heart disease  
        示例：了解甲羟戊酸途径参与低密度脂蛋白合成，以及低密度脂蛋白胆固醇是心脏病的驱动因素
2.  Find a target: a protein (usually) that is involved in a disease and whose activity can potentially be modulated (turned up or down). It tends to be easier to block the action of a protein than to enhance it. (Example: HMG-CoA [reductase](https://en.wikipedia.org/wiki/HMG-CoA_reductase))  
    找到一个目标：一种与疾病有关的蛋白质（通常），其活性可能会被调节（上调或下调）。阻断蛋白质的作用往往比增强它更容易。 （例如：HMG-CoA 还原酶）
    
3.  Find a small molecule that delivers the desired effect, i.e. that binds to the catalytic domain of an enzyme to inhibit it  
    找到一种能产生所需效果的小分子，即结合酶的催化结构域以抑制它
    
    1.  Usually one tries lots of compounds (high throughput screening), then picks promising ones and tweaks them until one seems to work well.  
        通常一个人会尝试很多化合物（高通量筛选），然后挑选出有前途的化合物并对其进行调整，直到其中一种看起来效果不错。
    2.  Here one can also do some ML to speed up e.g. [docking](https://en.wikipedia.org/wiki/Docking_(molecular)) calculations  
        这里也可以做一些 ML 来加速，例如对接计算
    3.  Example: [Atorvastatin](https://en.wikipedia.org/wiki/Atorvastatin), which inhibits the action of HMG-CoA thus reducing LDL synthesis downstream  
        示例：阿托伐他汀，可抑制 HMG-CoA 的作用，从而减少下游低密度脂蛋白的合成
4.  Ensure that said small molecule can be taken orally. There are various rules of thumb here like [Lipinski's](https://en.wikipedia.org/wiki/Lipinski%27s_rule_of_five) rules to guess if a molecule will be "[druglike](https://en.wikipedia.org/wiki/Druglikeness)".  
    确保所述小分子可以口服。这里有各种经验法则，比如 Lipinski 的规则来猜测一个分子是否会“像药物”。
    
    1.  This is not always the case; some drugs are injected so no need to worry about gut absorption then. Vaccines are the clearest example.  
        这并非总是如此;有些药物是注射的，所以不用担心肠道吸收。疫苗是最明显的例子。
5.  Ensure that said small molecule doesn't have side-effects  
    确保所述小分子没有副作用
    
    1.  Example: Statins do have side effects, but they are considered minimal in relation to the benefit of the drug. Nonetheless the search for even safer interventions has led to other LDL-lowering drugs like PCSK9 inhibitors.  
        示例：他汀类药物确实有副作用，但与药物的益处相比，它们被认为是微乎其微的。尽管如此，对更安全的干预措施的寻求导致了其他降低 LDL 的药物的出现，如 PCSK9 抑制剂。
    2.  Example 2: A gamma secretase inhibitor (For Alzheimer's treatment) [caused](https://massivesci.com/articles/alzheimers-blood-cancer-myeloma-drug-development-immunotherapy/) increased skin cancer, so even if it treated the disease it's not on net worth using  
        示例 2：γ 分泌酶抑制剂（用于阿尔茨海默氏症的治疗）导致皮肤癌增加，因此即使它治疗了这种疾病，也没有净值使用
6.  Profit! 利润！
    
    1.  Example: Lipitor (atorvastatin) generated billions of dollars of revenue for Pfizer over the last 20 years  
        示例：立普妥（阿托伐他汀）在过去 20 年为辉瑞公司带来了数十亿美元的收入
    2.  Example 2: Even when drugs don't end up making it all the way to the clinic (As happened with [Sirtris](https://en.wikipedia.org/wiki/Sirtris_Pharmaceuticals)) you can profit too sometimes, what's not to like! /jk  
        示例 2：即使药物最终并没有一路运到诊所（就像 Sirtris 发生的那样），有时您也可以获利，有什么不喜欢的！ /jk

You might wonder a few things here:  
你可能想知道这里有几件事：

1.  How do you know what the target should be? First principles thinking, domain knowledge, little experiments here and there.  
    你怎么知道目标应该是什么？第一性原理思维、领域知识、到处都是小实验。
    
    1.  Example: Atorvastatin came from earlier research on other molecules, [lovastatin](https://en.wikipedia.org/wiki/Lovastatin) and [mevastatin](https://en.wikipedia.org/wiki/Mevastatin), which in turn was discovered by searching for antimicrobial agents, fermenting broths of a [fungus](https://en.wikipedia.org/wiki/Penicillium_citrinum)  
        示例：阿托伐他汀来自早期对其他分子洛伐他汀和美伐他汀的研究，这些分子又是通过寻找抗菌剂、发酵真菌肉汤而发现的
2.  Why a single target? It's easier to carefully study two entities (a protein and a ligand for it) than to study every molecular entity in a cell in detail  
    为什么是单一目标？仔细研究两个实体（一种蛋白质及其配体）比详细研究细胞中的每个分子实体更容易
    
3.  Why restrict ourselves to orally administered drugs? Because these drugs will need to be administered repeatedly (they are small molecules, eventually they get metabolized and excreted), usually at home, and having people injecting themselves daily is considered unfeasible.  
    为什么要限制我们口服药物？因为这些药物需要反复给药（它们是小分子，最终会被代谢和排出体外），通常是在家里，让人们每天自己注射被认为是不可行的。
    

As an analogy here, consider self-driving cars: Traditionally the problem of driving a car initially required engineers to identify features like lines and map them to say lanes and then keep the car in there. The algorithms used for this were simple and understandable like [Canny](https://en.wikipedia.org/wiki/Canny_edge_detector) edge detectors or [Hough](https://en.wikipedia.org/wiki/Hough_transform) transforms. The answers to the equivalent questions would have been something like:  
作为这里的类比，考虑自动驾驶汽车：传统上驾驶汽车的问题最初需要工程师识别线等特征并将它们映射到车道，然后将汽车停在那里。用于此的算法简单易懂，如 Canny 边缘检测器或霍夫变换。等价问题的答案应该是这样的：

1.  How do you know what features to use? First principles thinking, asking domain experts, little experiments here and there.  
    您怎么知道要使用哪些功能？第一性原理思考，询问领域专家，到处做小实验。
2.  Why a small number of features, why two lines/a single lane? It's hard to consider very complex scenarios, let's do a single lane at a time.  
    为什么只有少量特征，为什么有两条线/一条车道？很难考虑非常复杂的场景，让我们一次只做一个车道。
3.  Why restrict ourselves to driving on sunny days with good visibility? It's already hard to do this!  
    为什么要限制自己在能见度好的晴天开车？这已经很难了！

With self-driving cars we are now seeing a competition between two approaches: This classical approach just described, where many intermediate, hand_craft_ed representations are modeled explicitly (mostly abandoned), and the new end to end approach (Tesla and comma.  
对于自动驾驶汽车，我们现在看到两种方法之间的竞争：刚刚描述的经典方法，其中许多中间的、手工制作的表示被显式建模（大部分被放弃），以及新的端到端方法（Tesla 和逗号。  
ai perhaps being the ones ideologically closer to this) where the car goes straight from pixels perceived to commands issued to the motors and steering system, where visualizations are still provided to the human driver for reassurance, but not being strictly required for model performance.  
人工智能可能在意识形态上更接近于此），其中汽车直接从感知到的像素到向电机和转向系统发出的命令，其中仍向人类驾驶员提供可视化以确保其安全，但并不是模型性能所严格要求的。

This second paradigm replaces an object-level research oriented mindset where one aims to understand the system of interest, with an engineering-heavy mindset where understanding is deprioritized in favor of control.  
第二种范式取代了以对象级研究为导向的思维模式，在这种思维模式中，人们旨在理解感兴趣的系统，而以工程为主的思维模式取代了理解优先于控制的思维模式。  
What matters then is instead designing systems able to ingest large quantities of data and models able to distill that into solutions to the problem, and that is an easier task than answering the question "how does one drive" or "what is driving" from first principles.  
那么重要的是设计能够摄取大量数据的系统和能够将其提炼为问题解决方案的模型，这比从一开始就回答“一个人如何驾驶”或“什么在驾驶”的问题更容易原则。

What would the equivalent of this approach look like for drug discovery?  
对于药物发现，这种方法的等价物会是什么样子？

## Self driving cars are easier than drug discovery  
自动驾驶汽车比药物发现更容易

While not perfect in all cases yet, it's now possible for a commercially available car to [drive itself all the way](https://www.youtube.com/watch?v=WR8wX1pejzI) from SF to LA. What made this possible is largely the same thing that made DeepMind's achievements in Go and Chess possible: Lots of data and simulators that are very close to the real domain.  
虽然在所有情况下都不是完美的，但现在商用汽车可以从旧金山一路自动驾驶到洛杉矶。使这一切成为可能的，在很大程度上与使 DeepMind 在围棋和国际象棋方面取得成就的事情是一样的：大量的数据和非常接近真实领域的模拟器。  
The domain where the model is operating (a car in the real world) can be trained on real world data for that same system (from the Tesla fleet) and enhanced with simulated driving data.  
模型运行的领域（现实世界中的汽车）可以根据同一系统（来自特斯拉车队）的真实世界数据进行训练，并使用模拟驾驶数据进行增强。  
The physics of driving a car are understood well enough and graphics can be made so realistic than one can train on [simulators](https://www.youtube.com/watch?v=6hkiTejoyms) too!  
驾驶汽车的物理原理已经被充分理解，而且图形可以制作得如此逼真，甚至连在模拟器上训练都无法做到！

In biological systems this is not the case: The state of a human body is extremely complex and not yet fully understood. The dynamics of it extend over days (fighting an infection), months (pregnancy), and even decades (for processes like puberty).  
在生物系统中情况并非如此：人体的状态极其复杂且尚未完全了解。它的动态会持续数天（对抗感染）、数月（怀孕），甚至数十年（青春期等过程）。  
Measuring this state is also nontrivial; one can only collect blood only so often, and measure only so much.  
测量这种状态也很重要。一个人只能如此频繁地采集血液，并且只能进行如此多的测量。  
Extracting biopsies to access organ state directly is highly invasive, and the perturbations a human is exposed to in the wild are far from what would be required to find new drugs.  
提取活组织切片以直接获取器官状态具有高度侵入性，而且人类在野外受到的扰动远非寻找新药所需的扰动。  
Natural data is useful to learn about things like exercise and diet (and even that's hard), but we don't go around taking random pills so that one can build models of what random compounds do to us.  
自然数据对于了解诸如运动和饮食之类的事情很有用（即使那也很难），但我们不会到处乱吃药，这样人们就可以建立随机化合物对我们的影响的模型。

Sometimes a variant of this _is_ possible: Because (twins aside) we are all genetically distinct, nature is running the world greatest clinical trial in us already, and with large enough collections of sequenced genomes it's possible to [chart](https://twitter.com/lal_avantika/status/1617350800153665537) a path towards new drugs.  
有时这种情况的变体是可能的：因为（除了双胞胎）我们在基因上都是不同的，大自然已经在我们身上进行了世界上最伟大的临床试验，并且有了足够多的测序基因组集合，就有可能规划出一条通向新药的道路。

But genetic lottery aside, short of a large army of willing volunteers, we can't use the actual system (the human body) to experiment with directly at scale, and we can't simulate it yet, we have to settle for something simpler.  
但是撇开基因彩票不谈，缺少大量自愿的志愿者，我们不能使用实际系统（人体）直接进行大规模实验，我们还不能模拟它，我们必须满足于更简单的东西.  
We can either test in animals (a whole organism) or we can test in human cells in vitro, or eventually in organoids.  
我们可以在动物（整个生物体）中进行测试，也可以在体外对人体细胞进行测试，或者最终在类器官中进行测试。

I am very pro in vivo testing: Ultimately yes we are made up of cells but there are many different kinds that interact in different ways.  
我非常支持体内测试：最终是的，我们是由细胞组成的，但有许多不同的种类以不同的方式相互作用。  
If immune rejuvenation is one key part of the future of medicine, we wouldn't know the full extent of that if we just observe that indeed the function of a given type of immune cell can be improved, one has to see what a that cell does when placed in the context of an organism where it can now more effectively fight cancer and pathogens.  
如果免疫再生是未来医学的一个关键部分，如果我们只是观察到特定类型的免疫细胞的功能确实可以得到改善，我们就不会知道它的全部范围，我们必须看看那个细胞是什么当置于有机体的环境中时，它现在可以更有效地对抗癌症和病原体。

What originally inspired me to write this are these following articles that I read last year. I got a sense there was a sense of renewed excitement in the field (Or just it was a coincidence that I these ended up in my reaading list) that was worth thinking about.  
最初激发我写这篇文章的是我去年阅读的以下文章。我感觉到该领域出现了一种新的兴奋感（或者只是巧合，我这些最终出现在我的阅读列表中）值得思考。

One idea is say training a large language model on the entirety of Scihub and then asking it to solve a particular problem like predicting protein structure, producing drug candidates, or explaining why Alzheimer's actually happens.  
一个想法是在整个 Scihub 上训练一个大型语言模型，然后要求它解决一个特定的问题，比如预测蛋白质结构、产生候选药物或解释阿尔茨海默氏症实际发生的原因。  
This has been tried before and the results have been... far from that promise: Albeit trained on less data, this is what happened with Galactica, and this is the current state of _ChatGPT_ and similar state of the art models. Scraping Scihub is feasible, but the results probably won't be that enlightening: We want the models to tell us new things, and so far LLMs tend to be very conservative. But beyond that, there isn't that much data out there.  
之前已经尝试过这种方法，但结果却……与承诺相差甚远：尽管训练的数据较少，但这就是卡拉狄加发生的情况，这就是 _ChatGPT_ 和类似的最先进模型的当前状态。 Scraping Scihub 是可行的，但结果可能不会那么有启发性：我们希望模型告诉我们新事物，到目前为止，LLM 往往非常保守。但除此之外，那里没有那么多数据。  
The papers might describe at a high level an experiment that was done and some particular results, but accessing the raw or processed data that was gathered is something one can't get from the paper or even the public internet in many cases. Sam Rodriques is [right](https://www.sam-rodriques.com/post/why-is-progress-in-biology-so-slow) when he says that _I am also skeptical of the ability of even an AI trained on the entire scientific literature to predict drug efficacy for diseases for which have no effective drugs and no understanding of how they work._  
论文可能在较高层次上描述了一项已完成的实验和一些特定的结果，但在许多情况下，访问收集到的原始数据或经过处理的数据是无法从论文甚至公共互联网上获得的。山姆·罗德里克斯 (Sam Rodriques) 说得对，我也怀疑即使是在整个科学文献中训练过的 AI 也无法预测没有有效药物且不了解其工作原理的疾病的药物疗效。

Josh Nicholson, who [wrote](https://future.com/how-to-build-gpt-3-for-science/) in more detail about how difficult it would be to do this actual thing, is more optimistic. But as he points out, we already have this: [ScholarBERT](https://arxiv.org/pdf/2205.11342v1.pdf) was actually trained on what seems to be all scientific papers (75M of them, 221B tokens, as opposed to 48M papers/88B tokens for Galactica. Scihub has ~80M), and Science remains an unsolved problem.  
乔什·尼科尔森 (Josh Nicholson) 更详细地描述了做这件真实的事情会有多困难，他更加乐观。但正如他指出的那样，我们已经有了这个：ScholarBERT 实际上接受了似乎所有科学论文的训练（其中 7500 万篇，221B 令牌，而不是卡拉狄加的 4800 万篇论文/88B 令牌。Scihub 有大约 8000 万）和科学仍然是一个未解决的问题。  
ScholarBERT is a relatively small model (770M parameters) so one can always think that maybe 100x parameter count would lead to better performance at _Solving Science_ but I doubt it.  
ScholarBERT 是一个相对较小的模型（770M 参数），因此人们总是认为 100 倍的参数数量可能会在 Solving Science 中带来更好的性能，但我对此表示怀疑。

However, the real problem we care about is not producing plausible (given current knowledge) completions to papers.  
然而，我们真正关心的问题不是为论文生成合理的（给定当前知识）补全。  
An assistant that has access to the world's scientific knowledge (or its publicly available portion) would be valuable but not that useful, especially if scientists working in a domain already have that knowledge.  
可以访问世界科学知识（或其公开可用部分）的助手将是有价值的但不是那么有用，特别是如果在某个领域工作的科学家已经拥有该知识。  
It would be a different matter if a model generates new hypothesis or proposes new experiments that are unintuitive but promising.  
如果一个模型产生新的假设或提出不直观但有希望的新实验，那将是另一回事。

Adam Green [writing](https://markov.bio/biomedical-progress/) _A Future History of Biomedical Progress_ expresses the same sentiment I share throughout the essay, going perhaps even further than I would. His essay is the most substantial inspiration for my own:  
亚当·格林 (Adam Green) 撰写的《生物医学进步的未来史》(A Future History of Biomedical Progress) 表达了我在整篇文章中所表达的相同观点，甚至可能比我想的更进一步。他的文章是对我自己最重要的启发：

> progress in basic biology research tools has created the potential for accelerating medical progress; however, this potential will not be realized unless we fundamentally rethink our approach to biomedical research. Doing so will require **discarding the reductionist, human-legibility-centric research ethos** underlying current biomedical research, which has generated the remarkable basic biology progress we have seen, **in favor of a purely control-centric ethos based on machine learning**. Equipped with this new research ethos, we will realize that control of biological systems obeys empirical scaling laws and is bottlenecked by biocompute. These insights point the way toward accelerating biomedical progress. \[...\]  
> 基础生物学研究工具的进步为加速医学进步创造了潜力；然而，除非我们从根本上重新思考我们的生物医学研究方法，否则这种潜力将无法实现。这样做需要摒弃当前生物医学研究背后的还原论者、以人类可读性为中心的研究精神，这种精神已经产生了我们所看到的显着的基础生物学进步，转而支持基于机器学习的纯粹以控制为中心的精神。有了这种新的研究精神，我们将意识到生物系统的控制遵循经验尺度定律，并受到生物计算的瓶颈。这些见解为加速生物医学进步指明了方向。 \[...\]
> 
> One cut on this is how physics-like you think the future of biomedical research is: are there human-comprehensible “general laws” of biomedical dynamics left to discover, or have all the important ones already been discovered?  
> 一个切入点是你认为生物医学研究的未来有多像物理学：是否存在人类可以理解的生物医学动力学“一般规律”有待发现，或者是否已经发现了所有重要的规律？  
> And how lumpy is the distribution of returns to these ideas—will we get another theory on par with Darwin’s?  
> 这些想法的回报分布有多不稳定——我们会得到另一个与达尔文的理论相提并论的理论吗？
> 
> For instance, RNA polymerases were [discovered over 50 years ago](https://www.nature.com/articles/s41594-019-0303-1), and a tremendous amount of basic biology knowledge has followed from this discovery—had we never discovered them, our knowledge of transcriptional regulation, and therefore biomedical dynamics, would be correspondingly impoverished. Yet [when](https://en.wikipedia.org/wiki/List_of_Nobel_laureates_in_Physiology_or_Medicine) [was](https://en.wikipedia.org/wiki/List_of_Nobel_laureates_in_Chemistry) the last time we made a similarly momentous discovery in basic biology? Might biomedicine be exhausted of grand unifying theories, left only with factoids to discover? Or might these theories and laws be inexpressible in the language of human-legible models?  
> 例如，RNA 聚合酶是在 50 多年前发现的，大量的生物学基础知识都源于这一发现——如果我们从未发现它们，我们对转录调控以及生物医学动力学的知识就会相应地贫乏。然而，我们上一次在基础生物学中取得类似的重大发现是什么时候？生物医学可能会耗尽大统一理论，只剩下事实证明吗？或者这些理论和定律可能无法用人类可读模型的语言来表达？

But in one of the footnotes there's a point where the complications of truly being "end to end" become more obvious:  
但在其中一个脚注中，真正“端到端”的复杂性变得更加明显：

> Insitro et al. are to drug discovery as Waymo et al. are to autonomous vehicles.  
> Instro 等人。与 Waymo 等人一样致力于药物发现。是自动驾驶汽车。  
> Just as some think autonomous vehicles will be solved by building high-definition maps of cities and modeling dynamics at the level of individual pedestrian behavior, some think biomedicine will be solved by building high-definition molecular [“maps” of diseases](https://cellarity.com/platform) and modeling dynamics at the level of individual cellular behavior. Though they are directionally correct in their use of machine learning, they [fail to](https://biotech-insider.com/cellarity-nets-123m-to-drive-cell-behavior-pipeline-toward-clinic/) abstract [sufficiently](https://www.youtube.com/watch?v=hbLiehrC2DQ&t=460s).  
> 正如一些人认为自动驾驶汽车将通过构建城市的高清地图和在个体行人行为层面建模动力学来解决一样，一些人认为生物医学将通过构建疾病的高清分子“地图”和在单个行人行为层面建模动力学来解决。个体细胞行为水平。尽管他们在使用机器学习方面方向正确，但他们未能充分抽象。

Green wants to truly "end-to-end" biology. That is, having a system we can ask "make a human healthy" and getting an answer, trained on triplets of (diseased human, perturbation, healthy human).  
格林想要真正“端到端”的生物学。也就是说，拥有一个系统，我们可以询问“让人类健康”并得到答案，并在三元组（患病的人、扰动的人、健康的人）上进行训练。  
Of course, he admits this is unrealistic because of ethical considerations; so rather he proposes to do this in mice and organoids (as close as possible to the real system) and then try to transfer from there.  
当然，出于伦理的考虑，他承认这是不现实的；因此，他建议在小鼠和类器官（尽可能接近真实系统）中这样做，然后尝试从那里转移。  
In the paragraph above he says Cellarity is not going far enough: They are trying to fix cells, but cells are not what we ultimately care about (the whole organism); in his view fixing cells is like learning to recognize traffic cones when building a self-driving car: a hand-engineered feature that is not required if one can end-to-end enough.  
在上面的段落中，他说 Cellarity 还不够远：他们试图修复细胞，但细胞并不是我们最终关心的（整个有机体）；在他看来，固定细胞就像在建造自动驾驶汽车时学习识别交通锥：如果端到端足够，则不需要手工设计的功能。

I think cells are better models than he thinks, perhaps. Biological systems have the advantage of being built of similar building blocks (all cells work in the same fundamental way), where parts of the system are adjusting themselves to the state of other parts.  
我认为细胞可能是比他想象的更好的模型。生物系统的优势在于由相似的构件构成（所有细胞都以相同的基本方式工作），其中系统的某些部分会根据其他部分的状态进行自我调整。  
If you rejuvenate e.g. blood, you can probably have effects elsewhere. If you hit 60% of a tissue with a successfully rejuvenating therapy, chances are you might go beyond that 60% through cell-to-cell signaling.  
如果您恢复活力，例如血液，你可能会对其他地方产生影响。如果你通过成功的恢复活力疗法击中了 60% 的组织，那么你可能会通过细胞间信号传导超过这 60%。  
The self-driving analogy shouldn't be cones but rather charging electric cars: Given the task "Driving an electric car across the United States without human intervention" one has to automate driving and charging.  
自动驾驶类比不应该是圆锥体，而应该是给电动汽车充电：给定“在没有人为干预的情况下驾驶电动汽车穿越美国”的任务，必须自动驾驶和充电。  
The true end to end approach would be to train a joint model to control both the car and the charger (perhaps equipped with one of [these](https://www.youtube.com/watch?v=uMM0lRfX6YI)). A single neural network that tells the car what to do and same for the charger.  
真正的端到端方法是训练一个联合模型来控制汽车和充电器（可能配备其中之一）。一个单一的神经网络，告诉汽车该做什么，对充电器也一样。  
But in practice this is unnecessary: You can have a model that drives the car to a spot in the charger and then a simple computer vision based model that controls the charger and gets the car charged.  
但在实践中这是不必要的：你可以有一个模型将汽车开到充电器中的某个位置，然后有一个简单的基于计算机视觉的模型来控制充电器并为汽车充电。  
The performance of this split approach wouldn't be inferior to the true end to end solution, and it is easier to train.  
这种拆分方法的性能不会逊色于真正的端到端解决方案，而且更容易训练。

Similarly, while on paper the problem of "altering the state of a cell" involves a) designing what to do to the cell and b) getting that to the cell, I could imagine how one can solve (a), say a model that predicts what transcription factors to get a cell to express, then [trying to find a way to package](https://www.dynotx.com/) that into an AAV or something else, (b). This might not be doable, but then one can pick the next solution from the model that solves (a) and try again. To the extent that the domains being decoupled, one can substitute end-to-end learning with some more trial and error.  
同样，虽然在纸面上“改变细胞状态”的问题涉及 a) 设计对细胞做什么以及 b) 将其传递给细胞，但我可以想象如何解决 (a)，说一个模型预测哪些转录因子可以让细胞表达，然后试图找到一种方法将其包装到 AAV 或其他东西中，(b)。这可能不可行，但可以从解决 (a) 的模型中选择下一个解决方案，然后再试一次。就领域分离的程度而言，可以用更多的试验和错误来代替端到端学习。  
Ultimately, the question is: Should we put more resources on organoids or better models, ultimately having '[organs](https://en.wikipedia.org/wiki/Organ-on-a-chip) on a chip' so that we can collect data to train end-to-end models? Or should we try to develop therapies with the tools we have available right now? My hunch is that the latter approach can still be useful.  
最终，问题是：我们是否应该将更多资源投入到类器官或更好的模型上，最终拥有“芯片上的器官”，以便我们可以收集数据来训练端到端模型？还是我们应该尝试使用我们现在可用的工具来开发疗法？我的直觉是后一种方法仍然有用。

One more argument against the need for complete end-to-end is that biology is incredibly 'plug and play'. It's possible to replace or address subsystems of an organism separately.  
反对完全端到端需求的另一个论点是，生物学是令人难以置信的“即插即用”。可以单独替换或解决有机体的子系统。  
For example one can replace old bone marrow with young bone marrow without having to concurrently replace everything else. One can even [implant](https://orbi.uliege.be/bitstream/2268/23720/1/Thymo_kidney.pdf) bits of organs in the right place and those organs will function somewhat. And obviously we have seen many successful drugs being developed by modeling just parts of the whole.  
例如，可以用年轻骨髓代替旧骨髓，而不必同时更换其他所有东西。人们甚至可以在正确的位置植入一些器官，这些器官就会发挥一定的作用。显然，我们已经看到许多成功的药物是通过对整体的一部分进行建模来开发的。

And lastly, as readers of Nintil know, I'm a fan of [partial](https://nintil.com/aging-solved-in-vitro) reprogramming.  
最后，正如 Nintil 的读者所知，我是部分重新编程的粉丝。  
I do think fixing aging goes a long way in extending healthy lives, and aging is, to a large extent, the deteriotation of processes that are common to all cell types (like transcription, translation, or autophagy), hence fixing this in vitro and solving systemic delivery seem to, together, go a long way!  
我确实认为修复衰老对延长健康寿命大有帮助，而衰老在很大程度上是所有细胞类型共有的过程的恶化（如转录、翻译或自噬），因此在体外和解决系统性交付似乎在一起，走很长的路！

Pablo Cordero writes [here](https://hyperparameter.space/blog/what-if-we-just-learn-a-language-model-for-all-of-life/) about unifying all of biology into a large model by thinking of biological knowledge as a graph, masking parts of it, and then predicting those parts from the rest of the data. It's not fully clear how one would go about doing this!  
Pablo Cordero 在这里写道，通过将生物学知识视为图形，屏蔽其中的部分，然后根据其余数据预测这些部分，将所有生物学统一到一个大模型中。目前还不完全清楚如何去做这件事！  
I'm no expert in graph neural networks, but certainly the post shares the spirit of "end-to-end biology".  
我不是图神经网络方面的专家，但这篇文章肯定分享了“端到端生物学”的精神。

Lastly, Jacob Kimmel wrote a [really good post](http://jck.bio/learning-representations-of-life/) last year on representation learning as an extension from the way early molecular biologists worked:  
最后，Jacob Kimmel 去年写了一篇关于表征学习的非常好的文章，作为早期分子生物学家工作方式的延伸：

> There’s no general solution to modeling complex systems, but the computational sciences offer a tractable alternative to the analytical approach.  
> 复杂系统的建模没有通用的解决方案，但计算科学提供了一种易于处理的分析方法替代方案。  
> Rather than beginning with a set of rules and attempting to predict emergent behavior, we can observe the emergent properties of a complex system and build models that capture the underlying rules.  
> 与其从一组规则开始并试图预测涌现的行为，不如观察复杂系统的涌现特性并构建捕获潜在规则的模型。  
> We might imagine this as a “top-down” approach to modeling, in contrast to the “bottom-up” approach of the physical tradition.  
> 我们可以将其想象为一种“自上而下”的建模方法，与物理传统的“自下而上”方法形成对比。
> 
> Whereas analytical modelers working on early structures had only a few experimental measurements to contend with – often just a few X-ray diffraction images – cellular and tissue systems within a complex organism might require orders of magnitude more data to properly describe.  
> 虽然研究早期结构的分析建模人员只有少数实验测量需要应对——通常只有几张 X 射线衍射图像——但复杂生物体内的细胞和组织系统可能需要更多数量级的数据才能正确描述。  
> If we want to model how transcriptional regulators define cell types, we might need gene expression profiles of many distinct cell types in an organism.  
> 如果我们想要模拟转录调节因子如何定义细胞类型，我们可能需要生物体中许多不同细胞类型的基因表达谱。  
> If we want to predict how a given genetic change might effect the morphology of a cell, we might similarly require images of cells with diverse genetic backgrounds. **It’s simply not tractable for human-scale heuristics to reason through this sort large scale data and extract useful, quantitative rules of the system.**  
> 如果我们想预测给定的遗传变化如何影响细胞的形态，我们可能同样需要具有不同遗传背景的细胞图像。人类规模的启发式方法很难通过这种大规模数据进行推理并提取有用的系统定量规则。

## Is this time different? 这次有什么不同吗？

Current "ML for drug discovery" startups are far from end to end. They still find a target the old fashioned way, and limit themselves to small molecules (As with [Relay](https://relaytx.com/) or [Exscientia](https://www.exscientia.ai/precision-target)). Some do go beyond the concept of a target and into phenotypic screening (like [Recursion](https://www.recursion.com/)), where there is no initial driving hypothesis behind a drug, instead the company builds models trained to recognize features of cells that look more or less diseased and then build relations between the drugs the cells were treated with and the observed change.  
当前的“用于药物发现的机器学习”初创公司远未结束。他们仍然以老式的方式找到目标，并将自己限制在小分子（与 Relay 或 Exscientia 一样）。有些确实超出了目标的概念并进入了表型筛选（如 Recursion ），其中没有药物背后的初始驱动假设，而是公司建立了经过训练的模型来识别看起来或多或少患病的细胞特征，然后建立关系在处理细胞的药物和观察到的变化之间。  
Recursion hasn't gotten any drug approved yet. [Cellarity](https://cellarity.com/) seems to follow a similar approach, moving away from the idea of a target and towards drugging cell state holistically. I suspect we will see more companies moving in this broad direction.  
Recursion 尚未获得任何药物批准。 Cellarity 似乎遵循类似的方法，从目标的想法转向整体药物细胞状态。我怀疑我们会看到更多的公司朝着这个大方向前进。

Why is this changing? The costs of [reading](https://www.genome.gov/about-genomics/fact-sheets/Sequencing-Human-Genome-cost) and writing DNA are the lowest they have ever been. So is the [number of cells](https://twitter.com/ArtirKel/status/1334347237913022472) we can measure per experiment. Just a few days ago a new paper came out reducing the cost of testing genetic perturbations in cells by an [order](https://twitter.com/DouglasYaoDY/status/1617670125930545154) of magnitude. "High-throughput" is now "[Ultra-high](https://www.nature.com/articles/s41592-021-01153-z) throughput". Collecting data was never as cheap as it is today.  
为什么会发生这种变化？读取和写入 DNA 的成本是有史以来最低的。我们每次实验可以测量的细胞数量也是如此。就在几天前，发表了一篇新论文，将测试细胞遗传扰动的成本降低了一个数量级。 “高通量”现在是“超高通量”。收集数据从来没有像今天这样便宜。

In parallel to increasing volumes of data being collected, only very recently we have started to see the appearance of models that can output predictions on what to do to a population of cells to shift them to a desired state (like [PerturbNet](https://www.biorxiv.org/content/10.1101/2022.07.20.500854v2.full.pdf), from 2022) or models that can predict the effect of combined genetic perturbations ([GE_AR_S](https://www.biorxiv.org/content/10.1101/2022.07.12.499735v2.full.pdf), also from 2022), and of course transformers are coming for perturbation prediction as well ([scFormer](https://www.biorxiv.org/content/10.1101/2022.11.20.517285v1), once again 2022). Thanks to neural networks and progress in representation learning, the model can predict chemical perturbations or gene perturbations alike.  
在收集的数据量不断增加的同时，直到最近我们才开始看到模型的出现，这些模型可以输出关于如何对细胞群进行操作以将它们转变为所需状态的预测（例如 PerturbNet ，从 2022 年开始）或可以预测组合遗传扰动影响的模型（GE_AR_S，也是从 2022 年开始），当然变形金刚也将用于扰动预测（scFormer，再次是 2022 年）。由于神经网络和表示学习的进步，该模型可以预测化学扰动或基因扰动等。

I don't have concrete timelines for when we are going to 'solve biology with ML', but working towards that end seems enormously valuable  
对于我们何时“用 ML 解决生物学问题”，我没有具体的时间表，但朝着这个目标努力似乎非常有价值

## Further reading 延伸阅读

[AI and Drug Discovery: Attacking the Right Problems | Science | AAAS](https://www.science.org/content/blog-post/ai-and-drug-discovery-attacking-right-problems)[When Quality Beats Quantity: Decision Theory, Drug Discovery, and the Reproducibility Crisis | PLOS ONE](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0147215)  
AI 和药物发现：解决正确的问题 |科学 | AAAS 当质量胜过数量：决策理论、药物发现和可重复性危机 |公共科学图书馆

[Computational Happiness, Delayed | Science | AAAS  
计算幸福，延迟 |科学 |美国科学促进会](https://www.science.org/content/blog-post/computational-happiness-delayed)

[Artificial intelligence in drug discovery: what is realistic, what are illusions? Part 1: Ways to make an impact, and why we are not there yet - ScienceDirect  
药物发现中的人工智能：什么是现实，什么是幻想？第 1 部分：产生影响的方法，以及我们尚未达到的原因 - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1359644620305274)

[Artificial intelligence in drug discovery: what is realistic, what are illusions? Part 2: a discussion of chemical and biological data - ScienceDirect  
药物发现中的人工智能：什么是现实，什么是幻想？第 2 部分：化学和生物学数据的讨论 - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1359644621000428)

[Computer-aided drug design: the next 20 years | SpringerLink](https://link.springer.com/article/10.1007/s10822-007-9142-y)[Is your machine learning telling you anything you didn’t already know?](http://drugdiscovery.net/data/cambridge_ai.pdf)  
计算机辅助药物设计：未来20年| SpringerLink 您的机器学习是否告诉您任何您还不知道的事情？

[AI in drug discovery, a 2022 review  
药物发现中的 AI，2022 年回顾](https://practicalcheminformatics.blogspot.com/2023/01/ai-in-drug-discovery-2022-highly.html)

[Four Decades Of Hacking Biotech And Yet Biology Still Consumes Everything  
四个十年的黑客攻击生物技术，但生物学仍然消耗一切](https://lifescivc.com/2017/04/four-decades-hacking-biotech-yet-biology-still-consumes-everything/)

[Using deep learning to model the hierarchical structure and function of a cell - PMC  
使用深度学习对细胞的层次结构和功能进行建模 - PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5882547/)

_Ricón, José Luis, “Notes on end-to-end biology”, Nintil (2023-01-26), available at https://nintil.com/biology-llms/.  
Ricón、José Luis，“关于端到端生物学的注释”，Nintil (2023-01-26)，可在 https://nintil.com/biology-llms/ 获取。_
