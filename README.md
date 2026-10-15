# Catatan Keuangan (PWA)

Aplikasi pencatatan keuangan bergaya BSI: pemasukan, pengeluaran, banyak dompet, grafik, statistik, input suara, dan scan foto bon. Semua data tersimpan di perangkat (localStorage), tanpa server.

## Isi folder
- `index.html` : seluruh aplikasi
- `manifest.webmanifest` : identitas aplikasi agar bisa diinstal
- `sw.js` : service worker (cache agar bisa dibuka offline)
- `icons/` : ikon aplikasi

## Pasang di GitHub Pages
1. Buat repository baru di GitHub (misal `keuangan`), publik.
2. Upload semua file dan folder `icons` ke root repository (Add file > Upload files).
3. Buka Settings > Pages > Source: **Deploy from a branch**, Branch: **main**, folder **/ (root)**, lalu Save.
4. Tunggu 1-2 menit. Alamatnya: `https://USERNAME.github.io/keuangan/`

## Instal di HP
- **Android (Chrome):** buka alamat di atas, menu titik tiga > **Instal aplikasi** / **Tambahkan ke layar utama**.
- **iPhone (Safari):** buka alamat di atas, tombol Bagikan > **Tambah ke Layar Utama**.

## Catatan
- Harus lewat HTTPS (GitHub Pages sudah HTTPS). Suara dan instalasi tidak jalan jika file dibuka langsung dari penyimpanan HP.
- **Suara:** memakai pengenalan suara browser (Chrome Android paling lancar; di iPhone dukungannya terbatas). Izinkan mikrofon.
- **Scan bon:** dibaca di perangkat dengan Tesseract.js. Pemakaian pertama perlu internet untuk mengunduh data bahasa Indonesia. Selalu periksa total dan tanggal sebelum menyimpan, karena hasil OCR bergantung pada kualitas foto.
- Data tidak tersinkron antar perangkat. Jika memperbarui aplikasi, naikkan nomor `CACHE` di `sw.js` (misal `keuangan-v2`) agar perangkat memuat versi baru.
