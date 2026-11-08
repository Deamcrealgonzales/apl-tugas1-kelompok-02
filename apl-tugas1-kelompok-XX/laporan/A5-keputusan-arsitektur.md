# A5. Keputusan Arsitektur dan ADR

**Penanggung jawab:** Siti Nur Alfiyyah

Bagian ini menjelaskan keputusan arsitektur untuk layanan kelas SPADA UMI-Kalam yang mencakup pendaftaran kelas, unggah materi, akses materi, dan pengumuman. Keputusan didokumentasikan dalam bentuk Architecture Decision Record (ADR) agar alasan pemilihan, dampak, dan cara pemeriksaannya dapat ditelusuri oleh seluruh anggota kelompok.

## 1. Ringkasan ADR-001: Penerapan Caching dan Load Balancing pada Pendaftaran Kelas

- **Status:** Diterima
- **ASR terkait:** ASR-1 (Kinerja dan Kapasitas)
- **ADR lengkap:** [ADR-001-kinerja-pendaftaran-kelas.md](../adr/ADR-001-kinerja-pendaftaran-kelas.md)

### Context

Berdasarkan ASR-1, layanan pendaftaran kelas harus mampu menangani 3.000 mahasiswa yang mengakses sistem secara bersamaan pada awal semester. Sebanyak 95% halaman daftar kelas dan proses pendaftaran ditargetkan selesai dalam waktu kurang dari 3 detik. Lonjakan pengguna dapat meningkatkan beban server dan basis data sehingga diperlukan mekanisme untuk menjaga kinerja.

### Decision

Kami akan menerapkan caching pada data daftar kelas yang sering dibaca dan load balancing untuk mendistribusikan permintaan ke beberapa server aplikasi. Proses pendaftaran tetap divalidasi melalui basis data utama agar konsistensi data terjaga.

### Consequences

**Dampak positif:**
- Mempercepat akses halaman daftar kelas.
- Mengurangi beban pembacaan berulang pada basis data.
- Membantu menangani lonjakan pengguna secara bersamaan.

**Dampak negatif:**
- Membutuhkan sumber daya server dan konfigurasi tambahan.
- Menambah kompleksitas pengelolaan sistem.
- Memerlukan pembaruan cache agar informasi kelas tidak kedaluwarsa.

**Trade-off:** Peningkatan kinerja diperoleh dengan menerima tambahan kompleksitas infrastruktur, tanpa mengorbankan konsistensi pendaftaran kelas.

### Compliance

Kepatuhan diperiksa melalui uji beban dengan 3.000 pengguna bersamaan, pengukuran persentil ke-95 waktu respons kurang dari 3 detik, serta pengujian distribusi beban, pembaruan cache, dan konsistensi data pendaftaran.

## 2. Ringkasan ADR-002: Penerapan Role-Based Access Control dan Pencatatan Akses Kelas

- **Status:** Diusulkan
- **ASR terkait:** ASR-3 (Keamanan Akses)
- **ADR lengkap:** [ADR-002-keamanan-akses-kelas.md](../adr/ADR-002-keamanan-akses-kelas.md)

### Context

Berdasarkan ASR-3, materi kelas hanya boleh diakses oleh dosen pengampu dan mahasiswa yang terdaftar pada kelas tersebut. Seluruh percobaan akses tanpa hak harus ditolak dan dicatat dalam log. Pemeriksaan login saja tidak cukup karena pengguna yang telah masuk belum tentu memiliki izin mengakses materi kelas lain.

### Decision

Kami akan menerapkan Role-Based Access Control (RBAC) berdasarkan peran mahasiswa, dosen, dan admin, disertai pemeriksaan keanggotaan kelas pada setiap permintaan akses materi. Percobaan akses tanpa hak akan ditolak dan dicatat dalam log.

### Consequences

**Dampak positif:**
- Melindungi materi kelas dari akses tidak berwenang.
- Memperjelas pembatasan hak akses berdasarkan peran dan keanggotaan kelas.
- Memudahkan penelusuran kejadian keamanan melalui log.

**Dampak negatif:**
- Pemeriksaan otorisasi menambah proses pada setiap permintaan.
- Perubahan keanggotaan kelas membutuhkan pembaruan hak akses.
- Penyimpanan log memerlukan pengelolaan tambahan.

**Trade-off:** Keamanan akses materi diprioritaskan meskipun pemeriksaan otorisasi menambah waktu pemrosesan.

### Compliance

Kepatuhan diperiksa melalui pengujian akses berdasarkan peran dan keanggotaan kelas. Seluruh skenario akses tanpa hak harus ditolak dan dicatat dalam log. Tinjauan kode dilakukan untuk memastikan pemeriksaan otorisasi diterapkan pada sisi server.

## 3. Rencana Komunikasi Keputusan Arsitektur

1. **Lokasi dokumentasi:** ADR lengkap disimpan pada folder `adr/` dalam repository GitHub kelompok, sedangkan ringkasannya dicantumkan pada bagian A5.
2. **Penerima informasi:** Seluruh anggota kelompok, terutama penanggung jawab ASR, karakteristik arsitektur, analisis trade-off, dan diagram arsitektur.
3. **Mekanisme komunikasi:** Keputusan dibahas bersama anggota terkait dan setiap perubahan didokumentasikan melalui pembaruan ADR serta riwayat commit GitHub.
4. **Perubahan keputusan:** Jika terdapat keputusan baru yang menggantikan keputusan sebelumnya, status ADR lama diperbarui dan dibuat ADR pengganti yang menjelaskan alasan perubahan.

### Pencegahan Antipattern Komunikasi

- **Covering Your Assets:** ADR digunakan untuk mendokumentasikan alasan teknis, alternatif, dan konsekuensi keputusan, bukan untuk mencari pihak yang disalahkan ketika terjadi masalah.
- **Groundhog Day:** Keputusan yang telah didokumentasikan menjadi acuan agar kelompok tidak mengulang diskusi yang sama tanpa adanya informasi baru.
- **Email-Driven Architecture:** Keputusan penting tidak hanya disampaikan melalui pesan pribadi atau percakapan, tetapi harus dicatat secara resmi dalam berkas ADR di repository GitHub.

Dengan dokumentasi tersebut, keputusan arsitektur dapat ditelusuri, diperiksa, dan digunakan sebagai acuan bersama dalam merancang layanan kelas SPADA UMI-Kalam.
