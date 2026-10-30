Penanggung jawab: [Nur Annisa Az Zahra Diponegoro]
# B2. Atribut Kualitas yang Terukur

Layanan yang dianalisis: **layanan kelas di SPADA UMI-Kalam** (pendaftaran kelas, unggah materi, akses materi, dan pengumuman).

Tiga karakteristik pendorong yang diukur di bawah ini adalah **Kinerja**, **Ketersediaan**, dan **Keamanan**. Ketiganya dipilih dari kebutuhan stakeholder pada A2: mahasiswa menuntut akses materi cepat dan layanan selalu ada, sedangkan dosen menuntut materi aman dari akses pihak yang tidak berhak.

## B2.1 Tabel Atribut Terukur

| Karakteristik pendorong | Atribut terukur (angka target) | Kondisi pengukuran | Cara mengukur / menguji |
| --- | --- | --- | --- |
| **Kinerja** | 95% halaman daftar materi kelas tampil penuh dalam **< 3 detik**, dan unduhan materi (berkas ≤ 10 MB) mulai berjalan dalam **< 3 detik** | **1.500 pengguna aktif bersamaan** (mahasiswa membuka kelas pada awal jam kuliah atau saat dosen baru mengunggah materi), dengan jaringan kampus normal dan data sebanyak satu semester berjalan | **Uji beban** di lingkungan uji (bukan sistem produksi kampus) memakai alat seperti Apache JMeter atau k6: skenario login → buka kelas → buka daftar materi → unduh materi. Hitung persentil ke-95 waktu respons dari 3 kali uji; target lolos bila persentil ke-95 < 3 detik pada ketiganya |
| **Ketersediaan** | Layanan kelas dapat diakses **≥ 99,5% per bulan** pada jam layanan 06.00–23.00 WITA (17 jam × 30 hari = 510 jam, sehingga henti tak terjadwal maksimum ± 2,5 jam per bulan) | Pemeliharaan terjadwal yang diumumkan ≥ 24 jam sebelumnya tidak dihitung sebagai henti; pengukuran mencakup masa padat (awal semester dan pekan ujian) | **Pemantauan uptime** otomatis (pemeriksaan tiap 1 menit ke halaman login dan halaman kelas) selama 30 hari berturut-turut, lalu hitung persentase menit tersedia dari log pemantauan; dibandingkan dengan laporan insiden helpdesk |
| **Keamanan** | **100%** percobaan membuka materi kelas oleh pengguna **tanpa login** atau **bukan peserta kelas** ditolak (respons 401/403), dan **100%** penolakan serta setiap akses unggah tercatat di log (waktu, akun, kelas) | Pada semua fitur kelas (daftar materi, unduh, unggah, pengumuman) dengan peran mahasiswa terdaftar, mahasiswa bukan peserta, dosen pengampu, dan tanpa akun | **Uji akses berbasis skenario** di lingkungan uji atau prototipe memakai akun uji milik kelompok sendiri: minimal 100 skenario (50 tanpa login, 50 akun bukan peserta); lolos bila 0 skenario berhasil membuka materi dan seluruh penolakan muncul di log. Ditambah tinjauan konfigurasi hak akses oleh PDTI |

## B2.2 Dasar Penetapan Angka dan Asumsi

- **Jumlah pengguna bersamaan (1.500)** adalah **asumsi** perancangan untuk lonjakan di awal jam kuliah. Sesuaikan dengan keterangan responden atau data dari pengelola SPADA UMI-Kalam bila tersedia (tulis sumbernya sebagai R1, R2, dst.).
- **Batas 3 detik** mengikuti pola contoh pada Lampiran A tugas dan umum dipakai sebagai batas kenyamanan akses halaman web.
- **Ketersediaan 99,5%** dipilih karena layanan kelas dipakai harian, tetapi tidak sekritis layanan seperti pembayaran; 0,5% dari 510 jam = 2,55 jam per bulan.
- **Keamanan 100%** dipilih karena kebocoran materi atau akses oleh bukan peserta tidak dapat ditoleransi sama sekali.

## B2.3 Keterkaitan dengan Bagian Lain

- Kinerja dan ketersediaan menjadi dasar ASR tentang lonjakan akses saat awal kuliah (A4) dan keputusan pemisahan penyimpanan berkas/materi dari aplikasi utama (A5).
- Keamanan menjadi dasar ASR tentang hak akses per peserta kelas (A4).
- Tiga karakteristik pendorong ini harus sama dengan yang dipilih pada **B1**, dan dipetakan ke ISO/IEC 25010 pada **B4** (Kinerja → *Performance efficiency*; Ketersediaan → *Reliability*; Keamanan → *Security*).

