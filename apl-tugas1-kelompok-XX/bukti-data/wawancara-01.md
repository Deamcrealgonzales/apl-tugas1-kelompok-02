# Ringkasan Wawancara 01

- **Tanggal:** 29-10-2026
- **Responden (peran saja):** Mahasiswa semester 5
- **Pewawancara:** Siti Nur Alfiyyah
- **Layanan yang dibahas:** Layanan kelas SPADA UMI-Kalam

## Pertanyaan dan Ringkasan Jawaban

| Pertanyaan | Ringkasan Jawaban |
|---|---|
| 1. Bagaimana pengalaman Anda ketika mengakses SPADA UMI-Kalam saat awal semester ketika banyak mahasiswa melakukan pendaftaran kelas? | Ketika banyak mahasiswa mengakses sistem secara bersamaan, proses membuka halaman atau mengakses informasi kelas berpotensi menjadi lebih lambat. Sistem sebaiknya mampu menangani banyak pengguna tanpa mengalami gangguan. |
| 2. Menurut Anda, apakah diperlukan mekanisme untuk mempercepat akses daftar kelas ketika banyak mahasiswa menggunakan SPADA secara bersamaan? | Ya, diperlukan. Informasi daftar kelas yang sering dibuka sebaiknya dapat ditampilkan dengan cepat. Penggunaan caching dan pembagian beban server dapat membantu meningkatkan kecepatan akses. |
| 3. Menurut Anda, apakah mahasiswa seharusnya dapat mengakses seluruh materi kelas di SPADA atau hanya materi dari kelas yang diikutinya? | Mahasiswa hanya boleh mengakses materi dan pengumuman dari kelas yang diikutinya. Materi kelas lain seharusnya tidak dapat dibuka oleh mahasiswa yang tidak terdaftar. |
| 4. Jika pemeriksaan hak akses membuat proses membuka materi sedikit lebih lama, apakah keamanan tetap perlu diprioritaskan? | Ya, keamanan tetap perlu diprioritaskan. Pemeriksaan hak akses diperlukan agar materi perkuliahan tidak dapat dibuka oleh pengguna yang tidak berwenang. Namun, proses pemeriksaan sebaiknya tetap dioptimalkan agar tidak terlalu memperlambat sistem. |
| 5. Jika terjadi gangguan pada sistem pemeriksaan hak akses, menurut Anda apakah SPADA sebaiknya tetap memberikan akses materi agar layanan dapat digunakan? | Sistem sebaiknya tidak memberikan akses materi sebelum hak pengguna berhasil diverifikasi. Namun, perlu ada mekanisme pemulihan agar mahasiswa yang berwenang dapat kembali mengakses materi ketika layanan normal. |

## Temuan yang Dipakai pada Laporan

- **A5:** Mahasiswa membutuhkan akses daftar kelas yang cepat, terutama saat awal semester. Temuan ini mendukung penerapan caching dan load balancing pada ADR-001.
- **A5:** Akses materi perlu dibatasi berdasarkan peran dan keanggotaan kelas. Temuan ini mendukung penerapan Role-Based Access Control (RBAC) pada ADR-002.
- **B5:** Kecepatan akses penting, tetapi tidak boleh menghilangkan pemeriksaan hak akses materi. Temuan ini mendukung prioritas Security dibandingkan Performance.
- **B5:** Sistem tidak sebaiknya memberikan akses materi tanpa verifikasi ketika komponen keamanan mengalami gangguan. Temuan ini mendukung prioritas Security dibandingkan Availability.
- **B5:** Pemulihan layanan tetap diperlukan agar mahasiswa yang berwenang dapat kembali mengakses materi setelah gangguan teratasi.
