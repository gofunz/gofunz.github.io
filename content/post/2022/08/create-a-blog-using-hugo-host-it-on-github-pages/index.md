---
title: "透過 Hugo & Github Pages 部落格"
slug: "create-a-blog-using-hugo-host-it-on-github-pages"
description:
date: 2022-08-16T23:24:47+08:00
image:
math:
license:
hidden: false
comments: true
draft: true
categories:
  - WebsiteDevelopment
tags:
  - Blog
  - Hugo
  - Github
  - Github Pages
---

## 大綱

1. 介紹 Hugo
2. 安裝 Hugo
3. 下載 「Hugo Theme Stack Starter」 部落格主題
4. 設定主題參數
5. 上架至 Github Pages

## 介紹 Hugo

待補

## 安裝 Hugo

待補

## 下載 「Hugo Theme Stack Starter」 部落格主題

```bash
git submodule add https://github.com/CaiJimmy/hugo-theme-stack/ && \
    themes/hugo-theme-stack

```

複制範例內容

```bash
cp exampleSite/config.yaml .
cp -r exampleSite/content .
```

啟動

```bash
hugo server -w
```

## 參考

1. [留言工具 - unnerances](https://bjmqfg83.github.io/blog/hugo_unnerances/)
2. [部落格主題 - Hugo Theme Stack](https://github.com/CaiJimmy/hugo-theme-stack-starter)
