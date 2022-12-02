---
title: "再见，数据科学 – ryx, r"
date: 2022-12-03T01:15:16+08:00
updated: 2022-12-03T01:15:16+08:00
taxonomies:
  tags: []
extra:
  source: https://ryxcommar.com/2022/11/27/goodbye-data-science/?utm_source=hackernewsletter&utm_medium=email&utm_term=fav
  hostname: ryxcommar.com
  author: 
  original_title: "Goodbye, Data Science"
  original_lang: en
---

This is more of a personal post than something intended to be profound. If you are looking for a point, you will not find one here. Frankly I am not even sure who the target audience is for this (probably “data scientists who hate themselves”?).

这更像是一篇个人帖子，而不是意在深远的东西。 如果你正在寻找一个点，你不会在这里找到一个。 坦率地说，我什至不确定目标受众是谁（可能是“讨厌自己的数据科学家”？）。

I had been a data scientist for the past few years, but in 2022, I got a new job as a data engineer, and it’s been pretty good to me so far.

过去几年我一直是一名数据科学家，但在 2022 年，我找到了一份数据工程师的新工作，到目前为止对我来说还不错。

I’m still working alongside “data scientists,” and do a little bit of that myself still, but most of my “data science” work is directing and consulting on others’ work. I’ve be focusing more on implementation of data science (“MLops”) and data engineering.

我仍然和“数据科学家”一起工作，我自己也做一点，但我的大部分“数据科学”工作是指导和咨询其他人的工作。 我一直更关注数据科学（“MLops”）和数据工程的实施。

The main reason I soured on data science is that the work felt like it didn’t matter, in _multiple_ senses of the words “didn’t matter”:

我对数据科学感到厌恶的主要原因是，从 _的多种意义上来说，这项工作感觉并不重要：_ “无关紧要”这个词

-   The work is downstream of engineering, product, and office politics, meaning the work was only often as good as the weakest link in that chain.
-   这项工作处于工程、产品和办公室政治的下游，这意味着这项工作的好坏往往取决于该链条中最薄弱的环节。
-   Nobody knew or even cared what the difference was between good and bad data science work. Meaning you could absolutely suck at your job or be incredible at it and you’d get nearly the same regards in either case.
-   没有人知道甚至不关心数据科学工作好坏之间的区别。 这意味着你可能完全不擅长你的工作，也可能做得非常出色，而且在任何一种情况下你都会得到几乎相同的尊重。
-   The work was often very low value-add to the business (often compensating for incompetence up the management chain).
-   这项工作通常对业务的附加值很低（通常是为了弥补管理链上的无能）。
-   When the work’s value-add exceeded the labor costs, it was often personally unfulfilling (e.g. tuning a parameter to make the business extra money).
-   当工作的附加值超过劳动力成本时，个人通常不会感到满意（例如调整参数以使企业赚取额外收入）。

## Shitty management & insane projects

## 糟糕的管理和疯狂的项目

Management was by far my biggest gripe. I am completely exhausted by the absolute insanity that was the tech industry up to 2021. Companies all over were consistently pursuing things that could be reasoned about _a priori_ as being insane ideas– ideas any decently smart person should know wouldn’t work before they’re tried. Some projects could have saved whole person-years of labor had anyone possessed a better understanding of the business, customers, broader economic / social landscape, financial accounting, and (far too underrated in tech) any relevant subject matter areas.

到目前为止，管理是我最大的抱怨。 直到 2021 年，科技行业的绝对疯狂让我感到筋疲力尽。各地的公司都在不断追求可以被 _先验_ 推理为疯狂想法的东西——任何聪明人都应该知道的想法在他们之前是行不通的。重试。 如果任何人对业务、客户、更广泛的经济/社会格局、财务会计和（在技术上被低估的）任何相关主题领域有更好的了解，一些项目本可以节省整个人年的劳动时间。

