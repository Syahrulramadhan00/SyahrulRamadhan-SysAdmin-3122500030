
**LAPORAN PRAKTIKUM WORKSHOP** 

**ADMINISTRASI JARINGAN**

“Instalasi Debian 12”

![](image/cover.png)


`  `**Disusun Oleh:**

**Gede Hari Yoga Nanda  					3122500005**

**Handaru Dwiki Yuntara     				3122500017**

**Muhammad Syahrul Ramadhan				3122500030**

` `**2 D3 INFORMATIKA**

**A**
# **DEPARTEMEN TEKNIK INFORMATIKA DAN KOMPUTER JURUSAN TEKNIK INFORMATIKA**
**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA**

**2023/2024**



**SOAL:**

Buatlah tulisan tentang langkah-langkah instalasi sistem operasi Debian. Anda bisa menggunakan aplikasi virtualisasi seperti VirtualBox, VMWare Player, Vmware Fusion (MAC), dls. Kebutuhan sistem adalah sebagai berikut :

1. CPU : 2 core
1. RAM : 4096 (min)
1. HDD : 25 GB dengan partisi :
   1. / : 20 GB
   1. /storage : 5 GB
   1. swap : 1,5 GB

- Langkah pertama beri nama direktori SysAdmin dan taruh direktori sesuai keinginan anda lalu masukan iso debian 12. berikut link downloadnya: [Debian -- Downloading Debian](https://www.debian.org/download) 

`	`![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.002.png)



- Lalu beri nama hostname dengan format: “SysAdmin-NRP” berikan username dan dan password sesuai keinginan anda lalu sesuaikan semua form dengan gambar dibawah ini:


![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.003.png)


- Set disk size 20 GB 

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.004.png)



- Ini adalah summary dari data yang sudah kita set sebelumnya. pastikan sesuai dengan spesifikasi yang ditentukan sebelumnya

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.005.png)

- Lalu sesuaikan penggunaan RAM 4GB dan Processor  2 CPU sesuai dengan persyaratan minimum. Jika device memumpuni maka lebihi agar lebih lancar.

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.006.png)



- Lalu pilih graphical Install dan akan muncul seperti dibawah berikut. setelah itu pilih bahasa english dan american english sesuai dengan gambar

  ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.007.png)

- Masukan hostname sesuai dengan hostname instalasi “SysAdmin-NRP” ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.008.png)



- Kosongi bagian domain name dan masukan password sesuai keinginan anda![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.009.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.010.png)
- Masukan nama user dan password sesuai dengan prefrensi anda

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.011.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.012.png)











- Masukan clock pacific dan pilih partition method secara manual dan lalu pilih yes

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.013.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.014.png)

- Setelah itu pilih menu seperti dibawah ini lalu pilih create new partition sebesar 20GB ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.015.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.016.png)

  ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.017.png)

- Pilih bootable flag agar on dan pilih menu done setting up the partition

  ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.018.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.019.png)

- Setelah itu buat partition baru dengan jenis partition disk primary dengan size 5GB![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.020.png)

  ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.021.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.022.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.023.png)

- Pilih menu use as dan pilih pilih enter manually dan ganti dengan “/storage” setelah itu pilih menu done setting up the partition![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.024.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.025.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.026.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.027.png)
- Lalu hasilnya seperti ini. setelah itu tambahkan lagi new partition

  ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.028.png)

- Masukan size partition 1,5GB lalu pilih menu use as dan pilih swap area setelah itu pilih done setting up the partition
- Setelah itu akan tampil seperti dibawah ini. lalu jika selesai pilih done setting up the partition![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.029.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.030.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.031.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.032.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.033.png)

- Setelah semua selesai pastikan semua settingan partition seperti dibawah berikut. Jika sesuai pilih finish partitioning and write changes to disk lalu pilih yes![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.034.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.035.png)
- pilih package manager dari deb.debian.org lalu pilih no untuk configure ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.036.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.037.png)







- Kosongi HTTP Proxy dan pilih continue untuk melanjutkan instalasi![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.038.png)![ref1]
- Centang web server dan SSH server lalu continue lalu pilih yes untuk install GRUB![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.040.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.041.png)
- Setelah selesai install GRUB pilih menu seperti dibawah ini![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.042.png)
- Maka akan tampil seperti dibawah jika instalasi selesai.![ref2]
- Pilih Debian GNU/Linux pada menu lalu login dengan password yang sudah di inputkan

  ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.044.png)![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.045.png)






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

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.046.png)
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

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.047.png)

- **su**:
  - Ketika menjalankan **su** tanpa opsi tambahan, itu akan mengganti pengguna (user) Anda saat ini dengan pengguna lain (biasanya root).
  - Lingkungan (environment) saat ini, seperti direktori kerja (working directory), variabel lingkungan, dan sebagainya, tetap tidak berubah. Ini berarti Anda masih tetap berada di lingkungan pengguna (user environment) yang Anda gunakan sebelumnya.
- **su -**:
  - Ketika Anda menjalankan **su -** (dengan opsi dash **``**), itu akan mengganti pengguna (user) Anda saat ini dengan pengguna lain (biasanya root) dan menginisialisasi lingkungan baru untuk pengguna tersebut.
  - Lingkungan baru yang diinisialisasi mencakup pengaturan lingkungan standar yang biasanya dimiliki oleh pengguna tersebut, seperti direktori kerja (working directory) yang akan diatur ke direktori home pengguna baru, serta pengaturan variabel lingkungan lainnya seperti **PATH**.
  - Ini membuatnya mirip dengan masuk ke sesi shell baru sebagai pengguna tersebut.



5\. Jelaskan fungsi dari "sudo" !

contoh penggunaan sudo untuk mengatur hak akses :

`	`![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.048.png)

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
1. ![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.049.png)

![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.050.png)


` `lalu cek dengan perintah sudo apa berhasil dibawah ini tidak berhasil karena saya sudah hapus tulisan diatas untuk versi yang berhasil ada di gambar yang atas	![](Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.051.png)


[ref1]: Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.039.png
[ref2]: Aspose.Words.1317805a-9a9b-43e4-8d67-e23820876ef7.043.png
