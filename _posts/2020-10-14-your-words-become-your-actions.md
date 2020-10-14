---
layout: post
title: Your words become your actions
image: /img/2020-10-14-aaron-blanco-tejedor-yH18lOSaZVQ-unsplash-edited.jpg
tags: [diversity, inclusion, inclusive-language]
---
Worlds Matters! A master slave relationship is not just a primary and replica dependency… Terms such as master and slave are associated to social discrimination and should be used just in their context. 

## How I got interested in cross-cultural linguistic awareness

I recently got a deeper interest in cross-cultural linguistic awareness. It is a topic that I followed closely after the waves of awareness triggered by the Black Lives Matter movement. However, in the last weeks, I was lucky to get first hand exposure also at work. 
I’m an ambassador of the SW Engineering Expert Forum of Roche. In a huge company, where software development is spread in different countries and timezones, this forum helps us to create a network of software engineers specialized in the medical sector. Here, we can share best practices, learn from other projects and so nurture the community empowering the knowledge sharing. I enjoy being in this forum. From one hand, I can grow from the technical side. On the other hand, meeting and discussing with people coming from so many different countries is an enriching experience. 
In the last session of the ambassador program, some colleagues shared their endeavour to remove racially loaded terms from their repositories and documentation to favour racially neutral alternatives. Not surprisingly, this topic has been pushed forward by our US colleagues. And as you can imagine It is not as easy as pie. We are in a highly regulated environment and our products have a huge amount of documentation. Many documents, such as wiki, sharepoints, code repository can be easily changed. On the other hand, approved documents are a different deal.

## Raise the bar of your code and documentation

We need to be clear: replacing racially loaded terms is not just a simple “find and replace”. Usually, the racially loaded terms are by far generic and they can refer to several concepts. In order to clarify this point, in table 1 I collected a list of racially charged terms commonly used in the software industry. As you can see in the same table, the racially neutral alternatives are quite far more descriptive and precise than their corrispettive. This is another important benefit when adopting cross-cultural linguistic awareness. Your code and documentation can improve remarkably in readability and clarity, because you will specify with more precision the context.

**Table1: Racially charged terms and possible alternatives**

| **Racially Charged Terms** | **Racially Neutral Alternatives**                            |
| -------------------------- | ------------------------------------------------------------ |
| Master / Slave             | Primary-secondary<br>Primary-replica<br>Leader-follower<br>Active-standby<br>Writer-reader<br>Coordinator-worker<br>Parent-helper |
| Whitelist / Blacklist      | Blocklist-allowlist<br>Deny-allow<br>Droplist-accesslist<br>Drop-permit<br>Block-permit |
| Master                     | Main<br>Parent<br>Server |
| Slave                      | Worker<br>Child<br>Helper |
| Blackhats / Whitehats      | Unethical-ethical |

## The software industry is moving forward

When searching for racially loaded terms, I got the impression that the number of projects and companies that were taking the responsibility to move the needle was very relevant. Reading tech articles and blog posts, pulling Twitter threads and checking pull requests I collected a considerable amount of information that I summarized in Table 2. Of course, it’s not intended as a comprehensive source of truth. However, it helped me to understand the trend and create the infographic shown in Figure 1. 

![Infographic](/img/2020-10-14-infographic-projects-and-company-changes.png)

**Figure 1: Infographic of projects and company creating cross-cultural linguistic awareness**

