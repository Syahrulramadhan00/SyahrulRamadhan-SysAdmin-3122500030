<h1 align="center">
LAPORAN PRAKTIKUM WORKSHOP

**ADMINISTRASI JARINGAN**
</h1>
<p align="center">
“Setting Mikrotik & instalasi package dan manager”
</p>

<p align="center">
    <img src="img/covernobg.png" alt="Cover Image" width="480" height="420">
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

<h2>8.6.1 informasi disk space</h2>
untuk penginformasian dari space disk 
menggunakan terminal mode di debian dengan command 
df -h
 
<p align="center">
    <img src="img/tugas3-1.png" alt="Cover Image" width="480" height="420">
</p>

-	untuk list sorted by decreasing size (ukuran terbesar ke kecil)
du -ms * | sort -nr

 <p align="center">
    <img src="img/tugas3-2.png" alt="Cover Image" width="480" height="420">
</p>

-	Penganalisis ruang disk dalam mode konsol. Untuk menjalankannya, cukup ketik "ncdu" di terminal Anda. Untuk menginstal perangkat lunak ini harus dalam mode admin
apt update && apt install ncdu

 <p align="center">
    <img src="img/tugas3-3.png" alt="Cover Image" width="480" height="420">
</p>

-	baobab
Penganalisis ruang disk dalam mode grafis, terintegrasi di dalam Gnome tetapi tersedia di lingkungan lain dengan
apt update &&apt install baobab
 
<p align="center">
    <img src="img/tugas3-4.png" alt="Cover Image" width="480" height="420">
</p>
<p align="center">
    <img src="img/tugas3-5.png" alt="Cover Image" width="480" height="420">
</p>
 
<h2>8.6.2 cleaning paket</h2>


Apt/aptitude/dpkg adalah manajer paket Debian yang umum digunakan. Saat Anda menginstal paket, file arsip-sumber/deb-nya disimpan di sistem Anda (di folder /var/cache/apt/archives/) untuk memungkinkan penginstalan ulang potensial tanpa koneksi Internet. Untuk membersihkan “apt cache," gunakan perintah sederhana dalam mode administrator (bab 3.8.3).

apt cache

Setelah cache paket yang terinstal dibersihkan, Anda juga dapat menghapus paket-paket yang tidak berguna dari sistem, beserta file konfigurasi mereka. Peringatan! Ingatlah untuk memeriksa dengan teliti daftar paket yang direncanakan untuk dihapus sebelum menerima operasi ini.

apt autoremove –purge

Jika Anda telah melakukan upgrade sistem, mungkin ada paket-paket yang tidak lagi tersedia di repositori baru karena sudah usang. Untuk menampilkan dan menghapus paket-paket tersebut, gunakan apt dan pastikan untuk memeriksa dengan teliti daftar paket yang direncanakan untuk dihapus.

apt list ‘?absolete’
apt remove ‘?absolete’

untuk menampilkan dan membersihkan file konfigurasi yang tetap ada meskipun aplikasi telah dihapus, Anda dapat menggunakan perintah-perintah berikut:

 <p align="center">
    <img src="img/tugas3-6.png" alt="Cover Image">
</p>

lebih detail, dapat menginstal alat deborphan yang mencantumkan paket-paket terlantar di sistem Anda
 
<p align="center">
    <img src="img/tugas3-7.png" alt="Cover Image">
</p>

<h2>8.6.3 kosongkan trash bin</h2>


Tiga tempat sampah file yang berbeda harus diperhatikan:

-	Tempat sampah pengguna: ~/.local/share/Trash/. Anda dapat mengosongkannya dengan manajer file sistem atau melalui terminal.
 <p align="center">
    <img src="img/tugas3-8.png" alt="Cover Image">
</p>

-	Tempat sampah administrator: /root/.local/share/Trash/. Untuk mengosongkannya dengan cara yang benar, gunakan terminal dalam mode administrator:
 <p align="center">
    <img src="img/tugas3-9.png" alt="Cover Image">
</p>

-	Tempat sampah eksternal: terletak pada disk eksternal Anda, biasanya dinamai '/media/y- our_id/your_disk/.Trash_1000', di mana your_id sesuai dengan nama login Anda.


<h2>8.6.4 mengosongkan cache aplikasi </h2>

beberapa aplikasi menggunakan folder cache untuk menyimpan gambar, video dll dari aplikasi. dimana akan menghabiskan banyak disk jadi dihapus saja gapapa dengan menggunakan command : 
 <p align="center">
    <img src="img/tugas3-10.png" alt="Cover Image">
