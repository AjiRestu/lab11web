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

Sekian dan terima kasih




