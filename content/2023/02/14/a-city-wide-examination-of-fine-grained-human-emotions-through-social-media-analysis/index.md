---
title: "通过社交媒体分析对人类情感的细粒度"
date: 2023-02-14T21:41:11+08:00
updated: 2023-02-14T21:41:11+08:00
taxonomies:
  tags: []
extra:
  source: https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749
  hostname: journals.plos.org
  author: Panote Siriaraya   , 帕诺特·西里拉亚，
  original_title: "A city-wide examination of fine-grained human emotions through social media analysis"
  original_lang: en
---

Open Access  

开放获取

Peer-reviewed  

同行评审

Research Article  

研究文章

-   Yihong Zhang,  
    
    张一红
-   Yukiko Kawai,  
    
    河井由纪子
-   Peter Jeszenszky,  
    
    彼得·耶曾斯基，
-   Adam Jatowt  
    
    亚当·贾托

## A city-wide examination of fine-grained human emotions through social media analysis  

通过社交媒体分析对人类情感的细粒度全市检查

-   Panote Siriaraya,   
    
    帕诺特·西里拉亚，
-   Yihong Zhang,   
    
    张一红
-   Yukiko Kawai,   
    
    河井由纪子
-   Peter Jeszenszky,   
    
    彼得·耶曾斯基，
-   Adam Jatowt  
    
    亚当·贾托

![PLOS](logo-plos.png)

x  

x

-   Published: February 1, 2023  
    
    发布日期：2023年2月1日
