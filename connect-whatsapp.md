### Langkah untuk Menghubungkan WhatsApp ke Socialchat

---

1. Buat Request POST ke API

```bash
- Method: `POST`
- Endpoint: `/partner/channel/whatsapp-unofficial`

Body:
{
  "name": "Socialchat",
  "phone": "081234567890"
}
```

2. Jika sukses, maka API akan mengembalikan nilai seperti

```bash
{
  "_id": String
}
```

<br>

3. Gunakan ID dari Response tersebut untuk mendapatkan Data Channel

```bash
- Method: `GET`
- Endpoint: `/partner/channel/:id`

Param:
{
  "id": String
}
```

<br>

4. Server akan mengembalikan nilai seperti

```bash
{
  "_id": "65b37833afe781e84afa001f",
  "name": "",
  "channelId": "",
  "channelType": "linkchat",
  "isConnected": false,
  "picture": "https://ui-avatars.com/api/?name=Socialchat&background=random",
  "label": {
    "name": "Socialchat",
    "phone": "081234567890"
  },
  "createdBy": {
    "_id": "65569e0d670f764888100b48",
    "email": "socialchat@gmail.com"
  },
  "additionalData": {
    "assistantId": "65b37f3c6359d5d7d2bb0a38",
    "qrcode": "base64-image",
    "virtualMachineId": "65b37f3c6359d5d7d2bb0a32"
  },
  "token": {
    "accessToken": "string"
  },
  "createdAt": "2024-01-30T03:58:24.369Z",
  "updatedAt": "2024-01-30T03:58:24.369Z"
}
```

<br>

5. Tampilkan Kode QR yang diambil dari kolom `additionalData.qrcode`, kolom tersebut berupa text base64 gambar

<br>

6. Gunakan Request Interval ke API `GET` `/partner/channel/:id` untuk melakukan Refresh Kode QR dan status `isConnected`
