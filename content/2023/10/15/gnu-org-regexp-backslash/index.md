---
title: "Regexp 反斜线（GNU Emacs 手册）"
date: 2023-10-15T23:22:04+08:00
updated: 2023-10-15T23:22:04+08:00
taxonomies:
  tags: []
extra:
  source: https://www.gnu.org/software/emacs/manual/html_node/emacs/Regexp-Backslash.html
  hostname: www.gnu.org
  author: 
  original_title: "gnu.org"
  original_lang: en
---

For the most part, ‘\\’ followed by any character matches only that character. However, there are several exceptions: two-character sequences starting with ‘\\’ that have special meanings. The second character in the sequence is always an ordinary character when used on its own. Here is a table of ‘\\’ constructs.  

在大多数情况下，" \\ '后跟任何字符都只匹配该字符。但也有几个例外：以 ' \\ ' 开头的两个字符序列具有特殊含义。'开头的两个字符序列具有特殊含义。序列中的第二个字符单独使用时总是普通字符。以下是" \\ " 结构的表格。'结构的表格。

\\|

specifies an alternative. Two regular expressions a and b with ‘\\|’ in between form an expression that matches some text if either a matches it or b matches it. It works by trying to match a, and if that fails, by trying to match b.  

指定了一个替代方案。两个正则表达式 a 和 b 之间加上" \\| '组成一个表达式，当 a 与某个文本匹配或 b 与某个文本匹配时，该表达式就会匹配该文本。它的工作原理是尝试匹配 a，如果失败，则尝试匹配 b。

Thus, ‘foo\\|bar’ matches either ‘foo’ or ‘bar’ but no other string.  

因此，" foo\\|bar 与" foo "或" bar "匹配。"或" bar '，但不匹配其他字符串。

‘\\|’ applies to the largest possible surrounding expressions. Only a surrounding ‘\\( … \\)’ grouping can limit the grouping power of ‘\\|’.  

' \\| 适用于最大可能的周围表达式。只有周围的 ' \\( … \\) '分组可以限制' \\| '的分组能力。'.

Full backtracking capability exists to handle multiple uses of ‘\\|’.  

具有完全的回溯功能，可处理多次使用' \\| '的情况。'.

\\( … \\)

is a grouping construct that serves three purposes:  

是一种分组结构，有三个作用：

1.  To enclose a set of ‘\\|’ alternatives for other operations. Thus, ‘\\(foo\\|bar\\)x’ matches either ‘foox’ or ‘barx’.  
    
    包含一组" \\| '替代其他操作。因此，" \\(foo\\|bar\\)x '匹配 ' foox '或' barx '.
2.  To enclose a complicated expression for the postfix operators ‘\*’, ‘+’ and ‘?’ to operate on. Thus, ‘ba\\(na\\)\*’ matches ‘bananana’, etc., with any (zero or more) number of ‘na’ strings.  
    
    后置运算符" \* "、" + ', ' + 和 ' ? 进行运算。因此，" ba\\(na\\)\* 匹配 ' bananana '等字符串与任意（零或更多）数量的 ' na '字符串。
3.  To record a matched substring for future reference.  
    
    记录匹配的子字符串，以备将来参考。

This last application is not a consequence of the idea of a parenthetical grouping; it is a separate feature that is assigned as a second meaning to the same ‘\\( … \\)’ construct. In practice there is usually no conflict between the two meanings; when there is a conflict, you can use a shy group, described below.  

最后一种应用并不是括号分组概念的结果；它是一个单独的特征，被赋予了同一个" \\( … \\) "结构的第二层含义。"结构的第二个含义。在实践中，这两个含义之间通常不会发生冲突；当发生冲突时，可以使用下文所述的羞涩分组。

