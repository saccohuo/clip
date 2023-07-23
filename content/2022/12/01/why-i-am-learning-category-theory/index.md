---
title: "我为什么学习范畴论"
date: 2022-12-01T22:56:39+08:00
updated: 2022-12-01T22:56:39+08:00
taxonomies:
  tags: []
extra:
  source: https://the.scapegoat.dev/why-i-am-learning-category-theory-1/
  hostname: the.scapegoat.dev
  author: 
  original_title: "Why I am learning category theory"
  original_lang: en
---

Category theory is a domain of mathematics that exerts a strange influence over programmers. One thing that can be said for sure about category theory is that it is highly abstract, and its relationship to software engineering is not immediately obvious. I consider myself to be more on the pragmatic side of software engineering, so **why did I set out to learn category theory beyond the few concepts popularized by functional programming?**

范畴论是对程序员产生奇怪影响的数学领域。 关于范畴论可以肯定地说的一件事是它是高度抽象的，它与软件工程的关系不是很明显。 我认为自己在软件工程方面更偏向于实用主义，那么 **为什么我要在函数式编程普及的少数概念之外开始学习范畴论呢？**

In particular, I have been following along [MIT 18.S097: Programming with Categories](http://brendanfong.com/programmingcats.html) and reading [Category Theory for Programmers](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/) by Bartosz Milewski along with a few books like Steve Awodey's [Category Theory](https://www.amazon.com/Category-Theory-Oxford-Logic-Guides/dp/0199237182) and [Seven Sketches in Compositionality](https://www.amazon.com/Invitation-Applied-Category-Theory-Compositionality/dp/1108711820/ref=d_bpx_wsirn_iabw_v1_sccl_2_1/144-6076266-4505621). I want to thank my fellow Recursers who are taking part in our category theory reading group, as I wouldn't have nearly as much fun as I have.

特别是，我一直在关注 [麻省理工学院 18.S097：使用类别编程](http://brendanfong.com/programmingcats.html) ，阅读 [Bartosz Milewski 的《面向程序员](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/) 》等几本书 [的类别理论》以及 Steve Awodey 的《类别理论》](https://www.amazon.com/Category-Theory-Oxford-Logic-Guides/dp/0199237182) 和 [《组合性七大草图](https://www.amazon.com/Invitation-Applied-Category-Theory-Compositionality/dp/1108711820/ref=d_bpx_wsirn_iabw_v1_sccl_2_1/144-6076266-4505621) 。 我要感谢参加我们范畴论阅读小组的 Recurs 同事，因为我不会像现在这样享受乐趣。

## My background in functional programming

## 我在函数式编程方面的背景

**My background is in systems programming**; I work mostly on embedded and full-stack web development. Having been a Common Lisp aficionado, I use a lot of functional programming patterns. Until recently, my knowledge of category theory was a set of applied patterns: functors, monoids, foldables, applicatives, and especially monads.

**我的背景是系统编程** ； 我主要从事嵌入式和全栈网络开发。 作为 Common Lisp 的狂热爱好者，我使用了很多函数式编程模式。 直到最近，我对范畴论的了解是一组应用模式：函子、幺半群、可折叠、应用，尤其是单子。

I rarely use these concepts explicitly, but they help me build software: I know when to fold a monoidal data structure, how to lift a functor into another, and how to use applicatives to validate data (if these sound abstract, that's because I wanted it to sound abstract. The programming itself is very pedestrian).

我很少明确使用这些概念，但它们帮助我构建软件：我知道何时折叠幺半群数据结构，如何将仿函数提升到另一个，以及如何使用应用程序来验证数据（如果这些听起来很抽象，那是因为我想要听起来很抽象。编程本身很乏味）。

Since I write mostly C++, PHP or Javascript, I use functions and simple data structures and don't go heavy on generics and type system magic. However, **because of its theoretical underpinnings, my code can (usually) be cleanly composed into larger structures.**

由于我主要编写 C++、PHP 或 Javascript，所以我使用函数和简单的数据结构，不会过多地使用泛型和类型系统魔法。 但是， **由于其理论基础，我的代码（通常）可以干净地组合成更大的结构。**

Yet, I always knew my approach to be a "pop-sci" version of category theory: I never bothered to look up the actual mathematical theory. The rare times I opened up a textbook, I was taken aback by millions of words I didn't know—I would look things up on Wikipedia or nlab and be utterly confused.

然而，我一直都知道我的方法是范畴论的“通俗科学”版本：我从不费心去查找实际的数学理论。 很少有几次我打开教科书，我会被数百万我不知道的单词吓到——我会在维基百科或 nlab 上查找内容，然后完全困惑。

My gut, however, was telling me that there was a lot of potential to be unlocked by delving deeper.

然而，我的直觉告诉我，通过更深入的研究可以释放很多潜力。

## Turning diagrams into code

## 将图表转化为代码

Since I was a kid, I have been fascinated with [diagrams](https://the.scapegoat.dev/diagrams/).

我从小就对 [图表](https://the.scapegoat.dev/diagrams/) 着迷。

Nowadays, **I write code by first drawing simple boxes and arrows and doodles, then iteratively transforming them into more formal constructs**. The drawings can represent time sequences, data structures, schema evolution, infrastructure, and state machines. At some point, the design is concrete enough that it can be turned into code.

现在， **我通过首先绘制简单的框、箭头和涂鸦来编写代码，然后将它们迭代地转换为更正式的结构** 。 绘图可以表示时间序列、数据结构、模式演变、基础设施和状态机。 在某些时候，设计足够具体，可以将其转化为代码。

**Using these diagrams made collaboration with engineers in other disciplines very effective.** For example, when drawing state machine diagrams and sequence diagrams, mechanical engineers I collaborated with were able to point out subtle race conditions, missed transitions, and faulty logic in my firmware.

**使用这些图表可以非常有效地与其他学科的工程师进行协作。** 例如，在绘制状态机图和序列图时，与我合作的机械工程师能够指出我的固件中微妙的竞争条件、错过的转换和错误的逻辑。

I "discovered" monads by trying really hard to encode the "arrows" of my state machines into more mundane programming languages like PHP or C++. It was a very autodidact approach, and I knew intuitively that there were formal ways of turning this visual approach to problem-solving into robust software.

我通过非常努力地将我的状态机的“箭头”编码成更普通的编程语言（如 PHP 或 C++）来“发现”monad。 这是一种非常自学的方法，我凭直觉知道有正式的方法可以将这种用于解决问题的视觉方法转化为健壮的软件。

It was only years later that I realized that I had been implementing monads all along. This was a deep moment of insight for me. It allowed me to reduce tricky programming problems (concurrency in embedded systems, transaction sequencing, and error handling in distributed systems) into a single, concise concept, along with almost trivial-looking code.

仅仅几年后，我才意识到我一直在实施 monad。 这对我来说是一个深刻的洞察力时刻。 它使我能够将棘手的编程问题（嵌入式系统中的并发性、事务排序和分布式系统中的错误处理）减少为一个简洁的概念，以及看起来几乎微不足道的代码。

Category theory is literally the mathematics of boxes (objects), arrows (morphisms), and composition. **Composition is how we build large software out of smaller parts while keeping complexity in check.** Boxes and arrows is also how humans think in other disciplines, which makes category theory a powerful tool for uncovering cross-disciplinary analogies.

范畴论实际上是盒子（对象）、箭头（态射）和组合的数学。 **组合是我们如何用较小的部分构建大型软件，同时控制复杂性。** 方框和箭头也是人类在其他学科中的思维方式，这使得范畴论成为揭示跨学科类比的有力工具。

## Putting words to my thinking

## 用文字表达我的想法

**I have always had an "expanding," holistic way of thinking about software systems.** Going back to software I wrote as a junior developer, like this [AVR Bluetooth Stack](https://github.com/wesen/avr-bt-stack), I wonder if I would write it any differently nowadays. My understanding of composition, naming, and components seem to already be fully formed, despite my inexperience (I only knew BASIC, assembly, and C when I wrote the above).

**I have always had an "expanding," holistic way of thinking about software systems.** Going back to software I wrote as a junior developer, like this [AVR Bluetooth Stack](https://github.com/wesen/avr-bt-stack), I wonder if I would write it any differently nowadays. My understanding of composition, naming, and components seem to already be fully formed, despite my inexperience (I only knew BASIC, assembly, and C when I wrote the above).

This holistic approach encompasses systems (the above stack runs on both the host and 8-bit microcontrollers, which wasn't a common pattern back in 2001), machine and human (I always try to think of the developer as an [actual user of the software they write](https://the.scapegoat.dev/you-the-developer-are-a-user-too/), code structure, runtime behavior, among other things. Of course, 18-year-old me didn't come up with these patterns out of the box, and they are influenced by the design of the Bluetooth specification, but the fact that I knew to recognize and apply them speaks to an innate sense of structure.

这种整体方法包括系统（上面的堆栈在主机和 8 位微控制器上运行，这在 2001 年不是一种常见模式）、机器和人（我总是试图将开发人员 [视为他们编写的软件](https://the.scapegoat.dev/you-the-developer-are-a-user-too/) 、代码结构、运行时行为等等。当然，18 岁的我并没有开箱即用地想出这些模式，它们受到蓝牙规范设计的影响，但是事实上，我知道如何识别和应用它们说明了一种与生俱来的结构感。

As described in the previous paragraph, I build software by drawing boxes and arrows first and refining them until I can encode them as software.

如前一段所述，我通过先绘制方框和箭头并完善它们来构建软件，直到我可以将它们编码为软件。

This structural approach encompasses much more than just code and data structures. I apply it to:

这种结构化方法不仅仅包含代码和数据结构。 我将它应用于：

-   product thinking
-   产品思维
-   communication structures
-   沟通结构
-   schema design and evolution (database design, data schema evolution)
-   schema design and evolution（数据库设计、数据模式演化）
-   logging and debugging (events, logging schema)
-   记录和调试（事件、记录模式）
-   runtime behavior (event loops, state machines, sequence diagrams)
-   运行时行为（事件循环、状态机、序列图）
-   module and codebase decoupling
-   模块和代码库解耦
-   software engineering workflow (git workflow, issues, and project management)
-   软件工程工作流程（git 工作流程、问题和项目管理）

Breaking things into boxes and arrows allows me to recognize commonalities across domains, so much so that I, for example, consider [web development to be the same as embedded development](https://the.scapegoat.dev/embedded-programming-is-like-web-development/). I thought this statement would be quite uncontroversial, but it turns out that I got a lot of pushback. The reason I consider the two to be similar, if not the same, is that I have been able to form abstractions that carry across from embedded development to web development. **An abstraction is a controlled form of forgetting the details to focus on something more fundamental, allowing one to make statements that are shorter to state yet broader in meaning.**

将事物分解成方框和箭头让我认识到跨领域的共性，以至于我，例如，认为 [网络开发与嵌入式开发相同](https://the.scapegoat.dev/embedded-programming-is-like-web-development/) 。 我原以为这个声明不会引起争议，但事实证明我遭到了很多反对。 我认为两者相似（如果不相同）的原因是我已经能够形成从嵌入式开发到 Web 开发的抽象。 **抽象是一种可控的形式，它会忘记细节以专注于更基本的事物，从而允许人们做出更简短但含义更广泛的陈述。**

Category theory is really the mathematics of composition, reducing everything it encounters to simple structures of objects and morphisms (boxes and arrows, really) and showing where they are similar and where they aren't based on how they can be composed. Once a system has been abstracted, that abstraction is abstracted: categories, functors, and monoids themselves form categories, which are yet more categories that can be put into relation with other categories.

范畴论实际上是组合的数学，将它遇到的一切都简化为对象和态射的简单结构（实际上是框和箭头），并根据它们的组合方式显示它们在哪里相似，在哪里不相似。 一旦一个系统被抽象出来，那个抽象就被抽象出来：范畴、函子和幺半群本身形成范畴，它们是更多的范畴，可以与其他范畴建立联系。

**I hope that category theory will allow me to formalize my intuitive understanding of abstraction, put words to it, and use those words (or, better, words others have written) to explain my thinking.** The hardest about abstraction is that it requires effort to form yet becomes trivial once understood. This leads to a myriad of confusing monad tutorials that assume that there is one easy way to form the mental chunk for that abstraction when really understanding monads about the repeated struggle to work with the concept until it finally clicks. Everybody's favorite monad tutorial is the third they worked through.

**我希望范畴论能让我形式化我对抽象的直觉理解，用文字表达它，并使用这些文字（或者，更好的是，其他人写的文字）来解释我的想法。** 抽象最难的地方在于，它需要付出努力才能形成，但一旦理解就会变得微不足道。 这导致了无数令人困惑的 monad 教程，这些教程假设在真正理解 monad 时，有一种简单的方法可以为该抽象形成心理块，直到它最终点击为止。 每个人最喜欢的 monad 教程是他们完成的第三个教程。

## Writing more expressive software

## 编写更具表现力的软件

Finally, I am seeing how learning about concepts I already had a good intuitive feel for (monoids, functors, ...) unlocks a whole new world of abstraction. I was swimming at the surface of seemingly simple concepts that actually have incredible depth, depths talented mathematicians have been studying for centuries. A good podcast about this is [corecursive's episode about portal abstractions with Sam Ritchie](https://corecursive.com/050-sam-ritchie-portal-abstractions-2/).

最后，我看到学习我已经有良好直觉的概念（幺半群、仿函数……）如何打开一个全新的抽象世界。 我在看似简单的概念表面游泳，但实际上具有令人难以置信的深度，有才华的数学家已经研究了几个世纪的深度。 关于这个的一个很好的播客是 [corecursive 与 Sam Ritchie 关于门户抽象的插曲](https://corecursive.com/050-sam-ritchie-portal-abstractions-2/) 。

While I already use a lot of these patterns when writing functional code, there is so much more to be gained from understanding monoids or functors as formulated in category theory language. I started recognizing them in schema migrations, database transactions, state transitions in embedded systems, wire protocols, etc.

虽然我在编写函数式代码时已经使用了很多这些模式，但通过理解范畴论语言中表述的幺半群或仿函数，我可以获得更多。 我开始在模式迁移、数据库事务、嵌入式系统中的状态转换、有线协议等中识别它们。

**While I rarely call my classes or functions or modules mathematical names (in fact, due to the messy imperative languages I tend to use, I often can't, as their type system is rarely powerful enough), my thinking is heavily inspired by the underlying mathematical concept**. That doesn't really matter much to me since writing verbose code due to not having programming language support doesn't impact the abstraction and its validity as such.

**虽然我很少给我的类或函数或模块起数学名称（事实上，由于我倾向于使用凌乱的命令式语言，我经常不能这样做，因为它们的类型系统很少足够强大），但我的想法在很大程度上受到了基本的数学概念** 。 这对我来说并不重要，因为由于没有编程语言支持而编写冗长的代码不会影响抽象及其有效性。

**The soundness of the abstractions unearthed by thinking about a domain in terms of category theory means that elegant, concise, and, most importantly, composable domain-specific languages can be designed.** This might be the most important result I get from learning more about mathematics. To me, a domain-specific language doesn't need to be an actual language but also encompasses API and protocol design.

**通过从类别理论的角度思考一个领域而挖掘出的抽象的健全性意味着可以设计优雅、简洁，最重要的是，可以设计可组合的领域特定语言。** 这可能是我从更多的数学知识中得到的最重要的结果。 对我来说，特定领域的语言不需要是实际的语言，还包括 API 和协议设计。

## A never-ending journey

## 永无止境的旅程

I am still at the very surface of category theory and just hit the first wall by working on F-algebras and recursion schemes. Yet, the value I got from sitting down and understanding functors, monoids, and adjunctions at a rigorous mathematical level, as well as working with the "actual" definition of categories, has already brought me a lot of confidence in my current approach to software design.

我仍然处于范畴论的最表面，并且刚刚通过研究 F 代数和递归方案触及了第一堵墙。 然而，我从严格的数学水平上坐下来理解函子、幺半群和附加，以及使用类别的“实际”定义，所获得的价值，已经让我对我目前的软件方法充满信心设计。

I couldn't be more excited about what is coming next.

我对接下来要发生的事情感到非常兴奋。
