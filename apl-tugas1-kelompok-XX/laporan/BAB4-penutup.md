
# BAB IV. PENUTUP

## 4.1 Kesimpulan

Berdasarkan hasil analisis arsitektur perangkat lunak pada layanan kelas SPADA UMI-Kalam, dapat disimpulkan bahwa layanan kelas memiliki peran penting dalam mendukung kegiatan pembelajaran daring di Universitas Muslim Indonesia. Analisis difokuskan pada empat fungsi utama, yaitu pendaftaran kelas, unggah materi, akses materi, dan pengumuman, yang melibatkan mahasiswa dan dosen sebagai pengguna utama.

Hasil analisis mengidentifikasi tiga karakteristik arsitektur yang menjadi prioritas, yaitu kinerja (*Performance*), ketersediaan (*Availability*), dan keamanan (*Security*). Ketiga karakteristik tersebut menjadi dasar dalam merumuskan kebutuhan arsitektur yang signifikan atau *Architecturally Significant Requirements* (ASR), serta menentukan atribut kualitas yang dapat diukur untuk mengevaluasi rancangan sistem.

Dalam mendukung kebutuhan tersebut, dirumuskan dua keputusan arsitektur melalui *Architecture Decision Record* (ADR), yaitu penerapan caching dan load balancing untuk meningkatkan kinerja layanan pendaftaran kelas, serta penerapan *Role-Based Access Control* (RBAC) dan pencatatan akses untuk melindungi materi perkuliahan dari pengguna yang tidak berwenang.

Analisis trade-off menunjukkan bahwa peningkatan kinerja dan ketersediaan perlu mempertimbangkan aspek keamanan. Oleh karena itu, rancangan arsitektur harus menyeimbangkan kebutuhan kualitas tersebut agar layanan dapat mendukung aktivitas pembelajaran secara optimal tanpa mengabaikan perlindungan hak akses pengguna.

Secara keseluruhan, hasil analisis ini memberikan dasar pertimbangan dalam merancang arsitektur layanan kelas SPADA UMI-Kalam yang lebih terarah, terukur, dan sesuai dengan kebutuhan pengguna. Keputusan yang dihasilkan masih berupa usulan rancangan sehingga memerlukan validasi lebih lanjut sebelum diterapkan pada sistem sebenarnya.

## 4.2 Saran

Berdasarkan hasil analisis yang telah dilakukan, terdapat beberapa saran untuk pengembangan dan evaluasi layanan kelas SPADA UMI-Kalam sebagai berikut:

1. **Melakukan pengujian kinerja layanan.** Pengujian beban perlu dilakukan untuk mengevaluasi kemampuan layanan pendaftaran kelas dalam menangani akses pengguna secara bersamaan, terutama pada awal semester. Pengujian dapat menggunakan Apache JMeter atau k6 dengan mengacu pada target kinerja yang telah ditetapkan.

2. **Meningkatkan pemantauan dan pemulihan layanan.** Mekanisme monitoring, redundansi, dan pemulihan sistem perlu dipertimbangkan untuk mendukung ketersediaan akses materi serta pengumuman selama kegiatan perkuliahan berlangsung.

3. **Memperkuat pengelolaan hak akses.** Penerapan RBAC dan pemeriksaan keanggotaan kelas perlu dievaluasi secara berkala untuk memastikan materi perkuliahan hanya dapat diakses oleh pengguna yang memiliki izin. Pencatatan log juga perlu dikelola dengan baik untuk mendukung pemeriksaan keamanan.

4. **Melakukan validasi kebutuhan dengan pihak terkait.** Hasil analisis dan asumsi yang digunakan sebaiknya dikonfirmasi melalui wawancara atau diskusi lanjutan dengan mahasiswa, dosen, dan pengelola sistem agar rancangan arsitektur lebih sesuai dengan kondisi serta kebutuhan layanan yang sebenarnya.

5. **Melakukan evaluasi terhadap keputusan arsitektur.** Setiap keputusan yang telah didokumentasikan dalam ADR perlu ditinjau kembali apabila terdapat perubahan kebutuhan, peningkatan jumlah pengguna, atau hasil pengujian yang menunjukkan perlunya penyesuaian rancangan.

Dengan mempertimbangkan saran tersebut, hasil analisis arsitektur diharapkan dapat menjadi referensi untuk pengembangan dan evaluasi layanan kelas SPADA UMI-Kalam pada tahap selanjutnya.