Those who have seen my Twitter posts know that I believe the role of the data scientist in a scenario of insane management is not to provide real, honest consultation, but to launder these insane ideas as having some sort of basis in objective reality even if they don’t. Managers will say they want to make data-driven decisions, but they really want decision-driven data. If you strayed from this role– e.g. by warning people not to pursue stupid ideas– your reward was their disdain, then they’d do it anyway, then it wouldn’t work (what a shocker). The only way to win is to become a stooge.

那些看过我的 Twitter 帖子的人都知道，我认为数据科学家在疯狂管理场景中的作用不是提供真实、诚实的咨询，而是洗白这些疯狂的想法，使其具有客观现实的某种基础，即使他们不。 经理们会说他们想做出数据驱动的决策，但他们真的想要决策驱动的数据。 如果你偏离了这个角色——例如通过警告人们不要追求愚蠢的想法——你的回报是他们的蔑视，然后他们无论如何都会这样做，然后它就不会起作用（多么令人震惊）。 取胜的唯一方法就是成为走狗。

The reason managers pursued these insane ideas is partly because they are hired despite not having any subject matter expertise in business or the company’s operations, and partly because VC firms had the strange idea that ballooning costs well in excess of revenue was “growth” and therefore good in all cases; the business equivalent of the Flat Earth Society. It was also beneficial for one’s personal career growth to manage an insane project (résumé lines such as “managed $10 million in top-line revenue,” failing to disclose that their COGS was $30 million). Basically, there’s a decent reward for succeeding and no downside for failing, and sometimes you will even be rewarded for your failures! So why not do something insane?

经理们追求这些疯狂想法的部分原因是他们在没有任何业务或公司运营方面的专业知识的情况下被聘用，部分原因是风险投资公司有一个奇怪的想法，即膨胀的成本远远超过收入是“增长”，因此在所有情况下都很好； 相当于 Flat Earth Society 的企业。 管理一个疯狂的项目也有利于一个人的个人职业发展（诸如“管理 1000 万美元的最高收入”之类的简历，却没有透露他们的 COGS 为 3000 万美元）。 基本上，成功有可观的奖励，失败也没有坏处，有时你甚至会因为失败而得到奖励！ 那么为什么不做一些疯狂的事情呢？

Also, it seems that VC firms like companies to run the same way their portfolios do– they want companies to try 100 different things, and if only 5 out of those 100 things work, then the VCs will consider that a success. On the ground floor, this creates a lot of misery, since the median employee at the company is almost certainly working on a product that is not destined to perform well, but the shareholders are happy, which is of course all that matters.

此外，风险投资公司似乎喜欢公司以与他们的投资组合相同的方式运营——他们希望公司尝试 100 种不同的东西，如果这 100 种东西中只有 5 种有效，那么风险投资公司就会认为这是成功的。 在底层，这造成了很多痛苦，因为公司的中等员工几乎肯定在开发一种注定不会表现良好的产品，但股东很高兴，这当然是最重要的。

## Shitty code & shitty data science

## 糟糕的代码和糟糕的数据科学

The median data scientist is horrible at coding and engineering in general. The few who are remotely decent at coding are often not good at engineering in the sense that they tend to over-engineer solutions, have a sense of self-grandeur, and want to waste time building their own platform stuff (folks, do not do this).

一般来说，中等数据科学家在编码和工程方面很糟糕。 少数在编码方面表现得体的人往往不擅长工程，因为他们倾向于过度设计解决方案，有一种自我夸大的感觉，并且想浪费时间构建自己的平台（伙计们，不要这样做这个）。

This leads to two feelings on my end:

这导致我有两种感觉：

1.  It got annoying not having some amount of authority over code and infra decisions. Working with data scientists without having control over infra feels like wading through piles of immutable shit.
2.  It was obvious that there is a general industry-wide need for people who are good at both data science and coding to oversee firms’ data science practices in a technical capacity.

1.  没有对代码和基础设施决策的一定权力，这很烦人。 在无法控制基础设施的情况下与数据科学家合作感觉就像在一堆不变的狗屎中跋涉。
2.  很明显，整个行业普遍需要同时擅长数据科学和编码的人以技术能力监督公司的数据科学实践。

