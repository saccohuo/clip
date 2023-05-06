---
title: "用API取代中层管理"
date: 2023-05-06T14:06:36+08:00
updated: 2023-05-06T14:06:36+08:00
taxonomies:
  tags: []
extra:
  source: https://rein.pk/replacing-middle-management-with-apis?ref=pt.plus
  hostname: rein.pk
  author: Peter Reinhardt
  original_title: "Replacing Middle Management with APIs by Peter Reinhardt"
  original_lang: en
---

本文讨论了硅谷创业公司在传统人力服务行业中创建软件层的趋势，这些软件服务雇佣大量人类工人，优化了他们的产出、生产力和质量，推动了价格下降。这些软件层通常有三个部分：面向终端客户的用户界面（UI），实际派遣人类工人的编程接口（API），工人有效执行任务的第二个接口。然而，这种趋势也带来了一些问题，例如人类工人成为机器中的齿轮，完全匿名化，而且软件层的引入使人们担心 5-20 年后的中期就业问题。

关键词：软件层、人类工人、API、自动化、就业问题、硅谷。

---

There’s a trend in Silicon Valley startups to create a software layer in industries that were traditionally pure human services.  

在硅谷的创业公司中，有一种趋势是在传统的纯人力服务行业中创建一个软件层。  

Uber and Lyft have created software layers in the taxi industry, 99designs Tasks in the visual design industry, Homejoy in the cleaning industry, and so on.  

Uber和Lyft在出租车行业创造了软件层，99designs Tasks在视觉设计行业，Homejoy在清洁行业，等等。  

These new software services employ armies of human workers, optimizing their output, productivity and quality while driving price down.  

这些新的软件服务雇佣了人类工人大军，优化了他们的产出、生产力和质量，同时推动了价格下降。

The software layer between the company and their armies of contractors eliminates a huge amount of middle management, and creates a worrisome disconnect between jobs that will be automated, and jobs of increasing leverage and value.  

公司和他们的承包商大军之间的软件层消除了大量的中间管理层，并在将被自动化的工作和越来越多的杠杆和价值的工作之间创造了一个令人担忧的脱节。

This software layer generally has three parts: the user interface (UI) for the end customer, a programming interface (API) that actually dispatches a human worker, and a second interface for the worker to execute the task efficiently.  

这个软件层通常有三个部分：面向终端客户的用户界面（UI），实际派遣人类工人的编程接口（API），以及工人有效执行任务的第二个接口。  

The API component is the interesting and slightly disturbing part.  

API组件是有趣的、略微令人不安的部分。

For example, Uber has a mobile app (UI) that talks to their servers (API).  

例如，Uber有一个移动应用程序（UI），与他们的服务器（API）对话。  

You can imagine that their servers effectively take three parameters: credit card, drive from, and drive to… and they dispatch a human to do it.  

你可以想象，他们的服务器有效地接受了三个参数：信用卡、开车来的、开车去的......并且他们派遣了一个人去做这件事。

```
uber.drive(card, pointA, pointB); // pseudocode obviously
```

What does that make the drivers? Cogs in a giant automated dispatching machine, controlled through clever programming optimizations like surge pricing?  

这让司机们怎么办？一个巨大的自动化调度机器中的齿轮，通过巧妙的编程优化（如激增定价）进行控制？  

Drivers have often told me that the job grants them incredible autonomy: they can drive whenever they feel like it, and they’ve stopped looking for jobs in finance or construction because the daily freedom is so valuable to them.  

司机们经常告诉我，这份工作赋予他们难以置信的自主权：他们可以随时开车，他们已经停止寻找金融或建筑业的工作，因为每天的自由对他们来说是如此宝贵。  

