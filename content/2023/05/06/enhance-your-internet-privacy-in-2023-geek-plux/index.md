---
title: "在2023年加强你的互联网隐私"
date: 2023-05-06T16:53:38+08:00
updated: 2023-05-06T16:53:38+08:00
taxonomies:
  tags: []
extra:
  source: https://geekplux.com/posts/internet-privacy
  hostname: geekplux.com
  author: GeekPlux
  original_title: "Enhance Your Internet Privacy in 2023 - GeekPlux"
  original_lang: en
---

In an increasingly digital world, maintaining online privacy has become a major concern. Many people are looking for ways to stay anonymous online to protect themselves from **invasive advertisements**, potential hackers, and **unwanted surveillance**.  

在一个日益数字化的世界里，维护在线隐私已成为一个主要的问题。许多人正在寻找在网上保持匿名的方法，以保护自己免受侵入性广告、潜在的黑客和不必要的监视。  

This article provides a comprehensive overview of the best practices and tools to enhance your internet privacy, including iCloud Private Relay, Cloudflare's 1.1.1.1, VPNs, and more.  

本文全面介绍了加强互联网隐私的最佳做法和工具，包括iCloud私人中继、Cloudflare的1.1.1.1、VPN，以及其他。  

Which is actually the solution used by myself, please feel free to give me more suggesstions.  

这实际上是我自己使用的解决方案，请随时给我更多建议。

## Understanding Cloudflare's 1.1.1.1  

