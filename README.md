# Sistem Manajemen Perpustakaan

## Tim Pengembang
| No | NIM | Nama | Peran |
|----|-----|------|-------|
| 1 | G64190038 | Rafida Nisa Maghfiroh | Analis Sistem |
| 2 | G64190081 | Andra Setiyo Wicaksono | Tester |
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

## Analisis Berorientasi Objek

### Identifikasi Aktor
| No | Aktor | Deskripsi |
|----|-------|-----------|
| 1 | Pustakawan | Aktor yang bertanggung jawab untuk menambahkan buku, menambahkan buku, menambah user, dan menghapus user |
| 2 | Antarmuka | Aktor yang berperan menampilkan objek antarmuka yang ada di dalam sistem kepada pustakawan |

### Identifikasi User Stories
| No | Aktor | User Story | Acceptance Criteria | 
|----|-------|------------|---------------------|
| 1 | Pustakawan | Sebagai seorang pustakawan, saya ingin menambahkan buku ke dalam list buku | Buku berhasil ditambahkan ke dalam list buku |
| | | Sebagai seorang pustakawan, saya ingin menghapus buku yang ada dalam list buku | Buku berhasil dihapus dari list buku |
| | | Sebagai seorang pustakawan, saya ingin menambahkan user yang ingin meminjam buku | User berhasil ditambahkan |
| | | Sebagai seorang pustakawan, saya ingin menghapus user yang telah mengembalikan buku | User berhasil dihapus |

### Identifikasi Use Case
| No | Aktor | Use Case | Brief Description | 
|----|-------|------------|---------------------|
| 1 | Pustakawan | Menambah buku | Pustakawan dapat menambahkan data buku ke dalam list buku untuk dimasukkan ke dalam database |
| | | Menghapus buku | Pustakawan dapat menghapus buku dari list buku |
| | | Menambah user | Pustakawan dapat menambahkan user yang ingin meminjam buku |
| | | Menghapus user | Pustakawan dapat menghapus user yang telah mengembalikan buku |
| | | Cari buku | Pustakawan dapat mencari buku pada kolom search berdasarkan judul buku, penulis, dan ISBN |
| | | Lihat buku | Pustakawan dapat melihat buku-buku yang ada pada list buku |
| | | Cari user | Pustakawan dapat mencari user pada kolom search berdasarkan nama, id user, dan buku yang dipinjam |
| | | Lihat user | Pustakawan dapat melihat daftar user |

### Use Case Diagram
![Use Case Diagram](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Use%20Case%20Diagram1.jpg)



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


### Pembuatan Activity Diagram

#### Pinjam Buku
![Pinjam Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/pinjam%20buku.png)

#### Mengembalikan Buku
![Mengembalikan Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/mengembalikan%20buku.png)

#### Menambah User
![Menambah User](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/tambah%20user.png)

#### Menambah Buku
![Menambah Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/tamba%20buku.png)

#### Mencari Buku
![Mencari Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/cari%20buku.png)

### Analysis of Things
| No | Things | Attributes | Kandidat Class |
|----|--------|------------|----------------|
| 1 | Buku | Judul, kategori, penerbit, jumlah halaman, jumlah stok, nomor isbn | Buku |
| 2 | Mahasiswa | Nama, nomor telfon, NIM,  jurusan, email | User, Mahasiswa |
| 3 | Dosen | Nama, nomor telfon, departemen,  jurusan, email | User, Dosen |
| 4 | Peminjaman | Buku | Pinjam |

### Class Diagram
![Class Diagram](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Perpustakaan%20Manajemen%20Sistem.jpeg)

## Desain Berorientasi Objek

### Design Principle
| Komponen | Deskripsi (Rincian + Alasan) |
|----------|------------------------------|
| Architecture Pattern | Layered Pattern kami gunakan pada sistem ini agar mempermudah pengelompokan subtask dan memperkecil kompleksitas dari sistem |
| Design Pattern | Builder untuk membentuk objek, Visitor untuk memanggil method dari objek lain |


### Sequence Diagram

#### Menambah Buku
![Menambah Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Add%20Book.jpg)

#### Menambah User
![Menambah User](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Add%20User.jpg)

#### Pinjam Buku
![Pinjam Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Borrow%20Book.jpg)

#### Mencari Buku
![Mencari Buku](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Search%20Book.jpg)

#### Mencari User
![Mencari User](https://github.com/andrawicaksonoipb/psbo-team-5/blob/andra/img/Search%20User.jpg)

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

