---
title: "Regexps 正则表达式（GNU Emacs Manual）"
date: 2023-10-03T23:02:15+08:00
updated: 2023-10-03T23:02:15+08:00
taxonomies:
  tags: []
extra:
  source: https://www.gnu.org/software/emacs/manual/html_node/emacs/Regexps.html
  hostname: www.gnu.org
  author: 
  original_title: "gnu.org"
  original_lang: en
---

This section (and this manual in general) describes regular expression features that users typically use. See [Regular Expressions](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regular-Expressions.html#Regular-Expressions) in The Emacs Lisp Reference Manual, for additional features used mainly in Lisp programs.  

本节（以及本手册的一般内容）介绍用户通常使用的正则表达式功能。有关主要在 Lisp 程序中使用的其他功能，请参阅《Emacs Lisp 参考手册》中的正则表达式。

Regular expressions have a syntax in which a few characters are _special constructs_ and the rest are _ordinary_. An ordinary character matches that same character and nothing else. The special characters are ‘$^.\*+?\[\\’. The character ‘\]’ is special if it ends a character alternative (see below). The character ‘\-’ is special inside a character alternative. Any other character appearing in a regular expression is ordinary, unless a ‘\\’ precedes it. (When you use regular expressions in a Lisp program, each ‘\\’ must be doubled, see the example near the end of this section.)  

正则表达式的语法中，有几个字符是特殊结构，其余都是普通字符。普通字符只匹配相同的字符，不匹配其他字符。特殊字符是 ' $^.\*+?\[\\ ' 。'.字符" \] '是特殊字符，如果它结束了一个替代字符（见下文）。字符 ' \- 字符"\- "在字符替代码中是特殊字符。正则表达式中出现的任何其他字符都是普通字符，除非前面有 ' \\ 前面有"\\ "。(在 Lisp 程序中使用正则表达式时，每个 ' \\ ' 必须加倍，参见示例。必须加倍，参见本节末尾的示例）。

For example, ‘f’ is not a special character, so it is ordinary, and therefore ‘f’ is a regular expression that matches the string ‘f’ and no other string. (It does _not_ match the string ‘ff’.) Likewise, ‘o’ is a regular expression that matches only ‘o’. (When case distinctions are being ignored, these regexps also match ‘F’ and ‘O’, but we consider this a generalization of “the same string”, rather than an exception.)  

例如，" f 不是特殊字符，所以是普通字符，因此 ' f 是一个正则表达式，它匹配字符串" f "，而不匹配其他字符串。和其他字符串。(同样，" o " 也是一个正则表达式，只匹配字符串" f "，不匹配其他字符串。｝是一个正则表达式，只匹配" o "。'.(当忽略大小写区别时，这些正则表达式还匹配 ' F 和 ' O 和 ' O 但我们认为这是 "同一字符串 "的概括，而不是例外）。

Any two regular expressions a and b can be concatenated. The result is a regular expression which matches a string if a matches some amount of the beginning of that string and b matches the rest of the string. As a trivial example, concatenating the regular expressions ‘f’ and ‘o’ gives the regular expression ‘fo’, which matches only the string ‘fo’. To do something less trivial, you need to use one of the special characters. Here is a list of them.  

可以将任意两个正则表达式 a 和 b 连接起来。如果 a 与字符串开头部分匹配，而 b 与字符串其余部分匹配，那么结果就是一个正则表达式。举个简单的例子，将正则表达式" f 和" o 的正则表达式" fo 只匹配字符串" fo "。'.要做一些不那么琐碎的事情，需要使用其中一个特殊字符。下面是一个特殊字符列表。

. (Period)  . （期间）

is a special character that matches any single character except a newline. For example, the regular expressions ‘a.b’ matches any three-character string that begins with ‘a’ and ends with ‘b’.  

是一个特殊字符，可以匹配除换行符以外的任何单个字符。例如，正则表达式 ' a.b 匹配以 ' a ' 开头、以 ' b ' 结尾的任何三个字符的字符串。'和以'b '结尾的三个字符串。'.

\*

is not a construct by itself; it is a postfix operator that means to match the preceding regular expression repetitively any number of times, as many times as possible. Thus, ‘o\*’ matches any number of ‘o’s, including no ‘o’s.  

本身并不是一个结构；它是一个后缀运算符，表示重复匹配前面的正则表达式，次数不限，越多越好。因此，" o\* 匹配任意数量的 ' o '，包括不匹配 ' o '。's.

‘\*’ always applies to the _smallest_ possible preceding expression. Thus, ‘fo\*’ has a repeating ‘o’, not a repeating ‘fo’. It matches ‘f’, ‘fo’, ‘foo’, and so on.  

' \* '总是适用于前面的最小表达式。因此， ' fo\* ' 有一个重复的 ' o '，而不是重复的 ' fo '。'.它匹配 ' f ', ' fo ', ' foo '等。

The matcher processes a ‘\*’ construct by matching, immediately, as many repetitions as can be found. Then it continues with the rest of the pattern. If that fails, backtracking occurs, discarding some of the matches of the ‘\*’-modified construct in case that makes it possible to match the rest of the pattern. For example, in matching ‘ca\*ar’ against the string ‘caaar’, the ‘a\*’ first tries to match all three ‘a’s; but the rest of the pattern is ‘ar’ and there is only ‘r’ left to match, so this try fails. The next alternative is for ‘a\*’ to match only two ‘a’s. With this choice, the rest of the regexp matches successfully.  

匹配器处理" \* 构造时，会立即匹配尽可能多的重复。然后继续处理模式的其余部分。如果匹配失败，则进行回溯，丢弃" \* "修改后结构的部分匹配结果。'修改过的结构体的部分匹配，以防因此而可能匹配到模式的其余部分。例如，在匹配" ca\*ar 匹配字符串" caaar 匹配时，" a\* 首先会尝试匹配所有三个" a 但模式的其余部分是 ' ar 只剩下 ' r 匹配，因此尝试失败。下一个选择是让 ' a\* 只匹配两个" a 's.这样，regexp 的其余部分就能成功匹配。

+

is a postfix operator, similar to ‘\*’ except that it must match the preceding expression at least once. Thus, ‘ca+r’ matches the strings ‘car’ and ‘caaaar’ but not the string ‘cr’, whereas ‘ca\*r’ matches all three strings.  

是一个后缀运算符，类似于" \* 除了必须至少与前面的表达式匹配一次之外。因此，' ca+r 匹配字符串 ' car 和 ' caaaar 但不匹配字符串 ' cr 匹配字符串" ca\*r "，而" ca\*r 则匹配所有三个字符串。

?

is a postfix operator, similar to ‘\*’ except that it can match the preceding expression either once or not at all. Thus, ‘ca?r’ matches ‘car’ or ‘cr’, and nothing else.  

是一个后缀运算符，类似于" \* '的不同之处在于，它可以与前面的表达式匹配一次，也可以完全不匹配。因此，' ca?r 匹配 ' car 或 ' cr '，而不匹配其他表达式。

\*?, +?, ?? [¶](https://www.gnu.org/software/emacs/manual/html_node/emacs/Regexps.html#index-non_002dgreedy-regexp-matching)  

\*? , +? , ?? ¶

are non-_greedy_ variants of the operators above. The normal operators ‘\*’, ‘+’, ‘?’ match as much as they can, as long as the overall regexp can still match. With a following ‘?’, they will match as little as possible.  

是上述算子的非贪心变体。正常算子 ' \* ', ' + ', ' ? 只要整个 regexp 仍能匹配，它们就能尽可能多地匹配。如果后面有 ' ? 则尽可能少匹配。

Thus, both ‘ab\*’ and ‘ab\*?’ can match the string ‘a’ and the string ‘abbbb’; but if you try to match them both against the text ‘abbb’, ‘ab\*’ will match it all (the longest valid match), while ‘ab\*?’ will match just ‘a’ (the shortest valid match).  

因此，" ab\* 和" ab\*? 可以匹配字符串" a 和字符串" abbbb 但如果尝试将它们同时与文本" abbb ', ' ab\* 将全部匹配（最长有效匹配），而" ab\*? 将只匹配" a '（最短的有效匹配）。

Non-greedy operators match the shortest possible string starting at a given starting point; in a forward search, though, the earliest possible starting point for match is always the one chosen. Thus, if you search for ‘a.\*?$’ against the text ‘abbab’ followed by a newline, it matches the whole string. Since it _can_ match starting at the first ‘a’, it does.  

非贪心运算符会从给定的起点开始匹配最短的字符串；但在前向搜索中，总是选择最早的起点进行匹配。因此，如果您搜索 ' a.\*?$ 的文本" abbab 后跟换行符，它就会匹配整个字符串。既然可以从第一个 ' a ' 开始匹配，那么就匹配了。'开始匹配，所以它就匹配了。

\[ … \]

is a _set of alternative characters_, or a _character set_, beginning with ‘\[’ and terminated by ‘\]’.  

是一组备选字符或字符集，以" \[ "开头，以" \] "结束。'开始，以' \] '结束。'.

In the simplest case, the characters between the two brackets are what this set can match. Thus, ‘\[ad\]’ matches either one ‘a’ or one ‘d’, and ‘\[ad\]\*’ matches any string composed of just ‘a’s and ‘d’s (including the empty string). It follows that ‘c\[ad\]\*r’ matches ‘cr’, ‘car’, ‘cdr’, ‘caddaar’, etc.  

在最简单的情况下，两个括号之间的字符就是该字符集可以匹配的字符。因此，" \[ad\] 匹配一个 ' a "或" d 和" \[ad\]\* '匹配任何由' a 和 ' d 的字符串（包括空字符串）。由此可见，" c\[ad\]\*r 匹配" cr ', ' car ', ' cdr ', ' caddaar 等等。

You can also include character ranges in a character set, by writing the starting and ending characters with a ‘\-’ between them. Thus, ‘\[a-z\]’ matches any lower-case ASCII letter. Ranges may be intermixed freely with individual characters, as in ‘\[a-z$%.\]’, which matches any lower-case ASCII letter or ‘$’, ‘%’ or period. As another example, ‘\[α-ωί\]’ matches all lower-case Greek letters.  

您还可以在字符集中包含字符范围，方法是在起始字符和终止字符之间写上" \- "。'夹在中间。因此，" \[a-z\] 匹配任何小写 ASCII 字母。范围可以与单个字符自由混合，如" \[a-z$%.\] '匹配任何小写 ASCII 字母或' $ ', ' % 或句号。又如，" \[α-ωί\] 匹配所有小写希腊字母。

You can also include certain special _character classes_ in a character set. A ‘\[:’ and balancing ‘:\]’ enclose a character class inside a set of alternative characters. For instance, ‘\[\[:alnum:\]\]’ matches any letter or digit. See [Char Classes](https://www.gnu.org/software/emacs/manual/html_node/elisp/Char-Classes.html#Char-Classes) in The Emacs Lisp Reference Manual, for a list of character classes.  

您还可以在字符集中包含某些特殊字符类。A ' \[: '和平衡 ' :\] '将字符类别包含在一组备选字符中。例如，" \[\[:alnum:\]\] 匹配任何字母或数字。有关字符类的列表，请参见《Emacs Lisp 参考手册》中的字符类。

To include a ‘\]’ in a character set, you must make it the first character. For example, ‘\[\]a\]’ matches ‘\]’ or ‘a’. To include a ‘\-’, write ‘\-’ as the last character of the set, tho you can also put it first or after a range. Thus, ‘\[\]-\]’ matches both ‘\]’ and ‘\-’.  

