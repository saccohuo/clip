---
title: "关系型数据库优缺点"
date: 2022-12-23T13:17:10+08:00
updated: 2022-12-23T13:17:10+08:00
taxonomies:
  tags: []
extra:
  source: https://www.simplethread.com/relational-databases-arent-dinosaurs-theyre-sharks/
  hostname: www.simplethread.com
  author: Justin Etheredge
  original_title: "Relational Databases Aren’t Dinosaurs, They’re Sharks"
  original_lang: en
---

![Relational Databases Aren’t Dinosaurs, They’re Sharks](pexels-vanessa-mignon-7334926.jpg)

![关系数据库不是恐龙，它们是鲨鱼](pexels-vanessa-mignon-7334926.jpg)

Worried you’ll miss us?  
担心你会想念我们？  

Subscribe to get our articles and updates in your inbox.  
订阅以在您的收件箱中获取我们的文章和更新。  

> Oh relational databases, that tired old relic of another age. Codd and friends were great in their time, but serious software engineers need to move on.
> 
> 哦，关系数据库，另一个时代的旧遗物。 Codd 和他的朋友们在他们的时代很伟大，但严肃的软件工程师需要继续前进。
> 
> #### People building Web Scale™ software  
> 人们构建 Web Scale™ 软件  

You’ve probably heard a similar sentiment at some point. That relational databases were great, but they are dinosaurs that are slowly being replaced by non-relational databases because they just can’t keep up with the demands of modern companies.

你可能在某个时候听到过类似的情绪。关系数据库很棒，但它们是慢慢被非关系数据库取代的恐龙，因为它们无法满足现代公司的需求。

In other words, they don’t scale. They aren’t agile.  
换句话说，它们无法扩展。他们不敏捷。  

Some of these criticisms can be valid, but only in context.  
其中一些批评可能是有效的，但仅限于上下文。  

We don’t ask ourselves how a technology that has arguably had more performance work done on it than almost any other class of software can be so easily surpassed by brand new entrants into the market.

我们不会问自己，一项可以说在性能上比几乎任何其他类别的软件都完成了更多工作的技术怎么会如此轻易地被市场上的新进入者超越。

As Rich Hickey once said:  
正如 Rich Hickey 曾经说过的：  

> Programmers know the benefits of everything and the tradeoffs of nothing.
> 
> 程序员知道一切的好处和无所事事的权衡。

We see the amazing benchmarks that some NoSQL databases provide, and we say “wow, they are so much faster/better/scalable than relational databases.” But we don’t ask ourselves why.

我们看到一些 NoSQL 数据库提供的惊人基准，我们说“哇，它们比关系数据库快得多/更好/可扩展。”但我们不问自己为什么。

Instead of asking “how are they so much better?” we should be asking “what are they giving up?”

而不是问“他们怎么好多了？”我们应该问“他们放弃了什么？”

You see, relational databases aren’t dinosaurs. They aren’t lumbering prehistoric relics doomed to extinction by a changing world. They are sharks. Apex predators honed by millions of years of evolution into a perfectly adapted creature that is just as effective today as it was eons ago. There is a reason they are still around, and their supremacy in their domain hasn’t been questioned.

你看，关系数据库不是恐龙。他们不是笨拙的史前遗迹，注定要因不断变化的世界而灭绝。他们是鲨鱼。顶级掠食者经过数百万年的进化磨练成一种完美适应的生物，在今天和亿万年前一样有效。他们仍然存在是有原因的，他们在自己领域的至高无上的地位没有受到质疑。

### What Relational Databases Give Us  
关系数据库给了我们什么  

As a primer, most relational databases come with four primary guarantees:

作为入门，大多数关系数据库都有四个主要保证：

**Atomicity** – The guarantee that any series of operations within a transaction are treated as a single unit. The entire thing either succeeds or fails, and won’t leave you in an invalid state.

