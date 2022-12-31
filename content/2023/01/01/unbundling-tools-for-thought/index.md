---
title: "分解思维工具"
date: 2023-01-01T04:25:33+08:00
updated: 2023-01-01T04:25:33+08:00
taxonomies:
  tags: []
extra:
  source: https://borretti.me/article/unbundling-tools-for-thought
  hostname: borretti.me
  author: Fernando Borretti
  original_title: "Unbundling Tools for Thought"
  original_lang: en
---

Short version:

-   Tools for thought promise to let you centralize and hyperlink all your data.  
    思维工具有望让您集中和超链接所有数据。  
    
-   In practice 95% of the use cases can be naturally unbundled into disjoint apps, and the lack of centralization and cross-app hyperlinking has no real negative effects.
    
    在实践中，95% 的用例可以自然地分解为不相交的应用程序，并且缺乏集中化和跨应用程序超链接没有真正的负面影响。
    

There’s a joke in game development that there’s two kinds of game devs: those who write engines, and those who make games. The people who make the engines do it for the intellectual pleasure of discovering a beautiful algebra of vectors, scenes, entities, and events; and watching a beautiful, crystalline machine in operation. The actual game—which is never finished, rarely started—is an afterthought. Of course you wouldn’t make a _game_. That would be parochial. The engine was the point. People who want to make games just download Unity and push through the horror.

游戏开发中有一个笑话，游戏开发者分为两种：一种是编写引擎的，另一种是制作游戏的。制造引擎的人这样做是为了发现美丽的向量、场景、实体和事件代数的智力乐趣；看着一台漂亮的水晶机器在运转。真正的游戏——永远不会结束，也很少开始——是事后才想到的。你当然不会制作游戏。那将是狭隘的。引擎是重点。想要制作游戏的人只需下载 Unity 并度过难关。

I’ve written something like six or seven personal wikis over the past decade. It’s actually an incredibly advanced form of procrastination<sup id="fnref:college" role="doc-noteref"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:college" rel="footnote">1</a></sup>. At this point I’ve tried every possible design choice.

在过去的十年里，我写了大约六七个个人维基。这实际上是一种令人难以置信的高级拖延形式。在这一点上，我已经尝试了所有可能的设计选择。

1.  **Lifecycle:** I’ve built a few compiler-style wikis: plain-text files in a `git` repo statically compiled to HTML. I’ve built a couple using live servers with server-side rendering. The latest one is an API server with a React frontend.
    
2.  **Storage:** I started with plain text files in a git repo, then moved to an SQLite database with a simple schema. The latest version is an avant-garde object-oriented hypermedia database with bidirectional links implemented on top of SQLite.
    
    存储：我从 git 存储库中的纯文本文件开始，然后转移到具有简单模式的 SQLite 数据库。最新版本是一个前卫的面向对象的超媒体数据库，在 SQLite 之上实现了双向链接。
    