#### Poor mentorship

#### 指导不力

I don’t want to be _too_ snooty: in a sense, it’s fine for data scientists to suck at coding! Especially if they bring other valuable skills to the table, or if they’re starting out. And in another sense, bad code getting into production is a symptom of bad team design and management, more than any individual contributors’ faults! By describing the median data scientist’s coding skills as shitty, I’m just trying to be honest, not scornful.

我不想 _太_ 傲慢：从某种意义上说，数据科学家在编码方面表现不佳是可以的！ 特别是如果他们将其他有价值的技能带到桌面上，或者如果他们刚刚起步。 从另一种意义上说，投入生产的糟糕代码是团队设计和管理不当的症状，比任何个人贡献者的错误都要严重！ 通过将中等数据科学家的编码技能描述为低劣，我只是想说实话，而不是轻蔑。

The problem is that the median data scientist works at a small to medium-sized company that doesn’t build their data science practices around a conceit that the data scientists’ code will suck. They’d rather let a 23 year old who knows how to `pip install jupyterlab` run loose and self-manage, or manage alongside other similarly situated 23 year-olds. Where is the adult in charge?

问题在于，中等数据科学家在一家中小型公司工作，这些公司并没有围绕数据科学家的代码会很烂的自负来构建他们的数据科学实践。 他们宁愿让一个 23 岁的人知道如何 `pip install jupyterlab`放任自流，自我管理，或与其他处境相似的 23 岁年轻人一起管理。 负责的大人在哪里？

23 year-old data scientists should probably not work in start-ups, frankly; they should be working at companies that have actual capacity to on-board and delegate work to data folks fresh out of college. So many careers are being ruined before they’ve even started because data science kids went straight from undergrad to being the third data science hire at a series C company where the first two hires either provide no mentorship, or provide shitty mentorship because they too started their careers in the same way.

坦率地说，23 岁的数据科学家可能不应该在初创企业工作； 他们应该在具有实际能力的公司工作，可以将工作委托给刚从大学毕业的数据人员。 许多职业甚至还没有开始就被毁了，因为数据科学的孩子直接从本科生成为 C 系列公司的第三名数据科学雇员，前两名雇员要么不提供指导，要么提供糟糕的指导，因为他们也开始了他们的职业生涯以同样的方式。

#### Poor self-directed education

#### 自主教育差

On the other hand, it’s not just the companies’ and managers’ faults; individual data scientists are also to blame for being really bad at career growth. This is not contemptible for people who are just starting out their careers, but at some point folks’ résumés starts to outpace actual accumulation of skills and I cannot help but to find that a teeny bit embarrassing.

另一方面，这不仅仅是公司和管理者的错； 个人数据科学家也应该为职业发展的糟糕表现负责。 这对于刚刚开始职业生涯的人来说并不可耻，但在某些时候，人们的简历开始超过实际技能的积累，我不禁觉得有点尴尬。

It seems like the main career growth data scientists subject themselves to is learning the API of some gradient boosting tool or consuming superficial + shallow + irrelevant knowledge. I don’t really sympathize with this learning trajectory because I’ve never felt the main bottleneck to my work was that I needed some gradient boosting tool. Rather the main bottlenecks I’ve faced were always crappy infrastructure and lacking (quality) data, so it has always felt natural to focus my efforts toward learning that stuff to unblock myself.

数据科学家的主要职业发展似乎是学习一些梯度提升工具的 API 或消耗肤浅的+肤浅的+不相关的知识。 我并不真正认同这种学习轨迹，因为我从来没有觉得我工作的主要瓶颈是我需要一些梯度提升工具。 相反，我面临的主要瓶颈总是糟糕的基础设施和缺乏（质量）数据，所以我总是很自然地把精力集中在学习这些东西上来解除自己的障碍。

