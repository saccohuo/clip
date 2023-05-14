---
title: "标签系统"
date: 2023-05-12T08:10:45+08:00
updated: 2023-05-12T08:10:45+08:00
taxonomies:
  tags: []
extra:
  source: https://buttondown.email/hillelwayne/archive/tag-systems/?ref=eleanorkonik.com
  hostname: buttondown.email
  author: 
  original_title: "Tag Systems"
  original_lang: zh
---

本文介绍了标签系统的设计，包括标签的定义、标签之间的关系、标签的实现考虑因素、智能标签、哈希标签、键值标签等。同时，文章还讨论了标签系统的应用场景和设计问题，如标签的创建者、标签与结构的关系、标签系统在图书馆学科中的应用等。

文章要点：
1. 标签是与内容相关联的元数据标签，主要用于查询和组织内容。
2. 标签之间的关系包括标签别名、子标签、DAG 标签等。
3. 智能标签基于规则而非显式分配，具有表达能力，但计算成本高。
4. 哈希标签是将标签嵌入到内容中的一种标记方式，但存在解析和元数据缺失的问题。
5. 键值标签是标签带有附加语义值的一种标记方式，但通常只用于字符串或枚举值。
6. 标签系统的设计问题包括标签创建者、标签与结构的关系、标签系统在图书馆学科中的应用等。

关键词：标签系统、标签关系、智能标签、哈希标签、键值标签、图书馆学科。

---

I’ve tried to write a blog post on tag systems for years now. Literally _years_, I think I first started drafting it out in 2018 or so? The problem is that there’s just _so much_ to them, so many different approaches and models and concerns that trying to be comprehensive and rigorous is an exercise in madness.  

多年来，我一直试图写一篇关于标签系统的博文。从字面上看，我想我是在 2018 年左右开始起草的？问题是它们的内容太多了，有太多不同的方法、模型和关注点，以至于试图做到全面和严谨是一种疯狂的练习。

So screw it. These are my noncomprehensive, poorly-researched thoughts on tag systems, thrown on the newsletter. **This is not about implementation of tag systems, just their design**.  

所以搞砸了。这些是我在时事通讯上发表的关于标签系统的不全面的、未经充分研究的想法。这与标签系统的实现无关，只是它们的设计。

## What is a Tag 什么是标签

A tag is a metadata label associated with content. The tag name is also the id: two tags with the same name are the same tag. Tags appear in almost all large systems:  

标签是与内容关联的元数据标签。标签名也是id：两个同名的标签是同一个标签。标签几乎出现在所有大型系统中：

-   Social media #hashtags. 社交媒体#hashtags。
-   Wikipedia categories. 维基百科类别。
-   Blog post/CMS labels. 博客文章/CMS 标签。
-   AWS infrastructure tags. AWS 基础设施标签。
-   ACM digital library index terms. ACM 数字图书馆索引术语。

