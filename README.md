## Pratikum 12

## Membuat table dan database

![](foto/13.PNG)

##  Konfigurasi koneksi database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. 
Konfigurasi dapat dilakukan dengan du acara, yaitu pada file app/config/database.php
atau menggunakan file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env. 

![](foto/14.PNG)

## Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada 
direktori app/Models dengan nama ArtikelModel.php

![](foto/15.PNG)

## Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.

![](foto/16.PNG)

## Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file 
baru dengan nama index.php.

![](foto/17.PNG)

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikeL

![](foto/18.PNG)

Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada 
database agar dapat ditampilkan datanya.

![](foto/19.PNG)

Refresh kembali browser, sehingga akan ditampilkan hasilnya.

![](foto/20.PNG)

## Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. 
Tambahkan fungsi baru pada Controller Artikel dengan nama view().

![](foto/21.PNG)

## Membuat View Detail
Buat view baru untuk halaman detail dengan nama app/views/artikel/detail.php.

![](foto/22.PNG)

## Membuat Routing untuk artikel detail
Buka Kembali file app/config/Routes.php, kemudian tambahkan routing untuk artikel 
detail.

![](foto/23.PNG)

refresh kembali browser, dan liat hasilnya

![](foto/24.PNG)

## Membuat Menu Admin
Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada 
Controller Artikel dengan nama admin_index().

![](foto/25.PNG)

## Selanjutnya buat view untuk tampilan admin dengan nama admin_index.php

![](foto/26.PNG)

Tambahkan routing untuk menu admin 

![](foto/27.PNG)

Akses menu admin dengan url http://localhost:8080/admin/artikel

![](foto/28.PNG)

## Menambah Data Artikel
Tambahkan fungsi/method baru pada Controller Artikel dengan nama add().

![](foto/29.PNG)

Kemudian buat view untuk form tambah dengan nama form_add.php

![](foto/30.PNG)

refresh browser dan liat hasilnya

![](foto/31.PNG)

## Mengubah Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama edit().

![](foto/32.PNG)

Kemudian buat view untuk form tambah dengan nama form_edit.php

![](foto/33.PNG)

refresh browser dan liat hasilnya

![](foto/34.PNG)

## Menghapus Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama delete().

![](foto/35.PNG)


## Pratikum 13

## Langkah - Langkah Pratikum
Persiapan.
Untuk memulai membuat modul Login, yang perlu disiapkan adalah database server 
menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui 
XAMPP.

## Membuat Tabel User

![](foto/36.PNG)

## Membuat Model User
Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada 
direktori app/Models dengan nama UserModel.php

![](foto/37.PNG)

## Membuat Controller User
Buat Controller baru dengan nama User.php pada direktori app/Controllers.
Kemudian tambahkan method index() untuk menampilkan daftar user, dan method 
login() untuk proses login.

![](foto/38.PNG)

## Membuat View Login
Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file 
baru dengan nama login.php.

![](foto/39.PNG)

## Membuat Database Seeder
Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul 
login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat 
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:

![](foto/40.PNG)

Selanjutnya, buka file UserSeeder.php yang berada di lokasi direktori 
/app/Database/Seeds/UserSeeder.php kemudian isi dengan kode berikut:

![](foto/41.PNG)

Selanjutnya buka kembali CLI dan ketik perintah berikut:

![](foto/42.PNG)

## Uji Coba Login
Selanjutnya buka url http://localhost:8080/user/login seperti berikut:

![](foto/47.PNG)

## Menambahkan Auth Filter
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php
pada direktori app/Filters.

![](foto/43.PNG)

Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:

![](foto/44.PNG)

Selanjutnya buka file app/Config/Routes.php dan sesuaikan kodenya

![](foto/45.PNG)

##  Percobaan Akses Menu Admin
Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut 
diakses maka, akan dimuculkan halaman login.

![](foto/47.PNG)

## Fungsi Logout
Tambahkan method logout pada Controller User seperti berikut:

![](foto/46.PNG)

## Pratikum 14

## Langkah-langkah Praktikum
# Membuat Pagination
Pagination merupakan proses yang digunakan untuk membatasi tampilan yang panjang 
dari data yang banyak pada sebuah website. Fungsi pagination adalah memecah 
tampilan menjadi beberapa halaman tergantung banyaknya data yang akan ditampilkan 
pada setiap halaman.
Pada Codeigniter 4, fungsi pagination sudah tersedia pada Library sehingga cukup 
mudah menggunakannya.
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi 
kode pada method admin_index seperti berikut.

![](foto/48.PNG)

Kemudian buka file views/artikel/admin_index.php dan tambahkan kode berikut
dibawah deklarasi tabel data

<?= $pager->links(); ?>

Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat 
hasilnya.

![](foto/49.PNG)

## Membuat Pencarian
Pencarian data digunakan untuk memfilter data.
Untuk membuat pencarian data, buka kembali Controller Artikel, pada method 
admin_index ubah kodenya seperti berikut

![](foto/50.PNG)

Kemudian buka kembali file views/artikel/admin_index.php dan tambahkan form 
pencarian sebelum deklarasi tabel seperti berikut:

<form method="get" class="form-search">
 <input type="text" name="q" value="<?= $q; ?>" placeholder="Cari data">
 <input type="submit" value="Cari" class="btn btn-primary">
</form>

Dan pada link pager ubah seperti berikut.

<?= $pager->only(['q'])->links(); ?>

Selanjutnya ujicoba dengan membuka kembali halaman admin artikel, masukkan kata 
kunci tertentu pada form pencarian.

![](foto/51.PNG)

## Upload Gambar
Menambahkan fungsi unggah gambar pada tambah artikel. Buka kembali Controller 
Artikel, sesuaikan kode pada method add seperti berikut:

![](foto/52.PNG)

Kemudian pada file views/artikel/form_add.php tambahkan field input file seperti 
berikut.

 <p>
 <input type="file" name="gambar">
</p>

Dan sesuaikan tag form dengan menambahkan ecrypt type seperti berikut.

<form action="" method="post" enctype="multipart/form-data">

Ujicoba file upload dengan mengakses menu tambah artikel

![](foto/53.PNG)  
  
  

