# hi, DemoChen's Clip

 <img src="./cover.jpg" width = "" height = "400" alt="DemoChen's Clip" />

 <br/>

在《[高效阅读英语信息的方法](https://demochen.com/posts/111501/)》中提到，我英语信息源占比越来越大，同时在 [immersive-translate](https://github.com/immersive-translate/immersive-translate ) 的加持下，我逐渐喜欢上看英语内容，但是对自己阅读过的文章希望能将 **「双语」版本** 保存下来，供后续查阅。

于是，我想到了两种方式，分别是保存到稍后读（[Readwise Reader](https://blog.readwise.io/readwise-reading-app/)）中或者下载到本地；前者会造成信息冗余（加上对英语不够熟悉会忘记关键词），后者会加重本地管理压力，都不是满意的方案。

在群里和 [@OwenYoung](https://www.owenyoung.com/about/ ) 表达了想法，他和我说：前两天刚好搭建了一个类似项目 [Owen's Clip](https://clip.owenyoung.com/ )，于是我申请复刻（白嫖）了。

经过不到 1 小时的折腾，站在巨人的肩膀上，我的 **DemoChen's Clip** 复刻成功。

工作流程：

- 浏览网页时用 [immersive-translate](https://github.com/immersive-translate/immersive-translate ) 完成中英文对照翻译；
- 如有必要，再用 [markdownload](https://github.com/theowenyoung/markdownload ) 插件将其下载到本站对应目录；
- 接着，通过 Git 将文章对应文件提交至[本站仓库](https://github.com/helloChenLei/clip);
- 最后，[Vercel](https://vercel.com/) 会自动化完成部署。

说明：

1. 99.78% 的文章会提供**中英文双语版本**； 
2. 本站内容均不是原创，仅保存自己的阅读记录；
3. 更新频次不定，可能 3 篇/天，也可能 1 篇/周，有空就更；
4. 如有侵权，联系删除；邮箱：i#demochen.com (将`#`换成`@`)。

> RSS 订阅：[https://clip.demochen.com/feed.xml](https://clip.demochen.com/feed.xml)