了解Cloudflare的1.1.1.1[](https://geekplux.com/posts/internet-privacy#understanding-cloudflares-1111)

Cloudflare's [1.1.1.1 (opens in a new tab)](https://1.1.1.1/) is a DNS resolver that provides faster internet speed and enhanced privacy for users.  

Cloudflare的1.1.1.1（在新标签中打开）是一个DNS解析器，为用户提供更快的网络速度和增强的隐私。  

Instead of using the default DNS provided by your internet service provider (ISP), which can often be slow and insecure, Cloudflare's 1.1.1.1 provides a more robust and private option.  

Cloudflare的1.1.1.1不使用互联网服务提供商（ISP）提供的默认DNS，该DNS通常很慢且不安全，而是提供了一个更强大和私密的选择。  

It does this by not logging personal data and by using [DNS over HTTPS (DoH) or DNS over TLS (DoT) protocols (opens in a new tab)](https://developers.cloudflare.com/1.1.1.1/encryption/) to add a layer of security, protecting your browsing information from potential "spy" and attackers.  

它通过不记录个人数据和使用DNS over HTTPS（DoH）或DNS over TLS（DoT）协议（在新标签中打开）来增加一层安全，保护你的浏览信息不被潜在的 "间谍 "和攻击者发现。

## iCloud Private Relay: An In-Depth Look  

iCloud私人中继：深入了解[](https://geekplux.com/posts/internet-privacy#icloud-private-relay-an-in-depth-look)

[iCloud Private Relay (opens in a new tab)](https://support.apple.com/en-us/HT212614) is a service offered by Apple to its iCloud+ subscribers. It functions much like a VPN, encrypting your internet traffic and routing it through **two relays** to obscure your IP address and the sites you visit:  

iCloud私人中继（在一个新标签中打开）是苹果公司为其iCloud+用户提供的一项服务。它的功能很像VPN，对你的互联网流量进行加密，并通过两个中继站进行路由，以掩盖你的IP地址和你访问的网站：

-   The first relay server, operated by Apple, knows your IP address but not the destination website.  
    
    第一个中继服务器由苹果公司运营，它知道你的IP地址，但不知道目的地网站。
-   The second relay server, operated by a third-party provider, knows the destination website but not your IP address.  
    
    第二台中继服务器由第三方供应商运营，知道目的地网站，但不知道你的IP地址。

This way, no single entity, including Apple, can have a full picture of both who you are and what sites you're visiting, thus adding an extra layer of privacy to your internet browsing activities.  

这样一来，包括苹果在内的任何一个实体都无法全面了解你是谁以及你正在访问哪些网站，从而为你的互联网浏览活动增加了一层隐私。

## Using 1.1.1.1 and iCloud Private Relay Together  

一起使用1.1.1.1和iCloud私人中继[](https://geekplux.com/posts/internet-privacy#using-1111-and-icloud-private-relay-together)

You can use both 1.1.1.1 and iCloud Private Relay together for enhanced privacy.  

你可以同时使用1.1.1.1和iCloud私人中继，以增强隐私。  

The DNS queries from your device will be resolved by 1.1.1.1, while the iCloud Private Relay will provide the encryption and rerouting of your internet traffic.  

你的设备的DNS查询将由1.1.1.1解决，而iCloud私人中继将为你的互联网流量提供加密和重新路由。

## The Need for Additional VPNs 增加VPN的必要性[](https://geekplux.com/posts/internet-privacy#the-need-for-additional-vpns)

Using iCloud Private Relay and 1.1.1.1 together provides a significant level of privacy and security, but whether to use an additional VPN depends on your specific needs.  

同时使用iCloud私人中继和1.1.1.1可以提供相当程度的隐私和安全，但是否使用额外的VPN取决于你的具体需求。  

If you require features such as selecting a specific country for your IP address, bypassing geo-restrictions, or if you need a higher level of security, you may consider adding a VPN into the mix.  

如果你需要一些功能，如为你的IP地址选择一个特定的国家，绕过地理限制，或者如果你需要更高的安全水平，你可以考虑在组合中加入一个VPN。  

It's crucial to choose a reputable VPN provider, such as [ExpressVPN (opens in a new tab)](https://www.expressvpn.com/) or [Surfshark (opens in a new tab)](https://surfshark.club/friend/csNhyZHY), to ensure quality service and true privacy.  

选择一个有信誉的VPN供应商至关重要，如ExpressVPN（在新标签中打开）或Surfshark（在新标签中打开） ，以确保优质服务和真正的隐私。

## A Wide Array of Internet Privacy Tools  

各种各样的互联网隐私工具[](https://geekplux.com/posts/internet-privacy#a-wide-array-of-internet-privacy-tools)

There are many other tools to enhance your internet privacy, such as privacy-focused browsers like [Brave (opens in a new tab)](https://brave.com/) or [Tor (opens in a new tab)](https://www.torproject.org/), ad and script blockers like [AdGuard (opens in a new tab)](https://adguard.com/en/welcome.html) and [uBlock Origin (opens in a new tab)](https://github.com/gorhill/uBlock), private search engines like [DuckDuckGo (opens in a new tab)](https://duckduckgo.com/), and secure email services like [ProtonMail (opens in a new tab)](https://proton.me/mail). Each of these tools serves a specific purpose in your privacy toolkit, helping you achieve a safer and more private internet experience.  

还有许多其他工具可以增强你的互联网隐私，例如注重隐私的浏览器，如Brave（在新标签中打开）或Tor（在新标签中打开），广告和脚本拦截器，如AdGuard（在新标签中打开）和uBlock Origin（在新标签中打开），私人搜索引擎，如DuckDuckGo（在新标签中打开），以及安全电子邮件服务如ProtonMail（在新标签中打开）。这些工具中的每一个都在你的隐私工具箱中发挥着特定的作用，帮助你实现更安全、更私密的互联网体验。

## Balancing Privacy and Convenience  

平衡隐私和便利性[](https://geekplux.com/posts/internet-privacy#balancing-privacy-and-convenience)

My **personal strategy** is to only turn on iCloud Private Relay + 1.1.1.1, and turn on a VPN when necessary, such as when using public networks.  

我的个人策略是只打开iCloud私人中继+1.1.1.1，必要时打开VPN，如使用公共网络时。  

However, it's important to note that adding layers of security can lead to a **DECREASE in internet speed**. This is a trade-off: **it's usually impossible to have both convenience and security**, so you'll have to make choices based on your situation.  

然而，重要的是要注意，增加安全层会导致网速下降。这是一种权衡：通常不可能同时拥有便利和安全，所以你必须根据自己的情况做出选择。

## Best Practices for Internet Privacy  

互联网隐私的最佳做法[](https://geekplux.com/posts/internet-privacy#best-practices-for-internet-privacy)

Protecting your privacy online is increasingly important in today's digital age.  

在今天的数字时代，保护你的在线隐私越来越重要。  

Some of the best practices include using privacy-friendly browsers, VPNs, ad and script blockers, and other privacy tools.  

一些最佳做法包括使用隐私友好型浏览器、VPN、广告和脚本拦截器以及其他隐私工具。  

By understanding the risks and employing a combination of these tools and strategies, you can significantly enhance your online privacy and enjoy a safer internet surf.  

通过了解风险并采用这些工具和策略的组合，你可以大大增强你的在线隐私并享受更安全的互联网冲浪。
