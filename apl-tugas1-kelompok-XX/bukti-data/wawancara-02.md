# Ringkasan Wawancara [02]

- **Tanggal:** 29-10-2026
- **Responden (peran saja):** Mahasiswa semester 5
- **Pewawancara:** A. Aqila Nurul Khalida
- **Layanan yang dibahas:** Layanan kelas SPADA UMI-Kalam

## Pertanyaan dan ringkasan jawaban

| Pertanyaan | Ringkasan jawaban |
|---|---|
| Apakah menurut Anda layanan pendaftaran kelas, materi perkuliahan, dan pengumuman pada SPADA UMI-Kalam sudah terintegrasi dengan baik? | Cukup membantu karena layanan kelas dapat digunakan melalui SPADA. Namun, akan lebih praktis jika seluruh informasi kelas, materi, dan pengumuman saling terhubung sehingga pengguna tidak perlu melakukan proses yang berulang. |
| Apakah Anda pernah mengalami kesulitan ketika membuka atau mengunduh materi karena format maupun ukuran file? | Pernah mengalami kesulitan ketika membuka file tertentu, terutama jika ukuran file cukup besar atau formatnya kurang sesuai dengan perangkat. Sebaiknya sistem memberikan informasi mengenai format dan batas ukuran file yang dapat digunakan. |
| Menurut Anda, fitur apa saja yang paling dibutuhkan dalam layanan kelas SPADA UMI-Kalam? | Menurut saya, fitur yang paling dibutuhkan adalah pendaftaran kelas, akses materi perkuliahan, dan pengumuman. Ketiga fitur tersebut sudah membantu kegiatan belajar, sedangkan pengumpulan tugas dan ujian daring dapat menjadi layanan yang terpisah. |
| Apakah SPADA UMI-Kalam mudah digunakan melalui komputer maupun ponsel? Bagaimana menurut Anda pembagian hak akses antara mahasiswa dan dosen? | Sistem sebaiknya dapat digunakan dengan nyaman melalui komputer maupun ponsel. Selain itu, dosen sebaiknya memiliki akses untuk mengunggah materi dan membuat pengumuman, sedangkan mahasiswa hanya dapat mengakses informasi sesuai kelas yang diikuti. |
| Informasi atau pemberitahuan seperti apa yang Anda harapkan ketika melakukan pendaftaran kelas atau ketika dosen mengunggah materi dan pengumuman baru? | Saya berharap ada konfirmasi setelah berhasil mendaftar kelas dan pemberitahuan ketika terdapat materi atau pengumuman baru. Dengan begitu, mahasiswa tidak perlu terus-menerus memeriksa halaman kelas secara manual. |

## Temuan yang dipakai pada laporan

- **A3:** Layanan kelas perlu terintegrasi dengan platform SPADA UMI-Kalam yang sudah tersedia serta mengikuti teknologi dan mekanisme pengelolaan data yang digunakan. Temuan ini mendukung kebutuhan integrasi antarlayanan dalam perancangan arsitektur.

- **A3:** Pengelolaan materi perlu memperhatikan format dan batas ukuran file yang didukung oleh sistem. Temuan ini mendukung perlunya modul validasi berkas sebelum materi disimpan.

- **A3:** Layanan kelas perlu berfokus pada empat fungsi utama, yaitu pendaftaran kelas, unggah materi, akses materi, dan pengumuman. Temuan ini mendukung pembatasan ruang lingkup layanan agar pengembangan tidak meluas ke fitur lain.

- **A3:** Sistem perlu mendukung penggunaan melalui komputer maupun ponsel serta menerapkan pembagian hak akses antara dosen dan mahasiswa. Temuan ini mendukung kebutuhan antarmuka responsif dan pengaturan hak akses pengguna.

- **B3:** Kebutuhan layanan yang terdiri atas tampilan pengumuman, pendaftaran kelas, dan materi mendukung pembagian modul berdasarkan fungsi dan tanggung jawabnya, yaitu lapisan tampilan, logika aplikasi, modul pendukung, dan akses data.

- **B3:** Kebutuhan konfirmasi pendaftaran serta pemberitahuan materi dan pengumuman baru menjadi masukan dalam perancangan komunikasi antarkomponen, khususnya server aplikasi, antrean notifikasi, worker notifikasi, dan gateway email atau push.
