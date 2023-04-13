---
title: "与Steve Yegge讨论开发者生产力的全貌"
date: 2023-04-13T17:39:06+08:00
updated: 2023-04-13T17:39:06+08:00
taxonomies:
  tags: []
extra:
  source: https://newsletter.pragmaticengineer.com/p/steve-yegge
  hostname: newsletter.pragmaticengineer.com
  author: Gergely Orosz
  original_title: "The Full Circle on Developer Productivity with Steve Yegge"
  original_lang: en
---

_👋 Hi, this is [Gergely](https://twitter.com/gergelyorosz) with the monthly free issue of the Pragmatic Engineer Newsletter. In every issue, I cover challenges at Big Tech and high-growth startups through the lens of engineering managers and senior engineers.  

👋 大家好，我是Gergely，为大家带来每月一期的免费《实用主义工程师通讯》。在每一期中，我都会通过工程经理和高级工程师的视角，报道大科技公司和高增长初创公司的挑战。_

_If you’re not a subscriber, you missed the issue on [Inside Figma’s engineering culture](https://newsletter.pragmaticengineer.com/p/inside-figmas-engineering-culture) and [a few others](https://newsletter.pragmaticengineer.com/archive). Subscribe to get two full issues every week. Many subscribers expense this newsletter to their learning and development budget. If you have such a budget, here’s [an email you could send to your manager](https://docs.google.com/document/d/1BTgvFmpxNsJX6m9T6duRfZy4jD4CfcySVqoOGSe343I/edit?usp=sharing).👇  

如果您不是订阅者，您就错过了关于 Inside Figma 的工程文化和其他一些问题。订阅后可每周获得两期完整的期刊。许多订阅者将此通讯作为他们学习和发展预算的开支。如果你有这样的预算，这里有一封邮件，你可以发给你的经理。_

[Steve Yegge](https://www.linkedin.com/in/steveyegge) has been in the industry for more than 30 years, alternating between being a software engineer and an engineering manager.  

He worked at GeoWorks, Amazon, Google and Grab, and joined Sourcegraph as their Head of Engineering in October 2022. _We recently did a deep-dive on how Sourcegraph operates in the issue [Inside Sourcegraph’s engineering culture](https://newsletter.pragmaticengineer.com/p/inside-sourcegraphs-engineering-culture)._  

史蒂夫-耶格在业内工作了30多年，交替担任软件工程师和工程经理。他曾在GeoWorks、亚马逊、谷歌和Grab工作，并于2022年10月加入Sourcegraph，担任其工程主管。我们最近在《Sourcegraph的工程文化内幕》一文中对Sourcegraph的运作方式做了深入探讨。

Steve became prolific within several tech communities thanks to his writing, which is casual, funny and covers topics that few have written about candidly. In 2008, he wrote the blog post [Get that job at Google](http://steve-yegge.blogspot.com/2008/03/get-that-job-at-google.html). The blog post was one of the best preparation materials, at the time, for the Google software engineering interview.  

Coming from someone working at Google at the time, the advice was surprisingly candid.  

史蒂夫在几个科技社区中变得多产，这要归功于他的写作，他的写作很随意，很有趣，涉及的话题很少有人坦率地写过。2008年，他写了一篇博文《在谷歌得到那份工作》。这篇博文是当时谷歌软件工程面试的最佳准备材料之一。来自当时在谷歌工作的人，他的建议出乎意料地坦率。

Steve kept writing, although most of his writing stayed within the companies he worked at.  

Also in 2008 he wrote an internal rant at Google, explaining why, despite doing almost everything better than Amazon, Amazon still does something much better than Google: building platforms. The “rant” gave a history lesson of the platform evolution at Amazon, cracked several jokes, and turned into a heavy criticism of Google.  

To give a taste of [the style of this rant](https://gist.github.com/chitchcock/1281611):  

史蒂夫一直在写作，尽管他的大部分写作都停留在他所工作的公司内部。同样在2008年，他在谷歌写了一篇内部咆哮，解释了为什么尽管亚马逊几乎什么都做得更好，但亚马逊仍然比谷歌做得更好：建立平台。这篇 "咆哮 "给亚马逊的平台演变上了一堂历史课，开了几个玩笑，然后变成了对谷歌的严厉批评。为了让大家领略一下这个咆哮的风格：

> “So one day Jeff Bezos issued a mandate. (...) His Big Mandate went something along these lines:  
> 
> "所以有一天，杰夫-贝佐斯发布了一项任务。(......)他的大任务大致是这样的：
> 
> 1\. All teams will henceforth expose their data and functionality through service interfaces.  
> 
> 1.此后，所有团队将通过服务接口公开其数据和功能。
> 
> 2\. Teams must communicate with each other through these interfaces.  
> 
> 2.各小组必须通过这些接口相互沟通。
> 
> (...)
> 
> 6\. Anyone who doesn't do this will be fired.  
> 
> 6.任何不这样做的人都会被解雇。
> 
> 7\. Thank you; have a nice day!  
> 
> 7.谢谢你；祝你有个愉快的一天!
> 
> Ha, ha! You 150-odd ex-Amazon folks here will of course realize immediately that #7 was a little joke I threw in, because Bezos most definitely does not give a shit about your day.”  
> 
> 哈，哈!你们在座的150多位前亚马逊人当然会立即意识到，第7号是我抛出的一个小笑话，因为贝索斯绝对不关心你们的日子。"

I’ve been meaning to interview Steve right as I started my newsletter. However, back then, he was still retired.  

我一直想采访史蒂夫，就在我开始写通讯的时候。然而，那时，他还在退休状态。  

Since then, he came out of retirement, and I jumped at the opportunity to get to know more about Steve’s career and stories he has to share, and attempt to collect learnings that are both useful and inspiring for software engineers and engineering managers.  

此后，他从退休状态中走了出来，我抓住机会了解了更多关于Steve的职业生涯和他所要分享的故事，并试图收集对软件工程师和工程经理来说既有用又有启发性的经验。

1.  **Learning to code and GeoWorks.** Steve learned to code on a programmable HP scientific calculator. At his first job, at GeoWorks, he used the best debugger, to date—and that was 30 years ago!  
    
    The experience left an impression on him, and an appreciation for developer tools.  
    
    学习编码和GeoWorks。史蒂夫是在一个可编程的惠普科学计算器上学习编码的。在他的第一份工作中，在GeoWorks，他使用了迄今为止最好的调试器--那是30年前的事了这段经历给他留下了深刻的印象，也让他对开发工具有了深刻的认识。
    
2.  **Amazon and the customer obsession mindset.** He joined Amazon a year after their IPO, became a technical program manager (TPM), and returned to a manager role when he tried to go back to being an engineer.  
    
    亚马逊和迷恋客户的心态。他在亚马逊上市一年后加入亚马逊，成为技术项目经理（TPM），当他试图重新成为一名工程师时，又回到了经理的角色。
    
3.  **Google: 13 years at the company.** Steve started strong: shutting down Print Ads (the first project he joined) and upsetting people on the way. Leaving the company, he had some unlearning to do.  
    
    谷歌：在该公司工作了13年。史蒂夫开始时很强势：关闭了Print Ads（他加入的第一个项目），并在此过程中让人们感到不安。离开公司时，他有一些需要学习的地方。
    
4.  **Grab: accomplishing a lot, only with passion.** Steve’s first trip at Grab led to Southeast Asia, to experience the service, on the ground.  
    
    It was here that he considered that perhaps Google over-indexes on processes, which Grab had very little of, compared to the search giant.  
    
    Grab公司：只用激情就能完成很多事情。史蒂夫在Grab的第一次旅行是去东南亚，实地体验服务。正是在这里，他考虑到也许谷歌在流程方面的指数过高，而与搜索巨头相比，Grab的流程非常少。
    
5.  **Retiring from corporate: the good and the bad.** Taking two years off from being an employee, Steve could get to a lot of the non-tech stuff he always wanted to do.  
    
    从公司退休：好与坏。用两年时间不做雇员，史蒂夫可以去做很多他一直想做的非技术性工作。
    
6.  **Sourcegraph: bringing the customer-first mindset.** Observations about the company where Steve joined as Head of Engineering.  
    
    Sourcegraph：带来客户至上的思想。关于史蒂夫作为工程主管加入的公司的观察。
    
7.  **The full circle on developer tools.** What started at GeoWorks, in 1992 - working with amazing developer tools - is coming full circle, with Steve.  
    
    关于开发者工具的完整圆圈。1992年在GeoWorks公司开始的工作--使用令人惊奇的开发工具--在史蒂夫的带领下，正在走入一个完整的圈子。
    

_With this, over to Steve:  

有了这个，就交给史蒂夫了：_

When I was 17, I decided I wanted to figure this programming thing out. I had a programmable HP scientific calculator, and this was the only computer in my household.  

So I used this device to teach myself 3D programming. I ended up rendering the [Utah teapot](https://en.wikipedia.org/wiki/Utah_teapot), which is a famous 30,000 node image from the ‘70s. It took half an hour to render on that HP calculator!  

在我17岁的时候，我决定要把编程这件事搞清楚。我有一个可编程的惠普科学计算器，这是我家里唯一的电脑。所以我用这个设备来教我自己三维编程。我最后渲染了犹他州的茶壶，这是70年代著名的30000个节点的图像。在那台惠普计算器上花了半个小时的时间来渲染!

I was then at the Navy for a year, where I was a nuclear reactor operator. My dad kicked me out when I turned 17: he said that on my 18th birthday, I had to go and make it on my own.  

然后我在海军工作了一年，在那里我是一个核反应堆操作员。我父亲在我17岁时把我赶了出来：他说在我18岁生日时，我必须去自力更生。  

The Navy rolled out the red carpet for me, so that’s the way I went.   

海军为我铺上了红地毯，所以我就这样走了。

Following my years in the Navy,  I enrolled to study computer science at the University of Washington.  

在海军服役几年后，我报名参加了华盛顿大学的计算机科学学习。

**My first full-time job was at GeoWorks, building developer tools.** GeoWorks was an Alameda-based company building an operating system.  

They came to campus in Seattle, Washington, in 1992, and made higher offers than any of the other companies recruiting from my university.  

我的第一份全职工作是在GeoWorks公司，建立开发工具。GeoWorks是一家位于阿拉米达的建立操作系统的公司。1992年，他们来到华盛顿州西雅图的校园，并提出了比其他任何从我的大学招聘的公司更高的报价。

What really got me interested wasn’t just the money, but how different they were to the other companies.  

真正让我感兴趣的不仅仅是钱，而是他们与其他公司的不同之处。  

When IBM recruiters showed up on campus, they told students to show up in suits for their interviews. At GeoWorks, there was none of this.  

当IBM的招聘人员出现在校园里时，他们告诉学生要穿着西装去面试。在GeoWorks，这些都没有。  

They were hip, they were young, and they were one of the first truly “tech companies” - and I wanted to work for them.  

他们很时髦，很年轻，是第一批真正的 "科技公司 "之一，我想为他们工作。

GeoWorks built the GEOS 16-bit operating system in the ‘90s. This system was built in 8086 Assembly language, and the company was writing and maintaining millions of lines of Assembly code.  

GeoWorks在90年代建立了GEOS 16位操作系统。这个系统是用8086汇编语言构建的，该公司编写和维护了数百万行的汇编代码。  

Everything was Assembly: the operating system, the apps - you name it.  

所有东西都是大会的：操作系统、应用程序--你的名字。

**Tooling and developer productivity was incredible.** I saw the best debugger I’ve ever used at GeoWorks. To this day, I’ve yet to see a debugger do what theirs did back then: path choice on the fly, undo on the spot, or step an instruction backwards.  

Even now, none of these fancy debuggers are as powerful as what we had there.  

工具和开发人员的生产力是令人难以置信的。我在GeoWorks看到了我所使用过的最好的调试器。时至今日，我还没有看到一个调试器能像他们当时那样做：即时选择路径，当场撤销，或倒退一条指令。即使是现在，这些花哨的调试器也没有我们当时的调试器强大。

GeoWorks had a “Core Tools” team that was building world-class tools using extension languages like [Tcl](https://en.wikipedia.org/wiki/Tcl). We also had [Emacs](https://en.wikipedia.org/wiki/Emacs) gurus working there and I found it astonishing to watch how effective they are. That’s where I started to learn a new Emacs thing every day, and I’ve been doing this for years.  

GeoWorks有一个 "核心工具 "团队，正在使用Tcl等扩展语言构建世界级工具。我们也有Emacs大师在那里工作，看着他们的效率，我觉得很惊讶。我就是在那里开始每天学习Emacs的新东西的，我已经这样做了好几年了。

These highly effective engineers at GeoWorks introduced me to the notion that developers can be super-productive.  

GeoWorks公司的这些高效的工程师向我介绍了开发者可以是超级生产力的概念。

We worked at a low level at GeoWorks. We didn’t have “if” statements and we didn’t have variables: we had registers. We used Assembly, and I also learned Tcl, Perl, shell scripting and Awk.  

我们在GeoWorks的工作水平很低。我们没有 "if "语句，也没有变量：我们有寄存器。我们使用汇编，我还学习了Tcl、Perl、shell脚本和Awk。  

That was pretty much everything we used there.  

这几乎是我们在那里使用的所有东西。

Even though we used Assembly, people were both super-happy and super-productive. It was all because of our tooling and our very basic CI/CD system.  

尽管我们用的是Assembly，但人们还是非常高兴，也非常有成就感。这都是因为我们的工具和我们非常基本的CI/CD系统。  

Developer tools made all the difference in feeling like GeoWorks is nirvana for software engineers.  

开发者工具使我们感到GeoWorks是软件工程师的涅槃。

**You don’t appreciate developer tools until you don’t have them.** I recently heard someone who left Google say:   

除非你没有这些工具，否则你不会欣赏开发者工具。我最近听到一个离开谷歌的人说：

> “I didn’t understand why Stevey was ranting all the time about developer tools, when he was at Google. Now I get it, after I left.”  
> 
> "我不明白为什么Stevey在Google的时候，一直在对开发者工具进行咆哮。现在我明白了，在我离开之后。"

When you have great developer tools, it’s nirvana.  

当你拥有伟大的开发工具时，这就是涅槃。  

When you don’t have them, either you don’t know what you’re missing, or you’re lucky enough to work with some people who know what’s missing, and so they evangelize getting those developer tools in place.  

当你没有这些工具时，要么你不知道你缺少什么，要么你很幸运地与一些知道缺少什么的人一起工作，所以他们宣扬要把这些开发工具安装到位。

I joined Amazon in 1998, a year after their IPO. Amazon was a very hot company back then to work for. I was going to join as an engineering manager, but they talked me into being a [technical program manager (TPM)](https://newsletter.pragmaticengineer.com/p/what-tpms-do). Even then, Amazon had this role.  

我在1998年加入亚马逊，在他们上市后一年。亚马逊在当时是一家非常热门的工作公司。我本来打算以工程经理的身份加入，但他们说服我成为技术项目经理（TPM）。即使在那时，亚马逊也有这个角色。

So I joined as a TPM. I worked for [Kim Rachmeler](https://www.linkedin.com/in/kimrachmeler), who was the group program manager for TPM. She was a master at cross-functional execution. Amazon’s execution was world-class and TPMs were in the middle of it.  

This was when I learned the art of delivery.  

所以我作为TPM加入。我为Kim Rachmeler工作，她是TPM的集团项目主管。她是一位跨职能执行的大师。亚马逊的执行力是世界级的，而TPM就在其中。我就是在这个时候学会了交付的艺术。

**These days, I recommend software engineers become a TPM at one point in their career.** The TPM role exercises a muscle that we’re all using, but not very well: the management of cross-functional projects.  

As TPMs, we worked not just with engineering but also with customer service, distribution center folks, and a lot of other areas.  

如今，我建议软件工程师在其职业生涯的某个阶段成为一名TPM。TPM的角色锻炼了我们都在使用的肌肉，但不是很好：跨职能项目的管理。作为TPM，我们不仅与工程部门合作，还与客户服务部门、分销中心的人以及其他很多领域合作。

Being a TPM gave me a tremendous amount of insight into the whole organization.  

作为一名TPM，我对整个组织有了极大的了解。  

And when, a year later, I decided it was time for me to leave the TPM role behind, it was easy for me to find my next team - because I’d already been working with so many other teams already!  

一年后，当我决定是时候离开TPM的角色时，我很容易就找到了我的下一个团队--因为我已经和许多其他团队合作过了！  

It was pretty cool how easy it was to move back to being an engineering manager, after I was a TPM. And so I chose to join the customer service team.  

在我做过TPM之后，再转回做工程经理是很容易的事情，这很酷。因此，我选择加入客户服务团队。

While I was a TPM, I fell in love with the customer service team and their problem space.  

Amazon had a lot of cool things going on, but the customer service challenge was unique in a way that I’d never seen before. Jeff Bezos said, right from the start: “Customer service is going to be [a profit center](https://newsletter.pragmaticengineer.com/p/profit-centers-cost-centers). We’re not going to do QA (quality assurance): we’ll just mix things up if it happens, and then we’ll shower customers who had an issue with gift certificates and praise.”  

在我做TPM的时候，我爱上了客户服务团队和他们的问题空间。亚马逊有很多很酷的事情，但客户服务的挑战是独特的，是我以前从未见过的。杰夫-贝索斯从一开始就说，："客户服务将是一个利润中心。我们不打算做QA（质量保证）：如果发生这种情况，我们就把事情混过去，然后我们会用礼券和赞美来沐浴那些出现问题的顾客。"

But how would the customer service tooling be able to answer any question that customers had, and fix any of their issues? It had to become this horizontal system that wraps around all other systems.  

但客户服务工具如何能够回答客户的任何问题，并解决他们的任何问题？它必须成为围绕所有其他系统的横向系统。

In retrospect, the need for world-class customer service tooling was the beginning for service discovery, because on the customer service tooling team we needed to be able to find and talk with all the systems that other teams built.  

现在回想起来，对世界级客户服务工具的需求是服务发现的开始，因为在客户服务工具团队中，我们需要能够找到并与其他团队建立的所有系统对话。

**I tried to go back to being an individual contributor at Amazon, but got pulled back into engineering management shortly after.** I’ve noticed that this keeps happening throughout my career: it happened at Amazon, and it happened later at Google as well.  

I would be working as an IC for a little while, and then someone comes up and asks, “Hey, could you take on just this little team?” More teams follow after the first one, and after a while I have 70-100 people in my organization.  

It’s what happened at Amazon as well.  

我在亚马逊试图回到个人贡献者的身份，但不久后就被拉回了工程管理部门。我注意到，这种情况在我的职业生涯中不断发生：它发生在亚马逊，后来也发生在谷歌。我作为一个IC工作了一段时间，然后有人来问："嘿，你能不能只负责这个小团队？"在第一个团队之后，更多的团队接踵而来，过了一段时间，我的组织里有70-100人。这也是在亚马逊发生的事情。

Why did I keep getting pulled back into engineering management? Well, first, you have to decide whether you even want to be a leader. Most people don’t want to take on this role.  

为什么我一直被拉回到工程管理中？嗯，首先，你必须决定你是否想成为一个领导者。大多数人不愿意承担这个角色。  

Once you decide to give it a go, you’ve got to try it. There are a lot of people who thought they wanted to be a leader but ended up hating it.  

一旦你决定给它一个机会，你就得去尝试。有很多人认为他们想成为一名领导，但最后却讨厌它。

As for me, I don’t mind leading or managing. My problem is that I don’t truly love the leadership aspect the same way as some people do. For me, leadership is a means to an end.  

至于我，我不介意领导或管理。我的问题是，我并不像有些人那样真正热爱领导方面的工作。对我来说，领导是达到目的的一种手段。  

Over the past 30 years, I’ve gotten okay at it, but it’s not what gets me up in the morning.  

在过去的30年里，我在这方面做得还不错，但这并不是让我早上起床的原因。

What I get most excited about is the vision. It’s the building part. It’s the “Look, I’m going to do this by myself. Do you want to help?” feeling.  

我最兴奋的是愿景。这是建设的一部分。它是 "看，我将自己做这个。你想帮忙吗？"的感觉。

I’m good at pulling people with me to go and build something exciting.  

我很善于拉着人们一起去建造一些令人兴奋的东西。  

However, when it comes to the organizational side of things, I see myself as pretty average, and have to lean on my world-class support team to make it work.  

然而，当涉及到组织方面的事情时，我认为自己很一般，必须依靠我的世界级支持团队来使其发挥作用。

In the end, at Amazon, I spent about two years in customer service tools, then moved back into developer tools. By the time I left, I was running about half of the developer tools organization.  

最后，在亚马逊，我花了大约两年的时间在客户服务工具上，然后又转回了开发者工具。在我离开的时候，我已经管理了大约一半的开发工具组织。

**The one thing I learned at Amazon that really helped me later was the customer obsession mindset.** At Amazon, we were told that the customer is everything. This approach worked well for the company.  

And things later came full circle in a surprising way, when I was on the other side of this, when I worked at Grab.  

我在亚马逊学到的一件事，对我后来的发展有很大的帮助，那就是迷恋客户的心态。在亚马逊，我们被告知，客户就是一切。这种方法对公司来说很有效。后来，当我在Grab工作时，事情以一种令人惊讶的方式圆满结束，我站在了这个问题的另一边。

Grab was a customer of AWS, and being this customer was an unbelievable experience. The AWS team sat down with me and asked things like: “What do you need? What can we do for you?  

Grab是AWS的客户，而作为这个客户是一个令人难以置信的经历。AWS团队与我坐下来，问了一些问题，比如："你需要什么？我们能为你做什么？  

Would elastic indexes help your business case?” When I say they sat down with me, I don’t mean about an account executive or a customer agent.  

弹性指数是否有助于你的商业案例？"当我说他们与我坐下来时，我不是指关于客户经理或客户代理。  

It was with the PM for DynamoDB, the engineering manager and the general manager (GM) for DynamoDB.  

这是与DynamoDB的PM、工程经理和DynamoDB的总经理（GM）一起。

As they’re talking to me, I’m now looking over my shoulder, trying to second-guess where the important person is in the room.  

当他们和我说话的时候，我现在正在看我的肩膀，试图猜测房间里的重要人物在哪里。  

After all, as Grab, we were still a tiny customer, compared to, for example, Netflix - one of the large Amazon customers.  

毕竟，作为Grab，我们仍然是一个很小的客户，与例如Netflix--亚马逊的大客户之一相比。  

But it didn’t matter, as Amazon treated their enterprise customers like royalty.  

但这并不重要，因为亚马逊像对待皇室一样对待他们的企业客户。

This is an experience I am absolutely bringing to Sourcegraph as we work with our enterprise customers. Treating customers very well was a huge takeaway for me.  

当我们与企业客户合作时，我绝对会将这一经验带到Sourcegraph。非常好地对待客户是我的一个巨大收获。

_Read more insights about the TPM role in the issue [What TPMs do and what software engineers can learn from them](https://newsletter.pragmaticengineer.com/p/what-tpms-do), and about the culture at Amazon in [Inside Amazon’s engineering culture](https://newsletter.pragmaticengineer.com/p/amazon).  

在《TPM做什么以及软件工程师能从他们身上学到什么》一文中阅读更多关于TPM角色的见解，以及在《亚马逊的工程文化内幕》中阅读关于亚马逊文化的见解。_

I was happy at Amazon and had a lot of friends there. Things were going well. However, this strange thing happened. I kept losing more and more interns to Google.  

我在亚马逊很开心，在那里有很多朋友。事情进展得很顺利。然而，这种奇怪的事情发生了。我不断失去越来越多的实习生到谷歌。

At Amazon, I was a “Closer.” If anyone has an offer from another company, and they were leaning towards that other company, they’d bring me in and I’d close them on Amazon.  

在亚马逊，我是一个 "成交员"。如果有人收到其他公司的邀请，而他们又倾向于其他公司，他们会把我找来，让我在亚马逊上与他们成交。  

I had a pretty good track record on closing.  

我在关闭方面有相当好的记录。

However, we started losing interns, despite me doing the closing calls. To me, this felt like a canary in the coal mine. Why weren’t interns choosing Amazon?  

然而，我们开始失去实习生，尽管我在做关闭电话。对我来说，这感觉就像煤矿里的金丝雀。为什么实习生不选择亚马逊？

So I started to dig in. What was it about Google that these interns were more excited about than what we were doing?  

所以我开始深入了解。是什么让这些实习生对谷歌的工作比我们的工作更感兴趣？  

And the more I dug into this, the more I realized that I also wanted to work at Google.  

而我越是深入了解，就越是意识到我也想在谷歌工作。

When joining Google, I decided to start as an individual contributor this time.  

在加入谷歌时，我决定这次从个人贡献者开始。  

It would be one of those cases where I’d eventually be pulled back into management again, but I lasted longer than in the past: I was an IC for six years.  

这将是我最终再次被拉回管理层的情况之一，但我坚持的时间比过去更长：我做了6年的IC。

At Google, I first worked on an Ads project, then a music search project, and then I did [Grok](https://www.youtube.com/watch?v=KTJs-0EInW8) - a large-scale source code analysis project.   

在谷歌，我首先参与了一个广告项目，然后是一个音乐搜索项目，然后我做了Grok--一个大规模的源代码分析项目。

**I was an L7 at Amazon, and got hired as an L5 at Google.** L7 at Amazon maps roughly to Principal Engineer and L5 at Google Maps to Senior Engineer. And I can count myself lucky, because some of my peers came in at an even lower level.  

Google has always had a high hiring bar and was strict on levelling, and this was especially true back then.  

我在亚马逊是L7，在谷歌被聘为L5。在亚马逊，L7级大致相当于首席工程师，在谷歌，L5级相当于高级工程师。我可以说自己很幸运，因为我的一些同龄人是以更低的水平进来的。谷歌的招聘门槛一直很高，对水平的要求也很严格，这在当时尤其如此。

During my time at Google, I ended up getting two promotions, so I was L7 by the time I would leave. I probably could have been promoted more, if I’d decided to play the game.  

在谷歌工作期间，我最终得到了两次晋升，所以在我即将离开时，我已经是L7了。如果我决定玩这个游戏，我可能会得到更多的晋升。  

The thing is, it’s extremely difficult to break into the Director level (L8) at Google. To do this, it becomes a numbers game at one point. You have to have an organization of a certain size.  

问题是，在谷歌闯入总监级别（L8）是非常困难的。要做到这一点，在某一点上就变成了一个数字游戏。你必须有一个具有一定规模的组织。

Because getting to Director levels and your organization size are often connected, this leads to a lot of infighting. However, I was always giving teams away because I didn’t care about the promotion.  

因为升到主任级别和你的组织规模往往是相关的，这导致了很多内讧的发生。然而，我总是把团队拱手相让，因为我并不关心晋升。  

All my peers were directors, and I had an organization that was roughly the size of what directors would run. I just didn’t care about the title.  

我的同龄人都是主任，我有一个组织，其规模与主任所管理的组织大致相同。我只是不关心这个头衔。

**I killed my first project at Google: Print Ads.** I joined the Print Ads team, and within six months made the proposal to kill the project.  

I remember how Susan Wojcicki - who would later be the CEO of YouTube, from 2014 to 2023 - was particularly mad at me for doing this, because she thought that there was still a billion dollars lurking in this market.  

But I didn’t.  

我杀死了我在谷歌的第一个项目：印刷广告。我加入了Print Ads团队，并在6个月内提出了杀死这个项目的建议。我记得苏珊-沃西奇（Susan Wojcicki）--后来成为YouTube的首席执行官，从2014年到2023年--对我这样做特别生气，因为她认为这个市场中还潜藏着10亿美元。但我没有。

As I joined the Print Ads project, I had to become an ads demand expert, and so I did. For six months I worked hard on how to make the project succeed.  

由于我加入了印刷广告项目，我必须成为一个广告需求专家，于是我就这样做了。六个月来，我努力工作，研究如何使项目成功。  

Then, I wrote a detailed postmortem outlining the decision tree on why Print Ads couldn’t possibly work.  

然后，我写了一份详细的事后总结，概述了为什么印刷广告不可能成功的决策树。

The postmortem went along the lines of, “This is everything that we could think of trying, and here’s why it doesn’t come together.” The gist of the problem was that the industry feared and disliked Google, and the Google brand was the reason why Print Ads wouldn’t take off.  

事后总结是这样的："这是我们能想到的所有尝试，这就是为什么它没有成功。"问题的要点是，行业害怕和不喜欢谷歌，而谷歌品牌是印刷广告无法起飞的原因。

After I left the team, Google tried on two more occasions to get Print Ads working. They asked for my postmortem document both times, before giving up.  

在我离开团队后，谷歌又两次试图让印刷广告发挥作用。他们两次都要求提供我的验收文件，然后就放弃了。

You might find it strange that a software engineer could have this much impact: stopping an entire, potentially large initiative at a company like Google.  

你可能会觉得奇怪，一个软件工程师能产生这么大的影响：在谷歌这样的公司阻止整个潜在的大型计划。  

But don’t forget that this was during what I like to think of as the golden age of Google, around 2003-2008, when bottom-up innovation was happening everywhere.  

但是别忘了，这是在我认为是谷歌的黄金时代，大约在2003-2008年，当时自下而上的创新到处都在发生。

Just to illustrate how bottom-up we were, after I started on the Print Ads in the Seattle office, Larry and Sergey made a joint trip to this office.  

为了说明我们是如何自下而上的，在我开始在西雅图办公室做印刷广告后，拉里和谢尔盖共同去了这个办公室。  

Back then, the Seattle office was tiny, and only one floor. Larry and Sergey walked around, and when they got to our desks, they were like: “Hey, you’re the Publication Ads team?  

那时，西雅图的办公室很小，只有一层楼。拉里和谢尔盖走来走去，当他们走到我们的办公桌前时，他们就会说："嘿，你是出版广告组的？  

Are you getting the support you need out of the sales and product teams?”  

你是否从销售和产品团队那里得到了你需要的支持？"

We had the PM and the engineering manager around us as well, but they were looking at me, as I was the tech lead of the engineering team.  

我们周围也有项目经理和工程经理，但他们都在看我，因为我是工程团队的技术负责人。  

And I told them that I didn’t think we were getting the support because the sales teams wanted to go after the big customers, and we wanted to go after whoever could become long-term customers.  

我告诉他们，我认为我们没有得到支持，因为销售团队想去争取大客户，而我们想去争取谁能成为长期客户。

Larry then said: “Well, we want you to treat this like a startup. You’re running this. The engineering team does what the engineering team should do.”  

拉里接着说："好吧，我们希望你把这当成一个创业公司。你在经营这个。工程团队做工程团队应该做的事。"

They said all of this while also looking at the PM and the EM, who had previously been complaining that we - the engineering team - weren’t working on what they wanted us to do.  

他们在说这些话的同时也在看PM和EM，他们之前一直在抱怨我们--工程团队--没有在做他们希望我们做的事情。  

They sent a very clear signal that things were working bottom-up.  

他们发出了一个非常明确的信号，即事情正在自下而上地进行。

**Leaving Google, one thing I had to unlearn was creating barriers that prevented engineers from talking to customers.** If you are someone working at Google, this is something you can perhaps help fix.  

The really big issue that I now see is really hurting Google right now is that they’ve put so much process - and so many barriers and obstacles - in place that this gets in the way of engineers talking with customers.  

This is especially the case with Cloud. The engineers have no idea what the customers want.  

离开谷歌时，我必须解开的一件事是制造障碍，阻止工程师与客户交谈。如果你是在谷歌工作的人，这是你也许可以帮助解决的事情。我现在看到的真正的大问题是，他们已经把这么多的程序--以及这么多的壁垒和障碍--放在那里，这妨碍了工程师与客户交谈。这在云计算方面尤其如此。工程师们不知道客户想要什么。

Google’s engineering operates in a different plane of existence.  

谷歌的工程在一个不同的存在平面上运作。  

They tend to think, “How can we get this wonderful experience we have inside Google, to reach our customers?” However, this is a huge mismatch to what customers want.  

他们倾向于认为，"我们如何才能把我们在谷歌内部的这种美妙体验，传递给我们的客户？"然而，这与客户的需求有很大的不匹配。  

I don’t think Google has solved this mismatch and needs to listen to their customers more.  

我不认为谷歌已经解决了这种不匹配的问题，需要更多地倾听客户的意见。

When I joined Grab, I travelled to Southeast Asia to meet the team and experience their products first-hand. The experience on the ground was so wild that it’s hard for me to characterize it.  

当我加入Grab时，我前往东南亚与团队会面，并亲身体验他们的产品。实地的体验是如此狂野，以至于我很难给它定性。  

It’s like when Anthony Bourdain said that Tokyo is the world's biggest party and you're not invited. It felt like that.   

就像安东尼-布尔丹（Anthony Bourdain）说，东京是世界上最大的聚会，而你没有被邀请。这感觉就像这样。

Southeast Asia is just exploding. Just being there, in the center of all of it, was amazing.  

东南亚正在爆发。只是在那里，在所有这一切的中心，是惊人的。

Then, I talked to actual customers - to some of the drivers and couriers.  

然后，我与实际的客户交谈--与一些司机和快递员交谈。  

They would tell me how they were able to buy an Android phone for their kids, or a household utility, thanks to their earnings, and this was super-inspiring to see: how our product was making a difference.  

他们会告诉我，由于他们的收入，他们能够为他们的孩子买一部安卓手机，或者买一个家庭用品，看到这一点，我感到非常振奋：我们的产品是如何发挥作用的。

Being out there, in Southeast Asia, changed the way me and my team thought about things: both from a design perspective and from a technical one.  

在那里，在东南亚，改变了我和我的团队思考问题的方式：无论是从设计角度还是从技术角度。  

Customers and drivers were legitimately confused about things that we thought should have been obvious.  

客户和司机对我们认为应该是显而易见的事情感到困惑，这是合理的。

I ended up partially working on developer tooling at Grab as well. A person on my team built out a bunch of machine learning infrastructure to support personalization functionality.  

我最终也在Grab公司部分地从事开发者工具的工作。我团队中的一个人建立了一堆机器学习基础设施，以支持个性化功能。  

As part of this, I worked closely with the dev tools team at Grab there - to the point that this team asked me to become an honorary member of their team!  

作为其中的一部分，我与Grab公司的开发工具团队紧密合作--以至于这个团队要求我成为他们团队的荣誉成员！我的目标是成为他们的一员！

**What did my title of ‘Head of Engineering’ at Grab mean?** It was akin to the Director of Engineering role.   

我在Grab公司的 "工程主管 "头衔是什么意思？它类似于工程总监的角色。

I’m observing a move away from the Director title, across the industry, because this title tends to be more controversial.  

我观察到，在整个行业中，有一种远离主任头衔的趋势，因为这个头衔往往更具争议性。  

“Head of” better conveys the intent of the title: that this person is the leader of that space.  

"首长 "更好地传达了标题的意图：这个人是该空间的领导。  

Also, it makes it clear that you don’t need to be at a particular level to have this title: which is not true for Director. At Grab, Head of Engineering spans all the way from levels 7 to 9.  

此外，它还明确指出，你不需要达到某个特定级别就能拥有这个头衔：对于总监来说，这一点并不正确。在Grab公司，工程主管的级别从7级到9级都有。

**One learning from Grab was how much you can accomplish with just passion.** At Grab, the team was pretty junior. Of course, there were some very senior folks as mentors and guides, but the majority of the people were less experienced.  

从Grab学到的一个经验是，只要有激情就能完成很多事情。在Grab，团队的成员都很年轻。当然，有一些非常资深的人作为导师和向导，但大多数人的经验较少。

I think that Google over-indexes on things like code health, processes, and repeatability. Contrast this with Grab, and companies similar to Grab.  

我认为，谷歌在代码健康、流程和可重复性等方面的指数过高。这与Grab以及与Grab类似的公司形成鲜明对比。  

Those scaleups get stuff done in a scrappy way, and I admire how they do this.  

这些规模化的企业以一种潦草的方式完成了任务，我很钦佩他们的做法。

**Ultimately, I realized that it was a mistake to sign up for a job that was 17 time zones away.** I got to the point where I was travelling eight times a year to Southeast Asia, pulling 13 to 14-hour days for months and it simply wasn’t sustainable.  

I learned that if you need to lead teams in Asia, go to Asia.  

最终，我意识到，签下一份相隔17个时区的工作是个错误。我到了这样的地步：我每年要到东南亚出差八次，连续几个月每天工作13到14个小时，这根本无法持续。我了解到，如果你需要在亚洲领导团队，就去亚洲。

This was the main reason I ended up leaving Grab. I left in 2020 and knew that I needed a long-term recharge.  

这是我最终离开Grab的主要原因。我在2020年离开，知道自己需要长期充电。

For the most part, I just laid and recovered during the pandemic. I worked on a side project of mine - a game called [Wyvern](https://www.ghosttrack.com/) - and made some nice progress. However, really, I just needed a break.  

在大多数情况下，我只是在大流行期间躺在床上恢复。我在做我的一个副业--一个叫Wyvern的游戏--并取得了一些不错的进展。然而，说真的，我只是需要休息一下。

Once I finished recovering, I started getting antsy, thinking about all the kinds of things I could be doing. I did [my YouTube channel](https://www.youtube.com/user/steveyegge) for fun, as an experiment. My favorite episode of the ones I recorded is [the one on Emacs](https://www.youtube.com/watch?v=lkIicfzPBys). I loved how many people it resonated with. I don’t think people realized that I was showcasing the same experience I had back in 1992, when I observed software engineers at GeoWorks using Emacs.  

People were commenting, saying, “What, you can do that??” It was so cool to get this reaction.  

一旦我完成了恢复，我开始变得焦躁不安，思考我可以做的所有种类的事情。我做YouTube频道是为了好玩，作为一个实验。在我录制的节目中，我最喜欢的一集是关于Emacs的那集。我喜欢它引起了多少人的共鸣。我认为人们没有意识到，我展示的是我在1992年时的经历，当时我在GeoWorks观察软件工程师使用Emacs。人们评论说："什么，你能做到吗？"得到这种反应真是太酷了。

Because we were in the middle of the pandemic, I didn’t have much to do. Had it not been for this, I would have had a lot of fun going out, meeting people, and travelling around this time.  

因为我们当时正处于大流行病中，我没有什么事情可做。如果不是这样，我在这段时间里会有很多乐趣，可以出去玩，认识人，旅行。  

As the pandemic has eased, I have been making up for lost time and grabbing coffee with lots of people, though.  

随着大流行病的缓解，我一直在弥补失去的时间，和很多人一起喝咖啡。

Then, the founders of Sourcegraph, Quinn and Beyang, reached out to me through Maxim Fateev, who is the cofounder of Temporal.  

然后，Sourcegraph的创始人Quinn和Beyang通过Maxim Fateev联系到我，他是Temporal的联合创始人。  

I knew Maxim because he was friends with Nikolay Sokratov, whom I worked with at Grab.  

我认识马克西姆是因为他是尼古拉-索克拉托夫的朋友，我在格拉布公司与他共事。  

As I talked to them, I realized I had unfinished business around developer tooling, and it was a no-brainer for me to join.  

当我与他们交谈时，我意识到我在开发人员工具方面还有未完成的工作，对我来说，加入他们是不难的。

**What were the good and bad things about my “retirement?”** The good thing was that I needed the break. I also had enough non-tech stuff to do that it felt to me that it was time to start with all of that. I was pretty happy, overall.   

我的 "退休 "有什么好处和坏处？好处是我需要休息。我也有足够的非技术性工作要做，我觉得是时候开始做这些工作了。总的来说，我很高兴。

What was not so good is how “retiring” made me a bit lazy. Since I “un-retired,” I got back to the person that I was before. I’m passionate and excited, working hard.  

不太好的是，"退休 "让我变得有点懒惰。自从我 "解除退休 "后，我又回到了以前的那个我。我充满激情和兴奋，努力工作。  

I get fired up just by coming back to work on something that’s fun. I can now see this difference.  

只要回到工作岗位上，我就会被激起兴趣，做一些有趣的事情。我现在可以看到这种差异。

Honestly, I doubt any company other than Sourcegraph could have pulled me out of retirement.  

说实话，除了Sourcegraph，我怀疑任何公司都能把我从退休中拉出来。

Why did I join Sourcegraph? After all, I’d worked at places like Amazon and Google before. Could a company become as big as Google has?  

我为什么要加入Sourcegraph？毕竟，我以前在亚马逊和谷歌等地方工作过。一个公司能不能像谷歌那样成为大公司？

Personally, I’m skeptical that any company will be able to grow to Google’s size, once the FTC passes new anti-trust regulation.  

就个人而言，我对一旦联邦贸易委员会通过新的反垄断法规，任何公司都能发展到谷歌的规模持怀疑态度。  

So we might have already lived through a unique period where we had these giant tech companies, right? However, there will be new tech giants.  

因此，我们可能已经经历了一个独特的时期，我们有这些巨型科技公司，对吗？然而，会有新的科技巨头出现。  

We always think that we’re done, but there are new companies which are born, and which grow.  

我们总是认为我们已经完成了，但是有一些新的公司诞生了，而且还在成长。

Developer tools is an area that’s is not understood well enough, anywhere. This is the one theme that’s persisted through my career: I kept getting back to working on dev tools, again and again.  

开发者工具是一个没有被充分理解的领域，在任何地方都是如此。这是我职业生涯中一直存在的一个主题：我不断地回到开发工具的工作中去，一次又一次。

**Sourcegraph is surprisingly open.** Their model isn’t that different from that of DataStax or similar companies. It’s open source with an enterprise SaaS model.  

Sourcegraph的开放程度令人惊讶。他们的模式与DataStax或类似公司的模式没有什么不同。它是具有企业SaaS模式的开源产品。

Where Sourcegraph takes the part of being open a lot further than any other company is how they’re open about their corporate practices and their philosophies and values.  

A lot of these are spelled out in great detail [in their handbook](https://handbook.sourcegraph.com/) - which is also in the open. This handbook contains things that most other companies would consider proprietary and confidential.  

Sourcegraph在开放方面比其他公司走得更远，他们对自己的企业做法、理念和价值观进行公开。其中很多内容在他们的手册中都有详细说明--该手册也是公开的。这本手册包含大多数其他公司会认为是专有和机密的东西。

Because of this open nature, we’re able to talk in the open about our planning process, thought process, and even strategic processes.  

由于这种开放的性质，我们能够公开谈论我们的规划过程、思考过程，甚至战略过程。  

Other companies might go, "Oh gosh, what if somebody fast-follows my strategy first and we lose?" At Sourcegraph, we don’t worry about this because we’re in it for the long game.  

其他公司可能会说："哦，天哪，如果有人先快速跟进我的战略，我们就输了怎么办？"在Sourcegraph，我们不担心这个问题，因为我们是为了长期的游戏。  

We know that by being open, we’re going to win, and we’ll win partially because of this openness.  

我们知道，通过开放，我们会赢，而我们会赢的部分原因是这种开放性。

**How do we bring the customer-first mindset to Sourcegraph?** The good news is that it’s already happening. But we’re also looking into programs where engineers get to work directly with a customer.  

I’d like to model how Amazon and Grab both handled their customer engagement, above a certain employee seniority level.  

For example, at Grab, at the senior engineer and above levels, we of course took the Grab rides, ordered the Grab food, and used Grab pay.  

But we also had to sit down with the drivers and talk with them about their experience.  

我们如何将客户至上的思想带到Sourcegraph？好消息是，这已经在发生了。但我们也在研究一些项目，让工程师直接与客户一起工作。我想模仿亚马逊和Grab都是如何处理他们的客户参与，超过一定的员工资历水平。例如，在Grab，在高级工程师及以上级别，我们当然会乘坐Grab的车，订购Grab的食物，并使用Grab的付款。但我们也必须与司机坐下来，与他们讨论他们的经验。

At Amazon, as engineers, Bezos would send us off to call centers and watch the customer support representatives answering customer emails.  

在亚马逊，作为工程师，贝索斯会把我们送到呼叫中心，看着客户支持代表回答客户的电子邮件。  

I’d sit there and panic, thinking we need to fix that bug that I saw our system do.  

我坐在那里惊慌失措，认为我们需要修复那个我看到我们的系统做的错误。  

This was because it was painstaking to see the representative have to work around a small bug: that small bug causing a lot of headache for them.  

这是因为看到代表们不得不围绕着一个小的错误工作是很痛苦的：这个小的错误给他们带来了很多头痛的问题。

My old boss, Mark Porter, was the CTO at Grab, and he said something I still remember:  

我的老上司马克-波特(Mark Porter)是Grab公司的首席技术官，他说过一句话，我至今还记得：

> “You know those _rough_ edges of our product we always talk about? When you’re a customer, they become _sharp_ edges.”  
> 
> "你知道我们的产品的那些粗糙边缘，我们总是在谈论？当你是一个客户时，它们就变成了锋利的边缘。"

**So why do most companies not expose software engineers to customer support?** It’s a proven recipe that exposing engineers to customers works, after all. It worked very well for Amazon, and it worked for Grab too.  

那么，为什么大多数公司不让软件工程师接触客户支持？毕竟，将工程师暴露在客户面前是行之有效的秘诀。它对亚马逊非常有效，对Grab也很有效。

But here’s the thing. Companies generally have a budget in how much they invest into things that they really don’t want to do. Take, for example, interviewing.  

但事情是这样的。公司一般都有一个预算，即在他们真正不想做的事情上投入多少资金。例如，以面试为例。  

Most companies conduct pretty standard interviews, and know that they don’t get very good signals from here.  

大多数公司进行相当标准的面试，并知道他们从这里得不到很好的信号。

A company that interviewed differently, and had a very high hiring bar, was GeoWorks.  

有一家公司的面试方式不同，而且招聘标准很高，它就是GeoWorks。  

GeoWorks required people to do a six-month callout before getting a full-time offer, meaning it could gather more signal than most companies could dream of gathering, before offering the candidate a full-time position.  

GeoWorks公司要求人们在获得全职工作之前做六个月的呼唤，这意味着在向候选人提供全职职位之前，它可以收集比大多数公司梦想的更多信号。

Most companies, however, under-invest in things. They under-invest in hiring and they under-invest in things like developer tools.  

然而，大多数公司在某些方面投资不足。他们在招聘方面的投资不足，他们在开发工具等方面的投资不足。

You can get ahead of your competition by breaking out from what everyone else is doing. For example: invest in engineers meeting with customers. Let’s say they do this two weeks every year.  

你可以通过突破别人的做法，在竞争中取得领先。例如：投资于工程师与客户的会面。比方说，他们每年有两个星期这样做。  

Sure, they’ll take a productivity hit, but they’ll build up empathy for customers. The problem starts to become how we’re not good at measuring intangible results such as these.  

当然，他们的生产力会受到影响，但他们会建立起对客户的共鸣。问题开始变成我们不善于衡量诸如这些无形的结果。

**What things am I excited about, at Sourcegraph?** For code search, I think that Sourcegraph is already a lot better than anything else out there. With code intelligence, we’re connecting dots that previously weren’t connected.  

在Sourcegraph，我对哪些事情感到兴奋？对于代码搜索，我认为Sourcegraph已经比其他任何东西好得多。通过代码智能，我们正在连接以前没有连接的点。

The intelligence platform is one that will power better code reviews and enable massive refactorings to be done quickly.  

这个智能平台将为更好的代码审查提供动力，并使大规模的重构得以快速完成。  

It’s one that will power lightweight IDEs (integrated development environments).  

这是一个将为轻量级IDE（集成开发环境）提供动力的。

Take Google as an example of investing in code intelligence.  

以谷歌为例，投资于代码智能的例子。  

The developer tooling ecosystem at Google is huge, and yet it’s likely Google doesn’t have more than a handful of people working on this problem space.  

谷歌的开发者工具生态系统非常庞大，但谷歌在这一问题领域的工作人员可能不超过几个人。  

Compared to how much effort we’ll spend on this area at Sourcegraph, Google’s investment looks minimal.  

与我们在Sourcegraph花在这个领域的努力相比，谷歌的投资看起来微不足道。  

And it makes sense for Google - because the decision maker deciding on the budget will be constrained.  

而且这对谷歌来说是有意义的--因为决定预算的决策者会受到限制。

**Taking a step back: code has become “Big Data.”** This is a broader trend that I’m seeing. We have customers that have hundreds of thousands of git repositories. They have a data management nightmare.  

Code has become as bad as data lakes were 5-10 years ago, and this problem space is on fire.  

退一步讲：代码已经成为 "大数据"。这是我看到的一个更广泛的趋势。我们的客户有几十万个git存储库。他们有一个数据管理的噩梦。代码已经变得和5-10年前的数据湖一样糟糕，而这个问题的空间正在火热。

Companies solving this problem will rise to the occasion. So many tech companies are struggling with problems thanks to the scale of their codebase. And IDEs are not helping solve this problem.  

解决这个问题的公司将迎难而上。由于代码库的规模，许多科技公司都在为问题而挣扎。而IDE并没有帮助解决这个问题。

This is one reason why companies turn to us. And whatever we do, we’ll prioritize based on the needs of our customers. We have this incredible code intelligence solution that’s scalable.  

这就是企业转向我们的原因之一。而无论我们做什么，我们都会根据客户的需求来确定优先次序。我们有这种令人难以置信的代码智能解决方案，是可扩展的。  

We’ll figure out the right ordering of work we do, but we’ll do it by working with customers.  

我们会弄清楚我们所做的工作的正确顺序，但我们会通过与客户合作来做到这一点。

Here’s an example of something we’ll eventually do. Wiring up the stack trace in the production log, so that it maps to the line of code that caused the outage, is something we did at Google.  

这是一个我们最终要做的事情的例子。将生产日志中的堆栈跟踪连接起来，使其与导致中断的代码行相对应，这是我们在谷歌所做的事情。  

It was super-useful when it worked. This is something we have the capability to do, and something that would be really useful at most companies.  

当它工作时，它是超级有用的。这是我们有能力做的事情，也是对大多数公司非常有用的事情。

And then we’re just scratching the surface. Think about the dynamic runtime data we could bring in, even to improve search quality.  

然后，我们只是抓到了表面。想想我们可以引入的动态运行时数据，甚至是为了提高搜索质量。  

For example, could you add developers voting on search results as an additional user signal, or find other clever ways to turn all this data into something that’s even more useful?  

例如，你能不能在搜索结果上增加开发者的投票，作为一个额外的用户信号，或者找到其他聪明的方法，把所有这些数据变成更有用的东西？

We’re facing a vast and unexplored problem space with large codebases. As long as we think about this as a Big Data problem, I expect to see unbelievable innovation in this space.  

我们正面临着一个巨大的、未曾探索过的问题空间，有大量的代码库。只要我们把这个问题看作是大数据问题，我期望在这个领域看到令人难以置信的创新。

**So what comes after code intelligence?** I’m gonna say the same thing I told people at Sourcegraph on my second day.  

那么，代码智能之后是什么？我想说的是我在Sourcegraph第二天告诉人们的同样的话。

If you look at dev tools, they are tools. Let’s call them hammers and saws. Well, Sourcegraph is a flashlight.  

如果你看一下设计工具，它们就是工具。让我们称它们为锤子和锯子。那么，Sourcegraph就是一个手电筒。  

You can turn this flashlight on and off, you can make it light a large area with weak light, and you can also make it tight and focused.  

你可以打开和关闭这个手电筒，你可以让它用微弱的光线照亮一大片区域，你也可以让它紧张和集中。

Right now, Sourcegraph is the unfocused and large version of this flashlight.  

现在，Sourcegraph是这个手电筒的非重点和大型版本。  

Code intelligence is best of class with amazing coverage, but the experience is not nearly as good as if you’re inside an IDE.  

代码智能是同类中最好的，具有惊人的覆盖率，但体验还不如你在集成开发环境中的好。

At Google, we turned this flashlight into a laser pointer and shined it around this dark cavern of unexplored space of code intelligence.  

在谷歌，我们把这个手电筒变成了激光指示器，并在代码智能的这个黑暗的洞穴未开发的空间里照亮它。  

We found interesting things that you’ll also see coming out of Sourcegraph in the future.   

我们发现了一些有趣的事情，你也会在未来看到Sourcegraph的出现。

While building new things, we had our share of misses on the way. For example, we’d build features like, “Maybe our users would want to query these cases” - and then nobody used that feature.  

在构建新事物的过程中，我们也有过失误的时候。例如，我们建立的功能是："也许我们的用户会想要查询这些案例" - 然后没有人使用这个功能。

Still, I feel that most people think that we’re done with IDEs, because IDEs have barely changed in 25 years.  

不过，我觉得大多数人认为我们已经完成了IDE，因为IDE在25年里几乎没有变化。  

However, with the machine learning stuff that’s coming out in code search, this is just the beginning.  

然而，随着机器学习的东西在代码搜索中的出现，这只是一个开始。  

I’m not just talking about what we’re seeing with GitHub Copilot, but all the things that will follow.  

我说的不仅仅是我们所看到的GitHub Copilot，而是所有后续的东西。

Code intelligence is going to transform the whole toolchain, and Sourcegraph will be at the center of this.  

代码智能将改变整个工具链，而Sourcegraph将是其中的中心。

**Nobody had done dev tools right, and only Google has gotten close to getting it right.** Google’s internal developer ecosystem is as close as it gets to getting developer tooling _almost_ right. This is also why many former Google engineers go off to other companies to try and copy parts of it.  

However, most companies just can’t get behind a Herculean effort like this, and they’re asking: why? Why would we invest so much into dev tooling?  

没有人把开发工具做得很好，只有谷歌已经接近于把它做对。谷歌的内部开发者生态系统是最接近于把开发者工具做得差不多的。这也是为什么许多前谷歌工程师去了其他公司，试图复制其中的一部分。然而，大多数公司就是不能支持这样一个巨大的努力，他们在问：为什么？为什么我们要在开发工具上投资这么多？

I realized that big companies are not capable of getting developer tooling right. Google is not capable, Amazon is not capable, and neither is Netflix.  

我意识到，大公司没有能力把开发人员的工具搞好。谷歌没有能力，亚马逊也没有能力，Netflix也没有。  

These companies can’t disrupt themselves to build the type of world-class developer tooling the world would need.  

这些公司不能破坏自己，以建立世界需要的那种世界级的开发者工具。

Yes, these companies build really, really cool internal developer tools. But they appear incapable of budgeting to build anything for engineers _outside_ of their company to be used. Nobody is doing this.  

是的，这些公司建立了非常、非常酷的内部开发工具。但他们似乎没有能力为公司以外的工程师建立任何可供使用的预算。没有人在做这个。

There’s a working model for software like stream-processing platform Kafka, which was originally created at LinkedIn.  

像流处理平台Kafka这样的软件有一个工作模式，它最初是在LinkedIn创建的。  

Then LinkedIn open-sourced it, and other companies are working together in a way that benefits the whole industry.  

然后LinkedIn将其开源，其他公司也在以一种有利于整个行业的方式进行合作。

Why has this model of collaborating and benefiting the whole industry not happened with dev tools? My take is that there’s an integration component that makes this too challenging.  

为什么这种合作并使整个行业受益的模式没有发生在开发工具上？我的看法是，有一个整合的组成部分，使之具有太大挑战性。

**Integrations are really hard with dev tools.** You need that code intelligence platform at its core, and then you need to do lots of integrations.  

For example, with source control you would need to integrate not just with Git but also with solutions like SVN, Mercurial, and others.  

You’d need to add support for a variety of programming languages - including ones your company might not use.  

对于开发工具来说，整合真的很难。你需要以代码智能平台为核心，然后你需要做很多整合。例如，在源码控制方面，你不仅需要与Git集成，还需要与SVN、Mercurial和其他解决方案集成。你需要增加对各种编程语言的支持--包括那些你的公司可能不使用的语言。

I think that most companies simply don’t have an appetite for the long tail of integrations. However, a company like Sourcegraph has opted to go this way.  

我认为，大多数公司根本没有胃口进行长尾整合。然而，像Sourcegraph这样的公司却选择了这种方式。

This is what made me bullish on Sourcegraph. Dev tools that benefit everyone are coming, and these can only be built by a company that doesn’t shy away from the integration part.  

这就是让我看好Sourcegraph的原因。让所有人都受益的开发工具即将到来，而这些工具只能由一个不回避整合部分的公司来打造。  

This is the type of solution that can win in this space.  

这是能够在这一领域获胜的解决方案的类型。

One more thing that made me excited to join was how, at Google, as I worked on the Code Search ecosystem, I was waiting for someone to come and compete with us.  

还有一件事让我对加入感到兴奋，那就是在谷歌，当我从事代码搜索生态系统的工作时，我一直在等待有人来与我们竞争。  

Years later, I would have companies offer something comparable to what we had at Google. And yet, I haven’t seen anyone, outside of Sourcegraph. So this made the decision to join easy.  

几年后，我会让公司提供一些与我们在谷歌的情况相媲美的东西。然而，在Sourcegraph之外，我还没有看到任何人。因此，这使得加入的决定很容易。

**I will keep coming back full circle on developer tools, until someone fixes this space.** 31 years ago, at GeoWorks, I worked with some of the best developer tools, which were well ahead of the industry. This gave me a glimpse of what great tools would do.  

我将不断地在开发工具上兜圈子，直到有人修复这个空间。31年前，在GeoWorks公司，我与一些最好的开发工具一起工作，这些工具远远领先于这个行业。这让我看到了伟大的工具会做什么。

And I’ve kept waiting for companies to step up and fix the developer tools experience - year after year, decade after decade.  

我一直在等待公司站出来，解决开发者工具的体验问题--年复一年，十年复十年。

I’m now done with waiting and I want to fix this space.  

我现在受够了等待，我想修复这个空间。

I’m now a decision maker at Sourcegraph and I decided that I’m going to go and build better tools for developers, and I have a much more generous budget to work with.  

我现在是Sourcegraph的决策者，我决定要去为开发者建立更好的工具，而且我有更慷慨的预算可以使用。  

As a code intelligence platform, Sourcegraph becomes an aggregator.  

作为一个代码智能平台，Sourcegraph成为一个聚合器。  

I don’t think we’ll become the next Google, but we might become something akin to the next Atlassian or the next JetBrains when we’re done with this work.  

我不认为我们会成为下一个谷歌，但当我们完成这项工作时，我们可能会成为类似于下一个阿特拉斯或下一个JetBrains的东西。

So if you’re passionate about developer tools, you should stay tuned.  

因此，如果你对开发者工具充满热情，你应该继续关注。

_This is Gergely again.  

这又是Gergely。_

Thanks for taking the time to talk, Steve. You can follow Steve [on LinkedIn](https://www.linkedin.com/in/steveyegge/), check out [his YouTube channel](https://www.youtube.com/user/steveyegge) with interesting talks, and read [his blog](https://steve-yegge.medium.com/). Steve recently published his first blog post in a while about coding assistants, AI and LLMs with the title [Cheating is all you need](https://about.sourcegraph.com/blog/cheating-is-all-you-need) - and I recommend reading that one as well.  

谢谢你抽出时间来谈话，史蒂夫。你可以在LinkedIn上关注Steve ，查看他的YouTube频道上的有趣讲座，并阅读他的博客。史蒂夫最近发表了他的第一篇关于编码助手、人工智能和法律硕士的博文，题目是作弊是你所需要的--我也推荐阅读这篇文章。

It’s hard to convey through text just how full of energy Steve was, throughout our conversation.  

在我们的谈话中，很难通过文字来表达史蒂夫是多么的精力充沛。  

It was so clear that Steve not only loves the developer tools space and cares about it but also lives and breathes it.  

很明显，Steve不仅热爱开发者工具领域，关心它，而且还生活和呼吸着它。

Here are the key takeaways I picked up from talking with Steve:  

以下是我从与史蒂夫的交谈中获得的主要收获：

**Down-leveling was a risk worth taking midway into Steve’s career.** Steve was an L7 at Amazon, but got an L5 offer at Google. Back in the day, Google was the hottest startup amongst software engineers. Still, Steve _did_ have 16 years of experience by this point. He sensed that Google had strong momentum - seeing interns consistently choose Google over Amazon - and put aside levels, joining at the level offered.  

在史蒂夫的职业生涯中，降级是一个值得承担的风险。史蒂夫在亚马逊是L7，但在谷歌得到了L5的邀请。在那个时候，谷歌是软件工程师中最热门的创业公司。尽管如此，史蒂夫这时已经有16年的经验了。他感觉到谷歌有强大的势头--看到实习生一直选择谷歌而不是亚马逊--于是抛开级别，以提供的级别加入。

Of course, when it comes to accepting a down-level offer, there is no generic advice. If you can join the next Google, sure, this is likely a fair trade-off.  

The problem is it’s hard to predict which company might be on such a growth trajectory! _We covered more on down-leveling in the issue [The Seniority Rollercoaster.](https://newsletter.pragmaticengineer.com/p/the-seniority-rollercoaster)_  

当然，当涉及到接受一个低级别的邀请时，没有通用的建议。如果你能加入下一个谷歌，当然，这可能是一个公平的交易。问题是很难预测哪家公司会有这样的发展轨迹！我们在《资历过山车》一文中介绍了更多关于降级的情况。

**Customer obsession, as a mindset, is incredibly powerful.** Having worked at Amazon, in the early days of the company, Steve walked away with a strong appreciation of putting customers first.  

Over the decades, he continued to appreciate this approach even more, and it’s one of the biggest changes he’s brought to Sourcegraph, right as he joined.  

对客户的痴迷，作为一种心态，是令人难以置信的强大。在亚马逊的早期工作中，史蒂夫对 "客户至上 "有了深刻的认识。几十年来，他继续欣赏这种方法，这是他加入Sourcegraph时带来的最大变化之一。

Curiously enough, the thing that Steve said he had to unlearn was how Google created barriers for engineers to talk to customers.  

奇怪的是，史蒂夫说他必须取消学习的东西是谷歌如何为工程师与客户交谈制造障碍。  

This observation was interesting to hear - and it’s a reminder for every founder and manager that the closer engineers are to customers, the better the outcomes that could come from this.  

这个意见很有意思--它提醒每个创始人和经理，工程师越接近客户，可能产生的结果就越好。

**Working too many time zones away can be too much.** Steve is one of the most energetic people I’ve talked with. Still, he sounded weary when he was talking about the second part of his time at Grab - once the honeymoon period was over.  

在太多的时区之外工作会让人受不了。史蒂夫是与我交谈过的最有活力的人之一。不过，当他谈到他在Grab公司的第二部分工作时--一旦蜜月期结束，他听起来还是很疲惫。

Turns out that there are some things that are very hard to work around.  

事实证明，有些事情是很难解决的。  

Being an engineering leader in a completely different time zone to where most of your team is can wear you out, and it wore Steve out.  

作为一个工程领导，在一个与你的团队大部分人所在的地方完全不同的时区，会让你疲惫不堪，这让史蒂夫很累。

**Once you see the difference world-class developer tools make, you cannot unsee it.** Steve got exposed to what was likely the bleeding edge of developer tools at GeoWorks: at his first job, out of college.  

一旦你看到世界一流的开发工具所带来的不同，你就无法不看到它。史蒂夫在GeoWorks接触到了可能是最前沿的开发工具：在他大学毕业后的第一份工作。

It felt to me that the reason Steve kept gravitating to the developer tools space throughout his career was because he knew that if he could recreate that GeoWorks’ developer experience - in a modern setting - then that would make a huge difference to any and all organizations.  

在我看来，史蒂夫在他的职业生涯中一直倾向于开发者工具领域的原因是，他知道如果他能在现代环境中重现GeoWorks的开发者体验，那么这将对任何和所有组织产生巨大影响。

I hope you enjoyed the stories, and found learnings from Steve’s experiences that you can reflect on. Good luck to Steve and the Sourcegraph team in moving developer tooling forward!  

我希望你喜欢这些故事，并从Steve的经历中找到你可以反思的学习内容。祝愿Steve和Sourcegraph团队在推进开发者工具的过程中取得好成绩!

_And if you’d like to learn more about how Sourcegraph works from an engineering point of view, and how their ‘Transparent by default’ principle shapes their culture: we went deep in the article [Inside Sourcegraph’s engineering culture](https://newsletter.pragmaticengineer.com/p/inside-sourcegraphs-engineering-culture).  

如果你想了解更多关于Sourcegraph如何从工程角度工作，以及他们的 "默认透明 "原则如何塑造他们的文化：我们在文章《Inside Sourcegraph的工程文化》中进行了深入探讨。_

_I have a favor to ask: I’m running the [Tech Leaders Compensation survey](https://form.typeform.com/to/nrZdNOIa?typeform-source=pragmaticengieer.com), together VC firm CREANDUM to answer the question “how are engineering leaders at tech companies compensated?” If you are in a lead or management position and have a few minutes to spare, [please share anonymous compensation details here](https://form.typeform.com/to/nrZdNOIa?typeform-source=pragmaticengieer.com). I’ll share detailed results in the newsletter around June - or add your email to get the report even before.  

我想请你帮个忙：我正在进行技术领导人报酬调查，与风险投资公司CREANDUM一起回答 "科技公司的工程领导人是如何得到报酬的？"如果你处于领导或管理职位，并且有几分钟的时间，请在这里分享匿名的补偿细节。我将在6月左右的新闻通讯中分享详细的结果--或者添加你的电子邮件，甚至在之前就能得到报告。_

_This is a collaboration I suggested after reading an earlier report from CREANDUM on an [early-stage founders compensation report](https://blog.creandum.com/europes-most-significant-early-stage-founders-compensation-report-43b0da810d1). I helped build the questions, and will also be analyzing results. I am not paid for this collaboration. For more details, see [my ethics policy](https://blog.pragmaticengineer.com/ethics-statement/).  

这是我在阅读了CREANDUM早先的一份关于早期创始人报酬报告后建议的合作。我帮助建立了这些问题，也将分析结果。我没有因为这次合作而得到报酬。更多细节，请看我的道德政策。_

If you’re hiring software engineers or engineering leaders, join [The Pragmatic Engineer Talent Collective](https://pragmatic-engineer.pallet.com/talent). It’s the #1 talent collective for software engineers and engineering managers. Get weekly drops of outstanding software engineers and engineering leaders open to new opportunities.  

I vet every software engineer and manager - and add a note on why they are a standout profile.  

如果你正在招聘软件工程师或工程领导，请加入务实的工程师人才集体。它是软件工程师和工程经理的第一人才集体。每周获得优秀的软件工程师和工程领导人的信息，并为他们提供新的机会。我对每一位软件工程师和经理进行审核--并添加说明，说明他们为什么是一个突出的形象。

Companies like Linear use this collective to hire better, and faster. [Read what companies hiring say](https://blog.pragmaticengineer.com/job-board-testimonials/). And if you’re hiring, apply here:  

像Linear这样的公司利用这个集体来更好、更快地招聘。 阅读正在招聘的公司的说法。如果你正在招聘，请在这里申请：

[Apply Now](https://pragmatic-engineer.pallet.com/talent)

[![](https3A2F2Fsubstack-post-media.s3.amazonaws.com2Fpublic2Fimages2F0811f33f-2153-44e2-94a5-91580da56d1b_1676x1444.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0811f33f-2153-44e2-94a5-91580da56d1b_1676x1444.png)

If you’re open for a new opportunity, join to get reachouts from vetted companies. You can join anonymously, and leave anytime:  

如果你正在寻找新的机会，加入后可以得到经过审查的公司的联系。你可以匿名加入，并随时离开：

[Apply Now](https://pragmatic-engineer.pallet.com/talent)

1.  [Engineering Leader - Card Platform](https://pragmatic-engineer.pallet.com/jobs/b164854a-c47e-435c-b471-fd005abb7c21) at X1 Card. **$250K+**. Remote (US).  
    
    工程负责人 - X1卡的卡平台。 **$250K+** .远程（美国）。
    
2.  [Senior iOS Engineer](https://pragmatic-engineer.pallet.com/jobs/c91f9b83-2971-478f-8bf5-1886f691f3cc) at Polarsteps. **£70-90K**. Amsterdam.  
    
    Polarsteps的高级iOS工程师。£70-90K.阿姆斯特丹。
    
3.  [Frontend Software Engineer](https://pragmatic-engineer.pallet.com/jobs/bdaa6b65-a836-4f83-92d9-b4721731f172) at Enveritas. **$130-150K**. Remote (Global).  
    
    Enveritas的前端软件工程师。 **$130-150K** .远程（全球）。
    
4.  [Senior Android Engineer](https://pragmatic-engineer.pallet.com/jobs/1dc3c677-9e4c-4287-847b-5d9b8fb1d512) at Polarsteps. Amsterdam.  
    
    Polarsteps公司的高级安卓工程师。阿姆斯特丹。
    
5.  [Senior Mobile Developer (React Native)](https://pragmatic-engineer.pallet.com/jobs/37981512-9fe2-4ea0-863a-ca751acb18f3) at Peppy. Remote (UK).  
    
    Peppy公司的高级移动开发人员（React Native）。远程（英国）。
    
6.  [Head of Data](https://pragmatic-engineer.pallet.com/jobs/0e47ee86-453e-4bac-8a61-88a418a34342) at Peppy. Remote (UK).  
    
    Peppy公司的数据主管。远程（英国）。
    
7.  [Senior Software Engineer, Distributed Systems](https://pragmatic-engineer.pallet.com/jobs/d3056a2a-b993-44dc-b3f2-7e188b866270) at Mixpanel. **$200-270K** + equity. New York, San Franciso, Seattle or Remote (US).  
    
    Mixpanel的分布式系统高级软件工程师。 **$200-270K** +股权。纽约，圣弗朗西斯科，西雅图或远程（美国）。
    
8.  [Senior Software Engineer, Fullstack](https://pragmatic-engineer.pallet.com/jobs/5e9c22e8-1068-4a1c-b7a0-9228dc3c1597) at Mixpanel. **$200-270K** + equity. New York, San Franciso, Seattle or Remote (US).  
    
    Mixpanel的高级软件工程师，全栈式。 **$200-270K** +股权。纽约、圣弗朗西斯科、西雅图或远程（美国）。
    
9.  [Senior Fullstack Engineer](https://pragmatic-engineer.pallet.com/jobs/2d6844d5-c30e-458a-a04b-445886421e47) at Synthesia. **£70-110K** . Remote (Europe or US Eastern time) or onsite (London, Amsterdam, New York).  
    
    Synthesia的高级全栈工程师。£70-110K .远程（欧洲或美国东部时间）或现场（伦敦、阿姆斯特丹、纽约）。
    
10.  [Senior Backend Engineer](https://pragmatic-engineer.pallet.com/jobs/4b5de642-2711-4e35-9d77-515acae0780c) at Synthesia. **£70-110K** . Remote (Europe or US Eastern time) or onsite (London, Amsterdam, New York).  
    
    Synthesia的高级后端工程师。£70-110K .远程（欧洲或美国东部时间）或现场（伦敦、阿姆斯特丹、纽约）。
    
11.  [Senior Frontend Engineer](https://pragmatic-engineer.pallet.com/jobs/952015f8-7789-4d57-b35a-afd3c1a937fb) at (catch) Health. **$90-120K** + equity. Remote (North America).  
    
    高级前端工程师在（抓）健康。 **$90-120K** +股权。远程（北美）。
    
12.  [Solutions Engineer](https://pragmatic-engineer.pallet.com/jobs/796be272-f2e7-4f6b-8361-49db49dce543) at Pigment. **$70-120K**. New York or Toronto.  
    
    颜料公司的解决方案工程师。 **$70-120K** .纽约或多伦多。
    
13.  [Senior Backend Engineer](https://pragmatic-engineer.pallet.com/jobs/4b389952-c6fa-4d0b-82c7-cb12260b5b83) at Comun. New York or Remote (US).  
    
    Comun公司的高级后端工程师。纽约或远程（美国）。
    

_See more senior engineer and leadership roles with great engineering cultures on [The Pragmatic Engineer Job board](https://pallet.xyz/list/pragmatic-engineer/jobs) - or post your own.  

在The Pragmatic Engineer Job Board上查看更多具有优秀工程文化的高级工程师和领导职位--或者发布你自己的职位。_
