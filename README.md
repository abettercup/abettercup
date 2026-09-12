# Website A Better Cup

Website statis (HTML/CSS/JS murni, tanpa build tool) untuk A Better Cup.
Siap diupload ke GitHub dan dihosting gratis lewat **GitHub Pages**, dengan
domain `abettercup.id` dan email (`admin@abettercup.id`, `marketing@abettercup.id`)
tetap di Hostinger sesuai rencana yang sudah didiskusikan.

## Isi folder

```
index.html      → Home
about.html      → Tentang Kami
menu.html       → Menu (item &amp; harga resmi)
outlets.html    → Lokasi Outlet
contact.html    → Kontak
assets/
  style.css     → Semua styling (1 file, dipakai semua halaman)
  script.js     → Toggle menu mobile + toggle tema terang/gelap
  img/menu/     → Foto-foto item menu (drink & pastry)
CNAME           → Supaya GitHub Pages mengenali domain abettercup.id
```

Tidak ada proses build — tinggal upload apa adanya.

## ⚠️ Yang masih perlu diisi sebelum go-live

- **Foto outlet** — belum ada foto asli tiap outlet, halaman `outlets.html` masih teks saja. Bisa ditambahkan kalau sudah tersedia.

Logo, foto produk hero, menu & harga resmi, nomor WhatsApp, dan akun Instagram/TikTok sudah memakai data resmi (bukan placeholder lagi).

## Cara upload ke GitHub

```bash
cd abettercup-site
git init
git add .
git commit -m "Initial website A Better Cup"
git branch -M main
git remote add origin https://github.com/<username-atau-organisasi>/<nama-repo>.git
git push -u origin main
```

## Cara mengaktifkan GitHub Pages

1. Buka repo di GitHub → tab **Settings** → menu **Pages** (di sidebar kiri).
2. Pada **Build and deployment → Source**, pilih **Deploy from a branch**.
3. Pilih branch `main` dan folder `/ (root)`, lalu **Save**.
4. Tunggu 1–2 menit, situs akan aktif di `https://<username>.github.io/<nama-repo>/`.

## Menghubungkan domain abettercup.id (dari Hostinger)

Domain tetap dibeli & dikelola di Hostinger, hanya DNS-nya diarahkan ke GitHub Pages,
sesuai rencana: **domain & email di Hostinger, website di GitHub Pages**.

**Di GitHub** (repo → Settings → Pages → Custom domain): masukkan `abettercup.id`
lalu Save. File `CNAME` di repo ini sudah berisi domain tersebut, jadi biasanya
otomatis terisi juga.

**Di Hostinger** (menu DNS / Zone Editor domain `abettercup.id`), tambahkan:

| Tipe  | Nama | Isi                  |
|-------|------|----------------------|
| A     | @    | 185.199.108.153      |
| A     | @    | 185.199.109.153      |
| A     | @    | 185.199.110.153      |
| A     | @    | 185.199.111.153      |
| CNAME | www  | `<username>.github.io.` |

(Empat IP di atas adalah alamat resmi GitHub Pages — cek ulang di dokumentasi
GitHub Pages saat setup, kadang ada penambahan.)

Setelah DNS aktif (bisa 1–24 jam), centang **Enforce HTTPS** di pengaturan
GitHub Pages supaya situs otomatis pakai `https://abettercup.id`.

**Email** (`admin@abettercup.id`, `marketing@abettercup.id`, dst.) tidak perlu
diubah — tetap jalan seperti biasa di Hostinger karena hanya DNS *A record*
website yang dipindah, MX record email dibiarkan seperti semula.

## Menjalankan/preview di komputer sendiri

Tidak perlu install apa pun — cukup buka `index.html` langsung di browser, atau
jalankan server lokal sederhana:

```bash
python3 -m http.server 8000
```

lalu buka `http://localhost:8000`.
