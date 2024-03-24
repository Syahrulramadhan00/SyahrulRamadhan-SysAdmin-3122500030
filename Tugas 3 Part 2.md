<h1 align="center">
LAPORAN PRAKTIKUM WORKSHOP

**ADMINISTRASI JARINGAN**

</h1>
<p align="center">
“Instalasi DNS Server dan Ekosistem Internet”
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


# EKOSISTEM INTERNET

Pengertian: <br>
Internet adalah hasil dari kemitraan global yang melibatkan berbagai aspek, termasuk teknologi, standar, organisasi, dan entitas yang bekerja sama untuk mendukung pengembangan dan operasionalnya. Kunci kesuksesan internet termasuk kepemilikan global bersama, jadii tidak ada yang memiliki internet.    pengembangan standar terbuka, dan ketersediaan proses pengembangan teknologi dan kebijakan yang transparan dan terbuka untuk diakses oleh semua pihak. Semua orang bebas menggunakan internet.

Cara Kerja Internet: <br>
Internet secara teknis melibatkan sistem routing yang mengatur aliran data antara jaringan, serta sistem penamaan domain (DNS) yang menerjemahkan nama domain menjadi alamat IP. Organisasi standar seperti Internet Engineering Task Force (IETF) memainkan peran penting dalam mengembangkan dan memelihara standar internet yang diperlukan untuk interoperabilitas global. Penyedia layanan internet, termasuk penyedia konten, penyedia akses, dan penyedia transit, bekerja sama untuk menyediakan koneksi dan layanan internet kepada pengguna di seluruh dunia. Registrasi IP dan domain dikelola oleh lembaga seperti Registri Regional Internet (RIR) dan Registri Nama Domain, yang mengkoordinasikan penugasan dan pengelolaan sumber daya internet. Cara kerja nya Pertama, pengguna mengakses internet melalui perangkat seperti komputer, ponsel, atau tablet yang terhubung ke jaringan internet melalui penyedia layanan internet (ISP). Ketika pengguna meminta akses ke situs web atau layanan online tertentu, perangkat mereka menggunakan protokol komunikasi, seperti HTTP atau HTTPS, untuk membuat permintaan kepada server yang menyimpan situs web atau layanan tersebut. Sistem Penamaan Domain (DNS) kemudian menerjemahkan nama domain menjadi alamat IP yang sesuai, yang digunakan oleh perangkat untuk menemukan situs web yang dimaksud. Setelah itu, data dikirim melalui jaringan internet melalui serangkaian perangkat jaringan, seperti router dan switch, menggunakan protokol seperti TCP/IP. Data tersebut diarahkan melalui rute terbaik dalam jaringan, melalui berbagai penyedia layanan dan simpul jaringan, menggunakan protokol routing seperti BGP (Border Gateway Protocol). Ketika data mencapai server tujuan, server tersebut memproses permintaan yang diterima dan mengirimkan informasi yang diminta kembali ke perangkat pengguna melalui jaringan yang sama. Terakhir, perangkat pengguna menerima informasi yang dikirimkan oleh server dan menampilkannya kepada pengguna melalui browser atau aplikasi, memungkinkan interaksi dengan situs web atau layanan tersebut. Seluruh proses ini berulang setiap kali pengguna melakukan akses ke situs web atau layanan online, membentuk dasar dari cara kerja internet yang kita gunakan sehari-hari.



# INSTALASI DNS SERVER

Saya menggunakan dokumentasi berikut sebagai refensi:
[Klik Disini](https://wiki.debian.org/Bind9#Debian_Bookworm)

Pertama-tama install bind 9 seperti berikut:

![langkah 1](img/tugas3-41.png)


Lalu masuk ke named.conf dengan command "sudo nano named.conf" sesuaikan berdasarkan konfigurasi dokumentasi dengan beberapa penyesuaian:

![Langkah 2](img/tugas3-42.png)


Lalu masuk ke named.conf.default-zones dengan command "sudo nano named.conf" sesuaikan berdasarkan konfigurasi dokumentasi dengan beberapa penyesuaian:

![Langkah 3](img/tugas3-43.png)


Lalu masuk ke named.conf.options dengan command "sudo nano named.conf.options" sesuaikan berdasarkan konfigurasi dokumentasi dengan beberapa penyesuaian:

![Langkah 4](img/tugas3-44.png)


Lalu masuk ke named.conf.options dengan command "sudo nano named.conf.options" sesuaikan berdasarkan konfigurasi dokumentasi dengan beberapa penyesuaian:

![Langkah 5](img/tugas3-45.png)


Pindah direktori ke /var/lib/bind/

![Langkah 6](img/tugas3-46.png)


Ketikan command "sudo nano db.kelompok4.local" dan sesuaikan konfigurasinya dengan dokumnetasi dengan sedikit improvisasi:

![Langkah 7](img/tugas3-47.png)


Dan juga ketikan "sudo nano db.kelompok4.local.inv" dan sesuiakan konfigurasinya dengan nama kelompok:

![alt](img/tugas3-48.png)


Ketikan perintah "sudo named-checkzone kelompok4.local db.kelompok4.local" jika berhasil maka akan muncul seperti dibawah ini:

![alt](img/tugas3-49.png)


Ketikan perintah "sudo named-checkzone 4.168.192.in-addr.arpa db.kelompok4.local.inv" jika berhasil maka akan muncul status OK seperti dibawah ini:

![alt](img/tugas3-50.png)


Pastikan pada wired connection anda manual dengan settingan ip dan dns seperti dibawah:

![alt](img/tugas3-52.png)


lalu cek status named dengan cara "sudo systemctl status named" pastikan running dan tidak ada masalah

![alt](img/tugas3-51.png)


Jika error atau ada masalah dengan named cara "sudo systemctl restart named" lalu jalankan "sudo systemctl status named" pastikan running dan tidak ada masalah

![alt](img/tugas3-53.png)


Jalankan "sudo systemctl status networking" untuk memeriksa apakah jaringan berjalan tidak ada masalah

![alt](img/tugas3-54.png)


Cek "sudo nano /etc/resolv.conf" dan konfigurasi seperti dibawah:

![alt](img/tugas3-55.png)


Tes menggunakan "nslookup 192.168.4.1" dan "nslookup ns.kelompok4.local" untuk melihat apakah IP sudah sesuai dengan nama kelompoknya:

![alt](img/tugas3-56.png)
![alt](img/tugas3-57.png)


Terakhir lakukan pengetesan dengan cara "dig ns.kelompok4.local" dan "dig 192.168.4.1"

![alt](img/tugas3-58.png)
![alt](img/tugas3-59.png)


selesai kurang lebih nya mohon maaf



