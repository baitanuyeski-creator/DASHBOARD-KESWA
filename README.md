# E-PUSBONAT — Dashboard Kesehatan Jiwa

Dashboard responsif untuk monitoring Kesehatan Jiwa Puskesmas Naibonat.

## Fitur
- Dashboard infografis responsif.
- Pemilihan bulan.
- Edit data langsung melalui antarmuka.
- Penyimpanan browser menggunakan localStorage.
- Impor dan ekspor JSON.
- Tampilan cetak.

## Menjalankan lokal
Python 3 diperlukan.

```bash
python3 -m http.server 8000
```

Buka http://127.0.0.1:8000

## Hosting GitHub Pages
Unggah `index.html` dan `README.md` ke repository GitHub.
Aktifkan Settings > Pages > Deploy from a branch > main > / (root).

## Catatan data
Data awal disalin dari referensi visual. Validasi dengan register resmi sebelum pelaporan.
Data edit tersimpan di browser yang digunakan, bukan otomatis tersinkron ke pengguna atau perangkat lain.
