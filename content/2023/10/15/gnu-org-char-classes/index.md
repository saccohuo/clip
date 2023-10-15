---
title: "字符类（GNU Emacs Lisp 参考手册）"
date: 2023-10-15T23:22:19+08:00
updated: 2023-10-15T23:22:19+08:00
taxonomies:
  tags: []
extra:
  source: https://www.gnu.org/software/emacs/manual/html_node/elisp/Char-Classes.html#Char-Classes
  hostname: www.gnu.org
  author: 
  original_title: "gnu.org"
  original_lang: en
---

Below is a table of the classes you can use in a character alternative, and what they mean. Note that the ‘\[’ and ‘\]’ characters that enclose the class name are part of the name, so a regular expression using these classes needs one more pair of brackets. For example, a regular expression matching a sequence of one or more letters and digits would be ‘\[\[:alnum:\]\]+’, not ‘\[:alnum:\]+’.  

下面的表格列出了可在字符备选方案中使用的类别及其含义。请注意，" \[ '和' \] 和' \] '字符是类名的一部分，因此使用这些类的正则表达式还需要一对括号。例如，匹配一个或多个字母和数字序列的正则表达式是 ' \[\[:alnum:\]\]+ '，而不是' \[:alnum:\]+ '。'.

‘\[:ascii:\]’ ' \[:ascii:\] '

This matches any ASCII character (codes 0–127).  

这符合任何 ASCII 字符（代码 0-127）。

‘\[:alnum:\]’ ' \[:alnum:\] '

