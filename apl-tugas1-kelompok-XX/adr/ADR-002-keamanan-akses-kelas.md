# ADR-002: Penerapan Role-Based Access Control dan Pencatatan Akses Kelas

- **Status:** Diusulkan
- **Tanggal:** 30-10-2026
- **Pengambil keputusan:** Siti Nur Alfiyyah (pengusul, menunggu persetujuan kelompok)

## Context

Layanan kelas SPADA UMI-Kalam melibatkan dosen, mahasiswa, dan administrator yang memiliki kewenangan berbeda dalam mengelola serta mengakses informasi kelas.

Berdasarkan ASR-3, materi kelas hanya boleh diakses oleh dosen pengampu dan mahasiswa yang terdaftar pada kelas tersebut. Seluruh percobaan akses tanpa hak harus ditolak dan dicatat dalam log.

Oleh karena itu, sistem memerlukan mekanisme otorisasi yang memeriksa peran dan keanggotaan kelas pada setiap permintaan akses terhadap materi.

## Decision

Kami akan menerapkan Role-Based Access Control (RBAC) yang dikombinasikan dengan pemeriksaan keanggotaan kelas dan pencatatan akses.

Pengaturan akses meliputi:
- Mahasiswa dapat mengakses materi dan pengumuman kelas yang diikutinya.
- Dosen dapat mengunggah dan mengelola materi serta pengumuman pada kelas yang diampunya.
- Administrator memiliki kewenangan administratif sesuai kebutuhan pengelolaan sistem, tanpa otomatis memperoleh izin membaca seluruh materi kelas.
- Sistem memeriksa identitas, peran, dan keanggotaan kelas pada setiap permintaan akses materi.
- Setiap percobaan akses tanpa hak ditolak dan dicatat dalam log.

## Consequences

Dampak positif:
- Melindungi materi perkuliahan dari akses tidak sah.
- Memastikan pengguna hanya menjalankan fungsi sesuai kewenangannya.
- Mempermudah penelusuran percobaan akses yang ditolak melalui log.
- Mendukung penerapan keamanan secara konsisten pada layanan kelas.

Dampak negatif:
- Menambah proses pemeriksaan otorisasi pada setiap permintaan.
- Membutuhkan penyimpanan dan pengelolaan log akses.
- Kesalahan pengaturan peran atau keanggotaan dapat menghambat akses pengguna yang berwenang.

Trade-off yang diterima adalah tambahan waktu pemrosesan dan penggunaan sumber daya demi menjaga keamanan akses materi kelas.

## Compliance

- Melakukan pengujian hak akses untuk peran mahasiswa, dosen, dan administrator.
- Memastikan mahasiswa tidak dapat membuka materi kelas yang tidak diikutinya.
- Memastikan dosen hanya dapat mengelola materi pada kelas yang menjadi tanggung jawabnya.
- Memastikan 100% percobaan akses tanpa hak pada skenario pengujian ditolak dan tercatat dalam log.
- Melakukan pemeriksaan penerapan otorisasi pada setiap fungsi akses materi.
