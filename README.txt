Atlas BUC - PWA untuk hosting sendiri
=====================================
Isi folder:
  index.html            aplikasi lengkap (satu file)
  manifest.webmanifest  identitas PWA (nama, ikon, warna)
  sw.js                 service worker: aplikasi tetap terbuka saat offline
  icon-192.png, icon-512.png

Cara pasang di server intranet (IIS, nginx, Apache, GitLab Pages):
  1. Salin seluruh folder ini ke satu direktori web, mis. https://intranet/atlas-buc/
  2. Wajib HTTPS (atau http://localhost) agar service worker dan "Install app" aktif.
  3. IIS: tambahkan MIME type .webmanifest = application/manifest+json.
  4. Buka alamatnya di Chrome/Edge, lalu pilih "Install app" / "Tambahkan ke layar utama".

Catatan penyimpanan pada mode hosting sendiri:
  - Data disimpan di browser perangkat masing-masing (localStorage).
  - Untuk berbagi antar pewawancara: menu Ekspor & pengaturan > Cadangan lengkap / Paket JSON,
    lalu Impor di perangkat lain; atau hubungkan ke API backend sendiri (SQL Server) di tahap berikutnya.
  - Asisten AI hanya aktif bila aplikasi dibuka di Claude.

Data contoh:
  Menu Ekspor & pengaturan > "Muat data contoh" menambahkan 17 BUC contoh (pabrik fragrance)
  untuk demo/pelatihan, bekerja juga saat offline. "Hapus data contoh" hanya menghapus BUC
  bertanda Contoh; BUC hasil wawancara tidak tersentuh.

Pembaruan: ganti index.html (dan sw.js) di server; perangkat yang sudah install otomatis
mengambil versi baru saat online berikutnya.
