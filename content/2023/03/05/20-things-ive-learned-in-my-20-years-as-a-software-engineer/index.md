---
title: "在我20年软件工程师生涯中学到的20件事"
date: 2023-03-05T19:37:54+08:00
updated: 2023-03-05T19:37:54+08:00
taxonomies:
  tags: []
extra:
  source: https://www.simplethread.com/20-things-ive-learned-in-my-20-years-as-a-software-engineer/?utm_source=substack&utm_medium=email
  hostname: www.simplethread.com
  author: Justin Etheredge
  original_title: "20 Things I've Learned in my 20 Years as a Software Engineer"
  original_lang: en
---

## Important, Read This First  

重要的是，请先阅读这个

You’re about to read a blog post with a _lot_ of advice. Learning from those who came before us is instrumental to success, but we often forget an important caveat. Almost all advice is contextual, yet it is rarely delivered with any context.  

你将要阅读的是一篇有很多建议的博文。向前人学习是成功的关键，但我们经常忘记一个重要的注意事项。几乎所有的建议都是有背景的，但它却很少在有背景的情况下被传递。

“You just need to charge more!” says the company who has been in business for 20 years and spent years charging “too little” to gain customers and become successful.  

"你只需要收取更多的费用！"这家公司已经经营了20年，花了多年时间收取 "太少 "的费用来获得客户并获得成功。

“You need to build everything as microservices!” says the company who built a quick monolith, gained thousands of customers, and then pivoted into microservices as they started running into scaling issues.  

"你需要把所有东西都建成微服务！"该公司说，他们快速建立了一个单体，获得了成千上万的客户，然后在开始遇到扩展问题时转而进入微服务。

Without understanding the context, the advice is meaningless, or even worse, harmful. If those folks had followed their own advice early on, they themselves would likely have suffered from it. It is hard to escape this trap. We may be the culmination of our experiences, but we view them through the lens of the present.  

如果不了解背景，这些建议就毫无意义，甚至更糟糕的是，是有害的。如果那些人在早期就听从自己的建议，他们自己很可能会因此而受到伤害。很难逃脱这个陷阱。我们可能是我们经验的结晶，但我们通过现在的镜头来看待它们。

So to give you a little context on where my advice comes from, I spent the first half of my career as a software engineer working for various small businesses and startups, then I went into consulting and worked in a number of really large businesses. Then I started Simple Thread and we grew from a team of 2 to a team of 25. 10 years ago we worked with mostly small/medium businesses, and now we work with a mix of big and small businesses.  

因此，为了给你介绍一下我的建议的来龙去脉，我的职业生涯的前半部分是作为一名软件工程师，为各种小型企业和初创公司工作，然后我进入咨询行业，在一些真正的大型企业工作。然后我创办了简单线程，我们从一个2人的团队发展到25人的团队。10年前，我们主要与小型/中型企业合作，现在我们与大型和小型企业混合工作。

My advice is from someone who…  

我的建议是来自一个...

1.  has almost always been on small, lean teams where we have to do a lot with very little.  
    
    几乎总是在小而精的团队中，我们必须用很少的钱做很多事情。
2.  values working software over specific tools.  
    
    重视工作软件而非特定工具。
3.  is starting new projects all the time, but also has to maintain a number of systems.  
    
    一直在启动新的项目，但也必须维护一些系统。
4.  values engineer productivity over most other considerations  
    
    重视工程师的生产力而不是其他大多数考虑因素

My experiences over the last 20 years have shaped how I view software, and have led me to some beliefs which I’ve tried to whittle down to a manageable list that I hope you find valuable.  

在过去的20年里，我的经历塑造了我对软件的看法，并使我产生了一些信念，我试图将这些信念缩减为一个可管理的清单，希望你能从中发现价值。

## On with the list  

继续列举

### 1\. I still don’t know very much  

1.我还是不太了解