My knowledge gaps have also historically been less grandiose than learning how some state of the art language model works or pretending I understand some arXiv white paper ornate with LaTeX notation of advanced calculus. Personally, I’ve benefited a ton from reading the first couple chapters out of advanced textbooks (while ignoring the last 75% of the textbook), and refreshing on embarrassingly pedestrian math knowledge like “how do logarithms work.” Yeah I admit it, I’m an old man and I’ve had to refresh on my high school pre-calc. Maybe it’s because I have 30k Twitter followers, but I live in constant anxiety that someone will pop quiz me with questions like “what is the formula for an F-statistic,” and that by failing to get it right I will vanish in a puff of smoke. So my brain tells me that I must always refresh myself on the basics. I admit this is perhaps a strange way to live one’s life, but it worked for me: after having gauged my eyes out on linear regression and basic math, it’s shockingly apparent to me how much people merely pretend to understand this stuff, and how much ostensible interest in more advanced topics is pure sophistry.

从历史上看，我的知识差距也没有学习一些最先进的语言模型是如何工作的或者假装我理解一些 arXiv 白皮书华丽的 LaTeX 高级微积分符号那么宏伟。 就我个人而言，我从阅读高级教科书的前几章（同时忽略了教科书的最后 75%）以及“对数如何工作”等令人尴尬的乏味数学知识中受益匪浅。 是的，我承认，我是个老人，我不得不复习我的高中预科。 也许是因为我有 30k 的 Twitter 关注者，但我一直生活在焦虑之中，担心有人会突然问我“F 统计量的公式是什么”之类的问题，如果做错了，我就会消失得无影无踪烟雾。 所以我的大脑告诉我，我必须始终在基础知识上刷新自己。 我承认这可能是一种奇怪的生活方式，但它对我有用：在审视了线性回归和基础数学之后，我震惊地发现有多少人只是假装理解这些东西，又有多少表面上对更高级主题的兴趣纯属诡辩。

For the life of me I cannot see how reading a blog post that has sentences in it such as “DALL-E is a diffusion model with billions of parameters” would ever be relevant to my work. The median guy who is into this sort of superficial content consumption hasn’t actually gone through chapters in an advanced textbook in years if ever. Don’t take them at their word that they’ve actually grinded through the math because people lie about how well-read they are _all the time_ (and it’s easy to tell when people are lying). Like bro, you want to do stuff with “diffusion models”? You don’t even know how to add two normal distributions together! You ain’t diffusing shit!

对于我的生活，我看不出阅读一篇包含诸如“DALL-E 是一个具有数十亿参数的扩散模型”这样的句子的博客文章与我的工作有什么关系。 沉迷于这种肤浅内容消费的中等水平的人实际上已经很多年没有读过高级教科书中的章节了。 不要相信他们的话，他们实际上已经通过数学磨练了，因为人们一直在撒谎他们的阅读能力有多好 _（_ 而且很容易看出人们何时在撒谎）。 像兄弟一样，你想用“扩散模型”做事吗？ 您甚至不知道如何将两个正态分布相加！ 你不是在散播狗屎！

I don’t want to blame people for spending their free-time doing things other than learning how to code or doing math exercises out of grad school textbooks. To actually become experts in multiple things is oppressively time-consuming, and leaves little time for other stuff. There’s more to life than your dang job or the subject matters that may be relevant to your career. One of the main sins of “data scientist” jobs is that it expects far too much from people.

我不想责怪人们把空闲时间花在学习如何编码或根据研究生教科书做数学练习之外的事情上。 真正成为多方面的专家是非常耗时的，而且几乎没有时间做其他事情。 生活不仅仅是你该死的工作或可能与你的职业相关的主题。 “数据科学家”工作的主要错误之一是它对人们的期望太高。

But there’s also a part of me that’s just like, how can you not be curious? How can you write Python for 5 years of your life and never look at a bit of source code and try to understand how it works, why it was designed a certain way, and why a particular file in the repo is there? How can you fit a dozen regressions and not try to understand where those coefficients come from and the linear algebra behind it? I dunno, man.

