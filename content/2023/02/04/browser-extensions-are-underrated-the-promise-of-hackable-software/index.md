---
title: "浏览器扩展被低估：可破解软件的承诺"
date: 2023-02-04T01:19:11+08:00
updated: 2023-02-04T01:19:11+08:00
taxonomies:
  tags: []
extra:
  source: https://www.geoffreylitt.com/2019/07/29/browser-extensions.html
  hostname: www.geoffreylitt.com
  author: 
  original_title: "Browser extensions are underrated: the promise of hackable software"
  original_lang: en
---

![Lego bricks](legos.jpg)

Photo by [Rick Mason on Unsplash](https://unsplash.com/photos/2FaCKyEEtis)  
Rick Mason 在 Unsplash 上拍摄的照片

Recent conversations about web browser extensions have focused on controversy: [malicious browser extensions capturing web history](https://arstechnica.com/information-technology/2019/07/dataspii-inside-the-debacle-that-dished-private-data-from-apple-tesla-blue-origin-and-4m-people/), and [Google limiting the capabilities used by ad blockers](https://www.wired.com/story/google-chrome-ad-blockers-extensions-api/?verso=true). These are important discussions, but we shouldn’t lose sight of the big picture: browser extensions are a special ecosystem worth celebrating.  
最近关于网络浏览器扩展的讨论集中在争议上：恶意浏览器扩展捕获网络历史，谷歌限制广告拦截器使用的功能。这些都是重要的讨论，但我们不应该忽视大局：浏览器扩展是一个值得庆祝的特殊生态系统。

Among major software platforms today, **browser extensions are the rare exception that allow and encourage users to modify the apps that we use**, in creative ways not intended by their original developers. On smartphone and desktop platforms, this sort of behavior ranges from unusual to impossible, but in the browser it’s an everyday activity.  
在当今的主要软件平台中，浏览器扩展是罕见的例外，它允许并鼓励用户以并非其原始开发人员意图的创造性方式修改我们使用的应用程序。在智能手机和桌面平台上，这种行为从不寻常到不可能发生，但在浏览器中却是日常活动。

Browser extensions remind us what it’s like to have deep control over how we use our computers.  
浏览器扩展提醒我们深入控制我们使用计算机的方式是什么感觉。

## Assembling our own software[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#assembling-our-own-software)  
组装我们自己的软件[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#assembling-our-own-software)

Once a software platform reaches a certain level of openness, it can fundamentally change the way that normal users relate to their software.  
一旦软件平台达到一定程度的开放性，它就可以从根本上改变普通用户与其软件相关的方式。  
By installing four different Gmail extensions that modify everything from the visual design to the core functionality, in some sense, I’ve put together my own email client. **Instead of being a passive user of pre-built applications, I can start assembling my own personalized way of using my computer.**  
通过安装四个不同的 Gmail 扩展程序，从视觉设计到核心功能，从某种意义上说，我已经组装了我自己的电子邮件客户端。我不再是预建应用程序的被动用户，而是可以开始组装我自己的个性化计算机使用方式。

The popularity of browser extensions proves that many people are interested in customizing their software, and it’s not just a hobby for power users. There are over 180,000 extensions on the Chrome store, and nearly half of all Chrome users have browser extensions installed.<sup id="fnref1" data-immersive-translate-effect="1"><a href="https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#fn1" rel="footnote">1</a></sup> When people have an easy way to extend their software with useful functionality, they apparently take advantage.  
浏览器扩展的流行证明很多人都对定制他们的软件感兴趣，而这不仅仅是高级用户的爱好。 Chrome 商店中有超过 180,000 个扩展程序，近一半的 Chrome 用户都安装了浏览器扩展程序。 <sup id="fnref1" data-immersive-translate-effect="1"><a href="https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#fn1" rel="footnote">1</a></sup> 当人们有一种简单的方法来用有用的功能扩展他们的软件时，他们显然会利用。

## Hackable platforms, not custom APIs[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#hackable-platforms-not-custom-apis)  
可入侵平台，而非自定义 API[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#hackable-platforms-not-custom-apis)

Browser extensions have remarkably broad use cases.  
浏览器扩展具有非常广泛的用例。  
I personally use Chrome extensions that fill in my passwords, help me read Japanese kanji, simplify the visual design of Gmail, let me highlight and annotate articles, save articles for later reading, play videos at 2x speed, and of course, block ads.  
我个人使用 Chrome 扩展程序来填写我的密码，帮助我阅读日文汉字，简化 Gmail 的视觉设计，让我突出显示和注释文章，保存文章供以后阅读，以 2 倍速度播放视频，当然还有屏蔽广告。

**The key to this breadth is that most extensions modify applications in ways that the original developers didn’t specifically plan for.** When Japanese newspapers publish articles, they’re not thinking about compatibility with the kanji reading extension.  
这种广度的关键是大多数扩展以原始开发人员未专门计划的方式修改应用程序。当日本报纸发表文章时，他们并没有考虑与汉字阅读扩展的兼容性。  
Extension authors gain creative freedom because they don’t need to use application-specific APIs that reflect the original developers’ view of how people might want to extend their application.  
扩展作者获得了创作自由，因为他们不需要使用反映原始开发人员对人们可能希望如何扩展其应用程序的观点的特定于应用程序的 API。

The web platform has a few qualities that enable this sort of unplanned extensibility. The foundational one is that the classic web deployment style is to ship all the client code to the browser in human-readable form.  
Web 平台有一些特性可以实现这种计划外的可扩展性。最基本的是，经典的 Web 部署风格是以人类可读的形式将所有客户端代码发送到浏览器。  
(Source maps are a key to preserving this advantage as we ship more code that’s minified or compiled from other languages.  
（源映射是保持这一优势的关键，因为我们发布了更多从其他语言压缩或编译的代码。  
) The web’s layout model also promotes extensibility by encouraging standardized semantic markup—my password manager extension works because web pages reliably use form tags for password submissions instead of building their own version.  
) Web 的布局模型还通过鼓励标准化语义标记来提高可扩展性——我的密码管理器扩展之所以有效，是因为网页可靠地使用表单标签来提交密码，而不是构建自己的版本。

Even with these advantages, it can still require clever tricks to modify a site in ways that it wasn’t built for. But it’s often a reasonable amount of work, not a years-long reverse engineering effort.  
即使有这些优势，它仍然需要巧妙的技巧才能以非构建网站的方式修改网站。但这通常是合理的工作量，而不是长达数年的逆向工程工作。  
The sheer variety of extensions available shows that extension authors are willing to jump through a few hoops to create useful software.  
可用扩展的种类繁多表明扩展作者愿意跳过几个环节来创建有用的软件。

Occasionally there are tensions between website developers and extension authors, but it seems far more common that developers are fine with their sites being extended in creative ways, as long as they don’t have to do any extra work.  
网站开发人员和扩展作者之间偶尔会出现紧张关系，但更常见的情况是，开发人员对以创造性方式扩展他们的网站没有意见，只要他们不需要做任何额外的工作。  
Extensions can even make life easier for application developers: if there’s a niche request that a small minority of users want, a motivated community member can just build an extension to support it.  
扩展甚至可以让应用程序开发人员的生活更轻松：如果有一小部分用户想要的小众请求，有积极性的社区成员可以构建一个扩展来支持它。  
By building on a hackable platform, developers allow their users to get even more value out of their applications.  
通过建立在一个可破解的平台上，开发人员允许他们的用户从他们的应用程序中获得更多价值。

Many browser extensions are generic tools designed to enhance my use of all websites. I can use my annotation extension on every website everywhere, instead of needing a different highlighting tool for each article I read.  
许多浏览器扩展都是通用工具，旨在增强我对所有网站的使用。我可以在任何地方的每个网站上使用我的注释扩展，而不是需要为我阅读的每篇文章使用不同的突出显示工具。  
Just like using a physical highlighter with paper articles, I can master the tool once, and get a lot of leverage by applying it in different contexts.  
就像在纸质文章中使用物理荧光笔一样，我可以一次掌握该工具，并通过在不同的上下文中应用它来获得很多影响力。

In many software platforms, we think of the operating system as providing the cross-cutting tools, and third parties as providing standalone “apps” that are used in isolation. **With browser extensions, third parties are also adding tools;** a single piece of software has the leverage to change my experience across all the apps I use.  
在许多软件平台中，我们认为操作系统提供横切工具，第三方提供独立使用的“应用程序”。随着浏览器扩展，第三方也在添加工具；单个软件可以改变我使用的所有应用程序的体验。

When software is built in small units, it also changes the economics. Most extensions I use are free, and are perhaps too small in their feature set to support a full-blown business. And yet, people still choose to make them, and I benefit immensely from these little bits of software.  
当软件以小单元构建时，它也会改变经济。我使用的大多数扩展都是免费的，而且它们的功能集可能太小而无法支持成熟的业务。然而，人们仍然选择制作它们，我从这些小软件中获益匪浅。  
Browsing the extension store feels more like going to a local flea market than going to a supermarket. Massive software built by huge companies isn’t the only way.  
浏览扩展商店感觉更像是去当地的跳蚤市场，而不是去超市。由大公司构建的大型软件并不是唯一的方法。

## The origins of openness[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#the-origins-of-openness)  
开放的起源[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#the-origins-of-openness)

It’s not an accident that this openness emerged on the web platform.  
这种开放性出现在网络平台上并非偶然。

Since the beginning of personal computing, there’s been a philosophical tradition that encourages using computers as an interactive medium where people contribute their own ideas and build their own tools—authorship over consumption.  
自从个人计算诞生以来，就有一种哲学传统鼓励使用计算机作为一种交互媒介，人们可以在其中贡献自己的想法并构建自己的工具——作者身份高于消费。  
This idea is reflected in systems like Smalltalk, Hypercard, and more recently, [Dynamicland](https://dynamicland.org/).  
这个想法反映在 Smalltalk、Hypercard 以及最近的 Dynamicland 等系统中。

When Tim Berners-Lee created the World Wide Web, he imagined it fitting into this tradition. “My vision was a system in which sharing what you knew or thought should be as easy as learning what someone else knew.”<sup id="fnref2" data-immersive-translate-effect="1"><a href="https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#fn2" rel="footnote">2</a></sup> There were some hiccups along the way<sup id="fnref3" data-immersive-translate-effect="1"><a href="https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#fn3" rel="footnote">3</a></sup>, but eventually that vision largely won out, and the Web became a place where anyone can publish their opinions or photos through social media platforms.  
当 Tim Berners-Lee 创建万维网时，他设想它符合这一传统。 “我的愿景是建立一个系统，在这个系统中，分享你的知识或想法应该像学习别人的知识一样容易。” <sup id="fnref2" data-immersive-translate-effect="1"><a href="https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#fn2" rel="footnote">2</a></sup> 在 <sup id="fnref3" data-immersive-translate-effect="1"><a href="https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#fn3" rel="footnote">3</a></sup> 的过程中遇到了一些小问题，但最终这一愿景在很大程度上取得了胜利，网络成为任何人都可以通过社交媒体平台发布意见或照片的地方。

Still, there’s a catch. When you’re using Facebook, you’re operating within a confined experience. You’re forced to publish in a certain format, and to use their app in a certain way (that includes, of course, seeing all the ads).  
尽管如此，还是有一个问题。当您使用 Facebook 时，您是在受限的体验中操作。你被迫以某种格式发布，并以某种方式使用他们的应用程序（当然，包括看到所有广告）。  
There’s more room for authorship than just browsing a news website, but only within the strict lines the app has painted for you.  
作者身份的空间不仅仅是浏览新闻网站，但仅限于应用程序为您绘制的严格界限内。

**Browser extensions offer a deeper type of control.** Instead of merely typing into the provided text box, we can color outside the lines and deeply modify the way we use any application on the web. Browser extensions offer a kind of decentralization: large companies building major websites don’t get to dictate all the details of our experience.  
浏览器扩展提供了更深层次的控制。我们不仅可以在提供的文本框中键入内容，还可以在行外着色并深入修改我们在 Web 上使用任何应用程序的方式。浏览器扩展提供了一种去中心化：构建主要网站的大公司无法支配我们体验的所有细节。

## Improving on extensions[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#improving-on-extensions)  
改进扩展[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#improving-on-extensions)

We clearly need to work on protecting people from malicious extensions that invade their privacy. But beyond that, here are some bigger picture opportunities I see for improving on extensions:  
我们显然需要努力保护人们免受侵犯他们隐私的恶意扩展。但除此之外，我还看到了一些改进扩展的更大前景的机会：

**Accessibility:** Today, it requires a big jump to go from using browser extensions to creating them: you need to learn a fair amount of web development to get started, and you can’t easily develop extensions in the browser itself.  
可访问性：今天，从使用浏览器扩展到创建它们需要一个巨大的飞跃：你需要学习大量的网络开发才能开始，而且你不能轻易地在浏览器本身中开发扩展。  
What if there were a quick way to get started developing and sharing extensions in the browser? You could imagine smoothly transitioning from editing a website in the developer tools to publishing a small extension.  
如果有一种快速的方法可以开始在浏览器中开发和共享扩展，那会怎样？您可以想象从在开发人员工具中编辑网站顺利过渡到发布小型扩展。

_Update_: I’ve started working on a system called [Wildcard](https://sdg.csail.mit.edu/projects/wildcard) to work towards this vision.  
更新：我已经开始研究一个名为 Wildcard 的系统来实现这一愿景。

**Compatibility:** Because extensions hook into websites in unsupported ways, updates to websites often result in extensions temporarily breaking, and extension authors scrambling to fix them.  
兼容性：由于扩展以不受支持的方式连接到网站，因此网站更新通常会导致扩展暂时中断，而扩展作者则争先恐后地修复它们。  
Can we make it easier for website developers and extension authors to form stable connections between their software, without necessarily resorting to using explicit extension APIs?  
我们能否让网站开发人员和扩展作者更容易地在他们的软件之间形成稳定的连接，而不必求助于使用显式扩展 API？

There are existing practices that fit into this category already—for example, using clean semantic markup, human-readable CSS, and source maps makes it easier to develop an extension.  
已经有适合这一类别的现有实践——例如，使用干净的语义标记、人类可读的 CSS 和源映射可以更容易地开发扩展。

A simple change that would allow for more stable extensions would be to give users more control over when they upgrade to new versions of cloud software.  
允许更稳定扩展的一个简单更改是让用户更好地控制何时升级到新版本的云软件。  
If I have a 3 month window to continue using an old version after the new one is released, that would give extension authors more time to upgrade their software for the new version.  
如果在新版本发布后我有 3 个月的时间继续使用旧版本，那么扩展作者将有更多时间为新版本升级他们的软件。

**Power:** Web extensions are limited in their power by the typical architecture of web applications: they have broad rights to modify the browser client, but the server is off limits.  
权力：网络扩展的权力受到典型网络应用程序架构的限制：他们拥有修改浏览器客户端的广泛权利，但服务器不受限制。  
For example, if my social media app’s server only provides an endpoint for querying my posts in chronological order, no browser extension can ever search through all my posts by keyword. How could we rethink the client-server boundary to enable extensions to make even deeper modifications?  
例如，如果我的社交媒体应用程序的服务器只提供一个端点来按时间顺序查询我的帖子，那么任何浏览器扩展程序都无法按关键字搜索我的所有帖子。我们如何重新考虑客户端-服务器边界以启用扩展以进行更深层次的修改？

This raises tough questions around security and privacy. The modern browser extension API has done a good job balancing extensibility with security, and yet we’re still grappling with the consequences of browser extensions invading people’s privacy.  
这引发了有关安全和隐私的棘手问题。现代浏览器扩展 API 在平衡可扩展性和安全性方面做得很好，但我们仍在努力应对浏览器扩展侵犯人们隐私的后果。  
Giving extensions more power would raise the stakes further. Still, we shouldn’t give up in the name of security—we should fight for extensibility as a value and find ways to balance these interests.  
赋予扩展更多权力将进一步增加赌注。尽管如此，我们不应该以安全的名义放弃——我们应该为可扩展性作为一种价值而斗争，并找到平衡这些利益的方法。

## The next platform[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#the-next-platform)  
下一个平台[](https://www.geoffreylitt.com/2019/07/29/browser-extensions.html#the-next-platform)

I’m intrigued by a couple projects that are rethinking the web in ways that might make it more extensible:  
我对一些以可能使其更具可扩展性的方式重新思考网络的项目很感兴趣：

The [Beaker Browser](https://beakerbrowser.com/about/) and the decentralized web community are exploring how the web works without centralized servers. It seems like their proposed architecture would give users fuller control over modifying the “server” side of web applications.  
Beaker 浏览器和去中心化网络社区正在探索网络如何在没有集中式服务器的情况下工作。看起来他们提议的架构会让用户更全面地控制修改 Web 应用程序的“服务器”端。

Tim Berners-Lee is working on a new project called [SOLID](https://inrupt.com/blog/one-small-step-for-the-web). I don’t yet understand precisely what they’re up to, but given Tim’s involvement I figure it’s worth paying attention.  
Tim Berners-Lee 正在从事一个名为 SOLID 的新项目。我还不明白他们到底在做什么，但考虑到蒂姆的参与，我认为这值得关注。  
A key principle is giving users more ownership over their data, which would enable people to use extensions and other software to manipulate their data in flexible ways beyond what application server APIs allow.  
一个关键原则是让用户对他们的数据有更多的所有权，这将使人们能够使用扩展和其他软件以超出应用程序服务器 API 允许的灵活方式来操作他们的数据。

Computing is still young, and platforms are changing quickly. Modern browser extensions and smartphone platforms have only been around for about a decade. These platforms will evolve, and there will be new platforms after them, and we will get to collectively decide how open they will be.  
计算还很年轻，平台变化很快。现代浏览器扩展和智能手机平台才出现了大约十年。这些平台会不断发展，之后还会有新的平台，我们将共同决定它们的开放程度。

Browser extensions give us one example to strive for: a place where we routinely hack the software we use and make it our own. ▪  
浏览器扩展为我们提供了一个努力争取的例子：一个我们经常破解我们使用的软件并将其变成我们自己的地方。 ▪

[_Discuss on Hacker News  
讨论 Hacker News_](https://news.ycombinator.com/item?id=20556382)
