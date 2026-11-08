
# Ringkasan Wawancara 1

- **Tanggal:** [DD-MM-2026]
- **Responden (peran saja):** Mahasiswa semester 5
- **Pewawancara:** Nabila Zahrani Azalea Arief
- **Layanan yang dibahas:** Layanan akademik berbasis sistem (pendaftaran kelas, akses materi, dan pengumuman).

## Pertanyaan dan Ringkasan Jawaban

| Pertanyaan | Ringkasan Jawaban |
|---|---|
| 1. Bagaimana pengalaman Anda ketika melakukan pendaftaran kelas pada awal semester? | Proses pendaftaran kelas terkadang mengalami kendala karena banyak mahasiswa mengakses sistem secara bersamaan. Halaman menjadi lambat dan membutuhkan waktu lebih lama untuk memuat informasi kelas. |
| 2. Apakah Anda pernah mengalami kesulitan mengakses materi perkuliahan atau pengumuman melalui sistem? | Pernah. Terkadang materi perkuliahan sulit dibuka ketika koneksi atau sistem sedang bermasalah. Hal ini mengganggu, terutama ketika materi dibutuhkan untuk belajar atau mengerjakan tugas. |
| 3. Menurut Anda, apakah informasi dan materi perkuliahan harus selalu tersedia ketika dibutuhkan? | Ya, karena mahasiswa membutuhkan akses materi dan pengumuman setiap hari, terutama menjelang ujian dan ketika dosen memberikan tugas. Sistem sebaiknya dapat digunakan selama jam perkuliahan tanpa sering mengalami gangguan. |
| 4. Menurut Anda, apakah materi perkuliahan perlu dibatasi berdasarkan kelas dan hak akses pengguna? | Ya. Materi seharusnya hanya dapat diakses oleh mahasiswa yang terdaftar pada kelas tersebut dan dosen pengampu. Dengan begitu, materi tidak dapat dibuka oleh pengguna yang tidak berkepentingan. |
| 5. Fitur atau peningkatan apa yang Anda harapkan dari sistem layanan akademik tersebut? | Sistem diharapkan memiliki waktu akses yang cepat, jarang mengalami gangguan, menyediakan keamanan akun dan materi perkuliahan, serta memudahkan mahasiswa menemukan pengumuman dan materi. |

## Temuan yang Dipakai pada Laporan

- **A4 / ASR-1:** Pendaftaran kelas perlu memiliki kinerja yang baik agar tetap cepat meskipun diakses banyak mahasiswa secara bersamaan.
- **A4 / ASR-2:** Sistem harus memiliki ketersediaan layanan yang tinggi agar mahasiswa dapat mengakses materi dan pengumuman tanpa gangguan berkepanjangan.
- **A4 / ASR-3:** Materi perkuliahan harus dilindungi dengan pembatasan hak akses berdasarkan peran dan kelas pengguna.
- **B4:** Kebutuhan kinerja dan skalabilitas berkaitan dengan *Performance Efficiency*.
- **B4:** Kebutuhan ketersediaan berkaitan dengan *Reliability*.
- **B4:** Kebutuhan keamanan akses berkaitan dengan *Security*.

---

# A4. Kebutuhan Signifikan (ASR)

**Penanggung Jawab:** Nabila Zahrani Azalea Arief

| Kode | Jenis | Pernyataan ASR | Mengapa Signifikan Secara Arsitektural |
|---|---|---|---|
| ASR-1 | Atribut kualitas (kinerja dan kapasitas) | Saat pendaftaran kelas dibuka di awal semester, 3.000 mahasiswa mengakses layanan bersamaan, dan 95% halaman daftar kelas serta proses pendaftaran selesai dalam waktu kurang dari 3 detik. | Lonjakan pengguna terjadi serentak pada jadwal tertentu. Arsitektur perlu mempertimbangkan caching, load balancing, atau antrean untuk proses pendaftaran. |
| ASR-2 | Atribut kualitas (ketersediaan) | Layanan akses materi dan pengumuman tersedia minimal 99,5% pada jam perkuliahan dan masa ujian (06.00–23.00 WITA), serta layanan pulih dalam waktu kurang dari 30 menit jika terjadi gangguan. | Kebutuhan ini memengaruhi keputusan redundansi server, pencadangan berkala, pemantauan layanan, dan prosedur pemulihan. |
| ASR-3 | Atribut kualitas (keamanan akses) | Materi kelas hanya dapat dibuka oleh dosen pengampu dan mahasiswa yang terdaftar pada kelas tersebut. 100% percobaan akses tanpa hak ditolak dan tercatat dalam log. | Sistem membutuhkan pengaturan hak akses berdasarkan peran, pengelolaan sesi, otorisasi, dan pencatatan akses pada seluruh komponen. |

---

# B4. Pemetaan ke ISO/IEC 25010

**Penanggung Jawab:** Nabila Zahrani Azalea Arief

| Karakteristik Pendorong | Karakteristik Mutu ISO/IEC 25010 | Subkarakteristik yang Relevan | Penjelasan Singkat | Terkait ASR |
|---|---|---|---|---|
| Kinerja dan skalabilitas | *Performance Efficiency* | *Time Behaviour*, *Capacity* | Waktu respons pendaftaran kelas dan akses materi saat 3.000 pengguna bersamaan, serta jumlah pengguna yang dapat dilayani sistem. | ASR-1 |
| Ketersediaan | *Reliability* | *Availability*, *Recoverability* | Layanan harus dapat diakses selama jam perkuliahan dan pulih dengan cepat setelah gangguan. | ASR-2 |
| Keamanan akses | *Security* | *Confidentiality*, *Authenticity*, *Accountability* | Materi hanya dapat diakses pengguna yang berhak, identitas pengguna diverifikasi, dan setiap akses tercatat dalam log. | ASR-3 |
