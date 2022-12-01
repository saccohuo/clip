---
title: "权威的 NS 记录多样性"
date: 2022-12-01T22:09:17+08:00
updated: 2022-12-01T22:09:17+08:00
taxonomies:
  tags: []
extra:
  source: https://netmeister.org/blog/nsauth-diversity.html
  hostname: netmeister.org
  author: 
  original_title: "Who controls the internet?"
  original_lang: en
---

### A look at diversity of authoritative NS records in gTLDs
### 了解 gTLD 中权威 NS 记录的多样性

November 15th, 2022

2022 年 11 月 15 日

[](https://xkcd.com/2347/)This is a blog post version of a talk I gave at the 5th [ICANN DNS Symposium](https://www.icann.org/ids).

 [![修改后的 XKCD 2347，将 DNS 作为主要的
依赖](xkcd2347-dns.png)](https://xkcd.com/2347/)这是我在 第五届 [ICANN DNS 座谈会](https://www.icann.org/ids) 。

Why yes, the internet is resting on a foundation of [duct tape and WD40](https://netmeister.org/blog/duct-tape-and-wd40.html) - it is known. And the DNS is the mother of all corner stones that, if knocked out, would quickly lead to the fall of western civilization. (And yes, it is a hard requirement to use [this XKCD cartoon](https://xkcd.com/2347/) to illustrate this.) But at least it's not quite as fragile as, say, [whois](https://netmeister.org/blog/whois.html), so yay!

为什么是的，互联网是建立在一个基础上的 和 [胶带 WD40](https://netmeister.org/blog/duct-tape-and-wd40.html) \- 众所周知。 DNS 是 所有房角石，如果被撞倒，很快就会 导致西方文明的没落。 （是的， 用 [这个XKCD卡通](https://xkcd.com/2347/) 是硬性要求 说明这一点。）但至少它不完全是 脆弱的，比如说， [whois](https://netmeister.org/blog/whois.html) ，所以 耶！

But while the DNS [root servers](https://root-servers.org/) are known to be distributed, I thought it might be interesting to take a closer look at the immediate levels up from the root, and so I went to analyze the diversity or centralization of the authoritative nameservers for the generic top-level domains (gTLDs) and the second-level domains in those gTLDs.

但是，虽然 DNS [根服务器](https://root-servers.org/) 是 已知被分发，我认为它可能是 有趣的是仔细看看眼前的 从根本上升级，所以我去分析 权威的多样性或集中化 通用顶级域 (gTLD) 的名称服务器 以及这些 gTLD 中的二级域。

To perform this analysis, I started out with the [root zone](https://www.iana.org/domains/root/files), which (as of November 2022) contains 1485 TLDs. As I [discussed previously](https://netmeister.org/blog/tlds.html), just what exactly you find in there is already utterly fascinating, but for our purposes here, let's note that you can then request access to all of the gTLD zone files via ICANN's [Centralized Zone Data Service](https://czds.icann.org/), which got me access to 1,165 zones in total. In addition, you can obtain the .gov zone from [CISA's GitHub repository](https://github.com/cisagov/dotgov-data), as well as .arpa from most of the root servers:

为了执行此分析，我从 [根 开始 zone](https://www.iana.org/domains/root/files) ，其中（截至 2022 年 11 月）包含 1485 顶级域名。 正如我 [所讨论的 以前](https://netmeister.org/blog/tlds.html) ，你在那里找到的正是 已经非常迷人了，但为了我们的目的 在这里，请注意您可以请求访问 的所有 gTLD 区域文件 [通过 ICANN 的集中区域数据 服务](https://czds.icann.org/) ，让我可以访问 1,165 个区域 全部的。 此外，您可以 获得.gov 区域 [从CISA GitHub 存储库](https://github.com/cisagov/dotgov-data) ，以及 .arpa 来自大部分根目录的 服务器：

```
$ dig +noall +answer +onesoa @f.root-servers.net arpa. AXFR | more
arpa.                   86400   IN      SOA a.root-servers.net. nstld.verisign-grs.com. 2022111501 1800 900 604800 86400
arpa.                   518400  IN      NS        m.ns.arpa.
arpa.                   518400  IN      NS        c.ns.arpa.
arpa.                   518400  IN      NS        f.ns.arpa.
[...]

```

This leaves us missing the .edu, .int, .mil and .post TLDs, which are not generally available. (If you know how to get access, please [let me know](mailto:jschauma@netmeister.org).)

这让我们错过了 .edu ， .int , .mil 和 .post TLD，它们不是 一般可用。 （如果你知道如何获得访问权限， 请 [让我 知道](mailto:jschauma@netmeister.org) 。）

For the country-code specific top-level domains (ccTLDs), it's a lot more difficult to gain access: most operators do not provide public access, although [some do](https://jpmens.net/2021/05/18/dns-open-zone-data/): you can AXFR some of them or gather some published data [from others](https://sk-nic.sk/subory/domains.txt). Commercial services exist that sell you zone data, but it seems to me that this data ought to be public, so I excluded ccTLDs from my analysis for the time being.

对于国家代码特定的顶级域 （ccTLD），获得访问权限要困难得多： 大多数运营商不提供公共接入，尽管 [一些 做](https://jpmens.net/2021/05/18/dns-open-zone-data/) ：你可以 AXFR 其中一些或收集 一些公布的数据 [来自 其他人](https://sk-nic.sk/subory/domains.txt) 。 存在卖给你的商业服务 区域数据，但在我看来，这些数据应该 是公开的，所以我从我的分析中排除了 ccTLD 暂时。

Anyway, so with 1,168 total zone files adding up to around 7GB of data (of which the .com zone accounts for 4.8 GB alone!), I went ahead and used a variety of shell scripts and some perl glue to parse out the NS records to then see just what domains _those_ are in, i.e., who controls them.

Anyway, so with 1,168 total zone files adding up to around 7GB of data (of which the .com zone accounts for 4.8 GB alone!), I went ahead and used a variety of shell scripts and some perl glue to parse out the NS records to then see just what domains _those_ are in, i.e., who controls them.

### The Root

### 根

The DNS root zone itself is served by 13 root authorities, and as such is obviously and trivially diverse. The 13 authorities are managed by [twelve root operators](https://www.iana.org/domains/root/servers): 9 US organizations (including three US government entities), of which one (Verisign) operates two roots, one Swedish company ([Netnod](https://www.netnod.se/)), one organization in Japan ([WIDE](https://www.wide.ad.jp/)), and one headquartered in the Netherlands ([RIPE NCC](https://www.ripe.net/)). Obviously, all are in the same domain (i.e., root-servers.net):

DNS 根区本身由 13 根服务 当局，因此显然是微不足道的 各种各样的。 13 个权限由 [12 个 管理 根运营商](https://www.iana.org/domains/root/servers) ：9 个美国组织（包括 三个美国政府实体），其中一个（Verisign） 经营两个根，一个瑞典公司（ [Netnod](https://www.netnod.se/) ），一个 日本的组织（ [WIDE](https://www.wide.ad.jp/) ），和一个 总部设在荷兰（ [RIPE NCC](https://www.ripe.net/) ）。 显然，所有这些都在同一个域中（即 root-servers.net ）：

Now for the root itself, this illustration is of course a bit silly, but it gives you an idea of what I'm looking for in this analysis. And things do get a bit more interesting once we process all the NS records from the root zone itself, where we find 7,507 total NS records across 5,612 unique name servers, which [looks](https://netmeister.org/blog/images/nsauth-root-ns.png) reasonably diverse:

现在对于根本身，这个插图是 当然有点傻，但它让你知道什么 我正在寻找这个分析。 事情确实得到了 一旦我们处理完所有的东西就更有趣了 NS 记录来自根区域本身，其中 我们在 5,612 条唯一记录中找到了 7,507 条 NS 记录 名称服务器， [看起来](https://netmeister.org/blog/images/nsauth-root-ns.png) 合理 各种各样的：

```
$ awk '/IN[       ]*NS[   ]/ { print $NF }' root.zone | wc -l
    7507
$ awk '/IN[       ]*NS[   ]/ { print $NF }' root.zone | sort | uniq -c | wc -l
    5625
$ awk '/IN[       ]*NS[   ]/ { print $NF }' root.zone | sort | uniq -c | sort -rn | head -20
 119 ac4.nstld.com.
 119 ac3.nstld.com.
 118 ac2.nstld.com.
 118 ac1.nstld.com.
  47 l.gmoregistry.net.
  47 k.gmoregistry.net.
  47 b.gmoregistry.net.
  47 a.gmoregistry.net.
  46 ns-tld5.charlestonroadregistry.com.
  46 ns-tld4.charlestonroadregistry.com.
  46 ns-tld3.charlestonroadregistry.com.
  46 ns-tld2.charlestonroadregistry.com.
  46 ns-tld1.charlestonroadregistry.com.
  27 anycast9.irondns.net.
  27 anycast24.irondns.net.
  27 anycast23.irondns.net.
  27 anycast10.irondns.net.
  21 j.zdnscloud.com.
  21 i.zdnscloud.com.
  21 g.zdnscloud.com.
$ 
```

But if you look closer, you'll notice that many of the nameservers are in the same domain, so if we then flatten the whole thing, we see a bit more of a centralization. For example, 6.3% of the NS records being under nstld.com, which is operated by Verisign:

但如果你仔细观察，你会发现很多 名称服务器在同一个域中，所以如果我们然后 把整个东西弄平，我们看到更多 集权。 例如，6.3% 的 NS 记录在 nstld.com 下， 由 Verisign 运营：

![馅饼 
显示根区](nsauth-root-domains.png)

But thinking about this distribution a bit more quickly makes you realize that there isn't really an even distribution in the gTLD, since not all domains have the same footprint. As you may guess, the .com zone has more records than some of the other zones. More specifically, .com has over 164 million NS records, making up 73% of all the NS records in _all_ the gTLDs.

但是多考虑一下这个分布 很快让你意识到没有真正的 在 gTLD 中均匀分布，因为并非所有域 有相同的足迹。 正如您可能猜到的那样， .com 区域的记录比某些区域多 其他区域。 更具体地说， .com 拥有超过 1.64 亿 NS 记录，占所有 NS 的 73% 中的记录。 _所有_ gTLD

![馅饼
显示所有 gTLD 中 NS 记录数量的图表](nsauth-ns-by-gtlds.png)

The NS records for .com are in the gtld-servers.net domain, but so are e.g., .net's; similarly, the NS records for .org and .info are in the same domain, so we can flatten this data a little bit more:

的 NS 记录 .com 在 gtld-servers.net 域中，但也是如此 例如， .net 的； 同样， 的NS 记录 .org 和 .info 在同一个域中，所以 我们可以将这些数据再展平一点：

![馅饼
显示所有 gTLD 中 NS 记录数量的图表
按域扁平化](nsauth-ns-by-gtlds-combined.png)

In other words, almost 80% of all NS records across _all_ gTLDs are under the gtld-servers.net domain, and thus the control of Verisign -- the same Verisign that _also_ operates two roots.

换句话说，几乎 80% 的 NS 记录 在 _所有_ gTLD 中 在 gtld-servers.net 域下，因此 威瑞信的控制权——同一个威瑞信 _还_ 经营两个根。

Ok, so this is the representation of the NS records _for_ the gTLDs within the root zone, but what about the NS records for all the second-level domains _within_ the gTLDs? Parsing all 1,168 zone files, we end up with 2,699,827 unique name servers that we can group under 1,063,092 domains:

好的，这就是 NS 记录的表示 _对于_ 根区内的 gTLD，但是什么 关于所有二级域名的NS记录 _在_ gTLD 中？ 解析所有 1,168 个区域 文件，我们最终得到 2,699,827 个唯一名称服务器 我们可以在 1,063,092 个域下分组：

![馅饼
显示所有 gTLD 中 NS 记录数量的图表
按域扁平化](nsauth-across-gtlds-by-domain.png)

This shows a notable centralization of the NS records found in all gTLD zones, with domaincontrol.com accounting for roughly 20% alone.

这表明了显着的中心化 在所有 gTLD 区域中找到NS 记录，其中 domaincontrol.com 占 单独约占20%。

Another thing that seems interesting here is that some of the cloud companies offering DNS services are choosing to use a larger number of NS records even across, in the case of AWS, thousands of second-level domains in several TLDs:

另一件有趣的事是 一些提供 DNS 服务的云公司是 选择使用更多的 NS 记录 甚至在 AWS 的情况下，数以千计的 几个 TLD 中的二级域：

```
$ grep awsdns- domain-counts.full | head
52221 awsdns-02.org.
49614 awsdns-23.net.
49264 awsdns-49.com.
48276 awsdns-05.co.uk.
46392 awsdns-35.org.
45955 awsdns-53.com.
45593 awsdns-19.net.
44409 awsdns-25.com.
44176 awsdns-22.co.uk.
44140 awsdns-45.org.
$ grep -c awsdns- domain-counts.full 
978

```

The data now show that out of the over 534 million NS records across a little over 1 million domains:

现在的数据显示，在超过 534 百万 NS 超过 1 的 记录 百万域名：

-   43% of all NS records (roughly 230 million) are served by only 165 name servers found in just 10 domains
-   所有 NS 记录中的 43%（大约 2.3 亿条）仅由 10 个域中的 165 个名称服务器提供服务
-   52% (~ 278 million) are served by 255 name servers in just 20 domains
-   52%（约 2.78 亿）由 20 个域中的 255 个名称服务器提供服务
-   75% (~ 401 million) are served by 1,580 name servers in just 100 domains
-   75%（约 4.01 亿）由 100 个域中的 1,580 个名称服务器提供服务
-   99% (~ 529 million) are served by 345,000 name servers in 6,000 domains
-   99%（约 5.29 亿）由 6,000 个域中的 345,000 个名称服务器提供服务

Let's look at these 20 domains and see who controls them, and thus over half of all the domains in all the gTLDs. They are:

让我们看看这 20 个域，看看谁在控制 他们，因此所有域中的一半以上 通用顶级域名。 他们是：

<table data-translationmark="copiedNode"><tbody><tr><td><ol><li><small><tt>domaincontrol.com</tt> is <s>Wild West Domains</s> GoDaddy 🇺🇸 (AS44273)</small></li><li><small><tt>googledomains.com</tt> is Google 🇺🇸 (AS15169)</small></li><li><small><tt>cloudflare.com</tt> is Cloudflare 🇺🇸 (AS13335)</small></li><li><small><tt>ui-dns.*</tt> is <s>IONOS</s> United Internet AG 🇩🇪 (AS8560)</small></li><li><small><tt>registrar-servers.com</tt> is Namecheap 🇺🇸 (AS397213)</small></li><li><small><tt>wixdns.net</tt> is Wix.com Ltd. 🇮🇱 (AS15169)</small></li><li><small><tt>hichina.com</tt> is Alibaba Cloud Computing 🇨🇳 (AS37963)</small></li><li><small><tt>dns.com</tt> is <s>Comodo</s> Xcitum 🇺🇸 (AS21859, AS133775 🇨🇳)</small></li><li><small><tt>awsdns-*</tt> is Amazon Web Services 🇺🇸 (AS16509)</small></li><li><small><tt>nsone.net</tt> is NS1 🇺🇸 (AS62597)</small></li></ol></td><td><ol start="11"><li><small><tt>namebrightdns.com</tt> is <s>NameBright</s> Turn Commerce Inc. 🇺🇸 (AS14618)</small></li><li><small><tt>gname-dns.com</tt> is Gname 🇸🇬 (AS13335)</small></li><li><small><tt>name-services.com</tt> is Enom 🇺🇸 / 🇨🇦 (AS15348)</small></li><li><small><tt>dnsowl.com</tt> is NameSilo 🇺🇸 (AS13335)</small></li><li><small><tt>squarespacedns.com</tt> is Squarespace 🇺🇸 (AS63911)</small></li><li><small><tt>worldnic.com</tt> is Network Solutions LLC 🇺🇸 (AS13335)</small></li><li><small><tt>bluehost.com</tt> is Newfold Digital, Inc 🇺🇸 (AS13335)</small></li><li><small><tt>name.com</tt> is <s>Donuts Inc</s> Identity Digital 🇺🇸 (AS62597)</small></li><li><small><tt>myhostadmin.net</tt> 🇨🇳 (AS38283)</small></li><li><small><tt>wordpress.(org|com)</tt> is Automattic Inc. 🇺🇸 (AS2635)</small></li></ol></td></tr></tbody></table>

<table><tbody><tr><td><ol><li><small><tt><span>domaincontrol.com </span></tt><span>是 </span><s><span>Wild West Domains </span></s><span>GoDaddy 🇺🇸 (AS44273)</span></small></li><li><small><tt><span>googledomains.com </span></tt><span>是 Google 🇺🇸 (AS15169)</span></small></li><li><small><tt><span>cloudflare.com </span></tt><span>是 Cloudflare 🇺🇸 (AS13335)</span></small></li><li><small><tt><span>ui-dns.* </span></tt><span>是 </span><s><span>IONOS </span></s><span>United Internet AG 🇩🇪 (AS8560)</span></small></li><li><small><tt><span>registrar-servers.com </span></tt><span>是 Namecheap 🇺🇸 (AS397213)</span></small></li><li><small><tt><span>wixdns.net </span></tt><span>是 Wix.com Ltd. 🇮🇱 (AS15169)</span></small></li><li><small><tt><span>hichina.com </span></tt><span>是阿里云计算 ⇨🇳 (AS37963)</span></small></li><li><small><tt><span>dns.com </span></tt><span>是 </span><s><span>Comodo </span></s><span>Xcitum 🇺🇸（AS21859，AS133775 ⇨🇳）</span></small></li><li><small><tt><span>awsdns-* </span></tt><span>是亚马逊网络服务🇺🇸（AS16509）</span></small></li><li><small><tt><span>nsone.net </span></tt><span>是 NS1 🇺🇸 (AS62597)</span></small></li></ol></td><td><ol start="11"><li><small><tt><span>namebrightdns.com </span></tt><span>是 </span><s><span>NameBright </span></s><span>Turn Commerce Inc. 🇺🇸 (AS14618)</span></small></li><li><small><tt><span>gname-dns.com </span></tt><span>是 Gname 🇸🇬 (AS13335)</span></small></li><li><small><tt><span>name-services.com </span></tt><span>是 Enom 🇺🇸 / ⇨🇦 (AS15348)</span></small></li><li><small><tt><span>dnsowl.com </span></tt><span>是 NameSilo 🇺🇸 (AS13335)</span></small></li><li><small><tt><span>squarespacedns.com </span></tt><span>是 Squarespace 🇺🇸 (AS63911)</span></small></li><li><small><tt><span>worldnic.com </span></tt><span>是 Network Solutions LLC 🇺🇸 (AS13335)</span></small></li><li><small><tt><span>bluehost.com </span></tt><span>是 Newfold Digital, Inc 🇺🇸 (AS13335)</span></small></li><li><small><tt><span>name.com </span></tt><span>是 </span><s><span>Donuts Inc </span></s><span>Identity Digital 🇺🇸 (AS62597)</span></small></li><li><small><tt><span>我的主机管理员网 ⇨🇳 </span></tt><span>(AS38283)</span></small></li><li><small><tt><span>wordpress.(org|com) </span></tt><span>是 Automattic Inc. 🇺🇸 (AS2635)</span></small></li></ol></td></tr></tbody></table>

You may notice that of these 20 organizations, 15 are US entities, 2 Chinese, 1 German, 1 Israeli, and one from Singapore, giving you an idea what governments could -- in theory, at least -- exert control over what percentage of the internet.

您可能会注意到，在这 20 个组织中，有 15 个 是美国实体，2个中国，1个德国，1个以色列，和 一个来自新加坡，让你知道什么 政府可以——至少在理论上——发挥 控制互联网的百分比。

Another interesting thing to point out here is that even though the domains are registered by different organizations, the name servers in use may actually be _operated_ from a different entity's networks. In particular, it looks like several of the name servers in these domains are running out of, fronted by, or otherwise utilizing Cloudflare's network, while Wix seems to be using Google Cloud (I'm guessing) to run their name servers.

这里要指出的另一件有趣的事情是 即使域名由不同的人注册 组织，正在使用的名称服务器实际上可能是 _运营_ 从不同实体的网络 。 特别像几个名字 这些域中的服务器快用完了 通过或以其他方式利用 Cloudflare 的网络， 而 Wix 似乎在使用谷歌云（我 猜测）来运行他们的名称服务器。

name.com is owned by [Identity Digital](https://en.wikipedia.org/wiki/Identity_Digital), the rebranding of the merged Donuts and Afilias (previously discussed [here](https://netmeister.org/blog/whois.html#registries)) registries, which _also_ operates a significant number of TLD domains.

name.com 归 [Identity 所有 Digital](https://en.wikipedia.org/wiki/Identity_Digital) ，合并后的 Donuts 和 Afilias（之前在 [这里](https://netmeister.org/blog/whois.html#registries) 讨论过）注册中心， 经营 _它还_ 着大量的 顶级域名。

All in all a sign that perhaps we should take a look at the Autonomous System (AS) numbers the various name servers are in, and so, a few thousand lookups later:

总而言之，也许我们应该采取一个迹象 查看自治系统 (AS) 编号 各种名称服务器都在，所以，几千 稍后查找：

![显示 AS 多样性的饼图
所有 gTLD 的 NS 记录编号](nsauth-gtlds-by-as.png)

That's right: around 34% of the majority of NS records are resolving to IP addresses in Cloudflare's AS13335, and over half of all are ultimately served from only four Autonomous Systems: Cloudflare ([AS13335](https://bgp.he.net/AS13335#_whois)), Alibaba ([AS37963](https://bgp.he.net/AS37963#_whois)), GoDaddy ([AS44273](https://bgp.he.net/AS44273#_whois)), and IONOS ([AS8560](https://bgp.he.net/AS8560#_whois)) (hinting at [the other big load-bearing infrastructure pillar](https://en.wikipedia.org/wiki/Border_Gateway_Protocol) that also remains largely insecure by default.

没错：大约 34% 的大多数人 NS 记录解析为 IP 地址 Cloudflare 的 AS13335，其中超过一半是 最终仅由四个自治系统提供服务： Cloudflare ( [AS13335](https://bgp.he.net/AS13335#_whois) ), 阿里巴巴（ [AS37963](https://bgp.he.net/AS37963#_whois) ）， GoDaddy ( [AS44273](https://bgp.he.net/AS44273#_whois) ), 和 IONOS ( [AS8560](https://bgp.he.net/AS8560#_whois) ) 暗示 [（ 大型承重基础设施支柱](https://en.wikipedia.org/wiki/Border_Gateway_Protocol) 其他 默认情况下，在很大程度上仍然是不安全的。

And while that is interesting by itself, just as before when we looked at the name servers serving the gTLD domains themselves and we tried to weigh them against how many domains they support, perhaps we should also look at not only the NS diversity in the raw gTLDs; after all, control of google.com or facebook.com surely counts more than, say, monkeyjungle.com.

虽然这本身很有趣，就像 之前当我们查看服务于 gTLD 域本身，我们试图权衡它们 他们支持多少域，也许我们 还应该不仅关注 NS 多样性 原始 gTLD； 毕竟，控制 google.com 或 facebook.com 肯定更重要 比说 monkeyjungle.com 。

So what do people do when they want to look at popular domains? They go for the "Alexa Top 1 Million Domains" list, of course! Only... Alexa was bought by Amazon, and in a sign of "who controls the internet", Amazon promptly [shut it down](https://alexa.com/). (As of November 8th, 2022, the [actual list](http://s3.amazonaws.com/alexa-static/top-1m.cvs.zip) was still available, but it looks like it has since been restricted.) Of course there are other, similar lists (like e.g., the [Cisco Umbrella](https://s3-us-west-1.amazonaws.com/umbrella-static/index.html) or the [Majestic Million](https://majestic.com/reports/majestic-million)), all of which intersect to some degree but remain distinct based on the heuristics used by the data collection mechanisms used. For this reason, researchers provide a normalized [Top 1 Million](https://tranco-list.eu/) list (see their [paper](https://tranco-list.eu/assets/tranco-ndss19.pdf) for more details), which I've used for this project here.

那么当人们想看的时候他们会做什么 热门域名？ 他们争取“Alexa 前 100 万” 域”列表，当然！只有...... Alexa 被收购了 亚马逊，并以“谁控制互联网”为标志， 亚马逊立即 [关闭它 下来](https://alexa.com/) 。 （截至2022年11月8日， [实际 列表](http://s3.amazonaws.com/alexa-static/top-1m.cvs.zip) 仍然可用，但看起来它有 因为被限制了。）当然还有其他的， 类似的列表（例如 [Cisco 雨伞](https://s3-us-west-1.amazonaws.com/umbrella-static/index.html) 或 [雄伟 百万](https://majestic.com/reports/majestic-million) ），所有这些都在某种程度上相交 但根据所使用的启发式方法保持不同 使用的数据收集机制。 为此原因， 研究人员提供了标准化的 [前 100 万](https://tranco-list.eu/) 名单 （见他们的 [论文](https://tranco-list.eu/assets/tranco-ndss19.pdf) 有关更多详细信息），我已将其用于此项目 这里。

Iterating over that full list and looking up the NS records for 1 million domains then yields a breakdown of 2,636,294 total NS records in 119,291 domains, as well as [the insight](https://twitter.com/jschauma/status/1590732890110820355) that spreadsheets are surprisingly bad at handling large data sets even of simple text data:

遍历整个列表并查找 NS 100 万个域的 记录然后产生 119,291 中 2,636,294 条 NS 记录的细分 以及 [域， 洞察力](https://twitter.com/jschauma/status/1590732890110820355) 电子表格出奇糟糕的 处理大型数据集，即使是简单的文本数据：

![展示 NS 多样性的饼图
记录前 100 万个域名的域名](nsauth-top1m.png)

So we see a very similar distribution to our analysis of all of the NS records in all of the gTLDs here in the top 1 million domains, too: More than half of the NS records used by the top one million domains are found in just 20 of the 120K domains, served by only 1,740 NS records.

所以我们看到一个非常相似的分布 分析所有 gTLD 中的所有 NS 记录 这里也是排名前 100 万的域： 超过一半的 NS 记录被 top 所使用 120,000 万个域中只有 20 个被发现 域，仅由 1,740 条 NS 记录提供服务。

The top ten NS record domains is represented by the usual suspects (Cloudflare, Amazon, GoDaddy, Akamai, DigiCert, Google, Microsoft, Alibaba, Network Solutions, and Namecheap), although not identical to those we observed for all of the gTLD records.

前十名 NS 记录域由 通常的嫌疑人（Cloudflare、亚马逊、GoDaddy、Akamai、 DigiCert、谷歌、微软、阿里巴巴、网络 解决方案和 Namecheap），虽然不完全相同 我们观察到的所有 gTLD 记录。

Also noteworthy is that the distribution across NS domains shifts somewhat when you look at the top 100 domains (Azure, AWS, Google, Akamai), the top 1,000 domains (AWS, Akamai, NS1, Google), the top 10K domains (AWS, AKamai, Cloudflare, NS1) and the full top 1 million (Cloudflare, Amazon, GoDaddy, Akamai), suggesting that more of the less popular sites use Cloudflare than do the higher ranked sites.

同样值得注意的是，NS 的分布 当您查看前 100 名时，域名会有所变化 域（Azure、AWS、Google、Akamai），前 1,000 个 域（AWS、Akamai、NS1、Google），前 10K 域（AWS、AKamai、Cloudflare、NS1）和完整的 前 100 万（Cloudflare、Amazon、GoDaddy、Akamai）， 建议更多不太受欢迎的网站使用 Cloudflare 比排名更高的网站。

At the same time, when we do the same breakdown by AS number as before (with many thanks to our friends at [Team Cymru](https://www.team-cymru.com/ip-asn-mapping)), we notice an even increased centralization:

同时，当我们做同样的分解时 AS 号码和以前一样（非常感谢我们的朋友 在 [团队 Cymru](https://www.team-cymru.com/ip-asn-mapping) ），我们注意到甚至增加了 集权：

![展示 NS 多样性的饼图
AS记录前100万个域名](nsauth-top1m-by-as.png)

Out of almost 10,000 IP addresses covering 75% of the top one million domains' NS records, over 40% again land in Cloudflare's AS13335, with most of the others being mere "also-ran"s.

在近 10,000 个 IP 地址中，覆盖了 75% 前百万域名的NS记录，超过40% 再次登陆 Cloudflare 的 AS13335，其中大部分 其他人仅仅是“失败者”。

Ok, so that's a whole lot of pie charts, and learning that there is indeed a fair bit of centralization at the gTLD level of the DNS will not come as a surprise to many. However, crunching those numbers still provides for some useful insights. So if we wanted to answer the question "Who controls the internet?", then I think that we may find multiple answers:

好的，这是一大堆饼图，学习 确实有相当多的中心化 DNS 的 gTLD 级别不会让人感到意外 太多。 然而，处理这些数字仍然 提供了一些有用的见解。 所以如果我们想 回答“谁控制互联网？”的问题，然后 我认为我们可能会找到多个答案：

**1\. Verisign** -- In addition to operating two of the DNS root authorities, Verisign also controls the gtld-servers.net domain, which we've seen above is home to a whopping 80% of all gTLD NS records! Take out Verisign, and the internet's going to have a bad day.

**1.威瑞信** ——除了运营两个 的 DNS 根权限，Verisign 还控制 gtld-servers.net 域 ， 我们在上面看到的是高达 80% 的 所有 gTLD NS 记录！ 去掉威瑞信，然后 互联网将有糟糕的一天。

**2\. A handful of large companies** -- i.e., the usual suspects. With 43% of all NS records in all gTLDs and 44% of those in the Top 1M in a combined 14 domains, any one of those could exert significant control over large chunks of the internet. But amongst those companies, a few stand out:

**2\. 少数大公司** ——即 普通嫌犯。 占所有 NS 记录的 43% gTLD 和前 1M 中 44% 的 14 领域，其中任何一个都可以发挥重要作用 控制互联网的大块。 但 在这些公司中，有几家脱颖而出：

**3\. GoDaddy** -- owner of the aptly named domaincontrol.com domain is responsible for 20% of all NS records in all gTLDs alone.

**3\.** GoDaddy——恰当命名的 domaincontrol.com 域的所有者是 负责所有 gTLD 中 20% 的 NS 记录 独自的。

**4\. Cloudflare** -- responsible for 20% of NS records in the top one million domains, Cloudflare also provides the IP space home to a total 40% of those NS records.

**4\. Cloudflare——** 负责20%的NS 前 100 万个域中的记录，Cloudflare 还为总共 40% 的 那些 NS 记录。

What this centralization means in practice and whether, for example, the US government could realistically exert control over the root operators and companies discussed here, is a different story altogether. But no matter how you look at it, the internet seems less distributed or decentralized than one might wish, as many businesses and organizations appear to concentrate in a handful of registries and cloud service providers.

这种集中化在实践中意味着什么 例如，美国政府是否可以 切实控制根运营商 和这里讨论的公司是另一回事 共。 但无论怎么看， 互联网似乎没有那么分散或去中心化 人们可能希望，许多企业和组织 似乎集中在少数几个注册表中 云服务提供商。

We don't have a single point of failure just yet, but I do see multiple points of calamity with increasing blast radius...

我们还没有单点故障， 但我确实看到了多个灾难点 增加爆炸半径...

November 15th, 2022

2022 年 11 月 15 日

___

Links:

链接：

-   [This blog post as a Twitter thread](https://twitter.com/jschauma/status/1592725563139145728)
-   [这篇博文作为 Twitter 主题](https://twitter.com/jschauma/status/1592725563139145728)
-   [Discussion on HackerNews](https://news.ycombinator.com/item?id=33794489)
-   [关于 HackerNews 的讨论](https://news.ycombinator.com/item?id=33794489)
-   [Google Sheet containing most of the above pie charts and data](https://docs.google.com/spreadsheets/d/1XJGnCRkfXqnznrg-E_28nAYuj05q3qq7yuYi7r_-1EA/edit#gid=1624786732)
-   [包含上述大部分饼图和数据的 Google 表格](https://docs.google.com/spreadsheets/d/1XJGnCRkfXqnznrg-E_28nAYuj05q3qq7yuYi7r_-1EA/edit#gid=1624786732)
-   [APNIC Blog analysis on DNS centralization](https://blog.apnic.net/2022/11/22/looking-at-centrality-in-the-dns)
-   [关于 DNS 的 APNIC 博客分析 集权](https://blog.apnic.net/2022/11/22/looking-at-centrality-in-the-dns)
-   [TLD Zone File Statistics](https://www.statdns.com/)
-   [TLD 区域文件统计](https://www.statdns.com/)
-   [ICANN DNS Symposium](https://www.icann.org/ids)
-   [ICANN DNS 研讨会](https://www.icann.org/ids)
-   [TLDs -- Putting the '.fun' in the top of the DNS](https://netmeister.org/blog/tlds.html)
-   [TLD——将“.fun”放在 DNS 的顶部](https://netmeister.org/blog/tlds.html)
-   [WHOIS: Fragile, unparseable, obsolete... and universally relied upon](https://netmeister.org/blog/whois.html)
-   [WHOIS：脆弱、无法解析、过时……并且普遍依赖](https://netmeister.org/blog/whois.html)
