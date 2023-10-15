---
title: "Regexp Special（GNU Emacs Lisp 参考手册）"
date: 2023-10-15T23:22:12+08:00
updated: 2023-10-15T23:22:12+08:00
taxonomies:
  tags: []
extra:
  source: https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html
  hostname: www.gnu.org
  author: 
  original_title: "gnu.org"
  original_lang: en
---

Here is a list of the characters that are special in a regular expression.  

下面列出了正则表达式中的特殊字符。

‘.’ (Period) [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_002e-in-regexp)  

' . '（句号

is a special character that matches any single character except a newline. Using concatenation, we can make regular expressions like ‘a.b’, which matches any three-character string that begins with ‘a’ and ends with ‘b’.  

是一个特殊字符，可以匹配除换行符外的任何单个字符。通过连接，我们可以创建正则表达式，如" a.b '，它可以匹配以' a '开头，以' b '结尾的任何三个字符的字符串。'和以' b '结尾的三个字符串。'.

‘\*’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_002a-in-regexp)  

' \* ' ¶

is not a construct by itself; it is a postfix operator that means to match the preceding regular expression repetitively as many times as possible. Thus, ‘o\*’ matches any number of ‘o’s (including no ‘o’s).  

本身并不是一个结构；它是一个后缀运算符，表示尽可能多次重复匹配前面的正则表达式。因此，" o\* 匹配任意数量的 ' o '（包括不匹配 ' o '）。

‘\*’ always applies to the _smallest_ possible preceding expression. Thus, ‘fo\*’ has a repeating ‘o’, not a repeating ‘fo’. It matches ‘f’, ‘fo’, ‘foo’, and so on.  

' \* '总是适用于前面的最小表达式。因此， ' fo\* ' 有一个重复的 ' o '，而不是重复的 ' fo '。'.它匹配 ' f ', ' fo ', ' foo '等。

The matcher processes a ‘\*’ construct by matching, immediately, as many repetitions as can be found. Then it continues with the rest of the pattern. If that fails, backtracking occurs, discarding some of the matches of the ‘\*’-modified construct in the hope that this will make it possible to match the rest of the pattern. For example, in matching ‘ca\*ar’ against the string ‘caaar’, the ‘a\*’ first tries to match all three ‘a’s; but the rest of the pattern is ‘ar’ and there is only ‘r’ left to match, so this try fails. The next alternative is for ‘a\*’ to match only two ‘a’s. With this choice, the rest of the regexp matches successfully.  

匹配器处理" \* 构造时，会立即匹配尽可能多的重复。然后继续处理模式的其余部分。如果匹配失败，就会进行回溯，丢弃" \* "修改过的结构体的部分匹配结果。'修改过的结构的部分匹配，希望这样可以匹配到模式的其余部分。例如，在匹配字符串" ca\*ar 匹配字符串" caaar 匹配时，" a\* 首先尝试匹配所有三个" a 但模式的其余部分是 ' ar 只剩下 ' r 匹配，因此尝试失败。下一个选择是让 ' a\* 只匹配两个" a 's.这样，regexp 的其余部分就能成功匹配。

‘+’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_002b-in-regexp)  

' + ' ¶

is a postfix operator, similar to ‘\*’ except that it must match the preceding expression at least once. So, for example, ‘ca+r’ matches the strings ‘car’ and ‘caaaar’ but not the string ‘cr’, whereas ‘ca\*r’ matches all three strings.  

是一个后缀运算符，类似于" \* 除了必须至少与前面的表达式匹配一次之外。例如，" ca+r 匹配字符串 ' car 和 ' caaaar 但不匹配字符串 ' cr 匹配字符串" ca\*r "，而" ca\*r 则匹配所有三个字符串。

‘?’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_003f-in-regexp)  

' ? ' ¶

is a postfix operator, similar to ‘\*’ except that it must match the preceding expression either once or not at all. For example, ‘ca?r’ matches ‘car’ or ‘cr’; nothing else.  

是一个后缀运算符，类似于" \* 除了必须与前面的表达式匹配一次或完全不匹配之外。例如，' ca?r 匹配 ' car 或 ' cr 或 ' cr ；除此之外，不能匹配任何其他表达式。

