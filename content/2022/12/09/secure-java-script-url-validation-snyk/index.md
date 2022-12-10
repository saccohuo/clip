---
title: "安全的 JavaScript URL 验证"
date: 2022-12-09T13:11:05+08:00
updated: 2022-12-09T13:11:05+08:00
taxonomies:
  tags: []
extra:
  source: https://snyk.io/blog/secure-javascript-url-validation/
  hostname: snyk.io
  author: Mannan TirmiziOctober 17, 2022
  original_title: "Secure JavaScript URL validation | Snyk"
  original_lang: en
---

When developers need to handle URLs in different forms for different purposes — such as browser history navigation, anchored targets, query parameters, and so on — we often turn to JavaScript. However, its frequent use motivates attackers to exploit its vulnerabilities. This risk of exploitation is why we must implement URL validation in our JavaScript applications.

当开发人员需要出于不同目的处理不同形式的 URL 时——例如浏览器历史导航、锚定目标、查询参数等——我们通常会求助于 JavaScript。 但是，它的频繁使用会促使攻击者利用其漏洞。 这种利用风险是我们必须在我们的 JavaScript 应用程序中实现 URL 验证的原因。

URL validation checks whether URLs follow proper URL syntax — the structure every URL must have. URL validation can save our applications from URL-based vulnerabilities like malicious script injection and server-side request forgery (SSRF). Malicious actors can employ SSRF attacks when we don’t apply secure coding conventions to validate user-supplied URLs when fetching a remote resource. SSRF [remains a critical threat](https://www.acunetix.com/blog/articles/server-side-request-forgery-vulnerability/) to JavaScript-based applications, both for the frontend and Node.js server-side applications, and was a featured category in the [OWASP Top 10](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/) list in 2021.

URL validation checks whether URLs follow proper URL syntax — the structure every URL must have. URL validation can save our applications from URL-based vulnerabilities like malicious script injection and server-side request forgery (SSRF). Malicious actors can employ SSRF attacks when we don’t apply secure coding conventions to validate user-supplied URLs when fetching a remote resource. SSRF [remains a critical threat](https://www.acunetix.com/blog/articles/server-side-request-forgery-vulnerability/) to JavaScript-based applications, both for the frontend and Node.js server-side applications, and was a featured category in the [OWASP Top 10](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/) list in 2021.

## URL validation

## URL 验证

URL validation exists to strengthen security against possible exploits and eliminate the chance of any bugs arising while running code. But when should we use URL validation, and what do we validate during the process? We should implement URL validation in all software that must identify and verify resources like pages, images, gifs, and videos. 

URL 验证的存在是为了加强安全性以防止可能的漏洞利用并消除运行代码时出现任何错误的可能性。 但是我们什么时候应该使用 URL 验证，我们在这个过程中验证什么？ 我们应该在所有必须识别和验证页面、图像、gif 和视频等资源的软件中实施 URL 验证。

A typical URL comprises multiple fragments, such as a protocol, domain name, hostname, resource name, origin, port, and so on. These tell the browser how to retrieve the particular resource. We can use these to validate URLs in several ways:

一个典型的 URL 包含多个片段，例如协议、域名、主机名、资源名称、来源、端口等。 这些告诉浏览器如何检索特定资源。 我们可以使用这些以多种方式验证 URL：

-   Using Regex literals and constructors
-   使用 Regex 文字和构造函数
-   URL constructors
-   网址构造器
-   `isValidURL` method
-   `isValidURL`方法
-   Input elements
-   输入元素
-   Anchor tag method
-   锚标签法

A typical URL validation scheme receives input from a user and then parses it to identify its various components. The validation scheme can ensure that all URL components comply with internet standards. For example, if required, it can check whether the URL uses a secure protocol. 

典型的 URL 验证方案接收来自用户的输入，然后对其进行解析以识别其各种组件。 验证方案可以确保所有 URL 组件都符合 Internet 标准。 例如，如果需要，它可以检查 URL 是否使用安全协议。

Hostname validation begins by breaking hostnames into separate labels to ensure they comply with the [Top Level Domain Name Specification](https://www.rfc-editor.org/rfc/rfc1591.txt#:~:text=There%20are%20a%20set%20of,created%20a%20hierarchy%20of%20names.). A typical hostname consists of a minimum of two labels segregated by dots. For example, [www.snyk.com](http://www.snyk.com/) has the labels “www,” “snyk,” and “com”. Each label can only consist of an alphanumeric character or a hyphen, regardless of their case. Then, the validation scheme can ensure the hostname matches an allowlist of allowable URLs to ensure only designated URLs are allowed and allowed URLs are not wrongfully disqualified.

主机名验证首先将主机名分成单独的标签，以确保它们符合 [顶级域名规范](https://www.rfc-editor.org/rfc/rfc1591.txt#:~:text=There%20are%20a%20set%20of,created%20a%20hierarchy%20of%20names.) 。 典型的主机名至少包含两个由点分隔的标签。 例如， [www.snyk.com](http://www.snyk.com/) 具有标签“www”、“snyk”和“com”。 每个标签只能包含一个字母数字字符或一个连字符，无论大小写如何。 然后，验证方案可以确保主机名与允许的 URL 白名单相匹配，以确保只允许指定的 URL，并且允许的 URL 不会被错误地取消资格。

Most paths to a resource used in URLs are allowed by default. However, ports can only be in the range of 1 to 65536. Anything outside that range should throw an error. We can also check numerical IP addresses to gauge if it’s an IPV4 address or an IPV6 address.

默认情况下允许 URL 中使用的大多数资源路径。 但是，端口只能在 1 到 65536 的范围内。超出该范围的任何内容都会引发错误。 我们还可以检查数字 IP 地址以判断它是 IPV4 地址还是 IPV6 地址。

Finally, although not obvious initially, we can also check URLs for usernames and passwords. This feature helps with compliance with company policies and credential protection. 

最后，虽然最初并不明显，但我们还可以检查 URL 中的用户名和密码。 此功能有助于遵守公司政策和凭证保护。

Now that you have the basics, let’s walk through URL validation using javascript!

现在您已经掌握了基础知识，让我们来看看使用 JavaScript 进行 URL 验证吧！

## How to perform URL validation in JavaScript

## 如何在 JavaScript 中执行 URL 验证

The easiest way to perform URL validation in JavaScript is by using the `new URL` constructor function. In addition to its simplicity, it’s supported by the Node.js runtime and [most browsers](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL#browser_compatibility).

在 JavaScript 中执行 URL 验证的最简单方法是使用 `new URL`构造函数。 除了简单之外，它还受到 Node.js 运行时和 [大多数浏览器](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL#browser_compatibility) 的支持。

The basic syntax is as follows:

基本语法如下：

```
  new URL (url)
    new URL (url , base)
```

JavaScript only requires the `base` element if we provide a relative URL. If we don’t provide one, it defaults to `undefined`. Alternatively, if we provide a `base` element with an absolute URL, JavaScript ignores the `base` element.

JavaScript 只需要 `base`元素，如果我们提供一个相对 URL。 如果我们不提供，则默认为 `undefined`. 或者，如果我们提供 `base`带有绝对 URL 的元素，JavaScript 会忽略 `base`元素。

To validate the URL, the following function can be used:

要验证 URL，可以使用以下函数：

```
function checkUrl (string) {
    let givenURL ;
    try {
        givenURL = new URL (string);
    } catch (error) {
        console.log ("error is", error);
       return false; 
    }
    return true;
  }
```

This function checks the validity of a URL — it returns true when the URL is valid and false when it’s not. If you pass `www.urlcheck.com` to this function, it will return false because it does not contain a valid URL scheme. The correct version of this URL is `https://urlcheck.com`. Another example is `mailto:John.Doe@example.com`. This is a valid URL, but if you remove the colon, JavaScript will no longer recognize it as a URL. A third example is `ftp://`. This is not valid because it doesn’t contain a hostname. If you add two dots (`..`), it will become valid because the dots will be considered a hostname, in this way `ftp://..` becomes a valid URL. 

此函数检查 URL 的有效性——当 URL 有效时返回 true，否则返回 false。 如果你通过 `www.urlcheck.com`对于此函数，它将返回 false，因为它不包含有效的 URL 方案。 此 URL 的正确版本是 `https://urlcheck.com`. 另一个例子是 `mailto:John.Doe@example.com`. 这是一个有效的 URL，但如果您删除冒号，JavaScript 将不再将其识别为 URL。 第三个例子是 `ftp://`. 这是无效的，因为它不包含主机名。 如果你加两个点（ `..`), 它将变得有效，因为点将被视为主机名，以这种方式 `ftp://..`成为一个有效的 URL。

It’s important to to bear in mind that unconventional, but perfectly valid, URLs exist! They might be unexpected for the developers working on them, but are otherwise perfectly appropriate. For example, both of the following URLs will return TRUE:

请务必牢记非常规但完全有效的 URL 的存在！ 对于处理它们的开发人员来说，它们可能出乎意料，但在其他方面却非常合适。 例如，以下两个 URL 都将返回 TRUE：

-   new URL(“youtube://a.b.c.d”);
-   新网址（“youtube://abcd”）；
-   new URL (“a://1.2.3.4@1.2.3.4”);
-   新网址（“a://1.2.3.4@1.2.3.4”）；

These examples are a reminder that developers should rely on the principles of URL validation, instead of focusing on the conventions.

这些示例提醒开发人员应该依赖 URL 验证的原则，而不是专注于约定。

If you want to make sure that the valid URL contains some specific URL scheme, you can use the following function:

如果你想确保有效的 URL 包含一些特定的 URL scheme，你可以使用下面的函数：

```
  function checkHttpUrl(string) {
    let givenURL;
    try {
        givenURL = new URL(string);
    } catch (error) {
        console.log("error is",error)
      return false;  
    }
    return givenURL.protocol === "http:" || givenURL.protocol === "https:";
  }
```

This function validates the URL, and then checks whether or not it’s using the HTTP or HTTPS schemes. Here, `ftp://..` will be invalid because it does not contain HTTP or HTTPS, while `http://..` remains valid.  
Some other ways to use the `URL` constructor function include:

此函数验证 URL，然后检查它是否使用 HTTP 或 HTTPS 方案。 这里， `ftp://..`将无效，因为它不包含 HTTP 或 HTTPS，而 `http://..`仍然有效。  
其他一些使用方法 `URL`构造函数包括：

```
  let m = 'https://snyk.io';
  let a = new URL("/", m); 
```

The above example uses the `base` element. Logging the value gives us `https://snyk.io/`.

上面的例子使用了 `base`元素。 记录值给了我们 `https://snyk.io/`.

To return a URL object without specifying the `base` parameter, the syntax is:

返回一个 URL 对象而不指定 `base`参数，语法为：

```
  let b = new URL(m);
```

To add a pathname to the host, we structure it as follows:

要向主机添加路径名，我们将其构造如下：

```
  let d = new URL('/en-US/docs', b);
```

The URL stored in `d` is `https://snyk.io/en-US/docs`.

URL 存储在 `d`是 `https://snyk.io/en-US/docs`.

Another functionality of the URL module is that it implements the [WHATWG URL API](https://www.ibm.com/docs/en/datapower-gateway/10.5?topic=module-whatwg-url-api), which adheres to the WHATWG URL standard browsers use:

URL 模块的另一个功能是它实现了 [WHATWG URL API](https://www.ibm.com/docs/en/datapower-gateway/10.5?topic=module-whatwg-url-api) ，它遵循浏览器使用的 WHATWG URL 标准：

```
  let adr = new URL("https://snyk.io/en-US/docs");
  let host = adr.host;
  let path = adr.pathname;
```

In the above example, we created a URL object called `adr`. Then, the code fetched the host and the pathname of the URL — which are `snyk.io` and `/en-US/docs`, respectively. Finally, we can compare the URL to an allowlist or blocklist to ensure only designated URLs are allowed and allowed URLs are not wrongfully disqualified.

在上面的示例中，我们创建了一个名为 `adr`. 然后，代码获取主机和 URL 的路径名——它们是 `snyk.io`和 `/en-US/docs`， 分别。 最后，我们可以将 URL 与允许列表或阻止列表进行比较，以确保只允许指定的 URL，并且允许的 URL 不会被错误地取消资格。

### How to validate a URL using regex — although you shouldn’t

### 如何使用正则表达式验证 URL——尽管你不应该这样做

Another way to validate a URL is by using a regular expression (regex) — or a string that forms a search pattern. We can use Regex to check whether the URL is valid.

验证 URL 的另一种方法是使用正则表达式 (regex) — 或构成搜索模式的字符串。 我们可以使用 Regex 来检查 URL 是否有效。

The JavaScript syntax for URL validation using regex is:

使用正则表达式进行 URL 验证的 JavaScript 语法是：

```
  function isValidURL(string) 
        {
            var res = 
            string.match(/(https?:\/\/(?:www\.|(?!www))[a-zA-Z0-9][a-zA-Z0-9-
            ]+[a-zA-Z0-9]\.[^\s]{2,}|www\.[a-zA-Z0-9][a-zA-Z0-9-]+[a-zA-Z0-9]
            \.[^\s]{2,}|https?:\/\/(?:www\.|(?!www))[a-zA-Z0-9]+\.[^\s]{2,}|w
            ww\.[a-zA-Z0-9]+\.[^\s]{2,})/gi);
        return (res !== null);
        };
```

To test some URLs:

测试一些 URL：

```
  var tc1 = "http://helloworld.com"
  console.log(isValidURL(tc1));
```

The regex-defined URL syntax checks whether the URL starts with the `http://` or `https://` schemes or a subdomain, and whether it contains a domain name. The statement on the console is `true` because it follows the URL syntax defined by the regex. In contrast, the following statement will return a `false` value because it doesn’t start with any of the allowed schemes or a subdomain, nor does it contain a domain name: 

正则表达式定义的 URL 语法检查 URL 是否以 `http://`或者 `https://`方案或子域，以及它是否包含域名。 控制台上的语句是 `true`因为它遵循正则表达式定义的 URL 语法。 相反，下面的语句将返回一个 `false`值，因为它不以任何允许的方案或子域开头，也不包含域名：

```
  var tc4 = "helloWorld";
  console.log (isValidURL(tc4));
```

The regex above is relatively simple but still difficult to navigate. It’s also an error-prone approach because a regex cannot adequately handle the rules for validating a URL. The most it can do is match valid URLs. Furthermore, executing the validation check becomes time-consuming when a regular expression either contains a complex validation logic or receives a lengthy input string. 

上面的正则表达式相对简单，但仍然难以导航。 这也是一种容易出错的方法，因为正则表达式无法充分处理验证 URL 的规则。 它最多能做的就是匹配有效的 URL。 此外，当正则表达式包含复杂的验证逻辑或接收到冗长的输入字符串时，执行验证检查变得非常耗时。

To meet the defined regex validation checks, the browser must backtrack on the order of millions through the input string. This much backchecking could result in “catastrophic backtracking”, a phenomenon in which complex regular expressions can freeze the browser or max out the CPU core processes.

为了满足定义的正则表达式验证检查，浏览器必须通过输入字符串回溯数百万次。 如此多的回溯可能会导致“灾难性回溯”，在这种现象中，复杂的正则表达式会冻结浏览器或最大化 CPU 核心进程。

### Real-world vulnerabilities and resolutions

### 现实世界的漏洞和解决方案

[Node.js](https://nodejs.dev/en/) is a free, open source, cross-platform JavaScript runtime environment that uses a package manager called Node Package Manager (npm). 

[Node.js](https://nodejs.dev/en/) 是一个免费、开源、跨平台的 JavaScript 运行时环境，它使用一个名为 Node Package Manager (npm) 的包管理器。

A similar event occurred in 2019 when an attacker single-handedly obtained unauthorized access to data from Capital One, one of the biggest banks in the United States. That data breach remains one of the most significant of the century. According to [_The New York Times_](https://www.nytimes.com/2019/07/29/business/capital-one-data-breach-hacked.html), the attacker gained access to 100 million customer records, 140,000 Social Security numbers, and 80,000 linked bank details of Capital One customers. 

类似的事件发生在 2019 年，当时一名攻击者单枪匹马地未经授权访问了美国最大银行之一 Capital One 的数据。 该数据泄露事件仍然是本世纪最重大的事件之一。 据 [_《纽约时报》报道_](https://www.nytimes.com/2019/07/29/business/capital-one-data-breach-hacked.html) ，攻击者获得了第一资本客户的 1 亿条客户记录、14 万个社会安全号码和 8 万个相关银行详细信息。

The attacker accessed the Capital One server hosted by Amazon Web Services (AWS). The delay in detection indicates that the attacker had a deep knowledge of the AWS infrastructure and saw an exploitable vulnerability in the Managed Security Service Provider’s (MODSEC) Web Application Firewall (WAF). Armed with this knowledge, the perpetrator carried out the SSRF attack, and made new HTTP requests by manipulating the vulnerable web server — thereby successfully gaining access to the AWS metadata service. 

攻击者访问了由 Amazon Web Services (AWS) 托管的 Capital One 服务器。 检测延迟表明攻击者对 AWS 基础设施有深入的了解，并在托管安全服务提供商 (MODSEC) 的 Web 应用程序防火墙 (WAF) 中发现了一个可利用的漏洞。 有了这些知识，犯罪者进行了 SSRF 攻击，并通过操纵易受攻击的 Web 服务器发出新的 HTTP 请求——从而成功获得对 AWS 元数据服务的访问权限。

Depending on company requirements, we can avoid SSRF attacks by restricting the system to only a few protocols, such as HTTP or HTTPS. To add more security, we must set up the application so it doesn’t pass the URL parameter without oversight. Allow and deny lists are typically used to filter and control the mechanism, reducing the probability of SSRF significantly. Allow lists enable the application to use a predefined assortment of objects and servers. Meanwhile, deny lists restrict the application from retrieving commonly available hostnames.

根据公司要求，我们可以通过将系统限制为仅使用几种协议（例如 HTTP 或 HTTPS）来避免 SSRF 攻击。 为了增加安全性，我们必须设置应用程序，使其不会在没有监督的情况下传递 URL 参数。 允许和拒绝列表通常用于过滤和控制机制，显着降低 SSRF 的可能性。 允许列表使应用程序能够使用预定义的对象和服务器分类。 同时，拒绝列表限制应用程序检索常用的主机名。

## Using JavaScript safely

## 安全地使用 JavaScript

As evidenced by the addition of SSRF to the new OWASP Top 10, URL validation has become increasingly crucial for JavaScript application security. Fortunately, we can help mitigate such attacks by validating URLs on the server side. Additionally, using the new `URL` function according to the preferred ways to validate and work with URLs can be highly beneficial. 

正如将 SSRF 添加到新的 OWASP Top 10 中所证明的那样，URL 验证对于 JavaScript 应用程序安全性变得越来越重要。 幸运的是，我们可以通过在服务器端验证 URL 来帮助减轻此类攻击。 此外，使用新的 `URL`根据首选方式验证和使用 URL 的功能可能非常有益。

After seeing a few use cases of the new `URL` function’s capability, we learned how to validate a URL with regex — and saw why this approach is cumbersome and error-prone. We then concluded with a case study of the SSRF JavaScript vulnerability. 

在看到新的几个用例之后 `URL`函数的功能，我们学习了如何使用正则表达式验证 URL——并了解了为什么这种方法很麻烦且容易出错。 然后，我们以 SSRF JavaScript 漏洞的案例研究作为结尾。

The security risks with URLs are less about their validity and more about dangerous URL schemes. As such, we need to ensure that the server-side application carries out the validation. An attacker can bypass the client-side validation mechanism, so relying solely on that isn’t the way to go.

URL 的安全风险不在于它们的有效性，而在于危险的 URL 方案。 因此，我们需要确保服务器端应用程序执行验证。 攻击者可以绕过客户端验证机制，因此完全依赖它是行不通的。

To learn more about managing your application security, visit [Snyk](https://snyk.io/) today. 

要了解有关管理应用程序安全性的更多信息，请立即访问 [Snyk](https://snyk.io/) 。

## Find and fix JavaScript vulnerabilities for free

## 免费查找和修复 JavaScript 漏洞

Create a Snyk account today for safe and secure JavaScript applications.

立即为安全可靠的 JavaScript 应用程序创建一个 Snyk 帐户。
