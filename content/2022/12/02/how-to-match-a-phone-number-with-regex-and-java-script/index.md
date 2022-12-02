---
title: "使用正则表达式和 JavaScript 匹配电话号码"
date: 2022-12-02T10:34:16+08:00
updated: 2022-12-02T10:34:16+08:00
taxonomies:
  tags: []
extra:
  source: https://indepthjavascript.dev/how-to-match-a-phone-number-with-regex-and-javascript
  hostname: indepthjavascript.dev
  author: Amit Mehta
  original_title: "How to Match a Phone Number with Regex and JavaScript"
  original_lang: en
---

I'll be honest, the first time I saw a regular expression, it was a scary experience. **It looks like a weird alien language!** I thought to myself: "I've spent months learning programming and now i gotta learn this seemly super complex language!?"

老实说，我第一次看到正则表达式时，那是一次可怕的经历。 **它看起来像一种奇怪的外星语言！** 我心想：“我花了几个月的时间学习编程，现在我必须学习这门看似超级复杂的语言！？”

However, once I sat down to actually learn regex, I discovered it's not super hard, once you learn the syntax.

然而，一旦我坐下来真正学习正则表达式，我发现它并不难，一旦你学会了语法。

### Why should I even bother Learning Regex?

### 我为什么还要费心学习正则表达式？

As you start coding more, and more, it really comes in handy in all types of situations, and not just to valid phone numbers, and email addresses. It's very helpful when extract data from logs, messy JSON data from API calls, and many other situations.

随着您开始编写越来越多的代码，它在所有类型的情况下都会派上用场，而不仅仅是有效的电话号码和电子邮件地址。 在从日志中提取数据、从 API 调用中提取杂乱的 JSON 数据以及许多其他情况时，它非常有用。

I'm going to teach you how to valid a phone number _with 1 line of code_, with 1 regular expression. **Validating a phone number WITHOUT regex becomes an obnoxious leetcode question.** 😧

我将教您如何 _使用 1 行代码_ 和 1 个正则表达式来验证电话号码。 **在没有正则表达式的情况下验证电话号码成为一个令人讨厌的 leetcode 问题。** 😧

### Why is validating a phone number so complex?

### 为什么验证电话号码如此复杂？

Let's say you have a form on your website to collect a phone number to spa-, I mean, SMS your subscribers, there are a bunch of different ways they could submit their phone numbers.

假设您的网站上有一个表格，用于收集 spa 的电话号码，我的意思是，向您的订户发送短信，他们可以通过多种不同的方式提交电话号码。

All of these are VALID US based numbers:

所有这些都是基于美国的有效号码：

-   `202-515-5555`
-   `(202)515 5555`
-   `1 202 515 5555`
-   `2025155555`
-   `1-202-515-5555`
-   `1202-515-5555`
-   `etc`

There are more valid combinations I didn't list, but you get the idea! Validating every combo because a nasty coding problem. _But NOT if you're using regex to validate it!_ 😉

还有更多我没有列出的有效组合，但你明白了！ 验证每个组合，因为一个讨厌的编码问题。 _但如果你使用正则表达式来验证它，那就不行了！_ 😉

### Let's start with the Simplest Case

### 让我们从最简单的案例开始

Let's first validate `202-515-5555`. The basic idea of regex is to build a pattern to match a string. What is the pattern in `202-515-5555` ?

我们先来验证 `202-515-5555`. 正则表达式的基本思想是建立一个模式来匹配一个字符串。 里面的图案是什么 `202-515-5555` ?

We start with 3 digits followed by a `-` followed by 3 more digits, followed by another `-`, then we end with 4 digits.

我们从 3 位数字开始，然后是 `-`接下来是 3 个数字，然后是另一个 `-`，然后我们以 4 位数字结尾。

Here's what the regex pattern to match `202-515-5555` looks like:

这是要匹配的正则表达式模式 `202-515-5555`好像：

Let's watch through this...

让我们看看这个...

The `^` just indicates the beginning of the string. In the above regex, we're stating that the phone number must start with `\d{3}` since we have `^` in front of `\d{3}`.

这 `^`只是表示字符串的开头。 在上面的正则表达式中，我们声明电话号码必须以 `\d{3}`因为我们有 `^`在...前面 `\d{3}`.

Now **`\d` => stands for single digit**, and **`{3}` simple means `\d` repeats exactly 3 times.** **So `^\d{3}` means our phone number STARTS with 3 digits.**

