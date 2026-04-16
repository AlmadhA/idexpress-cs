# 🚀 ID Express Customer Service — GitHub Pages

Website Customer Service ID Express berbasis GitHub Pages. Tanpa backend, tanpa biaya server.

---

## 📋 Fitur

- **Customer** bisa komplain tanpa login → dapat **kode E-Ticket unik**
- **Cek status tiket** kapan saja dengan kode E-Ticket
- **Admin** bisa login, lihat semua tiket, **balas**, dan update status
- Percakapan seperti **chat** antara customer dan admin
- Warna brand **ID Express** (Merah #C8231B)

---

## 🗂️ Struktur File

```
├── index.html       → Halaman buat komplain (customer)
├── cek-tiket.html   → Halaman cek status E-Ticket (customer)
├── admin.html       → Panel admin (CS ID Express)
└── README.md
```

---

## ⚙️ Cara Setup (GitHub Pages)

### Langkah 1: Buat Repository Baru

1. Login ke [github.com](https://github.com)
2. Klik **New Repository**
3. Nama repo: `idexpress-cs` (untuk website) — ini akan jadi alamat website
4. Set ke **Public**
5. Klik **Create Repository**

### Langkah 2: Buat Repository Tiket (Terpisah)

1. Buat repository kedua untuk menyimpan tiket
2. Nama repo: `idexpress-cs-tickets`
3. Set ke **Private** (agar data customer tidak publik)

### Langkah 3: Buat GitHub Personal Access Token

1. Pergi ke **Settings** → **Developer settings** → **Personal access tokens** → **Fine-grained tokens**
2. Klik **Generate new token**
3. Pilih repository: `idexpress-cs-tickets`
4. Beri izin:
   - **Issues**: Read & Write
   - **Metadata**: Read
5. Copy token yang dihasilkan

### Langkah 4: Update Konfigurasi di File HTML

Di setiap file (`index.html`, `cek-tiket.html`, `admin.html`), ganti:

```javascript
const GITHUB_TOKEN = 'YOUR_GITHUB_TOKEN_HERE';   // ← Token Anda
const GITHUB_OWNER = 'YOUR_GITHUB_USERNAME';      // ← Username GitHub Anda
const GITHUB_REPO  = 'idexpress-cs-tickets';      // ← Nama repo tiket
```

### Langkah 5: Upload ke GitHub Pages

1. Upload semua file ke repository `idexpress-cs`
2. Pergi ke **Settings** → **Pages**
3. Source: pilih **main branch** → folder **/ (root)**
4. Klik **Save**
5. Website akan live di: `https://USERNAME.github.io/idexpress-cs`

---

## 🔐 Kredensial Admin (Default)

```
Username : admin
Password : idexpress2024
```

**⚠️ Ganti password** di file `admin.html` sebelum deploy:

```javascript
const ADMIN_USER = 'admin';
const ADMIN_PASS = 'idexpress2024';  // ← Ganti ini!
```

---

## 💡 Cara Kerja

### Mode Demo (Tanpa GitHub API)
Jika GitHub Token belum dikonfigurasi, semua data disimpan di **localStorage browser**. Cocok untuk testing lokal.

### Mode Produksi (Dengan GitHub API)
Setiap tiket komplain akan membuat **GitHub Issue** baru di repo `idexpress-cs-tickets`. Balasan admin tersimpan sebagai **Comments** di Issue tersebut. Customer bisa melihat balasan via halaman Cek E-Ticket.

---

## 📱 Halaman & URL

| Halaman | URL | Untuk |
|---------|-----|-------|
| Buat Komplain | `/index.html` | Customer |
| Cek E-Ticket | `/cek-tiket.html` | Customer |
| Panel Admin | `/admin.html` | Tim CS ID Express |

---

## 🎨 Warna Brand

| Warna | Hex |
|-------|-----|
| Merah utama | `#C8231B` |
| Merah gelap | `#9E1A14` |
| Putih | `#FFFFFF` |

---

## 📞 Support

Dibuat untuk **ID Express Customer Service Team**.
