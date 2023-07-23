---
title: "CTO 洞察 - 第 133 期 - 作者：Tosho Trajanov"
date: 2023-07-23T23:16:36+08:00
updated: 2023-07-23T23:16:36+08:00
taxonomies:
  tags: []
extra:
  source: https://insights.toshotrajanov.com/p/cto-insights-issue-133?utm_source=substack&utm_medium=email
  hostname: insights.toshotrajanov.com
  author: Tosho Trajanov
  original_title: "CTO Insights - Issue #133"
  original_lang: en
---

Welcome to CTO Insights #133! 欢迎收看 CTO Insights #133！

This newsletter is delivering top-notch Software Engineering and Technical Leadership content, making your weekly reading more insightful and enjoyable.  

本通讯提供一流的软件工程和技术领导力内容，使您每周的阅读更有见地和乐趣。

This week’s favorite - _Right-sizing Your Technology Team_ & _Where are all the laid-off software developers going?_  

本周最爱--合理调整技术团队规模与被解雇的软件开发人员都去哪儿了？

CTO Insights is community-driven and thrives on your input. If you find value in what you read, I encourage you to share it with your friends in tech and your wider community, whether it be via social media, slack, teams, or any other channel you frequent.  

CTO Insights是由社区驱动的，并在你的投入下茁壮成长。如果你在阅读中发现价值，我鼓励你与你的技术朋友和更广泛的社区分享，无论是通过社交媒体、Slack、团队，还是你经常使用的任何其他渠道。

