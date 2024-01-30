### Langkah untuk Menghubungkan Instagram ke Socialchat

---

1. Pastikan sudah melakukan Set `callbackInstagramUrl` di API Partner, jika belum maka ubah terlebih dahulu.

```bash
- Method: `PUT`
- Endpoint: '/partner'

Body:
{
  "webhookChatUrl": String,
  "callbackMessengerUrl": String,
  "callbackInstagramUrl": String
}
```

<br>

2. Request ke API `GET` `/partner/channel/instagram/authorize` untuk mendapatkan URL Otorisasi

```bash
- Method: "GET"
- Endpoint: `/partner/channel/instagram/authorize`
```

<br>

3. Server akan mengembalikan nilai seperti

```bash
{
  "url": String
}
```

<br>

4. Gunakan URL dari Response Server untuk melakukan pengalihan URL

<br>

5. Izinkan Semua Halaman dan Instagram di Halaman Otorisasi Facebook untuk kelancaran

<br>

6. Setelah berhasil, maka URL akan dialihkan ke url callback yang sudah diset tadi dan ada parameter tambahan yaitu token. Seperti berikut: `https://app.com/callback/instagram?token=token...`

<br>

7. Setelah dialihkan, buat Request ke API `GET` `/partner/channel/instagram/account` untuk mendapatkan List Instagram yang ingin dihubungkan

```bash
- Method: `GET`
- Endpoint: `/partner/channel/instagram/account`

Query:
{
  "token": String,
  "nextOffset": String
}
```

<br>

8. Server akan mengembalikan nilai seperti

```bash
{
  "docs": [
    {
      "name": "Socialchat",
      "channelId": "11233412",
      "picture": "https://cdn.facebook.com/image..."
    }
  ],
  "hasNextPage": false,
  "nextOffset": "0jHNnNKMFZAccKpZC8smLrmOKlVUNrV3s7Ok..."
}
```

<br>

9. Selanjutnya, untuk menambahkan Instagram lakukan Request ke API `POST` `/partner/channel/instagram`

```bash
- Method: `POST`
- Endpoint: `/partner/channel/instagram`

Body:
{
  "channelId": String,
  "token": String
}
```

<br>

10. Untuk melakukan aksi `Reconnect`, cukup Kirimkan kolom \_id dari API `GET` `/partner/channel` dan token yang dihasilkan dari URL Otorisasi

```bash
- Method: `POST`
- Endpoint: `/partner/channel/instagram/:id`

Param:
{
  "id": String
}

Body:
{
  "token": String
}
```