“How can you not know what BGP is?” “You’ve never heard of Rust?” Most of us have heard these kinds of statements, probably too often. The reason many of us love software is because we are lifelong learners, and in software no matter which direction you look, there are wide vistas of knowledge going off in every direction and expanding by the day. This means that you can spend decades in your career, and still have a huge knowledge gap compared to someone who has also spent decades in a seemingly similar role. The sooner you realize this, the sooner you can start to shed your imposter syndrome and instead delight in learning from and teaching others.  

"你怎么可能不知道BGP是什么？""你没听说过Rust吗？"我们中的大多数人都听过这种说法，可能太频繁了。我们中的许多人之所以喜欢软件，是因为我们是终身学习者，在软件领域，无论你往哪个方向看，都有广阔的知识远景，并且日渐扩大。这意味着你可以在你的职业生涯中度过数十年，但与那些在一个看似相似的角色中度过数十年的人相比，仍有巨大的知识差距。你越早意识到这一点，你就能越早开始摆脱你的冒名顶替综合症，转而乐于向他人学习和教导。

### 2\. The hardest part of software is building the right thing  

2.软件最难的部分是建立正确的东西

I know this is cliche at this point, but the reason most software engineers don’t believe it is because they think it devalues their work. Personally I think that is nonsense. Instead it highlights the complexity and irrationality of the environments in which we have to work, which compounds our challenges. You can design the most technically impressive thing in the world, and then have nobody want to use it. Happens all the time. Designing software is mostly a listening activity, and we often have to be part software engineer, part psychic, and part anthropologist. Investing in this design process, whether through dedicated UX team members or by simply educating yourself, will deliver enormous dividends. Because how do you really calculate the cost of building the wrong software? It amounts to a lot more than just lost engineering time.  

我知道这一点是老生常谈，但大多数软件工程师不相信的原因是他们认为这贬低了他们的工作。我个人认为那是无稽之谈。相反，它强调了我们必须在其中工作的环境的复杂性和非理性，这使我们的挑战更加复杂。你可以设计出世界上技术上最令人印象深刻的东西，但却没有人愿意使用它。这种情况一直在发生。设计软件主要是一种倾听的活动，我们经常要成为部分软件工程师、部分心理学家和部分人类学家。在这个设计过程中的投资，无论是通过专门的用户体验团队成员还是通过简单的自我教育，都将带来巨大的回报。因为你如何真正计算出构建错误软件的成本？这不仅仅是损失的工程时间。

### 3\. The best software engineers think like designers  

3.最好的软件工程师像设计师一样思考

Great software engineers think deeply about the user experience of their code. They might not think about it in those terms, but whether it is an external API, programmatic API, user interface, protocol, or any other interface; great engineers consider who will be using it, why it will be used, how it will be used, and what is important to those users. Keeping the user’s needs in mind is really the heart of good user experience.  

伟大的软件工程师会深入思考他们代码的用户体验问题。他们可能不会从这些方面考虑，但无论是外部API、程序化API、用户界面、协议，还是其他任何界面；优秀的工程师会考虑谁会使用它，为什么会使用它，如何使用它，以及什么对这些用户是重要的。把用户的需求放在心上，确实是好的用户体验的核心。

### 4\. The best code is no code, or code you don’t have to maintain  

4.最好的代码是没有代码，或者你不必维护的代码

All I have to say is “coders gonna code.” You ask someone in any profession how to solve a problem, and they are going to err on the side of what they are good at. It is just human nature. Most software engineers are always going to err on the side of writing code, especially when a non-technical solution isn’t obvious. The same goes for code you don’t have to maintain. Engineering teams are apt to want to reinvent the wheel, when lots of wheels already exist. This is a balancing act, there are lots of reasons to grow your own, but beware of toxic “Not Invented Here” syndrome.  