原子性——保证事务中的任何系列操作都被视为一个单元。整件事要么成功要么失败，不会让你处于无效状态。

**Consistency** – The guarantee that any operation against the database will leave it in a valid state.

一致性——保证对数据库的任何操作都会使其处于有效状态。

**Isolation** – The guarantee that any operations executed concurrently will leave the database in the same state as they would have if they were executed sequentially. Generally this means that transactions can’t see data being modified by other transactions.

隔离——保证并发执行的任何操作都会使数据库处于与顺序执行时相同的状态。通常这意味着事务看不到被其他事务修改的数据。

**Durability** – The guarantee that once a transaction is committed, it will stay committed, regardless of whether the system crashes or power fails.

持久性——保证一旦事务被提交，它将保持提交状态，无论系统是否崩溃或电源故障。

And finally, not a core ACID guarantee of relational databases, but there is another critical feature set around data integrity. Tools such as foreign keys, unique constraints, not null constraints, check constraints, etc. Combine these features with transactions, and you now have customizable logical guarantees about your data that your database will enforce.

最后，不是关系数据库的核心 ACID 保证，而是围绕数据完整性的另一个关键特性集。外键、唯一约束、非空约束、检查约束等工具。将这些功能与事务相结合，您现在可以对数据库执行的数据进行可定制的逻辑保证。

All of these guarantees come together to make writing reliable systems that keep consistent data a routine problem. Sure, there are still challenges around how and when to apply these tools, but when used correctly it makes keeping your data clean and consistent a tractable task.

所有这些保证结合在一起使得编写可靠的系统以保持一致的数据成为常规问题。当然，关于如何以及何时应用这些工具仍然存在挑战，但如果使用得当，它会使保持数据清洁和一致成为一项易于处理的任务。

### NoSQL Tradeoffs  
NoSQL 权衡  

In order to gain some of their superpowers, NoSQL databases generally make tradeoffs around these guarantees. Guarantees that a lot of software engineers take for granted, or don’t even know that they are leaning on.

为了获得一些超能力，NoSQL 数据库通常会围绕这些保证进行权衡。保证很多软件工程师认为是理所当然的，或者甚至不知道他们在依靠什么。

An acronym was created, BASE, to describe the operational characteristics and tradeoffs of most NoSQL databases.

创建了一个首字母缩略词 BASE 来描述大多数 NoSQL 数据库的操作特征和权衡。

**Basically Available** – The system can guarantee availability, as defined by the [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem), but by potentially trading off consistency.

基本可用——系统可以保证可用性，正如 CAP 定理所定义的那样，但可能会牺牲一致性。

**Soft State** – The database doesn’t enforce data consistency, and values may change without interaction, due to eventual consistency.

软状态——数据库不强制数据一致性，由于最终一致性，值可能会在没有交互的情况下发生变化。

**Eventual Consistency** – When data is written, it isn’t guaranteed to be immediately consistent to all database consumers. Generally speaking, it has to be replicated across all nodes in the database, which means that any reads occurring during that time could be inconsistent.

最终一致性——写入数据时，不能保证所有数据库消费者立即保持一致。一般来说，它必须跨数据库中的所有节点进行复制，这意味着在此期间发生的任何读取都可能不一致。

### NoSQL Advantages  
NoSQL 优势  

NoSQL databases are offering different performance characteristics than most relational databases. So let’s look at some of the advantages that non-relational databases advertise, and what tradeoffs they make in order to accomplish them:

NoSQL 数据库提供与大多数关系数据库不同的性能特征。因此，让我们看看非关系数据库宣传的一些优势，以及它们为实现这些优势所做的权衡：

**High Write Performance** – Many NoSQL databases advertise having incredible write performance. Relational databases have spent years optimizing the speed of writes, but their speed is limited by their durability and consistency guarantees. Relational databases can only write as fast as their persistent memory will allow them to. Or as fast as they can process transactions, indexes, and foreign keys (especially if they have to block). Throwing out guaranteed immediate persistence, not allowing transactions, not enforcing foreign keys, etc… can immediately enable huge gains in write performance.

