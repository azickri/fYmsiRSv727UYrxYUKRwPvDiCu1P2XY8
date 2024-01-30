### Langkah untuk Menghubungkan Telegram ke Socialchat

---

1. Pastikan sudah membuat BOT di Telegram dan sudah menyalin Token yang dihasilkan dari Telegram

<br>

2. Buat Request ke API

```bash
- Method: `POST`
- Endpoint: `/partner/channel/telegram`

Body:
{
  "token": String
}
```

<br>

3. Jika token tidak valid, maka Server akan mengembalikan error yang menyatakan bahwa token tidak valid. Lalu, jika token valid maka Server akan mengembalikan nilai seperti

```
{
  "_id": String
}
```

<br>

4. Dengan begitu, Telegram sudah terhubung ke Socialchat.

<br>

5. Untuk melakukan aksi _Reconnect_ Buat Request ke API

```bash
- Method: `POST`
- Endpoint: `/partner/channel/telegram/:id`

Param:
{
  "id": String
}

Body:
{
  "token": String
}
```

<br>

6. Jika token valid tetapi akunnya berbeda, maka Server akan mengembalikan error
