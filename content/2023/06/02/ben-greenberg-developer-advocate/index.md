---
title: "使用 GitHub Actions 让你的 GitHub 配置文件自动化"
date: 2023-06-02T16:40:02+08:00
updated: 2023-06-02T16:40:02+08:00
taxonomies:
  tags: []
extra:
  source: https://www.bengreenberg.dev/posts/2023-04-09-github-profile-dynamic-content/
  hostname: www.bengreenberg.dev
  author: 
  original_title: "Use GitHub Actions to Make Your GitHub Profile Dynamic "
  original_lang: zh
---

## Use GitHub Actions to Make Your GitHub Profile Dynamic  

使用 GitHub Actions 让你的 GitHub 配置文件动态化

![](t3ggg3o8so8btyijcxg3.png)

### Ben Greenberg

#### April 9, 2023 2023 年 4 月 9 日

Where do people first discover you online?  

人们首先在网上在哪里发现您？  

Perhaps your social media presence is the first thing people find when they search for you, or perhaps it’s the portfolio site you created for yourself.  

也许您的社交媒体形象是人们在搜索您时首先找到的东西，或者它可能是您为自己创建的投资组合网站。  

However, if you use GitHub to share your code and participate in open source projects, then your GitHub profile may be the first place people go to in order to learn more about you.  

但是，如果您使用 GitHub 来共享您的代码并参与开源项目，那么您的 GitHub 个人资料可能是人们了解您的第一个地方。

What do you want your GitHub profile to say about you? How do you want to express what is important to you and who you are in a concise and easy to read manner for visitors?  

您希望您的 GitHub 个人资料对您有何评价？您希望如何以简洁易懂的方式向访问者表达对您来说重要的事情以及您是谁？  

Whether they are a prospective employer or a prospective partner in an open source project, it’s imperative you have a profile that stands out.  

无论他们是开源项目的潜在雇主还是潜在合作伙伴，您都必须拥有突出的个人资料。

Using GitHub Actions, you can turn a static markdown document into a dynamic experience that stays up to date on the latest information about you. How do you do that?  

使用 GitHub Actions，您可以将静态 markdown 文档转变为动态体验，随时了解有关您的最新信息。你是怎样做的？

I’ll show you an example of how you can do this quickly and without too much effort.  

我将向您展示一个示例，说明如何快速且不费力地完成此操作。  

In this example, you’ll learn how to scrape a website and use that data to dynamically update your GitHub profile.  

在此示例中，您将学习如何抓取网站并使用该数据动态更新您的 GitHub 配置文件。  

We’ll show this example in Ruby, but you can do this with JavaScript, TypeScript, Python, or other languages.  

我们将在 Ruby 中展示此示例，但您可以使用 JavaScript、TypeScript、Python 或其他语言来执行此操作。

## How Your GitHub Profile Works 你的 GitHub 配置文件是如何工作的