高写入性能——许多 NoSQL 数据库都宣传具有令人难以置信的写入性能。关系数据库多年来一直在优化写入速度，但它们的速度受到持久性和一致性保证的限制。关系数据库只能按照其持久内存允许的速度写入。或者尽可能快地处理事务、索引和外键（尤其是当它们必须阻塞时）。放弃有保证的即时持久性、不允许事务、不强制执行外键等……可以立即实现写入性能的巨大提升。

**High Read Performance** – Many NoSQL databases have incredible read performance. This is often enabled due to balancing reads across a number of instances in a cluster, which provides high write performance, but generally gives up consistency due to eventual consistency. Many NoSQL databases also increase read performance by having simpler query syntaxes that don’t allow complex joins or queries across multiple “tables”, or whatever grouping mechanism they use.

高读取性能——许多 NoSQL 数据库具有令人难以置信的读取性能。这通常是由于在集群中的多个实例之间平衡读取而启用的，这提供了高写入性能，但通常由于最终一致性而放弃了一致性。许多 NoSQL 数据库还通过使用更简单的查询语法来提高读取性能，这些语法不允许跨多个“表”或它们使用的任何分组机制进行复杂的连接或查询。

**Easy Horizontal Sharding** – Sharding historically has been a huge pain point for relational databases. The primary reason is that by sharding data across a number of remote instances, you end up having to give up a lot of the consistency guarantees that relational databases provide. For example, what if you had a foreign key between two tables that are sharded across a number of different instances. In order to enforce that foreign key, you would have to scan every instance in the cluster to find the related data. By getting rid of these kinds of data consistency checks, you can much more easily shard data across large numbers of instances without running into huge performance bottlenecks.

简单的水平分片——历史上分片一直是关系数据库的一个巨大痛点。主要原因是，通过跨多个远程实例分片数据，您最终不得不放弃关系数据库提供的大量一致性保证。例如，如果您在跨多个不同实例分片的两个表之间有一个外键怎么办。为了强制执行该外键，您必须扫描集群中的每个实例以查找相关数据。通过摆脱这些类型的数据一致性检查，您可以更轻松地跨大量实例分片数据，而不会遇到巨大的性能瓶颈。

**Easy Schema Updates** – Many NoSQL databases make database modifications much easier by being “schemaless”. This usually means that whatever structure you put data into the system, it is simply stored in that way. So if you need to add a new field, you simply start saving data with that new field. If you want that field across all of your data, then you write a job to update every record and add that field. Relational databases, on the other hand, usually have strict schemas and require more complex operations to update schemas. Particularly when a database is under heavy load.

简单的模式更新——许多 NoSQL 数据库通过“无模式”使数据库修改变得更加容易。这通常意味着无论您将数据放入系统的何种结构，它都会以这种方式简单地存储。因此，如果您需要添加新字段，只需开始使用该新字段保存数据即可。如果您希望所有数据都有该字段，那么您可以编写一个作业来更新每条记录并添加该字段。另一方面，关系数据库通常具有严格的模式并且需要更复杂的操作来更新模式。特别是当数据库负载很重时。

**More Reliable, and Predictable, Performance** – NoSQL databases often have much more reliable and predictable performance. Most relational databases provide a lot of opportunities to degrade performance, usually by poorly performing queries. SQL is an incredibly powerful language, but knowing the pitfalls of it, and how your particular relational database performs under different circumstances can be challenging. I’ve seen many instances where small changes to a SQL query can increase its performance by a hundred fold. Many NoSQL databases dramatically simplify data access (sometimes by only allowing key based access), and instead choose to duplicate data in order to make it more easily queryable or export data to dedicated reporting databases.