3.  **Markup:** I used Markdown here and there. Then I built my own [TeX-inspired markup language](https://github.com/eudoxia0/concordia). Then I tried XML, with mixed results. The latest version uses a WYSIWYG editor made with [ProseMirror](https://prosemirror.net/).
    
    标记：我到处都使用 Markdown。然后我构建了自己的受 TeX 启发的标记语言。然后我尝试了 XML，结果好坏参半。最新版本使用由 ProseMirror 制作的 WYSIWYG 编辑器。
    

And yet I don’t _use_ them. Why? Building them was fun, sure, but there must be utility to a personal database.

但我不使用它们。为什么？建立它们当然很有趣，但个人数据库必须有实用性。

At first I thought the problem was friction: the higher the activation energy to using a tool, the less likely you are to use it. Even a small amount of friction can cause me to go, oh, who cares, can’t be bothered. So each version gets progressively more frictionless<sup id="fnref:xml" role="doc-noteref" data-immersive-translate-mark="1" data-immersive-translate-paragraph-id="9"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:xml" rel="footnote">2</a></sup>. The latest version uses a WYSIWYG editor built on top of ProseMirror (it took a great deal for me to actually give in to WYSIWYG). It also has a link to the daily note page, to make journalling easier. The only friction is in clicking the bookmark to `localhost:5000`. It is literally _two clicks_  
`localhost:5000` 两次点击  
to get to the daily note.

And yet I still don’t use it. Why? I’m a great deal more organized now than I was a few years ago. My filesystem is beautifully structured and everything is where it should be. I _could_ fill out the contents of a personal wiki.

但我仍然不使用它。为什么？我现在比几年前更有条理了。我的文件系统结构精美，一切都在它应该在的地方。我可以填写个人维基的内容。

I’ve come to the conclusion that there’s no point: because everything I can do with a personal wiki I can do better with a specialized app, and the few remaining use cases are useless. Let’s break it down.

我得出的结论是没有意义：因为我可以用个人 wiki 做的一切，我可以用一个专门的应用程序做得更好，剩下的几个用例是无用的。让我们分解一下。

## Unbundling

The following use cases are very naturally separable:  
以下用例是非常自然可分离的：  

-   **Journalling:** 86% of the nodes in my personal wiki are journal entries. Mostly there’s no reason for them to be there, they are rarely linked to by anything. I have this fallacious view that I have to use the app to justify the time investment, therefore I should use it every day, and the obvious thing you can do every day is write a daily entry that has, say, the tasks for today along with journal-like text. Rarely do journal entries link to anything except incidentally.
    
    日记：我个人 wiki 中 86% 的节点是日记条目。大多数情况下，他们没有理由在那里，他们很少与任何事物联系在一起。我有一个错误的观点，我必须使用该应用程序来证明时间投资的合理性，因此我应该每天使用它，而且您每天可以做的显而易见的事情就是写一个每日条目，其中包含今天的任务带有类似日记的文字。日记条目很少链接到任何东西，除非是偶然。
    
-   **Todo Lists:** I used to write todo lists in the daily entries in my personal wiki. But this is very spartan: what about recurring tasks, due dates, reminders, etc.? Now I am a very happy user of [Todoist](https://todoist.com/) (which has increased my productivity at least 150%) and I’m not looking back.
    
    待办事项列表：我过去常常在个人维基的每日条目中写待办事项列表。但这是非常简单的：重复性任务、截止日期、提醒等怎么样？现在我是 Todoist 的一个非常快乐的用户（它使我的工作效率至少提高了 150%）而且我不会回头。
    

-   **Learning:** if you’re studying something, you can keep your notes in a TfT. This is one of the biggest use cases. But the problem is never note-taking, but reviewing notes. Over the years I’ve found that long-form lecture notes are all but useless, not just because you have to remember to review them on a schedule, but because spaced repetition can subsume every single lecture note. It takes practice and discipline to write good spaced repetition flashcards, but once you do, the long-form prose notes are themselves redundant.
    
    I also tried writing notes to ensure I understand something first, and then translating them to flash cards. I’ve found that, usually, all this does is add an extra layer of friction with no benefit.<sup id="fnref:notes" role="doc-noteref"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:notes" rel="footnote">3</a></sup>
    
    I also find that long-form study notes are a form of procrastination. I start re-organizing the headings, playing with the LaTeX to make everything look beautiful and structured, to really get the conceptual organization right so that when future me, who has forgotten everything, reads the notes back, he can easily re-acquire the information because of how well it is presented. This is planning for failure. Spaced repetition is insanely effective, even more so when you get the hang of writing flashcards that work for you.
    
    [RemNote](https://www.remnote.com/) combines long-form prose notes and flashcards in the same interface. The result is that both look like a mess.
    
    学习：如果您正在学习某些东西，您可以将笔记保存在 TfT 中。这是最大的用例之一。但问题从来不是做笔记，而是复习笔记。多年来，我发现长篇讲义几乎毫无用处，不仅因为你必须记住按计划复习它们，还因为间隔重复可以包含每一个讲义。写出良好的间隔重复抽认卡需要练习和纪律，但一旦你这样做了，长篇散文笔记本身就是多余的。 我也试着写笔记以确保我首先理解了一些东西，然后将它们翻译成闪存卡。我发现，通常情况下，所有这些只会增加一层额外的摩擦而没有任何好处。 3 我还发现长篇学习笔记是一种拖延。我开始重新组织标题，玩弄 LaTeX 让一切看起来漂亮而有条理，真正把概念组织正确，这样当未来的我，已经忘记了一切的时候，读回笔记时，他可以很容易地重新获得信息，因为它的呈现方式。这是为失败做准备。间隔重复非常有效，当你掌握了编写适合你的抽认卡的诀窍时更是如此。 RemNote 在同一界面中结合了长篇散文笔记和抽认卡。结果是两者看起来一团糟。
    

-   **Contacts:** if you have a page for a person, with data about them, you can then link to them: when you mention them in journal entries for example, or in writing meeting notes. I find that this is pointless. You know who `[[John Doe]]` refers to. Just use Google Contacts or a spreadsheet.
    
-   **Fiction Writing:** I actually started writing [_The Epiphany of Gliese 581_](https://borretti.me/fiction/eog581) in my personal wiki, with fragments and chapters in separate pages, but I quickly moved to a git repo with Markdown files because 1) I could compile the disparate files into a single PDF or HTML file for review, and 2) using git for version control (rather than my personal wiki’s native change tracking) makes a lot more sense for writing projects.
    
    And you could argue that I could have stayed in my personal wiki by implementing support for transclusion (to assemble all the fragments into one view) and improved the version control UI. But this advice can be applied equally to every domain I attack with a personal TfT and for which it is lacking: just write a plugin to do X. The work becomes infinite, the gains are imaginary. You end up with this rickety structure of plugin upon plugin sitting on top of your TfT, and UX typically suffers the death by a thousand cuts.
    
    小说写作：我实际上开始在我的个人 wiki 中写 The Epiphany of Gliese 581，片段和章节在单独的页面中，但我很快转移到带有 Markdown 文件的 git 存储库，因为 1) 我可以将不同的文件编译成单个 PDF 或用于审查的 HTML 文件，以及 2) 使用 git 进行版本控制（而不是我个人 wiki 的本机更改跟踪）对于编写项目更有意义。 你可能会争辩说，我本可以通过实现对嵌入的支持（将所有片段组装到一个视图中）并改进版本控制 UI 来留在我的个人 wiki 中。但这个建议同样适用于我用个人 TfT 攻击的每个领域，但它缺乏：只需编写一个插件来做 X。工作变得无限，收益是虚构的。你最终会在你的 TfT 之上看到一个又一个插件的摇摇欲坠的结构，而 UX 通常会被千刀万剐。
    

-   **Process Notes:** e.g. “how do I do X in Docker”. I often have cause to write notes like this and can never quite think of where to put them. But this can’t be a genuine use case for a tool for thought because there’s very little need to create links between process notes. So this is just a matter of finding somewhere to put them in the filesystem or in a note-taking app.
    
    工艺说明：例如“我如何在 Docker 中执行 X”。我经常有理由写这样的笔记，但总是想不出把它们放在哪里。但这不可能是思考工具的真正用例，因为几乎不需要在流程注释之间创建链接。所以这只是找个地方把它们放在文件系统或笔记应用程序中的问题。
    
-   **Organizing Legal Documents:** like immigration papers or medical test results. A decent folder structure and a few spreadsheets is all it takes in practice.
    
    组织法律文件：如移民文件或体检结果。在实践中只需要一个体面的文件夹结构和一些电子表格。
    
-   **Lists:** of things you own, people you know, places you’ve lived in, education history, work history, the administrativia of life. Spreadsheets work just fine for this and there is very rarely any genuine need to link from one to another.
    
    列出：你拥有的东西、你认识的人、你住过的地方、教育经历、工作经历、生活管理。电子表格在这方面工作得很好，很少有真正需要从一个到另一个链接。
    

What is left?  
剩下什么？  

-   **Collection Management:** this is an area where the software solutions are strangely very lacking.
    
    馆藏管理：奇怪的是，这是一个非常缺乏软件解决方案的领域。
    
    I have a [Calibre](https://calibre-ebook.com/) library for books. I have a [Zotero](https://www.zotero.org/) library for papers. I sometimes think about merging the former into the latter, which is more general and has a cleaner UI, but there’s no urgent need to do so. I also have folders with music, games, interactive fiction games, RPG PDFs, board game rulebook PDFs, and art.
    
    我有一个 Calibre 图书图书馆。我有一个用于论文的 Zotero 图书馆。我有时会考虑将前者合并到后者中，后者更通用且 UI 更简洁，但没有迫切需要这样做。我还有包含音乐、游戏、互动小说游戏、RPG PDF、棋盘游戏规则手册 PDF 和艺术的文件夹。
    
    Organizing collections with the filesystem is difficult, because of the hierarchical nature of the filesystem<sup id="fnref:fs" role="doc-noteref"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:fs" rel="footnote">4</a></sup>: do I file [_Nanosystems_](https://www.amazon.com/Nanosystems-P-K-Eric-Drexler/dp/0471575186) under “Chemistry” or “Eric Drexler” or “Textbooks” or “1992”? Do I file [_The Mermaid_](https://commons.wikimedia.org/wiki/File:John_William_Waterhouse_A_Mermaid.jpg) under “John William Waterhouse”, “Painting”, “Edwardian Era”, “Pre-Raphaelite Art”? Any categorization is defensible, and any categorization makes it harder to browse by an alternative scheme<sup id="fnref:fuse" role="doc-noteref"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:fuse" rel="footnote">5</a></sup>. I need tags, that is: I need a database.
    
    使用文件系统组织集合很困难，因为文件系统的层次结构特性4：我应该将 Nanosystems 归档在“Chemistry”或“Eric Drexler”或“Textbooks”或“1992”下吗？我是否将美人鱼归档在“约翰·威廉·沃特豪斯”、“绘画”、“爱德华时代”、“拉斐尔前派艺术”下？任何分类都是站得住脚的，而且任何分类都会让其他方案更难浏览 5。我需要标签，即：我需要一个数据库。
    
    And there is a void in app-space, where there should be an app that subsumes Calibre and the rest, but inexplicably it doesn’t exist<sup id="fnref:notion" role="doc-noteref"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:notion" rel="footnote">6</a></sup>. And it’s so obvious what it should be.
    
    应用程序空间中存在空白，应该有一个包含 Calibre 和其他应用程序的应用程序，但莫名其妙地不存在 6。很明显它应该是什么。
    
    It should be, essentially, an SQLite frontend with a fancy interface. You can define record templates (like `Book` or `Person` or `Song` or `Paper`) having typed fields (e.g. `Title: String`, `PDF: File`, `Authors: List[Link[Author]]`  
    `Book` `Person` `Song` `Paper` `Title: String` `PDF: File` `Authors: List[Link[Author]]`  
    , field types can be simple data like strings or dates, or links to other records, or lists of links, or a star rating, etc.), and then add records to your collection. You can put records in hierarchical folders, but you can also retrieve them with search and tags.
    
    The closest thing to this is a KDE app called [Tellico](https://tellico-project.org/) that I’ve never heard anyone talk about using.
    
    与此最接近的是一款名为 Tellico 的 KDE 应用程序，我从未听过有人谈论过它。
    

When you take out everything that is better served by an app or plain old folder structure, all you’re left with is collection management. So instead of building a personal wiki I should just build a “generalized Calibre”.

当您删除应用程序或普通旧文件夹结构更好地服务的所有内容时，剩下的就是集合管理。因此，与其构建个人 wiki，不如构建一个“通用 Calibre”。

## The Uselessness of Scale  
规模的无用  

So I often wonder: what do other people use their personal knowledge bases for? And I look up blog and forum posts where [Obsidian](https://obsidian.md/) and [Roam](https://roamresearch.com/) power users explain their setup. And most of what I see is junk. It’s never the [Zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten) of the next Vannevar Bush, it’s always a setup with tens of plugins, a daily note three pages long that is subdivided into fifty subpages recording all the inane minutiae of life. This is a recipe for burnout.

所以我常常想：其他人用他们的个人知识库做什么？我还查阅了博客和论坛帖子，其中 Obsidian 和 Roam 高级用户解释了他们的设置。我看到的大部分都是垃圾。它永远不会是下一个 Vannevar Bush 的 Zettelkasten，它总是一个带有数十个插件的设置，一个三页长的每日笔记，被细分为五十个子页面，记录了生活中所有无聊的细节。这是倦怠的秘诀。

People have this aspirational idea of building a vast, oppressively colossal, deeply interlinked knowledge graph to the point that it almost mirrors every discrete concept and memory in their brain. And I get the appeal of maximalism. But they’re counting [on the wrong side of the ledger](https://www.cs.utexas.edu/users/EWD/transcriptions/EWD10xx/EWD1036.html#:~:text=wrong%20side%20of%20the%20ledger). Every node in your knowledge graph is a _debt_. Every link doubly so. The more you have, the more in the red you are. Every node that has utility—an interesting excerpt from a book, a pithy quote, a poem, a fiction fragment, a few sentences that are the seed of a future essay, a list of links that are the launching-off point of a project—is drowned in an ocean of banality. Most of our thoughts appear and pass away instantly, for good reason.

人们有这样一种雄心勃勃的想法，即建立一个巨大的、压抑的巨大的、深度相互关联的知识图谱，以至于它几乎反映了他们大脑中每一个离散的概念和记忆。我得到了极简主义的吸引力。但他们指望的是账本的错误一面。知识图中的每个节点都是债务。每个链接都加倍如此。你拥有的越多，你就越红。每个节点都有用——一本书的有趣摘录、精辟的引语、一首诗、小说片段、作为未来论文种子的几句话、作为项目启动点的链接列表——淹没在平庸的海洋中。我们的大多数想法都会立即出现并消失，这是有充分理由的。

## The Single Graph Fallacy  
单图谬误  

There’s this pervasive idea that a tool for thought—a hypermedia database with bidirectional links—can be a universal database of “you”, and other apps can be built on top of that data, using plugins. There are two pros here:

有一种普遍的想法认为，一种思考工具——具有双向链接的超媒体数据库——可以是“你”的通用数据库，其他应用程序可以使用插件在该数据之上构建。这里有两个优点：

1.  **Centralization of Data:** everything is one central place, rather than spread out across your filesystem, Dropbox, and database rows in six different proprietary apps.
    
    数据集中：一切都集中在一个中心位置，而不是分散在六个不同专有应用程序中的文件系统、Dropbox 和数据库行中。
    
2.  **Hyperlinking:** you can link your data pervasively:
    
    1.  Link spaced repetition cards to their corresponding theory notes.
    2.  Link date metadata to the journal entry for that date.
    3.  Link calendar events to tasks, dates, people, and projects.
    
    超链接：您可以无处不在地链接您的数据： 将间隔重复卡片链接到相应的理论笔记。 将日期元数据链接到该日期的日记条目。 将日历事件链接到任务、日期、人员和项目。
    

Obsidian does this: it has some 700 plugins for this reason. There’s plugins for todo lists, calendar integration, spaced repetition, whatever.

Obsidian 就是这样做的：出于这个原因，它有大约 700 个插件。有用于待办事项列表、日历集成、间隔重复等的插件。

The main drawback is the user experience for this plugin-based app universe is always going to be inferior to the user experience for domain-specific apps. It’s very rare that an app does plugins right. It _always_ feels janky<sup id="fnref:plugins" role="doc-noteref"><a href="https://borretti.me/article/unbundling-tools-for-thought#fn:plugins" rel="footnote">7</a></sup>.

主要缺点是这种基于插件的应用程序世界的用户体验总是不如特定领域应用程序的用户体验。很少有应用程序能正确使用插件。总感觉很简陋7。

But the main drawback is: _you don’t need it_. The idea of having this giant graph where all your data is hyperlinked is cute, but in practice, it’s completely unnecessary. Things live in separate apps just fine. How often, truly, do you find yourself wanting to link a task in your todo list app to a file in Dropbox? And if you do manage to build this vast web of links: how often is each link actually followed?

但主要缺点是：你不需要它。拥有一个所有数据都超链接的巨大图表的想法很可爱，但在实践中，这是完全没有必要的。事物存在于单独的应用程序中就好了。实际上，您发现自己多久想将待办事项列表应用程序中的任务链接到 Dropbox 中的文件？如果你确实设法建立了这个庞大的链接网络：每个链接实际被访问的频率是多少？

(Aside: in the web, it makes sense that links should reflect _potential_, since you don’t know what people reading your document will want to follow. But in a personal database it makes a lot more sense that links should follow _usage_: they should be a crystallization of the trails you’ve followed, rather than an a-priori structure that you impose before usage.)

（另外：在网络中，链接应该反映潜力是有道理的，因为你不知道阅读你的文档的人会想要关注什么。但是在个人数据库中，链接应该遵循用法更有意义：他们应该是您所遵循的路径的结晶，而不是您在使用前强加的先验结构。）

The final argument against this is feasibility. Tiago Forte [writes](https://fortelabs.com/blog/para/):  
反对这一点的最后一个论点是可行性。蒂亚戈·福特写道：  

> … you will always need to use multiple programs to complete projects. You may use a centralized platform like Basecamp, Asana, Jira, or Zoho, but technology is advancing too quickly on too many fronts for any one company to do every single function best.
> 
> …您将始终需要使用多个程序来完成项目。您可能会使用像 Basecamp、Asana、Jira 或 Zoho 这样的集中式平台，但技术在太多方面发展得太快，以至于任何一家公司都无法将每一项功能都做到最好。

And he is absolutely right, unless you want to rewrite the entire universe on top of your TfT. The “one graph database” is an unproductive, monistic obsession.

他是绝对正确的，除非你想在你的 TfT 之上重写整个宇宙。 “单一图形数据库”是一种无益的、一元论的痴迷。

A final note: I find that upwards of 80% of the links in my wikis are essentially structural, they basically replicate folder structures. The rest are “incidental reference” links: I’m writing a journal entry saying I’m working on project X, so I add a link to project X, out of some vague feeling of duty to link things. And it’s pointless.

最后一点：我发现我的 wiki 中超过 80% 的链接本质上是结构性的，它们基本上复制了文件夹结构。其余的是“附带参考”链接：我正在写一篇日记，说我正在做项目 X，所以我添加了一个指向项目 X 的链接，出于某种模糊的链接事物的责任感。这是毫无意义的。

The idea of hyperlinks as “generative”, as a path that can follow and acquire new ideas from the random collision of information, mostly applies to the web, not to personal databases where all the content is written by you.

超链接的想法是“生成的”，作为一种可以遵循并从信息的随机碰撞中获得新想法的路径，主要适用于网络，而不适用于所有内容都由您编写的个人数据库。

## My Current Wiki  
我当前的维基  

![The home page of my current personal wiki](home.png)

(The text is a quote from [_Accelerando_](https://www.antipope.org/charlie/blog-static/fiction/accelerando/accelerando.html).)  
（文本引用自 Accelerando。）  

The natural conclusion of most tools for thought is a relational database with rich text as a possible column type. So that’s essentially what I built: an object-oriented graph database on top of SQLite.

大多数思维工具的自然结论是一个关系数据库，其中富文本作为可能的列类型。所以这基本上就是我构建的：一个基于 SQLite 的面向对象的图形数据库。

My current personal wiki is called Cartesian (after the [Cartesian theatre](https://en.wikipedia.org/wiki/Cartesian_theater), since I initially thought to build something much more ambitious). The conceptual vocabulary is simple: there’s objects, classes, and links.

我目前的个人 wiki 名为 Cartesian（在 Cartesian 剧院之后，因为我最初想建立一些更雄心勃勃的东西）。概念词汇很简单：有对象、类和链接。

1.  Objects are the nodes in the database: they have a globally-unique title and a set of properties, which are typed key-value pairs.
    
    对象是数据库中的节点：它们具有全局唯一的标题和一组属性，这些属性是类型化的键值对。
    
2.  Every object conforms to a class, which specifies what properties it has and their types. Property types can be: rich text, a link to a file, a boolean, a link to another object, or a list of links.
    
    每个对象都符合一个类，该类指定它具有的属性及其类型。属性类型可以是：富文本、文件链接、布尔值、另一个对象的链接或链接列表。
    
3.  Links go from one object property to another object (there’s no block references). Notion inspired a lot of this.
    
    链接从一个对象属性到另一个对象（没有块引用）。概念激发了很多这方面的灵感。
    

Most personal wikis are just a special case of this, where there’s a single class with a single text property. And, unsurprisingly, the main class I use is `Note`, which has a single rich text property called `Text`.

Initially I had an idea to build classes for managing bibliographies and other collections, e.g.:

最初我有一个想法来构建用于管理书目和其他集合的类，例如：

1.  A `Book` class to replace Calibre, with fields like:
    1.  `Authors`: a list of links to the author objects (thanks to bidirectional linking, going to an author’s page shows you the list of all objects that link to it, i.e. the things they’ve authored).
    2.  `PDF`: a file link.
2.  A `Paper` class to replace Zotero, with the fields you’d expect.
3.  An `Art` class to manage my art collection, with fields like `Arist`, `Year`, `Period`, `Genre`, `File`  
    `Art` `Arist` `Year` `Period` `Genre` `File`  
    .
4.  Classes to organize my legal documents, e.g. a `Document` class that has a file and a text property for notes.

But I’ve largely used it for journalling and brief text notes, like my journal:

但我主要用它来写日记和简短的文字笔记，比如我的日记：

![A screenshot of my personal wiki, showing a journal entry.](journal.png)

And study notes:  
以及学习笔记：  

![A screenshot of my personal wiki, showing notes on group theory.](group1.png)

![Another screenshot with notes on group theory.](group2.png)

Here’s an example of how you’d use it to organize an art collection:  
这是您如何使用它来组织艺术收藏的示例：  

![A screenshot of my personal wiki, showing an entry for John William Waterhouse's Jason and Medea, with fields for the artist, medium, period, image file, and year.](art.png)

The barriers to using it as The One Database are:  
将其用作 The One Database 的障碍是：  

1.  **Activation Energy:** migrating everything from my filesystem, from Calibre, from Zotero, from my browser bookmarks, etc. is a huge process. Even just migrating stuff from Calibre to the database would require me to write a script because my Calibre library is so huge.
    
    Activation Energy：从我的文件系统、Calibre、Zotero、浏览器书签等迁移所有内容是一个巨大的过程。即使只是将内容从 Calibre 迁移到数据库也需要我编写脚本，因为我的 Calibre 库非常庞大。
    
2.  **UI:** replacing the filesystem and most of my domain-specific apps means the wiki’s UI has to be stellar. It has to support searching, filtering, sorting, viewing collections of objects in different modes (list, table, gallery, etc., like in Notion). Getting this to the UX sweet spot where things are frictionless enough to use the app productively requires a significant time investment.
    
    UI：替换文件系统和我的大部分特定领域的应用程序意味着 wiki 的 UI 必须是一流的。它必须支持搜索、过滤、排序、查看不同模式（列表、表格、画廊等，如概念）中的对象集合。将其带到用户体验的最佳点，在那里一切都足够顺畅以高效地使用应用程序需要大量的时间投资。
    
3.  **Pointlessness of Organization:** my Calibre and Zotero libraries are a mess. But is that _bad_? Is there any point to organizing them? I can always find what I need, either by searching or browsing, because I have a spatial sense of where each book is in Calibre’s big grid view. If I went through everything in Calibre and Zotero, and fixed the titles, added missing authors, publishers, publication years, fixed the cover images—what then? What have I gained? Nothing. It is a waste of time to organize things too much.
    
    无意义的组织：我的 Calibre 和 Zotero 图书馆一团糟。但这很糟糕吗？组织他们有什么意义吗？我总是可以通过搜索或浏览找到我需要的东西，因为我对每本书在 Calibre 的大网格视图中的位置有空间感。如果我检查了 Calibre 和 Zotero 中的所有内容，修复了标题，添加了缺失的作者、出版商、出版年份，修复了封面图片——然后呢？我得到了什么？没有什么。把事情整理得太多是浪费时间。
    
4.  **Uncertain Payoff:** silver bullets are rare, and it’s possible that after making a titanic effort to migrate all my data and build a great UI, the result of very underwhelming.
    
    不确定的回报：灵丹妙药很少见，而且有可能在付出巨大努力迁移我的所有数据并构建出色的 UI 之后，结果却很平庸。
    

## Conclusion

Having reached the [trough of disillusionment](https://en.wikipedia.org/wiki/Gartner_hype_cycle): what’s next? I think I might clean up Cartesian and release it as a kind of “generalized Calibre”, for people who want to manage their disparate collections.

达到幻灭的低谷：下一步是什么？我想我可能会清理笛卡尔并将其作为一种“通用口径”发布，供那些想要管理其不同收藏的人使用。

Or I might try writing personal wiki #8 or so, since, while writing this post, I got a whole lot of new ideas, so I might allocate some time during the holidays to pushing that boulder up again.

或者我可能会尝试写个人 wiki #8 左右，因为在写这篇文章时，我有了很多新想法，所以我可能会在假期里分配一些时间再次推上那块巨石。
