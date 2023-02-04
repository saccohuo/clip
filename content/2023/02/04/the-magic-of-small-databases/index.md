---
title: "小型数据库的魔力"
date: 2023-02-04T12:10:59+08:00
updated: 2023-02-04T12:10:59+08:00
taxonomies:
  tags: []
extra:
  source: https://tomcritchlow.com/2023/01/27/small-databases/
  hostname: tomcritchlow.com
  author: 
  original_title: "The Magic of Small Databases"
  original_lang: en
---

summary

Publishing documents to the web is a well-served use case but publishing small indexes, databases and collections to the web is still an incredibly frustrating and under-served use case. Here I outline why I think it matters and a variety of approaches to solving it.  

将文档发布到 Web 是一个服务良好的用例，但将小型索引、数据库和集合发布到 Web 仍然是一个令人难以置信的令人沮丧且服务不足的用例。在这里，我概述了为什么我认为它很重要以及解决它的各种方法。

## Introduction  

介绍

Imagine you care very much about Japanese woodblock prints, and you love the web. So you decide as an interested amateur to build a website to house your library of 200k+ prints. This of course is a thing that the internet has: [ukiyo-e.org](https://ukiyo-e.org/) - Japanese Woodblock Print Search, created by John Resig.  

想象一下，您非常喜欢日本木版画，并且热爱网络。因此，作为一个感兴趣的业余爱好者，您决定建立一个网站来存放您的 20 万多张印刷品的图书馆。这当然是互联网上的东西：ukiyo-e.org - Japanese Woodblock Print Search，由 John Resig 创建。

Now, imagine that you’re not THE John Resig, world class web developer and founder of Jquery.  

现在，假设您不是 John Resig，他是世界级的 Web 开发人员和 Jquery 的创始人。

We’ve built many tools for publishing to the web - but I want to make the claim that we have underdeveloped the tools and platforms for publishing collections, indexes and small databases. It’s too hard to build these kinds of experiences, too hard to maintain them and a lack of collaborative tools.  

我们已经构建了许多用于发布到网络的工具——但我想声明我们还没有开发出用于发布集合、索引和小型数据库的工具和平台。构建此类体验太难，维护它们也太难，而且缺乏协作工具。

Here’s the thesis:  

这是论文：

1.  Independently published and maintained collections are interesting and valuable  
    
    独立出版和维护的馆藏有趣且有价值
2.  Publishing them to the modern web is too hard and there are few purpose-built tools that help  
    
    将它们发布到现代网络太难了，而且几乎没有专门构建的工具可以提供帮助
3.  Collaborating and maintaining them is a tough challenge  
    
    协作和维护它们是一项艰巨的挑战

Sari (building a community index Startupy) has a nice piece exploring this tension:  

Sari（建立社区索引 Startupy）有一篇很好的文章探讨了这种紧张关系：

There _AR_E tools that allow you to manage collections and indexes, for specialist use cases. Ecommerce is the most obvious example.  

有一些工具可让您针对专业用例管理集合和索引。电子商务是最明显的例子。  

The core needs of creating a database of products, adding metadata, enabling search and creating collections are all well served by a range of tools (Shopify, Squarespace, etc etc).  

创建产品数据库、添加元数据、启用搜索和创建集合的核心需求都可以通过一系列工具（Shopify、Squarespace 等）得到很好的满足。

Meanwhile, there are many tools that allow independent authors to create content (Wordpress, Substack, Squarespace, Ghost, Webflow etc etc). But these tools place a heavy emphasis on documents and pages and less of an emphasis on collections of objects, links and metadata.  

同时，有许多工具允许独立作者创建内容（Wordpress、Substack、Squarespace、Ghost、Webflow 等）。但是这些工具非常重视文档和页面，而不太重视对象、链接和元数据的集合。

To highlight this tension, consider a couple of examples:  

为了强调这种紧张关系，请考虑几个例子：

-   The personal website of Rob Giampietro [lined and unlined](https://linedandunlined.com/) has a lovely index-view of content but defaults to a site: search in Google to handle search.  
    
    Rob Giampietro 的个人网站 lined 和 unlined 有一个可爱的内容索引视图，但默认为一个站点：在 Google 中搜索以处理搜索。
-   The [Cyberfeminism Index](https://cyberfeminismindex.com/) is an amazing collection of 828 resources, each with notes and quotes. Although the site has search the whole thing is a single HTML file with 100k+ lines of code.  
    
    Cyberfeminism Index 是一个包含 828 种资源的惊人集合，每一种都有注释和引述。尽管该站点已进行搜索，但整个内容是一个包含 10 万多行代码的 HTML 文件。
-   Jarrett Fuller publishes a lovely collection of readings for people interested in design [readings.design](https://readings.design/) that has 251 resources but what appear to be manually created tags and no search.  
    
    Jarrett Fuller 为对设计阅读感兴趣的人出版了一个可爱的阅读集。设计有 251 个资源，但似乎是手动创建的标签并且没有搜索。
-   My friend Jonah Dragan has been documenting amazing kids picture books, both popular and obscure. He has [over 900 archived on his Instagram](https://www.instagram.com/jonahdragan/?hl=en). How might this archive become, well, an archive?  
    
    我的朋友 Jonah Dragan 一直在记录令人惊叹的儿童图画书，既有流行的也有鲜为人知的。他在他的 Instagram 上存档了 900 多个。这个档案馆如何成为一个档案馆？

To be clear, I’m not being critical of these resources! I very much enjoy them all and love that they exist. Indie web creators will use [digital bricolage](https://tomcritchlow.com/2023/01/20/digital-bricolage/) to use whatever tools they have to build things and that’s great. The Cyberfeminism Index even has an explicit focus on long-term maintainability and lack of dependencies which is great.  

需要明确的是，我并不是在批评这些资源！我非常喜欢它们，也喜欢它们的存在。独立网络创作者将使用数字拼贴来使用他们拥有的任何工具来构建东西，这很棒。网络女性主义指数甚至明确关注长期可维护性和缺乏依赖性，这很好。

But it shows some of the potential use cases where people are looking for “database publishing”.  

但它显示了人们正在寻找“数据库发布”的一些潜在用例。

These are all individuals - personal things. But this challenge applies to institutions too. Here’s the digital art foundation Rhizome on building their archive of digital art projects Artbase:  

这些都是个人——个人的事情。但这一挑战也适用于机构。这是数字艺术基金会 Rhizome 建立他们的数字艺术项目 Artbase 的档案：

## What do we need?  

我们需要什么？

Let’s think through the kinds of use cases and functionality that is important. I’d say that the core features are:  

让我们仔细考虑一下重要的用例和功能的种类。我会说核心功能是：

1.  Creating collections of objects  
    
    创建对象集合
2.  Adding and updating metadata for the objects (ideally in bulk if needed)  
    
    添加和更新对象的元数据（如果需要最好是批量）
3.  Creating collections, relationships and pathways through the data  
    
    通过数据创建集合、关系和路径
4.  Collaborating on these with others  
    
    在这些方面与他人合作
5.  Publishing to the web in an easy to consume way, with stable URLs, search etc  
    
    以易于使用的方式发布到网络，具有稳定的 URL、搜索等
6.  Open standard file formats for export / import / desktop editing  
    
    用于导出/导入/桌面编辑的开放标准文件格式

I think the last point is key to building an ecosystem of this stuff.  

我认为最后一点是建立这个东西的生态系统的关键。  

We have CSV files as a kind of open standard for any kind of data - possible to open it in all kinds of applications (or even edit directly with a text editor) and yet we have no standard concept for a database file that you can just open and edit in a range of applications?  

我们有 CSV 文件作为任何类型数据的一种开放标准——可以在各种应用程序中打开它（甚至可以直接使用文本编辑器编辑），但我们没有数据库文件的标准概念，您可以在一系列应用程序中打开和编辑？

## Cybernetic Indexes  

控制论索引

Let’s go beyond the simple use cases though - I’m excited about building extensions and automations for these small databases.  

让我们超越简单的用例——我很高兴为这些小型数据库构建扩展和自动化。  

The magic of the web is that automations (via chrome extensions, bookmarklets, zapier, cloud functions, github actions, replits etc) are becoming simple, easy to build and accessible to hobby-coders, not just professional developers.  

网络的魔力在于自动化（通过 chrome 扩展、书签、zapier、云函数、github 操作、replits 等）变得简单、易于构建并且业余爱好者可以访问，而不仅仅是专业开发人员。

In an era of chat GPT, cheap search & web-crawlers how can we make any small database come alive?  

在聊天 GPT、廉价搜索和网络爬虫的时代，我们如何让任何小型数据库活跃起来？

Here’s an example of cybernetic database I want to build: I’d like to build an index of all the artists in Brooklyn  

这是我要建立的控制论数据库的示例：我想建立布鲁克林 中所有艺术家的索引Erin and I still run [Fiercely Curious](https://www.fiercelycurious.com/), which is a small-scale, curated version of this.   

艾琳和我仍在运行 Fiercely Curious，这是一个小规模的策划版本。. This would be a resource for seeing a ton of local artists and their work all in one place. A database that’s searchable, taggable. This doesn’t exist today. How would you build it?  

.这将是一种资源，可以让您在一个地方看到大量当地艺术家和他们的作品。一个可搜索、可标记的数据库。这在今天不存在。你会如何建造它？

And importantly - after you’ve built it, how would you bring it to life? I’m thinking things like:  

重要的是——在你建造它之后，你将如何让它栩栩如生？我在想这样的事情：

-   Image machine learning to auto-extract tags and classifications around color, medium etc  
    
    图像机器学习自动提取颜色、介质等周围的标签和分类
-   Web-scrapers that can periodically re-crawl the artist’s websites and update the database with new works and new info  
    
    可以定期重新抓取艺术家网站并使用新作品和新信息更新数据库的网络抓取工具

I could probably build this myself if I was really motivated but it would require building an _actual_ database. There’s no readily available solution (that I know of) that would enable this kind of thing…  

如果我真的有动力，我可能可以自己构建它，但这需要构建一个实际的数据库。没有现成的解决方案（据我所知）可以实现这种事情……

I’m still actively researching the best tools out there for this kind of work but in the meantime I’ve created an Airtable database for tools, examples of small databases and interesting reading. Take a look (or [load the file directly here](https://airtable.com/shrYY94GrqVB4HUsi/tblHPrdomiPbLpod6/viwxizssDJMsGqhg9?backgroundColor=green&blocks=hide))  

我仍在积极研究用于此类工作的最佳工具，但与此同时，我已经为工具、小型数据库示例和有趣的阅读材料创建了一个 Airtable 数据库。看一看（或直接在此处加载文件）

An airtable of resources  

空中资源表

If you have suggestions and additions - email me!  

如果您有建议和补充 - 给我发电子邮件！

## Datasette  

数据集

I’d like to call out [Datasette](https://datasette.io/) in particular. Datasette is “An open source multi-tool for exploring and publishing data” created and maintained by Simon Willison.  

我想特别提到 Datasette。 Datasette 是由 Simon Willison 创建和维护的“用于探索和发布数据的开源多工具”。

Of all the projects I’ve come across Datasette feels so closely ideologically aligned to what I want. It’s open source, Simon really cares about helping non-developers use it (via a cloud product, a [desktop product](https://datasette.io/desktop) etc) - it’s even building out [web-scraping functionality](https://github.com/cldellow/datasette-scraper/releases/tag/0.5)! Datasette is like a swiss army knife tool for exploring data but also allows you to publish that data to the web.  

在我遇到的所有项目中，Datasette 感觉在意识形态上与我想要的非常一致。它是开源的，Simon 非常关心帮助非开发人员使用它（通过云产品、桌面产品等）——它甚至构建了网络抓取功能！ Datasette 就像一把用于探索数据的瑞士军刀工具，但也允许您将该数据发布到网络上。

Everything about Datasette feels great - the only problem is that it still feels slightly too far out of reach for your average enthusiast / indie publisher.  

Datasette 的一切感觉都很棒——唯一的问题是，对于普通爱好者/独立发行商来说，它仍然感觉有点遥不可及。  

There are still a lot of command line prompts around… This is not criticism of Simon - he’s an indie developer building the whole thing!  

仍然有很多命令行提示……这不是对 Simon 的批评——他是一个独立开发者，构建了整个东西！

Anyway - my point is that I think Datasette is going to get easier over time and may, if you’re more technical than me, be a good tool for this _today_.  

无论如何 - 我的观点是，我认为 Datasette 会随着时间的推移变得更容易，如果你比我更技术，今天可能会成为一个很好的工具。

## Market-making Small Databases  

做市商小型数据库

Actually - maybe this isn’t a real technology problem. Or at least not completely a technology problem. I think Substack is a good analogy here. Substack’s innovation comes in two flavors: firstly it is a lovely UX for creating, publishing and maintaining a paid email list.  

实际上——也许这不是真正的技术问题。或者至少不完全是技术问题。我认为 Substack 在这里是一个很好的类比。 Substack 的创新有两个方面：首先，它是一个可爱的用户体验，用于创建、发布和维护付费电子邮件列表。  

But secondly it’s also creating social validation and educating people that running a paid email list is a viable business.  

但其次，它也在创造社会认可度，并教育人们运行付费电子邮件列表是一项可行的业务。

I think there might be a similar market-making innovation here for small databases.  

我认为对于小型数据库，这里可能会有类似的做市创新。

Imagine a Substack for databases - an easy tool for creating, maintaining and publishing databases with the ability to restrict parts or all of it behind a pay wall. Pair it with the ability to send email updates to your audience about changes and additions.  

想象一下数据库的子堆栈——一种用于创建、维护和发布数据库的简单工具，能够将部分或全部数据库限制在付费墙后面。将其与向您的受众发送有关更改和添加的电子邮件更新的能力相结合。  

Maybe even roll in some of the data-cleanup and data-collection magic that machine learning and web scraping offers.  

甚至可以加入机器学习和网络抓取提供的一些数据清理和数据收集魔法。

Yes, you could assemble this exact business model today using a combination of Memberful and Airtable and Substack but…. it’s clunky. And there isn’t the market-awareness that running a business like this is viable, though there are some examples (e.g. [2pmlinks](https://2pml.com/) which is a paid email _newsletter_ but has a set of small-databases attached to it called their Executive Library with collections of things like indie media businesses or an agency index).  

是的，您今天可以使用 Memberful、Airtable 和 Substack 的组合来组装这个确切的商业模型，但是……。它很笨重。尽管有一些例子（例如 2pmlinks，这是一个付费电子邮件通讯，但有一组附加到它的小型数据库，称为他们的执行图书馆，其中包含独立媒体业务或代理索引之类的东西）。

## Conclusion: How can we let a thousand small libraries bloom?  

结语：如何让一千个小图书馆开花结果？

Depending on your mental model of the world, the shape of the data you want to work with, and your technical aptitude you might have strong reactions to this post. Things like “just use a real database!” or “no way!  

根据您对世界的心智模型、您要处理的数据的形状以及您的技术能力，您可能会对这篇文章产生强烈的反应。诸如“只需使用真实数据库！”之类的东西或“不可能！  

” or “This is missing the point” but I sincerely believe there is a whole set of publishing use cases waiting in the wings that are underserved today.  

”或“这没有抓住要点”，但我真诚地相信，有一整套出版用例正在等待今天的服务不足。

I want to empower more individuals to publish, maintain and collaborate on small indexes. To build a million tiny libraries, community databases, weird collections and indie indexes.  

我想让更多的人能够发布、维护和协作小型索引。建立一百万个小型图书馆、社区数据库、奇怪的收藏和独立索引。

___

This blog is written by Tom Critchlow, an independent strategy consultant living and working in Brooklyn, NY. If you like what you read please leave a comment below in disqus or sign up for my [Tinyletter](https://tinyletter.com/tomcritchlow).  

该博客由生活和工作在纽约布鲁克林的独立战略顾问 Tom Critchlow 撰写。如果您喜欢您阅读的内容，请在下面的 disqus 中发表评论或注册我的 Tinyletter。

___
