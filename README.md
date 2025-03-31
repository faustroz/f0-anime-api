# Wajik Anime API

Wajik Anime API adalah REST API untuk streaming dan mengunduh anime subtitle Indonesia dari berbagai sumber.

## 🎯 Fitur

- Mengambil data anime dari berbagai situs streaming.
- Menyediakan informasi anime terbaru dan ongoing.
- Unofficial API (tidak terkait dengan sumber asli).
- Sumber dapat diperbarui sesuai kebutuhan.

## 🔗 Sumber

API ini bersifat tidak resmi dan tidak berafiliasi dengan sumber yang digunakan. Jika ada sumber lain yang ingin ditambahkan, silakan ajukan permintaan.

| Sumber     | URL                                        |
| ---------- | ------------------------------------------ |
| Otakudesu  | [otakudesu.cloud](https://otakudesu.cloud) |
| Samehadaku | [samehadaku.mba](https://samehadaku.mba)   |

> ⚠️ **Catatan:** Domain sumber dapat berubah sewaktu-waktu. Periksa dan perbarui konfigurasi di `src/configs/animeConfig.ts` jika diperlukan.

---

## 🛠️ Instalasi

### 📌 Prasyarat

- **Node.js** ≥ 20.x

### 🚀 Cara Install

```sh
# Clone repository
git clone https://github.com/wajik45/wajik-anime-api.git

# Masuk ke folder proyek
cd wajik-anime-api

# Install dependensi
npm install

# Jalankan server dalam mode development
npm run dev
```

---

## 🔨 Build & Deploy

```sh
# Build aplikasi
npm run build

# Menjalankan server setelah build
npm start
```

> Server akan berjalan di: **http://localhost:3001**

Jika ingin menghapus sumber tertentu, edit atau hapus:

- **Folder terkait di:** `src/anims/{sumber}`
- **Referensi di:** `src/index.ts` dan `src/controllers/mainController.ts`

---

## 📌 API Routes

| Endpoint  | Deskripsi                                         |
| --------- | ------------------------------------------------- |
| `/sumber` | Mendapatkan daftar anime dari sumber yang dipilih |

### 📌 Contoh Request

```js
(async () => {
  const response = await fetch("http://localhost:3001/otakudesu/ongoing?page=1");
  const result = await response.json();
  console.log(result);
})();
```

### 📌 Contoh Response

```json
{
  "statusCode": 200,
  "statusMessage": "OK",
  "message": "",
  "ok": true,
  "data": {
    "animeList": [
      {
        "title": "Dr. Stone Season 3 Part 2",
        "poster": "https://otakudesu.cloud/wp-content/uploads/2024/01/Dr.-Stone-Season-3-Part-2-Sub-Indo.jpg",
        "episodes": 11,
        "releaseDay": "Jum'at",
        "latestReleaseDate": "05 Jan",
        "animeId": "drstn-s3-p2-sub-indo",
        "href": "/otakudesu/anime/drstn-s3-p2-sub-indo/",
        "otakudesuUrl": "https://otakudesu.cloud/anime/drstn-s3-p2-sub-indo/"
      }
    ]
  },
  "pagination": {
    "currentPage": 1,
    "hasPrevPage": false,
    "prevPage": null,
    "hasNextPage": true,
    "nextPage": 2,
    "totalPages": 4
  }
}
```

---

## 🎨 Contoh UI

Beberapa proyek yang menggunakan API ini:

- [Wajiknime](https://github.com/wajik45/wajiknime/)
- [Zannime](https://github.com/Fauzanmhr/zannime/)

---

## ⚠️ Disclaimer

API ini tidak berafiliasi dengan situs mana pun. Pengguna bertanggung jawab penuh atas penggunaan API ini. Jika ada permintaan takedown dari pemilik konten, repo ini dapat dihentikan kapan saja.

---

## 📩 Kontribusi & Kontak

Jika ingin berkontribusi atau ada saran fitur tambahan, silakan buat **pull request** atau hubungi saya melalui GitHub.

---

**© 2025 Wajik Anime API - Dibuat oleh [wajik45](https://github.com/wajik45/)**
