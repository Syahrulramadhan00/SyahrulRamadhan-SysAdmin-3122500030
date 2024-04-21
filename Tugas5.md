<h1 align="center">
LAPORAN PRAKTIKUM WORKSHOP

**ADMINISTRASI JARINGAN**

</h1>
<p align="center">
“WEB EMAIL SYSTEM SERVER”
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


# INSTALASI NTP

gunakan command `sudo apt-get install systemd-timesyncd` menginstall package timesyncd
![NTP](img/Tugas5/NTP1.png)


gunakan command `sudo timedatectl set-timezone Asia/Jakarta` untuk set waktu WIB (Jakarta)
![NTP](img/Tugas5/NTP2.png)

gunakan command `sudo timedatectl set-ntp true` untuk menjalankan NTP pada package
![NTP](img/Tugas5/NTP3.png)

`sudo nano /etc/systemd/timesyncd.conf`uncomment ubah bagian`NTP=` 
![NTP](img/Tugas5/NTP4.png)

Isi bagian NTP menjadi: `NTP=0.id.pool.ntp.org `
![NTP](img/Tugas5/NTP5.png)

`sudo systemctl restart systemd-timesyncd` untuk merestart services karena habis di setup lalu cek status dengan command `sudo systemctl status systemd-timesyncd`
![NTP](img/Tugas5/NTP6.png)

Cek apakah sudah sesuai dengan timezone WIB
![NTP](img/Tugas5/NTP7.png)


# INSTALASI WEB SERVER

Instal apache2 dengan command `sudo apt-get install apache2 -y`
![webserver](img/Tugas5/webserver1.png)

ketikan command `sudo nano /etc/apache2/conf-enabled/security.conf` rubah pada bagian ServerTokens menjadi Prod
![webserver](img/Tugas5/webserver2.png)

ketika command `sudo nano /etc/apache2/mods-enabled/dir.conf`
Ubah bagian DirectoryIndex menjadi index.html index.htm
![webserver](img/Tugas5/webserver3.png)


ketikan command `sudo nano /etc/apache2/apache2.conf` Tambahkan ServerName www.kelompok4.local
![webserver](img/Tugas5/webserver4.png)

Ketikkan command `sudo nano /etc/apache2/sites-available/000-default.conf`Ubah bagian webmaster@localhost menjadi webmaster@kelompok4.local
![webserver](img/Tugas5/webserver5.png)

Restart services apache 2 dengan command `sudo systemctl restart apache2` lalu cek status services apache2 `sudo systemctl status apache2`
![webserver](img/Tugas5/webserver6.png)

Buka browser dan ketikkan alamat `www.kelompok4.local` untuk mengecek
![webserver](img/Tugas5/webserver7.png)

install PHP dan fungsi mbstring digunakan untuk memanipulasi string atau text non ASCII `sudo apt -y install php8.2 php8.2-mbstring php-pear` lalu cek versi dengan command `php-v`![webserver](img/Tugas5/webserver8.png)

buat file `php_info.php` di /var/www/html `sudo nano /var/www/html/php_info.php` isi file php_info.php dengan kode berikut `<?php phpinfo(); ?>`
![webserver](img/Tugas5/webserver9.png)

install PHP FPM 
![webserver](img/Tugas5/webserver10.png)

ketikan command`sudo nano /etc/apache2/sites-available/default-ssl.conf` ini berfungsi untuk mengarahkan apache2 ke php-fpm tambahkan di dalam tag `<VirtualHost *:443></VirtualHost>`
  ```
    <FilesMatch \.php$>
        SetHandler "proxy:unix:/var/run/php/php8.2-fpm.sock|fcgi://localhost/"
    </FilesMatch>    
```
![webserver](img/Tugas5/webserver11.png)


Jalankan command dibawah

`a2enmod proxy_fcgi` setenvif Ini berfungsi untuk mengaktifkan modul proxy_fcgi dan setenvif `a2enconf php8.2-fpm` Ini berfungsi untuk mengaktifkan konfigurasi php8.2-fpm `systemctl restart php8.2-fpm apache2` Ini berfungsi untuk merestart php8.2-fpm dan apache2
![webserver](img/Tugas5/webserver12.png)

# KONFIGURASI DATABASE SERVER 

`sudo apt -y install mariadb-server` untuk menginstall mariadb
![Database Server](/img/tugas5/databaseserver1.png)


Isikan konfigurasi inisial seperti berikut:

    Enter current password for root (enter for none): Just press the Enter : (isi password root)
    Switch to unix_socket authentication [Y/n] : n
    Remove anonymous users? [Y/n] : Y
    Disallow root login remotely? [Y/n] : Y
    Remove test database and access to it? [Y/n] : Y
    Reload privilege tables now? [Y/n] : Y

![Database Server](/img/tugas5/databaseserver2.png)

masuk ke database command `sudo mysql -u root -p`
![Database Server](/img/tugas5/databaseserver3.png)

