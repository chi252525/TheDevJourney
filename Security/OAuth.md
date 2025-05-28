
# OAUTH

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
