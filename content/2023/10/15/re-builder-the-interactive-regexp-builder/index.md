---
title: "re-builder：交互式 regexp 生成器 - Mastering Emacs"
date: 2023-10-15T23:26:25+08:00
updated: 2023-10-15T23:26:25+08:00
taxonomies:
  tags: []
extra:
  source: https://www.masteringemacs.org/article/re-builder-interactive-regexp-builder
  hostname: www.masteringemacs.org
  author: Mickey Petersen
  original_title: "re-builder: the Interactive regexp builder"
  original_lang: en
---

## [![The Mastering Emacs ebook cover art](bookcover35.png)](https://www.masteringemacs.org/book)

Even if you're a wizard at regular expressions, you may occasionally want a little help. Emacs's regexp builder highlights matches and capturing groups in a buffer of your choice, and it works with a range of regular expression flavors.  

即使你是正则表达式的行家里手，偶尔也会需要一些帮助。Emacs 的 regexp 生成器可以在你选择的缓冲区中高亮显示匹配项和捕获组，并可与各种正则表达式配合使用。

Updated for **emacs 28** 已针对 emacs 28 进行更新

![](fleuron2.gif)

I doubt it’s a well-kept secret that Emacs has a regexp “helper” called `M-x re-builder`. But if you haven’t heard about it before, Emacs’s re-builder lets you interactively build a regular expression and see what it matches on the screen. It’ll even uniquely color capturing groups so you can tell them apart.  

Emacs 有一个名为 `M-x re-builder` 的 regexp "助手"，这恐怕不是什么秘密。.但如果你以前没听说过，Emacs 的重构器可以让你交互式地构建正则表达式，并在屏幕上看到它匹配的内容。它甚至会为捕获的组群涂上独特的颜色，以便你区分它们。

## Syntax 语法

What most people _don’t_ know is re-builder’s support for different syntax; but, sadly, not _PCRE_ – sorry!  

大多数人不知道的是，re-builder 支持不同的语法；但遗憾的是，不支持 PCRE - 抱歉！

There are five different syntax choices (see table below). You can either use customize (`M-x customize-variable RET reb-re-syntax RET`) or set the variable (`reb-re-syntax`) directly.  

有五种不同的语法可供选择（见下表）。您可以使用自定义 ( `M-x customize-variable RET reb-re-syntax RET` ) 或直接设置变量 ( `reb-re-syntax` )。

`read`

**Default**. Similar to `string` but requires “double escaping” of backslashes like you would be required to do in elisp. Example: `\\\\(foo\\\\\|bar\\\\)`  

默认值。与 `string` 类似，但需要对反斜线进行 "双重转义"，就像在 elisp 中需要做的那样。例如 `\\\\(foo\\\\\|bar\\\\)`

`string`

**Recommended**. Similar to `read` but you **don’t** have the issue of backslash plague that haunts the default settings. Example: `\\(foo\\\|bar\\)`  

推荐使用。与 `read` 类似，但不会出现默认设置中的反斜杠问题。例如 `\\(foo\\\|bar\\)`

`sregex`

**Deprecated**. A symbolic regular expression engine that uses s-expressions instead of strings.  

已废弃。使用 s 表达式而非字符串的符号正则表达式引擎。

`lisp-re`

**Deprecated**. Yet _another_ regular expression engine that uses s-expressions  

已废弃。另一种使用 s 表达式的正则表达式引擎

`rx`

**Recommended**. A _third_, and far more advanced, s-expression regexp engine. Use this and not `sregex` or `lisp-re` if you want to use a lisp-style regexp engine.  

推荐使用。第三个，也是更高级的 s-expression regexp 引擎。如果您想使用 lisp 风格的 regexp 引擎，请使用此引擎，而不要使用 `sregex` 或 `lisp-re` 。

## The backslash madness 疯狂的反斜杠

I recommend you switch to `string` right away; there’s little reason to use `read`, and the extra escaping will drive you insane unless you’re used to writing regexp in elisp.  

我建议您立即改用 `string` ；使用 `read` 的理由并不充分。除非你习惯用 elisp 写 regexp，否则额外的转义符会让你发疯。

Add this to your .emacs to switch the default syntax to `string`:  

将此添加到 .emacs 中，即可将默认语法切换为 `string` ：

```
(require 're-builder)
(setq reb-re-syntax 'string)
```

## Useful Keybinds 有用的按键绑定

If you do write a lot of elisp, you probably use (or should use!) `rx` to make your regexp experience in Emacs a bit more pleasant. Unfortunately, you can only have one default setting at a time so you have to switch manually with `C-c TAB` in re-builder.  

如果您经常编写 elisp，那么您可能会使用（或者应该使用！） `rx` ，让您在 Emacs 中的 regexp 体验更加愉悦。遗憾的是，您一次只能使用一种默认设置，因此必须在 re-builder 中使用 `C-c TAB` 手动切换。

You can enter the sub-expression mode with `C-c C-e` to only highlight capturing groups; you can toggle the case sensitivity with `C-c C-i`; and you can move between matches with `C-c C-s` and `C-c C-r`.  

您可以使用 `C-c C-e` 进入子表达式模式，以便只突出显示捕获组；您可以使用 `C-c C-i` 切换大小写敏感度；您还可以使用 `C-c C-s` 和 `C-c C-r` 在匹配项之间移动。.

The re-builder keybind `C-c C-w` bears mention as well: it will copy (and convert, where applicable) the expression to a string format suitable for use in elisp.  

值得一提的还有重编译键绑定 `C-c C-w` ：它会将表达式复制（并酌情转换）为适合在 elisp 中使用的字符串格式。

![](fleuron1.gif)

## Further Reading 更多阅读

Have you read my [Reading Guide](https://www.masteringemacs.org/reading-guide) yet? It's a curated guide to most of my articles and I guarantee you'll learn something whether you're a beginner or an expert. [And why not check out my book?](https://www.masteringemacs.org/book)  

你读过我的阅读指南了吗？这是我大部分文章的精选指南，无论你是初学者还是专家，我保证你都会有所收获。为什么不看看我的书呢？

**Subscribe** to the Mastering Emacs newsletter  

订阅《精通 Emacs》时事通讯

I write infrequently, so go on — sign up and receive an e-mail when I write new articles  

我很少写文章，所以请继续注册，并在我写新文章时收到电子邮件
