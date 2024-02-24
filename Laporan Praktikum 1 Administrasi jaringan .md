<h1 align="center">
LAPORAN PRAKTIKUM WORKSHOP

**ADMINISTRASI JARINGAN**
</h1>
<p align="center">
“Instalasi Debian 12”
</p>

<p align="center">
    <img src="img/cover.png" alt="Cover Image" width="480" height="420">
</p>

<h4 align="center">
   
Disusun Oleh:

**Gede Hari Yoga Nanda  					3122500005**

**Handaru Dwiki Yuntara     				3122500017**

**Muhammad Syahrul Ramadhan				3122500030**
</h4>

<h3 align="center">  
   
2 D3 INFORMATIKA A


DEPARTEMEN TEKNIK INFORMATIKA DAN KOMPUTER JURUSAN TEKNIK INFORMATIKA
POLITEKNIK ELEKTRONIKA NEGERI SURABAYA

2023/2024
</h3>



**SOAL:**

Buatlah tulisan tentang langkah-langkah instalasi sistem operasi Debian. Anda bisa menggunakan aplikasi virtualisasi seperti VirtualBox, VMWare Player, Vmware Fusion (MAC), dls. Kebutuhan sistem adalah sebagai berikut :

1. CPU : 2 core
1. RAM : 4096 (min)
1. HDD : 25 GB dengan partisi :
   1. / : 20 GB
   1. /storage : 5 GB
   1. swap : 1,5 GB

