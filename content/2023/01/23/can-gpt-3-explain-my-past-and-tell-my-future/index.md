---
title: "GPT-3 能解释我的过去并告诉我的未来吗？"
date: 2023-01-23T22:12:35+08:00
updated: 2023-01-23T22:12:35+08:00
taxonomies:
  tags: []
extra:
  source: https://every.to/chain-of-thought/can-gpt-3-explain-my-past-and-tell-me-my-future
  hostname: every.to
  author: by Dan Shipper 由丹托运人
  original_title: "Can GPT-3 Explain My Past and Tell My Future?"
  original_lang: en
---

#### Sponsor Every 赞助每一位

Every is the premier place for 65,000+ founders, operators, and investors to read about business, AI, and personal development.  
Every 是 65,000 多名创始人、运营商和投资者阅读商业、人工智能和个人发展的首选场所。

We're currently accepting sponsors for Q1! If you're interested in reaching our audience, learn more:  
我们目前正在接受第一季度的赞助商！如果您有兴趣接触我们的受众，请了解更多信息：

_What do you want to know about yourself?_ asks the bot.  
您想了解自己什么？机器人问。

The bot is built with [GPT-3](https://every.to/c/ai-and-gpt3), and has access to hundreds of my old journal entries from the last 10 years that it can use to answer my questions. It took me a few hours of programming, and I’m using it for the first time. I built it to analyze my past so, hopefully, I could better understand my future.  
该机器人是用 GPT-3 构建的，可以访问我过去 10 年的数百个旧日记条目，它可以用来回答我的问题。我花了几个小时来编程，这是我第一次使用它。我建立它是为了分析我的过去，希望我能更好地了解我的未来。  
“What’s past is prologue,” wrote Shakespeare, after all.  
“过去的就是序幕，”莎士比亚毕竟写道。

I start to type a question into my laptop. “When in his life has the author been the happiest?” GPT-3 doesn’t know my name yet, so I have to refer to myself as the author. “Please be specific about moments and situations. Identify what caused the happiness. Be truthful, don't make anything up. If you can't find a specific moment of happiness, don't summarize. Find moments that are surprising.”   
我开始在我的笔记本电脑上输入一个问题。 “作者一生中什么时候最快乐？” GPT-3 还不知道我的名字，所以我不得不称自己为作者。 “请具体说明时刻和情况。确定是什么导致了幸福。说实话，不要编造任何东西。如果找不到特定的幸福时刻，就不要总结。找到令人惊讶的时刻。”

I hit enter, and GPT-3 begins its work, finding the entries that are most relevant to my question and summarizing them to create an answer.  
我按下回车键，GPT-3 开始工作，找到与我的问题最相关的条目并总结它们以创建答案。

I watch its progress scroll past me with greedy focus. I feel like I just squeezed my soul into the coin slot of a self-designed slot machine. Now, I’m waiting to see if it will pay out.   
我贪婪地注视着它的进度从我身边滚过。我觉得我只是把我的灵魂挤进了一个自行设计的老虎机的投币口。现在，我在等着看它是否会得到回报。

Finally, a response comes back: 最后，返回一个响应：

_“The author felt the most happiness when he was walking on the beach in Koh Phangan, Thailand. He started out feeling somber, but as he walked he started to think about ideas for a novel about startups written in a style similar to Alain de Botton.  
“当他在泰国帕岸岛的海滩上散步时，作者感到最幸福。他开始感到忧郁，但当他走路时，他开始思考以类似于阿兰德波顿的风格写的关于创业公司的小说的想法。  
This inspired him and he felt a lot lighter and happier.”   
这激发了他的灵感，他感到更轻松、更快乐。”_

It continues: 它继续：

_“He also felt happiness when he was with Julia, reading, writing, building/creating things, having good conversations with people, watching football, reading Jonathan Gold, feeling in command of himself, going into an office and having people who look to him to set direction, and during/immediately after public speaking that went well.”  
“当他和朱莉娅在一起时，他也感到快乐，阅读、写作、建造/创造东西、与人进行愉快的交谈、看足球、阅读乔纳森·戈尔德、感觉能控制自己、走进办公室并有人看着他设定方向，并在公开演讲期间/之后立即进行得很顺利。”_

Jackpot. 

. . . . . . . .

I’ve been experimenting a lot with GPT-3 recently. I built [a chatbot based on the Huberman Lab podcast](https://every.to/chain-of-thought/i-trained-a-gpt-3-chatbot-on-every-episode-of-my-favorite-podcast). I built [a custom journal bot](https://every.to/chain-of-thought/gpt-3-is-the-best-journal-you-ve-ever-used) to help me unpack issues in my life.   
我最近对 GPT-3 进行了很多试验。我基于 Huberman Lab 播客构建了一个聊天机器人。我构建了一个自定义日记机器人来帮助我解决生活中的问题。

But this is by far my most personal experiment—and, in my opinion, one of the most valuable.   
但这是迄今为止我最个人化的实验——在我看来，也是最有价值的实验之一。

I’ll take you through how I came up with the idea, how I built it, what the results are, and what I think the future holds for these kinds of tools.  
我将向您介绍我是如何想到这个想法的，我是如何构建它的，结果是什么，以及我认为这些工具的未来会怎样。

## Summarizing the present

I found out innocently enough that GPT-3 is good at summarizing.  
我天真地发现 GPT-3 擅长总结。

I was writing an article for Every and having trouble finding the main thread, so I pasted what I had so far into _ChatGPT_ and asked it to summarize my key points. Usually, I’d ask someone at Every to help me with this, but no one was online. So I figured, why not ask GPT-3 to do it?   
我正在为 Every 写一篇文章，但找不到主线程，所以我将到目前为止的内容粘贴到 _ChatGPT_ 中，并要求它总结我的要点。通常，我会请 Every 的人帮我解决这个问题，但没人在线。所以我想，为什么不让 GPT-3 来做呢？

I hit enter and got the results—they were _great_. I saw the article I was writing in a totally new way, and I was able to finish it quickly and easily.  
我按下回车键并得到了结果——它们很棒。我以全新的方式看到了我正在写的文章，并且能够快速轻松地完成它。

My curiosity was piqued. What else might GPT-3 be good at summarizing? Maybe it would work for more than just my half-finished essays.   
我的好奇心被勾起来了。 GPT-3 还擅长总结什么？也许它不仅适用于我完成了一半的论文。

In my next therapy session I had an idea. I asked my therapist if I could record our session and feed the transcripts into GPT-3. It’s been a tough few weeks, and I wanted to see if it could help me look at what I was dealing with from a new perspective.   
在我的下一次治疗中，我有了一个主意。我问我的治疗师我是否可以记录我们的会议并将成绩单输入 GPT-3。这几周很艰难，我想看看它是否能帮助我从新的角度看待我正在处理的事情。

He was intrigued, so we laid a few ground rules about what I would do with the recording and what I would share. Then we dove in. _(Note: if you are in therapy, do not do this without explicitly discussing it with your therapist.)_ Afterwards I threw a section of the transcript into _ChatGPT_ and asked it to summarize.   
他很感兴趣，所以我们制定了一些基本规则，规定了我将如何处理录音以及我将分享什么。然后我们就开始了。（注意：如果你正在接受治疗，请不要在没有与你的治疗师明确讨论的情况下这样做。）之后我把一段文字记录扔进了 _ChatGPT_ 并要求它进行总结。

The results were stunning. 结果令人震惊。

_“From this session, it appears the client is experiencing a lot of stress due to a variety of life events, such as \[REDACTED\].  
“从本次会议来看，客户似乎因各种生活事件（例如\[已编辑\]）而承受着很大的压力。  
The client is feeling overwhelmed, exhausted, and scared, and is struggling to manage conflicting feelings of wanting to escape the situation and wanting to remain brave and committed to working through it.  
来访者感到不知所措、精疲力尽和害怕，并且正在努力处理想要逃离这种情况和想要保持勇敢并致力于解决它的矛盾情绪。  
On a deeper level, the client is struggling with feelings of inadequacy and fear of disappointing others, and a fear of conflict.”  
在更深层次上，来访者正在与自己的不足感、害怕让别人失望以及害怕发生冲突的感觉作斗争。”_

It correctly identified each of the things that I was struggling with, and then, in its own words, it expressed how I’d been feeling—but far more precisely than I had been able to do on my own. In some strange way, it felt like the AI knew me better than I knew myself.  
它正确地指出了我正在努力解决的每一件事，然后用它自己的话表达了我的感受——但比我自己所能表达的要准确得多。以某种奇怪的方式，感觉人工智能比我自己更了解我。

When someone, or something, puts their finger on exactly what you’re feeling, something clicks, and it creates an instant sense of relief. That’s exactly what happened when I read the summary.  
当某人或某物将手指准确地放在您的感受上时，会发出咔嗒声，并立即产生如释重负的感觉。这正是我阅读摘要时发生的事情。  
I had never directly used the word “inadequacy” to explain how I was feeling in that situation, but I was clearly feeling it. Now, when that feeling comes up, I can recognize it, label it, and work with it in a way that I wasn’t able to before.   
我从来没有直接用“不足”这个词来解释我在那种情况下的感受，但我清楚地感觉到了。现在，当那种感觉出现时，我可以识别它，给它贴上标签，并以一种我以前无法做到的方式处理它。

The experience left me even more curious to experiment.  
这段经历让我对实验更加好奇。

What other kinds of insights were hiding in plain sight? What would happen if I had recorded more than that one therapy session? I wanted to try giving it 100x the amount of material to work with.   
还有哪些其他类型的见解隐藏在众目睽睽之下？如果我记录了不止一次治疗会怎样？我想尝试给它 100 倍的材料来处理。

I had an idea where to look.  
我知道去哪里看。

## Explaining the past 解释过去

A journal is a way to catch pieces of yourself as they float through the present.  
日记是一种捕捉自己漂浮在当下的片段的方式。

I’ve been patiently catching those pieces for 10 years, in journals of every type. I’ve marked up markdown files and back-linked my morning pages in Roam. I’ve scrawled in yellow legal pads, Moleskines, and Midoris. (I even built a [GPT-3 journal](https://every.to/superorganizers/gpt-3-is-the-best-journal-you-ve-ever-used).)  
10 年来，我一直耐心地在各种类型的期刊中捕捉这些片段。我在 Roam 中标记了降价文件并反向链接了我的早间页面。我在黄色便笺本、Moleskines 和 Midoris 上潦草地写过。 （我什至建立了一个 GPT-3 期刊。）

I’ve always wondered why I do journaling. It helps me think through things in the moment, but I’ve always felt like I would use all of these entries for something more important. Maybe a book—a memoir. Now, it occurred to me that I should feed my journal into a machine.  
我一直想知道我为什么要写日记。它帮助我思考当下的事情，但我一直觉得我会把所有这些条目用于更重要的事情。也许是一本书——回忆录。现在，我想到我应该将我的日记输入一台机器。

It is, perhaps, the most delightfully narcissistic use of AI ever. But maybe it will also be helpful.   
这也许是有史以来对人工智能最令人愉快的自恋使用。但也许它也会有所帮助。

There’s only one problem. 只有一个问题。

## Solving GPT-3’s poor memory 解决 GPT-3 记忆力差的问题

GPT-3 might be good at summarizing text, but, at least for now, it has a poor memory. You can only feed it a few pages of text at a time to get summaries back. If you try to, say, feed it an entire journal, it'll error out.  
GPT-3 可能擅长总结文本，但至少就目前而言，它的记忆力很差。您一次只能提供几页文本以获取摘要。例如，如果您尝试向它提供一整本日记，它就会出错。

I needed an alternative solution.   
我需要一个替代解决方案。

Luckily, I discovered a new library called [GPTIndex](https://github.com/jerryjliu/gpt_index) that makes this easy with just a few lines of code. I spent a few hours on it (and some time on the phone with GPTIndex’s creator, [Jerry Liu](https://twitter.com/jerryjliu0)) and eventually arrived at a setup that works like this:  
幸运的是，我发现了一个名为 GPTIndex 的新库，只需几行代码即可轻松完成此操作。我在上面花了几个小时（还花了一些时间与 GPTIndex 的创建者 Jerry Liu 通了电话），最终得出了一个如下所示的设置：

1.  It breaks all of my entries into small chunks.  
    它将我所有的条目分成小块。
2.  It stores them in a form that makes them easily searchable.  
    它以一种易于搜索的形式存储它们。
3.  When I ask a question, it retrieves the most relevant chunks.  
    当我问一个问题时，它会检索最相关的块。
4.  It summarizes the chunks, and then synthesizes the summaries repeatedly until it gets a final answer.  
    它总结了这些块，然后反复综合这些摘要，直到得到最终答案。
5.  It displays the answer. 它显示答案。

Here’s more detail on how it works.  
这是有关其工作原理的更多详细信息。

### **Preparing the journal entries 准备日记帐分录**

The first thing I needed to do was prepare the journal entries. I compiled them into a folder and—using GPTIndex’s GPTSimpleVectorIndex, a data structure—wrote a short script that could break them into chunks and store them in a way that made them easily searchable.  
我需要做的第一件事是准备日记条目。我将它们编译到一个文件夹中，并使用 GPTIndex 的 GPTSimpleVectorIndex 数据结构编写了一个简短的脚本，可以将它们分成块并以易于搜索的方式存储它们。

The code looks like this: 代码如下所示：

[![](optimized_voTHtzZV90yjhT-ouo5XSjFyjyXrpG0P94OBVy_casPy4ycDq58myDvu1zWIzXkWHJSmomS_AA6jcP-nI6VnaTAc6alNH5qWUW4QPeQB_gObp0RlrHpcOjCuxc5liu0u8C0AgNfsPlW-CndcKJ2qnOu6OQlzLmrvGNs6LPVPCO0LIy-3_kD-NjX_WYj_mg.png)](https://d24ovhgu8s7341.cloudfront.net/uploads/editor/posts/2437/optimized_voTHtzZV90yjhT-ouo5XSjFyjyXrpG0P94OBVy_casPy4ycDq58myDvu1zWIzXkWHJSmomS_AA6jcP-nI6VnaTAc6alNH5qWUW4QPeQB_gObp0RlrHpcOjCuxc5liu0u8C0AgNfsPlW-CndcKJ2qnOu6OQlzLmrvGNs6LPVPCO0LIy-3_kD-NjX_WYj_mg.png?link=true)

_(Paid subscribers can access the file_ [_here_](https://every.to/chain-of-thought/code-for-gpt-3-journal-summarizer)_.)_  
（付费订阅者可以在此处访问该文件。）

The result of this code is a single file that contains chunks of all of my journal entries stored so that they can be easily searched and summarized. All I needed to do was write a script to query it.  
此代码的结果是一个文件，其中包含我存储的所有日记条目的块，以便可以轻松地搜索和汇总它们。我所需要做的就是编写一个脚本来查询它。

### Querying the entries 查询条目

The query script is simple, but the details took me a while to figure out.  
查询脚本很简单，但我花了一些时间才弄清楚细节。

It starts by asking the user for what kind of journal chunks it should load. I can write something like, “Collect all of the documents where the author is exhibiting joy, happiness, and excitement”—and it will find the top matches.   
它首先询问用户应该加载哪种日志块。我可以这样写，“收集作者表现出快乐、幸福和兴奋的所有文件”——它会找到最匹配的。

Once the documents are returned, I can ask my actual question. I might ask something like:  
一旦文件被退回，我就可以提出我的实际问题。我可能会问这样的问题：

_“Please summarize the times when the author has exhibited the most joy. Output Identify what caused the happiness. Be truthful, don't make anything up. If you can't find a specific moment of joy don't summarize. Find moments that are surprising.  
“请总结一下作者表现出最大喜悦的时刻。输出 确定是什么导致了幸福。说实话，不要编造任何东西。如果找不到特定的快乐时刻，请不要总结。找到令人惊讶的时刻。  
Please return a list as bullet points.”   
请返回列表作为要点。”_

I have to ask it not to make stuff up so that it stays as close to what it finds in the entries as possible.  
我必须要求它不要编造内容，以便它尽可能接近它在条目中找到的内容。  
 Then it will go through each journal chunk, summarize it to answer my question, and synthesize those summaries until it can produce a single summary of all of the chunks we started with.   
然后它将遍历每个日志块，对其进行总结以回答我的问题，并综合这些摘要，直到它可以生成我们开始的所有块的单一摘要。

While this may sound like a lot of code, it’s mostly done under the hood with GPTIndex. Here’s what the code looks like:  
虽然这听起来可能有很多代码，但它主要是在后台使用 GPTIndex 完成的。代码如下所示：

[![](optimized_hgACbEAOFilJM9d2Wrg_GnQ5t6QQHDoyERoWwS89Wrs_L5zw3gbY4_5D5FhC6RqZKJ4kI0ngkuKMsUf3WNnJSpc4DWGHipundIrzgxzLgug-Rnup9yT7x3NG2fIYPhyfJGu0lqrjFG612ss17j-TMKT75ffD2_Za93i5EHwj4-z9tKi--RUl5DzF-QVEmA.png)](https://d24ovhgu8s7341.cloudfront.net/uploads/editor/posts/2437/optimized_hgACbEAOFilJM9d2Wrg_GnQ5t6QQHDoyERoWwS89Wrs_L5zw3gbY4_5D5FhC6RqZKJ4kI0ngkuKMsUf3WNnJSpc4DWGHipundIrzgxzLgug-Rnup9yT7x3NG2fIYPhyfJGu0lqrjFG612ss17j-TMKT75ffD2_Za93i5EHwj4-z9tKi--RUl5DzF-QVEmA.png?link=true)

_(Paid subscribers can access the file_ [_here_](https://every.to/chain-of-thought/code-for-gpt-3-journal-summarizer)_.)_  
（付费订阅者可以在此处访问该文件。）

## The results 结果

There are a lot of interesting ways to use this technology. A few are too personal to share. “Tell me about why this relationship ended?” produced incredible results—but isn’t something I want to put on the internet.  
有很多有趣的方法可以使用这项技术。有些太私人了，无法分享。 “告诉我为什么这段关系结束了？”产生了令人难以置信的结果——但我不想把它放在互联网上。

Here are some that produced the best answers for me that I'm comfortable sharing:  
以下是一些对我来说最好的答案，我很乐意分享：

___

**What might the author need to learn in order to improve their life?  
为了改善他们的生活，作者可能需要学习什么？**

The author might need to learn:  
作者可能需要学习：

-   How to identify and address underlying beliefs that may be impacting their behavior.  
    如何识别和解决可能影响他们行为的潜在信念。
-   How to differentiate between their own needs and wants and those of other people.  
    如何区分他们自己和其他人的需求和愿望。
-   How to develop strategies for managing ambivalence and inner conflict.  
    如何制定管理矛盾心理和内心冲突的策略。
-   How to prioritize tasks and manage their inbox more effectively.  
    如何确定任务的优先级并更有效地管理收件箱。

___

**What is obvious to everyone around the author, but doesn’t appear obvious to the author?  
什么对作者周围的每个人来说都是显而易见的，但对作者来说并不明显？**

What is obvious to everyone around the author, but doesn't appear to be obvious to the author, is that they have achieved a lot and should be proud of themselves.  
对作者周围的每个人来说显而易见，但对作者而言似乎并不明显的是，他们取得了很多成就，应该为自己感到骄傲。

___

**What is the author’s deepest unmet need?  
作者最深未满足的需求是什么？**

The author's deepest unmet need is for a sense of connection, understanding, and acceptance in their relationships with others, as well as a sense of purpose and appreciation for the little things in life.  
作者最深的未满足需求是在与他人的关系中获得联系感、理解感和接纳感，以及对生活中的小事的目标感和欣赏感。

___

**What are the author’s deepest hopes and dreams?  
作者最深切的希望和梦想是什么？**

The author's deepest hopes and dreams are to write amazing things, build something important, appreciate the little things, and have a job that they can wear a cape to; to bring more awareness to their emotions, create a sense of agency around their experiences, and savor the feeling of excitement for their work.  
作者最深切的希望和梦想是写出令人惊叹的东西，建立重要的东西，欣赏小东西，并拥有一份可以披上斗篷的工作；让更多人意识到他们的情绪，围绕他们的经历创造一种代理感，并体味他们工作的兴奋感。

___

**What is the author’s Myers-Briggs personality type?  
作者的 Myers-Briggs 人格类型是什么？**

Based on the context information provide, it is difficult to determine the author’s Myers-Briggs personality type. However, based on the information provided, it is possible to make an educated guess.  
根据所提供的上下文信息，很难确定作者的 Myers-Briggs 人格类型。但是，根据提供的信息，可以做出有根据的猜测。  
The author appears to be an analytical thinker who is creative and enjoys problem solving. They appear to be organized and have a strong sense of responsibility. They also appear to be open-minded and willing to explore new ideas.  
作者似乎是一位富有创造力并乐于解决问题的分析型思考者。他们看起来很有条理，责任感很强。他们似乎也思想开放，乐于探索新想法。  
Based on these characteristics, it is likely that the author is an INTJ (Introverted, Intuitive, Thinking, Judging) personality type.  
基于这些特征，作者很可能是INTJ（Introverted, Intuitive, Thinking, Judging）人格类型。

___

**If the author were to write a _New York Times_ bestselling book about the intersection of their interests and AI, what would it be about?  
如果作者要写一本关于他们的兴趣与 AI 的交集的《纽约时报》畅销书，它会是关于什么的？**

The author’s _New York Times_ bestselling book would be about how to use AI to find more meaning in their lives.  
作者的纽约时报畅销书将讲述如何使用 AI 在他们的生活中找到更多意义。  
The book would explore how AI can be used to help people better understand their own thoughts and feelings, and how to use that understanding to make better decisions and find more fulfillment in life.  
这本书将探讨如何使用人工智能来帮助人们更好地理解自己的想法和感受，以及如何利用这种理解做出更好的决定并在生活中找到更多的满足感。

___

## My conclusions 我的结论

This experiment appeals to me deeply because it uses technology to speak to the most basic human questions:  
这个实验深深地吸引了我，因为它使用技术来回答最基本的人类问题：

-   Who am I? 我是谁？
-   How did I get here? 我怎么到这里了？
-   Where am I going? 我要去哪里？

And it comes, or seems to come, tantalizingly close to answering them in a useful way. It's far from perfect: its answers are sometimes repetitive. Sometimes they’re generic. Sometimes they’re just plain wrong.   
它来了，或者似乎来了，非常接近以有用的方式回答他们。它远非完美：它的答案有时是重复的。有时它们是通用的。有时他们完全错了。

But sometimes, it provides that valuable “aha!” moment where something clicks. There’s a moment of recognition, and it causes me to remember something about myself that I knew but had forgotten, or that had always been there but hadn’t recognized before.  
但有时，它提供了有价值的“啊哈！”发出咔嗒声的那一刻。有一个瞬间被认出来，它让我想起一些我知道但已经忘记的，或者一直存在但以前没有意识到的关于我自己的事情。  
  That’s when it seems to be the most valuable.  
这时候才显得最值钱。

### **The 'aha' moment “啊哈”时刻**

What is that "aha!" moment, really? Is it insight? Or is it confirmation bias dressed up in insight’s clothes. Does it matter?  
那是什么“啊哈！”片刻，真的吗？是洞察力吗？或者是披着洞察力外衣的确认偏见。有关系吗？

I think it’s probably a bit of both. It’s trained to respond based on _my_ journal entries, so it’s not going to go too far beyond what I’ve said. I think it’s alright to have a tool that can help me understand what _I_ already think, if that’s what it’s doing.   
我认为可能两者兼而有之。它经过训练可以根据我的日记条目做出回应，所以它不会超出我所说的范围。我认为拥有一个可以帮助我理解我已经在想的东西的工具是可以的，如果那是它正在做的事情的话。

But there’s also the worry that it’s subtly putting words in my mouth. Maybe it’s using words to describe me that I never would have used before have now adopted as my own. That could be dangerous if it’s not handled properly.  
但也有人担心它会巧妙地把话塞进我的嘴里。也许它正在使用我以前从未使用过的词来形容我，现在已经被我自己采用了。如果处理不当，那可能很危险。

The dangers are important to point out.  
指出危险很重要。

### **The danger of too much knowledge  
知识过多的危险**

The most obvious danger is security. I don’t recommend uploading your soul to a cloud service unless you’re ready to take on the risks.   
最明显的危险是安全。我不建议将你的灵魂上传到云服务，除非你准备好承担风险。

But beyond the problem of data leaks is the larger problem of knowledge. Every culture has myths about the danger of too much knowledge, starting with Adam and Eve. Eating from the tree of knowledge of good and evil had some pretty terrible consequences, after all.  
但除了数据泄露问题之外，还有更大的知识问题。从亚当和夏娃开始，每种文化都有关于知识过多的危险的神话。毕竟，吃了善恶知识树的果子会产生一些非常可怕的后果。

The most dangerous knowledge of all is, of course, prophecy. And that’s the temptation of this tool: to use its knowledge of my past to get it to tell me about my future. That, too, is fraught in world literature.  
最危险的知识当然是预言。这就是这个工具的诱惑：利用它对我过去的了解，让它告诉我我的未来。这在世界文学中也充满了。  
Oedipus, Macbeth, even Lord Voldemort have found ruin in following prophecy. But the interesting lesson of these literary figures is that it’s not the prophecy that gets you—it’s how you react to the prophecy that does.  
俄狄浦斯、麦克白，甚至伏地魔都曾在跟随预言中遭遇毁灭。但这些文学人物的有趣教训是，让你着迷的不是预言——而是你对预言的反应。

Each of those characters brought about their own ruin by the decisions they made in reaction to knowledge of their fate, not to the knowledge itself. But can you possess knowledge of fate without reacting to it?   
这些角色中的每一个都因他们对自己命运的了解而不是对知识本身的反应而做出的决定导致了自己的毁灭。但是你能拥有命运的知识而不对它做出反应吗？

I feel prepared to handle whatever the model spits back out to me, but I worry about people who might not be ready for it. I don’t yet know what to do but worry about it—and write about it.  
我觉得自己已经准备好应对模特向我反馈的任何问题，但我担心那些可能还没有做好准备的人。我还不知道该怎么办，只是担心它——然后写下来。

### **Incredible powers—and limitations  
难以置信的力量和局限性**

For the time being, we get out of these tools what we put in.  
目前，我们从这些工具中取出我们放入的东西。

The responses we receive are highly dependent on the information fed into the model and the way the prompts are phrased. If you ask leading questions, you’ll get leading answers. For now, we’re building mirrors to show us our own faces in a slightly different light.   
我们收到的回复在很大程度上取决于输入模型的信息和提示的措辞方式。如果你提出领先的问题，你会得到领先的答案。现在，我们正在建造镜子，以稍微不同的光线向我们展示我们自己的脸。

This is valuable in itself. But will the technology advance further?  
这本身就很有价值。但技术会进一步进步吗？

I have a temptation to hope that it will—that feeding myself into a super-intelligence will solve my problems. Eventually it might help, but not totally.  
我有一种希望它会成为现实的诱惑——将自己喂养到超级智能中会解决我的问题。最终它可能会有所帮助，但不完全是。

Any true insight that a theoretical GPT-6 has will bounce off me until I’m ready to hear it. In the words of Thoreau, “The light which puts out our eyes is darkness to us.”   
理论上 GPT-6 的任何真实见解都会从我身上反弹，直到我准备好听到它。用梭罗的话来说，“遮住我们眼睛的光对我们来说就是黑暗。”

For now, building a new way for _me_ to see my own self is valuable enough.  
现在，为我建立一种看待自己的新方式就足够有价值了。

___

_Thanks to_ [_Jerry Liu_](https://twitter.com/jerryjliu0) _for building GPTIndex and generously spending time with me in order to make this experiment possible._  
感谢 Jerry Liu 构建 GPTIndex 并慷慨地花时间与我一起使这个实验成为可能。
