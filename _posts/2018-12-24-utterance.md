---
layout: post
date: 2018-12-24 12:00:00
title: 从Gitment迁移到utterance
subtitle: 'Gitment到utterance无缝迁移，不丢评论'
author: jindaxia
categories: []
tags: [Gitment, utterance]
---

> Gitment无缝迁移到utterance

考虑到Gitment的安全性[争议]:https://blog.wolfogre.com/posts/security-problem-of-gitment/

决定把评论系统迁移到同样基于github Issue系统的 

[utterance]:https://www.xianmin.org/post/utterances-comment-system/

## utterance的使用方法

1. 在需要创建评论的repo上安装 utterance的apps ，https://github.com/apps/utterances
2. 页面增加一个<script>代码段

```js
<script src="https://utteranc.es/client.js"
        repo="[ENTER REPO HERE]"
        issue-term="title"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
```

## 无缝迁移的关键设置

> issue-term="title"

让utterance默认识别对应Issue的关键字采用title，这和Gitment的Issue标题是对应的，如果文章的标题添加了一些SEO信息，如博客标题什么的，也可以用 og:title，前提是文章的OGtitle设置了干净的值