### API Channel

Channel Type

- linkchat
- webchat
- messenger
- instagram
- telegram
- whatsapp-unofficial

---

##### POST - Add Channel

- Method: `POST`
- Endpoint: `https://api.socialchat.id/public/channel`

**Request Body:**

```
{
  "name": String,
  "phone?": String,
  "type": String,
  "accessToken?": String
}
```

**Detail Request Body:**

| Field | Description | Required | Example |
| ---- | ------------ | -------- | ------- |
| name | for the name of the channel that will be created | true | Socialchat
| phone | for the phone of the channel that will be created | false | 081234567890
| type | type of channel to be created | true | enum of channelType
| accessToken | only used for telegram | false | telegram_token

<br>

Response:

```
{
  "_id": String,
  "authorizationUrl?": String
}
```

**Detail Response**

| Field | Description | Example |
| ----- | ----------- | ------- |
| _id | id of the channel created | 65569e0d670f764888100b48
| authorizationUrl | authorization url for messenger and instagram channels | https://example.com

---

##### GET - Get Channel

- Method: `GET`
- Endpoint: `https://api.socialchat.id/public/channel`

**Request Query**

```
{
  "page": Number,
  "limit": Number,
  "search?": String,
  "type?": String
}
```

| Field | Description | Required | Example |
| ----- | ----------- | -------- | ------- |
| page | request current page | true | 1 |
| limit | limit per page in request | true | 20 (recommedation) |
| search | for searching channel by name | false | Socialchat |
| type | enum of channelType | false | webchat |

<br>

**Response Body**

```
{
  "docs": [
    {
      "_id": String,
      "name": String,
      "channelId": String,
      "channelType": String,
      "isConnected": Boolean,
      "picture": String,
      "status": String,
      "label?": {
        "name": String,
        "phone": String,
      },
      "additionalData?": {
        // for all channel use ai assistant
        "assistantId": String,

        // only for channel whatsapp
        "qrcode": String,

        // only for channel webchat and linkchat
        "shortId": String,
        "hashId": String,
        "isActivePreChat": Boolean,
        "descriptionPreChat": String,
        "isActiveWelcomeMessage": Boolean,
        "welcomeMessage": String,
        "delayWelcomeMessage": Number,
        "websiteUrl": String
      },
      "token?": {
        "accessToken": String
      },
      "createdAt": Date,
      "updatedAt": Date
    },
    ...
  ],
  "totalDocs": Number,
  "limit": Number,
  "totalPages": Number,
  "page": Number,
  "pagingCounter": Number,
  "hasPrevPage": Boolean,
  "hasNextPage": Boolean,
  "prevPage": Boolean,
  "nextPage": Boolean
}
```

**Detail Response**

| Field | Description | Example |
| ----- | ----------- | ------- |
| docs | data from the resulting channel | see Response Body |
| totalDocs | total of docs | 10 |
| limit | limit of request per page | 10 |
| totaPages | total pages of all docs | 2 |
| page | current page | 1 |
| pagingCounter | paging counter of all docs | 1 |
| hasPrevPage | flag of has prev page | false |
| hasNextPage | flag of has next page | false |
| prevPage | flag of has prev page | false |
| nextPage | flag of has next page | false |

---

##### GET - Get One Channel

- Method: `GET`
- Endpoint: `https://api.socialchat.id/public/channel/:id`

**Request Parameter**

```
{
  "id": String
}
```

| Field | Description | Required | Example |
| ----- | ----------- | -------- | ------- |
| id | id of channel | true | 65569e0d670f764888100b48 |

**Response Body**

```
{
  "_id": String,
  "name": String,
  "channelId": String,
  "channelType": String,
  "isConnected": Boolean,
  "picture": String,
  "status": String,
  "label?": {
    "name": String,
    "phone": String,
  },
  "additionalData?": {
    // for all channel use ai assistant
    "assistantId": String,

    // only for channel whatsapp
    "qrcode": String,

    // only for channel webchat and linkchat
    "shortId": String,
    "hashId": String,
    "isActivePreChat": Boolean,
    "descriptionPreChat": String,
    "isActiveWelcomeMessage": Boolean,
    "welcomeMessage": String,
    "delayWelcomeMessage": Number,
    "websiteUrl": String
  },
  "token?": {
    "accessToken": String
  },
  "createdAt": Date,
  "updatedAt": Date
}
```

**Detail Response**

| Field | Description | Example |
| ----- | ----------- | ------- |
| _id | id of channel | 65569e0d670f764888100b48 |
| name | name of channel | Socialchat |
| channelId | generated channelId | 214224552 |
| channelType | type of channel | webchat |
| isConnected | flag of connection channel | true |
| picture | picture of channel | https://image.com |
| status | status of channel | enum of free and premium |
| label | label name and phone of channel | see Response Body |
| additionalData | additional data of channel | see Response Body |
| token | token of channel only for messenger, instagram and telegram | token
| createdAt | date of created channel | 2024-01-22T09:43:34.337Z |
| updatedAt | last date of updated channel | 2024-01-22T09:43:34.337Z |