但我也有一部分就像，你怎么能不好奇呢？ 你怎么能用 5 年的时间编写 Python 而从来不看一点源代码并试图理解它是如何工作的，为什么它是以某种方式设计的，以及为什么 repo 中的特定文件在那里？ 你怎么能拟合一打回归而不试图理解这些系数的来源及其背后的线性代数？ 我不知道，伙计。

Ultimately nobody really knows what they are doing, and that’s OK. But between companies not building around this observation, and individuals not self-directing their educations around this observation, it is just a bit maddening to feel stuck in stupid hell.

最终没有人真正知道他们在做什么，这没关系。 但是，在不围绕这一观察进行建设的公司，以及不围绕这一观察进行自我指导的个人之间，感觉陷入愚蠢的地狱有点让人抓狂。

## Data engineering has been relaxing

## 数据工程一直在放松

These are the things I’ve been enjoying about data engineering:

这些是我一直喜欢数据工程的事情：

-   Sense of autonomy and control.
    
    -   By virtue of what my job is, I have tons of control over the infrastructure.
    
    -   Data engineering feels significantly less subject to the whims and direction of insane management.
-   自主感和控制感。
    
    -   凭借我的工作，我对基础设施拥有大量的控制权。
    
    -   数据工程明显不受疯狂管理的突发奇想和方向的影响。
-   Less need for sophistry.
    -   My work is judged based on how good the data pipelines are, not based on how good looking my slide decks are or how many buzzwords I can use in a sentence. Not to say data engineering doesn’t have buzzwords and trends, but that’s peddled by SaaS vendors more than actual engineers.
-   不需要诡辩。
    -   我的工作是根据数据管道的好坏来判断的，而不是根据我的幻灯片有多好看或者我可以在一个句子中使用多少流行语。 并不是说数据工程没有流行语和趋势，但 SaaS 供应商比实际工程师更多地兜售这些。
-   More free time.
    -   I dunno, it feels like becoming a data engineer cured my imposter syndrome? I feel like I have more ability to dick around in my spare time without feeling inadequate about some aspect of my job or expertise. But this is probably highly collinear with not being a lackey for product managers.
-   更多空闲时间。
    -   我不知道，成为一名数据工程师感觉就像治愈了我的冒名顶替综合症？ 我觉得我有更多的能力在业余时间四处闲逛，而不会对我的工作或专业知识的某些方面感到不足。 但这可能与不成为产品经理的走狗高度一致。
-   Obvious and immediate value that is not tied to a KPI.
    
    -   I like being valued, what can I say.
    
    -   Ultimately the data scientists need me more than I need them; I’m the reason their stuff is in production and runs smoothly.
    -   I have a sense that, if my current place of business needed to chop employees, that it would be a dumb decision to chop me over any data scientist.
-   与 KPI 无关的明显且直接的价值。
    
    -   我喜欢被重视，我能说什么。
    
    -   最终，数据科学家比我需要他们更需要我； 我是他们的产品投入生产并顺利运行的原因。
    -   我有一种感觉，如果我目前的营业场所需要裁掉员工，那么裁掉我而不是任何数据科学家都是一个愚蠢的决定。
-   Frankly, I feel really good at what I do.
    -   As someone who has worked a variety of downstream data-related jobs, I have both a very strong sense of what my downstream consumers want, as well as the chops to QC/QA my own work with relative ease the way a good analyst would.
    -   At my last company I had a lot of “I could totally do a better job at designing this” feelings regarding our data stack, and it has immensely fed my ego to have confirmed all of these suspicions myself.
    -   This role gets to leverage basically everything I’ve learned in my career so far.
-   坦率地说，我对自己的工作感觉非常好。
    -   作为从事过各种下游数据相关工作的人，我对下游消费者的需求有着非常强烈的感觉，并且能够像优秀分析师一样相对轻松地对自己的工作进行质量控制/质量检查。
    -   在我上一家公司时，我对我们的数据堆栈有很多“我完全可以在设计这个方面做得更好”的感觉，这极大地满足了我的自我，让我自己证实了所有这些怀疑。
    -   这个角色基本上可以利用我迄今为止在职业生涯中学到的一切。