This matches any letter or digit. For multibyte characters, it matches characters whose Unicode ‘general-category’ property (see [Character Properties](https://www.gnu.org/software/emacs/manual/html_node/elisp/Character-Properties.html)) indicates they are alphabetic or decimal number characters.  

可匹配任何字母或数字。对于多字节字符，它匹配 Unicode ' general-category ' 属性（请参阅字符属性）表示是字母或十进制数字的字符。属性（请参阅 "字符属性"）表示它们是字母或十进制数字字符的字符。

‘\[:alpha:\]’ ' \[:alpha:\] '

This matches any letter. For multibyte characters, it matches characters whose Unicode ‘general-category’ property (see [Character Properties](https://www.gnu.org/software/emacs/manual/html_node/elisp/Character-Properties.html)) indicates they are alphabetic characters.  

可匹配任何字母。对于多字节字符，它匹配 Unicode ' general-category ' 属性（请参阅字符属性）表示是字母字符的字符。属性（请参阅 "字符属性"）表示其为字母字符的字符。

‘\[:blank:\]’ ' \[:blank:\] '

This matches horizontal whitespace, as defined by Annex C of the Unicode Technical Standard #18. In particular, it matches spaces, tabs, and other characters whose Unicode ‘general-category’ property (see [Character Properties](https://www.gnu.org/software/emacs/manual/html_node/elisp/Character-Properties.html)) indicates they are spacing separators.  

它匹配统一码技术标准 #18 附件 C 中定义的水平空白。特别是，它匹配空格、制表符和其他 Unicode ' general-category ' 属性（请参阅字符属性）表示它们是间距分隔符的字符。属性（请参阅 "字符属性"）表示它们是间隔分隔符的字符。

‘\[:cntrl:\]’ ' \[:cntrl:\] '

This matches any character whose code is in the range 0–31.  

它匹配代码范围在 0-31 之间的任何字符。

‘\[:digit:\]’ ' \[:digit:\] '

This matches ‘0’ through ‘9’. Thus, ‘\[-+\[:digit:\]\]’ matches any digit, as well as ‘+’ and ‘\-’.  

这与" 0 '到' 9 '.因此，" \[-+\[:digit:\]\] 匹配任何数字，" + 和 ' \- '.

‘\[:graph:\]’ ' \[:graph:\] '

This matches graphic characters—everything except spaces, ASCII and non-ASCII control characters, surrogates, and codepoints unassigned by Unicode, as indicated by the Unicode ‘general-category’ property (see [Character Properties](https://www.gnu.org/software/emacs/manual/html_node/elisp/Character-Properties.html)).  

这与图形字符相匹配--除了空格、ASCII 和非 ASCII 控制字符、代用字符以及 Unicode 未指定的码位（如 Unicode ' general-category ' 属性所示）以外的所有字符。属性（请参阅字符属性）。

‘\[:lower:\]’ ' \[:lower:\] '

This matches any lower-case letter, as determined by the current case table (see [The Case Table](https://www.gnu.org/software/emacs/manual/html_node/elisp/Case-Tables.html)). If `case-fold-search` is non-`nil`, this also matches any upper-case letter. Note that a buffer can have its own local case table different from the default one.  

根据当前大小写表（请参阅大小写表），它匹配任何小写字母。如果 `case-fold-search` 不是 `nil` ，则也匹配任何大写字母。则也会匹配任何大写字母。请注意，缓冲区可以拥有不同于默认大小写表的本地大小写表。

‘\[:multibyte:\]’ ' \[:multibyte:\] '

This matches any multibyte character (see [Text Representations](https://www.gnu.org/software/emacs/manual/html_node/elisp/Text-Representations.html)).  

这可以匹配任何多字节字符（请参阅文本表示法）。

‘\[:nonascii:\]’ ' \[:nonascii:\] '

This matches any non-ASCII character.  

这可以匹配任何非 ASCII 字符。

‘\[:print:\]’ ' \[:print:\] '

This matches any printing character—either spaces or graphic characters matched by ‘\[:graph:\]’.  

这将匹配任何打印字符--空格或" \[:graph:\] "匹配的图形字符。'.

‘\[:punct:\]’ ' \[:punct:\] '

This matches any punctuation character. (At present, for multibyte characters, it matches anything that has non-word syntax, and thus its exact definition can vary from one major mode to another, since the syntax of a character depends on the major mode.)  

它可以匹配任何标点符号。(目前，对于多字节字符，它匹配任何非单词语法的字符，因此，由于字符的语法取决于主要模式，它的确切定义可能因主要模式而异）。

‘\[:space:\]’ ' \[:space:\] '

This matches any character that has whitespace syntax (see [Table of Syntax Classes](https://www.gnu.org/software/emacs/manual/html_node/elisp/Syntax-Class-Table.html)). Note that the syntax of a character, and thus which characters are considered “whitespace”, depends on the major mode.  

这与任何具有空白语法的字符相匹配（参见语法类别表）。请注意，字符的语法以及哪些字符被视为 "空白 "取决于主要模式。

‘\[:unibyte:\]’ ' \[:unibyte:\] '

This matches any unibyte character (see [Text Representations](https://www.gnu.org/software/emacs/manual/html_node/elisp/Text-Representations.html)).  

它匹配任何单字节字符（参见文本表示法）。

‘\[:upper:\]’ ' \[:upper:\] '

This matches any upper-case letter, as determined by the current case table (see [The Case Table](https://www.gnu.org/software/emacs/manual/html_node/elisp/Case-Tables.html)). If `case-fold-search` is non-`nil`, this also matches any lower-case letter. Note that a buffer can have its own local case table different from the default one.  

根据当前大小写表（请参阅大小写表），它匹配任何大写字母。如果 `case-fold-search` 不是 `nil` ，则也匹配任何小写字母。则也会匹配任何小写字母。请注意，缓冲区可以拥有不同于默认大小写表的本地大小写表。

‘\[:word:\]’ ' \[:word:\] '

This matches any character that has word syntax (see [Table of Syntax Classes](https://www.gnu.org/software/emacs/manual/html_node/elisp/Syntax-Class-Table.html)). Note that the syntax of a character, and thus which characters are considered “word-constituent”, depends on the major mode.  

这与任何具有单词语法的字符相匹配（参见语法类别表）。请注意，字符的语法以及哪些字符被视为 "由词构成 "取决于主要模式。

‘\[:xdigit:\]’ ' \[:xdigit:\] '

This matches the hexadecimal digits: ‘0’ through ‘9’, ‘a’ through ‘f’ and ‘A’ through ‘F’.  

这符合十六进制数字：" 0 '到' 9 ', ' a '到' f 和 ' A '到' F '.
