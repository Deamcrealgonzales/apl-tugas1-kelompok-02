# B1. Identifikasi dan Klasifikasi Karakteristik Arsitektur

Penanggung jawab: [Dea Mcreal Gonzales]

## 1. Kandidat Karakteristik Arsitektur

| No. | Karakteristik Arsitektur | Kategori | Sifat | Alasan |
|---|---|---|---|---|
| 1 | Availability (Ketersediaan) | Operational | Implicit | Layanan kelas harus dapat diakses mahasiswa dan dosen ketika dibutuhkan untuk kegiatan pembelajaran. |
| 2 | Performance (Kinerja) | Operational | Implicit | Sistem perlu memberikan respons yang baik saat pengguna mendaftar kelas, mengakses materi, dan melihat pengumuman. |
| 3 | Scalability (Skalabilitas) | Operational | Implicit | Sistem perlu mampu menangani peningkatan jumlah pengguna dan aktivitas kelas secara bersamaan. |
| 4 | Reliability (Keandalan) | Operational | Implicit | Sistem perlu berjalan dengan baik agar proses pendaftaran kelas dan pengelolaan materi tidak mudah mengalami kegagalan. |
| 5 | Maintainability (Kemudahan Pemeliharaan) | Structural | Implicit | Sistem perlu mudah diperbaiki dan dipelihara ketika terjadi kesalahan atau perubahan kebutuhan. |
| 6 | Extensibility (Kemudahan Pengembangan) | Structural | Implicit | Sistem perlu memungkinkan penambahan fitur pembelajaran baru tanpa harus mengubah keseluruhan sistem. |
| 7 | Security (Keamanan) | Cross-cutting | Implicit | Sistem perlu melindungi akun pengguna, materi perkuliahan, dan informasi kelas dari akses yang tidak berwenang. |
| 8 | Usability (Kemudahan Penggunaan) | Cross-cutting | Implicit | Sistem perlu memiliki tampilan dan alur penggunaan yang mudah dipahami oleh mahasiswa maupun dosen. |
| 9 | Accessibility (Aksesibilitas) | Cross-cutting | Implicit | Sistem perlu dapat digunakan oleh pengguna dengan kebutuhan dan kemampuan yang berbeda, termasuk pengguna yang membutuhkan teknologi bantu. |
| 10 | Interoperability (Interoperabilitas) | Cross-cutting | Implicit | Sistem perlu mendukung pertukaran informasi dengan layanan atau komponen lain yang terhubung dengan SPADA. |

## 2. Tiga Karakteristik Arsitektur yang Menjadi Driver

Berdasarkan sepuluh kandidat di atas, dipilih tiga karakteristik yang paling berpengaruh terhadap keberhasilan sistem.

| No. | Karakteristik | Alasan Pemilihan |
|---|---|---|
| 1 | Availability (Ketersediaan) | Ketersediaan menjadi penting karena mahasiswa dan dosen membutuhkan akses layanan kelas untuk kegiatan pembelajaran. Jika sistem tidak dapat diakses, proses pembelajaran dan penyampaian informasi dapat terganggu. |
| 2 | Security (Keamanan) | Keamanan diperlukan untuk melindungi akun mahasiswa dan dosen serta memastikan materi dan informasi kelas hanya dapat diakses oleh pengguna yang memiliki hak akses. |
| 3 | Usability (Kemudahan Penggunaan) | Kemudahan penggunaan diperlukan agar mahasiswa dapat mendaftar dan mengakses materi, sedangkan dosen dapat mengunggah materi serta menyampaikan pengumuman tanpa kesulitan. |

## 3. Pengujian Tiga Kriteria Karakteristik Arsitektur

Tiga karakteristik yang dipilih kemudian diuji berdasarkan tiga kriteria karakteristik arsitektur.

| No. | Kriteria Pengujian | Availability | Security | Usability |
|---|---|---|---|---|
| 1 | Merupakan pertimbangan desain di luar fungsi utama sistem (nondomain consideration). | Ya | Ya | Ya |
| 2 | Memengaruhi aspek struktural atau desain sistem. | Ya | Ya | Ya |
| 3 | Penting terhadap keberhasilan aplikasi. | Ya | Ya | Ya |
