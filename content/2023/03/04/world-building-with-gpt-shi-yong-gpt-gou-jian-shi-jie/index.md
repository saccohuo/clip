---
title: "使用 GPT 构建世界"
date: 2023-03-04T11:36:49+08:00
updated: 2023-03-04T11:36:49+08:00
taxonomies:
  tags: []
extra:
  source: https://ianbicking.org/blog/2023/02/world-building-with-gpt.html
  hostname: ianbicking.org
  author: 
  original_title: "World Building With GPT"
  original_lang: en
---

I’ve been doing lots of experiments with GPT, though I’ve only [written about one](https://ianbicking.org/blog/2023/01/infinite-ai-array.html) until now… the more serious something is the harder it is to call it finished or identify the outcomes. Here I’ll describe something a bit lighter: world building, or specifically city building, with GPT.  

我一直在用 GPT 做很多实验，尽管直到现在我只写过一个……事情越严重，就越难称之为完成或确定结果。在这里，我将描述一些更轻松的事情：使用 GPT 构建世界，或者特别是城市构建。

This post is for people who are interested in building interactive tools on top of GPT and want to see some of the things I’ve encountered and what I’ve found that is successful and what is still a challenge.  

这篇文章是为那些对在 GPT 之上构建交互式工具感兴趣并希望了解我遇到的一些事情以及我发现的成功和仍然存在挑战的人而写的。

## Where it started  

从哪里开始

I enjoy game worlds where the world seems alive and the details suggest a backstory. The real world both is and isn’t this way: every house has stories, people invested in its details, each building is occupied and reoccupied repeatedly.  

我喜欢游戏世界，在这个世界里，世界似乎充满活力，细节暗示着一个背景故事。现实世界既是这样又不是这样：每栋房子都有故事，人们对其细节进行了投资，每栋建筑都被反复占用和重新占用。  

But our world is also quiet, private, less eccentric than we might want, and imaginary worlds can be fun. Procedurally generated roguelike games give some of the excitement of exploration but lack story and depth.  

但我们的世界也很安静、私密，没有我们想要的那么古怪，想象的世界也很有趣。程序生成的 roguelike 游戏提供了一些探索的刺激，但缺乏故事和深度。  

A game like Stardew Valley has stories but is necessarily pretty small and static.  

像 Stardew Valley 这样的游戏有故事，但一定很小而且是静态的。

With generative AI we can change these trade-offs! Is it possible to make a big world that is both eclectic and consistent? Can it include story and personality? I don’t know the answer, but I’d like to share what I’ve got…  

使用生成式 AI，我们可以改变这些权衡取舍！是否有可能创造一个既折衷又一致的大世界？它可以包括故事和个性吗？我不知道答案，但我想分享我所知道的……

## The tool  

工具

In a previous experiment in story building I used a step-by-step approach: generate the first passage, generate a next passage, etc. That’s appealing and simple but leads to a wandering and unstructured narrative.  

在之前的故事构建实验中，我使用了一种循序渐进的方法：生成第一段，生成下一段，等等。这很吸引人，也很简单，但会导致漫无目的的、无结构的叙述。  

I believe in both stories and worlds we want a kind of fractal complexity: at each scale we want most things to be “typical” but also some surprise.  

我相信在故事和世界中我们都想要一种分形的复杂性：在每个尺度上，我们都希望大多数事物都是“典型的”，但也希望有一些惊喜。  

In a story the surprises might go from large to small scale like: an unusual character arc, a surprise plot development, an alternate perspective, an unexpected response in dialog, a perceptive detail in a description, and an unusual word in a sentence.  

在一个故事中，惊喜可能从大到小，例如：不寻常的人物弧线、令人惊讶的情节发展、不同的视角、对话中意想不到的反应、描述中的感知细节以及句子中不寻常的词。  

If you always write the-most-likely-next-thing then it’ll be boring. If you only write surprises then there’s nothing to even be surprised about.  

如果你总是写最有可能的下一件事，那会很无聊。如果您只写惊喜，那么就没有什么值得惊讶的了。

Similarly we want to build a world or city that expresses a broad theme and consistency, but also has diversity and surprises throughout it. To do this I’ve approached the building hierarchically:  

同样，我们希望构建一个表达广泛主题和一致性的世界或城市，同时也具有多样性和惊喜。为此，我分层次地研究了这座建筑：

1.  Establish the type of city (medieval, fantasy, noir, etc). Give it a name and some story.  
    
    确定城市类型（中世纪、奇幻、黑色等）。给它起个名字和一些故事。
2.  Identify distinct neighborhoods.  
    
    识别不同的社区。
3.  Create buildings in those neighborhoods.  
    
    在这些街区建造建筑物。
4.  Create people associated with the buildings.  
    
    创建与建筑物相关联的人。
5.  Populate the buildings with rooms, furniture, and objects.  
    
    用房间、家具和物品填充建筑物。

There are problems with this approach that I’ll touch on later, but it’s a start.  

这种方法存在一些问题，我稍后会谈到，但这只是一个开始。

You can see it in action here:  

您可以在此处查看实际效果：

<iframe src="https://www.youtube.com/embed/YUEXo3wrf70" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="" data-immersive-translate-effect="1"></iframe>

## What works?  

什么有效？

Some stuff I really like…  

有些东西我真的很喜欢……

### GPT\-generated lists  

GPT 生成的列表

GPT is good at coming up with lists: lists of city types, names, people. As I used the tool more I started to have my own opinions on what I wanted to make, but those lists were an important part of expanding my own imagination. I’ve made [other experiments](https://www.youtube.com/watch?v=nsIPC_eqfwg) where I filled in all the initial information by hand without any GPT suggestions, and I miss the lists.  

GPT 擅长列出列表：城市类型、名称、人物的列表。随着我越来越多地使用该工具，我开始对自己想要制作的东西有自己的看法，但这些列表是扩展我自己想象力的重要部分。我做了其他实验，在没有任何 GPT 建议的情况下，我手动填写了所有初始信息，但我错过了列表。

### Natural language context  

自然语言上下文

The cities are formed in a top-down way, and all the top layers (city, backstory, neighborhood) are purely context. The top layer descriptions are very important but have no need for structure, it’s all just language.  

城市以自上而下的方式形成，所有顶层（城市、背景故事、社区）都是纯粹的背景。顶层描述很重要，但不需要结构，它只是语言。  

Not every aspect has to be enumerated, just the ones that seem important for this city.  

不必列举每个方面，只需列举对这座城市而言似乎很重要的方面。

### Reinforcing city character  

强化城市特色

A general character to the city (e.g., “fantasy city”) isn’t enough to build something consistent. The character of the city needs to be repeated and reinforced at different levels. Details like architecture and building materials may have to be specified.  

城市的一般特征（例如，“幻想城市”）不足以建立一致的东西。城市的特色需要在不同层面上得到重复和强化。可能必须指定建筑和建筑材料等细节。

This is primarily done at the neighborhood level, though it would benefit from building-specific attributes more strongly informing person generation.  

这主要是在社区层面完成的，尽管它会受益于建筑物特定的属性，这些属性更能强烈地告知人们的生成。  

For instance in a fantasy city it’s common that everyone will start out powerful and loyal and wise, even when they occupy a hovel or explicitly partake in the dark arts.  

例如，在一个奇幻城市中，每个人一开始都会变得强大、忠诚和睿智，即使他们住在一间小屋或明确参与黑魔法时也是如此。

### Structured output  

结构化输出

When we get to parts with specific structure it’s a comfortable transition. Buildings have sizes, people have roles, etc. GPT can fill in these details. If you wanted to plug the city into a map builder or other structured game format, you can produce the metaata you need.  

当我们到达具有特定结构的部分时，这是一个舒适的过渡。建筑物有大小，人有角色等。GPT 可以填写这些细节。如果您想将城市插入地图构建器或其他结构化游戏格式，您可以生成所需的元数据。

### Filling out content you create  

填写您创建的内容

When you don’t want to take a GPT suggestion, GPT is pretty good at filling in the details in something you produce. So if you ask for a “factory” it works well for GPT to turn that into a fuller description, size, etc.  

当您不想采纳 GPT 建议时，GPT 非常擅长在您生成的内容中填写详细信息。因此，如果您要求“工厂”，GPT 可以很好地将其转化为更完整的描述、尺寸等。

I only implemented this for structured elements, and not freeform fields like neighborhood descriptions. I should fix that!  

我只为结构化元素实现了这个，而不是像社区描述这样的自由格式字段。我应该解决这个问题！

### Pushing GPT helps  

推动 GP 帮助

Small contextual prompt additions can be helpful. For instance GPT has sometimes wanted to suggest sofas and armchairs for a factory, but a small note (“factory equipment and tools”) can fix that.  

小的上下文提示添加可能会有所帮助。例如，GPT 有时想为工厂推荐沙发和扶手椅，但一张小纸条（“工厂设备和工具”）可以解决这个问题。

**However** I’ve found this needed too often for character descriptions. The descriptions start out seeming OK but begin to feel boring and repetitious. The building and neighborhood need to more explicitly affect the people prompt. Right now the prompt is effectively:  

但是我发现角色描述经常需要这个。这些描述一开始看起来还不错，但开始让人觉得无聊和重复。建筑物和社区需要更明确地影响人们的提示。现在提示有效：

> **\[General city context\]  
> 
> \[一般城市背景\]**  
> 
> A list of owners, caretakers, residents, tenants, and other inhabitants for **\[Building Name\]** (**\[Building Description\]**) Give each person an interesting and culturally appropriate name and a colorful background and personality.  
> 
> \[建筑物名称\]（\[建筑物描述\]）的所有者、管理员、住户、租户和其他住户的列表，给每个人一个有趣且符合文化的名字，以及丰富多彩的背景和个性。

If you ask a more open-ended question like:  

如果您问一个更开放的问题，例如：

> Make a numbered list of the kinds of people that would occupy a building called **\[Building Name\]** described as: **\[Building Description\]**  
> 
> 列出居住在名为 \[Building Name\] 的建筑物中的人员类型，描述如下： \[Building Description\]

then you get a good list of professions and roles (better than my hardcoded set). If you add this:  

然后你会得到一个很好的职业和角色列表（比我的硬编码集更好）。如果您添加以下内容：

> For each item include a 10-word note on the likely personality, limitations, and character flaws  
> 
> 对于每个项目，包括一个 10 字的注释，说明可能的性格、局限性和性格缺陷

then you also start battling the relentless positivity, with results like “Supply Chain Managers: Responsible and knowledgeable, but prone to micromanaging” and “Magical Robots: Resourceful and imaginative, but restricted by programming”.  

然后你也开始与无情的积极性作斗争，结果如“供应链经理：负责任和知识渊博，但容易微观管理”和“魔法机器人：足智多谋和想象力，但受编程限制”。

\[Note: after writing this I implemented a list of jobs/roles as part of buildings; it was effective!\]  

\[注意：写完这篇文章后，我将工作/角色列表作为建筑物的一部分；这是有效的！\]

### Putting people in buildings is great  

把人放在建筑物里很棒

For all my criticisms in the previous section, adding people is great and I only want it to be better! Buildings have some history and personality, but the people associated with them make it seem much more alive.  

对于我在上一节中的所有批评，加人很棒，我只希望它变得更好！建筑物具有一定的历史和个性，但与之相关的人让它看起来更有活力。

> **Razzaqua Sephina**: Razzaqua Sephina is the mysterious and enigmatic owner of the Warehouse of the Cankered Crypt. She is a master at thaumaturgy, specializing in curses and dark artifacts. Those who have met her say she is as cold as ice.  
> 
> Razzaqua Sephina：Razzaqua Sephina 是 Cankered Crypt 仓库的神秘主人。她是奇术大师，专攻诅咒和黑暗神器。见过她的人都说她冷若冰霜。  
> 
> Despite this, locals claim she is fiercely loyal and protective of her tenants.  
> 
> 尽管如此，当地人声称她非常忠诚并保护她的房客。
> 
> **Kana Wazri**: Kana is a charming young student from a well-known family of merchants. She has a great love of magic but isn’t incredibly talented at it. Despite this, she is always seen studying and researching the magical arts, hoping to one day unlock her true potential.  
> 
> Kana Wazri：Kana 是一位来自知名商人家庭的迷人年轻学生。她非常喜欢魔法，但在这方面并不是非常有天赋。尽管如此，人们总是看到她学习和研究魔法艺术，希望有一天能释放她真正的潜力。
> 
> **Morgaine de Sombra**: Morgaine de Sombra was an aristocrat in the court of King Tragen before she found her calling in the dark arts. She runs a tight ship, instilling a sense of discipline among the students of the Academy.  
> 
> Morgaine de Sombra：Morgaine de Sombra 在发现她对黑暗艺术的召唤之前是 Tragen 国王宫廷中的贵族。她严于律己，在学院的学生中灌输纪律意识。  
> 
> Morgaine has a no-nonsense attitude when it comes to teaching and is feared by many of the students.  
> 
> Morgaine 在教学方面严肃认真，令许多学生望而却步。
> 
> **Fayza Silverwing**: Fayza is a beautiful priestess, wearing a dress of shimmering pearlescent feathers. She is gentle and kind, and her voice is melodious and soothing. She uses her singing voice to call down the blessings of the sky goddess, and to ward off evil.  
> 
> Fayza Silverwing：Fayza 是一位美丽的女祭司，穿着闪闪发光的珠光羽毛连衣裙。她温柔善良，声音悠扬舒缓。她用歌声祈求天女的庇佑，驱除邪恶。  
> 
> She also tends to the birds of the temple, providing them with a special place to dwell.  
> 
> 她还照料神殿的鸟类，为它们提供一个特殊的栖息地。
> 
> **Mathilde Velasquez**: Mathilde Velasquez was a cunning and ambitious woman in life, a talented emissary and negotiator. She was the right hand of an 18th century nobleman, and in death, she still roams the halls of the Mansion, planning out her strategies and scheming her way through the afterlife.  
> 
> 玛蒂尔德·委拉斯开兹：玛蒂尔德·委拉斯开兹在生活中是一位狡猾而雄心勃勃的女性，是一位才华横溢的使者和谈判者。她是 18 世纪贵族的得力助手，死后仍徘徊在大宅的大厅中，谋划着来世的计谋。

I had to nudge some of these into existence, but I’m still quite enamored with the variety it can produce, and believe GPT can do much better with further refinement.  

我不得不推动其中一些实现，但我仍然非常喜欢它可以产生的多样性，并且相信 GPT 可以通过进一步改进做得更好。

## What doesn’t work?  

什么不起作用？

I think these things could be fixed, but they aren’t yet, and if you implement something similar you are likely to encounter these same problems:  

我认为这些问题可以解决，但目前还没有，如果您实施类似的措施，您可能会遇到这些相同的问题：

### Reverting to normal/boring  

恢复正常/无聊

GPT is constantly normalizing things, including modernization. I want to make weird stuff, but also stylistically consistent stuff.  

GPT 正在不断规范化事物，包括现代化。我想制作奇怪的东西，但也想制作风格一致的东西。

As a general rule asking GPT for a list will help it be more creative. But when it gets on a roll producing normal/boring things, it will fill out the list with normal/boring things.  

作为一般规则，向 GPT 索取列表将有助于它更有创意。但是当它开始生产正常/无聊的东西时，它会用正常/无聊的东西填满列表。

Examples of this: “smart homes” (there is no time when I want “smart homes”), lots of references to tourism, “high-end restaurants”. How many cities should have art galleries? The primary attribute of a harbor area is not its historic cobbled streets and tourist amenities.  

这方面的例子：“智能家居”（我没有时间想要“智能家居”），大量提及旅游，“高端餐厅”。有多少城市应该有美术馆？海港区的主要特征不是其历史悠久的鹅卵石街道和旅游设施。  

These are all examples where GPT introduces a modern perspective.  

这些都是 GPT 引入现代视角的例子。

### GPT is desperately positive  

GPT 非常积极

Every building is grand. Every character is loyal and helpful. Every character is competent, respected, and wise.  

每一座建筑都气势恢宏。每个角色都是忠诚和乐于助人的。每个角色都称职、受人尊敬且睿智。

If you ask very explicitly for flaws you can get _some_. It’s very hard to get a truly despicable character. It’s hard to even get a realistically boring character, one who is not very competent or smart. It’s a fight, but armed with prompts we can still win the battle!  

如果您非常明确地要求缺陷，您可以得到一些。很难得到一个真正卑鄙的角色。甚至很难找到一个现实无聊的角色，一个不是很能干或不聪明的角色。这是一场战斗，但有了提示，我们仍然可以赢得这场战斗！

Some things that have helped:  

一些有帮助的事情：

1.  Asking for “exotic names”: this seems to result in a wide variety of ethnic names and other interesting combinations. For any one list GPT will often choose one ethnicity, such as Arabic names or Japanese names.  
    
    询问“异国情调的名字”：这似乎导致了各种各样的种族名字和其他有趣的组合。对于任何一个列表，GPT 通常会选择一个种族，例如阿拉伯名字或日本名字。
2.  “Colorful background/history”: this adds some playfulness  
    
    “丰富多彩的背景/历史”：这增加了一些趣味性
3.  Mentioning “culture”: this seems to fight against normalizing to modern American themes  
    
    提到“文化”：这似乎与现代美国主题的规范化作斗争
4.  Asking for “personality” or “character” in something: similar to “colorful”, this also tends to extend the descriptions  
    
    询问某事物的“个性”或“性格”：类似于“丰富多彩”，这也倾向于扩展描述
5.  Ask for “negative attributes”, “flaws”, “Achilles Heal”: descriptions will still be positive, but you’ll get some additional negative attributes  
    
    询问“负面属性”、“缺陷”、“致命弱点”：描述仍然是正面的，但您会得到一些额外的负面属性

### Fine detail is too much work  

精细的细节工作量太大

Once you generate a building and occupants you also have an opportunity to build rooms, to put furniture in those rooms, to put items in those rooms, and finally to define the room connections. This takes forever and is very boring!  

生成建筑物和居住者后，您还有机会建造房间，将家具放入这些房间，将物品放入这些房间，最后定义房间连接。这需要很长时间，而且非常无聊！

Many rooms have tables! Many buildings have a storage room! Many kitchens have utensils!  

许多房间都有桌子！许多建筑物都有储藏室！许多厨房都有餐具！

To generate real maps you do need these more concrete features. A building with no interior is no fun. An interior with no objects is no fun.  

要生成真实地图，您确实需要这些更具体的功能。没有内部装饰的建筑毫无乐趣可言。没有任何物体的室内装饰毫无乐趣可言。

If I were to approach this again I’d use this strategy:  

如果我再次处理这个问题，我会使用这个策略：

1.  Ask GPT for building “types” when creating a building. Maybe offer some initial types, but also invite GPT to make up new types.  
    
    在创建建筑物时向 GPT 询问建筑物“类型”。可能会提供一些初始类型，但也会邀请 GPT 来组成新的类型。
2.  For each type of building ask GPT to create an expansive list of rooms. Give the rooms types as well (hang-out, cooking, storage, etc). Ask for a range of room sizes.  
    
    对于每种类型的建筑，请 GPT 创建一个广泛的房间列表。还要给出房间类型（休闲、烹饪、储藏等）。询问一系列房间大小。
3.  For each type of room, or perhaps building-type/room-type combos, ask about furniture and items. Again ask for a long and expansive list.  
    
    对于每种类型的房间，或者建筑类型/房间类型的组合，询问家具和物品。再次要求一份长而广泛的清单。

At this point you could use a simple non-GPT algorithm to assign rooms to buildings. But you could also use abbreviated forms of these list and ask for GPT to fill out a building, like:  

此时，您可以使用简单的非 GPT 算法将房间分配给建筑物。但您也可以使用这些列表的缩写形式，并要求 GPT 填写建筑物，例如：

> The building is called “**\[Building Name**\]” and is described as: **\[Building Description\]** Fill out this list:  
> 
> 该建筑名为“\[建筑名称\]”，描述为：\[建筑描述\]填写此列表：
> 
> 1.  **\[Room type\]**: \[description\]  
>     
>     \[房型\]：\[描述\]
> 2.  **\[Furniture\]**: \[description\]  
>     
>     \[家具\]：\[描述\]

… basically letting GPT customize the building in one step, given a randomly chosen set of specific elements.  

…基本上让 GPT 一步自定义建筑物，给定一组随机选择的特定元素。

### Bad spatial reasoning  

糟糕的空间推理

GPT’s spatial reasoning isn’t very good (unsurprisingly). It’s OK at general sizes and heights of buildings, but when it has to relate spaces to each other (like placing rooms in buildings) it doesn’t understand.  

GPT 的空间推理不是很好（不出所料）。在建筑物的一般尺寸和高度上还可以，但是当它必须将空间彼此关联时（例如在建筑物中放置房间），它就无法理解。

This probably calls for traditional procedural generation techniques.  

这可能需要传统的程序生成技术。

It’s possible that GPT could help by coming up with constraints. For instance when generating rooms GPT is asked if the room is “public”, “private” (impolite to enter), “secure” (locked), or “secret”. These hints could provide constraints that keep the room layouts plausible.  

GPT 可能会通过提出约束来提供帮助。例如，在生成房间时，GPT 会询问房间是“公共”、“私人”（不礼貌进入）、“安全”（锁定）还是“秘密”。这些提示可以提供使房间布局合理的约束条件。

### Every detail of a prompt is a suggestion  

提示的每个细节都是一个建议

It’s very hard to tell GPT what is important and what is just framing. Some examples:  

很难告诉 GPT 什么是重要的，什么只是框架。一些例子：

1.  In an early prompt I used an example like `{name: "John Doe"}` for generating a person. GPT started coming up with names like “Jack Doe”, “John Smith” etc., _specifically_ choosing stereotypically generic names. I was able to improve it with a combination of asking for “interesting and culturally appropriate names” and replacing the example with `{name: "FirstName LastName"}`. (But now every so often GPT spits out FirstName LastName characters; you can’t win them all.)  
    
    在早期的提示中，我使用了一个像 `{name: "John Doe"}` 这样的例子来生成一个人。 GPT 开始提出诸如“Jack Doe”、“John Smith”等名称，特别是选择刻板的通用名称。我能够通过询问“有趣且符合文化的名称”并将示例替换为 `{name: "FirstName LastName"}` 的组合来改进它。 （但现在 GPT 偶尔会吐出 FirstName LastName 字符；您无法赢得所有字符。）
2.  Even a word like “building” is a suggestion. I wanted to make a floating pirate city made up of attached boats. GPT wasn’t sure whether to make things that matched my city description, or that matched what a “building” typically is, and it suggested a lot of boat-inappropriate structures.  
    
    甚至像“建造”这样的词也是一个建议。我想制作一个由附属船只组成的漂浮海盗城。 GPT 不确定是否要制作符合我的城市描述的东西，或者是否符合典型的“建筑物”，并且它建议了很多不适合船的结构。  
    
    Explicit prompt additions can help, but it would be even better if some of the core language could be substituted.  
    
    明确的提示添加会有所帮助，但如果可以替代某些核心语言，那就更好了。
3.  My beaver city also featured far too few dams and dens. Which is too bad because GPT is quite good at helping fill out these weird combinations so long as the prompt doesn’t fight with the premise.  
    
    我的海狸城的水坝和巢穴也太少了。这太糟糕了，因为只要提示不与前提相冲突，GPT 就非常擅长帮助填写这些奇怪的组合。

I can imagine having GPT rewrite some of the prompts as the city starts to be defined.  

我可以想象在开始定义城市时让 GPT 重写一些提示。

Another option is to have a glossary of terms where the author can adjust a few terms. I’ve specifically allowed the word “neighborhood” to be substituted (for quarter/district/etc), though the effect is minimal and GPT is happy to use different terms for neighborhoods without any special suggestions. Maybe other words are more impactful.  

另一种选择是有一个术语表，作者可以在其中调整一些术语。我特别允许用“neighborhood”这个词来代替（对于 quarter/district/etc），尽管效果很小，GPT 很乐意在没有任何特殊建议的情况下对社区使用不同的术语。也许其他词更有影响力。

### Constantly poking at the prompts is tiresome  

不断戳提示很烦人

Sometimes GPT just doesn’t come up with the right things at all. When that happens there’s a few ways to get GPT to change its output: adding or changing the overall context/backstory, making suggestions for a specific list, and asking for specific items.  

有时 GPT 根本没有想出正确的东西。当发生这种情况时，有几种方法可以让 GPT 更改其输出：添加或更改整体上下文/背景故事、针对特定列表提出建议以及询问特定项目。

Getting fun, interesting, and varied entities requires lots of nudging and iteration. But there’s not many ways to build up those notes. You can add the notes to the global context, and that can be a good idea, but it’s not a good iteration process.  

获得有趣、有趣和多样的实体需要大量的推动和迭代。但是建立这些笔记的方法并不多。您可以将注释添加到全局上下文中，这可能是个好主意，但这不是一个好的迭代过程。

I have a hunch there’s a way to experiment when creating specific buildings/etc, and then use GPT itself to percolate that up into more general prompt changes. But it’s only a hunch.  

我有一种预感，有一种方法可以在创建特定建筑物等时进行试验，然后使用 GPT 本身将其渗透到更一般的提示更改中。但这只是一种预感。

### Hallucinating metadata  

幻觉元数据

GPT will hallucinate metadata. This is both a problem and an opportunity.  

GPT 会使元数据产生幻觉。这既是问题也是机遇。

If you want to turn the output into structured data for another program you might find it annoying when it uses `{size: "6x10"}` instead of `{widthInMeters: 6, depthInMeters: 10}`.  

如果你想将输出转换为另一个程序的结构化数据，当它使用 `{size: "6x10"}` 而不是 `{widthInMeters: 6, depthInMeters: 10}` 时，你可能会发现它很烦人。

More often it’s actually interesting metadata that you might want to use more widely. For instance:  

更多时候，它实际上是您可能想要更广泛使用的有趣元数据。例如：

> **name:** The Cabal Of Witches  
> 
> 名称：女巫的阴谋  
> 
> **hierarchy:** Grand Witch -> Witch -> Apprentice -> Initiate  
> 
> 层级：大女巫->女巫->学徒->启蒙  
> 
> **initiates:** Keeper of the Dark Art, Spiritualists, Alchemists, Shaman  
> 
> 新手：黑魔法守护者、招魂师、炼金术士、萨满祭司
> 
> **name:** The Circle of Mages  
> 
> 名称：法师之环  
> 
> **hierarchy:** Grand Magus -> Magus -> Apprentice -> Initiate  
> 
> 等级：大魔导师->魔导师->学徒->入门  
> 
> **initiates:** Evokers, Enchanters, Abjurers, Illusionists  
> 
> 启蒙者：唤魔者、附魔者、防护者、幻术师
> 
> **name:** Abandoned Warehouse  
> 
> 名称：废弃仓库  
> 
> **dangers:** magically-altered creatures, unknown chemical pollutants, trapdoors and hidden passages  
> 
> 危险：魔法生物、未知化学污染物、活板门和隐藏通道

It seems odd to produce this metadata when presumably nothing is ready to consume it. But these attributes elicit responses from GPT, and do so more consistently than natural language requests.  

当大概没有准备好使用它时生成此元数据似乎很奇怪。但这些属性会引发 GPT 的响应，并且比自然语言请求更一致。

Adding this metadata gives **theme** and **variation**. The attribute is the theme, the value is the variation. This makes the set of things you’ve created more comprehensible, with a structure that makes it easier to appreciate the variety.  

添加此元数据可提供主题和变化。属性是主题，值是变体。这使您创建的一组事物更容易理解，其结构更容易欣赏多样性。

I don’t know how to expose this! Should we ask GPT to brainstorm attributes ahead of time? Invite it to hallucinate more widely and then the author picks the ones they like to become part of the prompts? Then… backfill?  

不知道怎么曝光！我们是否应该让 GPT 提前对属性进行头脑风暴？邀请它更广泛地产生幻觉，然后作者选择他们喜欢的那些成为提示的一部分？然后……回填？

### Corruption and fixation  

腐败和固定

Some of the magic of GPT is how it implicitly learns from context. Often it learns the wrong thing. This is particularly noticeable in _ChatGPT_, where it will often fixate on something despite or even because of corrections.  

GPT 的一些神奇之处在于它如何隐式地从上下文中学习。它经常学错东西。这在 _ChatGPT_ 中尤为明显，它经常会不顾或什至因为更正而注视某些东西。

This tool is much more explicit about context and doesn’t have anything that is specifically a chat. Still…  

该工具对上下文更加明确，并且没有任何专门用于聊天的内容。仍然…

1.  You’ll think the content of the backstory is all that matters, but the tone also informs GPT. Because GPT probably created that backstory this doubles down on its tone. (Is this feedback part of its tedious positivity?)  
    
    您会认为背景故事的内容才是最重要的，但基调也会影响 GPT。因为 GPT 可能创造了那个背景故事，所以它的基调加倍了。 （这种反馈是其乏味积极性的一部分吗？）
2.  When you ask for “more” of a list it will feed the existing list into the prompt… this helps it create new and distinct items, and sometimes helpfully refers to previous items (like creating interesting relations between people), but if you didn’t like the suggestions before you are unlikely to like the new ones.  
    
    当您要求“更多”列表时，它会将现有列表提供给提示……这有助于它创建新的和不同的项目，有时还有助于引用以前的项目（例如在人与人之间建立有趣的关系），但如果您没有在您不太可能喜欢新建议之前先不喜欢这些建议。  
    
    It copies tone, but also description length, metadata, name ethnicities, and architectural styles.  
    
    它复制语气，但也复制描述长度、元数据、姓名种族和建筑风格。

### GPT is expensive  

GPT 很贵

[Talamora](https://llm.ianbicking.org/citymaker/?name=builtin_talamora) cost me about $6 in GPT API costs to generate. That’s a lot!  

Talamora 花费了我大约 6 美元的 GPT API 成本来生成。好多啊！

Because I’m paying for API costs directly, and because the costs increase only when I use the tool, there’s a natural balance: if I’m not having fun and enjoying the output, I won’t generate more costs.  

因为我直接支付 API 成本，而且因为只有当我使用该工具时成本才会增加，所以有一个自然的平衡：如果我没有乐趣和享受输出，我就不会产生更多的成本。  

By the time I made Talamora I had enough improvements that I actually enjoyed the process and my enthusiasm wasn’t just built on dreams (which is the fuel for the first phase of any project).  

到我制作 Talamora 时，我已经有了足够的改进，我真的很享受这个过程，我的热情不仅仅建立在梦想之上（这是任何项目第一阶段的燃料）。

The cost means I’m not motivated to automate any of the authoring. Perhaps because the _output_ has little intrinsic value, so reducing the author’s involvement is a net loss.  

成本意味着我没有动力去自动化任何创作。可能是因为产出没有什么内在价值，所以减少作者的参与是一种净损失。

It also means I can’t easily make this available to other people. People are providing these services with “credit” models and subscriptions but the underlying costs are enough that it’s hard to imagine that working. So for now you can [try this](https://llm.ianbicking.org/) with your own API key, paying _OpenAI_ directly, and managing your own budget.  

这也意味着我无法轻易将其提供给其他人。人们正在通过“信用”模式和订阅来提供这些服务，但潜在的成本足以让人很难想象它会奏效。因此，现在您可以使用自己的 API 密钥进行尝试，直接向 _OpenAI_ 付款并管理自己的预算。

There are some ways that this could be made more efficient:  

有一些方法可以提高效率：

1.  Use other models (e.g., `text-ada-001`) for some tasks. Though few of the tasks feel amenable to the cheaper models.  
    
    对某些任务使用其他模型（例如， `text-ada-001` ）。尽管很少有任务适合便宜的型号。
2.  Get suggestions right the first time. For Talamora in particular I used lots of prompt adjustments to get results I was happy with. Overall prompt improvements would have avoided many of those.  
    
    第一时间获得正确的建议。特别是对于 Talamora，我使用了大量的即时调整来获得令我满意的结果。整体及时改进可以避免其中的许多问题。
3.  Reduce context on some queries. The base context of most prompts includes the whole city backstory, neighborhood, etc. That’s not necessary for every query. Perhaps some of the context is only needed for some types of queries.  
    
    减少某些查询的上下文。大多数提示的基本上下文包括整个城市的背景故事、社区等。这并不是每个查询都需要的。也许只有某些类型的查询才需要某些上下文。
4.  Get more out of every query. If there’s multiple queries then the context is repeated for each. This saves money when some queries produce dead ends, such as a building that the author doesn’t like and doesn’t want to expand.  
    
    从每个查询中获取更多信息。如果有多个查询，那么每个查询都会重复上下文。当某些查询产生死胡同时，例如作者不喜欢且不想扩建的建筑物，这可以节省资金。  
    
    But adding a little metadata to each item is usually a good investment.  
    
    但为每个项目添加一点元数据通常是一项不错的投资。
5.  Improve the quality. The more generated stuff you keep, the less queries you need to achieve some degree of success or satisfaction.  
    
    提高质量。您保留的生成的东西越多，获得某种程度的成功或满足所需的查询就越少。  
    
    Investing more time in quality parent context, like backstory and neighborhoods, will pay off with the both larger and more expensive leaf nodes like buildings.  
    
    将更多时间投入到高质量的父上下文（如背景故事和社区）中，将获得更大、更昂贵的叶节点（如建筑物）的回报。
6.  Summarize to reduce context. Right now this concatenate the context information. It might save some space by rephrasing that context, both combining the text in a more compact way, and selecting the salient details for generating specific kinds of items.  
    
    总结以减少上下文。现在，这连接了上下文信息。它可以通过重新措辞该上下文来节省一些空间，以更紧凑的方式组合文本，并选择显着的细节来生成特定类型的项目。
7.  Estimating list size for choices. If you get a list of 7 items but then you ask for the list to be extended that is _much_ more expensive than asking for 14 items up front. Similarly if you want 1 item then it’s cheaper just to make one item and not a long list.  
    
    估计选项的列表大小。如果您得到一份包含 7 项的清单，但随后要求扩展该清单，这比预先要求 14 项要昂贵得多。同样，如果您想要 1 件物品，那么只制作一件物品而不是长长的清单会更便宜。  
    
    It’s possible that the parent could estimate the list size for the child, or that we could just make better general estimates and hardcode those list sizes into the prompts.  
    
    父母可以为孩子估计列表大小，或者我们可以做出更好的一般估计并将这些列表大小硬编码到提示中。

## Image generation  

图像生成

All these words are interesting but some images would also be interesting. Right now there are too many considerations to do a detailed comparison of all of them, and things are changing fast, so I’ll just give a scattering of thoughts.  

所有这些词都很有趣，但有些图像也很有趣。现在有太多的考虑因素无法对所有这些进行详细比较，而且事情变化很快，所以我只是给出一些零散的想法。

### The generators  

发电机

I have a hard time understanding the array of AI image generators, but I’ve used these three enough to have opinions:  

我很难理解 AI 图像生成器的阵列，但我已经使用了这三个足够有意见：

1.  [Stable Diffusion  
    
    稳定扩散](https://replicate.com/stability-ai/stable-diffusion)
2.  [Dall-E 2  
    
    达尔-E 2](https://openai.com/dall-e-2/)
3.  [_Midjourney  
    
    中途_](https://www.midjourney.com/)

The first two have an API. That means I can integrate them directly into the tool, which has a real and significant workflow benefit. _Midjourney_ has absolute no affordances to integrate it into another application, but it creates great images. Generally I’ve found _Stable Diffusion_ to be unusable because it won’t create sensible compositions. There’s probably some flavor of _Stable Diffusion_ that would work better, but there’s just too much going on! Dall-E is OK but it doesn’t have a natural sense of style and the resulting images… just aren’t very fun.  

前两个有一个 API。这意味着我可以将它们直接集成到工具中，这对工作流程具有真正且重要的好处。 _Midjourney_ 绝对无法将其集成到另一个应用程序中，但它可以创建出色的图像。一般来说，我发现 _Stable Diffusion_ 无法使用，因为它不会创建合理的构图。可能有一些 _Stable Diffusion_ 的味道会更好，但发生的事情太多了！ Dall-E 还可以，但它没有自然的风格感和由此产生的图像……只是不是很有趣。

### Generating a prompt  

生成提示

The easy way is just to give the text directly to an image generator and let it imagine things as it will. There’s a danger it will have insufficient context, like being unaware of the era or environment.  

简单的方法就是将文本直接提供给图像生成器，让它随心所欲地想象事物。它存在上下文不足的危险，例如不了解时代或环境。

Let’s take a building to see. The base text:  

我们拿一栋楼来看看。基本文本：

> **Jubilous Forge:** A bustling forge bustling with laughter and the smell of hot metal forges and alchemical potions, with ornate decorations on its two-story walls.  
> 
> Jubilous Forge：一个熙熙攘攘的熔炉，充满欢声笑语，散发着热金属熔炉和炼金药水的气味，两层楼的墙壁上装饰着华丽的装饰。

It’s already a pretty visual description.  

这已经是一个非常直观的描述。

Here’s a quick prompt to expand the visuals:  

这是扩展视觉效果的快速提示：

> Given the building: Jubilous Forge: A bustling forge bustling with laughter and the smell of hot metal forges and alchemical potions, with ornate decorations on its two-story walls.  
> 
> 给定建筑： Jubilous Forge：一个熙熙攘攘的锻造厂，充满欢声笑语，散发着热金属锻造和炼金药水的气味，两层楼的墙壁上装饰着华丽的装饰。
> 
> In 2-3 sentences make a detailed visual description of the exterior of the building:  
> 
> 用 2-3 句话对建筑物的外观进行详细的视觉描述：
> 
> The Jubilous Forge looks like  
> 
> Jubilous Forge 看起来像

And it completes with:  

它完成了：

> a large, imposing structure, with walls of gray stone reaching two stories high. The windows are framed by intricate patterns of wrought iron and the door is adorned with a bright, golden door knocker.  
> 
> 一座宏伟的大建筑，灰色石墙高达两层楼。窗户镶有复杂的锻铁图案，门上装饰着明亮的金色门环。  
> 
> The outdoor walls are decorated with vibrant murals of blacksmiths and alchemists at work, lit up by the warm glow of nearby forge fires.  
> 
> 室外墙壁上装饰着充满活力的铁匠和炼金术士工作壁画，被附近锻造炉火的温暖光芒照亮。

This seems better! Unfortunately it is not… the use of the term “pillar” makes both Dall-E and _Midjourney_ think of banks.  

这似乎更好！不幸的是，它不是……“支柱”一词的使用让 Dall-E 和 _Midjourney_ 都想到了银行。

Here’s a generated image from the simple/unmodified building description:  

这是从简单/未修改的建筑描述中生成的图像：

![Midjourney - Isometric rendering of single building on a white background: Jubilous Forge: A bustling forge bustling with laughter and the smell of hot metal forges and alchemical potions, with ornate decorations on its two-story walls.](jubilant-midjourney-simple-1.png)

And here it is with the modified description:  

这是修改后的描述：

![Midjourney - Isometric art of a single building on a white background: The Jubilous Forge looks like a large, imposing structure, with walls of gray stone reaching two stories high. The windows are framed by intricate patterns of wrought iron and the door is adorned with a bright, golden door knocker. The outdoor walls are decorated with vibrant murals of blacksmiths and alchemists at work, lit up by the warm glow of nearby forge fires.](jubilant-midjourney-prompted-1.png)

The first prompt, which leaves more latitude to _Midjourney_, works better.  

第一个提示让 _Midjourney_ 有更多自由度，效果更好。

Oh the other hand, in a jungle city there is a building:  

哦，另一方面，在丛林城市中有一栋建筑：

> **The Zigzag Tower:** A tall and slender tower with a zigzag facade, The Zigzag Tower is a temple dedicated to the reverence of nature.  
> 
> Zigzag Tower：Zigzag Tower 是一座高大细长的塔，正面呈锯齿形，是一座崇敬自然的寺庙。

The _Midjourney_ results are all bland modern towers:  

_Midjourney_ 结果都是乏味的现代塔楼：

![Midjourney - Isometric rendering of a single building on a white background: The Zigzag Tower: A tall and slender tower with a zigzag facade, The Zigzag Tower is a temple dedicated to the reverence of nature.](zigzag-midjourney-simple-1.png)

When we include the city description and ask GPT to make a visual description we get:  

当我们包含城市描述并要求 GPT 进行视觉描述时，我们得到：

> The Zigzag Tower looks like a towering pillar of grandeur that sharply cuts into the sky, with its unique zigzag facade. Its yellow-brown hues blend with its natural surroundings, giving off a sense of harmony with the environment.  
> 
> 曲折塔的曲折立面别具一格，犹如一根直插云霄的巍峨巨柱。黄褐色的色调与周围的自然环境融为一体，给人一种与环境和谐相处的感觉。  
> 
> It is adorned with intricate carvings and sculptures of animals and plants that make it seem to come alive in its own right.  
> 
> 它装饰着错综复杂的动物和植物雕刻和雕塑，使它看起来像是活了过来。

The description doesn’t look that different but the effect is dramatic:  

描述看起来并没有什么不同，但效果是戏剧性的：

![Midjourney - Isometric rendering of a single building on a white background: The Zigzag Tower looks like a towering pillar of grandeur that sharply cuts into the sky, with its unique zigzag facade. Its yellow-brown hues blend with its natural surroundings, giving off a sense of harmony with the environment. It is adorned with intricate carvings and sculptures of animals and plants that make it seem to come alive in its own right.](zigzag-midjourney-prompted-1.png)

### Describing the style  

描述风格

If you ask for an image of a building that can mean all kinds of things. For instance this is what _Stable Diffusion_ gives for the Jubilant Forge:  

如果您要的是建筑物的图像，那可能意味着各种各样的事情。例如，这是 _Stable Diffusion_ 为 Jubilant Forge 提供的：

![jumbled old style drawing of a building](jubilant-sd-no-prefix.png)

Interesting! But not the format I intended. Here’s some additions to the prompt that help:  

有趣的！但不是我想要的格式。以下是对提示的一些补充：

1.  “Isometric” is a very strong word and will align the perspective and set the camera angle.  
    
    “等距”是一个非常强大的词，它将调整视角并设置相机角度。
2.  _Midjourney_ will happily make a stand-alone building. Dall-E often zooms too far in or gets confused, but it comes close. _Stable Diffusion_ feels hopeless! I’d be curious if _Stable Diffusion_ and Dall-E could be asked to infill a template photo; i.e., create a isometric-shaped-building-size-hole so it has to work in those constraints.  
    
    _Midjourney_会很乐意做一个独立的建筑。 Dall-E 经常放大得太远或感到困惑，但它很接近。稳定扩散感觉没希望了！我很好奇是否可以要求 _Stable Diffusion_ 和 Dall-E 填充模板照片；即，创建一个等轴测形状的建筑物大小的孔，以便它必须在这些约束条件下工作。
3.  “White background” suggests the building should be rendered without an environmental context.  
    
    “白色背景”表明建筑物应该在没有环境背景的情况下呈现。

This prompt seems decent for both _Midjourney_ and Dall-E: **Isometric rendering of single building on a white background**  

这个提示对于 _Midjourney_ 和 Dall-E 来说似乎都不错：白色背景上单个建筑物的等距渲染

## Conclusion  

结论

Many of the lessons from this experiment could be applied to other top-down authoring environments:  

这个实验的许多经验教训可以应用于其他自上而下的创作环境：

1.  Establishing hierarchical context.  
    
    建立层次结构上下文。
2.  Using GPT to offer suggestions at each level with author selection.  
    
    使用 GPT 在每个级别提供作者选择的建议。
3.  Using a combination of natural language and structured output.  
    
    使用自然语言和结构化输出的组合。
4.  Include points of intervention to “speak to” GPT.  
    
    包括与 GPT“对话”的干预点。
5.  Be aware of all the language in a prompt; it all matters.  
    
    注意提示中的所有语言；这一切都很重要。
6.  Use the tool a lot! The first couple things feel magical, but the magic will wear off after you’ve made a couple dozen things without special effort.  
    
    大量使用该工具！最初的几件事情感觉很神奇，但当你不费吹灰之力做了几十件事情后，这种魔力就会消失。

If you want to try this yourself check out [llm.ianbicking.org](https://llm.ianbicking.org/citymaker/), or [check out GitHub](https://github.com/ianb/llm-garden). If you are curious about the exact prompts look for `prompt =` in [citymakerdb.js](https://ianbicking.org/blog/2023/02/104537541227697934010/content_cache/d34/d33/637). Note that this is a personal project, it’s monolithic and only organized well enough for me to understand.  

如果您想自己尝试，请查看 llm.ianbicking.org，或查看 GitHub。如果您对确切的提示感到好奇，请在 citymakerdb.js 中查找 `prompt =` 。请注意，这是一个个人项目，它是整体的，并且组织得很好，足以让我理解。

Similarly: when using the site be warned I have not built it carefully for other people to use, stuff will be weird, errors will appear only in the JS Console, there are no promises. And you’ll have to bring your own GPT API key!  

类似地：当使用该站点时被警告我没有为其他人使用而仔细构建它，东西会很奇怪，错误只会出现在 JS 控制台中，没有任何承诺。而且您必须携带自己的 GPT APIkey！

Comments welcome on [Mastodon](https://hachyderm.io/@ianbicking/109937462683423813), [Twitter](https://twitter.com/ianbicking/status/1630231712499376130), [Hacker News](https://news.ycombinator.com/item?id=34967515).  

欢迎在 Mastodon、Twitter、Hacker News 上发表评论。

If you’ve gotten this far I will also throw in here that I ([Ian](https://ianbicking.org/)) am looking for a job, and maybe the best job for me is one that I don’t yet know exists. I’m particularly interested in the area of large language models, [natural language interfaces](https://ianbicking.org/blog/2023/01/thoughts-on-voice-interfaces-2-llms.html), new user interactions built on LLMs (especially their abilities to understand us in new ways). I’m excited about education, aiding in executive function, and human-centered interactions. [Let me know if you have ideas](mailto:ianbicking@gmail.com), [or hit me up on LinkedIn](https://www.linkedin.com/in/ianbicking/) I would appreciate it!  

如果你已经走到这一步，我也会在这里说我（伊恩）正在找工作，也许对我来说最好的工作是我还不知道的工作。我对大型语言模型、自然语言界面、基于 LLM 的新用户交互领域特别感兴趣（尤其是他们以新方式理解我们的能力）。我对教育、协助执行功能和以人为本的互动感到兴奋。如果您有任何想法，请告诉我，或者在 LinkedIn 上联系我，我将不胜感激！
