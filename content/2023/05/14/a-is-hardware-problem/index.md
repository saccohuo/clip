---
title: "AI 的硬件问题"
date: 2023-05-14T08:25:53+08:00
updated: 2023-05-14T08:25:53+08:00
taxonomies:
  tags: []
extra:
  source: https://asianometry.substack.com/p/ais-hardware-problem
  hostname: asianometry.substack.com
  author: Jon Y
  original_title: "AI's Hardware Problem"
  original_lang: zh
---

Summary: 本文讨论了人工智能硬件的问题，特别是与内存相关的问题。文章介绍了内存墙问题以及研究人员正在寻找解决方案的内存中心范例。此外，文章还提到了人工智能硬件行业正在尽可能快地扩展内存和处理单元性能，但是硬件性能并没有跟上模型增长的速度，尤其是在内存方面。

文章要点:
1. 人工智能硬件行业正在尽可能快地扩展内存和处理单元性能，但是硬件性能并没有跟上模型增长的速度，尤其是在内存方面。
2. 内存墙问题是人工智能硬件的一个限制，即处理单元需要等待内存执行读 / 写操作，从而浪费多个处理周期。
3. 人工智能硬件行业正在研究内存中心范例来解决内存墙问题。
4. 人工智能硬件行业存在实际和技术限制，无法无限制地增加内存。
5. 电力连接的损失也是人工智能硬件的一个限制，会消耗能量。

Keywords: 人工智能硬件、内存墙、内存中心范例、处理单元、电力连接

---

If you want to watch the video first, it is below:  

如果你想先看视频，下面是：

<iframe src="https://www.youtube-nocookie.com/embed/5tmGKTNW8DQ?rel=0&amp;autoplay=0&amp;showinfo=0&amp;enablejsapi=0" loading="lazy" gesture="media" allow="autoplay; fullscreen" allowautoplay="true" allowfullscreen="true" data-immersive-translate-effect="1" data-immersive-translate-block-mark="1" data-immersive-translate-mark="1" width="728" height="409" frameborder="0"></iframe>

_I worked on this video long before ChatGPT blew up the world so it had yet to come to my attention. But since then, AI has become a way bigger deal.  

在 ChatGPT 风靡世界之前很久我就制作了这个视频，所以它还没有引起我的注意。但从那时起，人工智能就成了一件大事。_

_I have been thinking of a good follow up to it. Got any suggestions? Reply to this email or shoot me an email at jon@asianometry.com  

我一直在考虑对它进行很好的跟进。有什么建议吗？回复此电子邮件或发送电子邮件至 jon@asianometry.com_

_Recently, I was listening to a podcast interview with OpenAI chief scientist Ilya Sutskever and one of those things that I found interesting was that he doesn’t think that hardware compute is a limitation for AI research.  

