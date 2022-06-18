# Sistem Manajemen Perpustakaan

## Tim Pengembang
| No | NIM | Nama | Peran |
|----|-----|------|-------|
| 1 | G64190038 | Rafida Nisa Maghfiroh | Analis Sistem |
| 2 | G64190038 | Andra Setiyo Wicaksono | Tester |
| 3 | G64190092 | Ramadhanti Nisa Permahadi | Analis Sistem |
| 4 | G64190096 | Febri Bawahir | Front End Developer |
| 5 | G64190097 | Muhamad Rian Nayandra | Analis Sistem |


## Product Vision Documents

### Problem Description
Perpustakaan adalah salah satu sarana penyediaan sumber-sumber informasi yang dapat digunakan untuk meningkatkan kualitas sumber daya manusia. Dalam Pasal 4 UU Nomor 43 Tahun 2007 tentang perpustakaan disebutkan bahwa perpustakaan bertujuan memberikan layanan kepada pemustaka (pengguna perpustakaan), meningkatkan kegemaran membaca, serta memperluas wawasan dan pengetahuan untuk mencerdaskan kehidupan bangsa. Di sisi lain, teknologi informasi telah menjadi kebutuhan pada berbagai aspek. Oleh karena itu, diperlukan pengembangan untuk mentransformasikan perpustakaan tradisional menjadi perpustakaan digital. 

### Kapabilitas Sistem
Sistem telah mampu melakukan CRUD sederhana untuk melakukan simulasi peminjaman buku. Kelas-kelas yang terlibat dalam simulasi ini adalah Buku, Dosen, Mahasiswa, Pinjam, UI, UIBuku, UIUser, User, Dosen, dan Mahasiswa. UIBuku dan UIUser di sini sebagai anak dari UI. Dosen dan Mahasiswa di sini sebagai anak dari User. Kemudian tugas utama pada sistem ini adalah:
- Mengelola katalog buku
- Mengelola peminjaman buku


### Manfaat Sistem
Sistem dapat digunakan oleh perpustakaan untuk mempermudah peminjaman buku. Dengan menggunakan sistem ini, peminjaman buku pada perpustakaan menjadi semakin terstruktur dan dapat tercatat dengan rapi. Sehingga, tidak perlu lagi mencatat peminjaman buku secara konservatif.

## Analisi Berorientasi Objek

### Analysis of Things
|No |Right columns| Right columns                                                           | Right columns       |
|---|-------------|-------------------------------------------------------------------------|---------------------|
| 1 | Buku        | judul, kategori, penerbit, jumlah halaman, jumlah stok, nomor isbn      | Buku                |
| 2 | Mahasiswa   | nama, nomor telphone, NIM, jurusan, email, status                       | User, Mahasiswa     |
| 3 | Dosen       | nama, nomor telphone, NIM, jurusan, email, status                       | User, Mahasiswa     |
| 4 | Peminjaman  | buku yang dipinjam                                                      | User, Mahasiswa     |

## Desain Berorientasi Object

### Design Principle
|Komponen            |Deskripsi(Rincian + Alasan)                                                                                                 |
|--------------------|----------------------------------------------------------------------------------------------------------------------------|
|Architecture Pattern|Layered Pattern kami gunakan pada sistem ini agar mempermudah pengelompokan subtask dan memperkecil kompleksitas dari sistem|
|Design Pattern      | Builder untuk membentuk objek Visitor untuk memanggil method dari objek lain                                               |