我只想说，"编码者要编码"。你问任何行业的人如何解决一个问题，他们都会偏向于他们擅长的方面。这只是人类的天性。大多数软件工程师总是倾向于写代码，特别是当非技术性的解决方案不明显时。对于你不需要维护的代码也是如此。工程团队很容易想重新发明轮子，而很多轮子已经存在了。这是一个平衡的行为，有很多理由让你自己成长，但要小心有毒的 "不是这里发明的 "综合症。

### 5\. Software is a means to an end  

5.软件是达到目的的一种手段

The primary job of any software engineer is delivering value. Very few software developers understand this, even fewer internalize it. Truly internalizing this leads to a different way of solving problems, and a different way of viewing your tools. If you really believe that software is subservient to the outcome, you’ll be ready to really find “the right tool for the job” which might not be software at all.  

任何软件工程师的主要工作都是交付价值。很少有软件开发人员理解这一点，甚至更少有人将其内化。真正内化这一点，会带来一种解决问题的不同方式，以及看待工具的不同方式。如果你真的相信软件是服从于结果的，你就会准备好真正找到 "适合工作的工具"，而这个工具可能根本就不是软件。

### 6\. Sometimes you have to stop sharpening the saw, and just start cutting shit  

6.有时你必须停止磨锯子，直接开始切割狗屎

Some people tend to jump into problems and just start writing code. Other people tend to want to research and research and get caught in analysis paralysis. In those cases, set a deadline for yourself and just start exploring solutions. You’ll quickly learn more as you start solving the problem, and that will lead you to iterate into a better solution.  

有些人倾向于跳进问题中，直接开始写代码。另一些人则倾向于想要研究和研究，并陷入分析瘫痪。在这些情况下，为自己设定一个期限，然后就开始探索解决方案。当你开始解决问题时，你会很快学到更多的东西，这将导致你迭代成一个更好的解决方案。

### 7\. If you don’t have a good grasp of the universe of what’s possible, you can’t design a good system  

7.如果你没有很好地掌握宇宙的可能性，你就无法设计一个好的系统。

This is something I struggle with a lot as my responsibilities take me further and further from the day to day of software engineering. Keeping up with the developer ecosystem is a huge amount of work, but it is critical to understand what is possible. If you don’t understand what is possible and what is available in a given ecosystem then you’ll find it impossible to design a reasonable solution to all but the most simple of problems. To summarize, be wary of people designing systems who haven’t written any code in a long time.  

这是我经常纠结的事情，因为我的职责使我离软件工程的日常工作越来越远。跟上开发人员的生态系统是一项巨大的工作，但了解什么是可能的是至关重要的。如果你不了解在一个特定的生态系统中什么是可能的，什么是可用的，那么你会发现除了最简单的问题之外，你不可能为所有的问题设计一个合理的解决方案。总而言之，对那些很久没有写过代码的系统设计者要保持警惕。

### 8\. Every system eventually sucks, get over it  

8.每个系统最终都很糟糕，克服它吧

Bjarne Stroustrup has a quote that goes “There are only two kinds of languages: the ones people complain about and the ones nobody uses”. This can be extended to large systems as well. There is no “right” architecture, you’ll never pay down all of your technical debt, you’ll never design the perfect interface, your tests will always be too slow. This isn’t an excuse to never make things better, but instead a way to give you perspective. Worry less about elegance and perfection; instead strive for continuous improvement and creating a livable system that your team enjoys working in and sustainably delivers value.  

Bjarne Stroustrup有一句话："只有两种语言：人们抱怨的语言和没人用的语言"。这句话也可以延伸到大型系统。没有 "正确的 "架构，你永远无法偿还所有的技术债务，你永远无法设计出完美的界面，你的测试总是太慢。这并不是一个永远不把事情做得更好的借口，而是给你一个视角。不要担心优雅和完美，而是要努力持续改进，创造一个可居住的系统，让你的团队喜欢在其中工作，并可持续地提供价值。

### 9\. Nobody asks “why” enough  

