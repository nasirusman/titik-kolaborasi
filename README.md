<div align="center">
<img alt="Colanode cover" src="assets/images/colanode-cover-black.png">
<p></p>
<a target="_blank" href="https://opensource.org/licenses/Apache-2.0" style="background:none">
    <img src="https://img.shields.io/badge/Licene-Apache_2.0-blue" style="height: 22px;" />
</a>
<a target="_blank" href="https://discord.gg/29fXUxAe" style="background:none">
    <img alt="" src="https://img.shields.io/badge/Discord-Colanode-%235865F2" style="height: 22px;" />
</a>
<a href="https://x.com/colanode" target="_blank">
  <img alt="" src="https://img.shields.io/twitter/follow/colanode.svg?style=social&label=Follow" style="height: 22px;" />
</a>
</div>

# Colanode

### Ruang kerja kolaborasi open-source & local-first yang dapat Anda self-host

Colanode adalah platform serba ada untuk kolaborasi yang mudah, dibangun dengan memprioritaskan privasi dan kendali data Anda. Dirancang dengan pendekatan **local-first**, Colanode membantu tim berkomunikasi, mengatur, dan mengelola proyek—baik saat online maupun offline. Dengan Colanode, Anda mendapatkan fleksibilitas alat kolaborasi modern ditambah ketenangan karena sepenuhnya memiliki data Anda.

### Apa yang bisa Anda lakukan dengan Colanode?

- **Chat Real-Time:** Tetap terhubung dengan pesan instan untuk tim dan individu.
- **Halaman Rich Text:** Buat dokumen, wiki, dan catatan menggunakan editor intuitif mirip Notion.
- **Basis Data yang Dapat Disesuaikan:** Atur informasi dengan data terstruktur, kolom kustom, dan tampilan dinamis (tabel, kanban, kalender).
- **Manajemen Berkas:** Simpan, bagikan, dan kelola berkas dengan mudah di workspace yang aman.

Dibuat untuk individu maupun tim, Colanode menyesuaikan kebutuhan Anda, apakah menjalankan proyek kecil, mengelola tim, atau bekerja sama di seluruh organisasi. Dengan model self-host, Anda memegang kendali penuh atas data sembari menikmati pengalaman kaya fitur yang polished.

![Colanode preview](assets/images/colanode-desktop-preview.gif)

## Cara kerja

Colanode terdiri dari aplikasi klien (web atau desktop) dan server yang dapat di-host sendiri. Anda dapat terhubung ke beberapa server dengan satu aplikasi, masing-masing berisi satu atau lebih **workspace** untuk tim atau proyek berbeda. Setelah masuk, pilih workspace untuk mulai berkolaborasi—mengirim pesan, mengedit halaman, atau memperbarui catatan basis data.

### Alur kerja local-first

Semua perubahan disimpan terlebih dulu ke basis data SQLite lokal kemudian disinkronkan ke server. Proses latar belakang menangani sinkronisasi agar Anda tetap bisa bekerja meskipun komputer atau server sedang offline. Pembacaan data juga dilakukan secara lokal sehingga Anda langsung mengakses konten apa pun yang Anda izinkan.

### Penyuntingan serempak

Colanode mengandalkan **Conflict-free Replicated Data Types (CRDTs)** – ditenagai oleh [Yjs](https://docs.yjs.dev/) – untuk memungkinkan kolaborasi waktu nyata pada entri seperti halaman atau catatan basis data. Artinya, beberapa orang dapat menyunting secara bersamaan dan sistem akan menggabungkan pembaruan setiap orang dengan mulus. Penghapusan juga dilacak sebagai transaksi khusus. Pesan dan operasi berkas tidak mendukung penyuntingan serempak dan menggunakan tabel basis data yang lebih sederhana.

## Mulai gratis

Cara termudah menggunakan Colanode adalah melalui **aplikasi web** kami, yang dapat diakses langsung di [app.colanode.com](https://app.colanode.com). Cukup masuk untuk mulai segera tanpa instalasi. _Harap dicatat, aplikasi web saat ini masih versi awal (early preview) dan dalam pengujian; Anda mungkin menemukan bug atau masalah kompatibilitas di beberapa browser._

Untuk kinerja optimal, Anda dapat menginstal **aplikasi desktop** kami yang tersedia di [halaman unduhan](https://colanode.com/downloads). Baik aplikasi web maupun desktop memungkinkan Anda terhubung ke server cloud beta gratis kami:

- **Colanode Cloud (EU)** – di-host di Eropa.
- **Colanode Cloud (US)** – di-host di Amerika Serikat.

Kedua server cloud tersebut saat ini tersedia dalam versi beta dan dapat digunakan gratis; detail harga akan diumumkan segera.

### Self-host dengan Docker

Jika Anda lebih suka meng-host server Colanode sendiri, cukup gunakan file Docker Compose di root repositori ini. Dalam waktu dekat, kami akan menyediakan petunjuk lebih rinci untuk lingkungan lain, termasuk Kubernetes. Untuk sekarang, berikut yang Anda perlukan untuk menjalankan Colanode sendiri:

- **Postgres** dengan ekstensi **pgvector**.
- **Redis** (layanan yang kompatibel dengan Redis juga berfungsi, misalnya Valkey).
- **Penyimpanan yang kompatibel dengan S3** (mendukung operasi berkas dasar: PUT, GET, DELETE).
- **API server Colanode**, disediakan sebagai gambar Docker.

Semua variabel lingkungan yang diperlukan untuk server Colanode dapat ditemukan di file docker-compose.

## Lisensi

Colanode dirilis di bawah [Lisensi Apache 2.0](LICENSE).
