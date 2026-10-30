# A3. Batasan Sistem

**Penanggung Jawab:** [A. Aqila Nurul Khalida]

| Kategori | Batasan Sistem | Dampak terhadap Arsitektur |
|:---|:---|:---|
| Teknologi | Sistem harus terintegrasi dengan platform SPADA UMI-Kalam yang sudah tersedia dan mengikuti teknologi serta mekanisme pengelolaan data yang digunakan oleh platform tersebut. | Arsitektur perlu menyesuaikan struktur sistem SPADA yang sudah ada agar layanan pendaftaran kelas, pengelolaan materi, akses materi, dan pengumuman dapat berjalan secara terintegrasi. |
| Teknologi | Pengunggahan materi pembelajaran harus mengikuti format dan batas ukuran file yang didukung oleh SPADA UMI-Kalam. | Arsitektur perlu menyediakan modul validasi file untuk memeriksa format dan ukuran materi sebelum file disimpan. |
| Bisnis | Layanan kelas hanya mencakup pendaftaran kelas, unggah materi, akses materi, dan pengumuman, tidak termasuk layanan pengumpulan tugas maupun ujian daring. | Arsitektur harus berfokus pada empat fungsi utama tersebut agar pengembangan sistem tidak meluas ke layanan lain di luar ruang lingkup penelitian. |
| Bisnis | Pendaftaran kelas dan pengelolaan materi harus mengikuti ketentuan akademik serta aturan pengelolaan kelas yang berlaku di UMI. | Arsitektur perlu menyediakan mekanisme validasi pendaftaran kelas dan pengaturan pengelolaan materi berdasarkan ketentuan yang ditetapkan. |
| Operasional | Sistem harus dapat digunakan oleh mahasiswa dan dosen melalui perangkat komputer maupun ponsel selama terhubung dengan internet. | Arsitektur perlu mendukung antarmuka yang responsif agar layanan dapat diakses dengan baik melalui berbagai ukuran layar dan perangkat. |
| Operasional | Pengelolaan materi dan pengumuman hanya dapat dilakukan oleh dosen atau pengelola kelas yang memiliki wewenang, sedangkan mahasiswa hanya dapat mengakses informasi sesuai hak aksesnya. | Arsitektur perlu menerapkan pengaturan hak akses berdasarkan peran pengguna agar setiap fitur hanya dapat digunakan oleh pihak yang berwenang. |
