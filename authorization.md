### Authorization

- App ID : app-id
- Secret Key : secret-key
- Authorization : Base64(appId_secretKey)

<br>

**Contoh Mendapatkan Header Otorisasi (NodeJS)**

```
function generateHeaderAuthorization(appId, secretKey) {
  return Buffer.from(`${appId}_${secretKey}`).toString('base64')
}
```

<br>

**Contoh Request dengan Axios**

```
const appId = "appId"
const secretKey = "secretKey"
const authorization = generateHeaderAuthorization(appId, secretKey)
const baseUrl = "https://api.socialchat.id/public/channel"

axios.post(
  baseUrl,
  {
    "name": "Socialchat",
    "phone": "081234567890",
    "type": "webchat",
    "accessToken": ""
  },
  {
    headers: {
      "authorization": authorization
    }
  }
).then((response) => {
  console.log('success request api', response.data)
}).catch((error) => {
  console.log('error request api', error.response?.data)
})

```

<br>

**Contoh Response Error**

Response Error:

```
{
  "statusCode": Number,
  "message": String,
  "originalMessage": String
}
```

**Detail Response Error**

| KOlom           | Deskripsi                               | Contoh                                |
| --------------- | --------------------------------------- | ------------------------------------- |
| statusCode      | http status dari error                  | 403                                   |
| message         | terjemahan dari pesan original          | Autentikasi tidak sah, silahkan login |
| originalMessage | pesan original, biasanya bahasa inggris | Unauthorized                          |