9.没有人问够 "为什么"

Take any opportunity to question assumptions and approaches that are “the way things have always been done”. Have a new team member coming on board? Pay attention to where they get confused and what questions they ask. Have a new feature request that doesn’t make sense? Make sure you understand the goal and what is driving the desire for this functionality. If you don’t get a clear answer, keep asking why until you understand.  

抓住任何机会，质疑 "事情一直以来的做法 "的假设和方法。有一个新的团队成员要加入吗？注意他们在哪里感到困惑，以及他们问了什么问题。有一个没有意义的新功能请求？确保你了解目标和驱动对这个功能的渴望的因素。如果你没有得到一个明确的答案，继续问为什么，直到你明白为止。

### 10\. We should be far more focused on avoiding 0.1x programmers than finding 10x programmers  

10.我们应该更专注于避免0.1x的程序员，而不是寻找10x的程序员。

[The 10x programmer is a silly myth.](https://www.simplethread.com/the-10x-programmer-myth/) The idea that someone can produce in 1 day what another competent, hard working, similarly experienced programmer can produce in 2 weeks is silly. I’ve seen programmers that sling 10x the amount of code, and then you have to fix it 10x the amount of times. The only way someone can be a 10x programmer is if you compare them to 0.1x programmers. Someone who wastes time, doesn’t ask for feedback, doesn’t test their code, doesn’t consider edge cases, etc… We should be far more concerned with keeping 0.1x programmers off our teams than finding the mythical 10x programmer.  

10倍程序员是一个愚蠢的神话。 有人能在1天内完成另一个有能力的、努力工作的、同样有经验的程序员在2周内完成的工作，这种想法是愚蠢的。我见过的程序员的代码量是其他程序员的10倍，而你需要修改的次数也是10倍。一个人能够成为10倍的程序员的唯一方法是，你把他们和0.1倍的程序员相比。那些浪费时间、不征求反馈意见、不测试自己的代码、不考虑边缘情况等的人......我们应该更关心如何让0.1倍的程序员离开我们的团队，而不是寻找神话中的10倍程序员。

### 11\. One of the biggest differences between a senior engineer and a junior engineer is that they’ve formed opinions about the way things should be  

11.高级工程师和初级工程师之间最大的区别之一是，他们已经形成了关于事情应该如何发展的意见

Nothing worries me more than a senior engineer that has no opinion of their tools or how to approach building software. I’d rather someone give me opinions that I violently disagree with than for them to have no opinions at all. If you are using your tools, and you don’t love or hate them in a myriad of ways, you need to experience more. You need to explore other languages, libraries, and paradigms. There are few ways of leveling up your skills faster than actively seeking out how others accomplish tasks with different tools and techniques than you do.  

没有什么比一个对自己的工具或如何构建软件没有意见的高级工程师更让我担心了。我宁愿有人给我一些我不同意的意见，而不是他们根本没有意见。如果你正在使用你的工具，而你对它们不爱也不恨，那么你需要体验更多。你需要探索其他语言、库和范式。没有什么方法能比积极寻找别人如何用与你不同的工具和技术来完成任务更快提高你的技能水平。

### 12\. People don’t really want innovation  

12.人们并不真正想要创新

People talk about innovation a whole lot, but what they are usually looking for is cheap wins and novelty. If you truly innovate, and change the way that people have to do things, expect mostly negative feedback. If you believe in what you’re doing, and know it will really improve things, then brace yourself for a long battle.  

人们谈论了很多创新，但他们通常寻找的是廉价的胜利和新奇。如果你真正地进行创新，并改变人们做事的方式，预计会有大部分的负面反馈。如果你相信你正在做的事情，并且知道它将真正改善事情，那么请准备好迎接一场漫长的战斗。

### 13\. Your data is the most important part of your system  

13.你的数据是你系统中最重要的部分

I’ve seen a lot of systems where hope was the primary mechanism of data integrity. In systems like this, anything that happens off the golden path creates partial or dirty data. Dealing with this data in the future can become a nightmare. Just remember, your data will likely long outlive your codebase. Spend energy keeping it orderly and clean, it’ll pay off well in the long run.  

我见过很多系统，希望是数据完整性的主要机制。在这样的系统中，任何发生在黄金路径之外的事情都会产生部分或肮脏的数据。在未来处理这些数据会成为一场噩梦。请记住，你的数据可能会比你的代码库长寿。花费精力保持它的有序和干净，从长远来看，这将会得到很好的回报。

### 14\. Look for technological sharks  

14.寻找技术型鲨鱼

Old technologies that have stuck around are [sharks, not dinosaurs](https://www.simplethread.com/relational-databases-arent-dinosaurs-theyre-sharks/). They solve problems so well that they have survived the rapid changes that occur constantly in the technology world. Don’t bet against these technologies, and replace them only if you have a very good reason. These tools won’t be flashy, and they won’t be exciting, but they will get the job done without a lot of sleepless nights.  

坚持下来的老技术是鲨鱼，而不是恐龙。它们很好地解决了问题，以至于它们在技术世界不断发生的快速变化中幸存下来。不要对这些技术下赌注，只有在你有非常好的理由时才替换它们。这些工具不会是华丽的，也不会是令人兴奋的，但它们会在没有很多不眠之夜的情况下完成工作。

### 15\. Don’t mistake humility for ignorance  

15.不要把谦逊误认为无知

There are a lot of software engineers out there who won’t express opinions unless asked. Never assume that just because someone isn’t throwing their opinions in your face that they don’t have anything to add. Sometimes the noisiest people are the ones we want to listen to the least. Talk to the people around you, seek their feedback and advice. You’ll be glad you did.  

有很多软件工程师，除非被要求，否则不会表达意见。不要以为别人没有把他们的意见扔到你面前，就认为他们没有什么可补充的。有时候，最吵的人是我们最不想听的人。与你周围的人交谈，寻求他们的反馈和建议。你会很高兴你这样做。

### 16\. Software engineers should write regularly  

16.软件工程师应定期写作

Software engineers should regularly blog, journal, write documentation and in general do anything that requires them to keep their written communication skills sharp. Writing helps you think about your problems, and helps you communicate those more effectively with your team and your future self. Good written communication is one of the most important skills for any software engineer to master.  

软件工程师应该定期写博客、日记、写文档，总之做任何需要他们保持书面沟通能力的事情。写作帮助你思考你的问题，并帮助你与你的团队和未来的自己更有效地沟通这些问题。良好的书面交流是任何软件工程师需要掌握的最重要的技能之一。

### 17\. Keep your processes as lean as possible  

17.尽可能地保持你的流程精简

Everyone wants to be agile these days, but being “agile” is about building things in small chunks, learning, and then iterating. If someone is trying to shoehorn much more into it than that, then they’re [probably selling something](https://www.simplethread.com/agile-at-20-the-failed-rebellion/). It isn’t to say that people don’t need accountability or help to work this way, but how many times have you heard someone from your favorite tech company or large open source project brag about how great their Scrum process is? Stay lean on process until you know you need more. Trust your team and they will deliver.  

现在每个人都想成为敏捷的人，但 "敏捷 "是指以小块的方式构建事物，学习，然后进行迭代。如果有人试图在其中塞进更多的东西，那么他们可能是在推销什么。这并不是说人们不需要责任感或帮助来工作，但你有多少次听到你最喜欢的科技公司或大型开源项目的人吹嘘他们的Scrum过程有多好？在你知道你需要更多之前，保持对流程的精益求精。相信你的团队，他们会交付的。

### 18\. Software engineers, like all humans, need to feel ownership  

18.软件工程师，像所有人类一样，需要感受到所有权

If you divorce someone from the output of their work, they will care less about their work. I see this almost as a tautology. This is the primary reason why cross-functional teams work so well, and why DevOps has become so popular. It isn’t all about handoffs and inefficiencies, it is about owning the whole process from start to finish, and being directly responsible for delivering value. Give a group of passionate people complete [ownership over designing](https://www.simplethread.com/doerrs-law-on-product-teams/), building, and delivering a piece of software (or anything really) and amazing things will happen.  

如果你把一个人从他们的工作成果中剥离出来，他们就会减少对他们工作的关心。我认为这几乎是一个同义词。这就是为什么跨职能团队运作良好的主要原因，也是为什么DevOps变得如此流行的原因。这并不是所有的交接和低效率，而是从头到尾拥有整个过程，并直接负责交付价值。让一群充满激情的人对设计、构建和交付一个软件（或任何东西）拥有完全的所有权，将会发生令人惊奇的事情。

### 19\. Interviews are almost worthless for telling how good of a team member someone will be  

19.面试对于判断一个人将成为多好的团队成员几乎毫无价值

Interviews are far better spent trying to understand who someone is, and how interested they are in a given field of expertise. Trying to suss out how good of a team member they will be is a fruitless endeavor. And believe me, how smart or knowledgable someone is is also not a good indicator that they will be a great team member. No one is going to tell you in an interview that they are going to be unreliable, abusive, pompous, or never show up to meetings on time. People might claim they have “signals” for these things… “if they ask about time off in the first interview then they are never going to be there!” But these are all bullshit. If you’re using signals like these you’re just guessing and turning away good candidates.  

面试最好是用来了解某人是谁，以及他们对某一专业领域的兴趣如何。试图找出他们将是一个多么好的团队成员是一个没有结果的努力。相信我，一个人有多聪明或知识渊博，也不是一个很好的指标，说明他们会成为一个伟大的团队成员。没有人会在面试时告诉你，他们会不可靠、滥用职权、华而不实，或者从不按时出席会议。人们可能会声称他们对这些事情有 "信号"...... "如果他们在第一次面试时问起休息时间，那么他们就永远不会去了！"但这些都是胡说八道。如果你使用这样的信号，你只是在猜测和拒绝好的候选人。

### 20\. Always strive to build a smaller system  

20.始终努力建立一个较小的系统

There are a lot of forces that will push you to build the bigger system up-front. Budget allocation, the inability to decide which features should be cut, the desire to deliver the “best version” of a system. All of these things push us very forcefully towards building too much. You should [fight this](https://www.simplethread.com/where-does-complexity-go/). You learn so much as you’re building a system that you will end up iterating into a much better system than you ever could have designed in the first place. This is surprisingly a hard sell to most people.  

有很多力量会促使你在前期建立更大的系统。预算分配，无法决定哪些功能应该被削减，渴望提供一个系统的 "最佳版本"。所有这些东西都会非常有力地推动我们建立过多的系统。你应该与此作斗争。你在建立一个系统的过程中会学到很多东西，你最终会迭代成一个比你当初设计的更好的系统。对大多数人来说，这竟然是个难点。

## What is your story?  

你的故事是什么？

So there you have it, 20 years of software distilled down into 20 pithy pieces of wisdom. I’d love to hear it if something resonated with you. I’d also love to hear if you have a piece of wisdom that you’ve picked up over your career that you’d like to share. Feel free to leave it down in the comments.  

所以，你有了它，20年的软件被提炼成20条精炼的智慧。如果你有什么共鸣的话，我很想听听。我也很想听听你是否有在你的职业生涯中获得的智慧，你想分享一下。欢迎在评论中留下你的意见。

Loved the article? Hated it? Didn’t even read it?  

喜欢这篇文章？讨厌它？甚至没有读过它？

We’d love to hear from you.  

我们很想听到你的意见。

[Reach Out  

联系我们](https://www.simplethread.com/contact)
