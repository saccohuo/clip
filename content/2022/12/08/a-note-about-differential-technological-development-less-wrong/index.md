---
title: "关于差异化技术发展的说明"
date: 2022-12-08T12:29:29+08:00
updated: 2022-12-08T12:29:29+08:00
taxonomies:
  tags: []
extra:
  source: https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development
  hostname: www.lesswrong.com
  author: by So8res
  original_title: "A note about differential technological development - LessWrong"
  original_lang: en
---

Crossposted from the [AI Alignment Forum](https://alignmentforum.org/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development). May contain more technical jargon than usual.

Quick note: I occasionally run into arguments of the form "my research advances capabilities, but it advances alignment more than it advances capabilities, so it's good on net". I do not buy this argument, and think that in most such cases, this sort of research does more harm than good. (Cf. [differential technological development](https://forum.effectivealtruism.org/posts/g6549FAQpQ5xobihj/differential-technological-development).)

快速说明：我偶尔会遇到这样的论点：“我的研究提高了能力，但它比提高能力更能促进一致性，所以它在网上很好”。 我不赞成这种说法，并认为在大多数此类情况下，这种研究弊大于利。 （参见 [差异技术发展](https://forum.effectivealtruism.org/posts/g6549FAQpQ5xobihj/differential-technological-development) 。）

For a simplified version of my model as to why:

对于我的模型的简化版本，为什么：

-   Suppose that aligning an AGI requires 1000 person-years of research.
    -   900 of these person-years can be done in parallelizable 5-year chunks (e.g., by 180 people over 5 years — or, more realistically, by 1800 people over 10 years, with 10% of the people doing the job correctly half the time).
    -   The remaining 100 of these person-years factor into four chunks that take 25 serial years apiece (so that you can't get any of those four parts done in less than 25 years).
-   假设对齐 AGI 需要 1000 人年的研究。
    -   这些人年中的 900 人可以在可并行的 5 年时间块中完成（例如，由 180 人在 5 年内完成——或者，更现实地说，由 1800 人在 10 年内完成，其中 10% 的人在一半时间内正确完成工作).
    -   这些人年中剩余的 100 个因素分为四个部分，每个部分需要 25 个连续年（这样你就无法在不到 25 年的时间内完成这四个部分中的任何一个）。

In this toy model, a critical resource is _serial time_: if AGI is only 26 years off, then shortening overall timelines by 2 years is a death sentence, _even if you're getting all 900 years of the "parallelizable" research done in exchange._

在这个玩具模型中，一个关键资源是 _串行时间_ ：如果 AGI 仅剩 26 年，那么将总体时间线缩短 2 年就是死刑， _即使您完成了所有 900 年的“可并行化”研究作为交换._

My real model of the research landscape is more complex than this toy picture, but I do in fact expect that serial time is a key resource when it comes to AGI alignment.

我对研究领域的真实模型比这张玩具图更复杂，但事实上我确实希望串行时间是 AGI 对齐的关键资源。

The most blatant case of alignment work that seems **parallelizable** to me is that of "AI psychologizing": we can imagine having enough success building comprehensible minds, and enough success with transparency tools, that with a sufficiently large army of people studying the alien mind, we can develop a pretty good understanding of what and how it's thinking. (I currently doubt we'll get there in practice, but if we did, I could imagine most of the human-years spent on alignment-work being sunk into understanding the first artificial mind we get.)

，最明显的对齐工作案例 **在我看来** 是“人工智能心理化”：我们可以想象在构建可理解的思维方面取得了足够的成功，并且在透明度工具方面取得了足够的成功，并且有足够多的人研究外星人的思维，我们可以很好地理解它在想什么以及如何思考。 （我目前怀疑我们是否会在实践中到达那里，但如果我们做到了，我可以想象人类花费在对齐工作上的大部分时间都被用于理解我们得到的第一个人工思维。）

The most blatant case of alignment work that seems **serial** to me is work that requires having a theoretical understanding of minds/optimization/whatever, or work that requires having just the right concepts for thinking about minds. Relative to our current state of knowledge, it seems to me that a lot of serial work is plausibly needed in order for us to understand how to safely and reliably aim AGI systems at a goal/task of our choosing.

，最明显的对齐工作案例 **对我来说** 是需要对思想/优化/任何东西有理论理解的工作，或者需要有正确的思维概念的工作。 相对于我们目前的知识水平，在我看来，为了让我们了解如何安全可靠地将 AGI 系统瞄准我们选择的目标/任务，似乎需要大量的系列工作。

A bunch of modern alignment work seems to me to sit in some middle-ground. As a rule of thumb, alignment work that is closer to behavioral observations of modern systems is more parallelizable (because you can have lots of people making those observations in parallel), and alignment work that requires having a good conceptual or theoretical framework is more serial (because, in the worst case, you might need a whole new generation of researchers raised with a half-baked version of the technical framework, in order to get people who both have enough technical clarity to grapple with the remaining confusions, and enough youth to invent a whole new way of seeing the problem—a pattern which seems common to me in my read of the development of things like analysis, meta-mathematics, quantum physics, etc.).

在我看来，一堆现代对齐工作处于中间位置。 根据经验，更接近现代系统行为观察的对齐工作更可并行化（因为你可以让很多人并行进行这些观察），而需要良好概念或理论框架的对齐工作更具串行性（因为，在最坏的情况下，你可能需要用半生不熟的技术框架培养新一代的研究人员，以便让既有足够的技术清晰度来解决剩余的困惑的人，也有足够的年轻人发明一种全新的看待问题的方式——在我阅读分析、元数学、量子物理学等事物的发展时，这种模式对我来说似乎很常见）。

As an egregious and fictitious (but "based on a true story") example of the arguments I disagree with, consider the following dialog:

作为我不同意的论点的一个令人震惊和虚构的（但“基于真实故事”）示例，请考虑以下对话：

___

**Uncharacteristically conscientious capabilities researcher:** Alignment is made significantly trickier by the fact that we do not have an artificial mind in front of us to study. By doing capabilities research now (and being personally willing to pause when we get to the brink), I am making it more possible to do alignment research.

**一反常态的认真能力研究员：** 由于我们面前没有人工思维可供研究，因此对齐变得更加棘手。 通过现在进行能力研究（并且个人愿意在我们走到边缘时停下来），我正在使进行一致性研究变得更有可能。

**Me:** Once humanity gets to the brink, I doubt we have much time left. (For a host of reasons, including: simultaneous discovery; the way the field seems to be on a trajectory to publicly share most of the critical AGI insights, once it has them, before wisening up and instituting closure policies after it's too late; Earth's generally terrible track-record in cybersecurity; and a sense that excited people will convince themselves it's fine to plow ahead directly over the cliff-edge.)

**我：** 一旦人类走到了边缘，我怀疑我们还有多少时间。 （出于多种原因，包括：同时发现；该领域似乎正处于公开分享大多数关键 AGI 见解的轨道上，一旦有了它们，在为时已晚之后明智地制定关闭政策之前；地球的通常在网络安全方面的糟糕记录；以及一种兴奋的人会说服自己直接翻过悬崖边缘的感觉。）

**Uncharacteristically conscientious capabilities researcher:** Well, we might not have many _sidereal_ years left after we get to the brink, but we'll have many, _many_ more _researcher_ years left. The top minds of the day will predictably be much more interested in alignment work when there's an actual misaligned artificial mind in front of them to study. And people will take these problems much more seriously once they're near-term. And the monetary incentives for solving alignment will be much more visibly present. And so on and so forth.

**一反常态的尽职尽责的能力研究员：** 好吧，在我们走到边缘之后，我们可能没有多少 _恒星_ 年了，但我们还有很多 _研究_ 很多 _年_ 。 当他们面前有一个真正错位的人工思维需要研究时，可以预见的是，当今的顶尖人才会对对齐工作更感兴趣。 一旦这些问题临近，人们就会更加认真地对待这些问题。 解决结盟问题的货币激励措施将更加明显。 等等等等。

**Me:** Setting aside how I believe that the world is derpier than that: even if you were right, I still think we'd be screwed in that scenario. In particular, that scenario seems to me to assume that there is not much serial research labor needed to do alignment research.

**我：** 抛开我如何相信世界比那更愚蠢：即使你是对的，我仍然认为我们会在那种情况下被搞砸。 特别是，在我看来，这种情况似乎假设进行对齐研究不需要太多的连续研究工作。

Like, I think it's quite hard to get something akin to Einstein's theory of general relativity, or Grothendieck's simplification of algebraic geometry, without having some researcher retreat to a mountain lair for a handful of years to build/refactor/distill/reimagine a bunch of the relevant concepts.

就像，我认为很难得到类似于爱因斯坦的广义相对论或格洛腾迪克对代数几何的简化的东西，而不是让一些研究人员撤退到山上的巢穴几年来构建/重构/提炼/重新想象一堆相关概念。

And looking at various parts of the history of math and science, it looks to me like technical fields often move forwards by building up around subtly-bad framings and concepts, so that a next generation can be raised with enough technical machinery to grasp the problem and enough youth to find a whole new angle of attack, at which point new and better framings and concepts are invented to replace the old. "A new scientific truth does not triumph by convincing its opponents and making them see the light, but rather because its opponents eventually die and a new generation grows up that is familiar with it" (Max Planck) and all that.

纵观数学和科学史的各个部分，在我看来，技术领域往往通过围绕微妙的错误框架和概念而向前发展，这样下一代就可以用足够的技术机制来解决问题和足够多的年轻人找到一个全新的攻击角度，在这一点上发明了新的更好的框架和概念来取代旧的。 “一个新的科学真理不会通过说服它的反对者并让他们看到光明而取得胜利，而是因为它的反对者最终会死去，而新一代熟悉它的人会成长起来”（马克斯·普朗克）等等。

If you need the field to iterate in that sort of way three times before you can see clearly enough to solve alignment, you're going to be hard-pressed to do that in five years no matter how big and important your field seems once you get to the brink.

如果你需要这个领域以这种方式迭代三次才能清楚地看到对齐问题，那么无论你的领域看起来多么大和重要，你都很难在五年内做到这一点。走到边缘。

(Even the 25 years in the toy model above feels pretty fast, to me, for that kind of iteration, and signifies my great optimism in what humanity is capable of doing in a rush when the whole universe is on the line.)

（即使是上面玩具模型中的 25 年，对我来说，对于这种迭代来说，也感觉相当快，这表明我非常乐观地认为，当整个宇宙都处于危险之中时，人类能够匆忙地做些什么。）

___

It looks to me like alignment requires both a bunch of parallelizable labor and a bunch of serial labor. I expect us to have very little serial time (a handful of years if we're lucky) after we have fledgling AGI.

在我看来，对齐既需要一堆可并行的工作，也需要一堆串行的工作。 我希望在我们拥有初出茅庐的 AGI 之后，我们的连续时间非常短（如果幸运的话，只有几年）。

When I've heard the “two units of alignment progress for one unit of capabilities progress” argument, my impression is that it's been made by people who are burning _serial_ time in order to get a bit more of the _parallelizable_ alignment labor done.

当我听到“一个单位的能力进步的两个单位的对齐进度”论点时，我的印象是，它是由那些正在燃烧 _串行_ 时间以完成更多可 _并行化_ 对齐工作的人做出的。

But the parallelizable alignment labor is not the bottleneck. The serial alignment labor is the bottleneck, and it looks to me like burning time to complete _that_ is nowhere near worth the benefits in practice.

但可并行化的对齐工作并不是瓶颈。 串行对齐工作是瓶颈，在我看来，完成 _这些_ 工作需要花费大量时间，这与实践中的好处相去甚远。

___

Some nuance I'll add:

我将添加一些细微差别：

I feel relatively confident that a large percentage of people who do capabilities work at OpenAI, FAIR, DeepMind, Anthropic, etc. with justifications like "well, I'm helping with alignment some too" or "well, alignment will be easier when we get to the brink" (more often EA-adjacent than centrally "EA", I think) are currently producing costs that outweigh the benefits.

我相对有信心，大部分从事能力工作的人在 OpenAI、FAIR、DeepMind、Anthropic 等公司工作，他们的理由是“好吧，我也在帮助一些对齐”或“好吧，当我们对齐时，对齐会更容易”走到边缘”（我认为，通常是与 EA 相邻，而不是位于中心的“EA”）目前产生的成本超过了收益。

Some relatively niche and theoretical agent-foundations-ish research directions might yield capabilities advances too, and I feel much more positive about those cases. I’m guessing it won’t _work_, but it’s the kind of research that seems positive-EV to me and that I’d like to see a larger network of researchers tackling, provided that they avoid publishing large advances that are especially likely to shorten AGI timelines.

一些相对小众和理论代理基础的研究方向也可能会产生能力进步，我对这些案例感到更加积极。 我猜它不会 _起作用_ ，但这种研究对我来说似乎是积极的 EV，我希望看到更大的研究人员网络来解决这个问题，前提是他们避免发表特别有可能缩短 AGI 时间线。

The main reasons I feel more positive about the agent-foundations-ish cases I know about are:

我对我所知道的类似代理基金会的案例感到更积极的主要原因是：

-   The alignment progress in these cases appears to me to be much more serial, compared to the vast majority of alignment work the field outputs today.
-   与当今现场输出的绝大多数对齐工作相比，这些案例中的对齐进度在我看来更为连续。
-   I’m more optimistic about the _total amount_ of alignment progress we’d see in the worlds where agent-foundations-ish research so wildly exceeded my expectations that it ended up boosting capabilities. Better understanding optimization in this way really would seem to me to take a significant bite out of the [capabilities generalization problem](https://www.lesswrong.com/posts/GNhMPAWcfBCASy8e6/a-central-ai-alignment-problem-capabilities-generalization), unlike [most alignment work I’m aware of](https://www.lesswrong.com/s/v55BhXbpJuaExkpcD/p/3pinFH3jerMzAvmza).
-   更加乐观 _总量_ 我对我们在 agent-foundations-ish 研究如此疯狂地超出我的预期以致最终提高能力的世界中看到的对齐进展 以这种方式更好地理解优化在我看来确实可以 [解决能力泛化问题](https://www.lesswrong.com/posts/GNhMPAWcfBCASy8e6/a-central-ai-alignment-problem-capabilities-generalization) 不同， [。 与我所知道的大多数对齐工作](https://www.lesswrong.com/s/v55BhXbpJuaExkpcD/p/3pinFH3jerMzAvmza) 。
-   The kind of people working on agent-foundations-y work aren’t publishing new ML results that break SotA. Thus I consider it more likely that they’d avoid publicly breaking SotA on a bunch of AGI-relevant benchmarks given the opportunity, and more likely that they’d only direct their attention to this kind of intervention if it seemed helpful for humanity’s future prospects.<sup><span><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fn242z44gs8ysh">[1]</a></span></span></sup>
-   从事 agent-foundations-y 工作的人不会发布破坏 SotA 的新 ML 结果。 因此，我认为，如果有机会，他们更有可能避免在一系列与 AGI 相关的基准测试中公开破坏 SotA，而且更有可能的是，如果这种干预对人类的未来前景有帮助，他们只会将注意力转移到这种干预上. <sup><span><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fn242z44gs8ysh"><span>[1]</span></a></span></span></sup>
-   Relatedly, the energy and attention of ML is elsewhere, so if they do achieve a surprising AGI-relevant breakthrough and accidentally leak bits about it publicly, I put less probability on safety-unconscious ML researchers rushing to incorporate it.
-   相关地，ML 的能量和注意力在别处，所以如果他们确实取得了令人惊讶的 AGI 相关突破并不小心公开泄露了一些信息，我认为没有安全意识的 ML 研究人员急于将其纳入其中的可能性较小。

I’m giving this example not to say “everyone should go do agent-foundations-y work exclusively now!”. I think it’s a neglected set of research directions that deserves far more effort, but I’m [far too pessimistic about it](https://www.lesswrong.com/s/v55BhXbpJuaExkpcD/p/3pinFH3jerMzAvmza#What_about_other_MIRI_people_) to want humanity to put all its eggs in that basket.

我举这个例子并不是说“现在每个人都应该专门去做 agent-foundations-y 工作！”。 我认为这是一组被忽视的研究方向，值得付出更多的努力，但我对此 [过于悲观，](https://www.lesswrong.com/s/v55BhXbpJuaExkpcD/p/3pinFH3jerMzAvmza#What_about_other_MIRI_people_) 不希望人类把所有的鸡蛋都放在那个篮子里。

Rather, my hope is that this example clarifies that I’m not saying “doing alignment research is bad” or even “all alignment research that poses a risk of advancing capabilities is bad”. I think that in a large majority of scenarios where humanity’s long-term future goes well, it mainly goes well because we made major alignment progress over the coming years and decades.<sup><span><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fnddvfphbtn7">[2]</a></span></span></sup> I don’t want this post to be taken as an argument against what I see as humanity’s biggest hope: figuring out AGI alignment.

相反，我希望这个例子能澄清我并不是说“做对齐研究是不好的”或者甚至“所有会带来提升能力风险的对齐研究都是不好的”。 我认为，在人类长期未来发展顺利的大多数情况下，它之所以进展顺利，主要是因为我们在未来几年和几十年取得了重大的协调进展。 <sup><span><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fnddvfphbtn7"><span>[2] </span></a></span></span></sup> 我不希望这篇文章被视为反对我认为人类最大希望的论点：找出 AGI 对齐方式。

1.  <sup><strong><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fnref242z44gs8ysh">^</a></span></strong></sup>
    
    On the other hand, weirder research is more likely to shorten timelines a _lot_, if it shortens them at all. More mainstream research progress is less likely to have a large counterfactual impact, because it’s more likely that someone else has the same idea a few months or years later.
    
    “Low probability of shortening timelines a lot” and “higher probability of shortening timelines a smaller amount” both matter here, so I advocate that both niche and mainstream researchers be cautious and deliberate about publishing potentially timelines-shortening work.
    
2.  <sup><strong><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fnrefddvfphbtn7">^</a></span></strong></sup>
    
    "Decades" would require timelines to be longer than my median. But when I condition on success, I do expect we have more time.
    

1.  <sup><strong><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fnref242z44gs8ysh"><span>^</span></a></span></strong></sup>
    
    另一方面，更奇怪的研究更有可能大大缩短时间线 _，_ 如果它能缩短时间线的话。 更主流的研究进展不太可能产生大的反事实影响，因为几个月或几年后其他人更有可能有同样的想法。
    
    “大大缩短时间线的可能性很小”和“缩短时间线的可能性较小”在这里都很重要，所以我主张小众和主流研究人员在发表可能缩短时间线的工作时都要谨慎和慎重。
    
2.  <sup><strong><span><a href="https://www.lesswrong.com/posts/vQNJrJqebXEWjJfnz/a-note-about-differential-technological-development#fnrefddvfphbtn7"><span>^</span></a></span></strong></sup>
    
    “几十年”需要时间线比我的中位数更长。 但当我以成功为条件时，我确实希望我们有更多时间。
    