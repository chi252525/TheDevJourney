
# OAUTH

當你想讓一個外部應用程式（比如說一個社交媒體 App 或是網站）可以使用你在其他平台上的資料時，OAuth2 就像是一把鑰匙，幫助你授權這個應用程式去取得你的資源，例如你的照片、個人資料或其他內容。這個鑰匙可以讓應用程式取得限定範圍內的資訊，同時不需要直接分享你的帳號密碼。OAuth2 讓你可以控制和限制應用程式對於你資料的存取權限，確保安全性和隱私。

樂天例子：
mms —> RMS (Google)
client 授權 mms 使用 RMS 登入到 mms

```
sequenceDiagram
    participant User as User
    participant Frontend as Frontend App
    participant Backend as Backend Server
    participant Google as Google OAuth API

    User ->> Frontend: 點擊 "Sign in with Google"
    Frontend ->> Google: 請求 OAuth 授權碼 (Authorization Code Flow)
    Google ->> User: 顯示 Google 登入頁面
    User ->> Google: 提供 Google 賬號認證及授權
    Google ->> Frontend: 返回授權碼 (Authorization Code)
    Frontend ->> Backend: 發送授權碼
    Backend ->> Google: 使用授權碼請求訪問令牌 (Access Token)
    Google ->> Backend: 返回訪問令牌 (Access Token) 和刷新令牌 (Refresh Token)
    Backend ->> Google: 使用訪問令牌請求用戶信息
    Google ->> Backend: 返回用戶信息 (如名稱、郵箱)
    Backend ->> Frontend: 返回用戶會話或 JWT
    Frontend ->> User: 顯示登入成功並重定向至主頁
```
[串接第三方登入實作](
https://fufong79570.medium.com/%E4%B8%B2%E6%8E%A5google-%E7%AC%AC%E4%B8%89%E6%96%B9%E7%99%BB%E5%85%A5-%E5%AF%A6%E4%BD%9C-node-js-b750821cde90)


