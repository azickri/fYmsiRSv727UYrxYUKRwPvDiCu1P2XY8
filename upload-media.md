### Authorization

- App ID : app-id
- Secret Key : secret-key
- Authorization : Base64(appId_secretKey)

<br>

**Example Generate Authorization (NodeJS)**

```
function generateHeaderAuthorization(appId, secretKey) {
  return Buffer.from(`${appId}_${secretKey}`).toString('base64')
}
```

<br>

**Exammple with Package Axios**

```
const appId = "appId"
const secretKey = "secretKey"
const authorization = generateHeaderAuthorization(appId, secretKey)
const baseUrl = "https://bucket.manypage.id/chat/public"

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

**Example Response Success**

```
{
  "url": String,
  "path": String,
  "sizeKB": Number
}
```

**Example Response Error**

```
{
  "statusCode": Number,
  "message": String
}
```
