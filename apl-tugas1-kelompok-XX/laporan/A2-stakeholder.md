# A2. Stakeholder dan Peta Power/Interest

Penanggung jawab:[Nur Annisa Az Zahra Diponegoro]

## A2.1 Stakeholder Register

Pengaruh (*power*) dinilai dari kemampuan memengaruhi keputusan arsitektur dan operasional layanan, bukan dari jumlah pengguna. Kepentingan (*interest*) dinilai dari seberapa besar stakeholder terdampak oleh layanan kelas.

| No | Stakeholder | Kelompok | Kebutuhan utama | Ekspektasi kualitas | Power / Interest | Prioritas |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Mahasiswa | Pengguna akhir | Mendaftar ke kelas mata kuliah, mengakses dan mengunduh materi, serta menerima pengumuman dosen tepat waktu | Akses materi cepat meski banyak pengguna bersamaan; layanan selalu tersedia; mudah dipakai dari ponsel; hanya mahasiswa terdaftar yang dapat membuka materi kelas | Rendah / Tinggi | Tinggi |
| 2 | Dosen pengampu | Pengguna akhir | Membuka kelas, mengunggah materi dengan mudah, mengatur siapa yang boleh mengakses, dan mengirim pengumuman ke seluruh peserta kelas | Unggah berkas berhasil dan tidak gagal di tengah jalan; pengumuman terkirim ke semua peserta; materi aman dari akses pihak yang tidak berhak | Tinggi / Tinggi | Tinggi |
| 3 | Pengembang dan administrator sistem SPADA UMI-Kalam (PDTI) | Tim pengembang | Kode dan konfigurasi yang mudah dirawat, mudah diubah saat aturan atau kebutuhan berubah, dan terintegrasi dengan sistem akademik kampus | Struktur modul jelas; pembaruan tidak mengganggu layanan; ada dokumentasi keputusan arsitektur | Tinggi / Tinggi | Tinggi |
| 4 | Admin prodi/fakultas dan *helpdesk* | Tim operasional | Mengelola daftar kelas dan peserta, membantu mahasiswa/dosen yang gagal masuk kelas atau gagal unggah, serta memantau kendala harian | Layanan mudah dipantau; masalah dapat ditelusuri lewat log; penanganan kendala cepat | Rendah / Tinggi | Sedang |
| 5 | Pimpinan universitas dan fakultas (Wakil Rektor bidang akademik, dekan, biro akademik) | Manajer bisnis | Perkuliahan daring berjalan lancar setiap semester; laporan penggunaan; anggaran infrastruktur terkendali | Layanan stabil sepanjang semester, terutama masa awal kuliah dan masa ujian; biaya wajar | Tinggi / Rendah | Sedang |
| 6 | Regulator pendidikan tinggi dan lembaga akreditasi | Pihak eksternal | Bukti pelaksanaan pembelajaran (materi dan aktivitas kelas) yang dapat diaudit | Data pembelajaran tersimpan, utuh, dan dapat ditelusuri | Tinggi / Rendah | Sedang |
| 7 | Penyedia infrastruktur pihak ketiga (jaringan/ISP, hosting, layanan surel atau notifikasi) | Pihak eksternal | Penggunaan layanan sesuai kontrak dan batas kapasitas | Beban dan trafik sesuai kesepakatan; tidak ada penyalahgunaan | Rendah / Rendah | Rendah |

## A2.2 Peta Power/Interest (Mendelow)

quadrantChart
    title Peta Power/Interest Stakeholder Layanan Kelas SPADA UMI-Kalam
    x-axis Power rendah --> Power tinggi
    y-axis Interest rendah --> Interest tinggi
    quadrant-1 Manage closely
    quadrant-2 Keep informed
    quadrant-3 Monitor
    quadrant-4 Keep satisfied
    Mahasiswa: [0.25, 0.90]
    Dosen pengampu: [0.70, 0.88]
    Pengembang dan admin PDTI: [0.88, 0.74]
    Admin prodi dan helpdesk: [0.38, 0.66]
    Pimpinan univ dan fakultas: [0.86, 0.38]
    Regulator dan akreditasi: [0.66, 0.24]
    Penyedia infrastruktur: [0.24, 0.24]
```

*Gambar A2.1. Peta power/interest stakeholder layanan kelas SPADA UMI-Kalam (posisi bersifat rekomendasi).*

**Keterangan peta.** Dosen pengampu dan tim pengembang/administrator PDTI berada pada kuadran *manage closely* karena keduanya menentukan keberhasilan layanan: dosen menentukan apakah materi dan pengumuman benar-benar dipakai, dan PDTI memegang keputusan teknis. Mahasiswa sangat berkepentingan tetapi tidak menentukan keputusan, sehingga cukup diberi informasi dan dimintai umpan balik. Pimpinan dan regulator berpengaruh tinggi tetapi hanya berkepentingan pada hasil akhir, sehingga perlu dipuaskan dengan laporan, bukan dilibatkan dalam urusan teknis harian.

## A2.3 Strategi Tiap Kuadran

| Kuadran | Stakeholder | Strategi | Bentuk tindakan |
| --- | --- | --- | --- |
| Power tinggi, interest tinggi (*Manage closely*) | Dosen pengampu; pengembang dan administrator PDTI | Libatkan dalam setiap keputusan penting | Ajak dosen menguji fitur unggah materi dan pengumuman sebelum rilis; PDTI ikut meninjau setiap ADR dan menjadi pemberi persetujuan keputusan arsitektur |
| Power tinggi, interest rendah (*Keep satisfied*) | Pimpinan universitas/fakultas; regulator dan lembaga akreditasi | Puaskan, jangan dibebani detail teknis | Laporan ringkas tiap semester: ketersediaan layanan, jumlah kelas aktif, dan insiden; sediakan data pembelajaran yang dapat diaudit |
| Power rendah, interest tinggi (*Keep informed*) | Mahasiswa; admin prodi/fakultas dan *helpdesk* | Beri informasi dan kumpulkan umpan balik | Pengumuman jadwal pemeliharaan lebih dulu, panduan singkat penggunaan, formulir keluhan/survei; helpdesk mendapat dokumen penanganan masalah umum |
| Power rendah, interest rendah (*Monitor*) | Penyedia infrastruktur pihak ketiga | Pantau seperlunya | Cek kapasitas dan kontrak secara berkala; libatkan lebih jauh hanya bila kapasitas atau biaya menjadi masalah |