Tags are primarily used for both _querying_, or discovering information based on tags, and _grouping_, or organizing content for processing. They are sometimes also used for business logic, like “all articles tagged `covid` are free even without a subscription” or “devs can upload to any s3 bucket with the [qa](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_tags.html#access_tags_control-tag-keys) tag”.  

标签主要用于基于标签查询或发现信息，以及分组或组织内容以进行处理。它们有时也用于业务逻辑，例如“所有标记为 `covid` 的文章即使没有订阅也是免费的”或“开发人员可以使用 qa 标签上传到任何 s3 存储桶”。

Tags are primarily _client-driven_. You do not need to make changes to the codebase to add or a remove a tag. This is in contrast with the content _structure_, which requires dev intervention to change.  

标签主要是客户端驱动的。您无需更改代码库即可添加或删除标签。这与需要开发人员干预才能更改的内容结构形成对比。

## Relationships between Tags 标签之间的关系

In the simplest system, all tags are uniquely identified by their name. `horse` and `horses` are separate tags. This is easy to implement and reason about, but it’s also really annoying for taggers. Why should I have to tag everything with both `horse` and `horses` if they clearly mean the same thing?  

在最简单的系统中，所有标签都由它们的名称唯一标识。 `horse` 和 `horses` 是单独的标签。这很容易实现和推理，但对标注者来说也很烦人。如果 `horse` 和 `horses` 显然是同一个意思，我为什么还要用它们来标记所有内容？

### Tag Aliases

The simplest relationship we could add are “tag aliases”: if A is aliased to B, then querying A is identical to querying B. While things could be tagged `horses`, the internal system only “knows” `horse`, and automatically converts searches for `horses` into searches for `horse`.  

我们可以添加的最简单的关系是“标签别名”：如果 A 是 B 的别名，那么查询 A 就等同于查询 B。虽然事物可以被标记为 `horses` ，但内部系统仅“知道” `horse` ，并且自动将对 `horses` 的搜索转换为对 `horse` 的搜索。

The best example of tag aliases is the fanfiction repository [_Archive of Our Own_](https://archiveofourown.org/faq/tags?language_id=en) (AO3). Fanfics use a lot of jargon to refer to various character pairings, which makes querying difficult.  

标签别名的最佳示例是同人小说库 Archive of Our Own (AO3)。同人小说使用大量行话来指代各种角色配对，这给查询带来了困难。  

Teams of volunteers comb through stories and manually add aliases to tags, so that stories tagged `Snape/Harry` and `snarry` show up under the root tag `Harry/Snape`.  

志愿者团队梳理故事并手动为标签添加别名，以便标记为 `Snape/Harry` 和 `snarry` 的故事显示在根标签 `Harry/Snape` 下。

The additional tag structure adds expressiveness. But it also raises use-case questions, like “should users be able to query a _specific_ tag alias?” ie, can I search for stories tagged with the _alias_ `snarry`? There’s no correct choice here. AO3 went with “no”.  

额外的标签结构增加了表现力。但它也提出了用例问题，比如“用户应该能够查询特定的标签别名吗？”即，我可以搜索标有别名 `snarry` 的故事吗？这里没有正确的选择。 AO3 选择了“否”。

### Subtags

In a subtag system, tags are placed into a hierarchy of parent tags and subtags. Anything tagged with the subtag also counts for the parent tag. For example, `quantum physics` could be a subtag of `physics`, which could be a subtag of `science`. Querying `science` would include content on quantum physics. A tag with no subtags is a **leaf tag**. This is arguably the most common kind of tag structure.  

在子标签系统中，标签被放置在父标签和子标签的层次结构中。任何标有子标签的内容也算作父标签。例如， `quantum physics` 可以是 `physics` 的子标签，也可以是 `science` 的子标签。查询 `science` 将包含有关量子物理学的内容。没有子标签的标签是叶标签。这可以说是最常见的一种标签结构。

Implementation considerations: transitive queries are expensive, and you need to prevent cycles in the tag hierarchy (A’s parent is B, B’s parent is A).  

实现注意事项：传递查询是昂贵的，你需要防止标记层次结构中的循环（A 的父级是 B，B 的父级是 A）。  

They also have major usage considerations:  

它们也有主要的使用注意事项：

-   Can things be tagged with root tags or just leaf tags?  
    
    东西可以用根标签或叶标签来标记吗？
-   Can things be tagged with something _and_ its subtag?  
    
    东西可以用东西和它的子标签来标记吗？
-   How do users search for X _without_ its subtags?  
    
    用户如何在没有子标签的情况下搜索 X？
-   How do set operations work? Does a book on particle physics and a book on elephant biology share the `science` tag?  
    
    集合操作如何工作？一本关于粒子物理学的书和一本关于大象生物学的书共享 `science` 标签吗？

_This post is sponsored by me. [I’m teaching an online TLA+ workshop](https://www.eventbrite.com/e/software-modeling-with-tla-workshop-tickets-520030754987?aff=email) in March, May, and June. Use the code `C0MPUT3RTHINGS` for 15% off!  

这篇文章是由我赞助的。我在 3 月、5 月和 6 月教授在线 TLA+ 研讨会。使用代码 `C0MPUT3RTHINGS` 可享受 15% 的折扣！_

### DAG tags

Most subtag systems form a forest (set of disjoint trees), where each tag has at most one parent. Wikipedia categories, on the other hand, can have multiple parents.  

大多数子标签系统形成一个森林（一组不相交的树），其中每个标签最多有一个父标签。另一方面，维基百科类别可以有多个父级。  

“American Male Novelists” is a subtag of “American Male Writers” and “American Novelists”, both of which are subtags of “American Writers”.  

“American Male Novelists”是“American Male Writers”和“American Novelists”的子标签，两者都是“American Writers”的子标签。  

The tag system forms a directed acyclic graph, so let’s call these DAG tags.  

标签系统形成一个有向无环图，我们称这些为DAG标签。

DAG tags makes preventing cycles harder and adds “redundancy” as a structural design question. If A is the child of B, can C be the child of both A and B? Wikipedia [sort of has it both ways](https://en.wikipedia.org/wiki/Wikipedia:Categorization#Category_tree_organization), with “diffusing” vs “nondiffusing” subtags. Querying also gets complicated.  

DAG 标签使防止循环变得更加困难，并将“冗余”添加为结构设计问题。如果A是B的孩子，C能同时是A和B的孩子吗？维基百科有点两全其美，有“扩散”和“非扩散”子标签。查询也变得复杂。  

How do we handle the query “all items with tag X but not tag Y” when an item has tag Z, which has as parents both X and Y? Is that even something you should let users query?  

当一个项目有标签 Z，同时有 X 和 Y 作为父项时，我们如何处理查询“所有项目有标签 X 但没有标签 Y”？这甚至是你应该让用户查询的东西吗？

Notice that the more richness in structure we add, the more ambiguous our queries become.  

请注意，我们添加的结构越丰富，我们的查询就越模糊。  

“Every article that shares a tag with article X that’s not also a tag on article Y” is unambiguous with simple tags, less so with a tag tree, even less so with a tag DAG.  

“每篇与文章 X 共享一个标签但又不是文章 Y 的标签的文章”对于简单标签是明确的，对于标签树更是如此，对于标签 DAG 更是如此。  

This is the standard “generality vs tractability” problem you see everywhere in CS, from static analysis to constraint solving to aliasing.  

这是您在 CS 中随处可见的标准“通用性与易处理性”问题，从静态分析到约束求解再到别名。  

Constraints liberate and liberties constraint.  

约束解放和自由约束。

### Smart Tags

So far all the tags have been “simple”: the set of tagged items is the set specifically assigned to that tag.  

到目前为止，所有标签都是“简单的”：带标签的项目集是专门分配给该标签的集合。  

This is made more complicated with aliases and parent tags but the core idea of explicit assignment is there.  

别名和父标签使这变得更加复杂，但显式分配的核心思想就在那里。  

“Smart tags” are instead based on a rule: anything matching that rule counts as having that tag.  

“智能标签”是基于规则的：任何匹配该规则的东西都算作具有该标签。  

For example, any recipe that doesn’t have any nut ingredients is automatically tagged _nut-free_.  

例如，任何不含任何坚果成分的食谱都会自动标记为无坚果。

Smart tags are very expressive. They also play hell with any other kind structure and even themselves if you’re not careful.  

智能标签非常有表现力。如果您不小心，它们还会与任何其他类型的结构甚至它们自己一起玩耍。  

One mobile device manager (MDM) I worked with allowed for smart tags like “every iPad assigned to a classroom in Ferndale High School _that’s not tagged ABC_”. As a curious and extremely dumb engineer, I added two smart tags:  

与我合作的一位移动设备经理 (MDM) 允许使用智能标签，例如“分配给 Ferndale 高中教室的每台 iPad，但没有标记为 ABC”。作为一个好奇又极其愚蠢的工程师，我添加了两个智能标签：

-   A: “Anything tagged B” A：“任何标有 B 的东西”
-   B: “Anything not tagged A” B：“任何未标记为 A 的东西”

And then the MDM crashed. 然后 MDM 崩溃了。

The lesson: don’t let users encode logical paradoxes. Also, don’t try making logical paradoxes on a production server.  

教训：不要让用户编码逻辑悖论。另外，不要尝试在生产服务器上制造逻辑悖论。

Smart tags are computationally expensive. Any change to any item can potentially require a large set of re-computations.  

智能标签的计算成本很高。对任何项目的任何更改都可能需要大量的重新计算。  

Between this and the logical paradoxes thing they’re a niche solution to specific problems. Which is a shame, I really like the idea of them.  

在这个和逻辑悖论之间，它们是针对特定问题的利基解决方案。真可惜，我真的很喜欢他们的想法。

### Hashtags

Hashtags are a form of tagging where the tag is embedded as part of the content of the object. The archetypical example is Twitter: a tweet containing the string `#foo` is considered to have the `foo` tag. Tag membership is tested by searching the text of the content. In practice, many systems will opt to cache the tags associated with the content for performance reasons.  

主题标签是一种标记形式，其中标签作为对象内容的一部分嵌入。典型示例是 Twitter：包含字符串 `#foo` 的推文被认为具有 `foo` 标签。通过搜索内容的文本来测试标签成员资格。实际上，出于性能原因，许多系统会选择缓存与内容关联的标签。  

Hashtags are very popular on social media because you don’t need to expose any additional input functionality to the user: they use the same textbox for both content and tags.  

标签在社交媒体上非常流行，因为您不需要向用户公开任何额外的输入功能：它们对内容和标签使用相同的文本框。

Hashtags have two limitations over other tagging systems. First, they have to be parsed as part of the content. This means Twitter cannot have the hashtag `#this tag` due to the parser interpreting the space as the end of the tag. It also means there’s no easy way to refer to the tag without including it.  

与其他标记系统相比，主题标签有两个限制。首先，必须将它们作为内容的一部分进行解析。这意味着 Twitter 不能有标签 `#this tag` ，因为解析器将空格解释为标签的结尾。这也意味着没有简单的方法可以在不包含标签的情况下引用标签。  

I can’t say “everybody who uses the #qanon tag is insane” without also tagging my post `qanon`!  

我不能说“每个使用#qanon 标签的人都是疯子”而不标记我的帖子 `qanon` ！

Second, there is no place for additional metadata. You can’t do tag aliases or subtags or anything.  

其次，没有额外元数据的位置。你不能做标签别名或子标签或任何东西。

### Key-value tags

Instead of a tag being a single label, the tag carries an additional semantic value that’s _not_ the tag id. Then you can query either the raw tag or the tag’s value. This is used a lot in technical tooling. A sprint planner might tag some things as `priority: 1`, in AWS you can tag resources as `env: production`, etc.  

标签不是一个单一的标签，而是带有一个额外的语义值，而不是标签 id。然后您可以查询原始标签或标签的值。这在技术工具中被大量使用。 sprint 计划者可能会将一些东西标记为 `priority: 1` ，在 AWS 中你可以将资源标记为 `env: production` 等。

For the most part I’ve only seen this done with string or enumerated values. While it’s plausible to tag something like `due date: 2023-01-30` so you can query by date range, in practice that’s usually lifted to built-in content structure instead of the ad-hoc tagging structure.  

在大多数情况下，我只看到过使用字符串或枚举值来完成此操作。虽然标记 `due date: 2023-01-30` 之类的东西是合理的，这样您就可以按日期范围进行查询，但在实践中，通常将其提升为内置内容结构，而不是临时标记结构。

## Other Thoughts on Tags 关于标签的其他想法

### Who creates the tags? 谁创建标签？

All tag systems have an audience, who the content itself is for, and a set of taggers, who are _doing the tagging_. These can be the same people or completely different groups. Some possible breakdowns:  

所有的标签系统都有一个观众，内容本身是为谁而设的，还有一组标签者，他们正在做标签。这些人可以是同一个人，也可以是完全不同的群体。一些可能的故障：

-   Individuals tagging for themselves: MacOS Finder tagging. Personal photo tagging. Adding tags to bookmarks.  
    
    个人为自己标记：MacOS Finder 标记。个人照片标记。添加标签到书签。
-   A group tagging for themselves: AWS tagging. Internal documentation. Bills.  
    
    为自己打标签的组：AWS tagging。内部文档。账单。
-   Public content with private taggers: Archive of Our Own. Wikipedia(ish). Newspapers. Library of Congress.  
    
    带有私人标签的公共内容：我们自己的档案。维基百科（ish）。报纸。国会图书馆。
-   Tagging for a distributed resource: Semantic web. Social media. Amazon Customer Stores.  
    
    分布式资源的标记：语义网。社交媒体。亚马逊客户商店。

All of these have different design and usage concerns.  

所有这些都有不同的设计和使用问题。

### The Instagram problem Instagram 问题

The last case, where everybody is tagging their own public content, poses two unique concerns. The obvious one is bad actors.  

在最后一种情况下，每个人都在标记自己的公共内容，这引起了两个独特的担忧。显而易见的一个是坏演员。  

In a distributed system everybody is competing with everybody else for attention, so there’s an incentive to add unrelated tags.  

在分布式系统中，每个人都在与其他人竞争注意力，因此存在添加不相关标签的动机。

> Metadata exists in a competitive world. Suppliers compete to sell their goods, cranks compete to convey their crackpot theories (mea culpa), artists compete for audience.  
> 
> 元数据存在于竞争激烈的世界中。供应商竞相销售他们的商品，怪人竞相传达他们的怪诞理论（mea culpa），艺术家们争夺观众。  
> 
> … That’s why a search for any commonly referenced term at a search-engine like Altavista will often turn up at least one porn link in the first ten results. — [Corey Doctorow](https://people.well.com/user/doctorow/metacrap.htm)  
> 
> ……这就是为什么在像 Altavista 这样的搜索引擎上搜索任何常用术语时，通常会在前十个结果中至少出现一个色情链接。 — 科里·多克托罗

The other problem is what I call “The Instagram Problem”. Instagram uses hashtags. Nobody coordinates the tags, so there’s no way of knowing _which_ tags people will look at. Here’s a picture of [a friend’s horse](https://www.instagram.com/p/CnsSNxZS4e_/):<sup id="fnref:horse-girl" data-immersive-translate-effect="1" data-immersive-translate-mark="1" data-immersive-translate-paragraph-id="151"><a href="https://buttondown.email/hillelwayne/archive/tag-systems/?ref=eleanorkonik.com#fn:horse-girl">1</a></sup>  

另一个问题就是我所说的“Instagram 问题”。 Instagram 使用主题标签。没有人协调标签，因此无法知道人们会查看哪些标签。这是朋友的马的照片： <sup id="fnref:horse-girl" data-immersive-translate-effect="1" data-immersive-translate-mark="1" data-immersive-translate-paragraph-id="151"><a href="https://buttondown.email/hillelwayne/archive/tag-systems/?ref=eleanorkonik.com#fn:horse-girl">1</a></sup>

![A picture of a horse with 21 tags](0cd60413-ddee-4da3-9f80-a8bb054a83d2.png)

In order to be sure that other horse girls on Instagram saw the picture, she had to tag it `#horse` _and_ `#horses` _and_ `#horsegirl` _and_ `#horsesofinstagram`. At some point “horse” stops being a word.  

为了确保 Instagram 上的其他马妹看到这张照片，她不得不将其标记为 `#horse` 和 `#horses` 以及 `#horsegirl` 和 `#horsesofinstagram` 。在某些时候，“马”不再是一个词。

### Tags vs Structure 标签与结构

I sometimes see tags used as a replacement for first class structure.  

我有时会看到标签被用作一流结构的替代品。  

Instead of having a “assigned to” field in a record, the record might be tagged with an “assigned to” property tag. This rankles me but I can’t quite place down why.  

记录中可能没有“分配给”字段，而是用“分配给”属性标记来标记记录。这让我很生气，但我不能完全说出原因。  

People do this because it’s more expressive and lot easier to set up. But you lose the advantages of having that structure made explicit.  

人们这样做是因为它更具表现力并且更容易设置。但是你失去了使该结构明确的优势。

### Libraries

Library scientists have written a _lot_ about tagging systems. [Foundations of Library and Information Science](https://www.amazon.com/Foundations-Library-Information-Science-Third/dp/1555706908) book is a good intro to this (and other librarian topics).  

图书馆科学家写了很多关于标签系统的文章。 Foundations of Library and Information Science 一书很好地介绍了这一点（以及其他图书馆员主题）。  

In my experience, they tend to focus on metadata strictly controlled by professionals for the purpose of knowledge categorization, which is not-entirely-in-line with how a lot of software systems use tagging.  

根据我的经验，他们倾向于关注由专业人士严格控制的元数据，用于知识分类，这与许多软件系统使用标记的方式并不完全一致。  

Even so, if you really want to get deep into the nuances of information classification, library science is the way to go. Some topics:  

即便如此，如果你真的想深入了解信息分类的细微差别，图书馆学是必经之路。一些主题：

-   [Controlled Vocabulary  受控词汇](https://www.getty.edu/research/publications/electronic_publications/intro_controlled_vocab/what.pdf)
-   [Ontologies](https://library.buffalo.edu/scholarly/documents/Barry-Smith-Ontologies-What-Librarians-Need-to-Know.pdf)
-   [Authority Control](https://ac.bslw.com/community/blog/2010/05/why-is-authority-control-important/)
-   [Metadata](https://groups.niso.org/higherlogic/ws/public/download/17446/Understanding%20Metadata.pdf)

_[Thanks again to me for sponsoring this newsletter](https://www.eventbrite.com/e/software-modeling-with-tla-workshop-tickets-520030754987?aff=email).  

再次感谢我赞助这份时事通讯。_

___

### Update for the Internets 互联网更新

This was sent as part of an email newsletter; you can subscribe [here](https://buttondown.email/hillelwayne/). Updates are 6x a month. I also have a [website](https://www.hillelwayne.com/).  

这是作为电子邮件通讯的一部分发送的；你可以在这里订阅。每月更新 6 次。我也有一个网站 。
