# Kas Kelas

Aplikasi pembukuan kas kelas (ceklis pembayaran bulanan + pengeluaran), 100% offline,
data tersimpan di HP lewat `localStorage`, dibungkus jadi APK Android dengan Capacitor.

## Struktur folder

```
kas-kelas-app/
├── www/
│   └── index.html          <- aplikasi (satu file, semua logic ada di sini)
├── package.json
├── capacitor.config.json
├── .github/workflows/build-apk.yml   <- workflow build otomatis
└── .gitignore
```

Folder `android/` **belum ada** di sini — workflow GitHub Actions akan membuatnya
otomatis lewat `npx cap add android` setiap kali build jalan.

## Cara pakai

1. Upload semua isi folder ini ke repo GitHub (pertahankan struktur foldernya,
   termasuk folder `.github` yang tersembunyi).
2. Push ke branch `main` — workflow otomatis jalan.
3. Buka tab **Actions** di repo, tunggu sampai selesai (tanda centang hijau).
4. Klik hasil build paling atas, scroll ke bagian **Artifacts**, unduh
   `kas-kelas-debug-apk`. Di dalamnya ada `app-debug.apk`.
5. Pindahkan APK itu ke HP, install seperti biasa (mungkin perlu izinkan
   "install dari sumber tidak dikenal" karena ini APK debug, bukan dari Play Store).

## Kalau mau ubah tampilan/fitur aplikasi

Edit langsung file `www/index.html`, lalu push lagi — workflow otomatis build ulang.

## Catatan

- APK yang dihasilkan workflow ini adalah **APK debug** (untuk dites sendiri di HP).
  Untuk dipublikasikan resmi (Play Store), perlu proses signing APK release —
  bisa dibahas lagi kalau sudah sampai tahap itu.
- Nama paket app: `com.korlas.kaskelas` — bisa diganti di `capacitor.config.json`
  kalau mau nama lain (misal disesuaikan nama sekolah).