Test database dengan command `show grants for 'root'@'localhost';`
![Database Server](/img/tugas5/databaseserver4.png)

tampilkan user,host dan password dari db mysql dan tabel user `select user,host,password from mysql.user;`
![Database Server](/img/tugas5/databaseserver5.png)

Tampilkan database yang ada pada MariaDB dengan command `show databases;`
![Database Server](/img/tugas5/databaseserver6.png)

buat database baru `create database siswa;`
lalu `use siswa;` lalu buat table dengan berikut
`create table siswa.siswa_table (nrp int, name varchar(50), address varchar(50), primary key (id));`
![Database Server](/img/tugas5/databaseserver7.png)

Isi value table dengan command `insert into siswa_table values(1, 'budi gaming', 'mongolia'); `
![Database Server](/img/tugas5/databaseserver8.png)

Cek database apakah sudah terinsert atau belum `select * from siswa_table;`
![Database Server](/img/tugas5/databaseserver9.png)


# INSTALL PHPMYADMIN 

Install phpmyadmin dengan command `sudo apt -y install phpmyadmin` lalu pilih apache2
![phpmyadmin](/img/Tugas5/phpmyadmin1.png)

Pilih configure database for phpmyadmin dengan dbconfig-common yes
![phpmyadmin](/img/Tugas5/phpmyadmin2.png)

Masukan password root phpmyadmin disini saya menggunakan password `user123`
![phpmyadmin](/img/Tugas5/phpmyadmin3.png)

Isikan password konfirmasi `user123`
![phpmyadmin](/img/Tugas5/phpmyadmin4.png)

masuk pada `sudo nano /etc/apache2/apache2.conf` Tambahkan baris berikut pada file konfigurasi apache2 di bagian paling bawah
```
 Include /etc/phpmyadmin/apache.conf
```
![phpmyadmin](/img/Tugas5/phpmyadmin5.png)

Buka browser dan akses phpmyadmin dengan alamat http://kelompok4.local/phpmyadmin
![phpmyadmin](/img/Tugas5/phpmyadmin6.png)

Masukkan username dan password root mysql yang telah diatur sebelumnya contoh:

    username: phpmyadmin
    password: user123
![phpmyadmin](/img/Tugas5/phpmyadmin7.png)


login ke mysql mysql -u root -p
tambahkan privilege user phpmyadmin dan password ganti dengan `user123` sesuai dengan yang kita setup tadi

    GRANT ALL PRIVILEGES ON *.* TO 'phpmyadmin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
    FLUSH PRIVILEGES;

![phpmyadmin](/img/Tugas5/phpmyadmin8.png)

Maka hasil ketika memberikan privileges root ke user phpmyadmin
![phpmyadmin](/img/Tugas5/phpmyadmin9.png)


# MAIL SERVER 

install postfix dengan command `apt -y install postfix sasl2-bin`
![mailserver](/img/Tugas5/mailserver1.png)

Pilih No configuration
![mailserver](/img/Tugas5/mailserver2.png)

Copas file main.cf ke direktori lain seperti berikut `cp /usr/share/postfix/main.cf.dist /etc/postfix/main.cf`
![mailserver](/img/Tugas5/mailserver3.png)