- Langkah pertama beri nama direktori SysAdmin dan taruh direktori sesuai keinginan anda lalu masukan iso debian 12. berikut link downloadnya: [Debian -- Downloading Debian](https://www.debian.org/download) 

<p align="center">
    <img src="img/setup_1.png" alt="setup1" width="500" height="300">
</p>



- Lalu beri nama hostname dengan format: “SysAdmin-NRP” berikan username dan dan password sesuai keinginan anda lalu sesuaikan semua form dengan gambar dibawah ini:


<p align="center">
    <img src="img/setup_2.png" alt="setup2" width="500" height="300">
</p>


- Set disk size 20 GB sesuai dengan instruksi soal

<p align="center">
    <img src="img/setup_3.png" alt="setup3" width="500" height="300">
</p>



- Ini adalah summary dari data yang sudah kita set sebelumnya. pastikan sesuai dengan spesifikasi yang ditentukan sebelumnya

<p align="center">
    <img src="img/setup_4.png" alt="setup4" width="500" height="300">
</p>

- Lalu sesuaikan penggunaan RAM 4GB dan Processor  2 CPU sesuai dengan persyaratan minimum. Jika device memumpuni maka lebihi agar lebih lancar.


<p align="center">
    <img src="img/setup_5.png" alt="setup5" width="500" height="300">
</p>


- Lalu pilih graphical Install dan akan muncul seperti dibawah berikut. setelah itu pilih bahasa english dan american english sesuai dengan gambar


<p align="center">
    <img src="img/1.PNG" alt="" width="500" height="300">
</p>


- Masukan hostname sesuai dengan hostname instalasi “SysAdmin-NRP” 

<p align="center">
    <img src="img/2.PNG" alt="" width="500" height="300">
</p>

- Kosongi bagian domain name 

<p align="center">
    <img src="img/3.PNG" alt="" width="500" height="300">
</p>

- Masukan user dan password sesuai dengan prefrensi anda

<p align="center">
    <img src="img/4.PNG" alt="" width="400" height="300">
    <img src="img/5.PNG" alt="" width="400" height="300">
</p>

- Masukan clock pacific dan pilih partition method secara manual dan lalu pilih yes

<p align="center">
   <img src="img/7.PNG" alt="" width="400" height="300">
     <img src="img/8.PNG" alt="" width="400" height="300">
</p>

- Setelah itu pilih menu seperti dibawah ini lalu pilih create new partition sebesar 20GB 

  <p align="center">
     <img src="img/11.PNG" alt="" width="400" height="300">
  <img src="img/12.PNG" alt="" width="400" height="300">
    <img src="img/10.PNG" alt="" width="400" height="300">
</p>

- Pilih bootable flag agar on dan pilih menu done setting up the partition
  
<p align="center">
    <img src="img/13.PNG" alt="" width="400" height="300">
    <img src="img/14.PNG" alt="" width="400" height="300">
</p>

- Setelah itu buat partition baru dengan jenis partition disk primary dengan size 5GB

  <p align="center">
    
    <img src="img/15.PNG" alt="" width="400" height="300">
    <img src="img/16.PNG" alt="" width="400" height="300">
    <img src="img/17.PNG" alt="" width="400" height="300">
    <img src="img/18.PNG" alt="" width="400" height="300">
    
</p>

- Pilih menu use as dan pilih pilih enter manually dan ganti dengan “/storage” setelah itu pilih menu done setting up the partition

  <p align="center">
    
    <img src="img/19.PNG" alt="" width="400" height="300">
    <img src="img/20.PNG" alt="" width="400" height="300">
    <img src="img/21.PNG" alt="" width="400" height="300">
    <img src="img/22.PNG" alt="" width="400" height="300">
    
</p>

- Lalu hasilnya seperti ini. setelah itu tambahkan lagi new partition

 <p align="center">  
    <img src="img/23.PNG" alt="" width="400" height="300">
</p>

- Masukan size partition 1,5GB lalu pilih menu use as dan pilih swap area setelah itu pilih done setting up the partition
   <p align="center">  
   <img src="img/24.PNG" alt="" width="400" height="300">
   <img src="img/26.PNG" alt="" width="400" height="300">
   <img src="img/27.PNG" alt="" width="400" height="300">
    <img src="img/25.PNG" alt="" width="400" height="300">
</p>

- Setelah itu akan tampil seperti dibawah ini. lalu jika selesai pilih done setting up the partition

<p align="center">  
    <img src="img/28.PNG" alt="" width="400" height="300">
</p>

- Setelah semua selesai pastikan semua settingan partition seperti dibawah berikut. Jika sesuai pilih finish partitioning and write changes to disk lalu pilih yes

<p align="center">  
    <img src="img/29.PNG" alt="" width="400" height="300">
    <img src="img/30.PNG" alt="" width="400" height="300">
</p>

- pilih package manager dari deb.debian.org lalu pilih no untuk configure 

<p align="center">  
   <img src="img/32.PNG" alt="" width="400" height="300">
    <img src="img/31.PNG" alt="" width="400" height="300">
</p>

- Kosongi HTTP Proxy dan pilih continue untuk melanjutkan instalasi

<p align="center">  
   <img src="img/33.PNG" alt="" width="400" height="300">
    <img src="img/34.PNG" alt="" width="400" height="300">
</p>

- Centang web server dan SSH server lalu continue lalu pilih yes untuk install GRUB

  <p align="center">  
   <img src="img/35.PNG" alt="" width="400" height="300">
   <img src="img/tambahan.png" alt="" width="400" height="300">
</p>

- Setelah selesai install GRUB pilih menu seperti dibawah ini. lalu pilih continue tunggu sampai instalasi selesai

  <p align="center">  
   <img src="img/36.PNG" alt="" width="400" height="300">
</p>

- Maka akan tampil seperti dibawah jika instalasi selesai.

  <p align="center">  
   <img src="img/37.PNG" alt="" width="400" height="300">
</p>

- Pilih Debian GNU/Linux pada menu lalu login dengan password yang sudah di inputkan

  <p align="center">  
   <img src="img/38.PNG" alt="" width="400" height="300">
   <img src="img/39.PNG" alt="" width="400" height="300">
</p>






  2\.  Buat ringkasan tentang perbedaan dari Debian 12 (bookworm) dengan Debian 11 (bullseye) : versi kernel, kebutuhan sistem, penerapan systemd dan perbedaan packagenya (dalam bentuk tabel) !

|Variabel|Debian 12 (bookworm)|Debian 11 (bullseye)|
| :- | :- | :- |
|Versi Kernel|5\.15.X|5\.10.X|
|Kebutuhan sistem|Mungkin memebutuhkan lebih banyak sumber daya (tergantung pada perubahan spesifik)|` `Lebih ringan, mungkin membutuhkan lebih dikit sumber daya|
|Penerapan System|Penggunaan system terus diterapkan dan dioptimalkan|Penerapan system dengan versi yang lebih lama dan mungkin memiliki beberapa perbedaan konfigurasi|
|Perbedaan Paket|Mungkin termasuk versi perangat lunak yang lebih baru dan perbaikan keamanan yang lebih baru|Paket mungkin tidak se-up-to-date dengan versi terbaru dan perbaikan keamanan yang terbaru|


3\. Jelaskan fungsi dari file "/etc/groups" beserta formatnya!

File "/etc/group" adalah salah satu file konfigurasi pada sistem Linux yang mengelola informasi tentang grup pengguna. Fungsi utamanya adalah menyimpan daftar grup yang ada di sistem beserta informasi terkait setiap grup. Berikut adalah penjelasan tentang format dan fungsi dari file "/etc/group":

isi file :

  <p align="center">  
   <img src="img/nomor_3.png" alt="" width="500" height="400">
</p>

### <a name="_p7du05ek0398"></a>**Fungsi:**
1. **Mengelola Grup Pengguna:** File "/etc/group" digunakan untuk mengelola grup-grup pengguna pada sistem Linux. Setiap baris dalam file ini mewakili satu grup, dan setiap grup memiliki beberapa atribut yang terkait dengannya seperti nama grup, ID grup, anggota grup, dan grup administrator.
1. **Akses dan Hak Akses:** File "/etc/group" juga berperan dalam mengatur akses ke berbagai sumber daya sistem seperti file dan direktori. Grup-grup yang terdaftar dalam file ini dapat digunakan untuk memberikan atau membatasi akses pengguna terhadap file dan direktori tertentu.
   ### <a name="_vq34ovtdnkxi"></a>**Format:**
Setiap baris dalam file "/etc/group" memiliki format sebagai berikut:

makefileCopy code

nama\_grup:password:ID\_grup:daftar\_anggota:grup\_administrator


- **nama\_grup:** Nama dari grup pengguna.
- **password:** Biasanya digunakan untuk menyimpan password grup, tetapi saat ini sering diisi dengan 'x' yang menunjukkan bahwa informasi password tersimpan dalam file **/etc/gshadow** atau **/etc/shadow**.
- **ID\_grup:** Nomor identifikasi unik (numerik) untuk grup.
- **daftar\_anggota:** Daftar pengguna yang merupakan anggota dari grup, dipisahkan oleh koma.
- **grup\_administrator:** Pengguna yang memiliki hak administratif terhadap grup. Biasanya kosong atau diisi dengan nama pengguna yang menjadi administrator grup.

Contoh baris dalam file "/etc/group":

bashCopy code

users:x:100:john,jane:admin


Di sini:

- Nama grup adalah "users".
- Password diwakili oleh "x" yang menunjukkan bahwa password tersimpan dalam file terpisah.
- ID grup adalah 100.
- Anggota grup adalah "john" dan "jane".
- Administrator grup adalah "admin".

File "/etc/group" hanya dapat diakses oleh pengguna root untuk menghindari modifikasi yang tidak sah oleh pengguna lain yang dapat menyebabkan masalah keamanan.

4\. Jelaskan perbedaan penggunaan perintah "su" dengan "su -"!

 <p align="center">  
   <img src="img/nomor_4.png" alt="" width="500" height="400">
</p>

- **su**:
  - Ketika menjalankan **su** tanpa opsi tambahan, itu akan mengganti pengguna (user) Anda saat ini dengan pengguna lain (biasanya root).
  - Lingkungan (environment) saat ini, seperti direktori kerja (working directory), variabel lingkungan, dan sebagainya, tetap tidak berubah. Ini berarti Anda masih tetap berada di lingkungan pengguna (user environment) yang Anda gunakan sebelumnya.
- **su -**:
  - Ketika Anda menjalankan **su -** (dengan opsi dash **``**), itu akan mengganti pengguna (user) Anda saat ini dengan pengguna lain (biasanya root) dan menginisialisasi lingkungan baru untuk pengguna tersebut.
  - Lingkungan baru yang diinisialisasi mencakup pengaturan lingkungan standar yang biasanya dimiliki oleh pengguna tersebut, seperti direktori kerja (working directory) yang akan diatur ke direktori home pengguna baru, serta pengaturan variabel lingkungan lainnya seperti **PATH**.
  - Ini membuatnya mirip dengan masuk ke sesi shell baru sebagai pengguna tersebut.



5\. Jelaskan fungsi dari "sudo" !

contoh penggunaan sudo untuk mengatur hak akses :

 <p align="center">  
   <img src="img/nomor_5.png" alt="" width="400" height="350">
</p>

Perintah **sudo** (singkatan dari "superuser do") adalah utilitas yang umum digunakan dalam sistem Unix dan Linux untuk memberikan hak akses superuser (atau hak akses root) kepada pengguna biasa untuk menjalankan perintah atau menjalankan program dengan hak akses yang diperlukan. Ini memberikan fleksibilitas dalam manajemen hak akses di lingkungan multi-pengguna, di mana tidak semua pengguna perlu memiliki akses penuh ke sistem.

Berikut adalah beberapa fungsi utama dari **sudo**:

1. **Eksekusi Perintah dengan Hak Akses Root**: Salah satu fungsi utama dari **sudo** adalah memberikan pengguna biasa kemampuan untuk menjalankan perintah atau program yang membutuhkan hak akses root tanpa harus masuk ke akun root. Ini membantu mencegah penggunaan akun root yang berlebihan, yang dapat meningkatkan keamanan sistem.
1. **Audit dan Pelacakan Aktivitas Pengguna**: **sudo** biasanya dapat dikonfigurasi untuk memantau dan mencatat aktivitas pengguna. Ini memungkinkan administrator sistem untuk melakukan audit dan pelacakan terhadap perintah yang dijalankan oleh pengguna, membantu dalam investigasi insiden keamanan atau pemecahan masalah.
1. **Kontrol Akses yang Diberikan**: **sudo** memungkinkan administrator untuk mengatur dengan tepat hak akses yang diberikan kepada pengguna. Ini dapat dilakukan dengan memperbolehkan atau membatasi penggunaan **sudo** untuk perintah atau program tertentu, atau bahkan mengatur waktu tertentu di mana akses **sudo** diizinkan.
1. **Pemisahan Tugas Administratif**: Dengan **sudo**, tugas administratif pada sistem Linux dapat dibagi-bagi di antara beberapa pengguna tanpa perlu memberikan semua pengguna hak akses root. Sebagai contoh, seorang administrator jaringan dapat memberikan hak akses **sudo** kepada seorang pengguna untuk mengelola pengguna-pengguna lokal tanpa memberikan akses ke bagian-bagian lain dari sistem.
1. **Melakukan Perintah Sebagai Pengguna Lain**: Selain menjalankan perintah sebagai root, **sudo** juga dapat digunakan untuk menjalankan perintah sebagai pengguna lain, dengan asumsi bahwa pengguna tersebut memiliki hak akses yang diperlukan untuk menjalankan perintah tersebut.

6\. Jelaskan langkah-langkah penambahan user anda sebagai user sudo ! Gunakan perintah "su -" lalu setelah masuk sebagai root, jalankan perintah "visudo". Tambahkan user anda di bawah user root pada bagian " # User privilege specification"

1. Buka terminal atau command prompt di sistem Linux.
1. Masuk sebagai pengguna root dengan perintah **su -** dan masukkan kata sandi root saat diminta:
1. ​​Setelah Anda masuk sebagai root, jalankan perintah visudo untuk mengedit file sudoers dengan pengamanan:
1. Ini akan membuka file sudoers dalam editor teks yang terkonfigurasi untuk sistem Anda. Jangan menggunakan editor teks biasa untuk mengedit file ini karena kesalahan dalam file sudoers dapat menyebabkan masalah yang serius.
1. ` `Di dalam file sudoers, cari bagian yang disebut "User privilege specification". Biasanya, bagian ini berada di bawah komentar yang dimulai dengan "# User privilege specification".
1. ` `Di bawah baris yang mencantumkan hak akses root, tambahkan baris baru untuk menambahkan hak akses sudo untuk pengguna. Misalnya, karena nama user saya handarudwiking maka saya masukkan itu:
1. Artinya, "handarudwiking" diberikan izin untuk menjalankan semua perintah (ALL) sebagai semua pengguna ((ALL)) dan dalam semua terminal ((ALL)).
1. Save Konfigurasi dan keluar

   <img src="img/nomor_6a.png" alt="" width="600"></p>
1.
     
<img src="img/nomor_6b.png" alt="" width="600">


lalu cek dengan perintah sudo apa berhasil dibawah ini tidak berhasil karena saya sudah hapus tulisan diatas untuk versi yang berhasil ada di gambar yang atas	


<img src="img/nomor_6c.png" alt="" width="600" >