If we put aside the Los Angeles County that already in 2003 asked suppliers and contractors to stop using “master” and "slave" on computer equipment. It’s not a surprise that the open source community has been an early bird on this aspect. Django and Drupal in 2014 replaced occurrences of master/slave terminology respectively with leader/follower and primary/replica. And as a .Net enthusiast, I’m happy to see that in 2015 the Roslyn compiler removed the term "whitelist", probably pushed by the .NET foundation that was recently born. In the following years several OSS and non-profit corporations followed their example. Here we can find big names such as the Internet Systems Consortium, Python, Redis, Chromium, PostgreSQL among others. 
However, the real game changer has been the Black Lives Matter movement in 2020. Then, also the enterprise world joined the party. Here, huge names such as Twitter, IBM, Linkedin showed their compromise to remove racially-charged phrases and move toward an inclusive language. For example, Google removed from Android Open Source Project (AOSP) worlds as "whitelist" and "blacklist" in favour of "allowlist" and "blocklist". Probably the more famous and emblematic of these changes has been performed by Microsoft, with GitHub. From the 1st of October of this year, all new repositories will not be created anymore with master as default branch. The new default will be the main branch. GitHub is trying to cause as little disruption to existing projects as possible. However, their roadmap is clear. In the next few months they are seamlessly moving existing repositories in the same direction. Also in 2020, the amount of OSS adopting racially neutral alternatives exploded.  

**Table 2: Reference of projects and company creating cross-cultural linguistic awareness**

