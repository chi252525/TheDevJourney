

## Spring Security 架構圖

        +---------------------------+
        |     Client (瀏覽器/App)  |
        +------------+-------------+
                     |
                     v
        +------------+-------------+
        |   Filter Chain (多個 Filter)  | ← DelegatingFilterProxy
        +------------+-------------+
                     |
        +------------+-------------+
        | UsernamePasswordAuthenticationFilter |
        | JwtAuthenticationFilter（如使用 JWT）|
        | BasicAuthenticationFilter           |
        | SecurityContextPersistenceFilter     |
        | ExceptionTranslationFilter           |
        | FilterSecurityInterceptor           |
        +------------+-------------+
                     |
        +------------+-------------+
        | AuthenticationManager   |
        +------------+-------------+
                     |
        +------------+-------------+
        | AuthenticationProvider  |
        +------------+-------------+
                     |
        +------------+-------------+
        | UserDetailsService       |
        | PasswordEncoder          |
        +--------------------------+


| 組件                            | 說明                                                          |
| ----------------------------- | ----------------------------------------------------------- |
| **DelegatingFilterProxy**     | Spring Boot 會將這個 Filter 委派給 Spring Security 的 Filter Chain。 |
| **Filter Chain**              | 包含多個 Filter，負責處理各種安全邏輯（如認證、權限檢查等）。                          |
| **AuthenticationManager**     | 接收認證請求，將其委派給對應的 `AuthenticationProvider`。                   |
| **AuthenticationProvider**    | 根據傳入的 `Authentication` 對象判斷是否合法（例如 username/password）。      |
| **UserDetailsService**        | 根據使用者名稱載入使用者詳細資訊（通常從資料庫取得）。                                 |
| **PasswordEncoder**           | 驗證密碼是否正確（例如 BCryptPasswordEncoder）。                         |
| **SecurityContextHolder**     | 儲存當前使用者的安全資訊（例如已通過的認證資訊）。                                   |
| **FilterSecurityInterceptor** | 最後一關：處理 URL 權限的存取控制（通常和 `@PreAuthorize` 或 `@Secured` 有關）。   |


```java
// set SecurityContext manually
SecurityContext context = SecurityContextHolder.createEmptyContext();
Authentication authentication = new PreAuthenticatedAuthenticationToken(memberInfo.getId().getMemberId(), null, Collections.emptyList());
context.setAuthentication(authentication);
SecurityContextHolder.setContext(context);
```

```java
SecurityContext context = SecurityContextHolder.getContext();
context.setAuthentication(null);
SecurityContextHolder.clearContext();
```
