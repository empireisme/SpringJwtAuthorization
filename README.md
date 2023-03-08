# SpringJwtAuthorization (for 工一科技)
 
## 專案技術

1. mysql
2. SpringSecurity with jwt token

我們將在 accessToken token 當中儲存 role 腳色訊息

此專案的目的是為了展示 RBAC Model

我們有兩種腳色

一個是consumer
另外一個是editor

consumer and editor 都可以獲取商品
但是只有editor 可以 新增商品

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

他的帳號是 mike@gmail.com
他的密碼是 mike345

4. 在users_roles當中去指定每個user他的腳色

![image](https://user-images.githubusercontent.com/27859973/223652310-47c26f33-21d3-4dc1-8949-8df356d46dfa.png)

5. 目前的設計邏輯是 只有editor可以 add products 其餘的人只能get Product

## 使用順序

1. 使用postman 來登入獲取access token
post
localhost:8080/auth/login

{
    "email":"mike@gmail.com",
    "password":"mike345"
}

![image](https://user-images.githubusercontent.com/27859973/223655415-1a45b01c-7e13-4696-aefb-fc48f3cc2836.png)

2. 獲取商品，你可以先在資料庫當中建立一些假的商品

將access token 放在 Token中，圖片有很詳細的解釋

Get
localhost:8080/products

![image](https://user-images.githubusercontent.com/27859973/223656418-6333bb7e-a4ce-4b83-b730-26e7051ef556.png)

3. 新增商品

post
localhost:8080/products

一樣記得先放入token

![image](https://user-images.githubusercontent.com/27859973/223657145-1e0dbcd6-e0ab-41bc-a44f-204007485d6b.png)

在這裡 我們可以發現 因為 我將mike@gmail.com的權限設定為consumer，所以他只能夠看到商品，不能夠新增商品








