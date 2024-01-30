### Authorization

- App ID : app-id
- Secret Key : secret-key
- Authorization : Base64(appId_secretKey)

<br>

**Contoh Pembuatan Otorisasi (NodeJS)**

```
function generateHeaderAuthorization(appId, secretKey) {
  return Buffer.from(`${appId}_${secretKey}`).toString('base64')
}
```

<br>

**Contoh dengan Axios**

```
const appId = "appId"
const secretKey = "secretKey"
const authorization = generateHeaderAuthorization(appId, secretKey)
const baseUrl = "https://bucket.manypage.id/chat/partner"

const formData = FormData()
formData.append('file', file)

axios.post(
  baseUrl,
  formData,
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

---

**Contoh Response Berhasil**

```
{
  "url": String,
  "path": String,
  "sizeKB": Number
}
```

**Contoh Response Error**

```
{
  "statusCode": Number,
  "message": String
}
```