现在 **`\d`\=>代表单个数字** ，并且 **`{3}`简单的方法 `\d`正好重复 3 次。** **所以 `^\d{3}`表示我们的电话号码以 3 位数字开头。**

Now let's just jump to the end: `$` indicates the end of the string match. **`\d{4}$` means our phone number must END with 4 digits**. _Does this make sense?_

现在让我们跳到最后： `$`表示字符串匹配结束。 **`\d{4}$`意味着我们的电话号码必须以 4 位数字结尾** 。 _这有意义吗？_

**`-` just means the phone number must have a dash at that spot.**

**`-`只是意味着电话号码必须在那个地方有破折号。**

So let's read the entire regex from left to right now:

现在让我们从左到右阅读整个正则表达式：

1.  `^\d{3}` => start with 3 digits
2.  `-` => followed by a dash
3.  `\d{3}` => followed with 3 digits
4.  `-` => followed by a dash
5.  `\d{4}$` => ends with 4 digits

1.  `^\d{3}`\=> 以 3 位数字开头
2.  `-`\=> 后跟破折号
3.  `\d{3}`\=> 后接 3 位数字
4.  `-`\=> 后跟破折号
5.  `\d{4}$`\=> 以 4 位数字结尾

Please read the above section a few times, if necessary, to make sure you fully understand before we move on.

如有必要，请多读几遍以上部分，以确保在我们继续之前您已完全理解。

### How do I match the phone number if dashes are options?

### 如果破折号是选项，我如何匹配电话号码？

Great question! How do we match BOTH: `202-515-5555` and `2025155555`

好问题！ 我们如何匹配两者： `202-515-5555`和 `2025155555`

To make a character match optional, just add a `?` after it.

要使字符匹配可选，只需添加一个 `?`在它之后。

Here's what our new improved match looks like:

这是我们新的改进匹配的样子：

**`-?` simply means the `-` is optional**: it may, or may not, be there!

**`-?`只是意味着 `-`是可选的** ：它可能存在，也可能不存在！

Let's read the entire regex again:

让我们再次阅读整个正则表达式：

1.  `^\d{3}` => start with 3 digits
2.  `-?` => _optionally_ followed by a dash
3.  `\d{3}` => followed with 3 digits
4.  `-?` => _optionally_ followed by a dash
5.  `\d{4}$` => ends with 4 digits

1.  `^\d{3}`\=> 以 3 位数字开头
2.  `-?`\=> _可选地_ 后跟破折号
3.  `\d{3}`\=> 后接 3 位数字
4.  `-?`\=> _可选地_ 后跟破折号
5.  `\d{4}$`\=> 以 4 位数字结尾

### How about matching the phone number if there are spaces, instead of dashes?

### 如果有空格而不是破折号，如何匹配电话号码？

Now let's work on matching: `202-515-5555`, `2025155555`, AND `202 515 5555`

现在让我们开始匹配： `202-515-5555`, `2025155555`， 和 `202 515 5555`

