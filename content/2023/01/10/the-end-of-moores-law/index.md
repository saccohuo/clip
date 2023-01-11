---
title: "摩尔定律的终结？"
date: 2023-01-10T07:59:49+08:00
updated: 2023-01-10T07:59:49+08:00
taxonomies:
  tags: []
extra:
  source: https://every.to/p/the-end-of-moore-s-law
  hostname: every.to
  author: by Anna-Sofia Lesiv 安娜-索菲亚·莱西夫
  original_title: "The End of Moore’s Law?"
  original_lang: en
---

This phenomenon is responsible for creating the most valuable companies on Earth while completely redefining humanity's relationship with technology. So it’s particularly startling that all that is now in the past.

这种现象造就了地球上最有价值的公司，同时彻底重新定义了人类与技术的关系。因此，特别令人吃惊的是，现在的一切都已成为过去。

“Moore’s Law is dead,” [pronounced](https://www.digitaltrends.com/computing/nvidia-says-falling-gpu-prices-are-over/) Nvidia’s CEO Jensen Huang in September 2022, before adding, “The idea that the chip is going to go down in price is a story of the past.”

“摩尔定律已死，”Nvidia 首席执行官黄仁勋在 2022 年 9 月宣布，然后补充说，“芯片价格将下降的想法已成为过去。”

Today’s chips come packed with billions of transistors, capable of executing billions of instructions per second. The smallest transistors on the market are now hitting the 3 nanometer mark, a length equivalent to 15 Silicon atoms. But getting ever smaller presents tremendous financial, let alone physical, challenges, and many are bracing themselves for a world where achieving our digital dreams is only going to get more expensive from here.

今天的芯片配备了数十亿个晶体管，每秒能够执行数十亿条指令。市场上最小的晶体管现在达到了 3 纳米大关，相当于 15 个硅原子的长度。但是，越来越小会带来巨大的财务挑战，更不用说体力挑战了，许多人都在为实现我们的数字梦想只会付出更多代价的世界做好准备。

Every major company that relies on computing is exploring ways to approach this new normal. Some are rethinking the designs of chips in their devices while others are beefing up the number of silicon experts they have in house. We can trace the evolution of chip economics and design to better understand how we got here, and explore what the future might look like as a new chapter opens up in the world of hardware.

每个依赖计算的大公司都在探索应对这一新常态的方法。一些公司正在重新考虑其设备中的芯片设计，而另一些公司则在增加内部硅专家的数量。我们可以追溯芯片经济学和设计的演变，以更好地了解我们是如何走到这一步的，并探索随着硬件世界新篇章的开启，未来会是什么样子。

## The flow of electricity 电流的流动

Electricity plays a crucial role in computers: it represents the physical form of information. So to manipulate information, we first needed to figure out how to manipulate the flow of electricity.

电在计算机中起着至关重要的作用：它代表信息的物理形式。所以要操纵信息，我们首先需要弄清楚如何操纵电流。

In the early twentieth century, one of the biggest puzzles in electrical engineering was finding a mechanism that could switch electrical signals on and off—using electrical signals themselves. In 1911, Palo Alto native Lee DeForest figured out one of the first ways of doing it when he discovered the vacuum tube.

二十世纪初，电气工程中最大的难题之一是找到一种可以使用电信号本身打开和关闭电信号的机制。 1911 年，帕洛阿尔托本地人 Lee DeForest 在发现真空管时想出了最早的方法之一。

A vacuum tube is a glass vial with two components: a cathode at one end, which heats up and produces a stream of electrons, and an anode at the other end. By regulating whether or not a voltage is applied to the anode, you can control whether electrons will be permitted to pass across the vacuum from the cathode end to the anode end, powering a circuit.

真空管是一个由两部分组成的玻璃瓶：一端是阴极，它加热并产生电子流，另一端是阳极。通过调节是否向阳极施加电压，您可以控制是否允许电子从阴极端穿过真空到达阳极端，从而为电路供电。

These circuits, made by soldering together vacuum tubes, copper wires, and other rudimentary electrical components, could be assembled to perform basic logic functions. If you put enough logic functions together, you could make a primitive calculator—one that could do basic addition, subtraction, division, and multiplication. The University of Pennsylvania's ENIAC, built in 1946, was one of the first attempts at a large-scale electrical computer that could perform these calculations. But it was composed of 18,000 vacuum tubes and miles of copper wire, and required 150,000 watts of power to operate. There was a rumor that whenever the ENIAC was switched on, the lights in Philadelphia dimmed.

这些电路通过将真空管、铜线和其他基本电子元件焊接在一起制成，可以组装起来执行基本的逻辑功能。如果你把足够多的逻辑函数放在一起，你就可以制作一个原始的计算器——一个可以进行基本的加法、减法、除法和乘法的计算器。宾夕法尼亚大学的 ENIAC 建于 1946 年，是对可以执行这些计算的大型电子计算机的首次尝试之一。但它由 18,000 个真空管和数英里长的铜线组成，需要 150,000 瓦的功率才能运行。有传言说，每当打开 ENIAC 时，费城的灯光就会变暗。

The vacuum tubes would glow with heat, which required fans to cool them down. The glowing also attracted moths, which would short-circuit the machine, requiring engineers to literally de-bug it.

真空管会因发热而发光，这需要风扇来冷却它们。发光还吸引了飞蛾，这会使机器短路，需要工程师真正调试它。

An improvement on glowing-hot vacuum tubes soon arrived from Bell Labs, where researchers were experimenting with a new class of materials they called semiconductors. Somewhere in between a conductor, like a metal, and an insulator, like glass, semiconductor materials selectively allowed electrical current to flow through them. The trick was to figure out how to make the semiconductors allow current to flow through them when prompted.

贝尔实验室很快对炽热真空管进行了改进，研究人员正在实验室试验一种他们称之为半导体的新型材料。在导体（如金属）和绝缘体（如玻璃）之间的某处，半导体材料有选择地允许电流流过它们。诀窍是弄清楚如何让半导体在提示时允许电流流过它们。

The breakthrough came in 1947 from John Bardeen and Walter Brattain, a duo working under the guidance of William Shockley at Bell Labs. Together, Bardeen and Brattain built the first working prototype of a solid state electrical switch, the transistor. Transistors allowed electricity to flow selectively through solid material, rather than having to detour through fragile and hot glass bulbs. That meant smaller circuits, which could be turned on and off faster and use less energy to do it.

1947 年，约翰·巴丁 (John Bardeen) 和沃尔特·布拉顿 (Walter Brattain) 在贝尔实验室的威廉·肖克利 (William Shockley) 的指导下工作，两人取得了突破。 Bardeen 和 Brattain 一起构建了第一个固态电气开关工作原型，即晶体管。晶体管允许电流选择性地流过固体材料，而不必绕过易碎和热的玻璃灯泡。这意味着更小的电路可以更快地打开和关闭并且使用更少的能量来完成它。

Two years later in an interview, Shockley said, "There has been a great deal of thought spent on electronic brains, or computing machines. It seems to me that in these robotic brains, the transistor is the ideal nerve cell."

两年后，在接受采访时，肖克利说：“人们对电子大脑或计算机器花费了大量的思考。在我看来，在这些机器人大脑中，晶体管是理想的神经细胞。”

## The integrated circuit 集成电路

Shockley realized the transistor would soon take over the world of electronics, replacing everything that was touched by vacuum tubes. He started his own company, Shockley Semiconductors, to start mass manufacturing the devices, and sought out America's finest minds to help him. That quest led him to Robert Noyce, a physicist from MIT, and Gordon Moore, a chemist from Caltech. Shockley certainly had the right idea, but he was a deeply unpleasant personality. Within a year of signing up to work with him, all the engineers Shockley hired walked out to start their own company instead.

肖克利意识到晶体管将很快接管电子世界，取代真空管接触到的一切。他创办了自己的公司 Shockley Semiconductors，开始大规模制造这些设备，并寻求美国最优秀的人才来帮助他。这一探索使他找到了麻省理工学院的物理学家罗伯特诺伊斯和加州理工学院的化学家戈登摩尔。肖克利的想法当然是正确的，但他是一个非常令人讨厌的人。在签约与他一起工作的一年内，肖克利雇佣的所有工程师都离开了，开始了自己的公司。

That operation, named Fairchild Semiconductors, after their main backer, was arguably Silicon Valley's first “startup.” The opportunity of mass-producing transistors was unparalleled, but the experience of making them was hell. The transistors were tiny and still needed to be hand-soldered to other electrical components, which was a grueling, inaccurate, and frustrating feat of human labor.

这家公司以其主要支持者的名字命名为 Fairchild Semiconductors，可以说是硅谷的第一家“创业公司”。大规模生产晶体管的机会是无与伦比的，但制造它们的经历却是地狱般的。晶体管很小，仍然需要手工焊接到其他电子元件上，这是一项艰巨、不准确且令人沮丧的人工劳动。

Rather than spend hours hunched over a soldering iron, Robert Noyce figured it might be a better idea to etch the complete circuit—transistors, wires, and all—onto one solid wafer of semiconductor material. The integrated circuit was born. "I was lazy," said Noyce, reflecting on his bout of genius. "It just didn't make sense having people soldering together these individual components."

罗伯特·诺伊斯 (Robert Noyce) 认为，与其花几个小时弯腰坐在烙铁前，不如将完整的电路（晶体管、电线等）蚀刻到一块半导体材料的固体晶片上。集成电路诞生了。 “我很懒惰，”诺伊斯回忆起他的天才时说。 “让人们将这些单独的组件焊接在一起是没有意义的。”

The etching was done by a process called photolithography, which shone light rays at silicon treated with light-sensitive material that hardened when exposed to light. This process allowed manufacturers to produce the circuit's grooves. Year after year, photolithographic techniques got better and better, which allowed Fairchild to make their circuits more and more complex.

蚀刻是通过一种称为光刻的工艺完成的，该工艺将光线照射在用光敏材料处理过的硅上，这些光敏材料在暴露于光线时会硬化。这个过程允许制造商生产电路的凹槽。年复一年，光刻技术越来越好，这让 Fairchild 的电路越来越复杂。

The first integrated circuit made by Fairchild Semiconductors had only a single transistor, capable of completing just one logic function. By 1968, the transistors on Fairchild's integrated circuits numbered over 1,000.

仙童半导体制造的第一个集成电路只有一个晶体管，只能完成一个逻辑功能。到 1968 年，Fairchild 集成电路上的晶体管数量已超过 1,000 个。

As integrated circuits got smaller, they started to be called chips, but despite the cutesy name, something remarkable was happening on their surface. The smaller the transistors got, the smaller the current needed to activate them, and the smaller the transistors, the more transistors you could fit on the same chip. In perhaps the greatest example of economies of scale in history, the tinier transistors got, the more computation you could do for less power. The economics of miniaturization were so good they were almost unbelievable. By [scaling](http://worrydream.com/refs/Mead%20-%20Gene%20Youngblood%20Interview.pdf) down the size of a transistor by two, you scaled up the computational power by a factor of eight.

随着集成电路变得越来越小，它们开始被称为芯片，但尽管名字很可爱，但它们的表面却发生了一些非凡的事情。晶体管越小，激活它们所需的电流就越小，晶体管越小，同一芯片上可以容纳的晶体管就越多。也许是历史上规模经济最伟大的例子，晶体管越小，您可以用更少的功率进行更多的计算。小型化的经济效益非常好，几乎令人难以置信。通过将晶体管的尺寸缩小两倍，您可以将计算能力扩大八倍。

Naturally, this begged the question how far this miniaturization could go. Already by 1965, Gordon Moore had predicted, or maybe prophesied, that the number of components on a chip would double every two years. But Moore's colleague at Caltech, the engineer and physicist Carver Mead, wanted an answer to how small these transistors _could_ get. After all, transistors were just little gates that allowed electrons to flow through when activated and blocked electrons when deactivated. The gates, in theory, could get really small indeed. Though the technology didn't exist to make transistors this small yet, Mead [theorized](https://authors.library.caltech.edu/54798/2/FundamentalLimitationsInMicroelectronics%20I.%20MOS_Technology.pdf) that you could theoretically get them small enough to fit something like 10^7 to 10^8 onto an area of 1cm^2.

自然地，这引出了这种小型化能走多远的问题。早在 1965 年，戈登·摩尔就已经预测，或者说预言过，芯片上的元件数量每两年就会翻一番。但是，摩尔在加州理工学院的同事、工程师兼物理学家卡弗·米德 (Carver Mead) 想要知道这些晶体管可以变得多小。毕竟，晶体管只是小门，在激活时允许电子流过，在停用时阻止电子流过。从理论上讲，大门确实可以变得非常小。虽然目前还没有使晶体管变得这么小的技术，但米德推测，理论上你可以把它们做得足够小，以在 1cm^2 的面积上容纳 10^7 到 10^8 之类的东西。

For 1972, these claims were outrageous. At the time, integrated circuits only had about 1,000 transistors on them, but Mead was predicting an improvement of five to six magnitudes. While many academics and computer specialists were busy doubting Mead's predictions, Gordon Moore was already working tirelessly to make them a reality.

对于 1972 年，这些说法令人发指。当时，集成电路上只有大约 1,000 个晶体管，但米德预测会有五到六个数量级的改进。当许多学者和计算机专家忙于怀疑米德的预测时，戈登摩尔已经不懈地努力使它们成为现实。

## The central processing unit 中央处理器

By 1968, Fairchild Semiconductors was a big, clunky company with 30,000 employees. It wasn't a startup anymore—it was, as Robert Noyce put it, a supertanker. In order to compete with the fast-moving world of electronics, Noyce and Moore left Fairchild to start a new, nimbler venture. They called their new company Integrated Electronics, which they shortened to Intel.

到 1968 年，仙童半导体是一家拥有 30,000 名员工的大公司。它不再是一家初创公司——正如罗伯特·诺伊斯 (Robert Noyce) 所说，它是一艘超级油轮。为了与快速发展的电子世界竞争，Noyce 和 Moore 离开 Fairchild 开始了一个新的、更灵活的冒险。他们将新公司命名为 Integrated Electronics，并将其简称为 Intel。

Right around the seventies, these integrated circuits were starting to count pretty well, but they couldn't remember much. Noyce and Moore figured that if transistors could increase the speed and energy efficiency of processing logic functions, maybe they could do the same for memory storage.

大约在七十年代，这些集成电路开始算得很好，但他们记不住太多东西。诺伊斯和摩尔认为，如果晶体管可以提高处理逻辑功能的速度和能源效率，也许它们也可以在内存存储方面发挥同样的作用。

Intel's first product was the 1103—a semiconductor-based memory chip. Transistors would open and close to either store or release an electric charge, thereby storing or releasing information.

英特尔的第一个产品是 1103——一种基于半导体的内存芯片。晶体管会打开和关闭以存储或释放电荷，从而存储或释放信息。

The insight for Intel's next great invention came from Ted Hoff, an engineer who wondered what might happen if you could integrate both a 1103 memory chip and a processing unit all into the same integrated circuit. The result was the 4004 chip, released in the third year of Intel's existence. The 4004 wasn't just a chip—it was an entire computer on a chip. It cost $360, had 2,300 transistors, and could perform 60,000 instructions per second, but most importantly, it could execute instructions stored in a memory bank and had working "scratch pad" memory to help it complete more complicated calculations.

英特尔下一个伟大发明的洞察力来自泰德霍夫，他是一位工程师，他想知道如果将 1103 内存芯片和处理单元都集成到同一个集成电路中会发生什么。结果就是 4004 芯片，在英特尔成立的第三年发布。 4004 不仅仅是一个芯片——它是一个芯片上的完整计算机。它的成本为 360 美元，拥有 2,300 个晶体管，每秒可执行 60,000 条指令，但最重要的是，它可以执行存储在内存条中的指令，并具有可工作的“便签本”内存来帮助它完成更复杂的计算。

This made it the first generally programmable “central processing unit,” or CPU, and it was a game changer. Ted Hoff later [said](https://www.youtube.com/watch?v=YtqF2gUsiU4), "We democratized the computer."

这使它成为第一个普遍可编程的“中央处理器”或 CPU，并且改变了游戏规则。泰德霍夫后来说，“我们使计算机民主化了。”

The year after Intel released the 4004, they released the 8008, then in two years the 8080, which was 10 times faster than the 4004, but still cost the same $360.

英特尔发布 4004 后的第二年，他们发布了 8008，然后在两年后发布了 8080，它比 4004 快 10 倍，但价格仍然是 360 美元。

The fact that a generally programmable computer could be not only affordable, but also the size of a thumbnail, gave rise to the idea that computers weren’t just for offices anymore. Soon, each person could have a computer of their own.

普遍可编程的计算机不仅可以负担得起，而且只有缩略图那么大，这一事实使人们产生了这样一种想法，即计算机不再只是用于办公室。很快，每个人都可以拥有自己的电脑。

The Altair 8800, released in 1975, was the first attempt at a personal computer. It was powered by the Intel 8080 chip, had only 250 bytes of memory, and could be programmed by flipping a bunch of mechanical switches. Remarkably, [tens of thousands](https://arstechnica.com/features/2005/12/total-share/) of Altairs 8800s were sold, enough for the producers to break even. The Altair may not have had much staying power, but in the wake of its rollout, things moved fast.

1975 年发布的 Altair 8800 是个人计算机的首次尝试。它由 Intel 8080 芯片驱动，只有 250 字节的内存，可以通过拨动一组机械开关来进行编程。值得注意的是，售出了数万台 Altairs 8800，足以让生产商收支平衡。 Altair 可能没有太多的持久力，但在它推出之后，事情发展得很快。

Later that year, Bill Gates and Paul Allen launched Microsoft, whose first product was an interpreter that helped users program their Altair 8800s. Two years later, in 1977, Steve Wozniak and Steve Jobs released the Apple II, a personal computer decked out with a monitor and the first commercially available graphical user interface, and powered by the MOS 6502 CPU, a chip rivaling Intel's.

那年晚些时候，比尔盖茨和保罗艾伦创立了微软，其第一款产品是帮助用户对他们的 Altair 8800 进行编程的解释器。两年后的 1977 年，Steve Wozniak 和 Steve Jobs 发布了 Apple II，这是一款配备显示器和第一款商用图形用户界面的个人电脑，搭载 MOS 6502 CPU，这是一款可与 Intel 媲美的芯片。

Intel's invention of a CPU that programmers could write their own code for gave birth to the personal computing movement. However, it was only when IBM, the largest computer company in the world, started ordering CPUs from Intel to produce _its_ line of PCs that Intel's dominance over the computing industry was set.

英特尔发明了一种 CPU，程序员可以为其编写自己的代码，从而催生了个人计算运动。然而，只有当世界上最大的计算机公司 IBM 开始向英特尔订购 CPU 以生产其 PC 系列时，英特尔在计算行业的统治地位才得以确立。

## General-purpose chips 通用芯片

IBM flooded Intel with orders. To meet the demand, Intel had to start licensing its chip designs, called instruction set architectures, to other semiconductor foundries.

IBM 向英特尔发出大量订单。为了满足需求，英特尔不得不开始将其芯片设计（称为指令集架构）授权给其他半导体代工厂。

The instruction set architecture provides a complete description of a chip. It defines which instructions the processor can perform, what data types it can read, and how memory is managed, along with a host of other things.

指令集架构提供了对芯片的完整描述。它定义了处理器可以执行哪些指令、可以读取哪些数据类型、如何管理内存以及许多其他内容。

All of Intel's chips were being built to the specifications of their x86 architecture; given the massive demand for Intel chips, soon nearly all semiconductor foundries were manufacturing chips according to Intel's x86 model, too.

英特尔的所有芯片都是按照其 x86 架构的规格制造的；鉴于对英特尔芯片的巨大需求，很快几乎所有的半导体代工厂也开始根据英特尔的 x86 模型制造芯片。

Manufacturing chips according to one set of specifications made it easier on semiconductor foundries and on software writers, who could be sure that their programs would be compatible with any chip as long as it was designed to x86 standards. But the extreme standardization was bad news for any other companies hoping that their chip designs would see the light of day.

根据一套规范制造芯片使半导体代工厂和软件编写者更容易，他们可以确信他们的程序将与任何芯片兼容，只要它是按照 x86 标准设计的。但对于任何希望自己的芯片设计能够问世的其他公司来说，极端标准化都是个坏消息。

The world of personal computing simply wasn't big enough for multiple versions of CPU architectures, and the fact that Intel's x86 model won out meant that many competing integrated device manufacturers fell by the wayside.

个人计算的世界根本不够大，无法容纳多个版本的 CPU 架构，而英特尔 x86 模型胜出的事实意味着许多竞争性集成设备制造商都被淘汰出局。

Given the landscape, most companies working on chips had to pick if they wanted to focus on designing and selling their own chip designs, and risk never getting any customers, or focus on fabricating someone else's designs, an increasingly competitive field where costs of production were starting to rise.

鉴于这种情况，大多数从事芯片工作的公司都必须做出选择，是要专注于设计和销售自己的芯片设计，冒着永远得不到任何客户的风险，还是专注于制造别人的设计，这是一个竞争日益激烈的领域，生产成本越来越高。开始上升。

By 2000, regularly available CPUs had nearly 10 million transistors. The transistor gate lengths were becoming smaller than the wavelengths of light and therefore invisible to the human eye. Manufacturing integrated circuits at such a tiny scale was becoming a more expensive operation such that soon, foundries were starting to out-innovate Intel. In 1999, Taiwan Semiconductor Manufacturing Company (TSMC) was the [first](https://www.tsmc.com/english/dedicatedFoundry/technology/logic/l_018micron) semiconductor foundry to make transistors that were 180 nanometers wide.

到 2000 年，常规可用的 CPU 有近 1000 万个晶体管。晶体管栅极长度变得小于光的波长，因此人眼不可见。以如此小的规模制造集成电路正变得更加昂贵，因此很快，代工厂开始在创新上超越英特尔。 1999 年，台积电 (TSMC) 成为第一家制造 180 纳米宽晶体管的半导体代工厂。

Year after year, the cost of producing smaller transistors pushed more and more foundries out of business. Getting your hands on the increasingly esoteric photolithography instruments required deep pockets, and not everyone could cough up the cash. In the following years, the semiconductor industry saw successive waves of corporate consolidation and mergers.

年复一年，生产更小晶体管的成本迫使越来越多的代工厂倒闭。获得越来越深奥的光刻仪器需要雄厚的财力，而且并不是每个人都能掏出现金。随后几年，半导体行业接二连三地出现了企业整合和兼并的浪潮。

As the struggle to miniaturize grew and progress slowed, the first predictions of an end to Moore's Law started rolling in—[often from Gordon Moore himself](https://www.youtube.com/watch?v=YfDDGEtyTmg). Many just couldn't see how it would be economical to continue making transistors smaller.

随着小型化斗争的加剧和进展的放缓，摩尔定律终结的第一个预测开始滚滚而来——通常来自戈登摩尔本人。许多人只是看不出继续使晶体管更小是多么经济。

To ensure continued improvements for consumers, CPUs started being designed with multiple processor cores. Rather than having one CPU in your computer, why not have two or three, which can handle twice or three times as many instructions at the same time? It soon became standard for most machines to start processing in “parallel.” Right now, your computer is doing many tasks at once: retrieving information from the Internet, connecting with Bluetooth devices, and refreshing your screen, alongside running many other programs. It's doing all of that and more through the help of parallel processing.

为了确保为消费者持续改进，CPU 开始设计为具有多个处理器内核。与其在您的计算机中使用一个 CPU，不如使用两个或三个，它们可以同时处理两倍或三倍的指令？它很快成为大多数机器开始“并行”处理的标准。现在，您的计算机同时执行许多任务：从 Internet 检索信息、连接蓝牙设备、刷新屏幕，同时运行许多其他程序。它在并行处理的帮助下完成了所有这些以及更多工作。

Parallel processing helped computers execute lots of independent tasks at the same time, and even the mere ability to do this ushered in a new era of computational possibility.

并行处理帮助计算机同时执行许多独立的任务，甚至仅仅能够做到这一点就开创了计算可能性的新时代。

For one thing, parallel processors made it possible for the Internet to be used by _billions_ around the world _at the same time_. Servers in data centers are packed with dozens of processor cores, each of which is busy connecting dozens of clients to web pages.

一方面，并行处理器使全球数十亿人同时使用互联网成为可能。数据中心的服务器挤满了数十个处理器内核，每个处理器内核都忙于将数十个客户端连接到网页。

For another, complicated matrix multiplication, a key feature of neural network calculations, was perfectly suited for parallel computation. Feeding big neural network problems into powerful multi-core processors was a watershed moment in producing more powerful AI algorithms, and marked a renewed interest in artificial intelligence, which once again seemed feasible after the field suffered years without any progress.

另一方面，复杂的矩阵乘法是神经网络计算的一个关键特征，非常适合并行计算。将大型神经网络问题输入强大的多核处理器是产生更强大的 AI 算法的分水岭，标志着人们对人工智能重新产生了兴趣，在该领域多年没有取得任何进展后，这似乎再次成为可能。

## Special-purpose chips 专用芯片

The hidden secret of the digital revolution lay in the consistently improving computational ability made possible by making transistors smaller, and putting more of them into our computers. Today, the smallest transistors we manufacture are somewhere around 3nm wide, but it's a challenge. Three nanometers is roughly the width of 15 Silicon atoms end to end, and at the atomic scale, weird stuff happens. With transistors this small, electrons don't always behave as assumed. Rather than flowing through the circuit as expected, electrons sometimes jump across into neighboring circuits, a phenomenon called electron tunneling, which messes up the function of the computer.

数字革命隐藏的秘密在于通过使晶体管更小并将更多晶体管放入我们的计算机中来不断提高计算能力。今天，我们制造的最小晶体管大约有 3 纳米宽，但这是一个挑战。 3 纳米大约是 15 个硅原子首尾相连的宽度，在原子尺度上，会发生奇怪的事情。对于这么小的晶体管，电子的行为并不总是像假设的那样。电子有时不会像预期的那样流经电路，而是跳入相邻电路，这种现象称为电子隧穿，会扰乱计算机的功能。

Semiconductor companies have devised mitigating strategies to address these defects, but incorporating them into integrated circuits only makes producing chips more expensive. Furthermore, given the number of defects in manufacturing chips has increased, the yield of functional chips from running fabs at this scale has declined. In [2015](https://www.youtube.com/watch?v=YfDDGEtyTmg), the cost of producing each individual transistor started increasing, a remarkable reversal in the economics of Moore's Law.

半导体公司已经制定了缓解策略来解决这些缺陷，但将它们集成到集成电路中只会使芯片的生产成本更高。此外，鉴于制造芯片中的缺陷数量增加，以这种规模运行的晶圆厂生产的功能芯片的产量已经下降。 2015 年，生产每个晶体管的成本开始增加，摩尔定律的经济学显着逆转。

Ever since writing his 1972 paper anticipating that chips would see 10^8 transistors over 1cm^2, Carver Mead's then-outrageous predictions have proved conservative in an era that can see over 6x10^9 over the same area. However, like any great physicist, Mead knew that no exponential lasts forever.

自从他 1972 年的论文预测芯片将在 1cm^2 上看到 10^8 个晶体管以来，Carver Mead 当时离谱的预测在一个可以在同一面积上看到超过 6x10^9 的时代被证明是保守的。然而，像任何伟大的物理学家一样，米德知道没有指数会永远持续下去。

He, too, had been anticipating the end of Moore's Law for quite some time, and had criticized the industry's tunnel vision over transistor density when the real improvements in computational speed might be found elsewhere entirely.

很长一段时间以来，他也一直在期待摩尔定律的终结，并批评了业界对晶体管密度的狭隘眼光，因为计算速度的真正提高可能完全在其他地方。

“The semiconductor guys don’t know much about computers so they’ve copied a bunch of ancient architectures,” [he said](http://worrydream.com/refs/Mead%20-%20Gene%20Youngblood%20Interview.pdf). “So what we have in the personal computers is creaky old architectures with this wonderful \[semiconductor\] technology. So the people driving the technology don’t know anything about systems and the people who have built traditional large computer systems haven’t participated in the \[semiconductor\] technology revolution."

“半导体人对计算机了解不多，所以他们复制了一堆古老的架构，”他说。 “因此，我们在个人计算机中拥有的是采用这种出色的\[半导体\]技术的破旧架构。因此，推动技术发展的人对系统一无所知，构建传统大型计算机系统的人也没有参与 \[半导体\] 技术革命。”

At the end of the day, the speed of computation is determined by how quickly electrons can move from point A to point B to complete their instructions. The idea that all computations should be run through the same standardized, general-purpose hardware architecture to complete those instructions is a huge bottleneck on computational efficiency.

归根结底，计算速度取决于电子从 A 点移动到 B 点以完成指令的速度。所有计算都应该通过相同的标准化通用硬件架构来完成这些指令的想法是计算效率的一个巨大瓶颈。

If you want to compute something really fast, you probably don't have time for the software you write to be compiled into x86 machine code and then executed. Instead, Carver Mead suggests that you map your program directly into the silicon. "The technology for doing that we understand pretty well. We’ve developed the technology for taking high-level descriptions and putting them on silicon,” he [said](http://worrydream.com/refs/Mead%20-%20Gene%20Youngblood%20Interview.pdf). “It’s called silicon compilation, which is the obvious next step. You need to compile things right down into the chip instead of compiling them into some code that you feed to this giant mass of chips that grinds away on it trying to interpret it.”

如果你想真正快速地计算一些东西，你可能没有时间将你编写的软件编译成 x86 机器代码然后执行。相反，Carver Mead 建议您将程序直接映射到硅片中。 “我们非常了解这样做的技术。我们已经开发出用于获取高级描述并将它们放在硅片上的技术，”他说。“这称为硅片编译，这是显而易见的下一步。你需要编译事情直接进入芯片，而不是将它们编译成一些代码，你将这些代码提供给这个巨大的芯片，这些芯片在它上面磨掉试图解释它。”

The concept of producing application-specific integrated circuits—or ASICs for short—is exactly what transpired. The most popularly recognizable variety of ASIC is probably the Bitcoin miner. These are processor chips whose circuits are designed specifically so they can be hyper-efficient at running the SHA-256 algorithm, and thereby mine Bitcoin.

生产专用集成电路（或简称 ASIC）的概念正是应运而生的。最广为人知的 ASIC 品种可能是比特币矿机。这些处理器芯片的电路经过专门设计，因此它们可以超高效地运行 SHA-256 算法，从而挖掘比特币。

However, the idea of making application specific chips doesn't just end with Bitcoin. Virtually every company that produces a device that relies on an integrated circuit has realized that sooner or later, they're going to need to start producing chips customized to their applications. The old Intel model of buying an off-the-shelf chip and sticking it into your product just isn't going to cut it anymore, especially in an era where you can't count on Moore's Law to deliver future improvements in performance.

然而，制造专用芯片的想法并不仅限于比特币。几乎每家生产依赖于集成电路的设备的公司都意识到，他们迟早需要开始生产针对其应用定制的芯片。购买现成芯片并将其安装到您的产品中的旧 Intel 模式将不再适用，尤其是在您不能指望摩尔定律在未来提供性能改进的时代。

All chip design shops—including Intel, Nvidia, and Qualcomm—are now facing the existential question of what to do when modern technology companies start hiring their own chip engineers capable of designing specialized integrated circuits.

所有芯片设计公司——包括英特尔、英伟达和高通——现在都面临着生存问题，即当现代科技公司开始雇佣自己的能够设计专用集成电路的芯片工程师时该怎么办。

In 2020, Apple moved away from using Intel chips to power its MacBooks after designing a specialized M1 chip, based on a different and faster kind of CPU architecture, called ARM, most commonly seen in smartphones. The real innovation of the M1 chip was to design a smarter placement of memory and processor centers so that information could flow faster between the two, thereby executing instructions faster. The decision to start making their own chip designs was a terrifically successful move for Apple, as its M1 chip is now considered the fastest CPU on the market.

2020 年，Apple 在设计了一种专门的 M1 芯片后不再使用英特尔芯片为其 MacBook 提供动力，该芯片基于一种不同且速度更快的 CPU 架构，称为 ARM，最常见于智能手机。 M1 芯片的真正创新在于设计了更智能的内存和处理器中心位置，以便信息可以在两者之间更快地流动，从而更快地执行指令。开始制作自己的芯片设计的决定对 Apple 来说是一个非常成功的举动，因为它的 M1 芯片现在被认为是市场上最快的 CPU。

The world of data centers has also seen a proliferation of specialized chip models. Amazon and Microsoft, running massive proprietary data centers, both now have teams that design chips tailor-made for their respective servers.

数据中心领域也见证了专用芯片模型的激增。亚马逊和微软运营着庞大的专有数据中心，现在都拥有专门为各自服务器设计芯片的团队。

And in the realm of AI, Google revealed the design of its [Tensor Processing Unit](https://cloud.google.com/blog/products/ai-machine-learning/google-supercharges-machine-learning-tasks-with-custom-chip) in 2016, a chip specifically designed to run Google's TensorFlow AI algorithm. Similarly, in 2022, Tesla announced that it has developed its own specialized [Dojo](https://www.nextplatform.com/2022/08/23/inside-teslas-innovative-and-homegrown-dojo-ai-supercomputer/) chip.

在人工智能领域，谷歌在 2016 年公布了其 Tensor Processing Unit 的设计，这是一款专门设计用于运行谷歌 TensorFlow AI 算法的芯片。同样，在 2022 年，特斯拉宣布开发了自己的专用 Dojo 芯片。

## A wild west of hardware 硬件的狂野西部

Hitting the physical limits on transistor length is an exciting, if uncertain, moment in the computing industry. New techniques will need to be pursued to gain improvements in computing speeds, and the way we think about computing might start to move away from a framework that, to date, has been dominated by the constraints of standardized chip architectures.

触及晶体管长度的物理极限是计算行业中一个激动人心的时刻，尽管不确定。需要寻求新技术来提高计算速度，我们对计算的思考方式可能会开始偏离一个框架，该框架迄今为止一直受标准化芯片架构的限制。

Designing microelectronics will have to become synonymous with computer science, and the gap in understanding between hardware and software will need to close. As the great computer scientist Alan Kay [once said](https://www.youtube.com/watch?v=XAfTXYa36f4), "People who are really serious about software should make their own hardware."

微电子设计必须成为计算机科学的代名词，硬件和软件之间的理解差距需要缩小。正如伟大的计算机科学家 Alan Kay 曾经说过的那样，“真正认真对待软件的人应该制造自己的硬件。”

And whereas the path to “making your own hardware” used to seem nearly impossible, it might actually be closer than we think. One of the biggest barriers to designing chips is the fact that making custom chips takes a long time—often years. While many of the design steps still require lots of manual review, the timeline might soon shrink as new solutions are emerging that can make the process more efficient. Google is working on producing a machine learning [model](https://www.nature.com/articles/s41586-021-03544-w.epdf?sharing_token=8za_nMkuk42509LyAn-xY9RgN0jAjWel9jnR3ZoTv0PW0K0NmVrRsFPaMa9Y5We97spjdO-aPpvZYXPHhKbfpfPljZaIm3b-kyQ3gKElVBjZIxn_5lBKsnqIIUn2YkCI3IFe5puGE49yIrhVbJrW9eUbKmMo7FS9KDgM4hs9TFFEBv1CLtLi4EFaXPirF-G_lwtOzFcc-pVSzW5vcQBQt19OPe2Fx4nUQHU5ItFuNC8%3D&tracking_referrer=www.theverge.com) that can assist chip designers in "chip floorplanning," a crucial step involved in designing chips. In early 2022, Google also revealed a program that lets chip designers access open source software for chip designing, even allowing users to print designs for [free](https://thenewstack.io/google-puts-open-source-in-chip-design-and-manufacturing/) with partner fabs.

尽管过去“制造自己的硬件”的道路似乎几乎是不可能的，但它实际上可能比我们想象的更近了。设计芯片的最大障碍之一是制造定制芯片需要很长时间——通常是数年。虽然许多设计步骤仍然需要大量人工审查，但随着可以提高流程效率的新解决方案的出现，时间可能很快就会缩短。谷歌正致力于开发一种机器学习模型，该模型可以帮助芯片设计人员进行“芯片布局规划”，这是设计芯片的关键步骤。 2022 年初，谷歌还透露了一项计划，允许芯片设计人员访问用于芯片设计的开源软件，甚至允许用户与合作伙伴晶圆厂免费打印设计。

In due time, researchers and entrepreneurs like [Anders Olofsson](https://www.maths.lth.se/matematiklu/personal/olofsson/) are anticipating that we might see faster growth in the open-source hardware community, as Carver Mead's vision for "silicon algorithms" and more widespread use of silicon compilers becomes more of a reality.

在适当的时候，像 Anders Olofsson 这样的研究人员和企业家预计，随着 Carver Mead 的“硅算法”愿景和硅编译器的更广泛使用成为现实，我们可能会看到开源硬件社区的更快增长。

There are even some doing research at the level of fundamental physics to find new, tinier materials that could succeed at making circuits faster and smaller. One such effort involves replacing silicon channels with circuits made of [carbon nanotubes](https://en.wikipedia.org/wiki/Carbon_nanotube_field-effect_transistor). Another is interested in replacing the electrons in those channels with tinier and faster-moving [photons](https://physicsworld.com/a/the-promise-of-silicon-photonics/).

甚至有一些人在基础物理学层面进行研究，以寻找新的、更细小的材料，这些材料可以成功地使电路变得更快、更小。其中一项努力涉及用碳纳米管制成的电路代替硅通道。另一个感兴趣的是用更小和更快移动的光子替换那些通道中的电子。

Until such breakthroughs succeed at producing commercially feasible products, many of us will have to reckon with a new digital normal. A world without ever smaller circuitry will certainly need a new computational paradigm, one that moves away from a chip-for-all framework, and toward a world of new and more varied chip architectures and devices. The computer scientists of the future will need to understand not only the software, but also the hardware on which their algorithms run, presaging a time where physics will rear its head yet again in our study of digital devices.

在这些突破成功生产出商业上可行的产品之前，我们中的许多人将不得不考虑新的数字常态。一个没有更小电路的世界肯定需要一种新的计算范式，一种从通用芯片框架转向一个新的、更多样化的芯片架构和设备的世界的范式。未来的计算机科学家不仅需要了解软件，还需要了解运行算法的硬件，这预示着物理学将在我们对数字设备的研究中再次抬头的时代。

___

_Unless otherwise noted, source material including quotes in this piece comes from_ [The Silicon Boys: And Their Valley of Dreams](https://www.amazon.com/Silicon-Boys-Their-Valley-Dreams/dp/0688179061) _by David A. Kaplan._

除非另有说明，否则本文中包括引用在内的原始资料均来自大卫·A·卡普兰 (David A. Kaplan) 的《硅男孩：他们的梦想之谷》(The Silicon Boys: And Their Valley of Dreams)。

___

_Anna-Sofia Lesiv is a writer at venture capital firm_ [_Contrary_](https://contrary.com/)_, where she originally published_ [_this piece_](https://contrary.com/blog/evolution-of-chips)_. She graduated from Stanford with a degree in economics, and has spent time at Bridgewater, Founders Fund, and 8VC._

Anna-Sofia Lesiv 是风险投资公司 Contrary 的作家，她最初是在该公司发表这篇文章的。她毕业于斯坦福大学，获得经济学学位，曾在桥水基金、Founders Fund 和 8VC 工作过。
