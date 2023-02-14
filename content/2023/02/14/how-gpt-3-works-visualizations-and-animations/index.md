---
title: GPT 3的工作原理-可视化和动画
date: 2023-02-14T13:34:10.000Z
updated: 2023-02-14T13:34:10.000Z
taxonomies:
  tags:
    - ChatGPT
extra:
  source: https://jalammar.github.io/how-gpt3-works-visualizations-animations/
  hostname: jalammar.github.io
  author: Jay Alammar
  original_title: How GPT3 Works - Visualizations and Animations
  original_lang: en

---

Discussions: [Hacker News (397 points, 97 comments)](https://news.ycombinator.com/item?id=23967887), [Reddit r/MachineLearning (247 points, 27 comments)  

讨论：黑客新闻（397分，97条评论），Reddit r/机器学习（247分，27条评论）](https://www.reddit.com/r/MachineLearning/comments/hwxn26/p_how_gpt3_works_visuals_and_animations/)  

Translations: [German](https://www.arnevogel.com/wie-gpt3-funktioniert/), [Korean](https://chloamme.github.io/2021/12/18/how-gpt3-works-visualizations-animations-korean.html), [Chinese (Simplified)](https://blogcn.acacess.com/how-gpt3-works-visualizations-and-animations-zhong-yi), [Russian  

译文：德语、韩语、简体中文、俄语](https://habr.com/ru/post/514698/)  

The tech world is [abuzz](https://www.theverge.com/21346343/gpt-3-explainer-openai-examples-errors-agi-potential) with GPT3 hype. Massive language models (like GPT3) are starting to surprise us with their abilities.  

科技界充斥着GPT3的炒作。大规模语言模型（如GPT3）的能力开始让我们吃惊。  

While not yet completely reliable for most businesses to put in front of their customers, these models are showing sparks of cleverness that are sure to accelerate the march of automation and the possibilities of intelligent computer systems.  

虽然还不是完全可靠的大多数企业摆在他们的客户面前，这些模型正在显示聪明的火花，肯定会加快自动化的步伐和智能计算机系统的可能性。  

Let’s remove the aura of mystery around GPT3 and learn how it’s trained and how it works.  

让我们揭开GPT3的神秘面纱，了解它是如何训练和工作的。

<iframe width="560" height="315" src="https://www.youtube.com/embed/MQnJZuBGmSQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" data-immersive-translate-effect="1"></iframe>

A trained language model generates text.  

训练的语言模型生成文本。

We can optionally pass it some text as input, which influences its output.  

我们可以选择性地向它传递一些文本作为输入，这会影响它的输出。

The output is generated from what the model “learned” during its training period where it scanned vast amounts of text.  

输出是由模型在训练期间扫描大量文本时“学习”的内容生成的。

![](01-gpt3-language-model-overview.gif)  

Training is the process of exposing the model to lots of text. That process has been completed. All the experiments you see now are from that one trained model. It was estimated to cost 355 GPU years and cost $4.6m.  

训练是将模型暴露于大量文本的过程。这一进程已经完成。你现在看到的所有实验都来自于这个训练过的模型。据估计，它需要花费355个GPU年和460万美元。

![](02-gpt3-training-language-model.gif)  

The dataset of 300 billion tokens of text is used to generate training examples for the model. For example, these are three training examples generated from the one sentence at the top.  

3000亿个文本标记的数据集用于生成模型的训练示例。例如，这是从顶部的一个句子生成的三个训练示例。

You can see how you can slide a window across all the text and make lots of examples.  

你可以看到你如何滑动一个窗口跨越所有的文本，并作出了大量的例子。

![](gpt3-training-examples-sliding-window.png)  

The model is presented with an example. We only show it the features and ask it to predict the next word.  

最后给出了一个算例。我们只给它看特征，让它预测下一个单词。

The model’s prediction will be wrong. We calculate the error in its prediction and update the model so next time it makes a better prediction.  

模型的预测将会是错误的。我们计算其预测中的误差并更新模型，以便下一次做出更好的预测。

Repeat millions of times  

重复数百万次

![](03-gpt3-training-step-back-prop.gif)  

Now let’s look at these same steps with a bit more detail.  

现在，让我们更详细地了解这些相同的步骤。

GPT3 actually generates output one token at a time (let’s assume a token is a word for now).  

GPT3实际上一次生成一个token（现在假设token是一个单词）。

![](04-gpt3-generate-tokens-output.gif)  

Please note: This is a description of how GPT-3 works and not a discussion of what is novel about it (which is mainly the ridiculously large scale). The architecture is a transformer decoder model based on this paper https://arxiv.org/pdf/1801.10198.pdf  

请注意：这是对GPT-3如何工作的描述，而不是对它有什么新奇之处的讨论（主要是可笑的大规模）。该架构是基于本文www.example.com的变换器解码器模型https://arxiv.org/pdf/1801.10198.pdf

GPT3 is MASSIVE. It encodes what it learns from training in 175 billion numbers (called parameters). These numbers are used to calculate which token to generate at each run.  

GPT3是巨大的。它将从训练中学到的知识编码成1750亿个数字（称为参数）。这些数字用于计算每次运行时生成哪个令牌。

The untrained model starts with random parameters. Training finds values that lead to better predictions.  

未经训练的模型从随机参数开始。训练会查找导致更好预测的值。

![](gpt3-parameters-weights.png)  

These numbers are part of hundreds of matrices inside the model. Prediction is mostly a lot of matrix multiplication.  

这些数字是模型中数百个矩阵的一部分。预测主要是大量的矩阵乘法。

In my [Intro to AI on YouTube](https://youtube.com/watch?v=mSTCzNgDJy4), I showed a simple ML model with one parameter. A good start to unpack this 175B monstrosity.  

在YouTube上的《人工智能入门》中，我展示了一个带有一个参数的简单ML模型。一个很好的开始，打开这个175B怪物。

To shed light on how these parameters are distributed and used, we’ll need to open the model and look inside.  

为了阐明这些参数是如何分布和使用的，我们需要打开模型并查看内部。

GPT3 is 2048 tokens wide. That is its “context window”. That means it has 2048 tracks along which tokens are processed.  

GPT3有2048个令牌宽。这就是它的“上下文窗口”。这意味着它有2048条处理代币的轨道。

![](05-gpt3-generate-output-context-window.gif)  

Let’s follow the purple track. How does a system process the word “robotics” and produce “A”?  

我们沿着紫色的轨道走。一个系统是如何处理“机器人”这个词并产生“A”的？

High-level steps:  

高级别步骤：

1.  Convert the word to [a vector (list of numbers) representing the word](https://jalammar.github.io/illustrated-word2vec/)  
    
    将单词转换为表示单词的向量（数字列表
2.  Compute prediction  
    
    计算预测
3.  Convert resulting vector to word  
    
    将生成的矢量转换为单词

![](06-gpt3-embedding.gif)  

The important calculations of the GPT3 occur inside its stack of 96 transformer decoder layers.  

GPT3的重要计算发生在其96个变换器解码器层的栈内。

See all these layers? This is the “depth” in “deep learning”.  

看到这些层了吗？这就是“深度学习”中的“深度”。

Each of these layers has its own 1.8B parameter to make its calculations. That is where the “magic” happens. This is a high-level view of that process:  

这些层中的每一层都有自己的1.8B参数来进行计算。这就是“奇迹”发生的地方。以下是该过程的高级视图：

![](07-gpt3-processing-transformer-blocks.gif)  

You can see a detailed explanation of everything inside the decoder in my blog post [The Illustrated GPT2](https://jalammar.github.io/illustrated-gpt2/).  

您可以在我的博客文章The Illustrated GPT2中看到解码器内部所有内容的详细解释。

The difference with GPT3 is the alternating dense and [sparse self-attention layers](https://arxiv.org/pdf/1904.10509.pdf).  

与GPT3的不同之处在于交替的密集和稀疏的自我注意层。

This is an X-ray of an input and response (“Okay human”) within GPT3. Notice how every token flows through the entire layer stack. We don’t care about the output of the first words. When the input is done, we start caring about the output. We feed every word back into the model.  

这是GPT3中输入和响应（“正常人”）的X射线。请注意每个令牌如何流经整个层堆栈。我们不关心第一个单词的输出。当输入完成后，我们开始关心输出。我们把每一个字都反馈到模型中。

![](08-gpt3-tokens-transformer-blocks.gif)  

In the [React code generation example](https://twitter.com/sharifshameem/status/1284421499915403264), the description would be the input prompt (in green), in addition to a couple of examples of description=>code, I believe. And the react code would be generated like the pink tokens here token after token.  

在React代码生成示例中，描述将是输入提示符（绿色），此外还有几个description =〉code的示例。反应代码会像这里的粉色标记一样一个接一个地生成。

My assumption is that the priming examples and the description are appended as input, with specific tokens separating examples and the results. Then fed into the model.  

我的假设是，启动例子和描述作为输入被附加，用特定的标记分隔例子和结果。然后输入模型。

![](09-gpt3-generating-react-code-example.gif)  

It’s impressive that this works like this. Because you just wait until fine-tuning is rolled out for the GPT3. The possibilities will be even more amazing.  

令人印象深刻的是它是这样工作的。因为您只需等待GPT3的微调推出。可能性将更加惊人。

Fine-tuning actually updates the model’s weights to make the model better at a certain task.  

微调实际上会更新模型的权重，以使模型更好地完成特定任务。

![](10-gpt3-fine-tuning.gif)