\\(?: … \\) [¶](https://www.gnu.org/software/emacs/manual/html_node/emacs/Regexp-Backslash.html#index-shy-group_002c-in-regexp)  \\(?: … \\) ¶

specifies a _shy group_ that does not record the matched substring; you can’t refer back to it with ‘\\d’ (see below). This is useful in mechanically combining regular expressions, so that you can add groups for syntactic purposes without interfering with the numbering of the groups that are meant to be referred to.  

指定了一个不记录匹配子字符串的 shy 组；您不能用 ' \\d ' 回调它（见下文）。'（见下文）。这在机械组合正则表达式时非常有用，这样就可以出于语法目的添加组，而不会影响要引用的组的编号。

\\d [¶](https://www.gnu.org/software/emacs/manual/html_node/emacs/Regexp-Backslash.html#index-back-reference_002c-in-regexp)  \\d ¶

matches the same text that matched the dth occurrence of a ‘\\( … \\)’ construct. This is called a _back reference_.  

匹配与" \\( … \\) "结构的第 d 次出现相匹配的相同文本。'结构体。这称为反向引用。

After the end of a ‘\\( … \\)’ construct, the matcher remembers the beginning and end of the text matched by that construct. Then, later on in the regular expression, you can use ‘\\’ followed by the digit d to mean “match the same text matched the dth ‘\\( … \\)’ construct”.  

在" \\( … \\) "结构体结束后，匹配器会记住该结构体所匹配文本的开头和结尾。结构体结束后，匹配器会记住该结构体所匹配文本的开头和结尾。然后，在正则表达式的后面，您可以使用" \\ 表示 "匹配与第 dth ' \\( … \\) ' 结构匹配的相同文本"。结构"。

The strings matching the first nine ‘\\( … \\)’ constructs appearing in a regular expression are assigned numbers 1 through 9 in the order that the open-parentheses appear in the regular expression. So you can use ‘\\1’ through ‘\\9’ to refer to the text matched by the corresponding ‘\\( … \\)’ constructs.  

与正则表达式中出现的前九个" \\( … \\) 结构的字符串会按照正则表达式中开放括号出现的顺序，被赋予 1 到 9 的编号。因此，您可以使用 ' \\1 到 ' \\9 来指代相应的 ' \\( … \\) ' 结构所匹配的文本。'结构所匹配的文本。

For example, ‘\\(.\*\\)\\1’ matches any newline-free string that is composed of two identical halves. The ‘\\(.\*\\)’ matches the first half, which may be anything, but the ‘\\1’ that follows must match the same exact text.  

例如，" \\(.\*\\)\\1 匹配任何由两个相同部分组成的无换行符字符串。 \\(.\*\\) 匹配前半部分，前半部分可以是任何内容，但后面的 ' \\1 '必须匹配完全相同的文本。

If a particular ‘\\( … \\)’ construct matches more than once (which can easily happen if it is followed by ‘\*’), only the last match is recorded.  

如果某个" \\( … \\) 结构匹配多次（如果后面有" \* "，这种情况很容易发生），则只记录最后一次匹配。

\\{m\\}

is a postfix operator specifying m repetitions—that is, the preceding regular expression must match exactly m times in a row. For example, ‘x\\{4\\}’ matches the string ‘xxxx’ and nothing else.  

是一个后缀运算符，指定了 m 次重复，也就是说，前面的正则表达式必须连续匹配 m 次。例如，" x\\{4\\} 匹配字符串" xxxx 匹配字符串" xxxx "，而不匹配其他字符串。

\\{m,n\\}

is a postfix operator specifying between m and n repetitions—that is, the preceding regular expression must match at least m times, but no more than n times. If n is omitted, then there is no upper limit, but the preceding regular expression must match at least m times.  

是一个后缀运算符，指定 m 到 n 之间的重复次数，也就是说，前面的正则表达式必须至少匹配 m 次，但不超过 n 次。如果省略 n，则没有上限，但前面的正则表达式必须至少匹配 m 次。  

‘\\{0,1\\}’ is equivalent to ‘?’.  

' \\{0,1\\} '等同于' ? '.  

‘\\{0,\\}’ is equivalent to ‘\*’.  

' \\{0,\\} '等同于' \* '.  

‘\\{1,\\}’ is equivalent to ‘+’.  

' \\{1,\\} '等同于' + '.

\\\`

matches the empty string, but only at the beginning of the string or buffer (or its accessible portion) being matched against.  

会匹配空字符串，但只能匹配字符串或缓冲区（或其可访问部分）的开头。

\\'

matches the empty string, but only at the end of the string or buffer (or its accessible portion) being matched against.  

会匹配空字符串，但仅限于与之匹配的字符串或缓冲区（或其可访问部分）的末尾。

\\=

matches the empty string, but only at point.  

匹配空字符串，但仅限于点。

\\b

matches the empty string, but only at the beginning or end of a word. Thus, ‘\\bfoo\\b’ matches any occurrence of ‘foo’ as a separate word. ‘\\bballs?\\b’ matches ‘ball’ or ‘balls’ as a separate word.  

匹配空字符串，但仅限于单词的开头或结尾。因此，" \\bfoo\\b 匹配" foo "的任何出现。作为一个单独的单词。' \\bballs?\\b 匹配" ball "或" balls '作为单独的单词。

‘\\b’ matches at the beginning or end of the buffer regardless of what text appears next to it.  

' \\b '匹配缓冲区的开头或结尾，而不管其旁边出现的是什么文本。

\\B

matches the empty string, but _not_ at the beginning or end of a word.  

匹配空字符串，但不匹配单词的开头或结尾。

\\<

matches the empty string, but only at the beginning of a word. ‘\\<’ matches at the beginning of the buffer only if a word-constituent character follows.  

匹配空字符串，但仅限于单词的开头。' \\< '仅在后面有单词组成字符时匹配缓冲区的开头。

\\>

matches the empty string, but only at the end of a word. ‘\\>’ matches at the end of the buffer only if the contents end with a word-constituent character.  

匹配空字符串，但仅限于单词末尾。' \\> '仅在缓冲区内容以单词组成字符结尾时匹配缓冲区结尾。

\\w

matches any word-constituent character. The syntax table determines which characters these are. See [Syntax Tables](https://www.gnu.org/software/emacs/manual/html_node/elisp/Syntax-Tables.html#Syntax-Tables) in The Emacs Lisp Reference Manual.  

匹配任何由单词构成的字符。语法表确定了这些字符。请参阅《Emacs Lisp 参考手册》中的语法表。

\\W

matches any character that is not a word-constituent.  

匹配任何非单词成分的字符。

\\\_<

matches the empty string, but only at the beginning of a symbol. A symbol is a sequence of one or more symbol-constituent characters. A symbol-constituent character is a character whose syntax is either ‘w’ or ‘\_’. ‘\\\_<’ matches at the beginning of the buffer only if a symbol-constituent character follows. As with words, the syntax table determines which characters are symbol-constituent.  

匹配空字符串，但仅限于符号的开头。符号是一个或多个符号组成字符的序列。符号组成字符的语法为" w "或" \_ "。"或" \_ '.' \\\_< \\\_< '只有在缓冲区开头有符号构成字符时才会匹配。与单词一样，语法表决定了哪些字符是由符号构成的。

\\\_>

matches the empty string, but only at the end of a symbol. ‘\\\_>’ matches at the end of the buffer only if the contents end with a symbol-constituent character.  

匹配空字符串，但仅限于符号末尾。' \\\_> '仅在缓冲区内容以符号组成字符结尾时匹配缓冲区的结尾。

\\sc

matches any character whose syntax is c. Here c is a character that designates a particular syntax class: thus, ‘w’ for word constituent, ‘\-’ or ‘ ’ for whitespace, ‘.’ for ordinary punctuation, etc. See [Syntax Class Table](https://www.gnu.org/software/emacs/manual/html_node/elisp/Syntax-Class-Table.html#Syntax-Class-Table) in The Emacs Lisp Reference Manual.  

匹配语法为 c 的任何字符。这里的 c 是指定特定语法类别的字符：因此，" w 表示单词成分，" \- '或' 表示空白，' . 表示普通标点符号，等等。表示普通标点符号，等等。参见《Emacs Lisp 参考手册》中的语法类表。

\\Sc

matches any character whose syntax is not c.  

匹配语法不是 c 的任何字符。

\\cc

matches any character that belongs to the category c. For example, ‘\\cc’ matches Chinese characters, ‘\\cg’ matches Greek characters, etc. For the description of the known categories, type M-x describe-categories RET.  

匹配属于 c 类别的任何字符。例如，" \\cc " 匹配中文字符，" \\cg " 匹配英文字符。'匹配汉字，' \\cg 匹配希腊字符等。有关已知类别的说明，请键入 M-x describe-categories RET 。.

\\Cc

matches any character that does _not_ belong to category c.  

匹配任何不属于 c 类别的字符。

The constructs that pertain to words and syntax are controlled by the setting of the syntax table. See [Syntax Tables](https://www.gnu.org/software/emacs/manual/html_node/elisp/Syntax-Tables.html#Syntax-Tables) in The Emacs Lisp Reference Manual.  

与单词和语法有关的构造由语法表的设置控制。请参阅《Emacs Lisp 参考手册》中的语法表。
