---
title: Authentication
sidebar_position: 1
---

The authentication is a crucial part of the application. It allows you to identify the user and to restrict access to some parts of the application.

There is several concepts to understand before diving into the authentication system:
- **access token**: A token that is used to authenticate the user. It is sent in the `Authorization` header of the request.
- **refresh token**: A token that is used to get a new access token when the current one is expired. It is sent in the `Authorization` header of the request.

:::note
All the endpoints answer the same body on success (200).  
The body is the following:
```js
{
  "accessToken": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ",
    "tokenExpiresAt": "2021-01-01T00:00:00.000Z"
  },
  "refreshToken": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ",
    "tokenExpiresAt": "2021-01-01T00:00:00.000Z"
  }
}
```
:::

## Endpoints

In the following, you will find the list of the endpoints that are related to the authentication.

### Register : `POST /auth/register`

This endpoint allows you to register a new user.

:::note
At the moment, the registration is open to everyone. Furthermore, there is no restriction like email or manual validation.  
However, thoses features are planned for the future.
:::

#### Parameters

Takes no parameters.

#### Body

- `username` : The username of the user (string), \*(required)
- `email` : The email of the user (string), \*(required)
- `password` : The password of the user (string), \*(required)

:::warning
- The password must be at least 8 characters long and contain at least one uppercase letter, one lowercase letter, one number, and one special character.
- The username must be unique and can only contain those characters : a-z, A-Z, 0-9, -, ., _, @.
- The email (as the username) must be unique and must be a valid email (e.g. `johndoe@example.com`).
:::

**Body example :**

```js
{
    "username": "johndoe",
    "email": "johndoe@example.com",
    "password": "Password1234?"
}
```

---

### Login : `POST /auth/login`

This endpoint allows you to login a user.

#### Parameters

Takes no parameters.

#### Body

The user can connect with either his username or his email.

- `username` : The username or the email of the user (string), \*(semi-required)
- `email` : The email of the user (string), \*(semi-required)
- `password` : The password of the user (string), \*(required)

**Body examples :**

```js
{
    "username": "johndoe",
    "password": "Password1234?"
}
```

```js
{
    "email": "johndoe@example.com",
    "password": "Password1234?"
}
```

```js
{
    "username": "johndoe",
    "email": "johndoe@example.com",
    "password": "Password1234?"
}
```
---

### Refresh token : `POST /auth/refresh`

This endpoint allows you to get a new access token when the current one is expired.

#### Parameters

Takes no parameters.

#### Body

- `refreshToken` : The refresh token (string), \*(required)

**Body example :**

```js
{
    "refreshToken": "super_token_of_the_turfu"
}
```
