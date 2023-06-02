---
title: "矢量搜索"
date: 2023-06-01T17:23:43+08:00
updated: 2023-06-01T17:23:43+08:00
taxonomies:
  tags: []
extra:
  source: https://amjith.com/blog/2023/vector_search/
  hostname: amjith.com
  author: 
  original_title: "Vector Search"
  original_lang: zh
---

Recently I learned about a new kind of search called [Vector Search](https://www.pinecone.io/learn/what-is-similarity-search/) or [Semantic Search](https://en.wikipedia.org/wiki/Semantic_search). This is a search technique that tries to find documents that match the meaning of the user’s search term instead of trying to match keywords like a Full Text Search (FTS).  

最近我了解了一种称为矢量搜索或语义搜索的新型搜索。这是一种搜索技术，它试图找到与用户搜索词的含义相匹配的文档，而不是像全文搜索 (FTS) 那样尝试匹配关键字。

I wanted to try Semantic Search for my blog. I came across [Alex Garcia’s post](https://observablehq.com/@asg017/introducing-sqlite-vss) about a new SQLite extension for Vector Search called [sqlite-vss](https://github.com/asg017/sqlite-vss). Since my blog data is already in a [SQLite database](https://amjith.com/blog/posthaven/) I figured, why not?  

我想为我的博客尝试语义搜索。我看到了 Alex Garcia 的帖子，该帖子介绍了一个名为 sqlite-vss 的用于矢量搜索的新 SQLite 扩展。由于我的博客数据已经在我认为的 SQLite 数据库中，为什么不呢？

The idea behind semantic search is to encode the contents of each document into a vector of floating point numbers called embeddings. Then use [cosine-similarity](https://en.wikipedia.org/wiki/Cosine_similarity#:~:text=In%20data%20analysis%2C%20cosine%20similarity,the%20product%20of%20their%20lengths.) algorithm to match search terms with documents. Calculating the embeddings requires a python library called [sentence transformers](https://www.sbert.net/). This can be installed with pip:  

语义搜索背后的想法是将每个文档的内容编码成一个称为嵌入的浮点数向量。然后使用余弦相似度算法将搜索词与文档进行匹配。计算嵌入需要一个名为句子转换器的 python 库。这可以用 pip 安装：

```
[object Object],[object Object],[object Object],[object Object],[object Object]
```

I used the trusty [sqlite-utils](https://sqlite-utils.readthedocs.io/) to add the embeddings to my database into new columns. The CLI has a [`convert`](https://sqlite-utils.datasette.io/en/stable/cli.html#using-a-convert-function-to-execute-initialization) sub-command that can be used to run a python function on each row of a table and write the results into a different column.  

我使用可信赖的 sqlite-utils 将嵌入到我的数据库中添加到新列中。 CLI 有一个 `convert` 子命令，可用于在表的每一行上运行 python 函数并将结果写入不同的列。  

I wrote a python function that calculates the embeddings and returns them as bytes. The results are written into a new column called `title_embeddings` of type `blob`.  

我写了一个 python 函数来计算嵌入并将它们作为字节返回。结果被写入名为 `title_embeddings` 的 `blob` 类型的新列中。

First let’s run the embeddings on the `title` column:  

首先让我们在 `title` 列上运行嵌入：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Next is the `mdbody` column to calculate the embeddings of each post’s body:  

接下来是 `mdbody` 列，用于计算每个帖子正文的嵌入：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Now we enable the sqlite-vss extension and use it to build an index.  

现在我们启用 sqlite-vss 扩展并使用它来构建索引。

I’m going to use my favorite CLI for SQLite called [litecli](https://litecli.com/).  

我将使用我最喜欢的 SQLite CLI，称为 litecli。

The two `.so` files that we downloaded from sqlite-vss github [releases](https://github.com/asg017/sqlite-vss/releases/tag/v0.1.0) page are loaded into the database:  

我们从 sqlite-vss github 发布页面下载的两个 `.so` 文件被加载到数据库中：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Using the vss0 extension we create a table called `posts_vss` that will hold the index:  

使用 vss0 扩展，我们创建一个名为 `posts_vss` 的表来保存索引：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Next we insert the data from the `posts` table into the `posts_vss` table:  

接下来我们将 `posts` 表中的数据插入到 `posts_vss` 表中：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Optionally, we can create a trigger that will keep the `posts_vss` table in sync with the `posts` table:  

或者，我们可以创建一个触发器，使 `posts_vss` 表与 `posts` 表保持同步：

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

We are ready to search using the vector search technique.    

When the user types in a query, we will create embeddings of the user input using the same encoding algorithm we used for the title and body. 

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Using the embeddings of the user input we can search the `posts_vss` table for the closest matches. I decided to do the query from python since encoding the search term had to be done in python. First I `pip install sqlite_vss` library. 

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

This searches both the title and the body for the closest matches and returns the top 5 results. The results are sorted by the closest match first. Here is a sample output: 

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

The results are pretty good. 

## Datasette

How do we get this to work with Datasette? Datasette has a plugin system that allows us to extend the functionality of Datasette.    

The author of the sqlite-vss has created a datasette plugin called [datasette-sqlite-vss](https://github.com/asg017/sqlite-vss#datasette) which loads the sqlite-vss extension for the sqlite3 db when datasette starts. 

```
[object Object],[object Object],[object Object]
```

The plugin also adds a new SQL function called `vss_search` that can be used to search the index. The plugin is installed and enabled when datasette starts. Now we can use the `vss_search` function to search the index. 

We are still missing a piece. How do we get the user input from the search box into the SQL query? Remember the [plugin system](https://datasette.io/docs/plugins.html) of datasette. I wrote a small plugin that can convert a user input string into the embeddings using SentenceTransformer. 

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

The plugin creates a new SQL function called `vector_encode` that can be used to encode a string into a vector. Save this in a python file called `vector_encode.py` in a folder called `plugins`. 

```
[object Object],[object Object],[object Object]
```

Now we can use the `vector_encode` function to encode the user input and use the `vss_search` function to search the index. Here is the SQL query that does the search: 

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Visit http://localhost:8001/blog/posts and paste the query in the SQL editor and click Run SQL. You should see an input box that let’s you type in the search term.  

访问 http://localhost:8001/blog/posts 并将查询粘贴到 SQL 编辑器中，然后单击运行 SQL。您应该会看到一个输入框，让您输入搜索词。

I would go a step farther to use the [canned-query](https://docs.datasette.io/en/stable/sql_queries.html#canned-query-parameters) feature in datasette to make this slightly easier.  

我会更进一步使用 datasette 中的固定查询功能来使这稍微容易一些。

Create a metadata.yml file 创建一个 metadata.yml 文件

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

Then relaunch datasette with the metadata file.  

然后使用元数据文件重新启动数据集。

```
[object Object],[object Object],[object Object],[object Object],[object Object]
```

Visit http://localhost:8001/blog and click on the Vector Search query. You should see an input box that let’s you type in the search term.  

访问 http://localhost:8001/blog 并单击 Vector Search 查询。您应该会看到一个输入框，让您输入搜索词。

Finally publish it to [fly.io](https://fly.io/) using the [datasette-publish-fly](https://datasette.io/plugins/datasette-publish-fly) plugin.  

最后使用 datasette-publish-fly 插件将其发布到 fly.io。

```
[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object],[object Object]
```

The additional `--install` flags are needed to install the dependencies for the plugin that we created to encode the search term.  

需要额外的 `--install` 标志来安装我们创建的用于对搜索词进行编码的插件的依赖项。

Unfortunately this does not fit in the free-tier fly.io instances. So I don’t have a demo version to show you. But trust me, it is awesome.  

不幸的是，这不适合免费层级的 fly.io 实例。所以我没有演示版可以给你看。但相信我，这太棒了。

Thank you, [Alex Garcia](https://alexgarcia.xyz/) and [Simon Willison](https://simonwillison.net/) for making these cool projects and writing about them in detail.  

感谢 Alex Garcia 和 Simon Willison 制作了这些很棒的项目并详细介绍了它们。
