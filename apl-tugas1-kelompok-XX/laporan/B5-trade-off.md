
# B5. Analisis Trade-off

**Penanggung jawab:** Siti Nur Alfiyyah

Analisis trade-off dilakukan untuk mengetahui hubungan antara karakteristik arsitektur yang saling memengaruhi pada layanan kelas SPADA UMI-Kalam. Analisis ini mengacu pada tiga kebutuhan signifikan secara arsitektural (ASR), yaitu kinerja (Performance), ketersediaan (Availability), dan keamanan (Security).

## 1. Trade-off antara Performance dan Security

**Penjelasan:**

Performance berkaitan dengan kecepatan sistem dalam memproses permintaan pengguna, sedangkan Security bertujuan melindungi materi dan informasi kelas dari akses yang tidak berwenang.

Penerapan Role-Based Access Control (RBAC) dan pemeriksaan keanggotaan kelas meningkatkan keamanan, tetapi menambah proses pemeriksaan pada setiap permintaan. Hal ini berpotensi memengaruhi waktu respons sistem ketika banyak mahasiswa mengakses layanan secara bersamaan.

**Dampak:**
- Pemeriksaan hak akses membantu mencegah pengguna yang tidak berwenang mengakses materi kelas.
- Proses otorisasi tambahan dapat meningkatkan waktu respons sistem.
- Mengurangi pemeriksaan keamanan demi mempercepat akses dapat meningkatkan risiko akses tidak sah.

**Keputusan Prioritas:**

Security diprioritaskan dibandingkan Performance untuk akses materi kelas. Sistem tetap melakukan pemeriksaan hak akses pada setiap permintaan meskipun membutuhkan waktu pemrosesan tambahan. Untuk menjaga kinerja, sistem dapat mengoptimalkan pemeriksaan otorisasi tanpa menghilangkan validasi keamanan.

**Alasan:**

Keputusan ini mendukung ASR-3 yang mewajibkan seluruh percobaan akses tanpa hak ditolak dan dicatat dalam log. Selain itu, sistem tetap perlu memperhatikan target kinerja pada ASR-1, yaitu 95% proses pendaftaran kelas selesai dalam waktu kurang dari 3 detik saat 3.000 mahasiswa mengakses layanan secara bersamaan.

## 2. Trade-off antara Availability dan Security

**Penjelasan:**

Availability berkaitan dengan kemampuan sistem untuk tetap menyediakan layanan ketika dibutuhkan, sedangkan Security memastikan bahwa hanya pengguna yang memiliki izin yang dapat mengakses materi dan informasi kelas.

Penerapan autentikasi dan otorisasi meningkatkan keamanan, tetapi dapat menimbulkan ketergantungan pada komponen pemeriksaan akses. Apabila komponen tersebut mengalami gangguan, mahasiswa dan dosen yang memiliki izin berpotensi tidak dapat mengakses layanan meskipun komponen lainnya masih berfungsi.

**Dampak:**
- Pemeriksaan akses melindungi materi kelas dari pengguna yang tidak berwenang.
- Gangguan pada komponen autentikasi atau otorisasi dapat mengurangi ketersediaan layanan.
- Mengabaikan pemeriksaan keamanan untuk mempertahankan akses dapat meningkatkan risiko penyalahgunaan sistem.

**Keputusan Prioritas:**

Security diprioritaskan untuk melindungi akses materi kelas. Sistem tidak boleh melewati pemeriksaan otorisasi ketika komponen keamanan mengalami gangguan. Untuk menjaga Availability, sistem perlu menerapkan pemantauan, redundansi komponen penting, dan mekanisme pemulihan layanan.

**Alasan:**

Keputusan ini mendukung ASR-3 mengenai keamanan akses materi sekaligus mempertimbangkan ASR-2 yang menetapkan ketersediaan layanan minimal 99,5% pada pukul 06.00–23.00 WITA dan waktu pemulihan kurang dari 30 menit.

## 3. Ringkasan Keputusan Trade-off

| Pasangan Karakteristik | Karakteristik Prioritas | Alasan |
|---|---|---|
| Performance vs Security | Security | Pemeriksaan hak akses tetap diperlukan untuk melindungi materi kelas meskipun menambah waktu pemrosesan. |
| Availability vs Security | Security | Akses tanpa izin harus tetap ditolak meskipun komponen keamanan mengalami gangguan. Ketersediaan dijaga melalui redundansi dan mekanisme pemulihan. |

Berdasarkan analisis tersebut, Security menjadi prioritas dalam kedua trade-off karena perlindungan akses materi merupakan kebutuhan signifikan pada layanan kelas SPADA UMI-Kalam. Meskipun demikian, Performance dan Availability tetap diperhatikan agar layanan dapat digunakan secara cepat dan tersedia ketika dibutuhkan.