Instead of optionally just having a `-` we can optionally have either `-` OR `` `. How do we represent this? Easy, put both ``\-`and` `inside of`\[...\]`like this:`\[ -\]\`.

而不是选择性地拥有一个 `-`我们可以选择 `-`或者 `` `. How do we represent this? Easy, put both ``\- `and` `inside of`\[...\] `like this:`\[ -\]\`.

Our new regex looks like this:

我们的新正则表达式如下所示：

```
^\d{3}[ -]?\d{3}[ -]?\d{4}$
```

Now it's definitely starting to look alien! 😅

现在它肯定开始看起来很陌生了！ 🤗

Let's break it down:

让我们分解一下：

1.  `^\d{3}` => start with 3 digits
2.  `[ -]?` => _optionally_ followed by a _space OR dash_
3.  `\d{3}` => followed with 3 digits
4.  `[ -]?` => _optionally_ followed by a _space OR dash_
5.  `\d{4}$` => ends with 4 digits

1.  `^\d{3}`\=> 以 3 位数字开头
2.  `[ -]?`\=> _可选地_ 后跟一个 _空格或破折号_
3.  `\d{3}`\=> 后接 3 位数字
4.  `[ -]?`\=> _可选地_ 后跟一个 _空格或破折号_
5.  `\d{4}$`\=> 以 4 位数字结尾

### How to Match `1` or `1` or `1-` at the beginning of our phone number

### 如何搭配 `1`或者 `1`或者 `1-`在我们电话号码的开头

Based on what we've learned, can you figure this out?

根据我们学到的知识，你能想出这个吗？

It's a bit tricky once you realize that the `1...` in the beginning is optional.

一旦你意识到 `1...`一开始是可选的。

Let's take it step by step...

让我们一步一步来......

If you want the phone number to start with `1` _we add `^1` to the beginning of the string match_, correct? Now we want to optionally add a dash or space after the 1. Luckily, we already know how to do that: \`\[ -\]?'.

如果您希望电话号码以 `1` _我们增加 `^1`到字符串 match 的开头，对_ 吗？ 现在我们想在 1 之后有选择地添加破折号或空格。幸运的是，我们已经知道如何做到这一点：\`\[-\]?'。

**Combining the 2 we get: `^1[ -]?`**

**结合我们得到的2： `^1[ -]?`**

Adding this to our previous regex we get:

将其添加到我们之前的正则表达式中，我们得到：

```
^1[ -]?\d{3}[ -]?\d{3}[ -]?\d{4}$
```

Can you sense there's something wrong here? **The above regex string match MUST start with `1`, it's not optional.** We need to make `1[ -]?` optional.

你能感觉到这里有什么不对吗？ **上面的正则表达式字符串匹配必须以 `1`，它不是可选的。** 我们需要做 `1[ -]?`可选的。

_How do we do that?_ Since we're talking about multiple elements here: `1` and `[ -]?` we need to place the whole thing in `(...)` creating a group. Then add a `?` after it to make the entire group optional!

_我们该怎么做？_ 由于我们在这里谈论多个元素： `1`和 `[ -]?`我们需要把整个东西放在 `(...)`创建一个组。 然后添加一个 `?`在它之后使整个组可选！

I know it's a lot to take in! Here's what it looks like:

我知道要接受很多东西！ 这是它的样子：

```
^(1[ -]?)?\d{3}[ -]?\d{3}[ -]?\d{4}$
```

Let's break it down again, with an extra step now:

让我们再次分解它，现在多了一步：

1.  `^(1[ -]?)?` => _optionally_ start with 1, which is _optionally_ followed by a _space OR dash_
2.  `\d{3}` => start with 3 digits
3.  `[ -]?` => _optionally_ followed by a _space OR dash_
4.  `\d{3}` => followed with 3 digits
5.  `[ -]?` => _optionally_ followed by a _space OR dash_
6.  `\d{4}$` => ends with 4 digits

1.  `^(1[ -]?)?`\=> _可选择_ 以 1 开头， _可选择_ 后跟一个 _空格或破折号_
2.  `\d{3}`\=> 以 3 位数字开头
3.  `[ -]?`\=> _可选地_ 后跟一个 _空格或破折号_
4.  `\d{3}`\=> 后接 3 位数字
5.  `[ -]?`\=> _可选地_ 后跟一个 _空格或破折号_
6.  `\d{4}$`\=> 以 4 位数字结尾

🤯

If you're still reading, congrats, you now know how to _think_ 'regex'!

如果您还在阅读，恭喜您，您现在知道如何 _思考_ “正则表达式”了！

![皮卡德正则表达式](6mzwct.jpg)

**There's still 1 outstanding issue:** how to match a phone number like: `(202)515 5555`. I'm going to leave that one for the reader (_hint:_ use the [pipe operator: `(...|...)`)](https://regexone.com/lesson/conditionals).

**还有 1 个悬而未决的问题：** 如何匹配电话号码，例如： `(202)515 5555`. 我要把那个留给读者（ _提示：_ 使用 [管道运算符： `(...|...)`)](https://regexone.com/lesson/conditionals) .

### Putting it all Together to Test an Actual Phone Number String

### 将它们放在一起以测试实际的电话号码字符串

Now let's take our regex and turn it into a regular expression in javaScript. To do that you just add `/.../` around it. Then use a method called `test`:

现在让我们把正则表达式转换成 javaScript 中的正则表达式。 为此，您只需添加 `/.../`周围。 然后使用一个名为 `test`:

```
const regex = /^(1[ -]?)?\d{3}[ -]?\d{3}[ -]?\d{4}$/;
const phoneNumber = '1202-515-5555';

// test returns 'true' if there's a match and 'false' if there is not
const match = regex.test(phoneNumber);
```

If you want to learn regex properly, here's a EXCELLENT free tutorial: [RegexOne](https://regexone.com/). This is literally how I learned Regex. It's worth going through ALL the exercises.

如果您想正确学习正则表达式，这里有一个非常好的免费教程： [RegexOne](https://regexone.com/) 。 这就是我学习正则表达式的方式。 值得完成所有练习。