There’s liquidity in the marketplace that allows them to come and go as they see fit. But the actual driving is perfectly orchestrated by software, and it’s not a secret that Uber [intends to eventually replace all their drivers with self-driving cars](http://www.theverge.com/2014/5/28/5758734/uber-will-eventually-replace-all-its-drivers-with-self-driving-cars). I worry that the army of Lyft and Uber drivers is opting into an easy, and sometimes-intended-to-be-temporary, dead-end career path.  

市场上有流动资金，允许他们根据自己的需要来往。但实际驾驶是由软件完美安排的，而且Uber打算最终用自动驾驶汽车取代他们所有的司机，这并不是什么秘密。我担心，Lyft和Uber的司机大军正在选择一条简单的，有时是打算临时的，没有前途的职业道路。  

This may be ok at the moment for some drivers who enjoy driving and the flexibility of the job.  

目前，对于一些喜欢驾驶和工作灵活性的司机来说，这可能是可以的。  

But driving as an occupation will disappear practically overnight when self-driving cars hit the road.  

但是，当自动驾驶汽车上路时，驾驶作为一种职业几乎会在一夜之间消失。

Similarly, 99designs Tasks has a web interface for the customer to explain a simple and quick design task, plus an API to dispatch a visual designer to complete the task.  

同样，99designs Tasks也有一个网络界面，供客户解释一个简单而快速的设计任务，另外还有一个API来派遣一个视觉设计师来完成这个任务。  

At Segment we’ve actually built a [99designs Tasks API](https://github.com/segmentio/nightmare-swiftly) to create vector logos from an image url:  

在Segment，我们实际上已经建立了一个99designs Tasks API，以从图片网址中创建矢量标识：

```
99designs.logo(card, url); // pseudocode ;)
```

What’s bizarre here is that these lines of code directly control real humans. The Uber API dispatches a human to drive from point A to point B.  

这里的怪异之处在于，这些代码行直接控制着真正的人类。Uber的API派遣一个人从A点开车到B点。  

And the 99designs Tasks API dispatches a human to convert an image into a vector logo (black, white and color).  

而99designs的任务API会派遣一个人将图像转换为矢量标志（黑色、白色和彩色）。  

Humans are on the verge of becoming literal cogs in a machine, completely anonymized behind an API.  

人类即将成为机器中的文字齿轮，在API后面完全匿名化。  

And the companies that control those APIs have strong incentives to drive down the cost of executing those API methods.  

而控制这些API的公司有强烈的动机来降低执行这些API方法的成本。

In the long run there’s always something for people to work on and improve, but the introduction of this software layer makes we worry about mid-term employment 5-20 years out.  

从长远来看，人们总是有一些东西需要努力和改进，但这个软件层的引入使我们担心5-20年后的中期就业问题。  

Drivers are opting into a dichotomous workforce: the worker bees below the software layer have no opportunity for on-the-job training that advances their career, and compassionate social connections don’t pierce the software layer either.  

司机们正在选择进入一个二分法的劳动力：软件层下面的工蜂没有机会接受在职培训以促进他们的职业发展，而富有同情心的社会关系也不能刺穿软件层。  

The skills they develop in driving are not an investment in their future.  

他们在驾驶中培养的技能并不是对他们未来的投资。  

Once you introduce the software layer between “management” (Uber’s full-time employees building the app and computer systems) and the human workers below the software layer (Uber’s drivers, Instacart’s delivery people), there’s no obvious path upwards.  

一旦你在 "管理层"（Uber建立应用程序和计算机系统的全职员工）和软件层下面的人类工作者（Uber的司机，Instacart的送货员）之间引入软件层，就没有明显的上升通道。  

In fact, there’s a massive gap and no systems in place to bridge it.  

事实上，有一个巨大的差距，而且没有任何系统来弥补这个差距。

And I suspect these software layers will only get thicker.  

而且我怀疑这些软件层只会变得更厚。  

Entrepreneurial software developers will find ways to tie these APIs together, delivering products that combine several “human” APIs.  

创业型软件开发商将找到将这些API联系在一起的方法，提供结合了几个 "人类 "API的产品。  

Someone could use Mechanical Turk’s API to automate sales prospect research, plug that data into 99designs Tasks’ API to prepare customized infographics for the prospect sent via email.  

有人可以使用Mechanical Turk的API来自动进行销售前景研究，将这些数据插入99designs Tasks的API中，为潜在客户准备通过电子邮件发送的定制信息图。  

Or someone could use Redfin’s API to automatically purchase houses, and send a Zirtual assistant instructions via email on how to project-manage a renovation, flipping the house completely programmatically.  

或者有人可以使用Redfin的API自动购买房屋，并通过电子邮件向Zirtual助理发送关于如何对装修进行项目管理的指示，完全以编程方式翻转房屋。  

These “real-world APIs” allow complex programs (or an AI in the spooky storyline here), to affect and control things in the real-world. It does seem apropos that we [invest in AI safety](http://www.wired.com/2015/01/elon-musk-ai-safety/) now.  

这些 "现实世界的API "允许复杂的程序（或这里的诡异故事情节中的人工智能），影响和控制现实世界中的事物。我们现在投资于人工智能的安全似乎是恰当的。

As the software layer gets thicker, the gap between Below the API jobs and Above the API jobs widens.  

随着软件层越来越厚，API以下工作和API以上工作之间的差距也越来越大。  

And economic incentives will push Above the API engineers to automate the jobs Below the API: self-driving cars and drone delivery are certainly on the way.  

而经济激励措施将推动API工程师将API下面的工作自动化：自动驾驶汽车和无人机送货肯定在路上。  

The gap in training and social groups above and below could mean that new automation technology causes sudden, large-scale unemployment and a surge in demand for subsidized training.  

培训和社会群体上下的差距可能意味着新的自动化技术会造成突然的大规模失业和对补贴培训的需求激增。  

I hope we’re ready. 我希望我们已经准备好了。