‘\*?’, ‘+?’, ‘??’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-non_002dgreedy-repetition-characters-in-regexp)  

' \*? ', ' +? ', ' ?? ' ¶

are _non-greedy_ variants of the operators ‘\*’, ‘+’ and ‘?’. Where those operators match the largest possible substring (consistent with matching the entire containing expression), the non-greedy variants match the smallest possible substring (consistent with matching the entire containing expression).  

是运算符 ' \* ' 、 ' + ' 的非贪心变体。', ' + '和' ? '.这些运算符匹配最大的子串（与匹配整个包含表达式一致），而非贪心变体匹配最小的子串（与匹配整个包含表达式一致）。

For example, the regular expression ‘c\[ad\]\*a’ when applied to the string ‘cdaaada’ matches the whole string; but the regular expression ‘c\[ad\]\*?a’, applied to that same string, matches just ‘cda’. (The smallest possible match here for ‘\[ad\]\*?’ that permits the whole expression to match is ‘d’.)  

例如，正则表达式" c\[ad\]\*a 应用于字符串 ' cdaaada 时，会匹配整个字符串；但正则表达式 ' c\[ad\]\*?a 匹配整个字符串；但正则表达式"c\[ad\]\*?a 应用于同一字符串时，只匹配 ' cda '。'.(这里" \[ad\]\*? "的最小匹配可能是的最小匹配是" d "）。'.)

‘\[ … \]’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-character-alternative-_0028in-regexp_0029)  

' \[ … \] ' ¶

is a _character alternative_, which begins with ‘\[’ and is terminated by ‘\]’. In the simplest case, the characters between the two brackets are what this character alternative can match.  

是一个替代字符，以" \[ "开头，以" \] "结束。'开始，以" \] "结束。'.在最简单的情况下，两个括号之间的字符就是该字符备选方案可以匹配的字符。

Thus, ‘\[ad\]’ matches either one ‘a’ or one ‘d’, and ‘\[ad\]\*’ matches any string composed of just ‘a’s and ‘d’s (including the empty string). It follows that ‘c\[ad\]\*r’ matches ‘cr’, ‘car’, ‘cdr’, ‘caddaar’, etc.  

因此，" \[ad\] 匹配一个 ' a "或" d 匹配，而" \[ad\]\* 匹配任何由" a "和" d "组成的字符串。和 ' d 的字符串（包括空字符串）。由此可见，" c\[ad\]\*r 匹配" cr ', ' car ', ' cdr ', ' caddaar 等等。

You can also include character ranges in a character alternative, by writing the starting and ending characters with a ‘\-’ between them. Thus, ‘\[a-z\]’ matches any lower-case ASCII letter. Ranges may be intermixed freely with individual characters, as in ‘\[a-z$%.\]’, which matches any lower case ASCII letter or ‘$’, ‘%’ or period. However, the ending character of one range should not be the starting point of another one; for example, ‘\[a-m-z\]’ should be avoided.  

您也可以在字符备选方案中包含字符范围，方法是在起始字符和终止字符之间加上" \- "。之间。因此，" \[a-z\] 匹配任何小写 ASCII 字母。范围可以与单个字符自由混合，如" \[a-z$%.\] '匹配任何小写 ASCII 字母或' $ ', ' % 或句号。但是，一个范围的结束字符不应该是另一个范围的起点；例如，" \[a-m-z\] 例如，应避免使用" \[a-m-z\] "。

A character alternative can also specify named character classes (see [Character Classes](https://www.gnu.org/software/emacs/manual/html_node/elisp/Char-Classes.html)). For example, ‘\[\[:ascii:\]\]’ matches any ASCII character. Using a character class is equivalent to mentioning each of the characters in that class; but the latter is not feasible in practice, since some classes include thousands of different characters. A character class should not appear as the lower or upper bound of a range.  

字符备选方案还可以指定已命名的字符类别（请参阅字符类别）。例如，" \[\[:ascii:\]\] 匹配任何 ASCII 字符。使用字符类等同于提及该类中的每个字符；但后者在实践中并不可行，因为有些字符类包括数千个不同的字符。字符类不应作为范围的下限或上限出现。

The usual regexp special characters are not special inside a character alternative. A completely different set of characters is special: ‘\]’, ‘\-’ and ‘^’. To include ‘\]’ in a character alternative, put it at the beginning. To include ‘^’, put it anywhere but at the beginning. To include ‘\-’, put it at the end. Thus, ‘\[\]^-\]’ matches all three of these special characters. You cannot use ‘\\’ to escape these three characters, since ‘\\’ is not special here.  