By far the most important thing here is the sense of independence. At this point it feels like the main person I should be complaining about is myself. (And self-loathing is so much healthier than hating a random product manager.) As long as my company’s data scientists are dependent on me to get code into production, I have veto power over a lot of bad code. So if they are putting bad code in production, that ultimately ends up being my fault.

到目前为止，这里最重要的是独立感。 在这一点上，我觉得我应该抱怨的主要人是我自己。 （自我厌恶比讨厌随机的产品经理要健康得多。）只要我公司的数据科学家依赖我将代码投入生产，我就对很多糟糕的代码拥有否决权。 因此，如果他们将错误的代码投入生产，那最终将是我的错。

I think my career trajectory made sense– there was no way I was hopping straight into data engineering and doing a good job of it without having done the following first:

我认为我的职业轨迹是有道理的——如果没有先完成以下工作，我就不可能直接进入数据工程并做好它：

-   See a few data stacks and form opinions about them as a downstream consumer.
-   作为下游消费者，查看一些数据堆栈并形成对它们的看法。
-   Get better at coding.
-   更好地编码。
-   Pick up on the lingo that data engineers use to describe data (which is distinct from how social scientists, financial professionals, data scientists, etc. describe data), like “entity,” “normalization,” “slowly-changing dimension type 2,” “CAP theorem,” “upsert,” “association table,” so on and so on.
-   了解数据工程师用来描述数据的术语（这与社会科学家、金融专业人士、数据科学家等描述数据的方式不同），例如“实体”、“规范化”、“缓慢变化的维度类型 2”， ”“CAP 定理”、“upsert”、“关联表”等等。

So, ultimately I have no regrets having done data science, but I am also enjoying the transition to data engineering. I continue to do data science in the sense that these roles are murkily defined (at both my “data scientist” and “data engineer” jobs I spend like 40% of the time writing downstream SQL transformations), I get to critique and provide feedback on data science work, and, hey, I actually _did_ deploy some math heavy code recently. Hell, you could argue I’m just a data scientist who manages the data science infra at a company.

所以，最终我并不后悔从事数据科学工作，但我也很享受向数据工程的过渡。 我继续从事数据科学，因为这些角色定义模糊（在我的“数据科学家”和“数据工程师”工作中，我大约 40% 的时间用于编写下游 SQL 转换），我开始批评并提供反馈关于数据科学工作，而且，嘿，我 _最近确实_ 部署了一些数学繁重的代码。 见鬼，你可能会说我只是一名在公司管理数据科学基础设施的数据科学家。

Anyway, great transition, would recommend for anyone who is good at coding and currently hates their data science job. My advice is, if you want to get into this from the data science angle, make sure you are actively blurring the lines between data science and data engineering at your current job to prepare for the transition. Contribute code to your company’s workflow management repo; put stuff into production (both live APIs and batch jobs); learn how to do CI/CD, Docker, Terraform; and form opinions about the stuff your upstream engineers are feeding you (what you do and don’t like and why). In fact it is very likely this work is higher value and more fun than tuning hyperparameters anyway, so why not start now?

无论如何，伟大的转变，会推荐给任何擅长编码但目前讨厌他们的数据科学工作的人。 我的建议是，如果你想从数据科学的角度进入这个领域，请确保你在当前工作中积极模糊数据科学和数据工程之间的界限，为过渡做好准备。 为贵公司的工作流管理仓库贡献代码； 将东西投入生产（实时 API 和批处理作业）； 学习如何进行 CI/CD、Docker、Terraform； 并对你的上游工程师提供给你的东西形成意见（你喜欢什么，不喜欢什么，为什么）。 事实上，这项工作很可能比调整超参数更有价值、更有趣，那么为什么不现在就开始呢？

Sorry, this post has no point, so it’s ending rather anticlimactically.

对不起，这篇文章毫无意义，所以它的结局相当虎头蛇尾。
