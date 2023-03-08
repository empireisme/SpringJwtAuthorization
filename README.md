# SpringJwtAuthorization
 
## 專案技術

1. mysql
2. SpringSecurity with jwt token

我們將在jwt token 當中儲存 role 腳色訊息

## 前置作業

1. clone到本地端後，先去更改application.properties

```
spring.datasource.url=jdbc:mysql://localhost:3306/productsdb?serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=12111211
```

將對應的帳密換成你自己的帳密，並且在DB創建一個資料庫名稱為 productsdb
建資料庫就好，不需要建立表，表會自動產生

2. 在你的IDE當中去執行 RoleRepositoryTests 這將會幫你在roles資料庫當中建立對應的腳色

![image](https://user-images.githubusercontent.com/27859973/223651578-a011a100-b36c-42b7-a497-00bd1ee7738a.png)

3. 執行 UserApiTests 這將會讓你可以 創建一個使用者

他的帳號是 empire@gmail.com
他的密碼是 mikechen

4. 在users_roles當中去指定每個user他的腳色

![image](https://user-images.githubusercontent.com/27859973/223652310-47c26f33-21d3-4dc1-8949-8df356d46dfa.png)

5. 目前的設計邏輯是 只有editor可以 add products 其餘的人只能get Product

## 使用順序