通常的 regexp 特殊字符在字符替代码中并不特殊。一组完全不同的字符是特殊字符：" \] ', ' \- 和 ' ^ '.要在字符替代码中包含" \] 请将其放在开头。要包含" ^ 要包含" ^ "，请将其放在开头以外的任何位置。要包含 ' \- 要包含"\- "，请将其放在末尾。因此，" \[\]^-\] 匹配所有这三个特殊字符。不能使用 ' \\ 来转义这三个字符，因为" \\ "在此处并不特殊。在这里并不特殊。

The following aspects of ranges are specific to Emacs, in that POSIX allows but does not require this behavior and programs other than Emacs may behave differently:  

范围的以下方面是 Emacs 特有的，POSIX 允许但不要求这种行为，Emacs 以外的程序可能会有不同的行为：

1.  If `case-fold-search` is non-`nil`, ‘\[a-z\]’ also matches upper-case letters.  
    
    如果 `case-fold-search` 不是 `nil` ，则' \[a-z\] 为 `nil` 。, ' \[a-z\] '也匹配大写字母。
2.  A range is not affected by the locale’s collation sequence: it always represents the set of characters with codepoints ranging between those of its bounds, so that ‘\[a-z\]’ matches only ASCII letters, even outside the C or POSIX locale.  
    
    范围不受本地语言校对序列的影响：它总是表示码位在其边界之间的字符集，因此" \[a-z\] "只匹配 ASCII 字母，即使在 C 或 POSIX 本地语言之外也是如此。因此" \[a-z\] "只匹配 ASCII 字母，即使在 C 或 POSIX 本地语言之外也是如此。
3.  If the lower bound of a range is greater than its upper bound, the range is empty and represents no characters. Thus, ‘\[z-a\]’ always fails to match, and ‘\[^z-a\]’ matches any character, including newline. However, a reversed range should always be from the letter ‘z’ to the letter ‘a’ to make it clear that it is not a typo; for example, ‘\[+-\*/\]’ should be avoided, because it matches only ‘/’ rather than the likely-intended four characters.  
    
    如果范围的下限大于上限，则范围为空，不代表任何字符。因此，" \[z-a\] '总是无法匹配，而' \[^z-a\] 匹配任何字符，包括换行符。但是，反转范围应始终从字母 ' z 到字母" a 例如，" \[+-\*/\] "应避免与" \[+-\*/\] "匹配。应避免使用" \[+-\*/\] "，因为它只匹配" / "，而不是" / "。而不是原意的四个字符。