He also [touches on the concepts](https://youtu.be/Yf1o0TQzry8?t=1573) mentioned in today’s newsletter, the bottleneck between logic and memory.  

最近，我正在收听 OpenAI 首席科学家 Ilya Sutskever 的播客采访，我发现其中一件有趣的事情是他认为硬件计算不是 AI 研究的限制。他还谈到了今天时事通讯中提到的概念，即逻辑和内存之间的瓶颈。_

<iframe src="https://www.youtube-nocookie.com/embed/Yf1o0TQzry8?start=897&amp;rel=0&amp;autoplay=0&amp;showinfo=0&amp;enablejsapi=0" loading="lazy" gesture="media" allow="autoplay; fullscreen" allowautoplay="true" allowfullscreen="true" data-immersive-translate-effect="1" data-immersive-translate-block-mark="1" data-immersive-translate-mark="1" width="728" height="409" frameborder="0"></iframe>

_There seems to be still a lot of mystery in how AI hardware is built - especially the hardware that goes into data centers.  

I have tried digging to learn it myself too, but it seems most of it is proprietary. It would be nice to do more videos about the AI hardware concept in the coming months.  

人工智能硬件的构建方式似乎仍有很多谜团——尤其是进入数据中心的硬件。我自己也尝试过挖掘来学习它，但似乎大部分都是专有的。在接下来的几个月里制作更多关于 AI 硬件概念的视频会很好。_

Since the deep learning explosion started in 2012, the industry's biggest models have grown hundreds of thousands of times.  

自 2012 年深度学习爆发以来，业界最大的模型已经增长了数十万倍。

Today, OpenAI's Dall-E 2 has 3.5 billion parameters. Google's Imagen has 4.6 billion and GPT-3 has 175 billion parameters.  

如今，OpenAI 的 Dall-E 2 拥有 35 亿个参数。 Google 的 Imagen 有 46 亿个，GPT-3 有 1750 亿个参数。

Increasingly larger models are ahead. Google recently pre-trained a model with 1 trillion parameters.  

越来越大的模型领先。谷歌最近预训练了一个具有 1 万亿个参数的模型。

These increasingly large models strain the ability of our hardware to accommodate them. And many of these limitations tie back to memory and how we use it.  

这些越来越大的模型使我们的硬件无法容纳它们。许多这些限制都与内存以及我们如何使用它有关。

In this video, we are going to look at deep learning's memory wall problem. And some of the memory-centric paradigms researchers are looking at to solve it.  

在本视频中，我们将探讨深度学习的记忆墙问题。研究人员正在研究一些以内存为中心的范例来解决它。

Virtually every modern computer runs what is called a Von Neumann architecture. Meaning that it stores both its instructions and data on the same memory bank.  

实际上，每台现代计算机都运行所谓的冯·诺依曼架构。这意味着它将指令和数据存储在同一个内存库中。

At its heart are your processing units - a CPU or a GPU. Those processing units access memory to execute its instructions and process its data.  

它的核心是您的处理单元——CPU 或 GPU。这些处理单元访问内存以执行其指令并处理其数据。

The Von Neumann architecture has been really good for us. It helped make software as powerful as it is today. But it works nothing like a real human brain.  

冯诺依曼架构对我们来说真的很好。它帮助使软件像今天一样强大。但它的工作方式与真正的人脑完全不同。

The brain's compute ability is relatively low precision, but it tightly integrates that compute with memory and input/output communication.  

大脑的计算能力精度相对较低，但它将计算与记忆和输入/输出通信紧密结合在一起。

Computers on the other hand run on high precision - 32 or 64 bit floating point arithmetic for instance - but separates that compute from memory and communication.  

另一方面，计算机以高精度运行——例如 32 位或 64 位浮点运算——但将计算与内存和通信分开。  

This separation has consequences, especially for memory.  

这种分离会产生影响，尤其是对记忆而言。

The AI hardware industry is scaling up memory and processing unit performance as fast as they can. Nvidia's V100 GPU released in 2017 had a 32 GB offering.  

AI 硬件行业正在尽可能快地扩展内存和处理单元性能。 Nvidia 于 2017 年发布的 V100 GPU 提供 32 GB 容量。

Today, the top-of-the-line Nvidia data center GPUs A100 and H100 sport 80GB of memory.  

如今，顶级的 Nvidia 数据中心 GPU A100 和 H100 拥有 80GB 内存。

Despite this bulking-up, hardware performance is not keeping up with how fast these models are growing - especially when it comes to memory.  

尽管有这种膨胀，但硬件性能并没有跟上这些模型的增长速度——尤其是在内存方面。

Memory allocations for leading edge models can easily exceed hundreds of gigabytes.  

前沿模型的内存分配很容易超过数百 GB。  

Even with the latest parallelization techniques, a trillion-parameter model is estimated to require 320 A100 GPUs, each with 80 GB of memory.  

即使使用最新的并行化技术，一个万亿参数的模型估计也需要 320 个 A100 GPU，每个 GPU 具有 80 GB 的内存。

These differences in processing and capacity mean that a processing unit wastes multiple processing cycles waiting not only for all the data to travel in and out of the memory, but also for the memory to perform its read/write operation.  

这些处理和容量上的差异意味着处理单元浪费多个处理周期，不仅要等待所有数据进出内存，还要等待内存执行其读/写操作。

This limitation is known as the Memory Wall, or a Memory Capacity Bottleneck.  

此限制称为内存墙或内存容量瓶颈。

Alright then, the obvious solution would be then to add more memory to our GPUs right? What is stopping us from doing that?  

那么好吧，显而易见的解决方案是为我们的 GPU 添加更多内存，对吧？是什么阻止我们这样做？

There are practical and technology limits to how much extra memory you can add on. Not to mention the issues of connections and wiring.  

您可以添加多少额外内存存在实际和技术限制。更不用说连接和布线的问题了。  

Just think about how widening a highway does not much help with traffic.  

试想一下，加宽高速公路对交通没有太大帮助。

Additionally, there are very significant energy limitations associated with shuttling data between the chip and the memory. These electric connections have losses which cost energy.  

此外，芯片和内存之间的数据传输存在非常显着的能量限制。这些电连接具有消耗能量的损耗。  

I mentioned this in previous videos. Accessing memory off-chip uses 200 times more energy than a floating point operation.  

我在之前的视频中提到过这一点。访问片外存储器所消耗的能量是浮点运算的 200 倍。

80% of the Google TPU's energy usage is from its electrical connections rather than its logic computational units.  

谷歌 TPU 80% 的能源使用来自其电气连接，而不是其逻辑计算单元。

In some recent GPU and CPU systems, DRAM by itself accounts for 40% of the total system power.  

在最近的一些 GPU 和 CPU 系统中，DRAM 本身就占系统总功率的 40%。

Energy makes up 40% of a data center's operating costs. So for this reason, storage and memory has come to be a significant factor in the data center's ongoing profitability.  

能源占数据中心运营成本的 40%。因此，出于这个原因，存储和内存已成为数据中心持续盈利能力的重要因素。

In addition to the significant operating costs of the energy are the up-front capital costs of purchasing the AI hardware itself.  

除了巨大的能源运营成本外，还有购买 AI 硬件本身的前期资本成本。

As I mentioned earlier, a possible trillion-parameter model would need 320 A100 GPUs, each with 80 GB of memory.  

正如我之前提到的，一个可能的万亿参数模型将需要 320 个 A100 GPU，每个 GPU 具有 80 GB 的内存。

A100s cost $32,000 each at MSRP, so that's a clean $10 million. A hundred trillion parameter model might require over 6,000 such GPUs.  

A100 的建议零售价为每台 32,000 美元，因此这是一个干净的 1000 万美元。一百万亿个参数模型可能需要超过 6,000 个这样的 GPU。

That is just the cost of purchasing the hardware and does not even count the aforementioned energy costs of using these things to run inference on them, which is where 90% of a model's total costs are.  

这只是购买硬件的成本，甚至不包括上述使用这些东西对其进行推理的能源成本，这是模型总成本的 90%。  

It risks restricting the benefits of advanced AI only to the Uber rich tech giants or governments.  

它有可能将高级人工智能的好处仅限于优步富有的科技巨头或政府。

Much of these shortcomings are tied to historical and technological limits.  

这些缺点中的大部分都与历史和技术限制有关。  

In the 1960s and 70s, the industry adopted Dynamic Random Access Memory to form the basis of our computers.  

在 1960 年代和 70 年代，业界采用动态随机存取存储器来构成我们计算机的基础。

This adoption was largely made for technological and economic reasons. DRAM memories had relatively low latency and were cheap to manufacture in bulk.  

这种采用主要是出于技术和经济原因。 DRAM 内存具有相对较低的延迟，并且批量生产成本低廉。

This worked fine for a while. As late as 1995, the memory industry was valued at $37 billion, with microprocessors at $20 billion.  

这有一段时间效果很好。迟至 1995 年，存储器行业的价值为 370 亿美元，微处理器为 200 亿美元。

But after 1980, compute scaling far outpaced memory scaling.  

但在 1980 年之后，计算扩展远远超过了内存扩展。  

This is because - generally speaking - the CPU or GPU industries have had just one metric to optimize towards: Transistor density.  

这是因为 - 一般来说 - CPU 或 GPU 行业只有一个指标可以优化：晶体管密度。

The memory industry on the other hand not only has to scale DRAM capacity but also bandwidth and latency at the same time. Something has to give and usually that has been latency.  

另一方面，内存行业不仅需要扩展 DRAM 容量，还需要同时扩展带宽和延迟。必须付出一些代价，通常是潜伏期。

Over the past twenty years, memory capacity has improved 128 times and bandwidth 20 times.  

在过去的二十年里，内存容量提高了 128 倍，带宽提高了 20 倍。

Latency however has improved by just 30%.  

然而，延迟仅改善了 30%。

Secondly, the memory industry realized that shrinking DRAM cells beyond a certain size gave you worse performance.  

其次，内存行业意识到将 DRAM 单元缩小到一定尺寸以上会使性能变差。  

Less reliability, less secure, worse latency, energy inefficiency, and so on.  

可靠性较低、安全性较低、延迟较差、能源效率低下等。

Here's why. A DRAM cell stores 1 bit of data in the form of a charge within a capacitor - a capacitor being a device that stores electrical energy within a field.  

这就是为什么。 DRAM 单元以电容器内电荷的形式存储 1 位数据 - 电容器是一种在场内存储电能的设备。  

That bit is accessed using an access transistor.  

使用访问晶体管访问该位。

As you scale the cell down to nanoscale sizes, that capacitor and its access transistor get leakier and more vulnerable to outside electrical noise.  

当您将单元缩小到纳米级尺寸时，该电容器及其存取晶体管会变得更加泄漏，并且更容易受到外部电噪声的影响。  

It also opens up new security vulnerabilities.  

它还打开了新的安全漏洞。

These technical limitations and problems are fundamental to how the hardware works. Which makes them extremely difficult to engineer our way around.  

这些技术限制和问题是硬件工作方式的基础。这使得他们极难设计我们的解决方案。  

The industry is going to grind out small solutions, but those will be small.  

该行业将研究出小型解决方案，但这些解决方案将很小。

So the problem also opens the door to brand new, radical ideas that might give us a possible 10x improvement over the current paradigm.  

所以这个问题也为全新的、激进的想法打开了大门，这些想法可能会让我们比当前范式有 10 倍的改进。

In a previous video, I talked about the silicon photonic AI accelerator, where we try to use light's properties to make data transfer more energy efficient.  

在之前的视频中，我谈到了硅光子 AI 加速器，我们尝试利用光的特性使数据传输更加节能。

Alongside that, we have another idea.  

除此之外，我们还有另一个想法。  

Let's alleviate or even possibly eliminate the Von Neumann bottleneck and memory wall problems by making the memory do the computations themselves.  

让我们通过让内存自己进行计算来缓解甚至可能消除冯诺依曼瓶颈和内存墙问题。

Compute in Memory refers to a random access memory with processing elements integrated together - the two might be very near each other or even be integrated onto the same die.  

内存中计算是指将处理元件集成在一起的随机存取存储器——两者可能彼此非常接近，甚至集成到同一芯片上。

I have seen the idea be called other things throughout the years.  

这些年来，我看到这个想法被称为其他东西。  

Processing in Memory, Computational-RAM, Near-Data-Computing, Memory-centric Computing, In-Memory Computation, and so on.  

内存处理、计算 RAM、近数据计算、以内存为中心的计算、内存计算等。

I am aware that there are differences between these usages. But those differences are very subtle. I am generally stick to saying Compute-in-Memory.  

我知道这些用法之间存在差异。但这些差异非常微妙。我通常坚持说内存中计算。

The name has also been used to refer to concepts expanding on the SRAM idea. SRAM is often used for the memory cache that sits on-chip with the CPU.  

该名称还被用来指代在 SRAM 思想基础上扩展的概念。 SRAM 通常用于与 CPU 一起位于芯片上的内存缓存。  

But what we are more referring to here is bringing processing and compute ability to the computer main memory itself.  

但我们这里更多的是指给计算机主存本身带来处理和计算能力。

The idea is well suited for deep learning. If you recall, running a neural network model is about calculating these massive matrices.  

这个想法非常适合深度学习。如果您还记得，运行神经网络模型就是计算这些庞大的矩阵。  

The Google TPU had lots of circuits for running Multiply and Accumulate or MAC operations.  

谷歌 TPU 有很多用于运行乘法和累加或 MAC 运算的电路。

The actual arithmetic is relatively simple. The problem is that there is so much of it needs to be done.  

实际的算法相对简单。问题是需要做的事情太多了。  

So in an ideal case, a Compute-in-Memory chip can execute MAC operations right inside the memory chip.  

因此在理想情况下，内存计算芯片可以在内存芯片内部执行 MAC 操作。

This is especially helpful for running inference on the edge outside the data center. These use cases have energy, size, or heat restrictions.  

这对于在数据中心外的边缘运行推理特别有用。这些用例具有能量、尺寸或热量限制。  

Being able to cut up to 80% of a neural network's energy usage is a game changer.  

能够削减高达 80% 的神经网络能源使用是一个游戏规则的改变者。

The idea is decades old - dating back to the 1960s. Professor Harold Stone of Stanford University first notably explored the idea of "Logic in Memory".  

这个想法已有数十年历史 - 可以追溯到 1960 年代。斯坦福大学的哈罗德·斯通教授首先对“记忆中的逻辑”这一概念进行了著名的探索。

Stone noted that the number of transistors in a microprocessor was growing very fast, but the processor's ability to communicate with its memory was limited by the number of pins.  

Stone 指出，微处理器中的晶体管数量增长非常快，但处理器与其内存通信的能力受到引脚数量的限制。  

So he presented the idea of moving part of the computation into memory caches.  

因此，他提出了将部分计算移动到内存缓存中的想法。

The 1990s saw further explorations of the idea. In 1995, Terasys produced what we would probably call the first processor-in-memory chip.  

1990 年代对该想法进行了进一步探索。 1995 年，Terasys 生产了我们可能称之为第一款内存处理器芯片。  

It was a standard 4-bit memory with an integrated single bit logical unit.  

它是一个标准的 4 位内存，带有一个集成的单位逻辑单元。

This arithmetic logical unit can bring in data, apply some simple logic to it as dictated from a program, and then write it back to memory.  

这个算术逻辑单元可以引入数据，按照程序的指示对其应用一些简单的逻辑，然后将其写回内存。

And then in 1997, various professors at UC Berkeley including Professor David Patterson - the inventor of RISC - created the IRAM project with the goal of putting a microprocessor and DRAM on the same chip.  

然后在 1997 年，加州大学伯克利分校的多位教授，包括 RISC 的发明者 David Patterson 教授，创建了 IRAM 项目，目标是将微处理器和 DRAM 放在同一芯片上。

Several other such proposals followed throughout the 1990s. But none of these ever caught on for a number of practical reasons.  

在整个 1990 年代，其他几项此类提议也随之而来。但由于一些实际原因，这些都没有流行起来。

First, memory and logic are hard to manufacture together. Their fabrication have sort of opposing goals. Again, logic transistors are all about speed and performance.  

首先，内存和逻辑很难一起制造。他们的编造有一些相反的目标。同样，逻辑晶体管都是关于速度和性能的。  

But Memory transistors have to be about high density, low cost, and low leakage all at once.  

但是存储晶体管必须同时兼顾高密度、低成本和低泄漏。

It is hard to build a logic process with a DRAM process, and vice versa. DRAM designs are very regular, with lots of parallel wires.  

很难用 DRAM 工艺构建逻辑工艺，反之亦然。 DRAM 设计非常规则，有很多平行线。  

Logic designs on the other hand have much more complexity.  

另一方面，逻辑设计要复杂得多。

Circuit elements in a chip have connections - referred to as "metal layers".  

芯片中的电路元件具有连接 - 称为“金属层”。  

Having more metal layers allows for more complexity, but at the cost of current leakage and worse reliability.  

拥有更多的金属层会带来更多的复杂性，但代价是电流泄漏和更差的可靠性。

Contemporary DRAM processes use 3 to 4 metal layers. Contemporary logic processes use anywhere from 7 to 12 and even more metal layers.  

现代 DRAM 工艺使用 3 到 4 个金属层。当代逻辑过程使用 7 到 12 甚至更多的金属层。

So it is estimated that if you tried to make logic circuits with a DRAM process, then the logic circuits would be 80% bigger and perform 22% worse.  

所以据估计，如果你试图用 DRAM 工艺制作逻辑电路，那么逻辑电路会大 80%，性能会差 22%。

And if you were to try to make DRAM cells with a logic process then you are essentially making Embedded DRAM or eDRAM.  

如果你试图用逻辑过程制造 DRAM 单元，那么你实际上是在制造嵌入式 DRAM 或 eDRAM。  

The cells use significantly more power, take up to 10x more space, and are less reliable.  

这些电池消耗的功率明显增加，占用的空间增加了 10 倍，而且可靠性较低。

The industry has since considered these manufacturing shortcomings and have come up with a variety of workarounds.  

此后，该行业考虑了这些制造缺陷，并提出了各种解决方法。  

Many proposals of Compute-in-Memory are on three levels - the Device, Circuit, and System.  

内存计算的许多提议都在三个层面上——设备、电路和系统。

The Device level leans on new types of memory hardware other than the conventional DRAM and SRAM memories. Notable examples include Resistive Random Access Memory or ReRAM or RRAM;  

设备级别依赖于新型内存硬件，而不是传统的 DRAM 和 SRAM 内存。著名的例子包括电阻式随机存取存储器或 ReRAM 或 RRAM；

And spin-transfer torque magnetoresistive random access memory or STT-MRAM.  

以及自旋转移力矩磁阻随机存取存储器或STT-MRAM。

ReRAM is one of the more promising emerging memory technologies.  

ReRAM 是比较有前途的新兴内存技术之一。

Like I mentioned earlier, conventional RAM memories store information using a charge stored within a capacitor.  

正如我之前提到的，传统的 RAM 存储器使用存储在电容器中的电荷来存储信息。

ReRAM instead stores information by changing the electrical resistance of a certain material - referred to as a resistor - switching between a high and low resistance state.  

ReRAM 而是通过改变某种材料（称为电阻器）的电阻来存储信息，这种材料在高阻状态和低阻状态之间切换。  

This structure allows ReRAM to compute logical functions directly within the memory cells. Please Don't ask me to try to explain it any further than that.  

这种结构允许 ReRAM 直接在存储单元内计算逻辑函数。请不要让我尝试解释更多。

ReRAM is probably the emerging memory technology that is the closest to commercialization due to it being compatible with silicon CMOS.  

ReRAM 可能是最接近商业化的新兴内存技术，因为它与硅 CMOS 兼容。  

However there remain substantial hurdles to overcome before we see products arrive on shelves.  

然而，在我们看到产品上架之前，仍有许多障碍需要克服。

The Circuit level is where we modify peripheral circuits to do the calculations right inside the SRAM or DRAM memory arrays themselves.  

电路级别是我们修改外围电路以在 SRAM 或 DRAM 内存阵列本身内部进行计算的地方。

The phrase I see a lot is "in situ" computing. "In situ" meaning "locally" or "on site".  

我经常看到的短语是“原位”计算。 “In situ”意为“本地”或“现场”。

These are particularly clever. But they also require an intimate knowledge of how memory works, and still can be difficult to understand.  

这些特别聪明。但它们也需要对记忆如何运作有深入的了解，而且仍然很难理解。

One prominent example of this is Ambit, an in-memory accelerator proposed by people from Microsoft, Nvidia, Intel, ETH Zurich, and Carnegie Mellon.  

一个突出的例子是 Ambit，这是一种内存加速器，由 Microsoft、Nvidia、Intel、ETH Zurich 和 Carnegie Mellon 的人们提出。

A DRAM memory contains subarrays with many rows of DRAM cells.  

DRAM 存储器包含具有多行 DRAM 单元的子阵列。

In normal use, the memory activates one row at a time.  

在正常使用中，内存一次激活一行。

This system activates three rows at a time in order to implement an AND/OR logic function. Two rows for the inputs, and one for the output.  

该系统一次激活三行以实现 AND/OR 逻辑功能。两行用于输入，一行用于输出。

The concept is logically attractive. You can utilize the memory's internal bandwidth to do all the calculations.  

这个概念在逻辑上很有吸引力。您可以利用内存的内部带宽来进行所有计算。

However, there are significant concerns. Ambit can perform basic AND, OR, and NOT logic operations. But it takes multiple cycles.  

但是，存在重大问题。 Ambit 可以执行基本的 AND、OR 和 NOT 逻辑运算。但是需要多次循环。  

Furthermore, more complex logic implementations like XNOR remain challenging to utilize.  

此外，XNOR 等更复杂的逻辑实现仍然难以使用。

So far, the big downside with these two compute-in-memory approaches is that their performance still falls short of what can be achieved with current Von Neumann, GPU/ASIC-centric systems.  

到目前为止，这两种内存计算方法的最大缺点是它们的性能仍然达不到当前以冯诺依曼 GPU/ASIC 为中心的系统所能达到的水平。

In other words, they suffer the same drawbacks people saw in the 1990s. Putting memory and logic together still makes a "Jack of all trades, master of none" situation.  

换句话说，他们遭受了人们在 1990 年代看到的相同缺点。将内存和逻辑放在一起仍然会造成“万事通，无人能及”的局面。

So the middle ground that the industry seems to be moving towards is implementing compute-in-memory at a system level.  

因此，该行业似乎正在走向的中间立场是在系统级别实施内存计算。  

This is where we integrate together discrete processing units and memory at a very close level.  

这就是我们在非常接近的水平上将离散的处理单元和内存集成在一起的地方。

This is enabled thanks to new packaging technologies like 2.5D or 3D memory die stacking - where we stack a bunch of DRAM memory dies on top of a CPU die.  

这要归功于新的封装技术，如 2.5D 或 3D 内存芯片堆叠——我们将一堆 DRAM 内存芯片堆叠在 CPU 芯片之上。

The memories are then connected to the CPU using thousands of channels called Through-Silicon Vias or TSVs. This gives you immense amounts of internal bandwidth.  

然后使用数千个称为硅通孔或 TSV 的通道将存储器连接到 CPU。这为您提供了巨大的内部带宽。

AMD is working on something kind of like this with what they call 3D V-Cache - which is based on a TSMC 3D stacking packaging technology.  

AMD 正在研究类似的东西，他们称之为 3D V-Cache——它基于 TSMC 3D 堆叠封装技术。  

They used it to add more memory cache to their processor chips.  

他们用它来为他们的处理器芯片添加更多的内存缓存。

There is a future where we can use similarly advanced packaging technologies to add hundreds of gigabytes of memory to an AI ASIC.  

未来我们可以使用类似的先进封装技术为 AI ASIC 添加数百 GB 的内存。  

This lets us integrate together world class memory and logic dies closer than ever before without needing to place them on the same die.  

这使我们能够比以往更紧密地将世界一流的内存和逻辑芯片集成在一起，而无需将它们放在同一个芯片上。

Ideas in the laboratory are cheap. What is harder is to execute on those ideas in a way that performs well enough to replace what is already out there on the market.  

实验室里的想法很便宜。更难的是以一种足以取代市场上现有产品的方式执行这些想法。

And the fact is that the current Nvidia A100 and H100 AI GPUs are a very formidable competitor.  

事实上，当前的 Nvidia A100 和 H100 AI GPU 是一个非常强大的竞争对手。

But with leading edge semiconductor technologies slowing down the way they are, we need new ways to leapfrog towards more powerful and robust hardware for running AI.  

但随着前沿半导体技术的发展速度放缓，我们需要新的方法来跨越到更强大和更强大的硬件来运行 AI。

Generally speaking, bigger models perform better. Today's best performing Natural Language Processing and Computer Vision models are great. But they still have ways to go.  

一般来说，更大的模型表现更好。当今性能最好的自然语言处理和计算机视觉模型非常棒。但他们还有路要走。  

Which means they might have to get bigger so to get better.  

这意味着他们可能必须变得更大才能变得更好。

But unless we develop new systems and hardware that can overcome these aforementioned limits, it seems that deep learning might fall short of fulfilling its great expectations.  

但除非我们开发出能够克服上述这些限制的新系统和硬件，否则深度学习似乎无法实现它的远大期望。