[Share CTO Insights 分享首席技术官的见解](https://insights.toshotrajanov.com/?utm_source=substack&utm_medium=email&utm_content=share&action=share)

Together, we can make every edition of CTO Insights a wealth of knowledge for all!  

我们可以一起使每一期的CTO Insights成为所有人的知识财富!

> As part of strengthening the value for the community, at Adeva we run a questionnaire for product and tech leaders to understand their pain points while hiring talent for their organizations.  
> 
> 作为加强社区价值的一部分，Adeva 为产品和技术领导者提供了一份调查问卷，以了解他们在为企业招聘人才时的痛点。

Please spare 5-7 minutes to complete this survey. Your responses will remain confidential, used solely for market research purposes. The questionnaire is available on the following [link](https://adeva.qualtrics.com/jfe/form/SV_8wc89pXOJND492S).  

请抽出 5-7 分钟完成本调查。您的回答将被保密，仅用于市场调研目的。问卷可从以下链接获取 .

[Share Your Insights 分享您的见解](https://adeva.qualtrics.com/jfe/form/SV_8wc89pXOJND492S)

Read about the journey of building an experimental AI co-pilot for product strategy and generative ideation called “Boba”.  

了解我们如何为产品战略和生成式构思构建名为 "波巴 "的实验性人工智能辅助驾驶员。

The story contains some useful lessons on how to build AI applications formulated in terms of patterns. These patterns allow an application to help the user interact more effectively with a Large-Language Model (LLM), orchestrating prompts to gain better results, helping the user navigate a path of an intricate conversational flow, and integrating knowledge that the LLM doesn't have available.  

这个故事包含了一些有用的经验，告诉我们如何根据模式构建人工智能应用程序。通过这些模式，应用程序可以帮助用户更有效地与大型语言模型（LLM）进行交互，协调提示以获得更好的结果，帮助用户浏览错综复杂的对话流程，并整合 LLM 所不具备的知识。

Deployment patterns, like canary releases, blue/green and red/black deployments, feature toggles, A/B testing, and dark launches, offer automated ways to roll out app features while reducing downtime.  

金丝雀发布、蓝/绿和红/黑部署、功能切换、A/B 测试和暗启动等部署模式提供了自动推出应用程序功能的方法，同时减少了停机时间。

CD in software development involves using strategies such as feature flags, blue/green deployments, and permission systems, supported by robust test automation, to deliver quality software consistently. Tools such as Jenkins, Azure DevOps, CircleCI, and GitLab aid in this process. This story dives deep into each of these details.  

软件开发中的 CD 涉及使用功能标志、蓝/绿部署和权限系统等策略，并辅以强大的自动化测试，以始终如一地交付高质量的软件。Jenkins、Azure DevOps、CircleCI 和 GitLab 等工具都有助于这一过程。本故事将深入探讨这些细节。

Determining the right size of your technology team isn't just about the number of developers; it's about their effectiveness in meeting business outcomes and their autonomy in adding value. It's crucial to minimize waste in software engineering processes, understand user needs, and ensure your software is delivering the desired results.  

确定技术团队的适当规模并不仅仅是开发人员的数量问题，还关系到他们在实现业务成果方面的效率以及在增加价值方面的自主性。这对于最大限度地减少软件工程流程中的浪费、了解用户需求以及确保您的软件交付预期成果至关重要。

Internal and legacy software maintenance's hidden value should also be recognized and optimized. When software value starts to decline, it's essential to respond to changing user needs and market dynamics and improve feedback loops. Through these considerations, you can ensure you have an optimally sized and shaped tech team ready to deliver consistent results.  

还应认识到内部和传统软件维护的隐藏价值，并对其进行优化。当软件价值开始下降时，必须对不断变化的用户需求和市场动态做出反应，并改进反馈回路。通过这些考虑因素，您可以确保拥有一支规模适当、结构合理的技术团队，随时准备提供一致的结果。

I wrote this article that explores the concept of a Fractional CTO, a part-time tech leader who offers strategic guidance at a fraction of the cost of a full-time CTO.  

我撰写的这篇文章探讨了 "兼职首席技术官"（Fractional CTO）的概念，即兼职技术领导者，他们提供战略指导的成本仅为全职首席技术官的一小部分。

It discusses their benefits, potential drawbacks and identifies scenarios where their engagement is most beneficial. The piece also advises businesses on how to align their choice with strategic objectives and specific needs.  

文章讨论了它们的优点、潜在缺点，并确定了在哪些情况下使用它们最为有利。文章还建议企业如何根据战略目标和具体需求进行选择。

The blog post from Aha! presents a more organized way to manage customer research data.  

来自 Aha！的博文介绍了一种更有条理的客户研究数据管理方法。

It helps product teams collect, analyze and prioritize customer insights in a visual, easy-to-understand manner. The system allows for creating cards for each insight, tagging them with relevant attributes, linking them to other records like features and ideas, and then grouping and prioritizing them.  

它能帮助产品团队以可视化、易于理解的方式收集、分析和优先处理客户洞察。该系统允许为每个洞察创建卡片，用相关属性标记它们，将它们链接到其他记录（如功能和想法），然后对它们进行分组和优先排序。

Chronon is Airbnb's innovative solution to address feature management issues encountered by machine learning engineers. It centralizes data computation for model training and inference, ensuring consistency and enabling efficient feature generation.  

Chronon 是 Airbnb 为解决机器学习工程师遇到的特征管理问题而推出的创新解决方案。它集中了用于模型训练和推理的数据计算，确保了一致性并实现了高效的特征生成。

With capabilities such as data ingestion from various sources, transformation via SQL-like operations, and producing both real-time and batch results, Chronon significantly streamlines feature engineering, transforming the landscape of machine learning at Airbnb.  

Chronon 具有从各种来源摄取数据、通过类似 SQL 的操作进行转换以及生成实时和批量结果等功能，大大简化了特征工程，改变了 Airbnb 机器学习的面貌。

In this blog post, Durga Krishnan, an Engineering Manager at Deliveroo, discusses her professional journey and the role of resilience.  

在这篇博文中，Deliveroo 的工程经理 Durga Krishnan 讨论了她的职业历程和复原力的作用。

She highlights her challenges as a woman in Tech, the strategies she developed to overcome them, and the importance of personal growth. She further provides advice for other minorities in Tech, emphasizing authenticity, mental health, and personal strengths, while also stressing the need for supportive and inclusive work environments, particularly for neurodivergent individuals.  

她强调了自己作为科技界女性所面临的挑战、克服挑战的策略以及个人成长的重要性。她还为科技界的其他少数群体提供了建议，强调了真实性、心理健康和个人优势，同时还强调了支持性和包容性工作环境的必要性，尤其是对神经变异者而言。

2023 has seen significant tech sector layoffs, predominantly from major companies like Meta, Alphabet, Microsoft, Amazon, and Apple. Despite this, hiring speed has increased as companies aim to utilize the available talent pool.  

2023 年，科技行业大幅裁员，主要来自 Meta、Alphabet、微软、亚马逊和苹果等大公司。尽管如此，由于各公司都希望利用现有的人才库，因此招聘速度有所加快。

Many engineers, rather than downgrading, are seeking similar or higher-level roles. Non-tech companies are presented with an opportunity to enhance their engineering quality, though their outreach needs improvement. Notably, many laid-off tech workers are starting their own businesses.  

许多工程师非但没有降级，反而在寻求类似或更高级别的职位。非技术公司面临着提高工程质量的机会，尽管他们的推广工作需要改进。值得注意的是，许多下岗的科技人员正在创业。

Thanks for making it this far! 🙏  

谢谢你能走到今天!🙏

I hope you enjoyed this week’s issue. Use the thumbs up/down buttons to rate and don’t forget to share the newsletter with fellows.  

我希望你喜欢本周的期刊。使用大拇指向上/向下按钮进行评价，不要忘记与伙伴们分享通讯。

### Subscribe to CTO Insights 订阅《首席技术官观察 首席技术官见解CTO Insights

By Tosho Trajanov · Launched 7 months ago  

作者：Tosho Trajanov - 7 个月前发布 \- 7 个月前推出 · Launched 7 months agoLaunched 7 months ago

Software Engineering & Technical Leadership.  

软件工程与技术领导。
