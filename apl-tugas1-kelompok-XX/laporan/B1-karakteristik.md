# B1. Identifikasi dan Klasifikasi Karakteristik Arsitektur

**Penanggung jawab:** Dea Mcreal Gonzales

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

Berdasarkan sepuluh kandidat karakteristik arsitektur, dipilih tiga karakteristik yang paling berpengaruh terhadap keberhasilan layanan kelas SPADA UMI-Kalam, yaitu Performance, Availability, dan Security. Pemilihan ini diselaraskan dengan kebutuhan signifikan secara arsitektural (ASR) pada bagian A4.

| No. | Karakteristik | Alasan Pemilihan |
|---|---|---|
| 1 | Performance (Kinerja) | Performance menjadi karakteristik utama karena layanan pendaftaran kelas berpotensi mengalami lonjakan akses pada awal semester. Berdasarkan ASR-1, sistem harus mampu melayani 3.000 mahasiswa secara bersamaan dengan 95% halaman daftar kelas dan proses pendaftaran selesai dalam waktu kurang dari 3 detik. Karakteristik ini memengaruhi penerapan caching dan load balancing. |
| 2 | Availability (Ketersediaan) | Availability diperlukan agar mahasiswa dan dosen tetap dapat mengakses materi serta pengumuman selama kegiatan perkuliahan. Berdasarkan ASR-2, layanan harus tersedia minimal 99,5% pada pukul 06.00–23.00 WITA dan dapat pulih dalam waktu kurang dari 30 menit jika terjadi gangguan. Karakteristik ini memengaruhi kebutuhan pemantauan, redundansi, dan pemulihan layanan. |
| 3 | Security (Keamanan) | Security diperlukan untuk melindungi materi kelas dari akses yang tidak berwenang. Berdasarkan ASR-3, materi hanya boleh diakses oleh dosen pengampu dan mahasiswa yang terdaftar pada kelas tersebut. Seluruh percobaan akses tanpa hak harus ditolak dan dicatat dalam log. Karakteristik ini memengaruhi penerapan Role-Based Access Control (RBAC), pemeriksaan keanggotaan kelas, dan pencatatan akses. |

Ketiga karakteristik tersebut dipilih karena memiliki dampak langsung terhadap keputusan desain arsitektur dan telah didukung oleh kebutuhan yang terukur pada bagian A4. Usability tetap menjadi karakteristik yang relevan, tetapi tidak dipilih sebagai salah satu dari tiga driver utama.

## 3. Pengujian Tiga Kriteria Karakteristik Arsitektur

Tiga karakteristik yang dipilih kemudian diuji berdasarkan tiga kriteria karakteristik arsitektur.

| No. | Kriteria Pengujian | Performance | Availability | Security |
|---|---|---|---|---|
| 1 | Merupakan pertimbangan desain di luar fungsi utama sistem (nondomain consideration). | Ya | Ya | Ya |
| 2 | Memengaruhi aspek struktural atau desain sistem. | Ya | Ya | Ya |
| 3 | Penting terhadap keberhasilan aplikasi. | Ya | Ya | Ya |

Berdasarkan hasil pengujian, Performance, Availability, dan Security memenuhi ketiga kriteria karakteristik arsitektur. Ketiganya bukan sekadar fungsi utama sistem, tetapi merupakan kebutuhan kualitas yang memengaruhi rancangan komponen, mekanisme pengelolaan layanan, dan keberhasilan operasional SPADA UMI-Kalam.
