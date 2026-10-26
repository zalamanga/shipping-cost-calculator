# Shipping Cost Calculator

Demo pengecekan ongkos kirim berdasarkan kota asal, tujuan, berat, dan kurir melalui RajaOngkir.

## Yang tersedia

- Pilihan provinsi, kota, kurir, dan berat kiriman.
- Endpoint kota per provinsi dan hasil biaya dari API RajaOngkir.
- Migrasi kota, provinsi, kurir, serta seeder lokasi.

## Menjalankan demo

Laravel v8.83.27, PHP ^7.3|^8.0, Composer, serta MySQL/MariaDB. Aset frontend memakai perintah pada package.json. Dependency Composer dan Node tidak disertakan.

1. Pakai versi PHP yang memenuhi composer.json dan lockfile. Aktifkan ekstensi PDO MySQL, mbstring, OpenSSL, tokenizer, XML, ctype, dan fileinfo.
2. Salin .env.example menjadi .env bila belum ada, lalu isi koneksi database sendiri. Jangan commit .env.
3. Jalankan `composer install`, lalu `php artisan key:generate`.
4. Buat database demo kosong, lalu jalankan `php artisan migrate`. Baca isi seeder sebelum menjalankan `php artisan db:seed`.
5. Untuk aset yang berasal dari source, jalankan `npm install` dan script development/production atau build yang tersedia pada package.json. Toolchain Node legacy belum diuji ulang.
6. Jalankan `php artisan serve` dan buka alamat yang dicetak terminal.

Isi RAJAONGKIR_API_KEY, lalu jalankan seeder lokasi/kurir hanya setelah memastikan API dan paket akun sesuai. Seeder lokasi menghubungi layanan eksternal.

## Struktur yang perlu dibaca

`app/` menyimpan controller/model atau komponen Livewire, `routes/` memetakan URL, `resources/views/` menyimpan Blade, `database/migrations/` berisi skema, dan `public/` adalah web root. `tests/` yang tersedia sebagian besar masih contoh bawaan framework.

## Batas implementasi

- API RajaOngkir dan seeder lokasi membutuhkan kredensial serta layanan eksternal yang masih kompatibel dengan klien Kavist 1.1.0; belum diuji terhadap layanan saat ini.
- Varian Laravel 7 yang memiliki scaffolding login tidak digabungkan. Sumber utama dipilih dari cek-ongkir dengan Laravel 8.83.27 dan validasi input pada controller.

## Pemeriksaan publikasi

- PHP lint: 61/61 berkas PHP non-Blade lolos menggunakan PHP 8.1.12.
- Salinan publik tidak menyertakan .env aktual, dependency Composer/Node, log, database dump, arsip, sesi, atau unggahan lokal.
- Tes framework, koneksi database, pengoperasian UI, build aset, dan API eksternal belum dijalankan pada salinan ini. Lint hanya memeriksa sintaks; tidak membuktikan seluruh fitur berfungsi.

## Asal source dan lisensi

Berasal dari [https://github.com/syafiqfajrianemha/cek-ongkir](https://github.com/syafiqfajrianemha/cek-ongkir). Riwayat Git sumber tidak dibawa ke salinan publik ini; atribusi upstream dan berkas lisensi yang tersedia tetap dipertahankan.

Aset UI statis yang dirujuk aplikasi tetap disertakan beserta lisensi yang tersedia. Konten merek dan gambar mengikuti hak pemilik aslinya. Perubahan untuk publikasi ini meliputi dokumentasi, pemisahan konfigurasi lokal, skema demo bila diperlukan, dan koreksi terbatas yang dicatat pada persiapan proyek.
