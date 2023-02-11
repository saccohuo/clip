---
title: "ChatGPT是Web的模糊JPEG"
date: 2023-02-11T19:25:38+08:00
updated: 2023-02-11T19:25:38+08:00
taxonomies:
  tags: []
extra:
  source: https://www.newyorker.com/tech/annals-of-technology/chatgpt-is-a-blurry-jpeg-of-the-web
  hostname: www.newyorker.com
  author: Ted Chiang
  original_title: "ChatGPT Is a Blurry JPEG of the Web"
  original_lang: en
---

In 2013, workers at a German construction company noticed something odd about their Xerox photocopier: when they made a copy of the floor plan of a house, the copy differed from the original in a subtle but significant way.  

2013年，一家德国建筑公司的工人注意到他们的施乐复印机有些奇怪：当他们复制一个房子的平面图时，复制品与原件有细微而显著的不同。  

In the original floor plan, each of the house’s three rooms was accompanied by a rectangle specifying its area: the rooms were 14.13, 21.11, and 17.42 square metres, respectively. However, in the photocopy, all three rooms were labelled as being 14.13 square metres in size.  

在最初的楼层平面图中，房子的三个房间都附有一个矩形，说明其面积：这些房间分别为14.13、21.11和17.42平方米。然而，在复印件中，所有三个房间的面积都被标为14.13平方米。  

