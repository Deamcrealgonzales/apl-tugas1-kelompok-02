# B2. Atribut Kualitas yang Terukur

**Penanggung jawab:** Nur Annisa Az Zahra Diponegoro

**Layanan yang dianalisis:** Layanan kelas SPADA UMI-Kalam, meliputi pendaftaran kelas, unggah materi, akses materi, dan pengumuman.

Tiga karakteristik pendorong yang diukur adalah Kinerja (Performance), Ketersediaan (Availability), dan Keamanan (Security), sesuai B1 dan kebutuhan signifikan pada A4.

## B2.1 Tabel Atribut Terukur

| Karakteristik pendorong | Atribut terukur (angka target) | Kondisi pengukuran | Cara mengukur / menguji |
|---|---|---|---|
| **Kinerja (Performance)** | Saat 3.000 mahasiswa mengakses layanan bersamaan, 95% halaman daftar kelas dan proses pendaftaran selesai dalam waktu kurang dari 3 detik. | Lonjakan 3.000 pengguna aktif bersamaan ketika pendaftaran kelas dibuka pada awal semester, di lingkungan pengujian yang merepresentasikan layanan. | Uji beban menggunakan Apache JMeter atau k6 dengan skenario membuka daftar kelas dan melakukan pendaftaran. Ukur persentil ke-95 waktu respons masing-masing proses dalam tiga kali pengujian. Target terpenuhi jika keduanya kurang dari 3 detik. |
| **Ketersediaan (Availability)** | Layanan akses materi dan pengumuman tersedia minimal 99,5% pada pukul 06.00–23.00 WITA dan pulih dalam waktu kurang dari 30 menit setelah gangguan. | Pengamatan pada jam layanan perkuliahan, termasuk masa ujian, dengan periode perhitungan uptime bulanan. | Pantau layanan akses materi dan pengumuman secara otomatis setiap satu menit. Hitung persentase waktu tersedia dan lakukan simulasi gangguan untuk mengukur waktu pemulihan. |
| **Keamanan (Security)** | 100% percobaan akses materi oleh pengguna tanpa hak ditolak dan dicatat dalam log. | Pengujian terhadap pengguna tanpa login, mahasiswa terdaftar, mahasiswa bukan peserta, dan dosen pengampu. | Lakukan minimal 100 skenario akses tanpa hak menggunakan akun uji: 50 tanpa login dan 50 akun bukan peserta. Seluruh percobaan harus ditolak dengan respons yang sesuai (401/403) dan dicatat dalam log. |

## B2.2 Dasar Penetapan Angka dan Asumsi

1. **3.000 pengguna bersamaan** mengacu pada ASR-1 dan digunakan sebagai asumsi lonjakan pendaftaran kelas pada awal semester. Angka ini perlu dikonfirmasi jika data pengelola tersedia.
2. **95% respons kurang dari 3 detik** mengikuti target ASR-1 untuk halaman daftar kelas dan proses pendaftaran.
3. **Ketersediaan minimal 99,5%** mengacu pada ASR-2. Pada bulan 30 hari dengan 17 jam layanan per hari, total waktu layanan adalah 510 jam. Batas ketidaktersediaan sebesar 0,5% setara dengan 2,55 jam.
4. **Pemulihan kurang dari 30 menit** mengacu pada ASR-2 untuk layanan akses materi dan pengumuman.
5. **100% akses tanpa hak ditolak dan dicatat** mengacu pada ASR-3.
6. **Minimal 100 skenario keamanan** merupakan rancangan pengujian kelompok, bukan bukti bahwa sistem bebas dari semua kerentanan.
7. **Pengujian dilakukan pada lingkungan uji atau prototipe.** Target di atas bukan hasil pengukuran nyata SPADA UMI-Kalam sebelum pengujian dilakukan.

## B2.3 Keterkaitan dengan Bagian Lain

- **B1:** Performance, Availability, dan Security merupakan tiga karakteristik pendorong.
- **A4:** ASR-1 menetapkan target kinerja; ASR-2 menetapkan target ketersediaan dan pemulihan; ASR-3 menetapkan pembatasan akses materi.
- **A5:** ADR-001 mendukung Performance melalui caching dan load balancing. ADR-002 mendukung Security melalui RBAC, pemeriksaan keanggotaan kelas, dan pencatatan log. Availability menjadi pertimbangan dalam pemantauan dan pemulihan layanan sesuai ASR-2.
- **B4:** Performance dipetakan ke Performance Efficiency, Availability ke Reliability, dan Security ke Security pada ISO/IEC 25010.
- **B5:** Target pada B2 menjadi dasar analisis Performance vs Security dan Availability vs Security.

Atribut terukur ini digunakan untuk mengevaluasi apakah rancangan arsitektur memenuhi target kualitas yang ditetapkan pada A4.
