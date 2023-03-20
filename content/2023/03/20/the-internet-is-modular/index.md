---
title: "互联网是模块化的"
date: 2023-03-20T17:38:01+08:00
updated: 2023-03-20T17:38:01+08:00
taxonomies:
  tags: []
extra:
  source: https://subconscious.substack.com/p/modularity
  hostname: subconscious.substack.com
  author: Gordon Brander
  original_title: "The internet is modular"
  original_lang: en
---

Sometimes you can gain fresh perspective walking back through familiar first principles. I had this experience recently after taking [a pilgrimage to MIT Press Bookstore](https://twitter.com/gordonbrander/status/1511036483112607744) and discovering Barbara van Schewick’s [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).  

有时，你可以从熟悉的第一原则中获得新的视角。最近，我在去麻省理工学院出版社的书店朝圣后，发现了芭芭拉-范-谢威克的《互联网架构与创新》，就有了这种体验。

[![Image](https3A2F2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com2Fpublic2Fimages2F1d3063c1-744d-488d-a3e0-5e1eb22ba9a8_1536x2048.jpeg "Image")](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1d3063c1-744d-488d-a3e0-5e1eb22ba9a8_1536x2048.jpeg)

[![](https3A2F2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com2Fpublic2Fimages2F85c1d271-0918-4b43-b022-74196a321858_3024x4032.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F85c1d271-0918-4b43-b022-74196a321858_3024x4032.jpeg)

The gist of the book is that there are specific reasons why the internet is so generative, and they can be mapped back to architectural choices made early in its history.  

It’s an important book if you want to [build new weblike things](https://subconscious.substack.com/p/weblike-things?s=w).  

这本书的主要内容是，互联网之所以如此具有生成性，是有具体原因的，而且可以追溯到其历史上早期的架构选择。如果你想建立类似网络的新事物，这是一本重要的书。

One of the key architectural principles of the internet is **modularity**. van Schewick devotes the opening chapters to it. What is modularity? How does it work? Why does it matter?  

互联网的关键架构原则之一是模块化。 范-谢威克在开篇的几章中专门讨论了这个问题。什么是模块性？它是如何工作的？它为什么重要？

If you work in software, modularity is one of those concepts that is so familiar it might seem banal.  

But this book has been prompting me to slow down, reflect on modularity, and try to see it again with [beginner’s mind](https://en.wikipedia.org/wiki/Shoshin).  

如果你从事软件工作，模块化是那些熟悉到可能看起来很平庸的概念之一。但这本书一直在促使我放慢脚步，反思模块化，并尝试以初学者的心态重新看待它。

> Modularity is a design principle that intentionally makes components highly independent (“loosely coupled”).  
> 
> 模块化是一个设计原则，它有意使组件高度独立（"松散耦合"）。  
> 
> _(Barbara van Schewick, 2010. [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).)  
> 
> (Barbara van Schewick, 2010. 互联网架构和创新。)_

A system is modular when it is made up of smaller independent parts with identifiable boundaries.  

当一个系统是由具有可识别边界的较小的独立部分组成时，它就是模块化。

> When designing a modular architecture, system architects decompose the system in a way that minimizes dependencies among components.  
> 
> 在设计模块化架构时，系统架构师以最小化组件之间的依赖性的方式来分解系统。  
> 
> _(Barbara van Schewick, 2010. [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).)  
> 
> (Barbara van Schewick, 2010. 互联网架构和创新。)_

A modular system can be decomposed and recomposed from component parts. In fact, the mathematical term for formally-pure modularity is _[compositionality](https://plato.stanford.edu/entries/compositionality/)_ — the property of being composable.  

一个模块化系统可以从组件中分解和重新组合。事实上，形式上纯粹的模块化的数学术语是组合性--可组合的属性。

How do you tell if a system is modularized? The key test is if pieces can be added, removed, modified, or swapped without changing other pieces.  

如何判断一个系统是否是模块化的？关键的测试是，是否可以在不改变其他部件的情况下增加、移除、修改或交换部件。

> If a product is modular in design, its components can be designed independently. If it is modular in production, its components can be produced independently.  
> 
> If it is modular in use, users of the product can replace or “mix and match” components at a later stage.  
> 
> 如果一个产品在设计上是模块化的，它的部件就可以独立设计。如果它在生产上是模块化的，它的部件就可以独立生产。如果它在使用上是模块化的，产品的用户可以在以后的阶段更换或 "混合和匹配 "组件。  
> 
> _(Barbara van Schewick, 2010. [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).)  
> 
> (Barbara van Schewick, 2010. 互联网架构和创新。)_

So a modular system is made up of independent parts. But these parts need some way to talk if we’re going to compose them into a system.  

因此，一个模块化系统是由独立的部分组成的。但是，如果我们要把这些部件组成一个系统，这些部件需要某种方式来交谈。

> To make components independent, and to maintain their independence, modularity employs abstraction, information hiding, and a strict separation of concerns.  
> 
> 为了使组件独立，并保持其独立性，模块化采用了抽象化、信息隐藏和严格的关注点分离。
> 
> A modular approach to design distinguishes between two types of information.  
> 
> 模块化的设计方法对两种类型的信息进行了区分。  
> 
> Information that is relevant to more than one module is completely specified as part of the architectural design process and is not allowed to change during detailed design.  
> 
> 与一个以上模块相关的信息作为建筑设计过程的一部分被完全指定，在详细设计期间不允许改变。  
> 
> This information is available or “visible” to all designers, and is therefore called the architecture’s visible information.  
> 
> 这些信息对所有设计者都是可用的或 "可见的"，因此被称为建筑的可见信息。  
> 
> In particular, this includes all the information modules need to work together, such as the information necessary to use a module or otherwise interact with it.  
> 
> 特别是，这包括所有模块需要一起工作的信息，如使用一个模块或以其他方式与之互动的必要信息。  
> 
> For each module, this information is completely defined in detailed interface specifications that describe all the interdependencies or points of interaction between that module and other modules and specify how they will be resolved.  
> 
> 对于每个模块，这些信息在详细的接口规范中被完全定义，这些规范描述了该模块与其他模块之间的所有相互依存关系或互动点，并规定了它们将如何被解决。  
> 
> Thus, a module’s visible information provides an external view of the module that lets other designers treat the module as a black box, letting them abstract from the complexity of the module.  
> 
> 因此，一个模块的可见信息提供了一个模块的外部视图，让其他设计者把这个模块当作一个黑盒子，让他们从模块的复杂性中抽象出来。
> 
> _(Barbara van Schewick, 2010. [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).)  
> 
> (Barbara van Schewick, 2010. 互联网架构和创新。)_

How modules talk to each other must be carefully specified to maintain independence. For example, lego rigorously defines the interface between pieces (“the dot”). If they didn’t, [each piece would have to make up its own mind about the kind of connector it should present](https://subconscious.substack.com/p/composability-with-other-tools?s=w#:~:text=One%2Doff%20API%20integration%20doesn%E2%80%99t%20scale). Many pieces wouldn’t click together. Those that did would have to know about the shapes of other pieces, and design their connectors around those specific pieces.  

The pieces would no longer be independent.  

模块之间的对话方式必须被仔细指定，以保持独立性。例如，乐高严格地定义了部件之间的接口（"点"）。如果不这样做，每一块都必须自己决定它应该呈现什么样的连接器。许多碎片就不会连接在一起。而那些有的则必须了解其他棋子的形状，并围绕这些特定的棋子来设计它们的连接器。这些棋子将不再是独立的。

> Clearly interfaces are a crucial aspect of compositionality, and I suspect that interfaces are in fact synonymous with compositionality.  
> 
> That is, compositionality is not just the ability to compose objects, but the ability to work with an object after intentionally forgetting how it was built.  
> 
> The part that is remembered is the “interface”, which may be a type, or a contract, or some other high-level description.  
> 
> 显然，接口是组合性的一个重要方面，我怀疑接口实际上是组合性的同义词。也就是说，组合性不仅仅是对对象进行组合的能力，而且是在有意忘记对象是如何被构建的情况下对其进行处理的能力。被记住的部分是 "接口"，它可能是一个类型，或者一个契约，或者其他一些高级描述。  
> 
> _(Jules Hedges, [On Compositionality](https://julesh.com/2017/04/22/on-compositionality/))  
> 
> (朱尔斯-赫奇斯，《论构成性》)_

Interfaces go by many names: APIs, protocols, function signatures, contracts, etiquette, lego dots. Regardless, the design of the interface is pivotal to the success or failure of a modular system.  

The modular interface is the grammar that defines the [expressive potential](https://subconscious.substack.com/p/possibility-space?s=w) of the [system alphabet](https://subconscious.substack.com/p/provoking-emergence-with-alphabets?s=w).  

接口有很多名字。API、协议、函数签名、合同、礼节、乐高点。不管怎么说，接口的设计对于模块化系统的成败是至关重要的。模块化接口是定义系统字母表的表达潜力的语法。

> …information that affects only one module—the inside of the black box—is hidden from everyone except its designers; it is called the architecture’s hidden information.  
> 
> This information is not specified during the design of the architecture, but is determined during the detailed design phase; it is free to evolve within the framework provided by the architecture’s visible information until the detailed designing ends.  
> 
> ......只影响一个模块的信息--黑盒子的内部--对除了设计者之外的所有人都是隐藏的；它被称为架构的隐藏信息。这些信息在架构的设计过程中没有被指定，而是在详细设计阶段被确定；它可以在架构的可见信息所提供的框架内自由发展，直到详细设计结束。  
> 
> _(Barbara van Schewick, 2010. [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).)  
> 
> (Barbara van Schewick, 2010. 互联网架构和创新。)_

Because modules are black boxes, you can change anything within the module, provided it doesn’t change the interface.  

因为模块是黑盒子，你可以改变模块内的任何东西，只要不改变界面。  

Modules give you the freedom to rapidly evolve the internals of a system without breaking any functionality.  

模块让你可以在不破坏任何功能的情况下，快速发展系统的内部结构。

…On the flip side, the module interface cannot evolve quickly, or the system would break.  

......反过来说，模块接口不能快速发展，否则系统会崩溃。

> Modularity is not without costs. An architecture’s visible information is not allowed to change during detailed design and is difficult to change later.  
> 
> Thus, modularity makes it more difficult to experiment on the architecture’s visible information (such as a module’s interfaces) in order to facilitate experimentation on the architecture’s hidden information (such as a module’s internals).  
> 
> In a way, the inflexibility of the visible information is the price for the flexibility with respect to the architecture’s hidden information.  
> 
> 模块化并不是没有代价的。一个架构的可见信息在详细的设计过程中是不允许改变的，而且以后也很难改变。因此，模块化使得在架构的可见信息（如模块的接口）上进行实验更加困难，以便于在架构的隐藏信息（如模块的内部结构）上进行实验。在某种程度上，可见信息的不灵活是对架构隐藏信息的灵活的代价。  
> 
> _(Barbara van Schewick, 2010. [Internet Architecture and Innovation](https://mitpress.mit.edu/books/internet-architecture-and-innovation).)  
> 
> (Barbara van Schewick, 2010. 互联网架构和创新。)_

> A protocol moves much more slowly than a platform. After 30+ years, email is still unencrypted; meanwhile WhatsApp went from unencrypted to full e2ee in a year.  
> 
> People are still trying to standardize sharing a video reliably over IRC; meanwhile, Slack lets you create custom reaction emoji based on your face. This isn’t a funding issue.  
> 
> If something is truly decentralized, it becomes very difficult to change, and often remains stuck in time.  
> 
> 协议的发展要比平台慢得多。30多年后，电子邮件仍然是未加密的；同时，WhatsApp在一年内从未加密到完全e2ee。人们仍在努力使通过IRC可靠地分享视频标准化；与此同时，Slack让你根据你的脸创建自定义的反应表情符号。这并不是一个资金问题。如果一个东西是真正的去中心化，它就会变得非常难以改变，而且经常停留在时间上。  
> 
> _(Moxie Marlinspike, 2022. [_Web3_ First Impressions](https://moxie.org/2022/01/07/web3-first-impressions.html).)  
> 
> (Moxie Marlinspike，2022年。_Web3_第一印象。)_

This presents us with a dilemma: it is crucial to draw the boundaries of modularity in the right place.  

这就给我们提出了一个难题：在正确的地方划定模块化的界限是至关重要的。  

The boundaries of modularity determine which parts of the system can evolve rapidly, and which will be frozen in time. Draw the lines in the wrong place, and you’ll be stuck!  

模块化的边界决定了系统的哪些部分可以快速发展，哪些部分将被冻结在时间中。在错误的地方画线，你就会被卡住!

To some degree, we might understand the web’s performance problems through this lens.  

在某种程度上，我们可以通过这个角度理解网络的性能问题。  

The modular boundaries of the web were drawn for networked documents, with content split into “pages”, and browser engines designed to lay out and scroll text.  

网络的模块化边界是为网络化的文件绘制的，内容被分割成 "页面"，浏览器引擎被设计用于布局和滚动文本。

As the basis of competition shifted appward, we found that the modular boundaries which had been drawn for docs were in the wrong place for apps!  

There are hard modular boundaries between pages, so we write [single-page apps](https://developer.mozilla.org/en-US/docs/Glossary/SPA) to hide them. The layout model of the web can reflow massive amounts of text, but this becomes [a liability for animation](https://gist.github.com/paulirish/5d52fb081b3570c81e3a), so we avoid it. Particular layout modules and and APIs make the web near impossible to parallelize.  

随着竞争的基础向应用程序转移，我们发现为文档划定的模块化边界对应用程序来说是错误的！在页面之间有硬性的模块化边界，所以我们写单页应用程序来隐藏它们。页面之间有硬性的模块化边界，所以我们编写单页应用程序来隐藏它们。网络的布局模型可以对大量的文本进行回流，但这对动画来说是一种负担，所以我们避免了这一点。特定的布局模块和API使得网络几乎不可能被并行化。

But the interface boundaries of the web have been drawn. We’re stuck with them now. The only way forward is to muddle through, with occasional heroic (or dastardly) feats of engineering.  

但网络的界面边界已经被划定。我们现在被它们困住了。前进的唯一途径是通过偶尔的英雄（或卑鄙的）工程壮举来蒙混过关。

You could see something like [Mighty](https://www.mightyapp.com/) as an attempt to redraw modular boundaries by putting all of the modules of the browser engine into a black box, and throwing computing power at that black box until the only module boundary that matters is the network boundary between client and server.  

你可以把像Mighty这样的东西看作是重新划定模块边界的尝试，把浏览器引擎的所有模块放到一个黑盒子里，并把计算能力投向这个黑盒子，直到唯一重要的模块边界是客户端和服务器之间的网络边界。

The cost of interfaces is also why “modularize all the things” can be a mistake. It proliferates interfaces, and limits your ability to rapidly evolve a system.  

接口的成本也是为什么 "把所有的东西都模块化 "会是一个错误。它增加了接口，并限制了你快速发展系统的能力。  

Big black boxes can create space for innovation.  

大黑盒子可以为创新创造空间。

What to modularize is a design problem with no easy answers, and the right boundaries depend upon goals, values, and co-evolutionary fit within the larger environment.  

什么是模块化是一个没有简单答案的设计问题，正确的边界取决于目标、价值和在大环境中的共同进化适应性。

> I know you think it's idealistic but evolution only builds on open formats and protocols. That's how technology layers.  
> 
> 我知道你认为这很理想化，但进化只建立在开放的格式和协议上。这就是技术的层次。  
> 
> _(Dave Winer, 2014. [Young Technologists Love Lockin?](http://scripting.com/2014/10/10/youngTechnologistsLoveLockin.html))_

Modules allow us to cordon off parts of a system so that they can evolve quickly, but they are also the mechanism by which the system itself evolves.  

模块使我们能够封锁系统的某些部分，以便它们能够快速演化，但它们也是系统本身演化的机制。

Long before DNA was discovered, it was known that the mechanism of heredity behind biological evolution must be digital, countable, modular. Why? Evolution happens in any system with [mutation, heredity, selection](https://gordonbrander.com/pattern/evolution), and you can’t have mutation unless it is possible to add and remove parts—modularity! So, modularity is a key attribute of evolving systems.  

早在DNA被发现之前，人们就知道，生物进化背后的遗传机制必须是数字化的、可计算的、模块化的。为什么？进化发生在任何系统中，有突变、遗传、选择，除非有可能添加和删除部分--模块化！否则你不可能有突变。所以，模块化是进化系统的一个关键属性。

In [The Nature of Technology](https://www.amazon.com/Nature-Technology-What-How-Evolves/dp/1416544062), W. Brian Arthur notes that modular technology has all of these properties too!  

在《技术的本质》中，W.Brian Arthur指出，模块化技术也具有所有这些特性

Mutation ← Changing or replacing modules  

突变 ← 改变或替换模块  

Heredity ← Composing new modules from old  

遗传 ← 从旧的模块组成新的模块  

Selection ← Usefulness  

选择 ← 有用性

Technology evolves. New technologies are composed recursively from old modules, then become modules in turn. Modules are like genes for invention.  

技术在不断发展。新技术是由旧模块递归组成的，然后反过来成为模块。模块就像发明的基因。

> Technology, once a means of production, is becoming a chemistry.  
> 
> We are shifting from technologies that produce fixed physical outputs to technologies whose main character is that they can be combined endlessly for fresh purposes.  
> 
> 技术，曾经是一种生产手段，正在成为一种化学反应。我们正在从产生固定物理产出的技术转向技术，其主要特征是它们可以为新的目的无休止地组合。  
> 
> _(W. Brian Arthur, 2009. [The Nature of Technology](https://sites.santafe.edu/~wbarthur/thenatureoftechnology.htm))  
> 
> (W. Brian Arthur, 2009. 技术的本质)_

If you want to create [open-ended systems](https://subconscious.substack.com/p/open-ended-tools-for-infinite-games?s=w), you need modularity.  

如果你想创建开放式的系统，你需要模块化。

Here are some questions I am asking myself as I reflect on modularity…  

以下是我在反思模块化时问自己的一些问题......

**What aspects of Subconscious should be black boxes?** What aspects of the tools for thought space is undergoing rapid evolution? What parts of the system need the freedom to experiment? In what ways might this change as the space matures?  

潜意识的哪些方面应该是黑箱？思想空间的工具的哪些方面正在经历快速的演变？系统的哪些部分需要自由实验？随着空间的成熟，这可能在哪些方面发生变化？

**Where should we present protocols?** What parts of the tools for thought space are well-understood? In what areas is it ok to evolve slowly? In what ways might this change as the space matures?  

我们应该在哪里提出协议？思想空间的工具的哪些部分是被充分理解的？在哪些领域可以缓慢发展？随着空间的成熟，这可能在哪些方面发生变化？

**Markup is a protocol, whether specified or not**. This is unavoidable. Even if your app doesn’t interface with other apps, it still talks with the rest of the world through copy/paste.  

标记是一种协议，无论是否指定。这一点是不可避免的。即使你的应用程序不与其他应用程序对接，它仍然通过复制/粘贴与世界其他地方对话。

We want markup to present an interface that is useful for many different modules. This is my motivation behind [Subtext](https://github.com/gordonbrander/subtext), a plain text format with markdownish flavors that easily parses to a flat list of blocks.  

我们希望标记能呈现一个对许多不同模块都有用的界面。这就是我在Subtext背后的动机，一种带有markdown味道的纯文本格式，可以很容易地解析为一个平面的块列表。

**Data formats are a protocol**, whether specified or not. This is one reason we’ve been prioritizing [Lindy](https://en.wikipedia.org/wiki/Lindy_effect) formats like plain text. They [compose well with other tools](https://subconscious.substack.com/p/composability-with-other-tools?s=w).  

数据格式是一种协议，无论是否指定。这就是我们一直优先考虑像纯文本这样的林迪格式的原因之一。它们能很好地与其他工具进行组合。