-   [https://doi.org/10.1371/journal.pone.0279749](https://doi.org/10.1371/journal.pone.0279749)

-   [Abstract  
    
    摘要](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#abstract0)
-   [Introduction  
    
    导言](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec001)
-   [Related research  
    
    相关研究](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec002)
-   [Data collection  
    
    数据收集](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec003)
-   [Detecting basic emotions  
    
    检测基本情绪](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec006)
-   [Temporal examination of emotions  
    
    情绪的时间检查](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec007)
-   [Contextualising emotions by places  
    
    按地点将情绪置于情境中](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec010)
-   [Conclusions & future work  
    
    结论和今后的工作](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec013)
-   [Supporting information  
    
    辅助资料](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#sec014)
-   [References  
    
    参考文献](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#references)

-   [Figures  
    
    图](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#)

## Abstract  

摘要

The proliferation of Social Media and Open Web data has provided researchers with a unique opportunity to better understand human behavior at different levels.  

社交媒体和开放网络数据的激增为研究人员提供了一个独特的机会，可以更好地了解不同层面的人类行为。  

In this paper, we show how data from Open Street Map and Twitter could be analyzed and used to portray detailed Human Emotions at a city wide level in two cities, San Francisco and London.  

在本文中，我们展示了如何分析来自开放街道地图和Twitter的数据，并将其用于描绘旧金山和伦敦这两个城市的城市范围内的详细人类情感。  

Neural Network classifiers for fine-grained emotions were developed, tested and used to detect emotions from tweets in the two cites. The detected emotions were then matched to key locations extracted from Open Street Map.  

针对细粒度情绪的神经网络分类器被开发、测试并用于检测这两个城市的推文中的情绪。然后将检测到的情绪与从开放街道地图中提取的关键位置进行匹配。  

Through an analysis of the resulting data set, we highlight the effect different days, locations and POI neighborhoods have on the expression of human emotions in the cities.  

通过对结果数据集的分析，我们强调了不同日期、地点和POI邻域对城市中人类情感表达的影响。

## Figures  

图

**Citation:** Siriaraya P, Zhang Y, Kawai Y, Jeszenszky P, Jatowt A (2023) A city-wide examination of fine-grained human emotions through social media analysis. PLoS ONE 18(2): e0279749. https://doi.org/10.1371/journal.pone.0279749

**Editor:** Jichang Zhao, Beihang University, CHINA  

编辑：赵继昌，北京航空航天大学

**Received:** July 11, 2022; **Accepted:** December 14, 2022; **Published:** February 1, 2023  

收稿日期：2022年7月11日;受理日期：二〇二二年十二月十四日;发布日期：2023年2月1日

**Copyright:** © 2023 Siriaraya et al. This is an open access article distributed under the terms of the [Creative Commons Attribution License](http://creativecommons.org/licenses/by/4.0/), which permits unrestricted use, distribution, and reproduction in any medium, provided the original author and source are credited.  

版权所有：© 2023 Siriaraya et al.这是一篇根据知识共享署名许可协议的条款发布的开放获取文章，该协议允许在任何媒体上不受限制地使用、分发和复制，前提是原作者和来源得到认可。

**Data Availability:** The following information is provided to allow researchers to replicate the results in this study: The raw list of POI data which we obtained in the Greater London area and San Francisco.  

数据可用性：提供以下信息，以允许研究人员复制本研究的结果：我们在大伦敦地区和旧金山获得的POI数据的原始列表。  

The list of each POI location in the Greater London area and San Francisco with information about the averaged emotions of the tweets that were matched with them. The list of days with the average of different emotions in Greater London and San Francisco.  

大伦敦地区和旧金山的每个POI位置的列表，以及与它们匹配的推文的平均情绪信息。大伦敦和旧金山不同情绪平均值的日子列表。  

The list of tweets with the number of POI categories in the nearby vicinity that display each emotion. For the raw tweet data (e.g.  

显示每种情绪的附近区域中具有POI类别数量的推文列表。对于原始推文数据（例如  

, tweet content), due to the Twitter terms of service, we could not provide the exact data used in this study as Twitter forbids the transfer of data between third parties.  

，推文内容），由于推特的服务条款，我们无法提供本研究中使用的确切数据，因为推特禁止在第三方之间传输数据。  

If required, we are able to provide the Tweet IDs used in this study that would allow those who are interested to collect data from Twitter using their API. A link to access the dataset in the figshare repository is provided here: [10.6084/m9.figshare.21408204](https://journals.plos.org/plosone/dx.doi.org/10.6084/m9.figshare.21408204).  

如果需要，我们可以提供本研究中使用的推文ID，以便感兴趣的用户使用其API从Twitter收集数据。此处提供了访问figshare存储库中数据集的链接：10.6084/平方米。图号：21408204。

**Funding:** This work was partially supported by the Japanese Ministry of Internal Affairs and Communication, Strategic Information and Communications R&D Promotion Program (MIC/SCOPE) #171507010 ([https://www.soumu.go.jp/main\_sosiki/joho\_tsusin/scope/](https://www.soumu.go.jp/main_sosiki/joho_tsusin/scope/)) and the Japan society for the promotion of science KAKENHI Grant Numbers 16H01722, 17H01822, 22K12274 and 22K19837 ([https://www.jsps.go.jp/english/index.html](https://www.jsps.go.jp/english/index.html)). Apart from these, there was no additional external funding received for this study.  

资金来源：这项工作得到了日本总务省战略信息和通信研发促进计划（MIC/SCOPE）#171507010（ [https://www.soumu.go.jp/main\_sosiki/joho\_tsusin/scope/](https://www.soumu.go.jp/main_sosiki/joho_tsusin/scope/) ）和日本科学促进协会KAKENHI赠款编号16H01722、17H01822、22K12274和22K19837（ [https://www.jsps.go.jp/english/index.html](https://www.jsps.go.jp/english/index.html) ）的部分支持。除此之外，本研究未收到额外的外部资金。

**Competing interests:** The authors have declared that no competing interests exist.  

利益冲突：提交人宣称不存在利益冲突。

## Introduction  

导言

The pervasive growth of social media has resulted in a large amount of digital information becoming available in the past decade.  

在过去十年中，社交媒体的普遍增长导致大量数字信息变得可用。  

As a result, it has become possible to obtain near real-time information about the opinions, activities and behaviors of various population groups by automatically analyzing data from public social network services such as Twitter and Flickr \[[1](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref001)\]. This trend has allowed researchers to better understand patterns of human behavior at an individualized level, but yet in a macroscopic scale. Notable examples include prior studies which have used social media data to highlight emerging topics and trends \[[2](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref002)\] or to provide an overview of the mobility patterns for an entire population \[[3](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref003), [4](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref004)\].  

因此，通过自动分析来自公共社交网络服务（如Twitter和Flickr）的数据，可以获得关于各种人群的观点、活动和行为的近实时信息\[ 1 \]。这一趋势使研究人员能够更好地了解人类行为模式在个性化的水平，但仍然在宏观尺度。值得注意的例子包括使用社交媒体数据突出新兴主题和趋势\[ 2 \]或提供整个人群的移动模式概述\[ 3，4 \]的先前研究。

In recent studies, researchers have begun to investigate whether data from social media sources could also be useful in portraying the implicit aspects and characteristics of users (such as their emotions) in addition to their explicit behaviours (such as their activities and movement patterns).  

在最近的研究中，研究人员已开始调查社交媒体来源的数据是否也可用于描绘用户的隐性方面和特征（如情绪）以及其显性行为（如活动和移动模式）。  

Notable examples include the “pulse of the nation” project, which provides a broad visualization of happiness across the USA \[[5](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref005)\]. In most of these studies however, emotions were often matched to a country, state or city level spatial resolution, thus limiting the scope of possible research questions which could be addressed through the data set \[[6](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref006), [7](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref007)\]. For example, while it is possible to carry out large scale analysis to correlate the overall emotional status of the community population with measures related to well-being (such as in \[[8](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref008)\]), it is difficult to investigate relations at a more detailed spatial level, such as the role different recreational facilities (bars, sport venues, temples etc.) might have on mood and emotion in a specific city.  

著名的例子包括“国家脉搏”项目，该项目提供了美国各地幸福感的广泛可视化\[ 5 \]。然而，在大多数这些研究中，情绪通常与国家、州或城市级别的空间分辨率相匹配，从而限制了可通过数据集解决的可能研究问题的范围\[ 6，7 \]。例如，虽然可以进行大规模分析，将社区人口的整体情绪状态与幸福感相关指标相关联（如\[ 8 \]），但很难在更详细的空间水平上调查关系，如不同娱乐设施（酒吧、体育场馆、寺庙等）的作用。在特定的城市可能会对情绪和情感产生影响。  

In addition, earlier works also tended to focus primarily on positive or negative sentiment measures \[[9](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref009)\] and not on specific emotions.  

此外，早期的研究也倾向于主要关注积极或消极的情绪测量\[ 9 \]，而不是特定的情绪。

In this study, we expand upon the previous research domain and utilize data from the social media platform Twitter to analyze fine-grained human emotions at a city wide level.  

在本研究中，我们扩展了先前的研究领域，并利用社交媒体平台Twitter的数据来分析城市范围内的细粒度人类情绪。  

Different approaches for automatically detecting fine-grained human emotions from the social media platform Twitter were examined and evaluated.  

对从社交媒体平台Twitter自动检测细粒度人类情感的不同方法进行了检查和评估。  

Afterwards, Neural Network classifiers were used to identify emotions from geotagged tweets in two cities, San Francisco and London and data from Open Street Map data was used to spatially contextualize the social media information. Finally, we use the resulting data set to (1) _Visualize the temporal characteristics of emotions within the two cities_ and (2) _Analyze the influence different place types have on the expression of emotions_. Overall, the aim of our paper is to show how it is possible to study the characteristics of fine-grained emotions at both a spatial and temporal level throughout the whole city, using current technology and publicly available data sets.  

之后，神经网络分类器被用于识别弗朗西斯科和伦敦这两个城市的地理标记推文中的情绪，来自开放街道地图数据的数据被用于将社交媒体信息进行空间上下文化。最后，我们使用所得的数据集（1）可视化两个城市内情绪的时间特征和（2）分析不同场所类型对情绪表达的影响。总的来说，我们论文的目的是展示如何利用现有技术和公开可用的数据集，在整个城市的空间和时间水平上研究细粒度情绪的特征。  

Our research is unique in that whereas prior studies tend to focus on analyzing sentiment polarity or a single emotion such as happiness, we examined seven different fine-grained emotions (Anger, Anticipation, Disgust, Fear, Trust, Joy and Sadness) at a city-wide level based on large-scale data analysis from social media.  

我们的研究是独特的，因为之前的研究往往侧重于分析情绪极性或单一情绪，如幸福，我们检查了七个不同的细粒度情绪（愤怒，期待，厌恶，恐惧，信任，喜悦和悲伤）在城市范围内的大规模数据分析的基础上，从社交媒体。  

In addition, we also examine how these emotions are influenced at a more detailed spatial level (i.e. at a Point of interest level), as opposed to previous studies which tend to analyze data at coarse geographic levels (at the state, city or country level etc.).  

此外，我们还在更详细的空间水平（即兴趣点水平）上考察了这些情绪是如何受到影响的，这与以往倾向于在粗略的地理水平（州、城市或国家水平等）上分析数据的研究相反。  

The results from this study would serve as a preliminary basis for future research looking to investigate the occurrence of such emotions through large scale social media analysis.  

这项研究的结果将作为未来研究的初步基础，通过大规模的社会媒体分析来调查这种情绪的发生。

This paper is structured as follows. First, we describe how spatial and social media data from Open Street Map and Twitter was collected and processed for San Francisco and London.  

本文的结构如下。首先，我们描述了如何收集和处理旧金山和伦敦的开放街道地图和Twitter的空间和社交媒体数据。  

Next, we highlight the results of an experiment study carried out to evaluate different classification algorithms which could be used to detect user emotions from geotagged tweets, the best performing ones were then used to analyze the tweets collected in this study.  

接下来，我们强调了一项实验研究的结果，该研究旨在评估可用于从地理标记的推文中检测用户情绪的不同分类算法，然后使用性能最好的算法来分析本研究中收集的推文。  

Afterwards, we analyzed the characteristics of the daily level of emotions exhibited by the population in the two cities.  

然后，我们分析了两个城市的居民日常情绪水平的特点。  

Finally, we investigate the potential effect different place types have on each of the seven user emotions, first by examining the degree of emotions exhibited by users at different locations and then examining how the display of emotions is influenced by the type of locations at different vicinity levels.  

最后，我们调查了不同地点类型对七种用户情绪中每一种的潜在影响，首先通过检查用户在不同地点表现出的情绪程度，然后检查情绪的表现如何受到不同邻近水平的地点类型的影响。

## Related research  

相关研究

The use of social media data to analyze and provide a macro scale display of human emotions has been a popular topic of research in past studies. Earlier works tended to focus on broad sentiment measures such as positive and negative emotions.  

利用社交媒体数据分析并提供人类情绪的宏观尺度展示一直是过去研究的热门话题。早期的研究倾向于关注广泛的情绪测量，如积极和消极的情绪。  

In such studies, sentiment analysis is generally carried out on geotagged tweets to provide an overview about the overall mood of the population at different regions or cities \[[10](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref010)\]. Other studies focused on identifying user sentiment during or after a particular event (such as a pandemic \[[11](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref011), [12](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref012)\] or terrorism event \[[13](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref013)\]) or analyzed user sentiment at different geographical areas with the aim of investigating the mobility patterns of people within a city \[[14](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref014)\].  

在此类研究中，通常对地理标记的推文进行情感分析，以提供不同地区或城市人口的总体情绪概述\[ 10 \]。其他研究集中于在特定事件（诸如流行病\[ 11，12 \]或恐怖主义事件\[ 13 \]）期间或之后识别用户情绪，或分析不同地理区域的用户情绪，目的在于调查城市内的人的移动模式\[ 14 \]。  

In a number of these studies, data about the sentiment of the tweets themselves were correlated with various metrics affecting urban living (such as job opportunities and access to public transportation) to provide insight into the effect these measures have on the happiness of the population \[[15](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref015)\]. In a more applied setting, researchers have also incorporated sentiment analysis data from geotagged social media as part of a larger system or predictive model to recommend safe walking routes \[[16](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref016)\] or improve the accuracy of crime prediction \[[17](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref017)\].

More recent studies have begun to explore the expression of detailed emotions (such as fear and anger) through geotagged tweets.  

For instance, in the “We feel project”, researchers highlighted how people in different regions and countries exhibited the five primary emotions using geotagged tweets \[[18](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref018)\]. In another example, geotagged tweets were classified based on emotional dimensions such as pleasantness and dominance, the results of which were visualized over the world map to show emotional trends across different countries \[[19](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref019)\]. Other studies used geotagged tweets to analyze the emotions of people (fear, sadness, sympathy) in response to particular events such as the London Westminster and London Bridge attacks \[[13](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref013)\] and the Paris attacks (anger and sadness) \[[20](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref020)\].  

例如，在“我们感受项目”中，研究人员强调了不同地区和国家的人们如何使用地理标记的推文来表现五种主要情绪\[ 18 \]。在另一个例子中，地理标记的推文基于情感维度（如愉悦度和支配力）进行分类，其结果在世界地图上可视化，以显示不同国家的情感趋势\[ 19 \]。其他研究使用地理标记推文来分析人们对特定事件的反应（恐惧、悲伤、同情），如伦敦威斯敏斯特和伦敦桥袭击\[ 13 \]和巴黎袭击（愤怒和悲伤）\[ 20 \]。

These earlier studies which were discussed had several limitations however.  

然而，所讨论的这些早期研究有几个局限性。  

First, sentiment mapping is generally carried out at a country or state wide level and tends to focus on polarized sentiment measures (varying degrees of positive and negative emotions) and not on specific emotions (such as Anger, Joy and Disgust).  

首先，情绪映射通常在国家或州范围内进行，并且倾向于关注两极化的情绪测量（不同程度的积极和消极情绪），而不是特定情绪（例如愤怒、喜悦和厌恶）。  

While such studies are particularly useful for visualization purposes and to help researchers understand general trends regarding the mood of entire population groups, a higher resolution analysis into user emotions at a street or POI level would allow researchers to address more detailed questions about the city, such as the effect specific locations or places might have on the behaviour and emotions of people.  

虽然这种研究对于可视化目的和帮助研究人员理解关于整个人口群体的情绪的一般趋势特别有用，但是对街道或POI级别的用户情绪的更高分辨率分析将允许研究人员解决关于城市的更详细的问题，例如特定位置或地方可能对人们的行为和情绪的影响。  

A number of studies have suggested how this could be the case. For example, it is well known that green spaces within a city could contribute to an increase in positive mood and emotions \[[21](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref021)\]. In addition, the various locations within a city could elicit different emotional responses (arousal, tension etc.) for people walking along the street \[[22](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref022)\]. Studies have also shown that people near locations such as transportation hubs and sewage facilities tend to report more negative emotions and those near landmark buildings and tourist locations tend to report more positive ones \[[10](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref010)\]. Overall, this type of analysis could be extremely useful in fields such as urban planning and tourism and there have been more calls for further research to be carried out in this area of urban emotions \[[23](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref023)\]. We contribute to this direction of research in this paper, by showing how seven different fine-grained emotion types could be analyzed at a city-wide level. In addition, we provide an analysis into the effect of different place types have on human emotions at a POI level.  

许多研究表明了这是如何发生的。例如，众所周知，城市中的绿色空间有助于增加积极的情绪和情感\[ 21 \]。此外，城市中的不同地点可能会引发不同的情绪反应（唤醒，紧张等）。供人们沿着街上行走\[ 22 \]。研究还表明，靠近交通枢纽和污水处理设施等地点的人往往会报告更多的负面情绪，而靠近地标建筑和旅游景点的人往往会报告更多的正面情绪\[ 10 \]。总的来说，这种类型的分析在城市规划和旅游业等领域可能非常有用，并且越来越多的人呼吁在城市情感领域进行进一步的研究\[ 23 \]。我们在本文中通过展示如何在城市范围内分析七种不同的细粒度情绪类型来促进这一研究方向。 此外，我们还从兴趣点的角度分析了不同场所类型对人类情感的影响。

## Data collection  

数据收集

In this study, data collection was focused on two cities, San Francisco in the USA and London in the UK. The main reasons why these two cities were selected were: 1) The dense open data footprint (social media and open data) which was available (i.e.  

在这项研究中，数据收集集中在两个城市，美国的旧金山和英国的伦敦。这两个城市入选的主要原因是：1）密集的开放数据足迹（社交媒体和开放数据），这是可用的（即  

there were sufficient numbers of geotagged tweets, and Open Street Map was generally found to be more accurate in such densely populated urban areas \[[24](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref024)\]) and 2) The majority of the data was available in English, which was necessary as we were only able to assemble a sufficient number of training samples in that language when developing the automated models used to classify the different emotions.  

有足够数量的地理标记的推文，并且开放街道地图通常被发现在这种人口稠密的城市区域中更准确\[24\]）和2）大部分数据可用英语，这是必要的，因为当开发用于对不同情绪进行分类的自动化模型时，我们只能以该语言集合足够数量的训练样本。  

Data from Open Street Map was collected and used to represent the spatial characteristics of the city, while data from geotagged tweets was analyzed and used to represent the emotions of people within the city.  

从开放街道地图收集数据并用于表示城市的空间特征，而从地理标记的推文中收集数据并用于表示城市内人们的情绪。  

When collecting data for this study, we complied fully with the terms and conditions for the data sources.  

在为本研究收集数据时，我们完全遵守数据来源的条款和条件。

### Collecting spatial information  

收集空间信息

One notable source of information about the characteristics of the various locations and places in the physical world is Open Street Map (OSM) \[[25](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref025)\] This platform was created to provide a free open and editable map of the world, where information is provided by volunteers who collaborate with each other to generate knowledge about the streets, buildings and locations which exist in various cities.  

一个关于物理世界中不同位置和地点的特征的重要信息来源是开放街道地图（OSM）\[ 25 \]这个平台的创建是为了提供一个免费开放和可编辑的世界地图，其中的信息由志愿者提供，他们相互合作生成关于不同城市中存在的街道、建筑物和位置的知识。  

Despite OSM data being generated primarily by volunteers, studies show that the quality of the data available from this platform compares quite favorably with traditional spatial data sources, particularly in dense urban areas \[[24](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref024)\] (however, in underpopulated or rural areas, data could be less accurate \[[26](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref026), [27](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref027)\]).  

尽管OSM数据主要由志愿者生成，但研究表明，从该平台获得的数据质量与传统空间数据源相比相当有利，尤其是在人口稠密的城市地区\[ 24 \]（然而，在人口稀少或农村地区，数据可能不太准确\[ 26，27 \]）。

In this study, OSM tags from the nodes, ways and relations were used to represent the characteristics of different locations in the city. For example, a pet shop is generally tagged using a “key”:“value” format of “shop”: “pet”.  

在本研究中，OSM标签从节点、路径和关系三个方面来表示城市中不同位置的特征。例如，宠物店通常使用"商店"的"键"："值"格式进行标记："宠物"。  

The OSM elements which contain appropriate tags (such as leisure, shop or amenity tags) were considered as Points of Interests (POI). [Table 1](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-t001) shows the number of OSM elements and Points of Interests extracted for San Fransisco and London. As users could freely edit the tags in the OSM data, the dataset resulted in a large number of redundant tags which represented similar objects (such as dry\_cleaners and laundry etc.  

包含适当标签（例如休闲、商店或便利设施标签）的OSM元素被视为兴趣点（POI）。 表1显示了为旧金山和伦敦提取的OSM元素和兴趣点的数量。由于用户可以自由地编辑OSM数据中的标签，数据集产生了大量冗余的标签，这些标签代表了相似的对象（如干洗店和洗衣店等）。  

). This made it difficult to differentiate between meaningful categories. In addition, if these tag value were used as categories for the POIs, they would be too detailed for conducting analysis (e.g.  

）.这使得很难区分有意义的类别。此外，如果将这些标签值用作POI的类别，则它们对于执行分析而言过于详细（例如，  

for the tag values identified in the cities of San Francisco and Greater London, less than 47% contained more than 3 locations in each city and thus when matching tweets to the POIs based on tag values, a large proportion of POIs would have few or no tweets in the vicinity).  

对于在弗朗西斯科和大伦敦的城市中标识的标签值，少于47%的标签值在每个城市中包含多于3个位置，并且因此当基于标签值将推特与POI匹配时，大部分POI将在附近具有很少的推特或没有推特）。  

Therefore, the tags in the dataset were further classified into categories proposed by the Ordnance Survey Classification scheme in the UK \[[28](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref028)\] This classification scheme contains nine categories (Hotel and Restaurants, Commercial Services, Attractions, Sports and Entertainment, Education and Health, Public Infrastructure, Manufacturing and Production, Retail, Transportation).  

因此，数据集中的标签被进一步分类为英国地形测量分类方案提出的类别\[ 28 \]该分类方案包含九个类别（酒店和餐馆、商业服务、景点、体育和娱乐、教育和健康、公共基础设施、制造和生产、零售、交通）。  

In addition, we also added two other groups not included in the classification scheme, Residential to denote locations which are marked as places of residence and Office to denote workplaces. Residential locations are often tagged in OSM with values such as “flat”, “house” or “apartment”, while office buildings generally contain tags such as “office building”.  

此外，我们亦加入了两个不包括在分类计划内的组别，即住宅组别及办公室组别。住宅组别是指标示为居住地点的地点，而办公室组别则是指工作地点。住宅位置通常在OSM中用诸如"公寓"、"房子"或"公寓"之类的值来标记，而办公楼通常包含诸如"办公楼"之类的标记.  

When pre-processing the tags, tags which were of the same category but were written differently were also merged (such as those which were different due to singular and plural notations) or were different due to being written in American or British English (such as flat/apartment).  

当预处理标签时，具有相同类别但书写不同的标签也被合并（诸如由于单数和复数符号而不同的那些标签）或者由于以美式英语或英式英语书写而不同（诸如flat/apartment）。

Overall, there were 1,425 Unique POI types identified from the POI locations in Greater London and 527 Unique POI types identified from the POI locations in the city of San Francisco.  

总之，从大伦敦的POI位置识别出1，425个唯一POI类型，从旧金山市的POI位置识别出527个唯一POI类型。  

To classify these POI types into the categorizes proposed by the Ordinance Survey classification scheme, one researcher familiar with the scheme read through each of the Unique POI types and classified them into one of the 11 categories by hand.  

为了将这些兴趣点分类到条例调查分类方案建议的类别中，一名熟悉该方案的研究人员通读了每一个独特兴趣点类型，并将它们手工分类到11个类别中的一个。  

For example, the POI type “fast\_food” was classified as part of the “Hotel and Restaurants” category and “clothes” was classified as part of the “Retail” category.  

例如，POI类型“快餐”被分类为“旅馆和餐馆”类别的一部分，而“衣服”被分类为“零售”类别的一部分。  

When the POI type was ambiguous, the researcher referred back to several of the raw locations that used the POI type and examined the names and meta data of those locations (which could contain information such as the opening time, website url etc.  

当兴趣点类型不明确时，研究人员会参考使用该兴趣点类型的几个原始地点，并检查这些地点的名称和梅塔数据（可能包含开放时间、网站URL等信息）。  

) and referred to the data on OpenStreetMap’s wiki page \[[29](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref029)\] to make a decision. Furthermore, another researcher sampled the classified categories (especially those which were ambiguous) and any differences were verbally discussed and agreed upon.  

），并参考OpenStreetMap维基页面\[ 29 \]上的数据做出决定。此外，另一位研究人员对分类类别（特别是那些模棱两可的类别）进行了抽样，并口头讨论和商定了任何差异。

Overall, there was a considerable difference between some of the POI types which exist within the two cities. For example, a larger proportion of the POIs (57.52%) in the London dataset was tagged as a Residential while only (24.52%) of the elements in San Fransisco were tagged as such. Further examination of the Non-Residential and Non-Workplace tags also showed that while San Francisco contained more venues which serve food for customers (such as Restaurant & Cafes) (26.70%) compared to London (18.75%), the proportion of Retail Stores which sell food items was more than double compared to London (12.37%) than in San Francisco (5.34%). Other notable differences were in the proportion of Attractions (tourism spots, recreational facilities) in San Francisco (23.48%) when compared to Greater London (16.59%).  

总的来说，这两个城市中存在的一些POI类型之间存在相当大的差异。例如，伦敦数据集中较大比例的POI（57.52%）被标记为住宅，而旧金山中仅有（24.52%）的元素被标记为住宅。对非住宅和非工作场所标签的进一步检查还显示，尽管弗朗西斯科为顾客提供食品的场所（如餐馆和咖啡馆）（26.70%）比伦敦（18.75%）多，但销售食品的零售店比例（12.37%）比旧金山（5.34%）高出一倍多。其他显著差异是弗朗西斯科（23.48%）与大伦敦（16.59%）相比的景点（旅游景点、娱乐设施）比例。

### Collecting geotagged tweets  

收集地理标记的推文

Prior studies have shown how data from Twitter could be particularly useful in helping researchers understand human behavior and emotions.  

此前的研究已经表明，来自推特的数据如何在帮助研究人员了解人类行为和情绪方面特别有用。  

The public availability of information from this platform combined with the high frequency in which users provide information about the world around them has allowed Twitter to become a valuable data source in a number of data analysis studies \[[1](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref001), [18](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref018)\].  

该平台信息的公共可用性，加上用户提供其周围世界信息的高频率，使得Twitter在许多数据分析研究中成为有价值的数据源\[ 1，18 \]。

In this study, geotagged tweets were used in a similar manner as previous studies: as a proxy to explore human emotions at specific locations.  

在本研究中，地理标记推文的使用方式与之前的研究相似：作为在特定地点探索人类情感的代理。  

Geotagged tweets were collected from the cities of London and San Francisco for a one year period, from 1/9/2016 to 28/8/2017 (which coincided with the year of the tweets used to train our models to detect emotions).  

从伦敦和弗朗西斯科收集了一年时间的地理标记推文，从2016年1月9日到2017年8月28日（这与用于训练我们的模型检测情绪的推文年份一致）。  

We chose to use geo-tagged tweets in the earlier years in our analysis due to the more accurate location data \[[30](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref030)\]. Similar to other studies of this nature \[[31](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref031)–[33](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref033)\], the geotagged tweets were collected using the Twitter Streaming API. A location query was used, with the bounding box approach to gather geotagged tweets within the areas of San Francisco and Greater London (e.g.  

由于位置数据更准确，我们在早些年的分析中选择使用地理标记的推文\[ 30 \]。与其他此类性质的研究类似\[ 31 - 33 \]，使用Twitter流媒体API收集地理标记的推文。使用了一个位置查询，用边界框方法收集弗朗西斯科和大伦敦地区内的地理标记推文（例如，  

we defined the latitudes and longitudes of the Northwest and Southeast Corners of a rectangular region and all tweets that are within that region would be collected. For San Francisco, this region was set to Southeast Corner: (37.7020,-122.3362) Northwest Corner: (37.8355,-122.  

我们定义了矩形区域的西北角和东南角的纬度和经度，并且将收集该区域内的所有推特。对于弗朗西斯科，此区域设置为东南角：（37.7020，-122.3362）西北角：（37.8355，-122。  

5422) and for London, this region was set to Southeast Corner: (51.2765, 0.3571) Northwest Corner: (51.686,-0.5713)). In addition to the tweet text, we also collected meta data such as the user id, latitude, longitude, date and time of the tweet and language of the tweet.  

5422），对于伦敦，此区域设置为东南角：（51.2765，0.3571）西北角：（51.686，-0.5713））。除了推文文本，我们还收集了用户id、纬度、经度、推文的日期和时间以及推文的语言等梅塔数据。  

Overall, we collected approximately 0.96 million tweets in San Francisco and 2.18 million tweets in Greater London.  

总体而言，我们在弗朗西斯科收集了大约96万条推文，在大伦敦收集了218万条推文。  

In the pre-processing stage, the content of the tweets were examined and tweets which were automatically generated using linked applications (such as Foursquare) were identified using regular expression matching and were removed.  

在预处理阶段，检查推文的内容，并使用正则表达式匹配识别使用链接的应用程序（如Foursquare）自动生成的推文，并将其删除。  

These tweets generally do not contain content posted by actual users, mostly showing messages such as “I’m at X Location” tweets, “Just posted a photo/video @X” tweets, “Tmp 20C Wind 0mph Press 1010.0mb Cloud 1538 ft Rain 6.  

这些推文一般不包含实际用户发布的内容，大多显示“我在X位置”推文、“刚刚发布了一张照片/视频@X”推文、“温度20 C风0 mph按1010.0mb云1538 ft雨6.  

7mm Humidity 79” (which are automatically generated by weather stations). After pre-processing, there were 1.57 million tweets remaining for London (180,000 unique users) and 0.39 million tweets for San Francisco (65,000 unique users).  

7 mm湿度79”（由气象站自动生成）。预处理后，伦敦（180，000个独立用户）和弗朗西斯科（65，000个独立用户）分别有157万条和39万条推文。

## Detecting basic emotions  

检测基本情绪

Although the task of analyzing sentiment polarity from tweets (positive and negative etc.) has been well explored in prior studies (\[[9](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref009), [34](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref034)\] etc.), research into systems which allow us to detect the presence of more specific emotions in text based contexts have only emerged in recent years \[[35](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref035)\]. In this study, we focus on identifying the presence of the eight emotion types proposed by Plutchik’s multi-dimensional wheel of emotions (Anger, Anticipation, Disgust, Fear, Joy, Sadness, Surprise, Trust) in the geotagged tweets \[[36](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref036)\]. A binary classifier was constructed for each of the eight different emotions which would determine whether or not each tweet displays that particular emotion. We then examined the performance of six different classification approaches for detecting emotions from the tweets.  

虽然分析来自推文的情绪极性（正面和负面等）的任务已在既往研究中进行了充分探索（\[ 9，34 \]等），对允许我们在基于文本的上下文中检测更具体情感的存在的系统的研究只是在最近几年才出现\[ 35 \]。在这项研究中，我们重点关注Plutchik多维情绪轮提出的八种情绪类型（愤怒、预期、厌恶、恐惧、喜悦、悲伤、惊讶、信任）在地理标记推文中的存在\[ 36 \]。为八种不同的情绪中的每一种构建了一个二元分类器，它将确定每条推文是否显示了特定的情绪。然后我们检验了六种不同的分类方法在从推文中检测情感方面的性能。

1.  **SVM+Glove**: The pre-trained GloVe model (the 200 dimension Global Vectors for Word Representation trained with 22 billion tweets \[[37](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref037)\] was used to vectorize the tweets and the classification was performed using the SVM (Support Vector Machine) model with the mean value of the vectorized tweets as features.  
    
    SVM+Glove：使用预先训练的GloVe模型（使用220亿条推文\[ 37 \]训练的用于单词表示的200维全局向量）对推文进行向量化，并使用SVM（支持向量机）模型以向量化推文的平均值作为特征进行分类。  
    
    For SVM models, we experimented with different parameters and kernels and decided to use a linear kernal SVM with a C value of 1 and hinge loss function.  
    
    对于SVM模型，我们用不同的参数和核进行实验，并且决定使用具有为1的C值和铰链损失函数的线性核SVM。
2.  **SVM+Lexicon**: A lexicon based approach was used to train the model (see \[[35](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref035), [38](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref038), [39](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref039)\]), in which several word lexicons were used to extract the emotional and sentiment features from each tweet. Overall, 25 different lexicons were used as features to train the SVM model.  
    
    SVM+词典：使用基于词典的方法来训练模型（参见\[ 35，38，39 \]），其中使用若干词词典来从每条推文提取情感和情绪特征。总的来说，25个不同的词典被用作训练SVM模型的特征。  
    
    We experimented with different combinations of lexicons (from a total of 35 different lexicons) and the 25 lexicons combination used in this study resulted in the best performance.  
    
    我们用不同的词汇组合（总共35个不同的词汇）进行了实验，本研究中使用的25个词汇组合产生了最佳性能。  
    
    The lexicons which were used include the NRC-10 word-emotion association expanded lexicons and the NRC-10 Hash-emotion association lexicons (emotion lexicons for hash tag data) for the eight basic emotions as well as the positive and negative SentiWord and emoticons lexicons.  
    
    所使用的词典包括用于八种基本情绪的NRC-10词语-情绪关联扩展词典和NRC-10散列-情绪关联词典（用于散列标签数据的情绪词典）以及正面和负面的SentiWord和情绪词典。
3.  **SVM+Lexicon+Glove**: The vectorized tweets (Glove) and the extracted lexicon based emotions (similar to the SVM+ Lexicon model) were both used as input data.  
    
    SVM+词典+手套：矢量化的推文（手套）和提取的基于词汇的情感（类似于SVM+词汇模型）都被用作输入数据。
4.  **NN+Glove**: The vectorized tweets were classified using a Neural Network (2 layer dense Neural Network with 200 nodes sequentially connected. The last layer utilized a sigmoid activation function).  
    
    NN+Glove：使用神经网络（具有200个顺序连接的节点的2层密集神经网络）对矢量化的推文进行分类。最后一层使用S形激活函数）。
5.  **LSTM+Glove**: The vectorized tweets (Glove) were classified using an LSTM (Long short-term memory) neural network model (2 layer LSTM with 200 nodes and a drop-out layer of 0.4 sequentially connected to each other, the last layer utilized a sigmoid activation function).  
    
    LSTM+Glove：使用LSTM（长短时记忆）神经网络模型（2层LSTM，具有200个节点和0.4的脱落层，彼此顺序连接，最后一层使用S形激活函数）对矢量化推文（Glove）进行分类。  
    
    For the LSTM models, an RMSprop opitmizer was used with the binary cross-entropy loss function.  
    
    对于LSTM模型，RMSprop优化器与二元交叉熵损失函数一起使用。
6.  **Hybrid+Lexicon+Glove**: The vectorized tweets (Glove) and the extracted lexicon based emotions (similar to the SVM+ Lexicon model) were used as input in a hybrid Neural Network model. The Neural Network structure which had been used previously in \[[40](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref040)\] for bot detection was adapted and applied instead to detect emotions. [S1 Fig](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.s001) shows the architecture of this model.  
    
    混合动力+Lexicon+手套：矢量化的推文（手套）和提取的基于词汇的情绪（类似于SVM+词汇模型）被用作混合神经网络模型中的输入。之前在\[ 40 \]中用于机器人检测的神经网络结构被修改并应用于检测情绪。 S1图显示了该模型的体系结构。

The data used to train our models were obtained from the SemEval2017 and 2018 dataset. Overall, this dataset contained approximately 11,700 labeled tweets from 2016 to 2017.  

用于训练模型的数据来自SemEval 2017和2018数据集。总体而言，该数据集包含2016年至2017年约11,700条带标签的推文。  

The SemEval dataset was used to evaluate and train our models as it contained a sufficiently large number of human-labeled geotagged tweets which originated from the same time period as the tweets collected and used in our study.  

SemEval数据集用于评估和训练我们的模型，因为它包含足够多的人类标记的地理标记推文，这些推文与我们研究中收集和使用的推文来自同一时间段。  

Evaluation was carried out using 10-fold-cross validation. The dataset was shuffled randomly and split into 10 groups with each unique group being used as the testing data and the remaining nine groups being used as the training data.  

使用10倍交叉验证进行评价。数据集被随机打乱并分成10组，每个唯一的组用作测试数据，其余9组用作训练数据。  

The F-score was used as the evaluation score in the 10-fold-cross-validation.  

在10倍交叉验证中，F评分被用作评价评分。  

This score takes into account both Precision (the items correctly classified in each category) and Recall (the percentage of the category that was successfully classified) and is usually considered as more suitable for evaluating classifier systems than just a measure of overall accuracy.  

该评分同时考虑了精确度（正确分类到每个类别中的项目）和召回率（成功分类的类别百分比），通常被认为更适合评价分类器系统，而不仅仅是总体准确度的指标。

[Fig 1](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g001) shows the results of this evaluation. Overall, the **Hybrid+Lexicon+Glove** performed best in classifying emotions of Anger and Anticipation and the **LSTM+Glove** model performed best in classifying Fear, Joy, Sadness, Surprise and Trust. Finally, the **SVM+Lexicon+Glove** performed best in classifying the emotion of Disgust. In the proceeding analysis, the models which showed the best results were used to classify their respective emotions for this study. However, as Surprise performed quite poorly (obtaining an F-score of only 0.61 in the best case model), this emotion was excluded from the subsequent analysis. For comparison purposes, the performance of the models used in this study are summarized in [Fig 2](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g002) based on Accuracy, F-Score and AUC.  

图1显示了该评价的结果。总体而言，混合+词典+手套模型在愤怒和预期情绪分类方面表现最佳，LSTM+手套模型在恐惧、喜悦、悲伤、惊讶和信任情绪分类方面表现最佳。最后，SVM + Lexicon + Glove对厌恶情绪的分类效果最好。在后续的分析中，本研究会选取效果最佳的模型来进行情绪分类。然而，由于惊奇表现相当差（在最佳情况模型中获得的F评分仅为0.61），因此该情绪被排除在后续分析之外。出于比较目的，基于准确度、F评分和AUC，本研究中使用的模型性能总结见图2。

Using the previously mentioned classifiers, we analyzed the fine-grained emotions of the tweets collected in the study. 3.1% of the tweets had been classified with the emotion Anger, 5.5% Disgust, 5.8% Anticipation, 49.2% Joy, 4.1% Sadness, 3.7% Fear and 6.1% Trust for the city of San Francisco. In London, 3.8% of the tweets had been classified with the emotion Anger, 5.9% Disgust, 4.8% Anticipation, 49.5% Joy, 4.6% Sadness, 2.8% Fear and 4.0% Trust. [Table 2](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-t002) (at the end of the manuscript) shows examples of the tweets which were classified for each emotion that were used in the study.  

使用前面提到的分类器，我们分析了研究中收集的推文的细粒度情感。3.1%的推文被归类为愤怒、5. 5%厌恶、5. 8%期待、49. 2%喜悦、4. 1%悲伤、3. 7%恐惧和6. 1%信任旧金山市。在伦敦，3.8%的推文被归类为愤怒、5.9%厌恶、4.8%期待、49.5%喜悦、4.6%悲伤、2.8%恐惧和4.0%信任。 表2（在手稿的结尾）显示了研究中使用的每种情绪分类的推文示例。

## Temporal examination of emotions  

情绪的时间检查

To examine the temporal characteristics of emotion, we first calculated the level of emotions exhibited by the population on each date.  

为了检验情绪的时间特征，我们首先计算了每个日期人群所表现出的情绪水平。  

This was done based on the ratio of the number of tweets which the user had sent during that day that had been positively classified as exhibiting an emotion by our models.  

这是基于用户在那一天发送的推文数量的比率来完成的，这些推文被我们的模型积极地分类为表现出某种情绪。  

For example, if a user sent one angry tweet and 9 other non-angry tweets on a specific day, the angry emotion ratio for that user would be 0.1.  

例如，如果用户在特定的一天发送了一条愤怒的推文和9条其他非愤怒的推文，则该用户的愤怒情绪比率将是0.1。  

Calculating the emotions for each user individually was necessary to prevent bias from individuals who tend to send a large number of tweets (the number of tweets sent by each user tended to be unevenly distributed to a considerable degree).  

为了防止倾向于发送大量推文的个人产生偏见（每个用户发送的推文数量在很大程度上倾向于不均匀分布），有必要单独计算每个用户的情绪。  

Tukey’s fences were also used to filter out low range outlier days based on the number of tweets sent on that day (using K = 1.5) \[[41](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref041)\].  

Tukey栅栏还用于根据当天发送的推文数量过滤出低范围离群值天数（使用K = 1.5）\[ 41 \]。  

This helped filter out days where there were only few tweets, as days which had only a few users tweeting biased the average results (such days tended to only have a few users who tweeted one tweet that turned out to be positively classified; this would result in an abnormally large average).  

这有助于过滤出只有很少推文的日子，因为只有少数用户发推文的日子会使平均结果产生偏差（这样的日子往往只有少数用户发了一条推文，结果被证明是正面分类的;这将导致异常大的平均值）。  

Afterwards, the emotion value for all users on that day were averaged resulting in the daily emotion value. A time series of the emotions displayed on each day is shown in [S2 Fig](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.s002) for San Francisco and [S3 Fig](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.s003) for London.  

然后，对当天所有用户的情绪值进行平均，得到每日情绪值。在弗朗西斯科的S2图和伦敦的S3图中示出了每天显示的情绪的时间序列。

### Visualizing daily emotions throughout the year  

可视化全年的日常情绪

Temporal heat maps were created to visualize the average emotions on different days in San Francisco and London. The heatmap for the city of San Francisco is shown in [Fig 3](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g003). It should be noted that the heatmap values were presented using the z-score, allowing for an easier comparison between the different emotions. A visual inspection of the values showed spikes in emotion levels during the period of 20 Jan 2017 to 22 Jan 2017.  

他们制作了时间热图，以可视化弗朗西斯科和伦敦不同日子的平均情绪。弗朗西斯科市的热图如图3所示。应该注意的是，热图值是使用z得分表示的，这使得不同情绪之间的比较更加容易。数值目视检查显示，2017年1月20日至2017年1月22日期间情绪水平出现峰值。  

This coincided with two events in the U.S., the Presidential inauguration and the 2017 Women’s March. During the Women’s March in particular, users showed the highest level of Anticipation one day prior to the event (21 Jan 2017) (0.106 compared to a daily average of 0.07) and the highest level of Anger (0.069 compared to a daily average of 0.03), Disgust (0.097 compared to a daily average 0.058) and Sadness (0.081 compared to a daily average of 0.044) on the day of the event (22 Jan 2017). Another prominent event was the 2017 Berkeley protests that occurred during 26 Aug 2017, which resulted in the second highest level of Anger (0.615) and Disgust (0.092). On seasonal events such as New Years Eve, users showed the highest level of Joy (0.612 compared to a daily average of 0.502).  

与此同时，美国发生了两件事，总统就职典礼和2017年妇女游行。特别是在妇女游行期间，用户在活动前一天表现出最高的预期水平（2017年1月21日）（0.106，而日平均值为0.07）和最高水平的愤怒（0.069，而日平均值为0.03），事件当天（2017年1月22日），恶心（0.097，日平均值0.058）和悲伤（0.081，日平均值0.044）。另一个突出的事件是2017年8月26日发生的2017年伯克利抗议活动，导致愤怒（0.615）和厌恶（0.092）的第二高水平。在新年前夕等季节性活动中，用户表现出最高水平的喜悦（0. 612，而日平均值为0. 502）。

The heatmap for the city of London is shown in [Fig 4](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g004). Overall, there were two events which have a high spike in emotion levels in London. These were the Westminster attacks which occurred around 23 March 2017 and the London Bridge attack which occurred during 3 June 2017. Twitter users in London showed the highest level of Fear during the Westminster attack (0.097 compared to a daily average of 0.0275) and the second highest level at the days following the London Bridge attack (0.067 at 4 June 2017)(0.053 at 5 June 2017). The highest level of Sadness also occurred during the Westminster attack (0.122 compared to a daily average of 0.04) and the second highest during the days directly after the London Bridge attacks (0.084 at 4 June 2017). Seasonal events also played a prominent role, with New Years showing high levels of Joy (0.636 compared to a daily average of 0.509) as well as Valentine’s Day showing the second highest level of Joy (0.581) and the Christmas week (around 0.55 on 23 December for example). The highest level of Trust (0.0635 compared to a daily average of 0.041) and Anticipation (0.092 compared to a daily average of 0.056) was shown during UK General election (8 June 2017).  

伦敦市的热图如图4所示。总的来说，有两个事件在伦敦的情绪水平上有很高的峰值。这两起事件分别是2017年3月23日左右发生的威斯敏斯特袭击事件和2017年6月3日发生的伦敦桥袭击事件。伦敦的推特用户在威斯敏斯特袭击事件期间表现出最高的恐惧水平（0.097，而日均值为0.0275），在伦敦桥袭击事件后的几天里表现出第二高的恐惧水平（2017年6月4日为0.067）（2017年6月5日为0.053）。最高的悲伤水平也出现在威斯敏斯特袭击事件期间（0. 122，而日平均值为0. 04），第二高的是伦敦桥袭击事件后的几天（2017年6月4日为0. 084）。季节性事件也起到了突出的作用，新年显示出较高的快乐水平（0.636，而日均值为0.509），情人节显示出第二高的快乐水平（0.581），圣诞节（约为0.509）。例如12月23日55）。英国大选期间（2017年6月8日）的信任度（0.0635，日平均值为0.041）和预期度（0.092，日平均值为0.056）最高。

Overall, these results were mostly consistent with those reported in previous studies.  

总体而言，这些结果与既往研究报告的结果基本一致。  

For instance, prior studies found that during events of terrorism, there tends to be a spike in the display of emotions such as fear, sympathy and sadness on social media such as twitter based on the geographic proximity of the user to that event \[[42](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref042)\] or in space-time clusters \[[13](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref013)\]. A similar result was also discovered when analyzing tweets during the Paris and Brussels attacks, where emotions such as Anger, Sadness and Anxiety tending to spike on social media a couple of days after the event \[[20](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref020)\]. In terms of positive emotion, prior studies which analyzed geotagged tweets also showed that users tended to display more Joy and Happiness on holiday events such as Christmas and Valentine’s day \[[43](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref043), [44](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref044)\]. However, the results from this study also adds to those from the earlier studies, showing how terrorism events could elicit other negative emotions such as Disgust and that high levels of emotions such as Anticipation, Anger and Disgust could also be found during events such as protests.  

例如，先前的研究发现，在恐怖主义事件期间，基于用户与事件的地理接近度\[ 42 \]或时空聚类\[ 13 \]，在社交媒体（如twitter）上，恐惧、同情和悲伤等情绪的表现往往会出现峰值。在分析巴黎和布鲁塞尔袭击期间的推文时也发现了类似的结果，愤怒、悲伤和焦虑等情绪往往会在事件发生后几天在社交媒体上激增\[ 20 \]。在积极情绪方面，之前分析地理标记推文的研究也表明，用户往往在圣诞节和情人节等节日活动中表现出更多的喜悦和幸福\[ 43，44 \]。 然而，这项研究的结果也补充了早期研究的结果，表明恐怖主义事件如何引发其他负面情绪，如厌恶，以及在抗议等事件中也可以发现高水平的情绪，如预期、愤怒和厌恶。

### Emotions on different days of the week  

一周中不同日子的情绪

Next, we examined the differences in the display of emotions on different days of the week. Kruskal-Wallis tests were carried out to investigate these differences. The results showed significant differences in Anger, Anticipation, Sadness in San Francisco for different days of the week (p<0.01). A visual inspection suggested that Anger was higher during the middle of the week (on Wednesday (median = 0.037)) and less during the weekends (particularly Saturday (median = 0.287) and Sunday (median = 0.029)). The least amount of Anticipation was shown on Sunday (median = 0.0596) compared to the weekdays (such as during Friday (median = 0.0722)). The weekends also tended to have a lower amount of Sadness (with a median of 0.038 on Sunday and Saturday) when compared to the weekdays (a median of 0.044 for Monday etc.). [Fig 5](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g005) shows the emotions displayed on each days of the week which were significantly different in San Francisco.  

接下来，我们研究了一周中不同日子情绪表现的差异。进行Kruskal-Wallis检验以研究这些差异。结果表明，旧金山地区不同工作日的愤怒、期待、悲伤情绪差异有统计学意义（p〈0. 01）。视觉检查表明，愤怒在一周的中间时间（周三（中位数= 0.037））更高，在周末（特别是周六（中位数= 0.287）和周日（中位数= 0.029））更低。与工作日（如周五（中位数= 0.0722））相比，周日（中位数= 0.0596）的预期量最小。与工作日（周一等中位数为0.044）相比，周末的悲伤程度也较低（周日和周六中位数为0.038）。 图5示出了在旧金山显著不同的一周的每一天显示的情绪。

The results were similar in London. There were significant differences in the display of Anger, Anticipation, Joy, Sadness, Fear and Trust (p<0.01). Anger, Sadness and Fear was generally lowest during the weekends, on Sunday (median Anger = 0.034, median Sadness = 0.038, median Fear = 0.023) and highest during the weekdays (Tuesday for Anger (median = 0.04), Wednesday for Sadness (median = 0.046) and Fear (median = 0.028)). Similar to San Francisco, Anticipation was also lowest during Sunday (median = 0.045 compared to an average median of 0.055 for the other days). Finally Joy was generally high on Sunday (median = 0.513), compared to an average median of 0.508 for the other days. [Fig 6](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g006) shows the emotions displayed on each days of the week which were significantly different in London.  

伦敦的结果也差不多。在愤怒、期待、喜悦、悲伤、恐惧、信任等方面差异有统计学意义（p〈0.01）。愤怒、悲伤和恐惧通常在周末、周日最低（愤怒中位数= 0.034，悲伤中位数= 0.038，恐惧中位数= 0.023），在工作日最高（周二愤怒（中位数= 0.04），周三悲伤（中位数= 0.046）和恐惧（中位数= 0.028））。与旧金山相似，周日的预期也最低（中位数为0.045，而其他日期的平均中位数为0.055）。最后，快乐在周日普遍很高（中位数= 0.513），而其他日子的平均中位数为0.508。 图6显示了一周中每一天的情绪表现，这在伦敦是显著不同的。

Overall, the results for both San Francisco and London could be understood quite intuitively. Positive emotions tended to be higher on weekends and negative emotions higher on weekdays \[[45](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref045)\]. This is not surprising as people have more free time to spend on Joyful activities during the weekends. Higher levels of negative emotions during Tuesday and Wednesday could perhaps be explained by people trying to get through the middle of a working week \[[44](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref044)\]. Finally, the lower amount of Anticipation on Sunday might indicate that people were not looking forward to the coming work week compared to Thursday and Friday where people were looking forward to the weekends.  

总的来说，旧金山和伦敦的结果都可以很直观地理解。积极情绪往往在周末更高，消极情绪在工作日更高\[45\]。这并不奇怪，因为人们在周末有更多的空闲时间花在快乐的活动上。周二和周三的高水平负面情绪可能是因为人们试图度过一周工作的中间时间。最后，周日的预期值较低可能表明，与周四和周五相比，人们对即将到来的工作周并不期待，周四和周五人们期待的是周末。

## Contextualising emotions by places  

按地点将情绪置于情境中

In this section, we investigate the potential effect different places (based on the points of interests extracted using Open Street Map) have on the expression of emotions.  

在本节中，我们将研究不同地点（基于使用Open Street Map提取的兴趣点）对情绪表达的潜在影响。

### Expression of emotions at different POIs  

不同兴趣点的情绪表达

To analyze the effect different places have on fine-grained emotions, we examined the tweets which were near to different Points of Interests.  

为了分析不同地点对细粒度情绪的影响，我们检查了靠近不同兴趣点的推文。  

Due to the nature of this research which explores the possible relationship between POI types and emotions, we considered tweets which were within a specific distance from a POI to fall under the influence of that POI.  

由于这项研究的性质是探索POI类型和情绪之间的可能关系，我们认为与POI在特定距离内的推文受到该POI的影响。  

For each POI in our database, an appropriate radius for which a tweet could be considered to be influenced by that POI was determined by calculating the distance between each POI element in our database and the nearest non-tagged building or tagged POI (0.  

对于我们的数据库中的每个POI，通过计算我们的数据库中的每个POI元素与最近的未标记建筑物或标记POI之间的距离来确定推文可被认为受该POI影响的适当半径（0.  

44 million locations in London and 0.28 million locations in San Francisco). For POI locations which were isolated, the average distance calculated from all the other POIs was used instead (which for San Francisco was 14 meters and London 9 meters).  

伦敦的4400万个位置和弗朗西斯科的28万个位置）。对于被隔离的POI位置，使用从所有其他POI计算的平均距离（弗朗西斯科为14米，伦敦9米）。  

It should be noted that a POI was considered isolated when the distance to the nearest non-tagged building or tagged POI was more than the far-out outliers value (calculated using Tukey’s Fences which resulted in a distance of 51.5 meters for San Francisco and 50.  

应当注意，当与最近的未标记建筑物或标记POI的距离大于远异常值（使用Tukey's Fences计算，其导致弗朗西斯科的距离为51.5米，而旧金山的距离为50米）时，POI被认为是孤立的。  

0 meters for London). The distances between the tweets and the POI were calculated using the Haversine formula. Overall, there were 4,674 POIs (21.42%) which had nearby tweets from at least one Twitter user in San Francisco and 26,740 POIs (11.31%) in London.  

0米为伦敦）。使用半正矢公式计算推文和POI之间的距离。总体而言，弗朗西斯科有4，674个POI（21.42%）拥有至少一个Twitter用户的附近推文，伦敦有26，740个POI（11.31%）。

[Table 3](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-t003) shows the top 10 POIs (based on the original OSM tag values) where nearby users expressed the highest level of each emotion in the city of San Francisco and London.  

表3示出了前10个POI（基于原始OSM标签值），其中弗朗西斯科和伦敦的附近用户表达了每种情绪的最高级别。  

When calculating the top 10 results, POIs with less than 10 users were excluded as well as those with only one venue in the city (as these locations tended to have artificially high averages due to a low amount of users posting few tweets which happened to be classified as positive for certain emotions).  

在计算前10个结果时，用户少于10个的兴趣点以及在城市中只有一个地点的兴趣点被排除在外（因为这些地点往往具有人为的高平均值，因为很少有用户发布很少的推文，这些推文碰巧被归类为对某些情绪积极的）。  

From the results, it seems that locations such as hospitals, dentist and doctor offices tend to have tweets with high amounts of fear and sadness (perhaps indicating that people are fearful for their illness or for their love ones) and locations where water related activities can be carried out such as swimming pools, sailing ports, coastlines and boat ramps showed tweets with high levels of Joy. High negative emotions such as Anger and Disgust were also shown nearby Transportation locations such as bus stops, bridges and train stations, perhaps reflecting peoples’ frustration at waiting for their transportation or being stuck in traffic.  

从结果来看，医院、牙医和医生办公室等地点的推文往往带有大量的恐惧和悲伤（也许表明人们对自己的疾病或亲人感到恐惧），而游泳池、帆船港口、海岸线和船只坡道等可以进行与水有关的活动的地点的推文则显示出高水平的喜悦。愤怒和厌恶等高负面情绪也出现在公交车站、桥梁和火车站等交通地点附近，这可能反映了人们在等待交通工具或被困在交通中时的沮丧。

Next, we examined the display of emotions at different POIs based on the Ordnance Survey classification values. As the distribution of the tweets in each POI location followed a pattern which was similar to a power law distribution (e.g.  

接下来，我们基于地形测量分类值检查了不同POI处的情绪显示。由于每个POI位置中的推文的分布遵循类似于幂律分布的模式（例如，  

in San Francisco, the top 10 POI locations had on average 2,950 users tweeting and at the tail end, 29% of locations had 1 user), we had used non-parametric approaches to analyze the data in our study.  

在旧金山，排名前10的POI地点平均有2，950个用户在发推文，在最后，29%的地点有1个用户），我们使用非参数方法来分析我们研究中的数据。  

More specifically, Kruskal-Wallis tests were carried to examine the differences between the emotions expressed at the different categorical locations. The results showed significant differences for all the emotions in London (p<0.05 for Joy, p<0.001 for all the other 6 emotions) and for Anger, Joy, Sadness, (p<0.05) Anticipation, Fear and Trust (p<0.01) in San Francisco. There was no significant differences between the different categories for Disgust in SF. [Fig 7](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g007) shows the level of the emotions at different POI categories for San Francisco and [Fig 8](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-g008) shows the level of the emotions at different POI categories for London based on the mean rank obtained from the Kruskal-Wallis tests.  

更具体地说，Kruskal-Wallis检验是用来检验在不同类别位置表达的情绪之间的差异。结果显示，伦敦的所有情绪（快乐p〈0.05，其他6种情绪p〈0.001）和旧金山的愤怒、快乐、悲伤（p〈0.05）、预期、恐惧和信任（p〈0.01）存在显著差异。SF中不同类别的恶心无显著差异。 图7示出了基于从Kruskal-Wallis测试获得的平均等级的旧金山的不同POI类别处的情绪水平，图8示出了伦敦的不同POI类别处的情绪水平。  

It should be noted that the manufacturing category was excluded in the analyzed for San Francisco, due to the low number of such locations (n = 12).  

应注意的是，由于此类地点数量较少（n = 12），因此在旧金山的分析中排除了制造类别。

[Table 4](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-t004) provides an overview of the significantly different categories based on the results of Bonferroni corrected Dunn’s post-hoc tests carried out following the Kruskal-Wallis tests (at a p<0.05 level).  

表4根据Kruskal-Wallis检验（p〈0.05水平）后进行的Bonferroni校正Dunn事后检验的结果概述了显著不同的类别。  

For example, the results showed that in San Francisco, there was significantly more Anger near (9) Retail and (12) Office locations than close to (5) Education & Health locations. In addition there was significantly more Joy near (1) Hotel & Restaurant locations than (10) Transportation places (bus stops etc.). In London, the results showed for example that there was significantly more Anger near (4) Sports & Entertainment, (1) Hotel and Restaurant and (10) Transportation locations than near (5) Education & Health, (11) Residential and (9) Retail locations. It should be noted that the majority of the significant differences in London was due to the (11) Residential category, where there tended to be on average, significantly less emotions exhibited on the tweets at such locations than at other locations.  

例如，结果显示，在旧金山，靠近（9）零售和（12）办公场所的愤怒者明显多于靠近（5）教育和健康场所的愤怒者。此外，在（1）酒店和餐馆附近的欢乐明显多于（10）交通地点（公共汽车站等）。例如，在伦敦，结果显示，在（4）体育和娱乐、（1）酒店和餐馆以及（10）交通地点附近的愤怒明显多于在（5）教育和健康、（11）住宅和（9）零售地点附近的愤怒。应该注意的是，伦敦的大部分显著差异是由于（11）住宅类别，平均而言，这些地点的推文上表现出的情绪往往比其他地点少得多。

[![thumbnail](size=inline&id=10.1371)](https://journals.plos.org/plosone/article/figure/image?size=medium&id=10.1371/journal.pone.0279749.t004 "Click for larger image")

Table 4. Results of significantly different categories: (1): Hotel & Restaurants, (2): Commercial Services, (3): Attractions, (4): Sports & Entertainment, (5): Education & Health, (6): Public Infrast.  

表4.显著不同类别的结果：（1）：酒店和餐馆，（2）：商业服务（3）：景点，（4）：体育与娱乐，（5）：教育和卫生，（6）：公共基础设施。  

, (7): Manufacturing & Production, (9): Retail, (10): Transport, (11): Residential, (12): Office.  

，（7）：制造与生产，（9）：零售业（10）：运输（11）：住宅，（12）：办公室。

[https://doi.org/10.1371/journal.pone.0279749.t004](https://doi.org/10.1371/journal.pone.0279749.t004)

Overall, this analysis of fine-grained emotions at different POI categories provided a number of interesting findings.  

总的来说，对不同兴趣点类别的细粒度情绪的分析提供了许多有趣的发现。  

Similar to an earlier study which analyzed tweets at New York city, we found that transportation locations such as train stations, bus garages and bridges in London and San Francisco tend to elicit negative emotions (lower Joy and Higher Disgust etc.) \[[10](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref010)\]. Sports and Entertainment venues (such as stadiums) also tended to show high levels of Anger, Fear, Anticipation and Sadness. This is understandable as these were emotions which tended to be associated with the participation and viewing of sport activities (being fearful and sad when the team they are supporting is losing \[[46](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref046)\]. The high levels of Joy in the Hotel & Restaurant category could perhaps be explained by people tweeting about their food and tourist tweeting about their holiday. A manual inspection showed that several restaurants types in San Francisco and tourist accommodation types (motel, hostels) in London had high levels of Joy.  

与之前分析纽约市推文的研究类似，我们发现伦敦和旧金山的火车站、公交车车库和桥梁等交通地点往往会引发负面情绪（较低的喜悦和较高的厌恶等）。\[10\].体育和娱乐场所（如体育场）也往往表现出高水平的愤怒，恐惧，期待和悲伤。这是可以理解的，因为这些情绪往往与参与和观看体育活动有关（当他们支持的球队输球时感到恐惧和悲伤\[46\]）。酒店和餐厅类别中的高快乐度也许可以用人们在推特上谈论他们的食物和游客在推特上谈论他们的假期来解释。人工检查显示，旧金山的几种餐馆类型和伦敦的旅游住宿类型（汽车旅馆、招待所）的快乐程度很高。

### POI neighborhood effect on emotions  

兴趣点邻域对情绪的影响

Next, we further examine whether the display of emotions through the tweets was affected by the type of POI within the nearby vicinity.  

接下来，我们进一步检查通过推文的情绪显示是否受到附近POI类型的影响。  

This was done by drawing a radius around the center of each positively and not positively classified tweets for each emotion and identifying the amount of venues in each category which exist in that vicinity.  

这是通过围绕每种情绪的每一条积极和不积极分类的推文的中心画一个半径，并确定存在于该附近的每一类中的地点的数量来完成的。  

Distance levels of 10, 30 and 50 meters were examined for the tweets in San Francisco in this study. For example, if a positively classified Anger tweet contains 2 Restaurants, 6 Residential buildings and an Office and no other venues within 20 meters, then the independent variables for that tweet would be represented as (2,0,0,0,0,0,0,0,0,6,1) (the first representing the number of venues in the (1) Hotel & Restaurant category and the second, the number of venues in the (2) Commercial services category and so on).  

在这项研究中，弗朗西斯科的推文距离水平分别为10米、30米和50米。例如，如果被正面分类为愤怒的推文包含2个餐馆、6个住宅楼和一个办公室，并且在20米内没有其他场所，则该推文的自变量将被表示为（二、零、零、零、零、零、零、零、六、一）（第一项是属于（1）酒店及食肆类别的场地数目，第二项是属于（2）商业服务类别的场地数目，依此类推）。

Mann-Whitey tests were then carried out to examine the differences between the number of venues in each category that exist in the nearby vicinity of the tweets classified as positive and negative for each emotion.  

然后进行了曼-怀蒂测试，以检查每种情绪被分类为积极和消极的推文附近存在的每种类别中的地点数量之间的差异。  

In short, the results would indicate whether the tweets which were classified as positive or negative based on a specific emotion (such as Anger), might contain significantly higher or lower numbers of venues of a specific category within the nearby vicinity. Bonferroni correction was also applied to reduce the likelihood of finding significant results by chance due to multiple comparisons.  

简而言之，结果将指示基于特定情绪（诸如愤怒）被分类为正面或负面的推文是否可能包含附近区域内的特定类别的显著更高或更低数量的场所。还应用了Bonferroni校正，以降低由于多重比较而偶然发现显著结果的可能性。

The categories of locations which showed significant differences (p<0.05) in the display of emotions at the three different distance levels are shown in [Table 5](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone-0279749-t005). A category number in the “More” column indicates that tweets which were positively classified based on a specific emotion tend to have a significantly higher number of venues of such category in the nearby vicinity than those which were not positively classified.  

在三个不同的距离水平上，情绪表现有显著差异（p〈0.05）的位置类别如表5所示。“更多”列中的类别号指示基于特定情感被肯定分类的推文与未被肯定分类的推文相比，在附近区域中倾向于具有显著更高数目的这种类别的地点。  

A category number in the “Less” column indicates that tweets which were positively classified tend to have a significantly lower number of such venues in the nearby vicinity. For example, tweets which were positively classified as expressing Joy tend to have significantly more (1) Hotel & Restaurant, (2) Commercial Services and (4) Sports & Entertainment places within the vicinity (which might be indicative of tourist or shopping areas) than those which were not. Meanwhile, tweets which were classified as expressing Joy tend to have significantly less (12) Office locations within a 10 meter vicinity than those which were not. In addition, Angry and Sad tweets tend to have significantly higher numbers of (12) Offices in the nearby vicinity regardless of distance. There also seems to be an effect of distance in some cases, for example, Trust tweets tended to contain significantly higher numbers of (6) Public Infrastructure locations within 10 and 20 meters but a difference was no longer observed after extending the distance to 30 meters.  

“更少”列中的类别号指示被正面分类的推文趋向于在附近具有显著更少数量的这样的场所。例如，被积极分类为表达喜悦的推文往往比那些不表达喜悦的推文有更多的（1）酒店和餐馆，（2）商业服务和（4）附近的体育和娱乐场所（这可能表明旅游或购物区）。同时，被归类为表达喜悦的推文在10米范围内的办公室位置往往比不表达喜悦的推文少（12）个。此外，愤怒和悲伤的推文往往有明显更高的数量（12）办事处在附近，无论距离。 在某些情况下，距离似乎也有影响，例如，Trust推文往往在10米和20米范围内包含数量显著较高的（6）公共基础设施位置，但将距离延长至30米后，不再观察到差异。

[![thumbnail](size=inline&id=10.1.1371)](https://journals.plos.org/plosone/article/figure/image?size=medium&id=10.1371/journal.pone.0279749.t005 "Click for larger image")

Table 5. The categories of locations which showed significant differences (p<0.05) in the display of emotions at three different distance levels in San Francisco.  

表5.在旧金山的三个不同距离水平的情绪显示有显著差异（p〈0.05）的地点类别。

[https://doi.org/10.1371/journal.pone.0279749.t005](https://doi.org/10.1371/journal.pone.0279749.t005)

## Conclusions & future work  

结论和今后的工作

In this paper, open web data from Twitter and Open Street Map was analyzed to portray fine-grained human emotions in two cities, San Francisco and London.  

本文分析了Twitter和Open Street Map的开放网络数据，以描绘旧金山和伦敦这两个城市的细粒度人类情感。  

Neural Network classifiers were developed, tested and used to classify approximately 2 million geotagged tweets based on 7 different emotions.  

神经网络分类器被开发、测试并用于基于7种不同的情感对大约200万条地理标记的推文进行分类。  

A temporal examination regarding the portrayal of the different emotions was provided, highlighting for example how tweets in London displayed high levels of Sadness and Fear during two high profile terrorism incidents which occurred in the city, while political protest events resulted in high levels of Anger, Disgust and Sadness in San Francisco. Afterwards, the tweets were matched to POIs extracted from Open Street Map to examine the effect of different places on the display of emotion.  

提供了关于不同情绪描述的时间研究，例如，突出了伦敦的推文如何在该市发生的两起引人注目的恐怖主义事件期间显示出高水平的悲伤和恐惧，而政治抗议事件导致弗朗西斯科的高水平的愤怒、厌恶和悲伤。然后，将推文与从开放街道地图中提取的兴趣点进行匹配，考察不同地点对情绪表达的影响。  

The results showed significant differences with regard to the type of place, such as how tweets in London showed significantly more Anger at Transportation and Sport locations than at Education, and Residential locations and how tweets which display Anger and Sadness in SF tend to have significantly higher numbers of Office venues in the nearby vicinity.  

结果显示了地点类型的显著差异，例如伦敦的推文在交通和体育地点比在教育和住宅地点显示出更多的愤怒，以及在旧金山显示愤怒和悲伤的推文在附近的办公场所数量明显更多。

Compared to existing research, our work makes several novel contributions. While prior studies investigating the spatial distribution of emotions through social media tend to focus on sentiment polarity \[[9](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref009), [47](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref047)\] and are deployed at a coarse geographical level (state or country wide etc.) \[[6](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref006), [7](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref007), [18](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref018)\], our study shows how 7 different fine-grained emotions could be portrayed at a POI level in a finer scale.  

与已有的研究相比，我们的工作有一些新的贡献。虽然之前通过社交媒体调查情绪空间分布的研究倾向于关注情绪极性\[ 9，47 \]，并且在粗略的地理水平（州或全国范围内等）进行部署。\[ 6，7，18 \]，我们的研究显示了如何在POI级别以更精细的尺度描绘7种不同的细粒度情绪。  

In addition, we show how our approach could be beneficial to research related to the spatial and temporal characteristics of the fine-grained emotions by providing an overview into the effect different categories of places could have on the expression of emotion.  

此外，我们通过概述不同类别的地点对情绪表达的影响，展示了我们的方法如何有益于与细粒度情绪的空间和时间特征相关的研究。  

Our work thus provides a broad overview of how expressing emotions on Twitter reflects the surrounding spatial-temporal context.  

因此，我们的工作提供了一个在Twitter上表达情绪如何反映周围时空背景的广泛概述。

Accordingly, more in-depth analyses could be carried out to examine the expression of emotions at more specific location categories (different types of restaurant (fast food, cafe etc.), recreational facilities (sports, parks, bars)).  

因此，可以执行更深入的分析以检查在更具体的位置类别（不同类型的餐馆（快餐、咖啡馆等）、娱乐设施（体育、公园、酒吧））。  

In particular, we would be interested in addressing more specific research questions, such as the degree different places might have as a buffer for extreme emotions on days with adverse events (during terrorist events, do bars help reduce Fear when compared to places such as parks? etc.).  

特别是，我们会对解决更具体的研究问题感兴趣，比如在发生不良事件的日子里，不同的地方可能在多大程度上缓冲了极端情绪（在恐怖事件期间，与公园等地方相比，酒吧是否有助于减少恐惧？）等等）。  

There are a number of research areas which this work could be expanded into, for example, in areas such as digital archiving (to record not only facts, but also collective human emotional responses at a detailed spatial and temporal level).  

这项工作可以扩展到许多研究领域，例如，数字存档（不仅记录事实，而且在详细的空间和时间层面记录人类集体情感反应）。

Overall, there are a number of limitations in our study.  

总的来说，我们的研究存在一些局限性。  

As geotagged tweets were used as the main data source and we focused our data collection on two urban English speaking cities, the results might not be generalizable to other population groups with different languages and cultures.  

由于地理标记的推文被用作主要数据源，并且我们将数据收集集中在两个讲英语的城市，因此结果可能无法推广到具有不同语言和文化的其他人口群体。  

Furthermore, previous studies have also highlighted several biases that could be present in data from geotagged tweets, such as demographical biases, where users who post geotagged tweets tend to be younger and more educated than the general population \[[48](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref048), [49](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref049)\] and female users could be overrepresented in the urban city areas where we conducted our analysis \[[50](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref050)\]. Compared with non-geotagged tweets, there could also be significant differences in the age and gender of users who chose to share their location, though the effect of such differences tend to be small \[[51](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref051)\]. Users are also more likely to share information about specific public or social events in such tweets \[[52](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref052)\] and posting on social media in general represents a selection bias, in that individuals who may not feel elevated levels of emotion may not see a need to Tweet. As such, researchers should be cautious about overgeneralizing the results from this study to the overall population.  

此外，之前的研究还强调了地理标记推文数据中可能存在的几种偏见，如人口统计学偏见，即发布地理标记推文的用户往往比普通人群更年轻，受教育程度更高\[ 48，49 \]，女性用户在我们进行分析的城市地区可能占比过高\[ 50 \]。与无地理标记的推文相比，选择分享其位置的用户的年龄和性别也可能存在显著差异，尽管此类差异的影响往往很小\[ 51 \]。用户也更有可能在这些推文中分享关于特定公共或社会事件的信息\[ 52 \]，在社交媒体上发帖通常代表了一种选择偏见，因为可能没有感觉到情绪水平升高的个人可能不认为有必要发推文。因此，研究人员应该谨慎，不要将本研究的结果过度概括到整个人群。  

In addition, we should also mention that due to the large amount of data, an automatic algorithm was employed to detect emotions from tweets.  

此外，我们还应该提到，由于数据量大，采用了自动算法从推文中检测情绪。  

While we had experimented with several algorithms and selected a sufficiently high performing model with a respectable level of accuracy to use in our analysis, same as in the case of other studies which utilize an automated approach to detect emotions, there could still be errors in the classification process which could influence the results.  

虽然我们已经试验了几种算法，并选择了一个具有相当准确度的足够高性能的模型用于我们的分析，与利用自动化方法检测情绪的其他研究的情况相同，但在分类过程中仍然可能存在会影响结果的错误。

Finally, we should note that as the method which we used in this study relied primarily on VGI and Social media data, our method might not be as applicable to locations with a small digital footprint.  

最后，我们应该注意到，由于我们在本研究中使用的方法主要依赖于VGI和社交媒体数据，因此我们的方法可能不适用于数字足迹较小的位置。  

For example, in the UK, the data from OpenStreetMap of Northumberland (a county which is about 3.  

例如，在英国，来自诺森伯兰郡（一个大约3.  

3 times larger than the Greater London area, but has a far lower population density (64 people per square kilometers vs 5,671 for the Greater London area) contains mostly residential locations and few or no POIs of certain types (e.g.  

比大伦敦地区大3倍，但人口密度低得多（每平方公里64人，大伦敦地区为5，671人），主要包含住宅区，很少或没有某些类型的兴趣点（例如  

only 2 college and university tagged POIs vs 546 for London and no POIs tagged as “motorcycle parking”, “car sharing” and “jewelry” for Northumberland). In addition, there are also fewer recorded locations even for POI types commonly found in dense cities (e.g.  

只有2所学院和大学标记了POI，而伦敦有546个，诺森伯兰没有标记为“摩托车停车场”、“汽车共享”和“珠宝”的POI）。此外，即使是在人口密集的城市中常见的POI类型（例如，  

99 parks vs 2,953 in London, 135 retail vs 4,280 or 2 dry cleaning vs 435 in London). When querying geo-tagged tweets which fall under the Northumberland area, far less usable tweets were also identified for the area (approximately 34,000 geotagged tweets compared with 0.  

99个公园对伦敦2,953个，135个零售对4,280个或2个干洗对伦敦435个）。当查询落在诺森伯兰地区下的地理标记的推文时，也为该地区识别了少得多的可用推文（大约34，000个地理标记的推文，相比之下为0。  

6 million for London in 2021). This results in fewer tweets being matched to the POI locations, making it not as practical to conduct the type of fine-grained POI-based statistical analysis which we had done in this study (as sparse data could bias the results).  

2021年伦敦600万）。这导致与POI位置匹配的推文更少，使得我们在本研究中进行的基于POI的细粒度统计分析不太实用（因为稀疏数据可能会使结果产生偏差）。  

Other studies of this nature which utilized social media and VGI data as the data source have also highlighted similar limitations \[[53](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref053)\] (e.g. geo-tagged social media and VGI data tend to concentrate in large metropolitan cities and while they are accurate and comprehensive in such areas, they are less present and could be less accurate in smaller rural areas and cities \[[24](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref024), [54](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref054), [55](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749#pone.0279749.ref055)\]. Despite these limitations, we believe that the approach used in this paper would still provide valuable insight as it allows for a large scale analysis of fine-grained emotions through openly available web data and could serve as the basis of future research in this direction.  

利用社交媒体和VGI数据作为数据源的其他此类研究也强调了类似的局限性\[53\]（例如，地理标记社交媒体和VGI数据往往集中在大都市，虽然它们在这些地区准确和全面，但在较小的农村地区和城市，它们不太存在，可能不太准确\[24，54，55\]。尽管存在这些局限性，我们相信本文中使用的方法仍将提供有价值的见解，因为它允许通过公开可用的网络数据对细粒度情绪进行大规模分析，并可以作为未来这一方向研究的基础。

## Supporting information  

辅助资料

## References  

参考文献

1.  1.  
    
    1. Ansari MZ, Aziz M, Siddiqui M, Mehra H, Singh K. Analysis of political sentiment orientations on twitter. Procedia Computer Science. 2020;167:1821–1828.  
    
    安萨里·马兹、阿齐兹·马兹、西迪基·马兹、梅赫拉·H、辛格·K. twitter上的政治情绪导向分析。计算机科学。2020; 167：1821 - 1828。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.procs.2020.03.201 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Analysis+of+political+sentiment+orientations+on+twitter+Ansari+2020 "Go to article in Google Scholar")
2.  2.  
    
    2. Choi HJ, Park CH. Emerging topic detection in twitter stream based on high utility pattern mining. Expert systems with applications. 2019;115:27–36.  
    
    Choi HJ，Park CH.基于高效用模式挖掘的twitter流新兴话题检测。专家系统及其应用。2019年; 115：27 - 36。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.eswa.2018.07.051 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Emerging+topic+detection+in+twitter+stream+based+on+high+utility+pattern+mining+Choi+2019 "Go to article in Google Scholar")
3.  3.  
    
    3. Hasan S, Zhan X, Ukkusuri SV. Understanding urban human activity and mobility patterns using large-scale location-based data from online social media. In: Proceedings of the 2nd ACM SIGKDD international workshop on urban computing. ACM; 2013. p. 6.  
    
    哈桑·S、詹·X、乌库苏里SV使用在线社交媒体的大规模基于位置的数据了解城市人类活动和流动模式。在：会议记录的第二届ACM SIGKDD国际研讨会上的城市计算。ACM; 2013年。第6页。
    
4.  4.  
    
    4. Terroso-Saenz F, Muñoz A, Arcas F, Curado M. Can Twitter be a Reliable Proxy to Characterize Nation-wide Human Mobility? A Case Study of Spain. Social Science Computer Review. 2022; p. 08944393211071071.  
    
    特罗索-萨恩斯F、穆尼奥斯A、阿尔卡斯F、库拉多M Twitter能成为描述全国人口流动的可靠代理吗？西班牙的个案研究。社会科学计算机评论。2022年出版;第08944393211071071页。
    -   [View Article  
        
        查看文章](https://doi.org/10.1177/08944393211071071 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Can+Twitter+be+a+Reliable+Proxy+to+Characterize+Nation-wide+Human+Mobility%3F+A+Case+Study+of+Spain+Terroso-Saenz+2022 "Go to article in Google Scholar")
5.  5.  
    
    5.Mislove A. Pulse of the nation: US mood throughout the day inferred from Twitter; 2010. Available from: [http://www.ccs.neu.edu/home/amislove/twittermood/](http://www.ccs.neu.edu/home/amislove/twittermood/).  
    
    错爱A国家脉搏：从Twitter推断出的美国人一整天的情绪;2010.可从以下网址获取：一号。
    
6.  6.  
    
    6. Ashkezari-Toussi S, Kamel M, Sadoghi-Yazdi H. Emotional maps based on social networks data to analyze cities emotional structure and measure their emotional similarity. Cities. 2019;86:113–124.  
    
    0号阿什凯扎里-图西S卡迈勒M萨多吉-亚兹迪H基于社会网络数据的情感地图分析城市的情感结构，度量城市之间的情感相似性。城市。2019年; 86：113 - 124。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.cities.2018.09.009 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Emotional+maps+based+on+social+networks+data+to+analyze+cities+emotional+structure+and+measure+their+emotional+similarity+Ashkezari-Toussi+2019 "Go to article in Google Scholar")
7.  7.  
    
    7.Pauken B, Pradyumn M, Tabrizi N. Tracking happiness of different US cities from tweets. In: International conference on Big Data. Springer; 2018. p. 140–148.  
    
    保肯B，普拉久姆M，大不里士N.从推特上追踪美国不同城市的幸福感。参加：大数据国际会议。施普林格; 2018.第140 - 148页。
    
8.  8.  
    
    8. Mitchell L, Frank MR, Harris KD, Dodds PS, Danforth CM. The geography of happiness: Connecting twitter sentiment and expression, demographics, and objective characteristics of place. PloS one. 2013;8(5):e64417. pmid:23734200  
    
    米切尔L，弗兰克MR，哈里斯KD，多兹PS，丹福斯CM。幸福的地理分布：连接twitter的情感和表达，人口统计学，以及客观的地方特征。一号。2013年; 8（5）：e64417。总办事处编号：二三七三四二零零
    -   [View Article  
        
        查看文章](https://doi.org/10.1371/journal.pone.0064417 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/23734200 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=The+geography+of+happiness%3A+Connecting+twitter+sentiment+and+expression%2C+demographics%2C+and+objective+characteristics+of+place+Mitchell+2013 "Go to article in Google Scholar")
9.  9.  
    
    9. Cao X, MacNaughton P, Deng Z, Yin J, Zhang X, Allen JG. Using twitter to better understand the spatiotemporal patterns of public sentiment: A case study in Massachusetts, USA. International journal of environmental research and public health. 2018;15(2):250. pmid:29393869  
    
    曹X，麦克诺顿P，邓Z，殷J，张X，艾伦JG.利用Twitter更好地了解公众情绪的时空模式：美国马萨诸塞州的案例研究。国际环境研究与公共卫生杂志。2018年; 15（2）：250。项目编号：29393869
    -   [View Article  
        
        查看文章](https://doi.org/10.3390/ijerph15020250 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/29393869 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Using+twitter+to+better+understand+the+spatiotemporal+patterns+of+public+sentiment%3A+A+case+study+in+Massachusetts%2C+USA+Cao+2018 "Go to article in Google Scholar")
10.  10.  
    
    10.Bertrand KZ, Bialik M, Virdee K, Gros A, Bar-Yam Y. Sentiment in new york city: A high resolution spatial and temporal view. arXiv preprint arXiv:13085010. 2013;.  
    
    贝特朗KZ，比利克M，维迪K，格罗斯A，巴亚姆Y。纽约市的情绪：高分辨率空间和时间视图。arXiv预印本arXiv：13085010。2013年;
    
11.  11.  
    
    11. Valdez D, Ten Thij M, Bathina K, Rutter LA, Bollen J, et al. Social media insights into US mental health during the COVID-19 pandemic: Longitudinal analysis of Twitter data. Journal of medical Internet research. 2020;22(12):e21418. pmid:33284783  
    
    Valdez D，Ten Thij M，Bathina K，Rutter LA，Bollen J，et al. 2019冠状病毒病大流行期间社交媒体对美国心理健康的洞察：Twitter数据的纵向分析。医学互联网研究杂志。2020年; 22（12）：e21418。项目编号：33284783
    -   [View Article  
        
        查看文章](https://doi.org/10.2196/21418 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/33284783 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Social+media+insights+into+US+mental+health+during+the+COVID-19+pandemic%3A+Longitudinal+analysis+of+Twitter+data+Valdez+2020 "Go to article in Google Scholar")
12.  12.  
    
    12. Kumar V. Spatiotemporal sentiment variation analysis of geotagged COVID-19 tweets from India using a hybrid deep learning model. Scientific Reports. 2022;12(1):1–14. pmid:35115652  
    
    Kumar V.使用混合深度学习模型对来自印度的地理标记COVID-19推文进行时空情绪变化分析。科学报告。2022年; 12（1）：1 - 14。项目编号：35115652
    -   [View Article  
        
        查看文章](https://doi.org/10.1038/s41598-022-05974-6 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/35115652 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Spatiotemporal+sentiment+variation+analysis+of+geotagged+COVID-19+tweets+from+India+using+a+hybrid+deep+learning+model+Kumar+2022 "Go to article in Google Scholar")
13.  13.  
    
    13. Dai D, Wang R. Space-time surveillance of negative emotions after consecutive terrorist attacks in London. International journal of environmental research and public health. 2020;17(11):4000. pmid:32512901  
    
    0号戴D王R伦敦连续恐怖袭击后的负面情绪时空监控。国际环境研究与公共卫生杂志。2020年; 17（11）：4000。项目编号：32512901
    -   [View Article  
        
        查看文章](https://doi.org/10.3390/ijerph17114000 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/32512901 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Space-time+surveillance+of+negative+emotions+after+consecutive+terrorist+attacks+in+London+Dai+2020 "Go to article in Google Scholar")
14.  14.  
    
    14.Gallegos L, Lerman K, Huang A, Garcia D. Geography of Emotion: Where in a City are People Happier? In: Proceedings of the 25th International Conference Companion on World Wide Web. International World Wide Web Conferences Steering Committee; 2016. p. 569–574.  
    
    加列戈斯·L，勒曼·K，黄·A，加西亚·D.情绪地理学：城市里哪里的人更快乐？见：万维网上第25届国际会议论文集。国际万维网会议指导委员会;2016.第569 - 574页。
    
15.  15.  
    
    15.Guo W, Gupta N, Pogrebna G, Jarvis S. Understanding happiness in cities using Twitter: Jobs, children, and transport. In: Smart Cities Conference (ISC2), 2016 IEEE International. IEEE; 2016. p. 1–7.  
    
    郭伟，古普塔，波格列布纳，贾维斯使用Twitter了解城市幸福感：工作，孩子，交通。参见：2016年IEEE国际智能城市会议（ISC2）。IEEE; 2016年。第1 - 7页。
    
16.  16.  
    
    16.Kim J, Cha M, Sandholm T. Socroutes: safe routes based on tweet sentiments. In: Proceedings of the 23rd International Conference on World Wide Web. ACM; 2014. p. 179–182.  
    
    金·J、查·M、桑德霍姆·T socroutes：基于推文情感的安全路线。收录于：第23届万维网国际会议论文集。ACM; 2014年。第179 - 182页。
    
17.  17.  
    
    17. Chen X, Cho Y, Jang SY. Crime prediction using Twitter sentiment and weather. In: 2015 Systems and Information Engineering Design Symposium. IEEE; 2015. p. 63–68.  
    
    0号陈X、赵Y、张世易使用Twitter情绪和天气预测犯罪。2015年：系统与信息工程设计研讨会。IEEE; 2015年。第63 - 68页。
    
18.  18.  
    
    18. Larsen ME, Boonstra TW, Batterham PJ, O’Dea B, Paris C, Christensen H. We feel: mapping emotion on Twitter. IEEE journal of biomedical and health informatics. 2015;19(4):1246–1252. pmid:25700477  
    
    Larsen ME、Boonstra TW、Batterham PJ、O'Dea B、巴黎C、克里斯滕森H我们的感觉：在Twitter上映射情绪。生物医学与健康信息学杂志。2015年; 19（4）：1246 - 1252。项目编号：25700477
    -   [View Article  
        
        查看文章](https://doi.org/10.1109/JBHI.2015.2403839 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/25700477 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=We+feel%3A+mapping+emotion+on+Twitter+Larsen+2015 "Go to article in Google Scholar")
19.  19.  
    
    19. Guthier B, Alharthi R, Abaalkhail R, El Saddik A. Detection and visualization of emotions in an affect-aware city. In: Proceedings of the 1st International Workshop on Emerging Multimedia Applications and Services for Smart Cities. ACM; 2014. p. 23–28.  
    
    古蒂埃·B阿尔哈蒂·R阿巴哈尔·R萨迪克·A情感感知城市中情绪的检测和可视化。在：第一届国际研讨会的会议记录新兴的多媒体应用和服务的智能城市。ACM; 2014年。第23 - 28页。
    
20.  20.  
    
    20. Lin YR, Margolin D, Wen X. Tracking and analyzing individual distress following terrorist attacks using social media streams. Risk analysis. 2017;37(8):1580–1605. pmid:28556273  
    
    林玉，马格林D，文X。使用社交媒体流跟踪和分析恐怖袭击后的个人痛苦。风险分析。2017年;第37卷（8期）：1580 - 1605页。项目编号：28556273
    -   [View Article  
        
        查看文章](https://doi.org/10.1111/risa.12829 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/28556273 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Tracking+and+analyzing+individual+distress+following+terrorist+attacks+using+social+media+streams+Lin+2017 "Go to article in Google Scholar")
21.  21.  
    
    21. Reyes-Riveros R, Altamirano A, De la Barrera F, Rozas-Vasquez D, Vieli L, Meli P. Linking public urban green spaces and human well-being: A systematic review. Urban Forestry & Urban Greening. 2021;61:127105.  
    
    Reyes-Riveros R，Altamirano A，De la Barrera F，Rozas-Vasquez D，Vieli L，Meli P.将城市公共绿地与人类福祉联系起来：系统综述。城市林业与城市绿化。2021年;第61卷：127105页。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.ufug.2021.127105 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Linking+public+urban+green+spaces+and+human+well-being%3A+A+systematic+review+Reyes-Riveros+2021 "Go to article in Google Scholar")
22.  22.  
    
    22. Hogertz C. Emotions of the urban pedestrian: sensory mapping. Pedestrians quality needs. 2010;31.  
    
    霍格茨角城市行人情绪：感官映射。行人素质需求。2010年;31.
    -   [View Article  
        
        查看文章](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749# "Go to article in CrossRef")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Emotions+of+the+urban+pedestrian%3A+sensory+mapping+Hogertz+2010 "Go to article in Google Scholar")
23.  23.  
    
    23. Resch B, Summa A, Sagl G, Zeile P, Exner JP. Urban emotions Geo semantic emotion extraction from technical sensors, human sensors and crowdsourced data. In: Progress in location-based services 2014. Springer; 2015. p. 199–212.  
    
    研究B、总和A、Sagl G、Zeile P、Exner JP。从技术传感器、人体传感器和众包数据中提取地理语义情感。在：2014年基于位置的服务的进展。施普林格; 2015年。第199 - 212页。
    
24.  24.  
    
    24. Haklay M. How good is volunteered geographical information? A comparative study of OpenStreetMap and Ordnance Survey datasets. Environment and planning B: Planning and design. 2010;37(4):682–703.  
    
    哈克莱M.志愿提供的地理信息有多好？OpenStreetMap和地形测量数据集的比较研究。环境与规划B：规划和设计。2010; 37（4）：682 - 703.
    -   [View Article  
        
        查看文章](https://doi.org/10.1068/b35097 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=How+good+is+volunteered+geographical+information%3F+A+comparative+study+of+OpenStreetMap+and+Ordnance+Survey+datasets+Haklay+2010 "Go to article in Google Scholar")
25.  25.  
    
    25.OpenStreetMap. Open Street Map; 2022. [https://www.openstreetmap.org/](https://www.openstreetmap.org/).  
    
    打开街道地图。开放街道地图;2022. 一号。
    
26.  26.  
    
    26. Zheng S, Zheng J. Assessing the completeness and positional accuracy of OpenStreetMap in China. In: Thematic cartography for the society. Springer; 2014. p. 171–189.  
    
    Zheng S，Zheng J.评估OpenStreetMap在中国的完整性和定位准确性。在：专题制图为社会。施普林格; 2014年。第171 - 189页。
    
27.  27.  
    
    27. Helbich M, Amelunxen C, Neis P, Zipf A. Comparative spatial analysis of positional accuracy of OpenStreetMap and proprietary geodata. Proceedings of GI\_Forum. 2012; p. 24–33.  
    
    海尔比希·M，阿梅伦森·C，尼斯·P，齐普夫·A。OpenStreetMap和专有地理数据定位精度的比较空间分析。GI\_论坛会议记录。2012年;第24 - 33页。
    -   [View Article  
        
        查看文章](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0279749# "Go to article in CrossRef")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Comparative+spatial+analysis+of+positional+accuracy+of+OpenStreetMap+and+proprietary+geodata+Helbich+2012 "Go to article in Google Scholar")
28.  28.  
    
    28.Ordnance Survey GB. Points of interest classification scheme; 2021. [https://www.ordnancesurvey.co.uk/business-government/tools-support/points-of-interest-support](https://www.ordnancesurvey.co.uk/business-government/tools-support/points-of-interest-support).  
    
    英国地形测量局。兴趣点分类方案;2021. 一号。
    
29.  29.  
    
    29.Open Street Map Wiki. Tags-Open Street Map Wiki; 2022. [https://wiki.openstreetmap.org/wiki/Tags](https://wiki.openstreetmap.org/wiki/Tags).  
    
    打开街道地图Wiki。标签-打开街道地图Wiki;2022. 一号。
    
30.  30.  
    
    30.Kruspe A, Häberle M, Hoffmann EJ, Rode-Hasinger S, Abdulahhad K, Zhu XX. Changes in Twitter geolocations: Insights and suggestions for future usage. arXiv preprint arXiv:210812251. 2021;.  
    
    克鲁斯佩A，哈贝尔M，霍夫曼EJ，罗德-哈辛格S，阿卜杜拉哈德K，朱XX。Twitter地理位置的变化：对未来使用的见解和建议。arXiv预印本arXiv：210812251。2021年;
    
31.  31.  
    
    31. Plunz RA, Zhou Y, Vintimilla MIC, Mckeown K, Yu T, Uguccioni L, et al. Twitter sentiment in New York City parks as measure of well-being. Landscape and urban planning. 2019;189:235–246.  
    
    Plunz RA，Zhou Y，Vintimilla MIC，Mckeown K，Yu T，Uguccioni L，et al.《纽约市公园的Twitter情绪作为幸福感的衡量标准》。景观和城市规划。2019年; 189：235 - 246。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.landurbplan.2019.04.024 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Twitter+sentiment+in+New+York+City+parks+as+measure+of+well-being+Plunz+2019 "Go to article in Google Scholar")
32.  32.  
    
    32. Yang C, Srinivasan P. Life satisfaction and the pursuit of happiness on Twitter. PloS one. 2016;11(3):e0150881. pmid:26982323  
    
    Yang C，Srinivasan P.生活满意度和在Twitter上追求幸福。一号。2016年; 11（3）：e0150881。项目编号：26982323
    -   [View Article  
        
        查看文章](https://doi.org/10.1371/journal.pone.0150881 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/26982323 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Life+satisfaction+and+the+pursuit+of+happiness+on+Twitter+Yang+2016 "Go to article in Google Scholar")
33.  33.  
    
    33.Branz L, Brockmann P. Sentiment analysis of twitter data: towards filtering, analyzing and interpreting social network data. In: Proceedings of the 12th ACM International Conference on Distributed and Event-based Systems; 2018. p. 238–241.  
    
    Branz L，Brockmann P.推特数据的情绪分析：过滤、分析和解释社交网络数据。第12届ACM国际分布式和事件基系统会议文集;2018.第238 - 241页。
    
34.  34.  
    
    34. Da Silva NF, Hruschka ER, Hruschka ER Jr. Tweet sentiment analysis with classifier ensembles. Decision Support Systems. 2014;66:170–179.  
    
    达席尔瓦NF，赫鲁施卡急诊室，小赫鲁施卡急诊室基于分类器集成的推文情感分析。决策支持系统。2014年; 66：170 - 179.
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.dss.2014.07.003 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Tweet+sentiment+analysis+with+classifier+ensembles+Da+Silva+2014 "Go to article in Google Scholar")
35.  35.  
    
    35.Mohammad S. Portable Features for Classifying Emotional Text. In: Proceedings of the 2012 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies. NAACL HLT’12.  
    
    穆罕默德·S情感文本分类的可移植特征。在：会议记录的2012年会议北美分会的计算语言学协会：人类语言技术。NAACL HLT '12。  
    
    Stroudsburg, PA, USA: Association for Computational Linguistics; 2012. p. 587–591. Available from: [http://dl.acm.org/citation.cfm?id = 2382029.2382123](http://dl.acm.org/citation.cfm?id%20=%202382029.2382123).  
    
    美国宾夕法尼亚州斯特劳兹堡：计算语言学协会;2012.第587 - 591页。可从以下网址获取：零号。
    
36.  36.  
    
    36. Plutchik R. The nature of emotions: Human emotions have deep evolutionary roots, a fact that may explain their complexity and provide tools for clinical practice. American scientist. 2001;89(4):344–350.  
    
    普卢奇克河情感的本质：人类的情感有着深刻的进化根源，这一事实可以解释情感的复杂性，并为临床实践提供工具。美国科学家。2001; 89（4）：344 - 350.
    -   [View Article  
        
        查看文章](https://doi.org/10.1511/2001.4.344 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=The+nature+of+emotions%3A+Human+emotions+have+deep+evolutionary+roots%2C+a+fact+that+may+explain+their+complexity+and+provide+tools+for+clinical+practice+Plutchik+2001 "Go to article in Google Scholar")
37.  37.  
    
    37. Pennington J, Socher R, Manning CD. GloVe: Global Vectors for Word Representation. In: Empirical Methods in Natural Language Processing (EM_NLP_); 2014. p. 1532–1543. [http://www.aclweb.org/anthology/D14-1162](http://www.aclweb.org/anthology/D14-1162).  
    
    潘宁顿J，索赫尔R，曼宁CD。GloVe：用于单词表示的全局向量。自然语言处理的经验方法（EM_NLP_）;2014.第1532 - 1543页。 一号。
    
38.  38.  
    
    38.Bravo-Marquez F, Frank E, Mohammad SM, Pfahringer B. Determining word-emotion associations from tweets by multi-label classification. In: Web Intelligence (WI), 2016 IEEE/WIC/ACM International Conference on. IEEE; 2016. p. 536–539.  
    
    Bravo-Marquez F，Frank E，Mohammad SM，Pfahringer B。Determining word-emotion associations from tweets by multi-label classification。In：Web Intelligence(WI)，2016 IEEE/WIC/ACM International Conference on。IEEE;2016.第536-539页。
    
39.  39.  
    
    39.Agarwal A, Toshniwal D. Application of lexicon based approach in sentiment analysis for short tweets. In: 2018 International Conference on Advances in Computing and Communication Engineering (ICACCE). IEEE; 2018. p. 189–193.  
    
    Agarwal A，Toshniwal D。基于词库的方法在短文情绪分析中的应用。In：2018 International Conference on Advances in Computing and Communication Engineering(ICACCE)。IEEE;2018年。第189-193页。
    
40.  40.  
    
    40.Kudugunta S, Ferrara E. Deep Neural Networks for Bot Detection. arXiv preprint arXiv:180204289. 2018;.  
    
    Kudugunta S，Ferrara E。Deep Neural Networks for Bot Detection。arXiv preprint arXiv：180204289。2018年;。
    
41.  41.  
    
    41. Tukey JW. Exploratory data analysis. vol. 2. Reading, Mass.; 1977.  
    
    图基JW.探索性数据分析。第2卷。马萨诸塞州雷丁1977.
    
42.  42.  
    
    42. Lin YR, Margolin D. The ripple of fear, sympathy and solidarity during the Boston bombings. EPJ Data Science. 2014;3(1):31.  
    
    0号林·伊尔，马戈林·D波士顿爆炸案中恐惧、同情和团结的涟漪。EPJ数据科学2014年3月1日：31。
    -   [View Article  
        
        查看文章](https://doi.org/10.1140/epjds/s13688-014-0031-z "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=The+ripple+of+fear%2C+sympathy+and+solidarity+during+the+Boston+bombings+Lin+2014 "Go to article in Google Scholar")
43.  43.  
    
    43. Curini L, Iacus S, Canova L. Measuring idiosyncratic happiness through the analysis of twitter: An application to the italian case. Social Indicators Research. 2015;121(2):525–542.  
    
    库里尼湖、亚克斯湖、卡诺瓦湖通过对Twitter的分析来衡量特质幸福感：适用于意大利案件。社会指标研究。2015年; 121（2）：525 - 542。
    -   [View Article  
        
        查看文章](https://doi.org/10.1007/s11205-014-0646-2 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Measuring+idiosyncratic+happiness+through+the+analysis+of+twitter%3A+An+application+to+the+italian+case+Curini+2015 "Go to article in Google Scholar")
44.  44.  
    
    44. Dodds PS, Harris KD, Kloumann IM, Bliss CA, Danforth CM. Temporal patterns of happiness and information in a global social network: Hedonometrics and Twitter. PloS one. 2011;6(12):e26752. pmid:22163266  
    
    多兹PS，哈里斯KD，克鲁曼IM，布利斯CA，丹福斯CM。全球社交网络中快乐和信息的时间模式：心理测量学和推特。一号。2011年; 6（12）：e26752。项目编号：二二一六三二六六
    -   [View Article  
        
        查看文章](https://doi.org/10.1371/journal.pone.0026752 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/22163266 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Temporal+patterns+of+happiness+and+information+in+a+global+social+network%3A+Hedonometrics+and+Twitter+Dodds+2011 "Go to article in Google Scholar")
45.  45.  
    
    45. Trampe D, Quoidbach J, Taquet M. Emotions in everyday life. PloS one. 2015;10(12):e0145450. pmid:26698124  
    
    0号川普·D科伊德巴赫·J塔奎特·M日常生活中的情绪。一号。2015年; 10月（12日）：e0145450。项目编号：26698124
    -   [View Article  
        
        查看文章](https://doi.org/10.1371/journal.pone.0145450 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/26698124 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Emotions+in+everyday+life+Trampe+2015 "Go to article in Google Scholar")
46.  46.  
    
    46. Yu Y, Wang X. World Cup 2014 in the Twitter World: A big data analysis of sentiments in US sports fans’ tweets. Computers in Human Behavior. 2015;48:392–400.  
    
    于Y，王X。2014年世界杯在Twitter世界：大数据分析美国体育迷推文中的情绪。计算机在人类行为中的应用。2015年; 48：392 - 400。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.chb.2015.01.075 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=World+Cup+2014+in+the+Twitter+World%3A+A+big+data+analysis+of+sentiments+in+US+sports+fans%E2%80%99+tweets+Yu+2015 "Go to article in Google Scholar")
47.  47.  
    
    47.Li M, Ch’ng E, Chong A, See S. The new eye of smart city: Novel citizen Sentiment Analysis in Twitter. In: Audio, Language and Image Processing (ICALIP), 2016 International Conference on. IEEE; 2016. p. 557–562.  
    
    李明，昌娥，崇阿，见S。智慧城市新眼：Twitter中的新公民情绪分析。参加：音频、语言和图像处理（ICALIP），2016年IEEE国际会议;2016.第557 - 562页。
    
48.  48\. Blank G, Lutz C. Representativeness of social media in great britain: investigating Facebook, Linkedin, Twitter, Pinterest, Google+, and Instagram. American Behavioral Scientist. 2017;61(7):741–756.  
    
    空白G，Lutz C。英国社交媒体的代表性：调查Facebook、LinkedIn、Twitter、Pinterest、Google+和Instagram。美国行为科学家。2017年;第61卷第7期：741 - 756页。
    -   [View Article  
        
        查看文章](https://doi.org/10.1177/0002764217717559 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Representativeness+of+social+media+in+great+britain%3A+investigating+Facebook%2C+Linkedin%2C+Twitter%2C+Pinterest%2C+Google%2B%2C+and+Instagram+Blank+2017 "Go to article in Google Scholar")
49.  49.  
    
    49.Smith A, Anderson M. Social Media Use in 2018. Pew Research Report. 2018;.  
    
    #0史密斯A安德森M 2018年社交媒体使用情况。皮尤研究报告。2018年;
    
50.  50.  
    
    50. Jiang Y, Li Z, Ye X. Understanding demographic and socioeconomic biases of geotagged Twitter users at the county level. Cartography and geographic information science. 2019;46(3):228–242.  
    
    姜勇，李泽，叶X了解县一级地理标记Twitter用户的人口和社会经济偏见。制图学与地理信息科学。2019年;第46卷第3期：228-242页。
    -   [View Article](https://doi.org/10.1080/15230406.2018.1434834 "Go to article")
    -   [Google Scholar](http://scholar.google.com/scholar?q=Understanding+demographic+and+socioeconomic+biases+of+geotagged+Twitter+users+at+the+county+level+Jiang+2019 "Go to article in Google Scholar")
51.  51.  
    
    51. Sloan L, Morgan J. Who tweets with their location? Understanding the relationship between demographic characteristics and the use of geoservices and geotagging on Twitter. PloS one. 2015;10(11):e0142209. pmid:26544601  
    
    Sloan L，Morgan J.谁会在Twitter上发布自己的位置？了解人口特征与地理服务和Twitter地理标记使用之间的关系。一号。2015年; 10（11）：e0142209。项目编号：26544601
    -   [View Article](https://doi.org/10.1371/journal.pone.0142209 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/26544601 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Who+tweets+with+their+location%3F+Understanding+the+relationship+between+demographic+characteristics+and+the+use+of+geoservices+and+geotagging+on+Twitter+Sloan+2015 "Go to article in Google Scholar")
52.  52.  
    
    52. Nguyen QC, Li D, Meng HW, Kath S, Nsoesie E, Li F, et al. Building a national neighborhood dataset from geotagged Twitter data for indicators of happiness, diet, and physical activity. JMIR public health and surveillance. 2016;2(2):e5869. pmid:27751984  
    
    Nguyen QC，Li D，Meng HW，Kath S，Nsoesie E，Li F，et al.根据带有地理标记的Twitter数据构建全国社区数据集，以获取幸福感、饮食和身体活动指标。JMIR公共卫生和监测。2016年; 2（2）：e5869。项目编号：27751984
    -   [View Article  
        
        查看文章](https://doi.org/10.2196/publichealth.5869 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/27751984 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Building+a+national+neighborhood+dataset+from+geotagged+Twitter+data+for+indicators+of+happiness%2C+diet%2C+and+physical+activity+Nguyen+2016 "Go to article in Google Scholar")
53.  53.  
    
    53. Wakamiya S, Kawai Y, Aramaki E, et al. Twitter-based influenza detection after flu peak via tweets with indirect information: text mining study. JMIR public health and surveillance. 2018;4(3):e8627. pmid:30274968  
    
    Wakamiya S，Kawai Y，Aramaki E，et al.流感高峰后通过包含间接信息的推文进行基于推文的流感检测：文本挖掘研究。JMIR公共卫生和监测。2018年;第4（3）期：e8627。项目编号：30274968
    -   [View Article  
        
        查看文章](https://doi.org/10.2196/publichealth.8627 "Go to article")
    -   [PubMed/NCBI  
        
        PubMed/NCBI](http://www.ncbi.nlm.nih.gov/pubmed/30274968 "Go to article in PubMed")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Twitter-based+influenza+detection+after+flu+peak+via+tweets+with+indirect+information%3A+text+mining+study+Wakamiya+2018 "Go to article in Google Scholar")
54.  54.  
    
    54.Hecht B, Stephens M. A tale of cities: Urban biases in volunteered geographic information. In: proceedings of the international AAAI conference on web and social media. vol. 8; 2014. p. 197–205.  
    
    赫克特·B、斯蒂芬斯·M城市的故事：自愿提供的地理信息中的城市偏见。在：会议记录的国际AAAI会议上的网络和社交媒体。第8卷; 2014年。第197 - 205页。
    
55.  55.  
    
    55. Carley KM, Malik M, Landwehr PM, Pfeffer J, Kowalchuck M. Crowd sourcing disaster management: The complex nature of Twitter usage in Padang Indonesia. Safety science. 2016;90:48–61.  
    
    卡利KM，马利克M，兰德韦尔PM，普费弗J，科瓦尔查克M。众包灾难管理：印度尼西亚巴东地区Twitter使用的复杂性。安全科学。2016年; 90：48 - 61。
    -   [View Article  
        
        查看文章](https://doi.org/10.1016/j.ssci.2016.04.002 "Go to article")
    -   [Google Scholar  
        
        谷歌学术](http://scholar.google.com/scholar?q=Crowd+sourcing+disaster+management%3A+The+complex+nature+of+Twitter+usage+in+Padang+Indonesia+Carley+2016 "Go to article in Google Scholar")
