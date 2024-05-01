---
title: 從輸入網址列到畫面出現經歷了哪些過程？
description: 當你在瀏覽器中輸入一個網址，然後看到網頁內容，這個過程經歷了多個技術階段，包括網絡通信、網頁解析和呈現等。
slug: from-a-URL-to-a-webpage
date: 2024-04-30 22:00:00+0000
image: cover.jpg
categories:
    - frontend
tags:
    - domain
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

## 輸入網址和域名解析
- 當你在瀏覽器中輸入一個網址（例如 `www.example.com`），瀏覽器首先會進行域名解析，將域名轉換成對應的 IP 地址。
- 瀏覽器會查詢 DNS（域名系統）服務器，以獲取域名對應的 IP 地址。

## 建立網絡連接
- 瀏覽器獲得服務器的 IP 地址後，會使用 TCP 建立網絡連接。
- 如果網址是 HTTPS 協議，還需要建立 TLS（傳輸層安全協議）加密連接，以確保通信的安全性。

## 發送 HTTP 請求
- 連接建立後，瀏覽器向服務器發送 HTTP 請求，通常是 GET 請求。
- HTTP 請求包含標頭、查詢參數、Cookie 和其他必要信息。

## 服務器處理請求
- 服務器接收到 HTTP 請求後，會根據請求內容進行處理，例如查找資源、執行後端代碼、查詢數據庫等。
- 一旦處理完畢，服務器會生成 HTTP 回應，通常包括狀態代碼、回應標頭和可能的回應體（例如 HTML 文件）。

## 接收和處理 HTTP 回應
- 瀏覽器接收到 HTTP 回應後，檢查狀態代碼和標頭。
- 如果回應有效，瀏覽器將進行進一步的處理。若需要其他資源，如 CSS、JavaScript 或圖片，可能會發送額外的請求。

## 解析和呈現網頁
- 瀏覽器開始解析 HTML 文件，構建 DOM（文檔對象模型）。
- 在解析過程中，瀏覽器也會加載和解析 CSS 和 JavaScript。
- 最終，瀏覽器根據 DOM 和 CSS 規則渲染網頁。

## 執行 JavaScript 和用戶交互
- 在網頁渲染後，瀏覽器會執行 JavaScript 代碼。
- 這可能導致 DOM 的變化、進一步的網絡請求，以及其他用戶交互。
- 瀏覽器將根據用戶交互（如點擊和滾動）更新網頁。

## 維護和持續更新
- 當網頁顯示後，瀏覽器持續處理用戶交互。
- 此外，瀏覽器可能會使用 AJAX 或 WebSocket 與服務器持續通信，確保網頁內容動態更新。


> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)