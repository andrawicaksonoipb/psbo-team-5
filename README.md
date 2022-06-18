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




### Pembuatan Fully Developed Use Case Description
| Use Case Name: | Meminjam Buku |
| -------------- | ------------- |
| Scenario: | User/pustakawan  meminjam buku dari perpustakaan. |
| Triggering Event: | User/pustakawan ingin meminjam buku |
| Brief Description: | Peminjam memilih buku, kemudian meminjam buku tersebut hingga batas waktu tertentu. |
| Actor: | Pustakawan, user |
| Related Use Case(s): | - |
| Stakeholders: | User, pustakawan |
| Precondition(s): | Peminjam harus memiliki akun  dan buku harus tersedia untuk dipinjam. |
| Postcondition(s): | Peminjam dapat membaca buku dari aplikasi hingga batas waktu tertentu. |
| Flow of Activities | **Actor** |
|  | 1. User memilih buku yang ingin dipinjam. |
|  | 2. User meminjam buku. |
|  | **System** |
|  | 2.1 Sistem memeriksa apakah buku tersedia dan tidak sedang direservasi. |
|  | 2.2 Sistem menambahkan buku ke user dengan batas waktu tertentu |
|  | 2.3 Sistem menandai buku sedang dipinjam |
| Exception Conditions: | 2.1 Buku sedang dipinjam atau tidak ada di database. |

| Use Case Name: | Mengembalikan Buku |
| -------------- | ------------------ |
| Scenario: | User/pustakawan mengembalikan  buku ke perpustakaan. |
| Triggering Event: | User/pustakawan ingin mengembalikan buku |
| Brief Description: | Peminjam mengembalikan buku ke perpustakaan. |
| Actor: | Pustakawan, user |
| Related Use Case(s): | Meminjam buku |
| Stakeholders: | User, pustakawan |
| Precondition(s): | Peminjam harus mempunyai buku yang akan dikembalikan. |
| Postcondition(s): | Jumlah stok buku bertambah dan buku tidak dipegang peminjam. |
| Flow of Activities | **Actor** |
|  | 1. Peminjam mengembalikan buku. |
|  | **System** |
|  | 1.1 Sistem menambahkan stok buku tersebut. |
|  | 1.2 Sistem menghapus buku dari daftar bacaan user. |
| Exception Conditions | - |

| Use Case Name: | Tambah user |
| -------------- | ----------- |
| Scenario: | Pustakawan menambahkan user baru ke database. |
| Triggering Event: | Ada user yang ingin mendaftarkan diri. |
| Brief Description: | Pustakawan mendaftarkan user baru sebagai member di perpustakaan. |
| Actor: | Pustakawan, user |
| Related Use Case(s): | - |
| Stakeholders: | User, pustakawan |
| Precondition(s): | Calon user belum terdaftar di database. |
| Postcondition(s): | User terdaftar di database. |
| Flow of Activities | **Actor** |
|  | 1. User memberikan data dirinya |
|  | 2. Pustakawan memasukan data diri user ke database |
|  | **System** |
|  | 2.1 Sistem menambahkan data user ke database |
| Exception Conditions: | 2.1.1 User sudah ada di database |
|  | 2.1.2 Data yang dimasukan belum lengkap |

| Use Case Name: | Tambah buku |
| -------------- | ----------- |
| Scenario: | Pustakawan menambah buku di perpustakaan. |
| Triggering Event: | Ada buku baru yang ingin ditambahkan pustakawan. |
| Brief Description: | Pustakawan menambahkan buku baru ke database perpustakaan. |
| Actor: | Pustakawan |
| Related Use Case(s): | Meminjam buku |
| Stakeholders: | Pustakawan, user |
| Precondition(s): | Buku belum ada di database. |
| Postcondition(s): | Buku sudah ditambahkan di database. |
| Flow of Activities | **Actor** |
|  | 1. Pustakawan mengisi data-data dari buku yang akan ditambahkan. |
|  | **System** |
|  | 1.1 Sistem menambahkan data buku baru ke dalam database. |
| Exception Conditions: | Data buku belum diisi lengkap oleh pustakawan. |

| Use Case Name: | Cari  buku |
| -------------- | ---------- |
| Scenario: | Pustakawan mencari buku berdasarkan atributnya. |
| Triggering Event: | - |
| Brief Description: | Pustakawan mencari buku berdasarkan judul, ISBN, atau atribut lainnya. |
| Actor: | Pustakawan |
| Related Use Case(s): | - |
| Stakeholders: | Pustakawan, user |
| Precondition(s): | Pustakawan tahu data buku yang akan dicari. |
| Postcondition(s): | Sistem menampilkan hasil pencarian. |
| Flow of Activities | **Actor** |
|  | 1. Pustakawan memasukan info atribut buku seperti judul, pengarang, ISBN, dll. |
|  | 2. Pustakawan melakukan pencarian. |
|  | **System** |
|  | 2.1 Sistem menjalankan kueri untuk mencari buku tersebut menurut ID-nya. |
| Exception Conditions: | Data yang dimasukan salah atau tidak ada di database. |

## Testing Report
|Class Name:|UIBuku||||
|---|---|---|---|---|
|<strong>Testing Scenario: </strong>|
|Method Name|Input|Expected Output|Actual Output|Results|
|addBookToList|Form terisi penuh|Obyek buku dengan atribut sesuai dengan form|Obyek buku dengan atribut sesuai dengan form|Success|
|addBookToList|Form dengan nilai kosong|Alert “Lengkapi semua data”|Alert “Lengkapi semua data”|Success|
|<strong>Conclusion:</strong>|Testing Success|

|Class Name:|Pinjam||||
|---|---|---|---|---|
|<strong>Testing Scenario: </strong>|
|Method Name|Input|Expected Output|Actual Output|Results|
|pinjamBook|ISBN|Buku ditambahkan ke daftar pinjaman dan stok buku berkurang|Buku ditambahkan ke daftar pinjaman dan stok buku berkurang|Success|
|kembalikanBook|Judul buku|Buku dihapus dari daftar pinjaman dan stok buku bertambah|Buku dihapus dari daftar pinjaman dan stok buku bertambah|Success|
|<strong>Conclusion:</strong>|Testing Success|
