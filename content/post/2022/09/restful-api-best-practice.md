---
title: "瞭解 RESTful API 最佳實踐"
description:
date: 2022-09-07T22:56:18+08:00
image:
math:
license:
hidden: false
comments: true
draft: true
categories:
  - WebsiteDevelopment
tags:
  - RESTful
  - API
---

<!-- Stub
## {Title}

### 不好的方式 ❌

### 更好的方式 ✅
-->

## 大綱

1. 應避免 HTTP 80 Port
2. API Server 域名設計

## 說明

最近在學習 Golang 開發，遇到教學資源介紹 RESTful API 最佳實踐方式，因此更深入的瞭解文件中所提到的知識及改善方式，如果有誤也歡迎留言提出指正。

## 應避免 HTTP 80 Port

HTTP 是明文傳輸，由於傳輸過程有可能被篡改或是竊取資料，例如: 信用卡資訊、帳號密碼 ... 等，所以其實相當危險，因此應該要關閉 HTTP 80 Port 的設置。

### 不好的方式 ❌

Client 端請求 HTTP 80 Port 時，我們都會再導向至 HTTPS 443 Port。

### 更好的方式 ✅

應該直接返回錯誤。

## API Server 域名設計

- 彈性化調整 Http Server 設置
- 無 Cookie 共享
  - 需特別注意子網域可以修改或覆改母網域的 Cookie
- CDN 加速呼叫
  - 加速原理可參考 [Huawei. CDN 的加速原理是什么？](https://www.huaweicloud.com/zhishi/cdn001.html)

### 不好的方式 ❌

```plain
https://www.example.com/api
```

### 更好的方式 ✅

```plain
https://api.example.com
```

## API 版本控制

目前主要分兩種 API 版本控制

1. URI 版本控制
2. Header Accept 版本控制

總結來說，只要團隊共同定義好如何 API 版本控制，我覺得使用哪一種應該都沒關係。

> 補充: [Lokesh Gupta. REST API Versioning](https://restfulapi.net/versioning/) 也有網友在下面使用 `Content-Type` 字段來實作 Header Accept 版本控制，這部份可根據團隊來定義。

### URI 版本控制

```plain
https://api.example.com/v1

or

https://apiv1.example.com
```

### Header Accept 版本控制

使用`Header Accept 版本控制`可以讓 URL 更簡潔、乾淨！

```plain
# Header
Accept: application/vnd.github.v3+json
```

## URL 定位資源

## 參考

- [Summer. RESTful API 最佳实践](https://learnku.com/courses/go-api/1.19/api-development-best-practices/13475)
- [Jayden Lin. 網站安全 🔒 Same Origin Policy 同源政策 ! 一切安全的基礎](https://medium.com/%E7%A8%8B%E5%BC%8F%E7%8C%BF%E5%90%83%E9%A6%99%E8%95%89/same-origin-policy-%E5%90%8C%E6%BA%90%E6%94%BF%E7%AD%96-%E4%B8%80%E5%88%87%E5%AE%89%E5%85%A8%E7%9A%84%E5%9F%BA%E7%A4%8E-36432565a226)
- [Github REST API](https://docs.github.com/en/rest)
- [Huawei. CDN 的加速原理是什么？](https://www.huaweicloud.com/zhishi/cdn001.html)
- [Lokesh Gupta. REST API Versioning](https://restfulapi.net/versioning/)
