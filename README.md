# PANDUAN FIREBASE RULES & DEPLOYMENT — DOOMINIKS STORE

## 📋 RULES YANG HARUS KAMU GANTI

### 1. Firestore Rules (Paling Penting!)
Buka: **Firebase Console → Firestore Database → Rules**

Copy-paste isi file `firestore.rules` ke sana lalu klik **Publish**.

### 2. Realtime Database Rules
Buka: **Firebase Console → Realtime Database → Rules**

Copy-paste isi file `database.rules.json` ke sana lalu klik **Publish**.

---

## 🔒 PENJELASAN RULES

| Koleksi | Read | Write | Keterangan |
|---------|------|-------|-----------|
| `products` | ✅ Public | ✅ True | Produk bisa dilihat semua orang |
| `users` | ✅ True | ✅ True | Butuh untuk login/registrasi |
| `orders` | ✅ True | ✅ True | Customer buat order, owner update status |
| `transactions` | ✅ True | ✅ True | Topup request dari customer |
| `reviews` | ✅ True | ✅ True | Ulasan produk |
| `settings` | ✅ True | ✅ True | Konfigurasi toko & payment |
| `catalogs` | ✅ True | ✅ True | Katalog game |
| `discounts` | ✅ True | ✅ True | Kode diskon |
| `komplain` | ✅ True | ✅ True | Komplain customer |
| `user_notifs` | ✅ True | ✅ True | Notifikasi real-time customer |

---

## ⚠️ CATATAN KEAMANAN PENTING

1. **Password Owner** — Ubah username dan password owner di:
   `Owner Panel → Settings → Akun Owner`
   Jangan pakai password default!

2. **Webhook URL** — Simpan webhook URL Discord kamu hanya di Firebase settings, bukan di-share ke siapapun.

3. **API Key Firebase** — API Key yang ada di code adalah PUBLIC key, ini normal dan aman untuk Firebase. Yang penting adalah Rules yang benar.

4. **Upgrade Rules (Opsional)** — Jika kamu mau keamanan lebih ketat, tambahkan Firebase Authentication dan update rules untuk cek `request.auth.uid`.

---

## 🚀 CARA DEPLOY KE GITHUB PAGES

1. Upload file `index.html` ke repository GitHub kamu
2. Buka Settings → Pages → Source: `main` branch → root folder
3. Tunggu beberapa menit, website live di: `https://username.github.io/repo-name`

## 📁 STRUKTUR FOLDER GITHUB (Opsional - untuk gambar)

Jika kamu mau upload gambar payment method secara manual:
```
/images/
  dana.png       → Logo DANA
  bca.png        → Logo BCA
  seabank.png    → Logo SeaBank
  qris.png       → Logo QRIS
```

Lalu update URL di code dari Wikipedia ke: `./images/dana.png` dll.

---

## 🔔 FITUR BARU YANG DITAMBAHKAN

### Fitur Baru:
- ✅ Hero Slider — gambar game berputar otomatis di homepage
- ✅ Logo + Nama Website di bawah slider
- ✅ Kategori Game sebagai pill buttons yang mudah diklik
- ✅ Push Notification ke HP customer (popup browser)
- ✅ Notif real-time Firestore saat status order diupdate owner
- ✅ Webhook Discord dengan embed berbeda untuk Topup (warna emas)
- ✅ Webhook untuk Review baru
- ✅ Redirect otomatis ke halaman Orders setelah pembayaran

### Perbaikan:
- ✅ Upload gambar produk: drag & drop + notifikasi sukses
- ✅ Owner Panel: tabs dengan icon yang lebih rapi
- ✅ Payment methods: struktur gambar yang lebih baik dengan checkmark saat terpilih
- ✅ Topup: embed Discord berbeda (warna emas/kuning)
