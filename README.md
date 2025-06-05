# Aplikasi Expense Tracker
Aplikasi pelacakan pengeluaran berbasis web yang dibangun dengan AdonisJS, MySQL, dan template engine Edge.

## Tim Pengembang
- **Muhammad Bintang Indra Hidayat** - NPM: 2208107010023
- **Ahmad Syah Ramadhan** - NPM: 2208107010033
- **Indriani Miza Alfiyanti** - NPM: 2208107010026

## Teknologi yang Digunakan
- AdonisJS - Framework web Node.js yang lengkap
- MySQL - Database
- Edge - Template engine
- TypeScript

## Prasyarat
- Node.js (versi 14 atau lebih tinggi)
- MySQL Server
- Package manager npm atau yarn

## Instalasi
1. Clone repository:
```bash
git clone [url-repository-anda]
cd expense-tracker
```

2. Install dependencies:
```bash
npm install
# atau
yarn install
```

3. Konfigurasi database:
   - Buat database MySQL baru
   - Salin .env.example ke .env
   - Perbarui konfigurasi database di .env dengan kredensial MySQL Anda:
```env
MYSQL_HOST=localhost
MYSQL_PORT=3306
MYSQL_USER=username_anda
MYSQL_PASSWORD=password_anda
MYSQL_DB_NAME=nama_database_anda
```

4. Jalankan migrations:
```bash
node ace migration:run
```

5. Build aplikasi:
```bash
node ace build
```

6. Jalankan server:
```bash
node ace serve
# atau untuk development
node ace serve --watch
```

## Struktur Proyek
```
expense-tracker/
├── app/
│   ├── controllers/      # Controller aplikasi
│   └── models/          # Model database
├── config/              # File konfigurasi
├── database/
│   └── migrations/      # Migration database
├── resources/
│   └── views/          # File template Edge
└── start/
    └── routes.ts       # Route aplikasi
```

## Masalah Umum dan Solusi

### Konfigurasi Database
Jika Anda mengalami masalah timestamp MySQL, pastikan konfigurasi database di config/database.ts mencakup pengaturan timezone yang benar:
```typescript
{
  client: 'mysql',
  connection: {
    timezone: 'Z',
    dateStrings: true
  }
}
```

### Rendering Template Edge
Jika template ditampilkan sebagai teks biasa:
1. Pastikan Edge provider dikonfigurasi dengan benar di config/app.ts
2. Verifikasi bahwa views berada di lokasi yang benar (resources/views/)
3. Periksa bahwa controller menggunakan metode rendering view yang benar:
```typescript
return view.render('namaView', { data })
```

## Kontribusi
Kami menyambut kontribusi dari semua pihak. Silakan buat pull request atau buka issue untuk melaporkan bug atau mengusulkan fitur baru.


## Tentang Proyek
Aplikasi Expense Tracker ini dikembangkan sebagai bagian dari tugas mata kuliah. Aplikasi ini memungkinkan pengguna untuk mencatat dan melacak pengeluaran mereka dengan antarmuka yang mudah digunakan.

### Fitur Utama
- Pencatatan pengeluaran
- Kategorisasi transaksi
- Laporan keuangan
- Antarmuka yang responsif

### Cara Menggunakan
1. Jalankan aplikasi sesuai dengan petunjuk instalasi
2. Buka browser dan akses http://localhost:3333
3. Mulai mencatat pengeluaran Anda
4. Gunakan fitur laporan untuk melihat ringkasan keuangan