Your GitHub profile is found by going to `github.com/[your-username]` in a web browser, [here’s mine](https://github.com/hummusonrails) for example. Where does the content for that view come from?  

你的 GitHub 配置文件可以通过在网络浏览器中转到 `github.com/[your-username]` 找到，例如我的。该视图的内容来自哪里？

It lives in a special repository in your account with the name of your account username. If you do not have this repository yet, you will not see any special content when you visit `github.com/[your-username]`, so the first step is to ensure you have that repository created, and if you do not, go ahead and create it.  

它位于您帐户中的一个特殊存储库中，名称与您的帐户用户名相同。如果您还没有这个存储库，那么当您访问 `github.com/[your-username]` 时您将看不到任何特殊内容，因此第一步是确保您已经创建了该存储库，如果没有，请继续创建它。

### Exploring the files in the profile repository  

探索配置文件存储库中的文件

The only required file in the repository is a `README.md` file that is the source of your profile page.  

存储库中唯一需要的文件是 `README.md` 文件，它是您的个人资料页面的来源。

```
[object Object]
```

Go ahead and add some content in that file, save it, and refresh your username homepage, and you will see that content reflected there.  

继续在该文件中添加一些内容，保存并刷新您的用户名主页，您将看到该内容反映在那里。

### Adding the right folders for dynamic content  

为动态内容添加正确的文件夹

Before we create the code to make our profile dynamic, let’s add the folder structure.  

在我们创建代码以使我们的配置文件动态化之前，让我们添加文件夹结构。

Inside the top-level add a new folder called `.github` and inside `.github` add two new sub-folders: `scripts/` and `workflows/`.  

在顶层添加一个名为 `.github` 的新文件夹，在 `.github` 中添加两个新的子文件夹： `scripts/` 和 `workflows/` 。

Your file structure should now look like this:  

您的文件结构现在应该如下所示：

```
[object Object]
```

## Making a Dynamic Profile 制作动态配置文件

We need to do three things for this example:  

我们需要为这个例子做三件事：

-   Define a place in the `README` where the dynamic content will be  
    
    在 `README` 中定义动态内容所在的位置
-   Add a script inside `scripts/` that will do the scraping work  
    
    在 `scripts/` 中添加一个脚本来完成抓取工作
-   Add a workflow for GitHub Actions inside `workflows/` that will run the script on a schedule  
    
    在 `workflows/` 中为 GitHub Actions 添加一个工作流程，它将按计划运行脚本

Let’s do each of those steps now.  

现在让我们执行这些步骤中的每一个。

### Updating the README 更新自述文件

We need to add a section to the README that can be grabbed using Regex by the script to modify. It can be whatever you need it to be for your specific use case.  

我们需要在 README 中添加一个部分，脚本可以使用 Regex 抓取该部分进行修改。它可以是您特定用例所需的任何内容。  

For this example, we’ll add a section for recent blog posts in the README.  

对于此示例，我们将在 README 中为最近的博客文章添加一个部分。

Open up the `README.md` file in a code editor and add the following:  

在代码编辑器中打开 `README.md` 文件并添加以下内容：

```
[object Object],[object Object]
```

Now we have an area for the script to find.  

现在我们有一个供脚本查找的区域。

### Creating the script 创建脚本

The example script we are building is written in Ruby and uses the GitHub gem `octokit` to interact with your repository, the `nokogiri` gem to scrape the website, and the `httparty` gem to make the HTTP request.  

我们正在构建的示例脚本是用 Ruby 编写的，并使用 GitHub gem `octokit` 与您的存储库交互，使用 `nokogiri` gem 抓取网站，使用 `httparty` gem 发出 HTTP 请求。

In this example below, the element to be scraped has already been identified.  

在下面的这个例子中，要抓取的元素已经被识别。  

In your own use case, you’ll need to discover the path to the element on the site you wish to scrape, and it will undoubtedly be different than what is shown below as defined in the `posts` variable and for each `title` and `link` of each `post`.  

在您自己的用例中，您需要找到您希望抓取的网站上元素的路径，毫无疑问，它与下面显示的 `posts` 变量和每个 `title` 中定义的不同和每个 `post` 的 `link` 。

Here is the example code, which goes in the `scripts/` folder:  

这是位于 `scripts/` 文件夹中的示例代码：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

As you can see, first an HTTP request is made to the website and the section with the blog posts is gathered and the data is assigned to a `posts` variable. Then, the script iterates through the blog posts inside the `posts` variable and gathers the first 5 of them. You may want to change that number for your own needs. Each loop through the blog posts, a post is added to an array of `posts_list` with the title and the URL to the blog post.  

如您所见，首先向网站发出 HTTP 请求，并收集包含博客文章的部分，并将数据分配给 `posts` 变量。然后，脚本遍历 `posts` 变量内的博文并收集前 5 篇博文。您可能希望根据自己的需要更改该号码。每次循环浏览博客文章时，都会将一篇文章添加到 `posts_list` 数组中，其中包含博客文章的标题和 URL。

Lastly, the README file is updated by first finding it using the `octokit` gem, and then locating the spot in the README to update with some regex: `posts_regex = /### Recent Blog Posts\n\n[\s\S]*?(?=<\/td>)/m`.  

最后，通过首先使用 `octokit` gem 找到它来更新 README 文件，然后在 README 中找到要使用一些正则表达式更新的位置： `posts_regex = /### Recent Blog Posts\n\n[\s\S]*?(?=<\/td>)/m` 。

This script will do the job, but nothing is actually invoking this script. How does it get run? This is where GitHub Actions comes to the rescue!  

该脚本将完成这项工作，但实际上并没有调用该脚本。它是如何运行的？这就是 GitHub Actions 来拯救的地方！

### Creating the Action workflow 创建动作工作流程

Now that we have the script in place, we need a way to automatically run it on a schedule.  

现在我们有了脚本，我们需要一种方法来按计划自动运行它。  

GitHub Actions provides a powerful way to automate a wide variety of tasks, including running scripts.  

GitHub Actions 提供了一种强大的方法来自动执行各种任务，包括运行脚本。  

In this case, we’ll create a GitHub Actions workflow that runs the script once a week at midnight on Sunday.  

在这种情况下，我们将创建一个 GitHub Actions 工作流，每周日午夜运行一次脚本。

The workflow file should be placed in the .github/workflows/ directory and can be named something like update\_blog\_posts.yml. Here’s the content of the workflow file:  

工作流文件应放在 .github/workflows/ 目录中，并且可以命名为类似 update\_blog\_posts.yml 的名称。这是工作流文件的内容：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

This workflow is triggered on a schedule defined by the `cron` syntax, which specifies that it should run at 00:00 (midnight) every Sunday. Additionally, the workflow can be manually triggered using the `workflow_dispatch` event.  

此工作流按 `cron` 语法定义的计划触发，该语法指定它应在每个星期日的 00:00（午夜）运行。此外，可以使用 `workflow_dispatch` 事件手动触发工作流。

The `update_posts` job consists of several steps:  

`update_posts` 作业由几个步骤组成：

-   Checking out the repository using the `actions/checkout@v2` action.  
    
    使用 `actions/checkout@v2` 操作检出存储库。
-   Setting up Ruby using the `ruby/setup-ruby@v1` action, with the specified Ruby version of 3.1.  
    
    使用 `ruby/setup-ruby@v1` 操作设置 Ruby，指定的 Ruby 版本为 3.1。
-   Installing the required Ruby gems (`httparty`, `nokogiri`, and `octokit`) using the `gem install` command.  
    
    使用 `gem install` 命令安装所需的 Ruby gem（ `httparty` 、 `nokogiri` 和 `octokit` ）。
-   Running the script `update_posts.rb` located in the `.github/scripts/` directory. The `GITHUB_TOKEN` and `GITHUB_REPOSITORY` environment variables are provided to the script, allowing it to interact with the repository.  
    
    运行位于 `.github/scripts/` 目录中的脚本 `update_posts.rb` 。 `GITHUB_TOKEN` 和 `GITHUB_REPOSITORY` 环境变量提供给脚本，允许它与存储库交互。

With this workflow in place, your script will automatically run every week to scrape the blog posts and update the README file.  

有了这个工作流程，您的脚本将每周自动运行以抓取博客文章并更新 README 文件。  

GitHub Actions takes care of all the scheduling and execution, making the process seamless and efficient.  

GitHub Actions 负责所有的调度和执行，使流程无缝且高效。

## Putting it all Together 把它们放在一起

Nowadays, your online presence is often the first point of contact for people looking to connect with you—whether they’re prospective employers, collaborators, or contributors to open source projects.  

如今，您的在线形象通常是希望与您建立联系的人的第一联系方式——无论他们是未来的雇主、合作者还是开源项目的贡献者。  

Your GitHub profile, in particular, is a valuable platform for showcasing your skills, projects, and interests.  

您的 GitHub 个人资料尤其是展示您的技能、项目和兴趣的宝贵平台。  

So, how can you ensure that your GitHub profile remains up to date, relevant, and truly reflective of who you are?  

那么，您如何确保您的 GitHub 个人资料保持最新、相关并真正反映您的身份？

By harnessing the power of GitHub Actions, we’ve demonstrated how you can transform your GitHub profile from a static Markdown document into a dynamic, ever-changing example of who you are.  

通过利用 GitHub Actions 的强大功能，我们展示了如何将 GitHub 配置文件从静态 Markdown 文档转换为动态的、不断变化的自我示例。  

Through the example provided in this guide, you’ve learned how to scrape data from a website and use it to dynamically update your GitHub profile.  

通过本指南中提供的示例，您了解了如何从网站抓取数据并使用它来动态更新您的 GitHub 配置文件。  

And while our example was implemented in Ruby, the same principles can be applied using JavaScript, TypeScript, Python, or any other language of your choice.  

虽然我们的示例是用 Ruby 实现的，但可以使用 JavaScript、TypeScript、Python 或您选择的任何其他语言来应用相同的原则。

To recap, we walked through the process of creating a Ruby script that scrapes blog posts from a website, extracts relevant information, and updates the “Recent Blog Posts” section of your `README.md` file. Then, we used GitHub Actions to set up a workflow that runs the script on a regular schedule, ensuring that your profile remains current with your latest content.  

回顾一下，我们完成了创建 Ruby 脚本的过程，该脚本从网站上抓取博客文章，提取相关信息，并更新 `README.md` 文件的“最近的博客文章”部分。然后，我们使用 GitHub Actions 设置了一个定期运行脚本的工作流程，确保您的个人资料与最新内容保持同步。

But our journey doesn’t end here! The techniques and approaches shared in this guide can serve as a foundation for further exploration and creativity.  

但我们的旅程并没有就此结束！本指南中分享的技术和方法可以作为进一步探索和创造的基础。  

Whether it’s pulling in data from other sources, integrating with APIs, or experimenting with different content formats, the possibilities are endless.  

无论是从其他来源获取数据、与 API 集成，还是尝试不同的内容格式，都有无限可能。

So go ahead and make your GitHub profile a vibrant and dynamic extension of yourself. Let it tell your story, highlight your achievements, and invite collaboration with others.  

因此，继续吧，让你的 GitHub 个人资料成为你自己充满活力的延伸。让它讲述您的故事，突出您的成就，并邀请与他人合作。

⭐ Was this blog post helpful? Consider sponsoring my work on GitHub to help me create more content like this! ❤️  

⭐ 这篇博文有帮助吗？考虑赞助我在 GitHub 上的工作，帮助我创建更多这样的内容！ ❤️
