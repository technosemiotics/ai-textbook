---
permalink: /cases/xz/
title: xz
---

# xz backdoor: software vulnerability development and discovery

*NB! Technically,the XZ backdoor is not an "AI case". However, the case highlights human aspects of software systems which remain relevant for any other software development context, including AI.*

### quick overview of the case

lcamtuf 2024. ‘Techies vs Spies: The Xz Backdoor Debate’. *Substack newsletter. Lcamtuf’s Thing*. 30 March 2024. [https://lcamtuf.substack.com/p/technologist-vs-spy-the-xz-backdoor](https://lcamtuf.substack.com/p/technologist-vs-spy-the-xz-backdoor).

Quote: "More fundamentally, the xz backdoor **isn’t a technical problem** and it probably can’t be solved with technology alone. To a large extent, it’s a counterintelligence challenge..."

## vocabulary

### backdoor
In infosec parlance, a backdoor is a software vulnerability that allows bypassing normal authentication and/or encryption methods (username, password, etc). 

[Read about backdoor in Wikipedia »](https://en.wikipedia.org/wiki/Backdoor_(computing))


### dependency

[![XKCD illustration of dependency](https://imgs.xkcd.com/comics/dependency.png)](https://xkcd.com/2347/)





## timeline (descending, from discovery)

### 29 March 2024, Good Friday

In oss-security [open source software security] list, Andres Freund [announces the discovery of a software vulnerability](https://www.openwall.com/lists/oss-security/2024/03/29/4) in xz, an upstream software package/dependency used in various Linux-based operating systems.

Security implications: the vulnerability is not (yet) part of major systems, but it was on the way of being integrated in some. 

On further inquiry it turns out that the vulnerability was systematically and covertly introduced as a result of 2-3 years of social engineering by at least one or several other persons / accounts. Over that time, a single maintainer - Lasse Collin — of a small software package (xz utilities) was approached by a character "Jia Tan" who first worked to gain trust, make benign changes, then became co-maintainer of the software package. In January 2024, "Jia Tan" finally introduced the software updates that contain the beginnings of the backdoor system. The backdoor was hidden so that it was not apparent in the publicly available code.

