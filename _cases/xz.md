---
permalink: /cases/xz/
title: xz
---

# xz backdoor: software vulnerability development and discovery

*NB! Technically,the XZ backdoor is not an "AI case". However, the case highlights human aspects of software systems which remain relevant for any other software development context, including AI.*

## quick overview of the case

On 29 April 2024, a developed announces in OSS mailing list the discovery of a malicious backdoor in [XZ Utils](https://en.wikipedia.org/wiki/XZ_Utils). On further inquiry it turns out that the vulnerability was systematically and covertly introduced as a result of 2-3 years of social engineering by at least one or several persons / accounts. Over that time, the maintainer of XZ was approached by a character "Jia Tan" who worked to gain trust by making benign contributions, then became the co-maintainer of XZ. From January 2024, "Jia Tan" introduced the malicious changes that contained the backdoor system. The backdoor code was hidden so that it was not apparent in the publicly available code repository (kept on GitHub). Instead, the malicious codes were covertly loaded and executed from the test files. 

lcamtuf 2024. ‘Techies vs Spies: The Xz Backdoor Debate’. *Substack newsletter. Lcamtuf’s Thing*. 30 March 2024. [https://lcamtuf.substack.com/p/technologist-vs-spy-the-xz-backdoor](https://lcamtuf.substack.com/p/technologist-vs-spy-the-xz-backdoor).

Quote: "More fundamentally, the xz backdoor **isn’t a technical problem** and it probably can’t be solved with technology alone. To a large extent, it’s a counterintelligence challenge..."


## timeline of discovery

### 29 March 2024, Good Friday

- In oss-security [open source software security] list, Andres Freund [announces the discovery of a software vulnerability](https://www.openwall.com/lists/oss-security/2024/03/29/4) in [XZ Utils](https://en.wikipedia.org/wiki/XZ_Utils), an upstream software package/dependency used in various Linux-based operating systems.

Security implications: the vulnerability is not (yet) published as a part of major systems (Linux distributions), but was in some beta versions already. 

- [NIST](https://www.nist.gov/) assigns XZ a CVE ([Common Vulnerabilities and Exposures](https://www.redhat.com/en/topics/security/what-is-cve)) ID number [CVE-2024-3094](https://nvd.nist.gov/vuln/detail/CVE-2024-3094) with the maximum security threat score of 10 [critical].


### 30 March 2024

["xz/liblzma: Bash-stage Obfuscation Explained"](https://gynvael.coldwind.pl/?lang=en&id=782), an initial technical overview of the backdoor's functions by Gynvael Coldwind



### 12 April 2024

[Initial analysis by Kaspersky](https://securelist.com/xz-backdoor-story-part-1/112354/)


## vocabulary

### backdoor
In infosec parlance, a backdoor is a software vulnerability that allows bypassing normal authentication and/or encryption methods (username, password, etc). 

[Read about backdoor in Wikipedia »](https://en.wikipedia.org/wiki/Backdoor_(computing))


### dependency

[![XKCD illustration of dependency](https://imgs.xkcd.com/comics/dependency.png)](https://xkcd.com/2347/)






## threat and social engineering timeline


### 29 Oct 2021
The actor "Jia Tan" appears and makes an innocent, helpful contribution (a "patch") to the xz project. [(See e-mail message in xz mailinglist.)](https://www.mail-archive.com/xz-devel@tukaani.org/msg00512.html)


### 19 May - 29 Jun 2022
Various personas appear in the xz mailinglist and complain about the maintenance (slow updating schedule etc) of the XZ project. On **7 Jun 2022**, [a "Jigar Kumar" presses for a new maintainer](https://www.mail-archive.com/xz-devel@tukaani.org/msg00562.html), using emotional blackmail: "Submitting patches here has no purpose these days. The current maintainer lost interest or doesn't care to maintain anymore. It is sad to see for a repo like this." The [maintainer (Lasse Colllin) replies to the emotional blackmail on **Jun 8** and also mentions that "Jia Tan" has been helping](https://www.mail-archive.com/xz-devel@tukaani.org/msg00567.html). A week later, [on 14 Jun 2022, "Jigar Kumar" again replies](https://www.mail-archive.com/xz-devel@tukaani.org/msg00568.html) with more emotional blackmail, with the purpose of speeding up the maintainer change:
"You ignore the many patches bit rotting away on this mailing list. Right now you choke your repo. Why wait until 5.4.0 to change maintainer? Why delay what your repo needs?" [21 Jun 2022 a "Dennis Ens" repeats the suggestion for maintainer change](https://www.mail-archive.com/xz-devel@tukaani.org/msg00569.html).[On 29 Jun 2022, Lasse concedes that finding a co-maintainer is a possibility](https://www.mail-archive.com/xz-devel@tukaani.org/msg00571.html) and that it could be the "Jia Tan" persona.

### 2024
**19 Jan** - JiaT75 github account takes over the maintenance of XZ website [timeline](https://securelist.com/xz-backdoor-story-part-1/112354/)

23 Feb - the malicious script is added as test files
**24 Feb** - new version (XZ 5.6.0) release

**9 Mar** - anoother new version (XZ 5.6.1) released, contains additional malicious code

**28 Mar 2024**: "bug is discovered, Debian and RedHat notified" [(according to Kaspersky analysis)](https://securelist.com/xz-backdoor-story-part-1/112354/)

**29 Mar**: notification of backdoor in OSS Security mailing list


