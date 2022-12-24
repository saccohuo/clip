---
title: "WWW 是否仍然属于 URL？"
date: 2022-12-24T18:24:30+08:00
updated: 2022-12-24T18:24:30+08:00
taxonomies:
  tags: []
extra:
  source: https://css-tricks.com/does-www-still-belong-in-urls/
  hostname: css-tricks.com
  author: 
  original_title: "Does WWW still belong in URLs? | CSS-Tricks"
  original_lang: en
---

For years, a small pedantry war has been raging in our address bars. In one corner are brands like [Google](http://www.google.com/), [Instagram](http://www.instagram.com/), and [Facebook](http://www.facebook.com/). This group has chosen to redirect `example.com` to `www.example.com`. In the opposite corner: [GitHub](http://github.com/), [DuckDuckGo](http://duckduckgo.com/), and [Discord](http://discord.com/). This group has chosen to do the reverse and redirect `www.example.com` to `example.com`.

多年来，一场小型的迂腐之战一直在我们的地址栏中肆虐。 在一个角落里有 [谷歌](http://www.google.com/) 、 [Instagram](http://www.instagram.com/) 和 [Facebook](http://www.facebook.com/) 等品牌。 该组已选择重定向 `example.com`到 `www.example.com`. 在对角： [GitHub](http://github.com/) 、 [DuckDuckGo](http://duckduckgo.com/) 和 [Discord](http://discord.com/) 。 该组已选择进行反向和重定向 `www.example.com`到 `example.com`.

Does “WWW” belong in a URL? Some developers hold strong opinions on the subject. We’ll explore arguments for and against it after a bit of history.

“WWW”是否属于 URL？ 一些开发人员对这个问题持有强烈的意见。 在了解了一些历史之后，我们将探讨支持和反对它的论点。

### What’s with the Ws?

### Ws怎么了？

The three Ws stand for [“World Wide Web”](https://en.wikipedia.org/wiki/World_Wide_Web), a late-1980s invention that introduced the world to browsers and websites. The practice of using “WWW” stems from a tradition of naming subdomains after the type of service they provide:

三个 W 代表 [“万维网”](https://en.wikipedia.org/wiki/World_Wide_Web) ，这是 20 世纪 80 年代后期的一项发明，将世界引入浏览器和网站。 使用“WWW”的做法源于在子域提供的服务类型之后命名子域的传统：

-   a web server at _www.example.com_
-   的 Web 服务器 _位于www.example.com_
-   an FTP server at _ftp.example.com_
-   上的 FTP 服务器 _ftp.example.com_
-   an IRC server at _irc.example.com_
-   上的 IRC 服务器 _irc.example.com_

### WWW-less domain concern 1: Leaking cookies to subdomains

### 无 WWW 域问题 1：将 cookie 泄漏到子域

Critics of “WWW-less” domains have pointed out that in certain situations, _subdomain.example.com_ would be able to read cookies set by _example.com_. This may be undesirable if, for example, you are a web hosting provider that lets clients operate subdomains on your domain. While the concern is valid, the behavior was specific to Internet Explorer.

“无 WWW”域的批评者指出，在某些情况下， _subdomain.example.com_ 将能够读取由 _example.com_ 设置的 cookie 。 这可能是不受欢迎的，例如，如果您是允许客户在您的域上操作子域的 Web 托管提供商。 虽然这种担忧是有道理的，但该行为是特定于 Internet Explorer 的。

[RFC 6265](https://www.rfc-editor.org/rfc/rfc6265#section-4.1.2.3) standardizes how browsers treat cookies and explicitly calls out this behavior as incorrect.

[RFC 6265](https://www.rfc-editor.org/rfc/rfc6265#section-4.1.2.3) 标准化了浏览器如何处理 cookie 并明确指出此行为是不正确的。

Another potential source of leaks is the [`Domain` value](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie) of any cookies set by _example.com_. If the `Domain` value is explicitly set to _example.com_, the cookies will also be exposed to its subdomains.

另一个潜在的泄漏源是 [`Domain`值](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie) 设置的任何 cookie 的 _example.com_ 。 如果 `Domain`值明确设置为 _example.com_ ，cookie 也将暴露给它的子域。

| Cookie value | Exposed to _example.com_ | Exposed to _subdomain.example.com_ |
| --- | --- | --- |
| `secret=data` | ✅ | ❌ |
| `secret=data; Domain=example.com` | ✅ | ✅ |

| 饼干价值 | 暴露于 _example.com_ | 暴露给 _subdomain.example.com_ |
| --- | --- | --- |
| `secret=data` | ✅ | ❌ |
| `secret=data; Domain=example.com` | ✅ | ✅ |

In conclusion, as long as you don’t explicitly set a `Domain` value and your users don’t use Internet Explorer, no cookie leaks should occur.

总之，只要您不明确设置 `Domain`值并且您的用户不使用 Internet Explorer，则不会发生 cookie 泄漏。

### WWW-less domain concern 2: DNS headaches

### 无 WWW 域问题 2：DNS 问题

Sometimes, a “WWW-less” domain may complicate your Domain Name System (DNS) setup.

有时，“无 WWW”域可能会使您的域名系统 (DNS) 设置复杂化。

When a user types _example.com_ into their browser’s address bar, the browser needs to know the Internet Protocol (IP) address of the web server they’re trying to visit. The browser requests this IP address from your domain’s nameservers – usually indirectly through the DNS servers of the user’s Internet Service Provider (ISP). If your nameservers are configured to respond with an [A record](https://wizardzines.com/comics/dns-record-types/) containing the IP address, a “WWW-less” domain will work fine.

当用户在浏览器的地址栏中键入 _example.com_ 时，浏览器需要知道他们试图访问的 Web 服务器的 Internet 协议 (IP) 地址。 浏览器从您域的名称服务器请求此 IP 地址——通常是间接通过用户的互联网服务提供商 (ISP) 的 DNS 服务器。 如果您的名称服务器配置为使用包含 IP 地址的 [A 记录](https://wizardzines.com/comics/dns-record-types/) 进行响应，则“无 WWW”域可以正常工作。

In some cases, you may want to instead use a [Canonical Name (CNAME)](https://wizardzines.com/comics/cname/) record for your website. Such a record can declare that _www.example.com_ is an alias of _example123.somecdnprovider.com_, which tells the user’s browser to instead look up the IP address of _example123.somecdnprovider.com_ and send the HTTP request there.

在某些情况下，您可能希望为您的网站使用 [规范名称 (CNAME)](https://wizardzines.com/comics/cname/) 记录。 这样的记录可以声明 _www.example.com_ 是 _example123.somecdnprovider.com_ 的别名，它告诉用户的浏览器改为查找 _example123.somecdnprovider.com_ 的 IP 地址并向那里发送 HTTP 请求。

Notice that the example above used a WWW subdomain. It’s not possible to define a CNAME record for _example.com_. As per [RFC 1912](https://www.ietf.org/rfc/rfc1912.html#section-2.4), CNAME records cannot coexist with other records. If you tried to define a CNAME record for _example.com_, a MX (Mail Exchanger) record for _example.com_ would not be allowed to exist. As a result, it would not be possible to accept mail on _@example.com_.

请注意，上面的示例使用了 WWW 子域。 无法为 _example.com_ 定义 CNAME 记录。 根据 [RFC 1912](https://www.ietf.org/rfc/rfc1912.html#section-2.4) ，CNAME 记录不能与其他记录共存。 如果您尝试为 example.com 定义 CNAME 记录， _则_ 的 MX（邮件交换器）记录 _example.com_ 不允许存在 。 因此，将无法接受 _@example.com_ 上的邮件。

Some DNS providers will allow you to work around this limitation. Cloudflare calls their solution [CNAME flattening](https://blog.cloudflare.com/introducing-cname-flattening-rfc-compliant-cnames-at-a-domains-root/). With this technique, domain administrators configure a CNAME record, but their nameservers will expose an A record.

一些 DNS 提供商将允许您解决此限制。 Cloudflare 将他们的解决方案称为 [CNAME 扁平化](https://blog.cloudflare.com/introducing-cname-flattening-rfc-compliant-cnames-at-a-domains-root/) 。 使用这种技术，域管理员配置 CNAME 记录，但他们的名称服务器将公开 A 记录。

For instance, if the administrator configures a CNAME record for _example.com_ pointing to _example123.somecdnprovider.com_, and an A record for _example123.somecdnprovider.com_ exists pointing to _1.2.3.4_, then Cloudflare would expose an A record for _example.com_ pointing to _1.2.3.4_.

例如，如果管理员配置 _example.com_ 的 CNAME 记录指向 _example123.somecdnprovider.com_ ，并且 example123.somecdnprovider.com 的 A 记录 _指向_ 1.2.3.4 _，_ 那么 Cloudflare 将公开 _example.com_ 的 A 记录指向 _1.2.3.4_ 。

In conclusion, while the concern is valid for domain owners who wish to use CNAME records, certain DNS providers now offer a suitable workaround.

总之，虽然对于希望使用 CNAME 记录的域所有者来说，这种担忧是有效的，但某些 DNS 提供商现在提供了合适的解决方法。

### WWW-less benefits

### 无 WWW 的好处

Most of the [arguments against](https://dropwww.com/why) WWW are practical or cosmetic. “No-WWW” advocates have argued that it’s easier to say and type _example.com_ than _www.example.com_ (which may be less confusing for less tech-savvy users).

大多数 [反对](https://dropwww.com/why) WWW 的论点都是实用的或表面的。 “No-WWW”的拥护者争辩说，说出和输入 _example.com_ 比 _www.example.com_ 更容易（对于不太精通技术的用户来说，这可能不会造成混淆）。

Opponents of the WWW subdomain have also pointed out that dropping it comes with a humble performance advantage. Website owners could shave 4 bytes off each HTTP request by doing so. While these savings could add up for high-traffic websites like Facebook, bandwidth generally isn’t a scarce resource.

WWW 子域的反对者还指出，放弃它会带来微不足道的性能优势。 通过这样做，网站所有者可以减少每个 HTTP 请求的 4 个字节。 虽然这些节省对于像 Facebook 这样的高流量网站来说可能会有所增加，但带宽通常并不是稀缺资源。

### WWW benefits

### 万维网的好处

One practical argument in favor of WWW is in situations with newer top-level domains. For example, _www.example.miami_ is immediately recognizable as a web address when _example.miami_ isn’t. This is less of a concern for sites that have recognizable top-level domains like _.com_.

支持 WWW 的一个实际论据是在具有更新的顶级域的情况下。 例如， _时， www.example.miami_ 可以立即识别为网址 _当example.miami_ 不是 。 对于具有可识别的顶级域（如 _.com_ ）的站点，这不是一个问题。

### Impact on your search engine ranking

### 对您的搜索引擎排名的影响

The current consensus is that your choice does not influence your search engine performance. If you wish to migrate from one to the other, you’ll want to configure permanent redirects (HTTP 301) instead of temporary ones (HTTP 302). Permanent redirects ensure that the SEO value of your old URLs transfers to the new ones.

目前的共识是您的选择不会影响您的搜索引擎性能。 如果您希望从一个迁移到另一个，您需要配置永久重定向 (HTTP 301) 而不是临时重定向 (HTTP 302)。 永久重定向确保您的旧 URL 的 SEO 价值转移到新的 URL。

### Tips for supporting both

### 支持两者的技巧

Sites typically pick either _example.com_ or _www.example.com_ as their official website and configure HTTP 301 redirects for the other. In theory, it is possible to support both _www.example.com_ and _example.com_. In practice, the costs may outweigh the benefits.

网站通常选择 _example.com_ 或 _www.example.com_ 作为其官方网站，并为另一个配置 HTTP 301 重定向。 理论上，可以同时支持 _www.example.com_ 和 _example.com_ 。 在实践中，成本可能超过收益。

From a technical perspective, you’ll want to verify that your tech stack can handle it. Your content management system (CMS) or statically generated site would have to output internal links as relative URLs to preserve the visitor’s preferred hostname. Your analytics tools may log traffic to both hostnames separately unless you can configure the hostnames as aliases.

从技术角度来看，您需要验证您的技术堆栈是否可以处理它。 您的内容管理系统 (CMS) 或静态生成的站点必须将内部链接输出为相对 URL，以保留访问者的首选主机名。 您的分析工具可能会分别记录到两个主机名的流量，除非您可以将主机名配置为别名。

Lastly, you’ll need to take an extra step to safeguard your search engine performance. Google will consider the “WWW” and “non-WWW” versions of a URL to be [duplicate content](https://developers.google.com/search/docs/advanced/crawling/consolidate-duplicate-urls). To deduplicate content in its search index, Google will display whichever of the two it thinks the user will prefer – for better or worse.

最后，您需要采取额外的步骤来保护您的搜索引擎性能。 Google 会将 URL 的“WWW”和“非 WWW”版本视为 [重复内容](https://developers.google.com/search/docs/advanced/crawling/consolidate-duplicate-urls) 。 为了删除其搜索索引中的重复内容，谷歌将显示它认为用户更喜欢的两者中的任何一个——无论好坏。

To preserve control over how you appear in Google, it recommends inserting canonical link tags. First, decide which hostname will be the official (canonical) one.

为了保持对您在 Google 中的显示方式的控制，它建议插入规范链接标签。 首先，确定哪个主机名将是官方（规范）主机名。

For example, if you pick _www.example.com_, you will have to insert the following snippet in the `<head>` tag on _https://example.com/my-article_:

例如，如果您选择 _www.example.com_ ，则必须在 `<head>`上的标签 _https://example.com/my-article_ ：

```
<link href="https://www.example.com/my-article" rel="canonical">
```

This snippet indicates to Google that the “WWW-less” variant represents the same content. In general, Google will prefer the version you’ve marked as canonical in search results, which would be the “WWW” variant in this example.

此代码段向 Google 表明“WWW-less”变体表示相同的内容。 一般来说，Google 会更喜欢您在搜索结果中标记为规范的版本，在本例中就是“WWW”变体。

### Conclusion

### 结论

Despite intense campaigning on either side, both approaches remain valid as long as you are aware of the benefits and limitations. To cover all your bases, be sure to set up permanent redirects from one to the other and you’re all set.

尽管双方都进行了激烈的竞选活动，但只要您了解好处和局限性，这两种方法仍然有效。 要覆盖所有基地，请务必设置从一个基地到另一个基地的永久重定向，一切就绪。

_The author selected the [Open Internet/Free Speech Fund](https://www.brightfunds.org/funds/open-internet-free-speech) to receive a donation as part of the [Write for DOnations](https://do.co/w4do-cta) program._

_的一部分，作者选择了 [Open Internet/Free Speech Fund](https://www.brightfunds.org/funds/open-internet-free-speech) 来接收捐款。 [作为Write for DOnations](https://do.co/w4do-cta) 计划_
