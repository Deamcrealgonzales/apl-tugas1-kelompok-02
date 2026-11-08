# Ringkasan Wawancara 01

- **Tanggal:** 29-10-2026
- **Responden (peran saja):** Mahasiswa semester 5
- **Pewawancara:** Siti Nur Alfiyyah
- **Layanan yang dibahas:** Layanan kelas SPADA UMI-Kalam

## Pertanyaan dan Ringkasan Jawaban

| Pertanyaan | Ringkasan Jawaban |
|---|---|
| 1. Bagaimana pengalaman Anda saat mengakses SPADA UMI-Kalam, terutama ketika awal semester dan banyak mahasiswa melakukan pendaftaran kelas? | Menurut saya, kalau banyak mahasiswa yang mengakses secara bersamaan, terkadang sistem bisa menjadi lambat. Jadi, diharapkan SPADA tetap bisa digunakan dengan lancar meskipun sedang banyak pengguna. |
| 2. Menurut Anda, apakah perlu ada cara untuk mempercepat akses daftar kelas ketika banyak mahasiswa menggunakan SPADA? | Iya, perlu. Karena biasanya mahasiswa akan membuka informasi kelas secara bersamaan. Jadi, informasi yang sering diakses sebaiknya bisa ditampilkan lebih cepat agar tidak perlu menunggu terlalu lama. |
| 3. Menurut Anda, apakah mahasiswa boleh mengakses semua materi kelas atau hanya materi dari kelas yang diikutinya? | Menurut saya, sebaiknya mahasiswa hanya bisa melihat materi dari kelas yang memang diikutinya saja. Kalau materi kelas lain bisa dibuka bebas, tentu kurang aman karena tidak semua mahasiswa memiliki hak akses yang sama. |
| 4. Kalau pemeriksaan hak akses membuat proses membuka materi sedikit lebih lama, apakah keamanan tetap perlu diutamakan? | Iya, menurut saya keamanan tetap penting. Tidak masalah jika ada sedikit proses tambahan selama materi tetap terlindungi. Tetapi, sistem juga harus diusahakan agar tidak terlalu lambat saat digunakan. |
| 5. Jika terjadi gangguan pada sistem pemeriksaan hak akses, apakah SPADA sebaiknya tetap memberikan akses materi agar mahasiswa bisa menggunakannya? | Menurut saya, sebaiknya jangan dulu memberikan akses kalau sistem belum bisa memastikan hak pengguna. Lebih baik akses dibatasi sementara daripada materi bisa dibuka oleh orang yang tidak berhak. Setelah gangguan diperbaiki, mahasiswa bisa kembali mengakses materi seperti biasa. |

## Temuan yang Dipakai pada Laporan

- **A5:** Mahasiswa berharap akses daftar kelas tetap cepat meskipun banyak pengguna yang membuka SPADA secara bersamaan. Hal ini mendukung penggunaan caching dan load balancing pada ADR-001.
- **A5:** Mahasiswa berpendapat bahwa materi kelas sebaiknya hanya bisa diakses oleh mahasiswa yang terdaftar. Hal ini mendukung penerapan RBAC pada ADR-002.
- **B5:** Keamanan tetap perlu diutamakan meskipun pemeriksaan hak akses dapat menambah waktu respons. Kinerja sistem tetap perlu dioptimalkan tanpa menghilangkan pemeriksaan keamanan.
- **B5:** Jika sistem pemeriksaan hak akses mengalami gangguan, akses materi sebaiknya dibatasi sementara sampai sistem kembali normal. Hal ini menunjukkan bahwa keamanan lebih diprioritaskan dibandingkan ketersediaan akses tanpa verifikasi.
- **B5:** Sistem perlu memiliki mekanisme pemulihan agar mahasiswa yang berhak tetap bisa menggunakan layanan setelah gangguan teratasi.