4.  If the end points of a range are raw 8-bit bytes (see [Text Representations](https://www.gnu.org/software/emacs/manual/html_node/elisp/Text-Representations.html)), or if the range start is ASCII and the end is a raw byte (as in ‘\[a-\\377\]’), the range will match only ASCII characters and raw 8-bit bytes, but not non-ASCII characters. This feature is intended for searching text in unibyte buffers and strings.  
    
    如果范围的终点是原始 8 位字节（请参阅 "文本表示法"），或者范围的起点是 ASCII，终点是原始字节（如" \[a-\\377\] "），则范围将只匹配 ASCII 字符和原始 8 位字节，而不匹配非 ASCII 字符。该功能用于搜索单字节缓冲区和字符串中的文本。

Some kinds of character alternatives are not the best style even though they have a well-defined meaning in Emacs. They include:  

有些字符虽然在 Emacs 中有明确的含义，但并非最佳样式。它们包括

1.  Although a range’s bound can be almost any character, it is better style to stay within natural sequences of ASCII letters and digits because most people have not memorized character code tables. For example, ‘\[.-9\]’ is less clear than ‘\[./0-9\]’, and ‘\[\`-~\]’ is less clear than ‘\[\`a-z{|}~\]’. Unicode character escapes can help here; for example, for most programmers ‘\[ก-ฺ฿-๛\]’ is less clear than ‘\[\\u0E01-\\u0E3A\\u0E3F-\\u0E5B\]’.  
    
    虽然范围的边界几乎可以是任何字符，但由于大多数人都没有记住字符编码表，所以最好还是保持 ASCII 字母和数字的自然序列。例如，" \[.-9\] "比" \[./0-9\] "更不清晰。和" \[\`-~\] 不如" \[\`a-z{|}~\] "清晰。'.Unicode 字符转义可以在这方面提供帮助；例如，对于大多数程序员来说，" \[ก-ฺ฿-๛\] 对大多数程序员来说，" \[ก-ฺ฿-๛\] "比" \[\\u0E01-\\u0E3A\\u0E3F-\\u0E5B\] "更不清晰。'.
2.  Although a character alternative can include duplicates, it is better style to avoid them. For example, ‘\[XYa-yYb-zX\]’ is less clear than ‘\[XYa-z\]’.  
    
    尽管字符备选方案可以包含重复字符，但最好避免使用。例如，" \[XYa-yYb-zX\] '不如' \[XYa-z\] '清晰。'.
3.  Although a range can denote just one, two, or three characters, it is simpler to list the characters. For example, ‘\[a-a0\]’ is less clear than ‘\[a0\]’, ‘\[i-j\]’ is less clear than ‘\[ij\]’, and ‘\[i-k\]’ is less clear than ‘\[ijk\]’.  
    
    虽然范围可以只表示一个、两个或三个字符，但列出字符更简单。例如，" \[a-a0\] '不如' \[a0\] '清晰。', ' \[i-j\] "比" \[ij\] "更不清晰"比" \[i-k\] '不如' \[ijk\] '清晰。'.
4.  Although a ‘\-’ can appear at the beginning of a character alternative or as the upper bound of a range, it is better style to put ‘\-’ by itself at the end of a character alternative. For example, although ‘\[-a-z\]’ is valid, ‘\[a-z-\]’ is better style; and although ‘\[\*--\]’ is valid, ‘\[\*+,-\]’ is clearer.  
    
    虽然" \- 虽然" \- "可以出现在一个备选字符的开头或作为一个范围的上限，但" \- "本身最好放在备选字符的末尾。'本身出现在一个备选字符的末尾，是一种较好的样式。例如，尽管" \[-a-z\] 虽然" \[-a-z\] "有效，但" \[a-z-\] "的风格更好。'是更好的样式；虽然' \[\*--\] ' 有效，但' \[\*+,-\] '的样式更好。虽然" \[\*--\] "有效，但" \[\*+,-\] "更清晰。更清晰。

‘\[^ … \]’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_005e-in-regexp)  

' \[^ … \] ' ¶

‘\[^’ begins a _complemented character alternative_. This matches any character except the ones specified. Thus, ‘\[^a-z0-9A-Z\]’ matches all characters _except_ ASCII letters and digits.  

' \[^ 开始一个补码字符替代。除指定的字符外，该字符可匹配任何其他字符。因此，" \[^a-z0-9A-Z\] 匹配除 ASCII 字母和数字以外的所有字符。

‘^’ is not special in a character alternative unless it is the first character. The character following the ‘^’ is treated as if it were first (in other words, ‘\-’ and ‘\]’ are not special there).  

' ^ 除非是第一个字符，否则在字符备选方案中并不特殊。在" ^ "之后的字符被视为第一个字符（换句话说，" \- "和" \] "都是特殊字符。后的字符被视为第一个字符（换句话说，" \- "和" \] "在这里并不特殊）。

A complemented character alternative can match a newline, unless newline is mentioned as one of the characters not to match. This is in contrast to the handling of regexps in programs such as `grep`.  

除非换行符被指定为不匹配的字符之一，否则补码字符可以匹配换行符。这与 `grep` 等程序中对 regexps 的处理不同。.

You can specify named character classes, just like in character alternatives. For instance, ‘\[^\[:ascii:\]\]’ matches any non-ASCII character. See [Character Classes](https://www.gnu.org/software/emacs/manual/html_node/elisp/Char-Classes.html).  

您可以指定已命名的字符类别，就像在字符备选方案中一样。例如，" \[^\[:ascii:\]\] 匹配任何非 ASCII 字符。请参阅字符类别。

‘^’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-beginning-of-line-in-regexp)  

' ^ ' ¶

When matching a buffer, ‘^’ matches the empty string, but only at the beginning of a line in the text being matched (or the beginning of the accessible portion of the buffer). Otherwise it fails to match anything. Thus, ‘^foo’ matches a ‘foo’ that occurs at the beginning of a line.  

匹配缓冲区时，" ^ '会匹配空字符串，但仅限于被匹配文本的行首（或缓冲区可访问部分的开头）。否则，将无法匹配任何内容。因此，" ^foo 匹配" foo "。"会匹配出现在一行开头的" foo "。

When matching a string instead of a buffer, ‘^’ matches at the beginning of the string or after a newline character.  

匹配字符串而非缓冲区时，" ^ 匹配字符串的开头或换行符之后。

For historical compatibility reasons, ‘^’ can be used only at the beginning of the regular expression, or after ‘\\(’, ‘\\(?:’ or ‘\\|’.  

出于历史兼容性原因，" ^ 只能在正则表达式的开头或' \\( '、' \\(?: '之后使用。', ' \\(?: '或 ' \\| ' 之后。'.

‘$’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_0024-in-regexp)  

' $ ' ¶

is similar to ‘^’ but matches only at the end of a line (or the end of the accessible portion of the buffer). Thus, ‘x+$’ matches a string of one ‘x’ or more at the end of a line.  

类似于 ' ^ '类似，但仅匹配行尾（或缓冲区可访问部分的末尾）。因此，" x+$ '匹配一行末尾一个或多个 ' x ' 的字符串。的字符串。

When matching a string instead of a buffer, ‘$’ matches at the end of the string or before a newline character.  

匹配字符串而不是缓冲区时，" $ 匹配字符串的末尾或换行符之前。

For historical compatibility reasons, ‘$’ can be used only at the end of the regular expression, or before ‘\\)’ or ‘\\|’.  

出于历史兼容性原因，" $ 只能在正则表达式的末尾或 ' \\) ' 或 ' \\| ' 之前使用。'或'\\| '之前使用。'.

‘\\’ [¶](https://www.gnu.org/software/emacs/manual/html_node/elisp/Regexp-Special.html#index-_005c-in-regexp)  

' \\ ' ¶

has two functions: it quotes the special characters (including ‘\\’), and it introduces additional special constructs.  

有两个功能：引用特殊字符（包括 ' \\ '），并引入额外的特殊结构。

Because ‘\\’ quotes special characters, ‘\\$’ is a regular expression that matches only ‘$’, and ‘\\\[’ is a regular expression that matches only ‘\[’, and so on.  

因为 ' \\ 引用了特殊字符，因此 ' \\$ 是一个正则表达式，只匹配 ' $ 和 ' \\\[ 是只匹配 ' \[ ' 的正则表达式，以此类推。以此类推。

Note that ‘\\’ also has special meaning in the read syntax of Lisp strings (see [String Type](https://www.gnu.org/software/emacs/manual/html_node/elisp/String-Type.html)), and must be quoted with ‘\\’. For example, the regular expression that matches the ‘\\’ character is ‘\\\\’. To write a Lisp string that contains the characters ‘\\\\’, Lisp syntax requires you to quote each ‘\\’ with another ‘\\’. Therefore, the read syntax for a regular expression matching ‘\\’ is `"\\\\"`.  

请注意，" \\ '在 Lisp 字符串的读取语法中也有特殊含义（参见字符串类型），必须用' \\ '加引号。'.例如，匹配 ' \\ ' 字符的正则表达式是 ' \\\\ ' 。字符的正则表达式是 ' \\\\ '.要编写一个包含" \\\\ "字符的 Lisp 字符串，Lisp 语法要求您使用" \\ "引号。要写出一个包含 ' \\\\ ' 字符的 Lisp 字符串，Lisp 语法要求在每个 ' \\ ' 字符后面加上引号。和另一个 ' \\ ' 引号。'.因此，匹配" \\ "的正则表达式的读取语法是 `"\\\\"` 。的读取语法是 `"\\\\"` .

**Please note:** For historical compatibility, special characters are treated as ordinary ones if they are in contexts where their special meanings make no sense. For example, ‘\*foo’ treats ‘\*’ as ordinary since there is no preceding expression on which the ‘\*’ can act. It is poor practice to depend on this behavior; quote the special character anyway, regardless of where it appears.  

请注意：出于历史兼容性考虑，如果特殊字符在上下文中没有特殊含义，则将其视为普通字符。例如，" \*foo "将" \* '视为普通字符，因为前面没有" \* "可以作用的表达式。可以起作用。依赖这种行为的做法并不可取；无论特殊字符出现在何处，都应引用它。

As a ‘\\’ is not special inside a character alternative, it can never remove the special meaning of ‘\-’, ‘^’ or ‘\]’. You should not quote these characters when they have no special meaning. This would not clarify anything, since backslashes can legitimately precede these characters where they _have_ special meaning, as in ‘\[^\\\]’ (`"[^\\]"` for Lisp string syntax), which matches any single character except a backslash.  

由于" \\ 由于" \\ "在替代字符中并不特殊，因此它永远无法消除" \- "、" ^ "和" \] "的特殊含义。', ' ^ '或' \] '.如果这些字符没有特殊含义，则不应引用。这样做并不能说明任何问题，因为反斜线可以合法地出现在这些具有特殊含义的字符之前，如' \[^\\\] '（Lisp 字符串语法中为 `"[^\\]"` ），它匹配反斜线以外的任何单字符。

In practice, most ‘\]’ that occur in regular expressions close a character alternative and hence are special. However, occasionally a regular expression may try to match a complex pattern of literal ‘\[’ and ‘\]’. In such situations, it sometimes may be necessary to carefully parse the regexp from the start to determine which square brackets enclose a character alternative. For example, ‘\[^\]\[\]\]’ consists of the complemented character alternative ‘\[^\]\[\]’ (which matches any single character that is not a square bracket), followed by a literal ‘\]’.  

实际上，正则表达式中出现的大多数" \] 正则表达式中出现的大多数" \] "都关闭了一个字符选项，因此是特殊的。但是，正则表达式偶尔也会尝试匹配由" \[ "和" \] "组成的复杂模式。和 ' \] 的复杂模式。'.在这种情况下，有时可能需要从头开始仔细分析 regexp，以确定哪些方括号包含了字符选项。例如，" \[^\]\[\]\] '由补充字符' \[^\]\[\] '组成。匹配任何不是方括号的单字符），然后是字面意义上的" \] "。'.

The exact rules are that at the beginning of a regexp, ‘\[’ is special and ‘\]’ not. This lasts until the first unquoted ‘\[’, after which we are in a character alternative; ‘\[’ is no longer special (except when it starts a character class) but ‘\]’ is special, unless it immediately follows the special ‘\[’ or that ‘\[’ followed by a ‘^’. This lasts until the next special ‘\]’ that does not end a character class. This ends the character alternative and restores the ordinary syntax of regular expressions; an unquoted ‘\[’ is special again and a ‘\]’ not.  

确切的规则是，在 regexp 的开头，" \[ " 是特殊的，而" \] " 则是特殊的。'是特殊的，而' \] 则不特殊。这种情况一直持续到第一个无引号的" \[ 之后，我们就可以使用另一种字符；" \[ '不再是特殊符号（除非它是字符类的开头），但' \] 是特殊的，除非它紧跟在特殊的" \[ "之后。或 ' \[ '后接' ^ '。'.这种情况一直持续到下一个特殊 ' \] 不结束字符类。这样就结束了字符类，恢复了正则表达式的普通语法；未加引号的 ' \[ 再次成为特殊符号。再次成为特殊符号，而 ' \] 则不特殊。
