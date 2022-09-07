---
title: "學習 Golang - 瞭解 RESTful API 最佳實踐"
description:
date: 2022-09-07T22:56:18+08:00
image:
math:
license:
hidden: false
comments: true
draft: false
categories:
  - WebsiteDevelopment
tags:
  - RESTful
  - API
---

## 大綱

1. 應避免 HTTP 80 Port
2. API Server 域名設計

## 說明

參考 [2.3. RESTful API 最佳实践 - learnku.com](https://learnku.com/courses/go-api/1.19/api-development-best-practices/13475) 並截取重點，給我了一些不同的觀點，是值得閱讀的一篇文件，另外，此篇文章的作者也提到 [Github REST API](https://docs.github.com/en/rest) 設計方式也可以參考。

## 應避免 HTTP 80 Port

HTTP 是明文傳輸，由於傳輸過程有可能被篡改或是竊取資料，例如: 信用卡資訊、帳號密碼 ... 等，所以其實相當危險，因此應該要關閉 HTTP 80 Port 的設置。

### 不好的方式 ❌

Client 端請求 HTTP 80 Port 時，我們都會再導向至 HTTPS 443 Port。

### 更好的方式 ✅

應該直接返回錯誤。

## API Server 域名設計

- 彈性化調整 Http Server 設置
- 無 Cookie 共享
- CDN 加速

### 不好的方式 ❌

```plain
https://www.example.com/api
```

### 更好的方式 ✅

```plain
https://api.example.com
```

## 參考

- [2.3. RESTful API 最佳实践 - learnku.com](https://learnku.com/courses/go-api/1.19/api-development-best-practices/13475)
