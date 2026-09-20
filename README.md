# IRiT - Ingat Riwayat Transaksi (versi simpel, tanpa build)

Bantu Ibu Rumah Tangga untuk IRIT. Versi ini murni file statis
(HTML/CSS/JS biasa). Tidak perlu Node.js, tidak perlu `npm install`,
tidak perlu GitHub Actions. React dimuat langsung dari CDN di dalam
`index.html`, jadi tinggal upload apa adanya.

## Isi folder

```
index.html              ← seluruh aplikasi (tampilan + logika)
manifest.webmanifest     ← supaya bisa diinstal sebagai aplikasi di HP
sw.js                    ← service worker, supaya bisa dipakai offline
favicon.png
apple-touch-icon.png
icons/
  icon-192.png
  icon-512.png
  icon-maskable-512.png
```

## Cara deploy ke GitHub Pages (tanpa install apa pun)

1. Buat repository baru di github.com (kosong, jangan centang "Add a
   README file").
2. Di halaman repo yang masih kosong, klik **"uploading an existing
   file"** (atau Add file → Upload files).
3. Buka folder hasil ekstrak zip ini, pilih **semua isinya** (index.html,
   manifest.webmanifest, sw.js, favicon.png, apple-touch-icon.png, dan
   folder icons), drag semuanya ke halaman upload GitHub. Klik **Commit
   changes**.
4. Buka **Settings → Pages**. Di bagian **Source**, pilih **Deploy from a
   branch**. Di bawahnya pilih branch **main**, folder **/ (root)**, lalu
   klik **Save**.
5. Tunggu 1–2 menit, GitHub akan menampilkan link seperti
   `https://username.github.io/nama-repo/` — buka link itu, aplikasi
   langsung jalan.

Tidak ada langkah tambahan (tidak perlu bikin file workflow, tidak ada
proses "build" yang bisa gagal). Semua path di dalam file ini pakai path
relatif, jadi otomatis bekerja di alamat apa pun tanpa perlu diatur ulang.

## Instal ke HP

Buka link di atas lewat HP:

- **Android (Chrome):** akan muncul pita "Instal" di bagian atas, atau
  lewat menu titik tiga → Instal aplikasi.
- **iPhone (Safari):** tombol Bagikan → Tambah ke Layar Utama.

## Tentang data

Semua data (dompet, transaksi, toko, daftar harga) disimpan di
`localStorage` browser/perangkat masing-masing — tidak ada server. Kalau
cache/data situs di browser dibersihkan, catatan akan hilang. Ada tombol
"Hapus semua data" di halaman Dompet kalau mau mulai ulang.

## Mengedit aplikasi nanti

Karena tidak ada proses build, semua kode ada di dalam satu file
`index.html` (di dalam tag `<script type="text/babel">`). Untuk
mengembangkan lebih lanjut, edit langsung bagian itu, lalu upload ulang
file `index.html` yang sudah diubah ke GitHub (Add file → Upload files,
GitHub akan otomatis menimpa file lama).
