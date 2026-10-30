# B5. Analisis Trade-off

**Penanggung jawab:** Siti Nur Alfiyyah

Analisis trade-off dilakukan untuk mengidentifikasi hubungan antara karakteristik arsitektur yang saling memengaruhi pada layanan kelas SPADA UMI-Kalam. Analisis mengacu pada tiga karakteristik pendorong B1 dan target terukur B2, yaitu Performance, Availability, dan Security.

## 1. Trade-off antara Performance dan Security

### Penjelasan

Performance berkaitan dengan kecepatan sistem merespons permintaan, sedangkan Security memastikan materi hanya dapat diakses oleh pengguna yang berwenang.

Penerapan RBAC dan pemeriksaan keanggotaan kelas dapat menambah waktu pemrosesan karena sistem harus memvalidasi hak akses sebelum memberikan materi. Sebaliknya, menghilangkan pemeriksaan demi mempercepat respons dapat membuka peluang akses tidak sah.

### Dampak

- Pemeriksaan otorisasi meningkatkan perlindungan materi kelas.
- Pemeriksaan tambahan berpotensi meningkatkan waktu respons.
- Optimasi pemeriksaan diperlukan agar mekanisme keamanan tidak menjadi hambatan kinerja.
- Caching dan load balancing dapat membantu kinerja, tetapi tidak boleh melewati validasi akses.

### Keputusan Prioritas

**Security diprioritaskan ketika terjadi konflik yang mengancam hak akses materi.** Pemeriksaan otorisasi tetap dilakukan pada setiap permintaan akses materi. Optimasi kinerja dilakukan tanpa menghilangkan pemeriksaan tersebut.

### Alasan

Keputusan ini mendukung ASR-3 dan ADR-002. Target Performance pada ASR-1 tetap diupayakan melalui mekanisme caching dan load balancing yang dijelaskan dalam ADR-001.

## 2. Trade-off antara Availability dan Security

### Penjelasan

Availability memastikan layanan tetap dapat digunakan ketika dibutuhkan, sedangkan Security membatasi akses kepada pengguna yang memiliki izin.

Ketergantungan pada komponen autentikasi atau otorisasi dapat memengaruhi ketersediaan layanan. Jika komponen pemeriksaan akses mengalami gangguan, pengguna yang sah berpotensi tidak dapat membuka materi meskipun penyimpanan materi masih berfungsi.

### Dampak

- Pemeriksaan akses melindungi materi dari pengguna tidak berwenang.
- Gangguan komponen keamanan dapat menghambat akses pengguna yang sah.
- Melewati pemeriksaan otorisasi untuk mempertahankan akses dapat meningkatkan risiko keamanan.
- Pemantauan, redundansi, dan pemulihan komponen penting memerlukan sumber daya serta pengelolaan tambahan.

### Keputusan Prioritas

**Security diprioritaskan untuk perlindungan materi ketika komponen otorisasi mengalami gangguan.** Sistem tidak boleh memberikan akses materi tanpa verifikasi izin yang sah.

Untuk menjaga Availability, rancangan perlu mempertimbangkan pemantauan, redundansi komponen penting, dan mekanisme pemulihan.

### Alasan

Keputusan ini mendukung ASR-3 mengenai penolakan akses tanpa hak dan ASR-2 mengenai ketersediaan minimal 99,5% serta waktu pemulihan kurang dari 30 menit.

## 3. Ringkasan Keputusan Trade-off

| Pasangan Karakteristik | Prioritas ketika terjadi konflik | Dampak dan mitigasi |
|---|---|---|
| Performance vs Security | Security untuk akses materi | Pemeriksaan hak akses menambah proses, tetapi tetap wajib dilakukan. Kinerja dioptimalkan tanpa menghilangkan otorisasi. |
| Availability vs Security | Security untuk akses materi | Gangguan otorisasi dapat menghambat akses. Ketersediaan dijaga melalui pemantauan, redundansi, dan pemulihan tanpa melewati pemeriksaan keamanan. |

Berdasarkan analisis tersebut, Security diprioritaskan pada kondisi yang mengancam perlindungan materi kelas. Prioritas ini tidak berarti Performance dan Availability diabaikan. Keduanya tetap harus memenuhi target yang telah ditetapkan pada ASR-1, ASR-2, dan B2.
