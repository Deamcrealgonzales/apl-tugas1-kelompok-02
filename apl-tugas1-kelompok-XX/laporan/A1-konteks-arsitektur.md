# A1. Analisis Empat Konteks Arsitektur

Penanggung jawab: [Dea Mcreal Gonzales]
| Konteks | Kondisi pada Sistem | Dampak terhadap Arsitektur |
|---|---|---|
| **Teknis** | Layanan kelas pada SPADA UMI-Kalam digunakan untuk pendaftaran kelas, unggah materi, akses materi, dan pengumuman yang membutuhkan koneksi internet. | Arsitektur perlu memperhatikan integrasi dengan layanan SPADA yang sudah ada, pengelolaan data, penyimpanan materi, serta hak akses pengguna. |
| **Siklus Hidup Proyek** | Layanan kelas merupakan bagian dari platform SPADA UMI-Kalam yang sudah berjalan sehingga perubahan perlu mempertahankan fungsi yang telah tersedia. | Arsitektur perlu mendukung pemeliharaan dan pengembangan fitur secara bertahap tanpa mengganggu aktivitas perkuliahan. |
| **Bisnis** | Sistem mendukung kegiatan pembelajaran di UMI dengan membantu dosen membagikan materi dan pengumuman serta mahasiswa mendaftar dan mengakses kelas. | Arsitektur perlu mengutamakan kemudahan penggunaan, ketersediaan layanan, dan pengelolaan kelas yang efisien. |
| **Profesional** | Sistem melibatkan mahasiswa, dosen, administrator SPADA, dan tim IT yang memiliki tugas serta hak akses berbeda. | Arsitektur perlu memperhatikan pembagian hak akses, kemudahan pemeliharaan, dokumentasi, dan kemampuan tim dalam mengelola sistem. |

---