要在字符集中包含 ' \] 必须使其成为第一个字符。例如，" \[\]a\] 匹配 ' \] '或 ' a '.要包含 ' \- 要包含"\- "，请写入" \- '作为字符集的最后一个字符，但也可以将其放在字符串的前面或后面。因此，" \[\]-\] 匹配" \] "和" \- "。"和" \- '.

To include ‘^’ in a set, put it anywhere but at the beginning of the set. (At the beginning, it complements the set—see below.)  

要将" ^ 要在集合中加入" ^ "，请将其放在集合开头以外的任何位置。(在开头，它是对集合的补充--见下文）。

When you use a range in case-insensitive search, you should write both ends of the range in upper case, or both in lower case, or both should be non-letters. The behavior of a mixed-case range such as ‘A-z’ is somewhat ill-defined, and it may change in future Emacs versions.  

在大小写不敏感搜索中使用范围时，应将范围的两端都写成大写，或都写成小写，或都写成非字母。混合大小写范围的行为，例如" A-z '这样的混合大小写范围的行为有些定义不清，在未来的 Emacs 版本中可能会有所改变。

\[^ … \]

‘\[^’ begins a _complemented character set_, which matches any character except the ones specified. Thus, ‘\[^a-z0-9A-Z\]’ matches all characters _except_ ASCII letters and digits.  

' \[^ 开始一个补充字符集，该字符集匹配指定字符以外的任何字符。因此，" \[^a-z0-9A-Z\] 匹配除 ASCII 字母和数字以外的所有字符。

‘^’ is not special in a character set unless it is the first character. The character following the ‘^’ is treated as if it were first (in other words, ‘\-’ and ‘\]’ are not special there).  

