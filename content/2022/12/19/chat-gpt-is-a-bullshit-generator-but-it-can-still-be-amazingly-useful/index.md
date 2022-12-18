---
title: "ChatGPT 是废话生成器。但它仍然非常有用"
date: 2022-12-19T07:00:23+08:00
updated: 2022-12-19T07:00:23+08:00
taxonomies:
  tags: []
extra:
  source: https://aisnakeoil.substack.com/p/chatgpt-is-a-bullshit-generator-but
  hostname: aisnakeoil.substack.com
  author: Arvind Narayanan, Sayash Kapoor
  original_title: "ChatGPT is a bullshit generator. But it can still be amazingly useful"
  original_lang: en
---

The philosopher Harry Frankfurt defined bullshit as speech that is [intended to persuade without regard for the truth](https://en.wikipedia.org/wiki/On_Bullshit). By this measure, OpenAI’s new chatbot ChatGPT is the greatest bullshitter ever. Large Language Models (LLMs) are trained to produce [plausible](https://fediscience.org/@ct_bergstrom/109465410043497711) text, not true statements. ChatGPT is shockingly good at sounding convincing on any conceivable topic. But OpenAI is [clear](https://openai.com/blog/chatgpt/) that there is no source of truth during training. That means that using ChatGPT in its current form would be a bad idea for applications like education or answering health questions. Even though the bot often gives excellent answers, sometimes it fails badly. And it’s always convincing, so it’s hard to tell the difference.

哲学家哈里·法兰克福 (Harry Frankfurt) 将胡说八道定义为旨在说服而不考虑事实真相的言论。按照这个标准，OpenAI 的新聊天机器人 ChatGPT 是有史以来最伟大的胡说八道者。大型语言模型 (LLM) 经过训练以生成似是而非的文本，而不是真实的陈述。 ChatGPT 非常擅长在任何可以想到的话题上听起来令人信服。但 OpenAI 很清楚，在训练过程中没有真实来源。这意味着使用当前形式的 ChatGPT 对于教育或回答健康问题等应用程序来说不是一个好主意。尽管机器人经常给出很好的答案，但有时它会严重失败。而且它总是令人信服，所以很难区分。

Yet, there are three kinds of tasks for which ChatGPT and other LLMs can be extremely useful, despite their inability to discern truth in general:

然而，ChatGPT 和其他 LLM 对三种任务非常有用，尽管它们通常无法辨别真相：

1.  Tasks where it’s easy for the user to check if the bot’s answer is correct, such as debugging help.
    
    用户可以轻松检查机器人答案是否正确的任务，例如调试帮助。
    
2.  Tasks where truth is irrelevant, such as writing fiction.  
    与真相无关的任务，例如写小说。  
    
3.  Tasks for which there does in fact exist a subset of the training data that acts as a source of truth, such as language translation.
    
    实际上确实存在作为真实来源的训练数据子集的任务，例如语言翻译。
    

Let’s dive in. First the bad news, then the good.  
让我们开始吧。首先是坏消息，然后是好消息。  

ChatGPT is the best chatbot released so far. It has delighted users over the last week by generating fantastically weird text, such as an explanation of [how to remove a peanut butter sandwich from a VCR... in biblical verse](https://mobile.twitter.com/tqbf/status/1598513757805858820).

ChatGPT 是迄今为止发布的最好的聊天机器人。上周，它通过生成奇异的文本让用户感到高兴，例如解释如何从 VCR 中取出花生酱三明治......在圣经经文中。

But people are also excited about more serious applications, such as using it as a learning tool. Some are even [predicting](https://twitter.com/jdjkelly/status/1598021488795586561) that it will make Google redundant. Yes, ChatGPT is often extremely good at answering questions. But the danger is that you can't tell when it's wrong unless you already know the answer. We tried some basic information security questions. In most cases, the answers [sounded plausible but were, in fact, bullshit](https://twitter.com/random_walker/status/1598383507214020608). And here’s what happened with more complex questions:

但人们也对更严肃的应用感到兴奋，例如将其用作学习工具。有些人甚至预测它会使谷歌变得多余。是的，ChatGPT 通常非常擅长回答问题。但危险在于，除非您已经知道答案，否则您无法判断什么时候出错了。我们尝试了一些基本的信息安全问题。在大多数情况下，答案听起来很有道理，但实际上是胡说八道。这是更复杂的问题发生的情况：

Another trope about ChatGPT and education: universities are doomed because ChatGPT can write essays. That's silly. Yes, LLMs can write plausible essays. But the death of homework essays is a good thing for learning! We wrote about this [a month ago](https://aisnakeoil.substack.com/p/students-are-acing-their-homework), and nothing has really changed. 

关于 ChatGPT 和教育的另一个比喻：大学注定要失败，因为 ChatGPT 可以写论文。太傻了。是的，法学硕士可以写出似是而非的论文。但是作业作文的死对学习来说是件好事！我们一个月前就写过这篇文章，现在什么都没有真正改变。

What about search? Google's knowledge panels are already notorious for presenting misinformation authoritatively. Replacing them with an LLM could make things much worse. A [paper](https://dl.acm.org/doi/pdf/10.1145/3498366.3505816) by Chirag Shah and Emily Bender explores how things could go wrong if we replace search engines with LLMs.

搜索呢？谷歌的知识面板已经因权威地提供错误信息而臭名昭著。用 LLM 代替它们可能会使事情变得更糟。 Chirag Shah 和 Emily Bender 的一篇论文探讨了如果我们用 LLM 取代搜索引擎，事情会怎样出错。

The fact that these models can’t discern the truth is why Meta’s [Galactica](https://www.technologyreview.com/2022/11/18/1063487/meta-large-language-model-ai-only-survived-three-days-gpt-3-science/), an LLM for science, was an ill-conceived idea. In science, accuracy is the whole point. The backlash was swift, and the public demo was pulled down after three days. Similarly, [correctness and reliability](https://www.jmir.org/2018/9/e11510/) are everything if you want to use an LLM for answering health-related queries.

事实上，这些模型无法辨别真相，这就是为什么 Meta 的卡拉狄加，一个科学的法学硕士，是一个考虑不周的想法。在科学中，准确性是重点。强烈反对很快，三天后公开演示被撤下。同样，如果您想使用 LLM 来回答与健康相关的查询，那么正确性和可靠性就是一切。

Of course. But their ability to sound convincing is getting better just as [quickly](https://garymarcus.substack.com/p/how-come-gpt-can-seem-so-brilliant)! So we suspect it's getting harder for even experts to spot mistakes. 

当然。但他们听起来令人信服的能力正以同样快的速度变得更好！所以我们怀疑即使是专家也越来越难发现错误。

In fact, models such as Galactica and ChatGPT are great at generating authoritative-sounding text in any requested style: legalese, bureaucratese, wiki pages, academic papers, lecture notes, and even answers for Q&A forums. One side effect is that we can no longer rely on the _form_ of a text to gauge trustworthiness and legitimacy. 

事实上，Galactica 和 ChatGPT 等模型非常擅长以任何要求的风格生成听起来权威的文本：法律术语、官僚术语、维基页面、学术论文、讲义，甚至是问答论坛的答案。一个副作用是我们不能再依赖文本的形式来衡量可信度和合法性。

[StackOverflow found out the hard way](https://meta.stackoverflow.com/questions/421831/temporary-policy-chatgpt-is-banned). On the website, users answer programming questions to earn points, and points bring privileges like fewer ads and access to moderator tools. After ChatGPT was released openly to the public, the Q&A forum got thousands of incorrect answers generated using the LLM. But because the answers were written in the right style, they had to be vetted by experts before they could be removed. Within a week, the company had to ban answers generated using ChatGPT to reduce the number of plausible-sounding incorrect answers.

StackOverflow 发现了困难的方法。在网站上，用户通过回答编程问题来赚取积分，而积分会带来诸如减少广告和使用版主工具等特权。在 ChatGPT 向公众公开发布后，问答论坛收到了数千个使用 LLM 生成的错误答案。但由于答案的写作风格正确，因此在删除之前必须经过专家审查。一周之内，该公司不得不禁止使用 ChatGPT 生成的答案，以减少听起来似是而非的错误答案的数量。

Unless the accuracy of LLM responses can be improved, we suspect that the set of legitimate applications will remain relatively circumscribed. Note that GPT-3 is 2.5 years old. We're told the field is progressing every week, so that's like centuries. When it was released, people confidently predicted that there would be a “Cambrian explosion” of applications. But so far, there have been zero mainstream applications — except GitHub Copilot, if you count programming as mainstream.

除非可以提高 LLM 响应的准确性，否则我们怀疑合法应用程序集仍将相对受限。请注意，GPT-3 已有 2.5 年历史。我们被告知该领域每周都在进步，就像几个世纪一样。当它发布时，人们满怀信心地预测，将会出现应用程序的“寒武纪大爆发”。但到目前为止，主流应用程序为零——如果你把编程算作主流的话，除了 GitHub Copilot。

The accuracy issue is not necessarily hopeless. Intriguingly, LLMs seem to acquire some capacity to discern truth as a byproduct of learning to sound convincing. When researchers [asked](https://arxiv.org/pdf/2207.05221.pdf) an LLM to evaluate its own proposed answers for accuracy, it did far better than random chance! Work is underway to integrate this ability into the default behavior of chatbots, so that accurate answers are more likely to be produced.

准确性问题不一定是无望的。有趣的是，法学硕士似乎获得了一些辨别真相的能力，这是学习听起来令人信服的副产品。当研究人员要求 LLM 评估其自己提出的答案的准确性时，它的表现远好于随机机会！正在努力将这种能力整合到聊天机器人的默认行为中，以便更有可能产生准确的答案。

Meanwhile, here are three kinds of tasks for which LLMs are already useful.

同时，LLM 已经可以用于以下三种任务。

Debugging code is an application where programmers, especially novices, could benefit from LLMs. Note that once a bug is pointed out, it is generally easy to verify, so the fact that the bot’s answers might sometimes be wrong isn’t as much of a concern.

调试代码是程序员，尤其是新手，可以从 LLM 中受益的应用程序。请注意，一旦指出错误，通常很容易验证，因此机器人的答案有时可能是错误的这一事实并不是什么大问题。

_Generating_ code is a tricker story. In theory, the user can verify that automatically generated code is free of bugs (perhaps with the help of LLMs). But it is unclear whether this would be faster than manually writing the code. Security bugs are a particularly serious concern. A [study](https://arxiv.org/abs/2108.09293) last year found that Copilot generated insecure code 40% of the time. They don’t compare this figure to human programmers or offer an opinion on whether and when Copilot use is appropriate, but it is clear from the result that caution is warranted.

生成代码是一个骗人的故事。理论上，用户可以验证自动生成的代码没有错误（可能借助 LLM）。但尚不清楚这是否会比手动编写代码更快。安全漏洞是一个特别严重的问题。去年的一项研究发现，Copilot 有 40% 的时间生成不安全代码。他们没有将这个数字与人类程序员进行比较，也没有就 Copilot 使用是否合适以及何时合适提出意见，但从结果中可以清楚地看出，谨慎是有必要的。

Copilot is intended to increase the productivity of experts. What about users who can’t code — can they use AI tools to generate simple scripts? There’s a lot of promise here, too. Here’s one small experiment:

Copilot 旨在提高专家的工作效率。那些不会编码的用户怎么办——他们可以使用 AI 工具生成简单的脚本吗？这里也有很多希望。这是一个小实验：

The use of LLMs for code generation is an [active area](https://www.deepmind.com/blog/competitive-programming-with-alphacode) of [research](https://arxiv.org/pdf/2207.01780.pdf). There’s a lot of room for improvement in terms of increasing the correctness of the generated code and decreasing the frequency of bugs. This is an exciting area to watch.

使用 LLM 生成代码是一个活跃的研究领域。在提高生成代码的正确性和降低错误频率方面还有很大的改进空间。这是一个令人兴奋的领域。

ChatGPT has been a source of entertainment over the last week. From [writing jokes on specific personalities](https://twitter.com/gfodor/status/1598916489993940993) to explaining algorithms in the [style of fast-talking wise guys](https://twitter.com/goodside/status/1598077257498923010), people have found many creative uses for the tool. But could we use ChatGPT for more ambitious projects, such as writing fiction?

ChatGPT 上周一直是娱乐的来源。从写关于特定人物的笑话到以机智的智者风格解释算法，人们发现了该工具的许多创造性用途。但是我们可以将 ChatGPT 用于更雄心勃勃的项目，例如写小说吗？

LLMs are quite far from being able to produce long pieces of text, such as entire novels, because they can only store a [small number of tokens at a time](https://twitter.com/goodside/status/1598882343586238464?s=20&t=9aOBVGU1F7x9k4S14HxwJg). Still, authors and researchers are experimenting with them to generate ideas, [expand](https://www.wired.com/story/k-allado-mcdowell-gpt-3-amor-cringe/) on their prompts, and change the style of a text (e.g., "[rewrite this text to be more Dickensian](https://dl.acm.org/doi/fullHtml/10.1145/3490099.3511105)"). Interactive fiction games like [AI Dungeon](https://play.aidungeon.io/main/home) use LLMs to flesh out storylines using user inputs. We believe there is no fundamental barrier to continuing improvements in this area.

LLM 远不能生成长文本，例如整本小说，因为它们一次只能存储少量的标记。尽管如此，作者和研究人员仍在试验它们以产生想法、扩展他们的提示并更改文本的样式（例如，“重写此文本以使其更像狄更斯式的”）。像 AI Dungeon 这样的互动小说游戏使用 LLM 来充实用户输入的故事情节。我们相信在这一领域的持续改进不存在根本性障碍。

Similarly, text-to-image and image-to-image tools are useful for entertainment because creators can tune the prompt till they find an image they like. The latest app to make waves is [Lensa](https://prisma-ai.com/lensa), which creates portraits in various styles once the user uploads a few selfies. Its backend uses Stable Diffusion, an open-source image generation model from Stability AI.

同样，文本到图像和图像到图像工具对于娱乐很有用，因为创作者可以调整提示，直到找到他们喜欢的图像。最新掀起波澜的应用程序是 Lensa，一旦用户上传几张自拍照，它就会创建各种风格的肖像。它的后端使用 Stable Diffusion，这是一种来自 Stability AI 的开源图像生成模型。

Before we get carried away by this potential: racist, sexist, and biased outputs are still a problem for all generative models, [including ChatGPT](https://twitter.com/spiantado/status/1599462375887114240?s=20&t=vV-g_kUAg3L2era1c5G_aw). The model includes a [content filter](https://openai.com/blog/chatgpt/) that declines inappropriate requests, which works well enough to feel like a big improvement over previous tools, but there is still a long way to go.

在我们被这种潜力冲昏头脑之前：种族主义、性别歧视和有偏见的输出仍然是所有生成模型（包括 ChatGPT）的问题。该模型包括一个拒绝不当请求的内容过滤器，效果很好，感觉比以前的工具有了很大的改进，但还有很长的路要走。

Remarkably, GPT-3 [performs](https://arxiv.org/abs/2005.14165) roughly on par with special-purpose language translation models, and ChatGPT likely does as well. The likely reason is that it can exploit ground truth in the corpus (which consists, to a first approximation, of all text on the web). For example, there are web pages that are translated into multiple languages. Of course, during training, no explicit labels are provided to tell the model which texts correspond to each other, but presumably, the model can figure this out automatically[1](https://aisnakeoil.substack.com/p/chatgpt-is-a-bullshit-generator-but#footnote-1-88973379).

值得注意的是，GPT-3 的性能与专用语言翻译模型大致相当，ChatGPT 可能也是如此。可能的原因是它可以利用语料库中的基本事实（它包含网络上所有文本的初步近似值）。例如，有被翻译成多种语言的网页。当然，在训练期间，没有提供明确的标签来告诉模型哪些文本相互对应，但据推测，模型可以自动解决这个问题。

It’s not obvious why a chatbot would be a better tool for translation than existing tools like Google translate if their performance is equivalent. One possibility is that in a conversation between two speakers of different languages, a tool like ChatGPT could play the role of an interpreter, the advantage being that a tool used within a conversation can keep track of the dialog. This would allow it to rely on context and perform much more effectively and with far less awkwardness for the users.

如果聊天机器人的性能相当，为什么聊天机器人会比现有工具（如谷歌翻译）更好。一种可能性是，在两个使用不同语言的人之间的对话中，像 ChatGPT 这样的工具可以扮演翻译的角色，其优点是对话中使用的工具可以跟踪对话。这将允许它依赖于上下文并更有效地执行并且对用户来说更少尴尬。

Generative AI releases tend to look impressive based on cherry-picked examples that go viral. But that's [not the full picture](https://twitter.com/fchollet/status/1598147044744777729). For many applications, even a 10% failure rate is too high. There seem to be a fairly limited set of use cases where the lack of a source of truth isn’t a deal breaker. While these uses are still tremendously exciting, it’s far from obvious that people will soon be using chatbots in their everyday lives — for learning, or as a search replacement, or as a conversation partner.

基于精心挑选的病毒式传播示例，生成式 AI 版本往往看起来令人印象深刻。但这还不是全部。对于许多应用程序，即使是 10% 的故障率也太高了。似乎有一组相当有限的用例，其中缺乏真实来源不会破坏交易。虽然这些用途仍然非常令人兴奋，但人们很快就会在日常生活中使用聊天机器人——用于学习、搜索替代品或对话伙伴——还远未明朗。

Meanwhile, we’ve seen the first prominent use of LLMs for misinformation (on Stack Overflow). Of course, spammers were already using GPT-3 for search engine marketing and are [delighted](https://twitter.com/kavirkaycee/status/1599027845094744064) to get their hands on ChatGPT. But just as the predictions of transformation are overblown, we don’t agree with claims that the web will soon drown in an ocean of misinformation.

与此同时，我们已经看到了 LLM 首次被显着地用于错误信息（在 Stack Overflow 上）。当然，垃圾邮件发送者已经在使用 GPT-3 进行搜索引擎营销，并且很高兴能够使用 ChatGPT。但是，正如对转型的预测被夸大了一样，我们不同意网络将很快淹没在错误信息海洋中的说法。

We look forward to how people will use LLMs creatively as much as we cringe at the hype and the usual [self-serving AGI talk](https://twitter.com/elonmusk/status/1599128577068650498?s=20&t=-51HkNswEoX8uyGOw5_xPg).

我们期待人们如何创造性地使用 LLM，就像我们对炒作和通常的自利 AGI 谈话感到畏缩一样。

### Subscribe to **AI Snake Oil**  
订阅AI蛇油  

What AI \*can't\* do  
人工智能\*不能\*做什么
