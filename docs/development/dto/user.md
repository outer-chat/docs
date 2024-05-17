---
title: User DTO
---

# User DTO Readme

This document provides an overview of the User Data Transfer Object (DTO) structure and its various fields. This DTO is used to encapsulate user-related data in a structured format for use in various applications.

## User DTO Structure

### JSON Representation

```js
{
  "id": "37963246-7e9d-4239-a95f-96704c6dcbaa",
  "email": "example@example.com",
  "username": "my_super_username",
  "createdAt": "2021-01-01T00:00:00.000Z",
  "updatedAt": "2021-01-01T00:00:00.000Z",
  "avatar": "Byte array",
  "banner": "Byte array",
  "bannerColor": "#ffffff",
  "bio": "I am a software developer",
  "roles": [
    "USER"
  ],
  "friends": [
    "friend1",
    "friend2"
  ],
  "servers": [
    "server1",
    "server2"
  ],
  "channels": [
    "channel1",
    "channel2"
  ]
}
```

### Fields Description

1. **id**: `String`
   - A unique identifier for the user.
   - Example: `"37963246-7e9d-4239-a95f-96704c6dcbaa"`

2. **email**: `String`
   - The user's email address.
   - Example: `"example@example.com"`

3. **username**: `String`
   - The user's chosen username.
   - Example: `"my_super_username"`

4. **createdAt**: `String (ISO 8601 format)`
   - The timestamp of when the user was created.
   - Example: `"2021-01-01T00:00:00.000Z"`

5. **updatedAt**: `String (ISO 8601 format)`
   - The timestamp of the last update to the user's information.
   - Example: `"2021-01-01T00:00:00.000Z"`

6. **avatar**: `Byte array`
   - The user's avatar image in byte array format.

7. **banner**: `Byte array`
   - The user's banner image in byte array format.

8. **bannerColor**: `String (Hex color code)`
   - The hex color code for the user's banner background.
   - Example: `"#ffffff"`

9. **bio**: `String`
   - A short biography or description of the user.
   - Example: `"I am a software developer"`

10. **roles**: `Array of Strings`
    - The roles assigned to the user.  
      Possible values: `USER`, `ADMIN` (will be extended in the future).
    - Example: `["USER"]`

11. **friends**: `Many-to-Many Relationship`
    - An array of user IDs representing the user's friends.
    - Example: `["friend1", "friend2"]`

12. **servers**: `Many-to-Many Relationship`
    - An array of server IDs representing the servers the user is a member of.
    - Example: `["server1", "server2"]`

13. **channels**: `Many-to-Many Relationship`
    - An array of channel IDs representing the channels the user has access to.
    - Example: `["channel1", "channel2"]`
