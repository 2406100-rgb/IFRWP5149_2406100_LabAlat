Elemen                             |SIA-UC01 — Ajukan KRS
Tujuan                             |Menghasilkan pengajuan KRS yang tersimpan
Aktor                              |utama Mahasiswa
Sumber kebutuhan                   |Kebutuhan sistem terkait pengajuan KRS
Pemicu                             |Mahasiswa memilih fungsi pengajuan KRS
Prasyarat                          |Mahasiswa telah terautentikasi; data mata kuliah tersedia
Pascakondisi berhasil              |Pengajuan KRS tersimpan dengan nomor dan status Menunggu validasi
Pascakondisi gagal                 |Tidak ada pengajuan KRS baru yang berhasil tersimpan
Include                            |SIA-UC02 — Validasi KRS
Extension point                    |Bukti pengajuan tersedia, pada langkah 6
Extend                             |SIA-UC03 — Unduh Bukti Pengajuan KRS jika [mahasiswa memilih unduh]

Elemen                             |SIA-UC02 — Validasi KRS
Tujuan                             |Memastikan pengajuan KRS sesuai dengan ketentuan akademik
Aktor                              |utama Dosen Wali
Sumber kebutuhan                   |Kebutuhan sistem terkait validasi KRS
Pemicu                             |Dosen Wali memilih fungsi validasi KRS
Prasyarat                          |Dosen Wali telah terautentikasi; pengajuan KRS mahasiswa tersedia
Pascakondisi berhasil              |Pengajuan KRS tersimpan dengan status Disetujui atau Ditolak
Pascakondisi gagal                 |Status pengajuan KRS tidak berubah
Include                            |SIA-UC01 — Ajukan KRS
Extension point                    |Keputusan validasi tersedia, pada langkah 5
Extend                             |SIA-UC04 — Proses Keputusan KRS jika [diperlukan proses keputusan lanjutan]

Elemen                             |SIA-UC03 — Unduh Bukti Pengajuan KRS
Tujuan                             |Menghasilkan bukti pengajuan KRS yang dapat diunduh mahasiswa
Aktor                              |utama Mahasiswa
Sumber kebutuhan                   |Kebutuhan sistem terkait bukti pengajuan KRS
Pemicu                             |Mahasiswa memilih fungsi unduh bukti pengajuan KRS
Prasyarat                          |Mahasiswa telah terautentikasi; pengajuan KRS telah tersimpan
Pascakondisi berhasil              |Bukti pengajuan KRS berhasil diunduh oleh mahasiswa
Pascakondisi gagal                 |Bukti pengajuan KRS tidak berhasil diunduh
Include                            |SIA-UC01 — Ajukan KRS
Extension point                    |Bukti pengajuan siap diunduh, pada langkah 4
Extend                             |Tidak ada

Elemen                             |SIA-UC04 — Proses Keputusan KRS
Tujuan                             |Memproses keputusan akhir terhadap pengajuan KRS mahasiswa
Aktor                              |utama Dosen Wali
Sumber kebutuhan                   |Kebutuhan sistem terkait keputusan KRS
Pemicu                             |Dosen Wali memilih fungsi proses keputusan KRS
Prasyarat                          |Dosen Wali telah terautentikasi; pengajuan KRS telah divalidasi
Pascakondisi berhasil              |Keputusan KRS tersimpan dengan status Disetujui atau Ditolak
Pascakondisi gagal                 |Keputusan KRS tidak berhasil tersimpan
Include                            |SIA-UC02 — Validasi KRS
Extension point                    |Keputusan akhir tersedia, pada langkah 5
Extend                             |Tidak ada