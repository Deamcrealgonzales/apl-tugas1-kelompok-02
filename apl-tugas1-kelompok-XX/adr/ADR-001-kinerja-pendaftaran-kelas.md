# ADR-001: Penerapan Caching dan Load Balancing pada Pendaftaran Kelas

- **Status:** Diusulkan
- **Tanggal:** 30-10-2026
- **Pengambil keputusan:** Siti Nur Alfiyyah (pengusul, menunggu persetujuan kelompok)

## Context

Layanan kelas SPADA UMI-Kalam digunakan mahasiswa untuk melakukan pendaftaran kelas pada awal semester. Pada periode tersebut, jumlah pengguna dapat meningkat secara bersamaan sehingga menimbulkan beban tinggi pada server dan basis data.

Berdasarkan ASR-1, sistem ditargetkan mampu melayani 3.000 mahasiswa secara bersamaan dengan 95% halaman daftar kelas dan proses pendaftaran selesai dalam waktu kurang dari 3 detik.

Kondisi tersebut membutuhkan rancangan arsitektur yang mampu menangani lonjakan permintaan tanpa mengganggu proses pendaftaran kelas.

## Decision

Kami akan menerapkan mekanisme caching dan load balancing untuk meningkatkan kinerja layanan pendaftaran kelas.

Caching digunakan untuk menyimpan sementara informasi daftar kelas yang sering diakses, sehingga permintaan berulang tidak selalu diproses oleh basis data utama.

Load balancing digunakan untuk mendistribusikan permintaan pengguna ke beberapa server aplikasi agar beban pemrosesan tidak terpusat pada satu server.

Proses pendaftaran yang mengubah data keanggotaan kelas tetap divalidasi dan disimpan pada basis data utama untuk menjaga konsistensi data serta mencegah pendaftaran ganda.

## Consequences

Dampak positif:
- Mengurangi beban basis data untuk permintaan daftar kelas.
- Membantu mempercepat respons layanan pendaftaran.
- Mendistribusikan beban pengguna ke beberapa server.
- Meningkatkan kemampuan sistem menangani lonjakan akses.

Dampak negatif:
- Membutuhkan sumber daya server tambahan.
- Menambah kompleksitas konfigurasi dan pemeliharaan sistem.
- Memerlukan mekanisme pembaruan cache agar informasi kelas tetap akurat.

Trade-off yang diterima adalah peningkatan kinerja dan kapasitas dengan konsekuensi bertambahnya kompleksitas serta kebutuhan sumber daya. Konsistensi data pendaftaran tetap diprioritaskan melalui validasi pada basis data utama.

## Compliance

- Melakukan pengujian beban dengan simulasi 3.000 pengguna bersamaan.
- Memastikan minimal 95% halaman daftar kelas dan proses pendaftaran selesai dalam waktu kurang dari 3 detik.
- Memantau distribusi permintaan pada setiap server aplikasi.
- Memastikan pembaruan daftar kelas tercermin pada cache.
- Menguji pendaftaran bersamaan agar tidak terjadi data keanggotaan ganda.
