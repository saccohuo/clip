---
title: "Misframe - CTEs作为查询表"
date: 2023-03-11T09:00:49+08:00
updated: 2023-03-11T09:00:49+08:00
taxonomies:
  tags: []
extra:
  source: https://misfra.me/2023/ctes-as-lookup-tables/
  hostname: misfra.me
  author: Preetam Jinka
  original_title: "CTEs as lookup tables"
  original_lang: en
---

In the past I’ve had to write queries to convert data in a table into user-friendly display text. One way to do this is with CASE expressions. For example, let’s say you have a table with a column being a country code, and you want to add the country name in the final result.  

在过去，我不得不写查询，将表中的数据转换成用户友好的显示文本。一种方法是使用CASE表达式。例如，假设你有一个表，其中一列是国家代码，你想在最终结果中加入国家名称。

```
sqlite> SELECT code FROM data;
+------+
| code |
+------+
| us   |
| fr   |
| in   |
+------+
```

One approach is to use a CASE expression in your query like this:  

一种方法是在你的查询中使用CASE表达式，像这样。

```
sqlite> SELECT code,
   ...> CASE code 
   ...>   WHEN 'us' THEN 'United States'
   ...>   WHEN 'fr' THEN 'France'
   ...>   WHEN 'in' THEN 'India'
   ...>  END AS country
   ...> FROM data;
+------+---------------+
| code |    country    |
+------+---------------+
| us   | United States |
| fr   | France        |
| in   | India         |
+------+---------------+
```

The downside is that it’s harder to read, and if you need to do something similar elsewhere in the query, you’ll have to repeat the expression.  

其缺点是更难阅读，而且如果你需要在查询的其他地方做类似的事情，你将不得不重复表达。

An alternative is to use a CTE like this:  

另一种方法是使用类似这样的CTE。

```
sqlite> WITH countries (code, name) AS (
   ...>   SELECT * FROM (VALUES
   ...>     ('us', 'United States'), ('fr', 'France'), ('in', 'India')
   ...>   ) AS codes
   ...> )
   ...> SELECT data.code, name FROM data LEFT JOIN countries ON countries.code = data.code;
+------+---------------+
| code |     name      |
+------+---------------+
| us   | United States |
| fr   | France        |
| in   | India         |
+------+---------------+
```

Now the `countries` CTE becomes a lookup table that you can reference several times in your queries.  

现在， `countries` CTE成为一个查找表，你可以在查询中多次引用。

This approach works with SQLite and PostgreSQL.  

这种方法适用于SQLite和PostgreSQL。
