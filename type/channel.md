#### TYPE CHANNEL

```
{
  "_id": String,
  "name": String,
  "channelId": String,
  "channelType": String,
  "isConnected": Boolean,
  "isTimeout": Boolean,
  "picture": String,
  "status": String,
  "label?": {
    "name": String,
    "phone": String
  },
  "createdBy": {
    "_id": String,
    "email": String
  },
  "additionalData?": {
    "assistantId": String,
    "shortId": String,
    "hashId": String,
    "isActivePreChat": Boolean,
    "decriptionPreChat": String,
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

<br>

#### Deskripsi Kolom

| Kolom                                 | Deskripsi                                                                                              |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| \_id                                  | id unik dari database                                                                                  |
| name                                  | nama channel                                                                                           |
| channelId                             | id dari masing-masing channel tergantung tipenya                                                       |
| channelType                           | tanda untuk tipe tiap channel (linkchat, webchat, messenger, instagram, telegram, whatsapp-unofficial) |
| isConnected                           | tanda untuk channel apakah terhubung atau terputus                                                     |
| isTimeout                             | tanda untuk channel whatsapp, apakah timeout saat melakukan generate qrcode                            |
| picture                               | url gambar channel                                                                                     |
| status                                | tipe status untuk channel (free, premium)                                                              |
| label.name                            | nama yang diinput oleh pengguna                                                                        |
| label.phone                           | nomor hp yang diinput oleh pengguna                                                                    |
| additionalData.assistantId            | id untuk asisten jika memakai fitur AI Assistant                                                       |
| additionalData.shortId                | shortId untuk tipe channel linkchat                                                                    |
| additionalData.hashId                 | hashId untuk tipe channel linkchat dan webchat                                                         |
| additionalData.isActivePreChat        | tanda bahwa linkchat atau webchat mengaktifkan Pre Chat                                                |
| additionalData.descriptionPreChat     | deskripsi untuk pre chat                                                                               |
| additionalData.isActiveWelcomeMessage | tanda bahwa webchat mengaktifkan pesan selamat datang                                                  |
| additionalData.welcomeMessage         | teks untuk pesan selamat datang                                                                        |
| additionalData.delayWelcomeMessage    | penundaan munculnya pesan selamat datang (dalam detik)                                                 |
| additionalData.websiteUrl             | pengenal URL Website untuk webchat                                                                     |
