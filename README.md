# k8s-go

## Description

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This is a project for summarizing working experience before. I develop each service individually
in my free time. After all service is done, I’ll refactor these services to fix micro system architecture.

### Feature

- For client, user can use api after loging in by oauth verfication and getting jwt token.
- For admin, maneger can manage admin manager's permissions, users, oauth clients and scopes via admin console.

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