</p>

<h2>8.6.5 membersihkan thumbnails</h2>


Setiap kali Anda membuka folder yang berisi gambar atau video, thumbnail dibuat untuk mewakili file grafis tersebut. Thumbnail ini disimpan di folder khusus untuk digunakan kembali.Permasalahannya muncul ketika Anda menghapus file grafis, karena thumbnail-nya tetap ada di sistem, dan ini menyebabkan ruang disk terbuang untuk menyimpan thumbnail yang sudah lama.
Untuk membersihkannya, cukup hapus folder 
 <p align="center">
    <img src="img/tugas3-11.png" alt="Cover Image">
</p>

<h2>8.7.1 instalasi Graphic mode dengan GDebi</h2>

GDebi adalah utilitas grafis yang memungkinkan instalasi paket eksternal dengan format ".deb", sambil mengelola dependensinya. Untuk menginstalnya, cari "gdebi" di manajer paket seperti Synaptic, Discover, Software atau lebih mudahnya lagi dari terminal dalam mode administrator dengan menggunakan perintah "su"

apt update && apt install gdebi

setelah terdownload klik kanan dan select open with gdebi

 <p align="center">
    <img src="img/tugas3-12.png" alt="Cover Image" width="480" height="420">
</p>

dalam menu dalam, klik file lalu open dan enter path .deb file
 
<p align="center">
    <img src="img/tugas3-13.png" alt="Cover Image">
</p>

lalu install paket 
 
 <p align="center">
    <img src="img/tugas3-14.png" alt="Cover Image">
</p>
 <p align="center">
    <img src="img/tugas3-15.png" alt="Cover Image">
</p>

untuk menuninstall. klik saja removal package 

<p align="center">
    <img src="img/tugas3-16.png" alt="Cover Image">
</p>

<h2>8.7.2 instalasi di terminal dengan dpkg</h2>


Dpkg adalah utilitas perangkat lunak di Debian yang menangani paket, mirip dengan apt, tapi tidak mengurus dependensi. Artinya, jika Anda menggunakan dpkg untuk menginstal paket eksternal, Anda harus menginstal paket-paket "tergantung" satu per satu melalui terminal. Dpkg sudah terpasang secara default di Debian dan harus digunakan dalam mode administratif.

untuk install external paket dengan 

1.	step pertama adalah donwload package extensi .deb untuk melakukan extraksi. disini contoh saya install sublime text 
  <p align="center">
    <img src="img/tugas3-17.png" alt="Cover Image" width="480" height="420">
</p>
2.	 setelah didownload, akan menghasilkan file .deb yang bisa dicek didalam direktoru download. 
lalu langsung saja melakukan perintah dpkg -i <nama_file.deb> untuk melakukan instalasi di ubuntu dari file yang sudah di download .deb 

 <p align="center">
    <img src="img/tugas3-18.png" alt="Cover Image" width="480" height="420">
</p>
 
3.	 setelah success, aplikasi akan sudah terinstall dan bisa digunakan di ubuntu kalian, bisa dicek dengan searching 

 <p align="center">
    <img src="img/tugas3-19.png" alt="Cover Image" width="480" height="420">
</p>
 
4.	atau bisa dicek dengan melalui terminal dengan perintah 
dpkg -l atau dpkh -install -> untuk melihat aplikasi yang diinstall lalu cari saja sublime-text

  <p align="center">
    <img src="img/tugas3-20.png" alt="Cover Image" width="480" height="420">
</p>







result sublime-text yaitu nama aplikasi nya 

  <p align="center">
    <img src="img/tugas3-21.png" alt="Cover Image" width="480" height="420">
</p>

jadi alhasil udah terinstall dan bisa digunakan. 

SEKARANG CARA MENGHAPUS INSTALASI 
1.	menggunakan terminal perintah 
dpkg –purge <nama_aplikasi>
saya disini akan uninstall sublime text yang udah saya download dan install
 
 <p align="center">
    <img src="img/tugas3-22.png" alt="Cover Image" width="480" height="420">
</p>

lalu bisa dicek, aplikasi pasti sudah di uninstall 

  <p align="center">
    <img src="img/tugas3-23.png" alt="Cover Image" width="480" height="420">
</p>

bisa dicek dengan searching aplikasi atau menggunakan perintah yang sebelumnya yaitu dpkg -l -> untuk melihat aplikasi yang diinstall pasti tidak ada 