' ^ 除非是第一个字符，否则在字符集中并不特殊。而" ^ "后面的字符则被视为第一个字符（换句话说，" \- "和" \] "在这里并不特殊。后的字符被视为第一个字符（换句话说，" \- "和" \] "并不特殊）。

A complemented character set can match a newline, unless newline is mentioned as one of the characters not to match. This is in contrast to the handling of regexps in programs such as `grep`.  

补码字符集可以匹配换行符，除非换行符被列为不匹配字符之一。这与 `grep` 等程序对 regexps 的处理形成鲜明对比。.

^

is a special character that matches the empty string, but only at the beginning of a line in the text being matched. Otherwise it fails to match anything. Thus, ‘^foo’ matches a ‘foo’ that occurs at the beginning of a line.  

是一个特殊字符，可以匹配空字符串，但仅限于被匹配文本的行首。否则，它将无法匹配任何内容。因此，" ^foo 与" foo "匹配。"会匹配出现在一行开头的" foo "。

For historical compatibility reasons, ‘^’ can be used with this meaning only at the beginning of the regular expression, or after ‘\\(’ or ‘\\|’.  

出于历史兼容性原因，" ^ '只能在正则表达式的开头或' \\( '或' \\| '之后使用。'或' \\| '之后。'.

$

is similar to ‘^’ but matches only at the end of a line. Thus, ‘x+$’ matches a string of one ‘x’ or more at the end of a line.  

类似于 ' ^ '类似，但只在行尾匹配。因此，" x+$ '匹配一行末尾一个或多个 ' x ' 的字符串。'或更多的字符串。

For historical compatibility reasons, ‘$’ can be used with this meaning only at the end of the regular expression, or before ‘\\)’ or ‘\\|’.  