The company contacted the computer scientist David Kriesel to investigate this seemingly inconceivable result. They needed a computer scientist because a modern Xerox photocopier doesn’t use the physical [xerographic process](https://www.newyorker.com/magazine/2018/02/12/why-paper-jams-persist) popularized in the nineteen-sixties. Instead, it scans the document digitally, and then prints the resulting image file. Combine that with the fact that virtually every digital image file is compressed to save space, and a solution to the mystery begins to suggest itself.  

该公司联系了计算机科学家大卫·克里塞尔，调查这一看似不可思议的结果。他们需要一位计算机科学家，因为现代施乐复印机不使用20世纪60年代流行的物理静电复印过程。相反，它以数字方式扫描文档，然后打印生成的图像文件。联合收割机事实上每一个数字图像文件都被压缩以保存空间，这个谜团的解决方案就开始出现了。

Compressing a file requires two steps: first, the encoding, during which the file is converted into a more compact format, and then the decoding, whereby the process is reversed.  

压缩文件需要两个步骤：首先是编码，在编码期间文件被转换成更紧凑的格式，然后是解码，由此该过程是相反的。  

If the restored file is identical to the original, then the compression process is described as lossless: no information has been discarded.  

如果恢复的文件与原始文件相同，则压缩过程称为无损压缩：没有信息被丢弃。  

By contrast, if the restored file is only an approximation of the original, the compression is described as lossy: some information has been discarded and is now unrecoverable.  

相比之下，如果还原的文件只是原始文件的近似值，则将压缩描述为有损压缩：一些信息已被丢弃并且现在不可恢复。  

Lossless compression is what’s typically used for text files and computer programs, because those are domains in which even a single incorrect character has the potential to be disastrous.  

无损压缩通常用于文本文件和计算机程序，因为在这些领域中，即使是一个不正确的字符也有可能造成灾难性的后果。  

Lossy compression is often used for photos, audio, and video in situations in which absolute accuracy isn’t essential. Most of the time, we don’t notice if a picture, song, or movie isn’t perfectly reproduced.  

有损压缩通常用于绝对准确性不重要的情况下的照片、音频和视频。大多数情况下，我们不会注意到图片、歌曲或电影是否被完美地复制。  

The loss in fidelity becomes more perceptible only as files are squeezed very tightly. In those cases, we notice what are known as compression artifacts: the fuzziness of the smallest _JPEG_ and _MPEG_ images, or the tinny sound of low-bit-rate [MP3s](https://www.newyorker.com/culture/culture-desk/the-warm-glow-of-the-blog-rock-era).  

只有当文件被压缩得非常紧时，保真度的损失才变得更加明显。在这些情况下，我们会注意到所谓的压缩伪像：最小的jpeg和mpeg图像的模糊，或者低比特率MP3的微弱声音。

Xerox photocopiers use a lossy compression format known as _JBIG_2, designed for use with black-and-white images. To save space, the copier identifies similar-looking regions in the image and stores a single copy for all of them; when the file is decompressed, it uses that copy repeatedly to reconstruct the image.  

施乐复印机使用一种称为jbig 2的有损压缩格式，专为白色图像设计。为了保存空间，复印机识别图像中看起来相似的区域，并为所有这些区域存储一个副本;当文件被解压缩时，它重复地使用该副本来重构图像。  

It turned out that the photocopier had judged the labels specifying the area of the rooms to be similar enough that it needed to store only one of them—14.13—and it reused that one for all three rooms when printing the floor plan.  

结果是，复印机判断出标明房间面积的标签非常相似，只需要存储其中一个--14.13--在打印平面图时，它对所有三个房间都重复使用了那个标签。

The fact that Xerox photocopiers use a lossy compression format instead of a lossless one isn’t, in itself, a problem. The problem is that the photocopiers were degrading the image in a subtle way, in which the compression artifacts weren’t immediately recognizable.  

施乐复印机使用有损压缩格式而不是无损压缩格式这一事实本身并不是问题。问题是，复印机以一种微妙的方式降低了图像质量，压缩后的伪像无法立即识别。  

If the photocopier simply produced blurry printouts, everyone would know that they weren’t accurate reproductions of the originals.  

如果复印机只是打印出模糊的输出，每个人都会知道它们不是原件的准确复制品。  

What led to problems was the fact that the photocopier was producing numbers that were readable but incorrect; it made the copies seem accurate when they weren’t. (In 2014, Xerox released a patch to correct this issue.)  

导致问题的原因是复印机产生的数字可读但不正确;它让复印件看起来很准确其实不然。(In 2014年，Xerox发布了一个修补程序来纠正此问题。）

I think that this incident with the Xerox photocopier is worth bearing in mind today, as we consider _OpenAI_’s [_ChatGPT_ and other similar programs](https://www.newyorker.com/tech/annals-of-technology/whispers-of-ais-modular-future), which A.I. researchers call large language models. The resemblance between a photocopier and a large language model might not be immediately apparent—but consider the following scenario. Imagine that you’re about to lose your access to the Internet forever.  

我认为，施乐复印机的这一事件今天值得我们铭记，因为我们考虑_OpenAI_的_ChatGPT_和其他类似的程序，其中A.I.研究人员称之为大型语言模型。复印机和大型语言模型之间的相似之处可能不会立即显现出来，但请考虑以下场景。想象一下，你将永远无法访问互联网。  

In preparation, you plan to create a compressed copy of all the text on the Web, so that you can store it on a private server.  

在准备过程中，您计划创建Web上所有文本的压缩副本，以便可以将其存储在专用服务器上。  

Unfortunately, your private server has only one per cent of the space needed; you can’t use a lossless compression algorithm if you want everything to fit.  

不幸的是，您的私人服务器只有所需空间的百分之一;如果你想让所有内容都适合，就不能使用无损压缩算法。  

Instead, you write a lossy algorithm that identifies statistical regularities in the text and stores them in a specialized file format.  

相反，您可以编写一个有损算法来识别文本中的统计规律，并将其存储在一个专门的文件格式中。  

Because you have virtually unlimited computational power to throw at this task, your algorithm can identify extraordinarily nuanced statistical regularities, and this allows you to achieve the desired compression ratio of a hundred to one.  

因为你有几乎无限的计算能力来完成这项任务，你的算法可以识别出异常微妙的统计规律，这使你能够达到100比1的压缩比。

Now, losing your Internet access isn’t quite so terrible; you’ve got all the information on the Web stored on your server.  

现在，失去互联网接入并不是那么可怕;你已经把网上的所有信息都存储在你的服务器上了。  

The only catch is that, because the text has been so highly compressed, you can’t look for information by searching for an exact quote; you’ll never get an exact match, because the words aren’t what’s being stored.  

唯一的问题是，因为文本已经被高度压缩，你不能通过搜索精确的引用来寻找信息;你永远不会得到一个完全匹配的单词，因为单词不是被存储的。  

To solve this problem, you create an interface that accepts queries in the form of questions and responds with answers that convey the gist of what you have on your server.  

要解决这个问题，您需要创建一个接口，该接口以问题的形式接受查询，并以传达服务器上内容的要点的答案进行响应。

What I’ve described sounds a lot like _ChatGPT_, or most any other large language model. Think of _ChatGPT_ as a blurry _JPEG_ of all the text on the Web. It retains much of the information on the Web, in the same way that a _JPEG_ retains much of the information of a higher-resolution image, but, if you’re looking for an exact sequence of bits, you won’t find it; all you will ever get is an approximation. But, because the approximation is presented in the form of grammatical text, which _ChatGPT_ excels at creating, it’s usually acceptable. You’re still looking at a blurry _JPEG_, but the blurriness occurs in a way that doesn’t make the picture as a whole look less sharp.  

我所描述的听起来很像_ChatGPT_，或者大多数其他大型语言模型。可以将_ChatGPT_看作Web上所有文本的模糊jpeg。它保留了网络上的许多信息，就像jpeg保留了高分辨率图像的许多信息一样，但是，如果你要寻找一个精确的比特序列，你就找不到它;你得到的只是一个近似值。但是，因为近似值是以语法文本的形式呈现的，而_ChatGPT_擅长创建语法文本，所以它通常是可以接受的。你仍然在看一个模糊的jpeg，但是模糊发生的方式并没有使图片作为一个整体看起来不那么清晰。

This analogy to lossy compression is not just a way to understand _ChatGPT_’s facility at repackaging information found on the Web by using different words. It’s also a way to understand the “hallucinations,” or nonsensical answers to factual questions, to which large language models such as _ChatGPT_ are all too prone.  

这种对有损压缩的类比不仅仅是理解_ChatGPT_通过使用不同的单词重新打包Web上找到的信息的工具的一种方式。这也是一种理解"幻觉"或对事实问题的无意义回答的方法，_ChatGPT_等大型语言模型都很容易出现这种情况。  

These hallucinations are compression artifacts, but—like the incorrect labels generated by the Xerox photocopier—they are plausible enough that identifying them requires comparing them against the originals, which in this case means either the Web or our own knowledge of the world.  

这些幻觉是压缩的产物，但就像施乐复印机产生的错误标签一样，它们的可信度很高，识别它们需要将它们与原件进行比较，在这种情况下，原件意味着网络或我们自己对世界的知识。  

When we think about them this way, such hallucinations are anything but surprising; if a compression algorithm is designed to reconstruct text after ninety-nine per cent of the original has been discarded, we should expect that significant portions of what it generates will be entirely fabricated.  

当我们以这种方式思考它们时，这样的幻觉一点也不令人惊讶;如果压缩算法被设计成在原始文本的99%被丢弃之后重构文本，则我们应当预期它所生成的文本的相当大的部分将完全是伪造的。

This analogy makes even more sense when we remember that a common technique used by lossy compression algorithms is interpolation—that is, estimating what’s missing by looking at what’s on either side of the gap.  

当我们记得有损压缩算法使用的一种常用技术是插值时，这种类比就更有意义了，也就是说，通过查看差距两侧的内容来估计丢失的内容。  

When an image program is displaying a photo and has to reconstruct a pixel that was lost during the compression process, it looks at the nearby pixels and calculates the average. This is what _ChatGPT_ does when it’s prompted to describe, say, losing a sock in the dryer using the style of the Declaration of Independence: it is taking two points in “lexical space” and generating the text that would occupy the location between them.  

当图像程序显示照片并且必须重建在压缩过程中丢失的像素时，它会查看附近的像素并计算平均值。这就是_ChatGPT_在被提示描述时所做的事情，比如说，用《独立宣言》的风格描述在烘干机里丢了一只袜子：它在"词汇空间"中取两个点，并生成占据它们之间位置的文本。  

(“When in the Course of human events, it becomes necessary for one to separate his garments from their mates, in order to maintain the cleanliness and order thereof. . . .”) _ChatGPT_ is so good at this form of interpolation that people find it entertaining: they’ve discovered a “blur” tool for paragraphs instead of photos, and are having a blast playing with it.  

（"在人类活动的过程中，一个人有必要把他的衣服和他的同伴分开，以保持衣服的清洁和秩序。。。."）_ChatGPT_非常擅长这种形式的插值，人们觉得它很有趣：他们发现了一个"模糊"工具，可以用来处理段落而不是照片，并且玩得很开心。

Given that large language models like _ChatGPT_ are often extolled as the cutting edge of artificial intelligence, it may sound dismissive—or at least deflating—to describe them as lossy text-compression algorithms.  

考虑到像_ChatGPT_这样的大型语言模型经常被誉为人工智能的前沿，将它们描述为有损文本压缩算法可能听起来令人不屑一顾--或者至少令人泄气。  

I do think that this perspective offers a useful corrective to the tendency to anthropomorphize large language models, but there is another aspect to the compression analogy that is worth considering. Since 2006, an A.I.  

我确实认为这种观点对将大型语言模型拟人化的倾向提供了一种有用的纠正，但是压缩类比还有另一个方面值得考虑。从2006年开始，一个人工智能  

researcher named Marcus Hutter has offered a cash reward—known as the Prize for Compressing Human Knowledge, or the Hutter Prize—to anyone who can losslessly compress a specific one-gigabyte snapshot of [Wikipedia](https://www.newyorker.com/magazine/2022/04/25/wikipedia-in-the-flesh) smaller than the previous prize-winner did. You have probably encountered files compressed using the zip file format.  

一位名叫Marcus Hutter的研究人员向任何能够无损压缩维基百科上一个特定的1G快照，使其比前一位获奖者更小的人提供一个现金奖励--被称为压缩人类知识奖，或Hutter奖。您可能遇到过使用zip文件格式压缩的文件。  

The zip format reduces Hutter’s one-gigabyte file to about three hundred megabytes; the most recent prize-winner has managed to reduce it to a hundred and fifteen megabytes. This isn’t just an exercise in smooshing.  

压缩格式将Hutter的1G文件压缩到大约300M;最近的获奖者已经设法将其减少到115兆字节。这不仅仅是一个练习。  

Hutter believes that better text compression will be instrumental in the creation of human-level artificial intelligence, in part because the greatest degree of compression can be achieved by understanding the text.  

Hutter认为，更好的文本压缩将有助于创造人类级别的人工智能，部分原因是通过理解文本可以实现最大程度的压缩。

To grasp the proposed relationship between compression and understanding, imagine that you have a text file containing a million examples of addition, subtraction, multiplication, and division.  

为了理解压缩和理解之间的关系，假设你有一个文本文件，里面包含了一百万个加、减、乘、除的例子。  

Although any compression algorithm could reduce the size of this file, the way to achieve the greatest compression ratio would probably be to derive the principles of arithmetic and then write the code for a calculator program.  

尽管任何压缩算法都可以减小该文件的大小，但实现最大压缩比的方法可能是推导算术原理，然后编写计算器程序的代码。  

Using a calculator, you could perfectly reconstruct not just the million examples in the file but any other example of arithmetic that you might encounter in the future. The same logic applies to the problem of compressing a slice of Wikipedia.  

使用计算器，你不仅可以完美地重构文件中的数百万个例子，还可以重构你将来可能遇到的任何其他算术例子。同样的逻辑也适用于压缩维基百科切片的问题。  

If a compression program knows that force equals mass times acceleration, it can discard a lot of words when compressing the pages about physics because it will be able to reconstruct them.  

如果一个压缩程序知道力等于质量乘以加速度，那么在压缩物理页面时，它可以丢弃很多单词，因为它将能够重建它们。  

Likewise, the more the program knows about supply and demand, the more words it can discard when compressing the pages about economics, and so forth.  

同样，程序对供给和需求了解得越多，在压缩有关经济学等内容的页面时，可以丢弃的单词就越多。

Large language models identify statistical regularities in text. Any analysis of the text of the Web will reveal that phrases like “supply is low” often appear in close proximity to phrases like “prices rise.  

大型语言模型识别文本中的统计规律。对网络文本的任何分析都会发现，像"供应不足"这样的短语经常出现在"价格上涨"这样的短语附近。  

” A chatbot that incorporates this correlation might, when asked a question about the effect of supply shortages, respond with an answer about prices increasing.  

"当被问及供应短缺的影响时，一个包含这种相关性的聊天机器人可能会回答价格上涨。  

If a large language model has compiled a vast number of correlations between economic terms—so many that it can offer plausible responses to a wide variety of questions—should we say that it actually understands economic theory? Models like _ChatGPT_ aren’t eligible for the Hutter Prize for a variety of reasons, one of which is that they don’t reconstruct the original text precisely—i.e., they don’t perform lossless compression.  

如果一个大型的语言模型已经汇集了大量经济术语之间的相关性如此之多以至于它可以为各种各样的问题提供合理的答案我们是否应该说它实际上理解了经济理论？像_ChatGPT_这样的模型没有资格获得Hutter奖，原因有很多，其中之一是它们不能精确地重构原始文本，即：它们不执行无损压缩。  

But is it possible that their lossy compression nonetheless indicates real understanding of the sort that A.I. researchers are interested in?  

但是，有没有可能他们的有损压缩仍然表明真正的理解排序人工智能。研究人员感兴趣的

Let’s go back to the example of arithmetic. If you ask GPT-3 (the large-language model [that _ChatGPT_ was built from](https://www.newyorker.com/magazine/2019/10/14/can-a-machine-learn-to-write-for-the-new-yorker)) to add or subtract a pair of numbers, it almost always responds with the correct answer when the numbers have only two digits. But its accuracy worsens significantly with larger numbers, falling to ten per cent when the numbers have five digits.  

让我们回到算术的例子。如果您要求GPT-3（构建_ChatGPT_的大型语言模型）对一对数字进行加减运算，当数字只有两位数时，它几乎总是会给出正确的答案。但它的准确性随着数字的增大而显著恶化，当数字为五位数时，准确性下降到10%。  

Most of the correct answers that GPT-3 gives are not found on the Web—there aren’t many Web pages that contain the text “245 + 821,” for example—so it’s not engaged in simple memorization.  

GPT-3给出的大多数正确答案在Web上都找不到, -例如，包含文本“245 + 821”的Web页面并不多, -因此，它并不是在进行简单的记忆。  

But, despite ingesting a vast amount of information, it hasn’t been able to derive the principles of arithmetic, either. A close examination of GPT-3’s incorrect answers suggests that it doesn’t carry the “1” when performing arithmetic.  

但是，尽管吸收了大量的信息，它也没有能够推导出算术原理。对GPT-3错误答案的仔细检查表明，它在执行算术运算时没有携带“1”。  

The Web certainly contains explanations of carrying the “1,” but GPT-3 isn’t able to incorporate those explanations. GPT-3’s statistical analysis of examples of arithmetic enables it to produce a superficial approximation of the real thing, but no more than that.  

Web上当然包含了对携带“1”的解释，但是GPT-3不能包含这些解释。GPT-3对算术例子的统计分析使它能够产生真实的事物的表面近似，但仅此而已。

Given GPT-3’s failure at a subject taught in elementary school, how can we explain the fact that it sometimes appears to perform well at writing college-level essays?  

考虑到GPT-3在小学教授的一门课程上的失败，我们如何解释它有时在写大学水平的论文时表现良好的事实呢？  

Even though large language models often hallucinate, when they’re lucid they sound like they actually understand subjects like economic theory. Perhaps arithmetic is a special case, one for which large language models are poorly suited.  

尽管大型语言模型经常会产生幻觉，但当它们清醒时，听起来就像它们实际上理解了经济理论之类的学科。也许算术是一个特例，大型语言模型不太适合。  

Is it possible that, in areas outside addition and subtraction, statistical regularities in text actually _do_ correspond to genuine knowledge of the real world?  

在加减法之外的领域，文本中的统计规律是否真的与真实世界的真实知识相对应？
