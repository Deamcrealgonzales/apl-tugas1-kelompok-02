# A4. Kebutuhan Signifikan (ASR)

Penanggung jawab: [Nabila Zahrani Azalea Arief]

| Kode | Jenis | Pernyataan ASR | Mengapa signifikan secara arsitektural |
|------|-------|----------------|----------------------------------------|
| ASR-1 | Atribut kualitas (kinerja dan kapasitas) | Saat pendaftaran kelas dibuka di awal semester, 3.000 mahasiswa mengakses layanan bersamaan, dan 95% halaman daftar kelas serta proses pendaftaran selesai dalam waktu kurang dari 3 detik. | Lonjakan pengguna terjadi serentak pada jadwal tertentu, bukan merata sepanjang semester. Satu server dengan proses sinkron tidak cukup. Arsitektur perlu *caching*, penyeimbang beban (*load balancing*), atau antrean untuk proses pendaftaran. Pilihan ini memengaruhi struktur komponen dan penempatan server. |
| ASR-2 | Atribut kualitas (ketersediaan) | Layanan akses materi dan pengumuman tersedia minimal 99,5% pada jam perkuliahan dan masa ujian (06.00–23.00 WITA), dan layanan pulih dalam waktu kurang dari 30 menit jika terjadi gangguan. | Mahasiswa dan dosen bergantung pada materi dan pengumuman untuk kegiatan belajar harian, dan gangguan terasa langsung di kelas. Target ini memengaruhi keputusan tentang redundansi server, pencadangan (*backup*) berkala, pemantauan layanan, dan prosedur pemulihan. |
| ASR-3 | Atribut kualitas (keamanan akses) | Materi kelas hanya dapat dibuka oleh dosen pengampu dan mahasiswa yang terdaftar pada kelas tersebut. 100% percobaan akses tanpa hak ditolak dan tercatat dalam log. | Materi kuliah adalah karya dosen yang perlu dilindungi. Aturan hak akses berbasis peran (dosen, mahasiswa, admin) harus ditegakkan pada setiap permintaan, bukan hanya pada halaman tertentu. Ini memengaruhi desain modul otorisasi, pengelolaan sesi, dan pencatatan akses di seluruh komponen. |