更可靠、更可预测的性能——NoSQL 数据库通常具有更可靠、更可预测的性能。大多数关系数据库提供了很多降低性能的机会，通常是通过执行不佳的查询。 SQL 是一种非常强大的语言，但了解它的缺陷以及您的特定关系数据库在不同情况下的执行方式可能具有挑战性。我见过许多实例，其中对 SQL 查询的微小更改可以将其性能提高一百倍。许多 NoSQL 数据库极大地简化了数据访问（有时只允许基于密钥的访问），而是选择复制数据以使其更易于查询或将数据导出到专用报告数据库。

## Look for tradeoffs, not benefits  
寻找权衡，而不是利益  

Non-relational databases can scale because they frequently throw out a lot of the guarantees that made relational databases so powerful. Any time you make one of these tradeoffs, you’re moving the complexity from the database into your application. Features such as relational integrity and data consistency are a problem that software engineers often underestimate. It is easy to maintain data consistency in the happy path of your application, but the edge cases and failure cases are where you really get in trouble.

非关系数据库可以扩展，因为它们经常抛弃使关系数据库如此强大的许多保证。每当您做出这些权衡之一时，您就是在将复杂性从数据库转移到您的应用程序中。关系完整性和数据一致性等特性是软件工程师经常低估的问题。在您的应用程序的顺利路径中保持数据一致性很容易，但边缘情况和失败情况才是您真正遇到麻烦的地方。

At Simple Thread we often like to say that your application will get rewritten, but your data is forever. Keeping your data consistent, well structured, and clean is a huge task. Doing whatever you can to make that easier is often a worthwhile investment.

在 Simple Thread，我们经常喜欢说您的应用程序将被重写，但您的数据是永远的。保持数据一致、结构良好且干净是一项艰巨的任务。尽你所能让它变得更容易通常是一项值得的投资。

However, in some instances you might work with vast quantities of data, or deal with transactional systems that just don’t easily fit the operational limitations of relational databases. And in those cases, you should consider moving some, or all, of your data into a non-relational database. Just make sure that you’re looking for the tradeoffs, and not solely at the benefits, because relational databases are sharks. They evolved over a long period of time to be really amazing at storing large volumes of data and offloading a lot of the complex work of maintaining data integrity and consistency. They continue to evolve, taking on workloads that you’d traditionally expect from non-relational databases (think of Postgres’ [jsonb datatype](https://www.postgresql.org/docs/9.5/functions-json.html)).

但是，在某些情况下，您可能会处理大量数据，或者处理无法轻易满足关系数据库操作限制的事务系统。在这些情况下，您应该考虑将部分或全部数据移动到非关系数据库中。只要确保您正在寻找权衡，而不仅仅是利益，因为关系数据库是鲨鱼。它们经过很长一段时间的发展，在存储大量数据和卸载大量维护数据完整性和一致性的复杂工作方面确实令人惊叹。它们继续发展，承担您传统上期望来自非关系数据库的工作负载（想想 Postgres 的 jsonb 数据类型）。

The next time you hear someone describe relational databases as yesterday’s technology, or the next time you see someone assume a relational database can’t handle the needs of their unproven MVP, stop and ask them how they are going to account for the tradeoffs they’re making. Make sure they understand they aren’t skipping a dead dinosaur, they’re taking a pass on the thousands of human-years of effort that have made relational databases the sharks of the data industry.

下次您听到有人将关系数据库描述为过时的技术，或者下次您看到有人认为关系数据库无法满足他们未经证实的 MVP 的需求时，请停下来问问他们将如何权衡他们的权衡重新制作。确保他们明白他们不是在跳过死去的恐龙，他们是在传递数千年来使关系数据库成为数据行业鲨鱼的人类努力。

Loved the article? Hated it? Didn’t even read it?  
喜欢这篇文章？讨厌吗？甚至没读过？  

We’d love to hear from you.  
我们很乐意听取您的意见。  

[Reach Out 伸手](https://www.simplethread.com/contact)
