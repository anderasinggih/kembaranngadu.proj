# KEMBARAN NGADU 📢
### Sistem Informasi Layanan Pengaduan & Aspirasi Publik Terpadu Berbasis Web Mobile-First

[![Laravel Version](https://img.shields.io/badge/Laravel-v12.x-FF2D20?style=flat-square&logo=laravel&logoColor=white)](https://laravel.com)
[![Livewire Version](https://img.shields.io/badge/Livewire-v3.x-4E56A6?style=flat-square&logo=livewire&logoColor=white)](https://livewire.laravel.com)
[![Alpine.js](https://img.shields.io/badge/Alpine.js-v3.x-8BC0D0?style=flat-square&logo=alpinedotjs&logoColor=white)](https://alpinejs.dev)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v3.x-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![MySQL](https://img.shields.io/badge/MySQL-v8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://www.mysql.com)
[![License: Hak Cipta DJKI](https://img.shields.io/badge/Hak_Cipta-DJKI_Kemenkumham_RI-blue?style=flat-square)](https://dgip.go.id)

---

## 📌 Ringkasan Ciptaan

**Kembaran Ngadu** adalah karya cipta perangkat lunak sistem informasi pelayanan publik (*e-Government*) yang dikembangkan secara spesifik untuk memfasilitasi komunikasi dua arah antara masyarakat dan aparatur pemerintah di tingkat kecamatan. Sistem ini mentransformasi alur birokrasi pengaduan konvensional menjadi ekosistem digital yang terbuka, responsif, partisipatif, serta akuntabel.

Dibangun dengan pendekatan *Mobile-First Responsive Design*, platform ini memungkinkan warga menyampaikan laporan aspirasi maupun keluhan fasilitas umum secara cepat tanpa hambatan pendaftaran akun yang rumit (*Guest Reporting Engine*), seraya menjamin keamanan pelacakan melalui *Cryptographic Tracking Code*, serta mengukur kepuasan penanganan melalui *Multi-Criteria Performance Rating*.

> 📘 **Dokumentasi Desain & Diagram Sistem**: Spesifikasi diagram arsitektur teknis lengkap (Use Case, Entity Relationship Diagram / ERD, Activity Diagram, dan Sequence Diagram) berbasis Mermaid.js terdokumentasi dalam berkas [DIAGRAMS.md](file:///Volumes/LVNPC/KULIAH/TA/PROJECT/KEMBARAN%20NGADU/kembaranngadu/DIAGRAMS.md).

---

## 💡 Karakteristik & Kebaruan Inovasi Sistem

Perangkat lunak ini memuat serangkaian inovasi fungsional dan teknis yang membedakannya dari sistem pelayanan konvensional:

### 1. Mekanisme Pelaporan Cepat (*Seamless Guest Reporting Engine*)
* Warga dapat langsung menyampaikan aduan dan aspirasi secara instan tanpa kewajiban login/registrasi akun yang panjang.
* Sistem menyediakan opsi fleksibilitas perlindungan privasi: **Publik** (terbuka untuk partisipasi masyarakat), **Anonim** (identitas pelapor disamarkan dari publik), maupun **Privat** (hanya dapat ditinjau oleh pihak pelapor dan petugas berwenang).

### 2. Kode Pelacakan Acak Kriptografis (*Cryptographic Tracking Code*)
* Setiap pengaduan yang berhasil dikirimkan akan memperoleh kode pelacakan alfanumerik 6-karakter acak berkekuatan tinggi (*high-entropy alphanumeric string*).
* Mencegah eksploitasi nomor urut (*ID enumeration attack*) pada database dan menjamin privasi serta kemudahan warga dalam mengecek status resolusi aduan kapan saja.

### 3. Kompresi Citra Cerdas di Sisi Klien (*Client-Side Canvas Pre-Compression*)
* Mengoptimalkan pengunggahan foto bukti pengaduan langsung di peramban pengguna (*browser-side*) menggunakan **HTML5 Canvas API** sebelum ditransmisikan ke server.
* Mereduksi beban ukuran berkas citra secara otomatis hingga ~35KB tanpa menurunkan kejelasan visual bukti, sehingga menghemat kuota internet warga dan meminimalkan beban komputasi serta kapasitas penyimpanan server.

### 4. Evaluasi Kinerja Layanan Multi-Dimensi (*Multi-Criteria Service Quality Rating*)
* Pengukuran indeks kepuasan masyarakat terhadap laporan yang telah berstatus **Selesai** berdasarkan 4 pilar utama layanan publik:
  1. **Kualitas Pelayanan**: Kesopanan, transparansi, dan kejelasan tindak lanjut.
  2. **Kecepatan Respon**: Ketepatan waktu dalam menindaklanjuti keluhan.
  3. **Kompetensi Petugas**: Kecakapan teknis petugas dalam menyelesaikan masalah.
  4. **Kualitas Fasilitas**: Ketuntasan perbaikan fisik atau sarana prasarana terkait.
* Dilengkapi mekanisme integritas anti-spam berbasis *Local Device Identifier Token* dan *IP Tracking* guna mencegah manipulasi penilaian berulang dari satu perangkat.

### 5. Sistem Eskalasi Urgensi Partisipatif (*Community Support & Upvoting*)
* Warga dapat memberikan dukungan (*upvote*) pada laporan fasilitas umum yang memerlukan perhatian bersama.
* Pengaduan yang mencapai ambang batas dukungan (≥ 50 dukungan) secara otomatis dikategorikan ke status prioritas **"Mendesak"** pada dasbor petugas untuk percepatan penanganan lapangan.

### 6. Tata Kelola SLA & Dasbor Eksekutif (*SLA Governance & Executive Analytics*)
* Pengaturan batas waktu penanganan (*Service Level Agreement* / SLA) terukur per kategori masalah (misal: Infrastruktur Jalan, Pengelolaan Sampah, Penerangan Jalan Umum).
* Dasbor manajemen analitik untuk pimpinan kecamatan yang menyajikan metrik statistik laporan masuk, efisiensi penanganan SLA, distribusi kepuasan masyarakat, dan ekspor laporan kinerja berkala (*Executive Performance Report*).

---

## 🏛️ Arsitektur Sistem & Spesifikasi Teknologi

Sistem dirancang mengadopsi standar rekayasa perangkat lunak modern untuk memastikan skalabilitas, kehandalan transmisi data, dan kemudahan pemeliharaan:

```
┌─────────────────────────────────────────────────────────────┐
│                   PRESENTATION LAYER                        │
│   Tailwind CSS  │  MaryUI Components  │  Alpine.js (DOM)     │
└──────────────────────────────┬──────────────────────────────┘
                               │ Reactive Livewire Wire-Protocol
┌──────────────────────────────▼──────────────────────────────┐
│                    APPLICATION LAYER                        │
│   Laravel 12.x Core  │  Livewire 3.x Reactive State Engine  │
│   Workflow Engine    │  Client-Side Pre-Compression Handler │
│   SLA Monitor        │  Cryptographic Tracking Generator    │
└──────────────────────────────┬──────────────────────────────┘
                               │ Eloquent ORM / Query Builder
┌──────────────────────────────▼──────────────────────────────┐
│                      DATA LAYER                             │
│   MySQL 8.0 Relational Database  │  Local Object Storage    │
└─────────────────────────────────────────────────────────────┘
```

| Komponen Teknologi | Spesifikasi / Pustaka | Peran & Fungsi dalam Sistem |
| :--- | :--- | :--- |
| **Framework Utama** | **Laravel v12.x** (PHP 8.2+) | *Core application engine*, autentikasi aman, routing, ORM, dan *middleware pipeline*. |
| **Reactive UI Engine** | **Livewire v3.x** | Mengelola sinkronisasi status antarmuka secara *real-time* tanpa *full-page reload*. |
| **Client Interaction** | **Alpine.js v3.x** | Menangani interaksi ringan di sisi peramban (modal, *dropdown*, *client-side pagination*). |
| **Styling Framework** | **Tailwind CSS v3.x** | Desain antarmuka modular, adaptif, konsisten, dan berorientasi *mobile-first*. |
| **Komponen UI** | **MaryUI** | Komponen Blade terstruktur yang mempercepat standardisasi visual form dan tabel. |
| **Basis Data** | **MySQL v8.0** | Relational Database Management System (RDBMS) untuk integritas data transaksi laporan. |
| **Geospasial / Peta** | **Leaflet Maps & OpenStreetMap** | Visualisasi penanda lokasi geografis (*geo-tagging*) aduan secara presisi. |
| **Manajemen Media** | **HTML5 Canvas API + GD Engine** | Kompresi citra ganda (*dual-layer image optimization*) di sisi klien dan server. |

---

## 🧩 Rincian Modul Fungsionalitas Sistem

Sistem **Kembaran Ngadu** tersusun atas beberapa modul fungsional terintegrasi:

### A. Modul Warga & Pelaporan Publik
* **Formulir Pengaduan Cerdas**: Input data judul, uraian masalah, kategori, penentuan koordinat peta otomatis (*geotagging*), dan unggah bukti foto beresolusi teroptimasi.
* **Feed Aduan Transparan**: Eksplorasi laporan masyarakat secara transparan dengan filter kategori, pencarian kata kunci, serta penanda status tahapan penanganan.
* **Pusat Pelacakan Real-Time**: Fasilitas pengecekan riwayat status aduan melalui input kode tracking dengan timeline milestone yang jelas (*Menunggu* ➡️ *Diproses* ➡️ *Selesai* / *Ditolak*).
* **Ruang Diskusi Komunitas**: Interaksi tanya jawab dan klarifikasi berjenjang (*nested comments*) antara pelapor, warga, dan petugas kecamatan.

### B. Modul Penilaian Kinerja Layanan (Feedback Engine)
* **Pemberian Rating Berbasis 4 Metrik**: Pengisian evaluasi performa penanganan setelah aduan tuntas.
* **Pop-up Ulasan Otomatis**: Pemicu dialog rating cerdas yang muncul otomatis saat warga meninjau aduan terselesaikan.
* **Pagination Komentar Ulasan**: Navigasi daftar ulasan warga dengan pagination client-side yang ringan dan responsif.

### C. Modul Manajemen & Disposisi Petugas
* **Verifikasi & Validasi Aduan**: Telaah materi laporan masuk untuk kelayakan disposisi.
* **Pembaruan Alur Kerja Status**: Pembaruan status penanganan bertahap disertai catatan progres dan unggahan foto bukti penyelesaian di lapangan.
* **Manajemen Kategori & SLA**: Pengelolaan master kategori pengaduan beserta penentuan tenggat waktu standar penyelesaian (hari kerja).
* **Audit Trail Riwayat**: Pencatatan otomatis identitas petugas, tanggal, dan kronologi setiap aksi pembaruan status pada sistem.

### D. Modul Analitik Eksekutif & Pelaporan
* **Dasbor Statistik Real-Time**: Visualisasi grafik volume laporan masuk, rasio penyelesaian, dan tingkat kepatuhan terhadap batas waktu SLA.
* **Distribusi Indeks Kepuasan**: Grafik sebaran penilaian masyarakat pada 4 pilar kualitas pelayanan kecamatan.
* **Executive Summary Export**: Fitur pencetakan dan ekspor rekapitulasi data pengaduan resmi untuk laporan berkala instansi pemerintah.

### E. Modul Keamanan & Kontrol Integritas
* **Role-Based Access Control (RBAC)**: Pembagian hak akses terisolasi antara *Superadmin*, *Petugas Kecamatan*, dan *Publik*.
* **Penghindaran Spam & Manipulasi**: Algoritma proteksi *Rate Limiter*, validasi *Local Storage Token*, dan pencatatan jejak audit.
* **Soft Delete Safety**: Proteksi data pengguna dan laporan dengan mekanisme *soft delete* untuk menjaga konsistensi rekam jejak historis.

---

## ⚙️ Persyaratan Sistem Operasional

### 1. Kebutuhan Lingkungan Server
* **Sistem Operasi**: Linux (Ubuntu 22.04 LTS / Debian 12 direkomendasikan) atau Windows Server.
* **PHP Runtime**: Versi 8.2 atau lebih tinggi (ekstensi: `pdo_mysql`, `mbstring`, `openssl`, `curl`, `gd`, `fileinfo`, `zip`).
* **Web Server**: Nginx atau Apache HTTP Server dengan dukungan *URL Rewriting*.
* **Basis Data**: MySQL Server versi 8.0 atau MariaDB 10.5+.
* **Composer**: Versi 2.x+.
* **Node.js**: Versi 18.x atau 20.x LTS (beserta NPM).

### 2. Kebutuhan Perangkat Pengguna (Klien)
* **Peramban Web**: Google Chrome, Mozilla Firefox, Safari, Microsoft Edge, atau Opera versi modern dengan dukungan Javascript & Canvas API aktif.
* **Dukungan Perangkat**: Smartphone Android / iOS, Tablet, Laptop, maupun Komputer Desktop.

---

## 🚀 Panduan Penerapan & Pengoperasian Sistem

Langkah-langkah berikut merupakan panduan standar untuk memasang dan menjalankan sistem pada lingkungan operasional:

### 1. Persiapan Berkas & Dependensi
```bash
# Masuk ke direktori proyek
cd kembaranngadu

# Instal dependensi backend (PHP)
composer install --no-dev --optimize-autoloader

# Instal dependensi frontend (Javascript/CSS)
npm install
```

### 2. Konfigurasi Lingkungan (*Environment*)
Salin berkas konfigurasi template dan sesuaikan parameter basis data:
```bash
cp .env.example .env
```
Buka berkas `.env` dan konfigurasikan koneksi basis data:
```env
APP_NAME="Kembaran Ngadu"
APP_ENV=production
APP_DEBUG=false
APP_URL=https://kembaranngadu.banyumaskab.go.id

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=kembaran_ngadu
DB_USERNAME=db_user
DB_PASSWORD=db_password_rahasia
```

### 3. Migrasi Skema Basis Data & Tautan Media
```bash
# Generate encryption application key
php artisan key:generate

# Eksekusi migrasi skema tabel basis data
php artisan migrate --force

# Buat symbolic link direktori berkas publik
php artisan storage:link

# Optimasi cache konfigurasi dan rute aplikasi
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

### 4. Kompilasi Aset Frontend
```bash
# Kompilasi aset siap produksi
npm run build
```

---

## 📄 Hak Kekayaan Intelektual & Lisensi

```text
Hak Cipta (c) 2026 Andera Singgih Pratama.
Seluruh Hak Dilindungi Undang-Undang.

Karya cipta perangkat lunak ini, termasuk arsitektur sistem, struktur basis data,
algoritma fungsional, dan desain antarmuka pengguna dilindungi oleh Undang-Undang
Republik Indonesia Nomor 28 Tahun 2014 tentang Hak Cipta (DJKI Kemenkumham RI).

Dilarang keras menyalin, memodifikasi, mendistribusikan ulang, atau memanfaatkan
seluruh atau sebagian dari perangkat lunak ini untuk tujuan komersial tanpa izin
tertulis resmi dari Pemegang Hak Cipta.
```

*Dikembangkan untuk kemajuan transparansi pelayanan publik dan tata kelola pemerintahan yang berorientasi pada masyarakat.*