出于历史兼容性原因，" $ '只能在正则表达式的末尾或' \\) '或' \\| '之前使用。'或' \\| '之前使用。'.

\\

has two functions: it quotes the special characters (including ‘\\’), and it introduces additional special constructs.  

有两个功能：引用特殊字符（包括 ' \\ '），并引入额外的特殊结构。

Because ‘\\’ quotes special characters, ‘\\$’ is a regular expression that matches only ‘$’, and ‘\\\[’ is a regular expression that matches only ‘\[’, and so on.  

因为 ' \\ 引用了特殊字符，因此 ' \\$ 是一个正则表达式，只匹配 ' $ 和 ' \\\[ 是只匹配 ' \[ ' 的正则表达式，以此类推。以此类推。

See the following section for the special constructs that begin with ‘\\’.  

有关以" \\ "开头的特殊结构体，请参见下一节。'.

Note: for historical compatibility, special characters are treated as ordinary ones if they are in contexts where their special meanings make no sense. For example, ‘\*foo’ treats ‘\*’ as ordinary since there is no preceding expression on which the ‘\*’ can act. It is poor practice to depend on this behavior; it is better to quote the special character anyway, regardless of where it appears.  

注意：为了历史兼容性，如果特殊字符的特殊含义没有意义，则将其视为普通字符。例如，" \*foo "将" \* '视为普通字符，因为前面没有" \* "可以作用的表达式。可以起作用。依赖这种行为的做法并不可取；最好还是引用特殊字符，无论它出现在何处。

As a ‘\\’ is not special inside a set of alternative characters, it can never remove the special meaning of ‘\-’, ‘^’ or ‘\]’. You should not quote these characters when they have no special meaning. This would not clarify anything, since backslashes can legitimately precede these characters where they _have_ special meaning, as in ‘\[^\\\]’ (`"[^\\]"` for Lisp string syntax), which matches any single character except a backslash.  

由于" \\ 由于" \\ "在一组备选字符中并不特殊，因此它永远无法消除" \- "、" ^ "和" \] "的特殊含义。', ' ^ "或" \] '.如果这些字符没有特殊含义，则不应引用。这样做并不能说明任何问题，因为反斜线可以合法地出现在这些具有特殊含义的字符之前，如' \[^\\\] '（Lisp 字符串语法中为 `"[^\\]"` ），它匹配反斜线以外的任何单字符。
