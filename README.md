# k8s-go

## Description

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;這是一個自己實作分散式系統的專案，算是對於過去的工作經驗的一次總結，目前已經先把主要架構想好，然後利用時間將每一個 Service 慢慢的建立起來。預計是先將 Service 先各自開發完成獨立的專案，再改寫微服務的版本再部署，最後開發前端 APP 做收尾。

### Feature

- 面向使用者的部分，使用者在登入時需要先經過 Oauth 驗證，確認具有權限後取得 jwt token，再和 API server 取得資料。
- 面向管理者的部分，則是有權限系統、Oauth 管理系統以及使用者管理系統。

### Target

1. Go with Gin framework as API server
2. Oauth 2.0 authorization code flow
3. Oauth scope management
4. Casbin authorization library
5. Docker + Kubernetes
6. Batch deployment
7. Service monitoring

## Architecture

![arch](./images/architecture.png)

## Repositories

### For Client

| Service                    | Repository                                                       |
| -------------------------- | ---------------------------------------------------------------- |
| Address Book Server        | [address-book-go](https://github.com/pinkeyu7/address-book-go)   |
| Oauth Authorization Server | [oauth2-server-go](https://github.com/pinkeyu7/oauth2-server-go) |
| User Server                | -                                                                |
| Client App                 | -                                                                |

### For Admin

| Service                 | Repository                                                         |
| ----------------------- | ------------------------------------------------------------------ |
| Admin Account Server    | [casbin-auth-go](https://github.com/pinkeyu7/casbin-auth-go)       |
| Oauth Management Server | [oauth2-console-go](https://github.com/pinkeyu7/oauth2-console-go) |
| User Management Server  | -                                                                  |
| Admin App               | -                                                                  |

## Data Storage

| Service      | MySQL Database | Cache |
| ------------ | -------------- | :---: |
| Address Book | address_book   |   O   |
| Oauth        | oauth_service  |   O   |
| User         | user_service   |   O   |
| Admin        | admin_service  |   X   |
