[Uploading README.md…]()
# Dashboard Kesehatan Jiwa --- Puskesmas Naibonat

Dashboard pemantauan program Kesehatan Jiwa (Keswa) untuk Puskesmas
Naibonat. Halaman dibuat sebagai aplikasi statis HTML, CSS, dan
JavaScript agar dapat dijalankan melalui GitHub Pages.

## Fitur

-   Dashboard ringkasan SPM Pelayanan ODGJ, Skrining Jiwa, dan Giat BOK.
-   Filter/pilihan bulan.
-   Informasi jumlah ODGJ dan sebaran berdasarkan wilayah.
-   Pengelolaan data pada browser, termasuk fitur edit yang tersedia di
    aplikasi.
-   Infografis satu halaman dengan opsi ekspor PNG resolusi tinggi dan
    opsi cetak/simpan PDF, jika fitur tersebut tersedia pada versi
    `index.html` yang dipasang.
-   Export PowerPoint satu slide (.pptx) dari tombol **▣ EXPORT
    POWERPOINT**, mengikuti model `KESWA_2026.pptx` dan berisi data bulan
    yang sedang aktif.
-   Tampilan responsif untuk desktop dan perangkat seluler.

## Export PowerPoint

Klik **▣ EXPORT POWERPOINT** untuk mengunduh
`Dashboard-Keswa-<BULAN>.pptx`. Model slide (`KESWA_2026.pptx`)
tersemat di dalam `index.html`; hanya angka dan teks data yang diganti,
sehingga bentuk, warna, dan tata letak sama dengan model.

-   Data yang diisi: SPM Pelayanan ODGJ, Skrining Jiwa, Info ODGJ,
    Kendala, Solusi, dan jumlah ODGJ per wilayah, sesuai bulan aktif.
-   Mengikuti model: Giat BOK tidak ikut diexport, kartu wilayah
    berjumlah lima (wilayah ke-6 masuk ke "Rincian: Lain-lain"), dan
    kendala/solusi maksimal lima butir.
-   Pertama kali dipakai, perlu koneksi internet untuk memuat pustaka
    JSZip dari cdnjs (sama seperti fitur ekspor PNG).
-   Ubah label "Zkizofrenia" melalui konstanta `LABEL_F20` pada blok
    script Export PowerPoint di `index.html`.

## Menjalankan di GitHub Pages

1.  Pastikan file utama bernama **`index.html`** berada di direktori
    utama (root) repositori.
2.  Unggah `index.html` dan `README.md` ke repositori GitHub.
3.  Buka **Settings → Pages**.
4.  Pada **Build and deployment**, pilih **Deploy from a branch**.
5.  Pilih branch `main` dan folder `/(root)`, lalu klik **Save**.
6.  Tunggu proses deployment selesai, lalu buka URL GitHub Pages yang
    ditampilkan di halaman Settings → Pages.

> GitHub Pages hanya menyajikan file statis. Dashboard ini tidak
> membutuhkan README untuk berjalan; README hanya dokumentasi proyek.

## Menjalankan secara lokal

Buka `index.html` langsung di browser, atau dari folder proyek jalankan:

``` bash
python3 -m http.server 8000
```

Kemudian buka `http://localhost:8000`.

## Firebase dan sinkronisasi data

Versi HTML ini menggunakan konfigurasi aplikasi web Firebase yang sudah terdaftar dan koleksi Firestore `dashboardMonths`. Saat halaman dibuka, aplikasi mencoba membaca data bulan dari Firestore; saat data disimpan, aplikasi menyimpan ke Firestore dan cache browser. Perubahan pada dokumen bulan aktif dipantau melalui listener realtime. Pastikan Rules Firestore mengizinkan operasi yang diperlukan. Jika koneksi atau Rules menolak operasi, periksa status Firebase yang tampil di sudut kanan bawah halaman.

## Catatan data dan privasi

-   Periksa dan validasi seluruh angka dashboard terhadap
    register/sumber resmi sebelum digunakan untuk pelaporan.
-   Jika aplikasi menyimpan perubahan menggunakan `localStorage`,
    perubahan itu hanya tersimpan pada browser/perangkat tersebut dan
    tidak otomatis tersinkron ke pengguna atau perangkat lain.
-   Hindari memasukkan identitas pasien atau data pribadi yang tidak
    diperlukan ke repositori publik.
-   Jangan mengunggah kredensial, token, atau data pasien ke GitHub.

## Struktur minimum repositori

``` text
E-PUSBONAT-Keswa/
├── index.html
└── README.md
```

Jika versi `index.html` menggunakan aset terpisah, sertakan juga seluruh
file CSS, JavaScript, gambar, atau aset lain yang dirujuk oleh HTML
tersebut.