Edit file dengan vscode pastikan sudah terinstall agar bisa berjalan. Berikut commandnya
`code /etc/postfix/main.cf` lalu isi dengan konfigurasi klik
[disini](https://pastelink.net/0o7rolcy)

Setelah itu perbarui databases aliases postfix dengan command `sudo newaliases` setelah itu restart postfix `sudo systemctl restart postfix`
![mailserver](/img/Tugas5/mailserver4.png)

buka file main.cf code /etc/postfix/main.cf
tambahkan baris berikut di paling bawah

    # reject unknown clients that forward lookup and reverse lookup of their hostnames on DNS do not match
    smtpd_client_restrictions = permit_mynetworks, reject_unknown_client_hostname, permit

    # rejects senders that domain name set in FROM are not registered in DNS or
    # not registered with FQDN
    smtpd_sender_restrictions = permit_mynetworks, reject_unknown_sender_domain,reject_non_fqdn_sender

    # reject hosts that domain name set in FROM are not registered in DNS or
    # not registered with FQDN when your SMTP server receives HELO command
    smtpd_helo_restrictions = permit_mynetworks, reject_unknown_hostname,reject_non_fqdn_hostname, reject_invalid_hostname, permit

Lalu restart lagi postfix  `sudo systemctl restart postfix`

Install dovecot dengan command `sudo apt -y install dovecot-core dovecot-pop3d dovecot-imapd`
![mailserver](/img/Tugas5/mailserver5.png)

Edit file /etc/dovecot/dovecot.conf `sudo nano /etc/dovecot/ dovecot.conf`uncomment baris 30
![mailserver](/img/Tugas5/mailserver6.png)

Edit file /etc/dovecot/conf.d/10-auth.conf `sudo nano /etc/dovecot/conf.d/10-auth.conf` uncomment baris 10 dan setting ke no
ubah di baris 100 menjadi `disable_plaintext_auth = plain login`
![mailserver](/img/Tugas5/mailserver7.png)
![mailserver](/img/Tugas5/mailserver8.png)

Edit file /etc/dovecot/conf.d/10-mail.conf `sudo nano /etc/dovecot/conf.d/10-mail.conf` uncomment baris 30 dan ubah menjadi `mail_location = maildir:~/Maildir`
![mailserver](/img/Tugas5/mailserver9.png)

Edit file /etc/dovecot/conf.d/10-master.conf `sudo nano /etc/dovecot/conf.d/10-master.con`f uncomment baris 107-109 dan ubah seperti berikut

    unix_listener /var/spool/postfix/private/auth {
        mode = 0666
        user = postfix
        group = postfix
    }
![mailserver](/img/Tugas5/mailserver10.png)

Setelah itu jangan lupa install net-tools agar bisa menjalankan netstat dan juga restart dovecot dengan perintah `systemctl restart dovecot`
![mailserver](/img/Tugas5/mailserver11.png)

Periksa dengan perintah `netstat -a| grep LISTEN` lalu lihat pada port berapa postfix berjalan lalu jalankan perintah `telnet mail.kelompok4.local (port)`
![mailserver](/img/Tugas5/mailserver12.png)

Install thunderbird dengan perintah `sudo apt install thunderbird`
![mailserver](/img/Tugas5/mailserver13.png)

Login dengan user debian12 dengan mail local `syahrul@kelompok4.local` dengan password `user123`
![mailserver](/img/Tugas5/mailserver14.png)

Coba buat user baru dengan `sudo useradd` lalu login setelah itu kirim pesan ke user baru tersebut 
![mailserver](/img/Tugas5/mailserver15.png)

# Roundcube 

Masuk ke` MySQL mysql -u root -p` setelah itu 
Buat Database `CREATE DATABASE roundcubemail;` lalu
Buat User `CREATE USER 'roundcube'@'localhost' IDENTIFIED BY 'password';`
![roundcube](/img/tugas5/roundcube1.png)

Berikan Hak Akses dengan command `grant all privileges on roundcube.* to roundcube@'localhost' identified by 'password'; `
![roundcube](/img/tugas5/roundcube2.png)

Install roundcube dengan command `sudo apt-get install -y roundcube roundcube-mysql` dan pilih no karena database sudah kita buat sebelumnya
![roundcube](/img/tugas5/roundcube3.png)

Masuk ke direktori konfigurasi `cd /usr/share/dbconfig-common/data/roundcube/install/`
import database `mysql -u roundcube -D roundcube -p < mysql `kemudian masukkan password yang telah dibuat sebelumnya
Konfigurasi database sudo nano /etc/roundcube/debian-db.php
![roundcube](/img/tugas5/roundcube6.png)

Lalu sesuaikan dengan konfigurasi database sebelumnya
![roundcube](/img/tugas5/roundcube7.png)

Konfigurasi Roundcube sudo nano /etc/roundcube/config.inc.php

- ubah line 27  $config['imap_host'] = ["tls://mail.kelompok3.local:143"];
- ubah line 31 $config['smtp_host'] = 'tls://mail.kelompok3.local:587';
- ubah line 39 $config['smtp_pass'] = '%p';
- ubah line 46 $config['product_name'] = 'Server Mail PENS';

tambah pada baris paling akhir:

        $config['smtp_auth_type'] = 'LOGIN';
        // specify SMTP HELO host
        $config['smtp_helo_host'] = 'mail.kelompok3.local';
        // specify domain name
        $config['mail_domain'] = 'mail.kelompok3.local';

        // specify UserAgent
        $config['useragent'] = 'Server World Webmail';
        // specify SMTP and IMAP connection option
        $config['imap_conn_options'] = array(
            'ssl'         => array(
                'verify_peer' => true,
                'CN_match' => 'kelompok3.local',
                'allow_self_signed' => true,
                'ciphers' => 'HIGH:!SSLv2:!SSLv3',
            ),
        );
        $config['smtp_conn_options'] = array(
        'ssl'   => array(
                'verify_peer' => true,
                'CN_match' => 'kelompok3.local',
                'allow_self_signed' => true,
                'ciphers' => 'HIGH:!SSLv2:!SSLv3',
            ),
        );

![roundcube](/img/tugas5/roundcube4.png)
![roundcube](/img/tugas5/roundcube5.png)


Setelah itu lanjut ke `sudo nano etc/apache2/sites-available/000-default.conf` tambahkan konfigurasi `Servername mail.kelompok4.local `dan `DocumentRoot /var/www/html`
![roundcube](/img/tugas5/roundcube9.png)