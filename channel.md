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

- Method : `POST`
- Endpoint : `https://api.socialchat.id/public/channel`

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

Response Success:

```
{
  "_id": String,
  "authorizationUrl?": String
}
```

**Detail Response Success**

| Field | Description | Example |
| ----- | ----------- | ------- |
| _id | id of the channel created | 65569e0d670f764888100b48
| authorizationUrl | authorization url for messenger and instagram channels | https://example.com

<br>

Response Error:

```
{
  "statusCode": Number,
  "message": String,
  "originalMessage": String
}
```

**Detail Response Error**

| Field | Description | Example |
| ----- | ----------- | ------- |
| statusCode | code of error | 403
| message | translated message of error | Autentikasi tidak sah, silahkan login
| originalMessage | original of message error | Unauthorized
