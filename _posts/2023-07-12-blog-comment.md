---
title: 博客使用 utterances 作为评论系统
author: lovupw
tags: TeXt
---
# utterances 是一款基于 GitHub issues 的评论工具。

## 相比同类的工具 gitment、gitalk 以及 disqus 评论工具，优点如下：

  *  极其轻量
  *  加载非常快
  *  配置比较简单

## 之前博客一直使用 disqus ,这个工具配置也比较简单，也是免费的。但是，广告多，而且加载也比较慢。

## 体验了一把 utterances 后，马上切换到 utterances。
### 安装 utterances

1. utterances 的安装相当简单，因为出品了一个 Github App。

2. 首先安装这个 App ，选择要关联评论的仓库。可以选择所有仓库，也可以只选择一个仓库。选择一个仓库比较安全。

3. 安装完成就是配置成功了，是不是非常简单。
### 使用 utterances

1. 在你要使用评论的地方，插入以下代码：
```javascript
<script src="https://utteranc.es/client.js"
        repo="nusr/blog"
        issue-term="pathname"
        theme="github-light"  
        crossorigin="anonymous"
        async>
</script>
```
 nusr/blog 是你配置允许访问的仓库，格式为 user-name/repo-name 。

2. 或者动态创建 script 标签：
```javascript
<script type="text/javascript">
    (function() {
        // 匿名函数，防止污染全局变量
        var utterances = document.createElement('script');
        utterances.type = 'text/javascript';
        utterances.async = true;
        utterances.setAttribute('issue-term','pathname')
        utterances.setAttribute('theme','github-light')
        utterances.setAttribute('repo','nusr/blog')
        utterances.crossorigin = 'anonymous';
        utterances.src = 'https://utteranc.es/client.js';
        // content 是要插入评论的地方
        document.getElementById('content').appendChild(utterances);
    })();
</script>
```
我的博客是使用 Hugo 搭建的，可以参考我的配置 config.toml。
### 配置 utterances

utterances 可以配置主题，评论映射。

1. 主题 theme 选项如下：

  *  github-light
  *  github-dark
  *  github-dark-orange
  *  icy-dark
  *  dark-blue
  *  photon-dark

2. 评论 issue-term 映射配置选项如下：

  *  pathname
  *  url
  *  title
  *  og:title
  *  issue-number
  *  specific-term

更多配置查看 https://utteranc.es/
