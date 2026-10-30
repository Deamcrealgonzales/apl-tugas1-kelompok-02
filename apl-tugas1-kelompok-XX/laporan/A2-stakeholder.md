# A2. Stakeholder dan Peta Power/Interest

Penanggung jawab: Nur Annisa Az Zahra Diponegoro

Stakeholder adalah pihak-pihak yang terlibat atau memiliki kepentingan terhadap layanan kelas di SPADA UMI-Kalam. Layanan ini digunakan untuk pendaftaran kelas, unggah materi, akses materi, dan pengumuman. Pengaruh (*power*) dinilai dari kemampuan memengaruhi keputusan, bukan dari jumlah pengguna. Kepentingan (*interest*) dinilai dari seberapa besar pihak tersebut terdampak oleh layanan.

## Stakeholder Register

| No. | Stakeholder | Kelompok | Kebutuhan utama | Ekspektasi kualitas | Power / Interest | Prioritas |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Mahasiswa | Pengguna akhir | Mendaftar ke kelas, mengakses dan mengunduh materi, menerima pengumuman tepat waktu | Akses materi cepat saat banyak pengguna bersamaan; layanan selalu tersedia; hanya peserta kelas yang dapat membuka materi | Rendah / Tinggi | Tinggi |
| 2 | Dosen pengampu | Pengguna akhir | Membuka kelas, mengunggah materi, mengatur akses, mengirim pengumuman ke peserta | Unggah berhasil dan tidak gagal di tengah jalan; pengumuman sampai ke semua peserta; materi aman dari pihak tidak berhak | Tinggi / Tinggi | Tinggi |
| 3 | Pengembang dan administrator sistem (PDTI) | Tim pengembang | Kode dan konfigurasi mudah dirawat dan diubah, terintegrasi dengan sistem akademik kampus | Struktur modul jelas; pembaruan tidak mengganggu layanan; keputusan arsitektur terdokumentasi | Tinggi / Tinggi | Tinggi |
| 4 | Admin prodi/fakultas dan helpdesk | Tim operasional | Mengelola daftar kelas dan peserta, menangani kendala pengguna | Layanan mudah dipantau; masalah dapat ditelusuri lewat log; penanganan kendala cepat | Rendah / Tinggi | Sedang |
| 5 | Pimpinan universitas dan fakultas | Manajer bisnis | Perkuliahan daring berjalan lancar setiap semester, laporan penggunaan, biaya terkendali | Layanan stabil, terutama awal kuliah dan masa ujian; biaya wajar | Tinggi / Rendah | Sedang |
| 6 | Regulator dan lembaga akreditasi | Pihak eksternal | Bukti pelaksanaan pembelajaran yang dapat diaudit | Data pembelajaran tersimpan, utuh, dan dapat ditelusuri | Tinggi / Rendah | Sedang |
| 7 | Penyedia infrastruktur pihak ketiga | Pihak eksternal | Penggunaan jaringan dan hosting sesuai kontrak dan batas kapasitas | Beban sesuai kesepakatan; tidak ada penyalahgunaan | Rendah / Rendah | Rendah |

## Peta Power/Interest (Mendelow)

![Peta power/interest stakeholder layanan kelas SPADA UMI-Kalam](A2-stakeholder-diagram.drawio.png)

## Strategi Tiap Kuadran

| Kuadran | Stakeholder | Strategi | Tindakan |
| --- | --- | --- | --- |
| Manage closely | Dosen pengampu; pengembang dan admin PDTI | Libatkan dalam setiap keputusan penting | Dosen menguji fitur unggah materi dan pengumuman sebelum rilis; PDTI meninjau dan menyetujui setiap ADR |
| Keep satisfied | Pimpinan; regulator dan akreditasi | Puaskan tanpa membebani detail teknis | Laporan ringkas tiap semester (ketersediaan, jumlah kelas aktif, insiden); data pembelajaran siap diaudit |
| Keep informed | Mahasiswa; admin prodi dan helpdesk | Beri informasi dan kumpulkan umpan balik | Umumkan jadwal pemeliharaan lebih dulu, beri panduan singkat, sediakan formulir keluhan atau survei |
| Monitor | Penyedia infrastruktur pihak ketiga | Pantau seperlunya | Cek kapasitas dan kontrak secara berkala |
