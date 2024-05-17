---
title: Channel DTO
---

# Channel DTO Readme

This document provides an overview of the Channel Data Transfer Object (DTO) structure and its various fields. This DTO is used to encapsulate channel-related data in a structured format for use in various applications.

## Channel DTO Structure

### JSON Representation

```js
{
  "id": "37963246-7e9d-4239-a95f-96704c6dcbaa",
  "name": "general",
  "type": "DM",
  "topic": "This is a general channel",
  "nsfw": false,
  "messages": [],
  "bitrate": 64000,
  "userLimit": 10,
  "rateLimitPerUser": 10,
  "recipients": [],
  "createdAt": "2024-05-17T03:15:17.227Z",
  "updatedAt": "2024-05-17T03:15:17.227Z",
  "lastMessageId": "37963246-7e9d-4239-a95f-96704c6dcbaa",
  "serverId": "37963246-7e9d-4239-a95f-96704c6dcbaa",
  "description": "This is a general channel",
  "position": 0,
  "permissionOverwrites": [],
  "ownerId": "37963246-7e9d-4239-a95f-96704c6dcbaa"
}
```

Not all values are required when creating a channel. Some values are optional and can be set to `null` or `undefined`.

### Fields Description

1. **id**: `String`
   - A unique identifier for the channel.
   - Example: `"37963246-7e9d-4239-a95f-96704c6dcbaa"`

2. **name**: `String`
    - The name of the channel.
    - Example: `"general"`

3. **type**: `String`
    - The type of the channel  
      According to the Enum `ChannelType`:
    - Is optional
    - Example: `"DM"`

4. **topic**: `String`
    - The topic of the channel.
    - Is optional
    - Example: `"This is a general channel"`

5. **nsfw**: `Boolean`
    - Indicates if the channel is NSFW (Not Safe For Work).
    - Is optional
    - Example: `false`

6. **messages**: `Array`
    - An array of message objects.
    - Is optional, but will return an empty array if not provided.
    - Example: `[]`

7. **bitrate**: `Number`
    - The bitrate of the channel.
    - Is optional
    - Example: `64000`

8. **userLimit**: `Number`
    - The user limit of the channel.
    - Is optional
    - Example: `10`

9. **rateLimitPerUser**: `Number`
    - The rate limit per user of the channel.
    - Is optional
    - Example: `10`

10. **recipients**: `Array`
    - An array of recipient objects.
    - Is optional, but will return an empty array if not provided (not possible because the owner is always a recipient).
    - Example: `[]`

11. **createdAt**: `String (ISO 8601 format)`
    - The timestamp of when the channel was created.
    - Example: `"2024-05-17T03:15:17.227Z"`

12. **updatedAt**: `String (ISO 8601 format)`
    - The timestamp of the last update to the channel's information.
    - Example: `"2024-05-17T03:15:17.227Z"`

13. **lastMessageId**: `String`
    - The ID of the last message sent in the channel.
    - Is optional
    - Example: `"37963246-7e9d-4239-a95f-96704c6dcbaa"`

14. **serverId**: `String`
    - The ID of the server the channel belongs to.
    - Is optional
    - Example: `"37963246-7e9d-4239-a95f-96704c6dcbaa"`

15. **description**: `String`
    - A description of the channel.
    - Is optional
    - Example: `"This is a general channel"`

16. **position**: `Number`
    - The position of the channel in the server's channel list.
    - Is optional
    - Example: `0`

17. **permissionOverwrites**: `Array`
    - An array of permission overwrite objects.
    - Is optional, but will return an empty array if not provided.
    - Example: `[]`

18. **ownerId**: `String`
    - The ID of the user who owns the channel.
    - Cannot be set at creation. By default, the owner is the user who created the channel.
    - Example: `"37963246-7e9d-4239-a95f-96704c6dcbaa"`

## Additional Information

- The `ChannelType` enum is used to define the type of channel. The possible values are:
  - `TEXT`: A text channel.
  - `VOICE`: A voice channel.
  - `DM`: A direct message channel.
  - `GROUP_DM`: A group direct message channel.
  - `CATEGORY`: A category channel.
  - `NEWS`: A news channel.
  - `STORE`: A store channel.
  - `UNKNOWN`: An unknown channel type.