| Year | Company - Project | Changes done | References |
| ---- | ---- | ---- | ------------- |
| 2003 | Los Angeles County | asked suppliers and contractors to stop using `master` and `slave` on computer equipment. | [1](https://edition.cnn.com/2003/TECH/ptech/11/26/master.term.reut/index.html) |
| 2014 | Django | replaced occurrences of master/slave terminology with ``leader/follower`` | [2](https://code.djangoproject.com/ticket/22667) |
| 2014 | Drupal | replaced 'master-slave' terminology with ``primary/replica`` | [3](https://www.drupal.org/project/drupal/issues/2275877) |
| 2015 |  Microsoft's Roslyn .NET compiler | removed the term ``whitelist`` | [4](https://github.com/dotnet/roslyn/pull/3507/files) |
| 2017 | [ISC] Internet Systems Consortium | removed usage of ``master/slave`` | [5](https://lists.isc.org/pipermail/bind-users/2020-June/103303.html) |
| 2018 | Python | removed ``master/slave`` terminology | [6](https://www.vice.com/en_us/article/8x7akv/masterslave-terminology-was-removed-from-python-programming-language) |
| 2018 | Redis | changed Redis ``master-slave`` replication terms | [7](https://github.com/antirez/redis/issues/5335) |
| 2019 | Chromium | cleanup of potentially offensive terms in codebase | [8](https://bugs.chromium.org/p/chromium/issues/detail?id=981129#c16) |
| 2019 | PostgreSQL | removed `replication slave` | [9](https://www.postgresql.org/message-id/flat/E393EC88-377F-4C59-A67A-69F2A38D17C7@yesql.se) |
| 2020 | National Security Cyber Center (NSCC) | used `allow list` and `deny list` in place of `whitelist` and `blacklist` | [10](https://www.ncsc.gov.uk/blog-post/terminology-its-not-black-and-white) |
| 2020 | Linkedin | removed any racially charged phrases | [11](https://twitter.com/gabrielcsapo/status/1269160583502327815) |
| 2020 | Github | replaced ``master`` with alternative term | [12](https://github.com/github/renaming) |
| 2020 | Twitter | moved toward inclusive language | [13](https://www.cnet.com/news/twitter-engineers-replace-racially-loaded-tech-terms-like-master-slave/) |
| 2020 | IBM | removed racially insensitive language from products | [14](https://www.zdnet.com/article/ibm-microsoft-staff-rally-to-remove-racially-insensitive-language-from-products/) |
| 2020 | IETF | encouraged inclusive terminology in the ongoing RFC series | [15](https://tools.ietf.org/id/draft-knodel-terminology-02.html) |
| 2020 | Google  | In Android removed ``whitelist`` and ``blacklist`` to ``allowlist`` and ``blocklist`` | [16](https://android-review.googlesource.com/q/topic:%22soong_inclusive_language%22+(status:open%20OR%20status:merged)) |
| 2020 | Go | replaced usages of `whitelist/blacklist` and ``master/slave`` | [17](https://go-review.googlesource.com/c/go/+/236857/) |
| 2020 | PHP Unit | removed the ``blacklist/whitelist`` terminology | [18](https://github.com/sebastianbergmann/phpunit/commit/8e9c76d33dab4095c9066072076f368193e4166d) |
| 2020 | Curl | avoided ``blacklist/whitelist`` stereotypes | [19](https://github.com/curl/curl/pull/5546) |
| 2020 | OpenZFS file storage manager | removed unnecessary references to slavery | [20](https://github.com/openzfs/zfs/pull/10435) |

## Is it worth it?
I’ll be honest. If you ask me this question, I’m for sure biased by the education I received. I have a strong opinion that it is worth investing energy to have a more inclusive language. It is not a coincidence that I’m working in a company stating that diversity and inclusion is the engine of our innovation. Infact, I think it really helps when your personal values are aligned with the vision of the company where you dedicate your time and passion. So, I was more than happy to see a bold commitment to remove racially loaded worlds.
I think that the software industry is not inclusive enough from different perspectives. So, it is already a good starting point having open discussions about diversity and inclusions. In this way, we can create awareness about a true story: nowaday racism is still a big issue and we should not forget it. Probably, some places suffer racism more than others. But we live in a globalized world and our software products are globally available.
I also think that our language strongly influences our behaviours. I don’t know how true are the claims of Neuro-Linguistic Programming (NLP) stating that there is a connection between neurological processes, language and behavioral patterns. But, I believe in the impact created by a little big man and I really trust its worlds:

“Your beliefs become your thoughts,
Your thoughts become your words,
Your words become your actions,
Your actions become your habits,
Your habits become your values,
Your values become your destiny.”
Gandhi

## References and Useful Readings 

1. [ Change done by Los Angeles County](https://edition.cnn.com/2003/TECH/ptech/11/26/master.term.reut/index.html)
2. [ Change done by Django](https://code.djangoproject.com/ticket/22667)
3. [ Change done by Drupal](https://www.drupal.org/project/drupal/issues/2275877)
4. [ Change done by Microsoft's Roslyn .NET compiler](https://github.com/dotnet/roslyn/pull/3507/files)
5. [ Change done by ISC - Internet Systems Consortium](https://lists.isc.org/pipermail/bind-users/2020-June/103303.html)
6. [ Change done by Python](https://www.vice.com/en_us/article/8x7akv/masterslave-terminology-was-removed-from-python-programming-language)
7. [ Change done by Redis](https://github.com/antirez/redis/issues/5335)
8. [ Change done by Chromium](https://bugs.chromium.org/p/chromium/issues/detail?id=981129#c16)
9. [ Change done by PostgreSQL](https://www.postgresql.org/message-id/flat/E393EC88-377F-4C59-A67A-69F2A38D17C7@yesql.se)
10. [ Change done by National Security Cyber Center (NSCC)](https://www.ncsc.gov.uk/blog-post/terminology-its-not-black-and-white)
11. [ Change done by Linkedin](https://twitter.com/gabrielcsapo/status/1269160583502327815)
12. [ Change done by Github](https://github.com/github/renaming)
13. [ Change done by Twitter](https://www.cnet.com/news/twitter-engineers-replace-racially-loaded-tech-terms-like-master-slave/)
14. [ Change done by IBM](https://www.zdnet.com/article/ibm-microsoft-staff-rally-to-remove-racially-insensitive-language-from-products/)
15. [ Change done by IETF](https://tools.ietf.org/id/draft-knodel-terminology-02.html)
16. [ Change done by Google](https://android-review.googlesource.com/q/topic:%22soong_inclusive_language%22+(status:open%20OR%20status:merged))
17. [ Change done by Go](https://go-review.googlesource.com/c/go/+/236857/)
18. [ Change done by PHP](https://github.com/sebastianbergmann/phpunit/commit/8e9c76d33dab4095c9066072076f368193e4166d)
19. [ Change done by Curl](https://github.com/curl/curl/pull/5546)
20. [ Change done by OpenZFS file storage manager](https://github.com/openzfs/zfs/pull/10435)

