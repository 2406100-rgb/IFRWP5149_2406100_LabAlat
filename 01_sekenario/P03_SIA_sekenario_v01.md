# DESKRIPSI SKENARIO

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalani validasi untuk memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan dengan status menunggu persetujuan dosen wali. Setelah pengajuan tersimpan, mahasiswa dapat memilih untuk mengunduh bukti pengajuan. Dosen wali bertugas menyetujui atau menolak KRS serta memberikan catatan keputusan.

# TABEL KEBUTUHAN

| ID | Kebutuhan Tugas |
|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah. |
| SIA-R02 | Admin Akademik dapat mengelola jadwal kuliah. |
| SIA-R03 | Mahasiswa dapat mengajukan KRS. |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari proses pengajuan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS. |

# BATASAN SISTEM DAN ATURAN

1. Pengguna telah terautentikasi.
2. Data mata kuliah, prasyarat, dan jadwal sudah tersedia.
3. Jika validasi gagal, pengajuan belum berhasil disimpan.
4. Mengunduh bukti bukan syarat keberhasilan pengajuan KRS.
5. KRS yang sudah tersimpan belum tentu disetujui.
6. Pembayaran, pengisian nilai, dan implementasi basis data tidak termasuk dalam tugas ini.

# TABEL IDENTIFIKASI AKTOR

| Aktor | Tujuan terhadap Sistem |
|---|---|
| Admin Akademik | Mengelola jadwal kuliah. |
| Mahasiswa | Melihat jadwal kuliah, mengajukan KRS, memilih mata kuliah, dan memilih untuk mengunduh bukti pengajuan. |
| Dosen Wali | Memeriksa pengajuan KRS, menyetujui atau menolak pengajuan, serta memberikan catatan keputusan. |

# TABEL KATALOG USE CASE

| ID | Nama Use Case | Aktor |
|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik |
| SIA-UC03 | Ajukan KRS | Mahasiswa |
| SIA-UC04 | Validasi KRS | Sistem |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali |

# RELASI INCLUDE

**1. Ajukan KRS dan Validasi KRS**

`SIA-UC03 «include» SIA-UC04`

Alasan: Validasi kelengkapan, prasyarat mata kuliah, dan benturan jadwal selalu dilakukan sebagai bagian dari proses pengajuan KRS.

**2. Proses Keputusan KRS dan Validasi KRS**

`SIA-UC06 «include» SIA-UC04`

Alasan: Validasi KRS digunakan sebagai bagian pemeriksaan sebelum dosen wali memberikan keputusan persetujuan atau penolakan.

# RELASI EXTEND

**Use Case:** Unduh Bukti Pengajuan KRS

`SIA-UC05 «extend» SIA-UC03`

- **Extension point:** Bukti pengajuan tersedia.
- **Kondisi:** Mahasiswa memilih untuk mengunduh bukti pengajuan.
- **Alasan:** Pengajuan KRS tetap dapat berhasil disimpan meskipun mahasiswa tidak mengunduh bukti.