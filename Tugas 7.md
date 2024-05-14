<h1 align="center">
LAPORAN PRAKTIKUM WORKSHOP

**ADMINISTRASI JARINGAN**

</h1>
<p align="center">
“Play With Docker - Docker 101”
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

# Getting Started

Pertama tama kunjungi laman berikut: `https://labs.play-with-docker.com/`
login dan jika belum punya akun sign up

![gettingstarted](/img/Tugas7/gettingstarted1.png)

Jalankan Perintah `docker run -dp 80:80 docker/getting-started:pwd` 

![gettingstarted](/img/Tugas7/gettingstarted2.png)

Klik open port 

![gettingstarted](/img/Tugas7/gettingstarted3.png)

Lalu masukan port 80 sesuai dengan command tadi

![gettingstarted](/img/Tugas7/gettingstarted4.png)

Maka akan tampil halaman berikut:

![gettingstarted](/img/Tugas7/gettingstarted5.png)

# Our Application

Download app.zip pada link berikut: `http://ip172-18-0-112-cp0r50aim2rg00ao0ll0-80.direct.labs.play-with-docker.com/assets/app.zip` Lalu drag app.zip ke terminal

![ourapplication](/img/Tugas7/ourapplication1.png)

Lalu unzip dengan command: `unzip app.zip`

![ourapplication](/img/Tugas7/ourapplication2.png)

Pergi ke direktori dengan command: `cd app/` dan `ls` dan akan terlihat isi nya

![ourapplication](/img/Tugas7/ourapplication3.png)

Buat file Dockerfile dengan cara: `vi Dockerfile` dan masukan konfigrasi seperti berikut:

    FROM node:10-alpine
    WORKDIR /app
    COPY . .
    RUN yarn install --production
    CMD ["node", "/app/src/index.js"]


![ourapplication](/img/Tugas7/ourapplication4.png)

Tekan esc dan tekan `:` lalu ketikan `wq!`

Masukan Command: `docker build -t docker-101 .` untuk build kode tadi

![ourapplication](/img/Tugas7/ourapplication5.png)

Jalankan perintah `docker run -dp 3000:3000 docker-101` untuk menjalankan container

![ourapplication](/img/Tugas7/ourapplication6.png)

Buka Port `3000` caranya seperti sebelumnya

![ourapplication](/img/Tugas7/ourapplication7.png)

Maka akan muncul TODO APP seperti dibawah:

![ourapplication](/img/Tugas7/ourapplication8.png)


# Updating our App

Pergi ke `/app/src/static/js/app.js` lalu edit line 56 seperti berikut:

    - <p className="text-center">No items yet! Add one above!</p>
    Ganti dengan
    + <p className="text-center">You have no todo items yet! Add one above!</p>


![updatingourapp](/img/Tugas7/updatingourapp1.png)

Pada direktori app jalankan perintah: ``docker build -t docker-101 .``

![updatingourapp](/img/Tugas7/updatingourapp2.png)

Maka ketika TODO APP kosong akan tampil pesan yang kita tulis tadi

![updatingourapp](/img/Tugas7/updatingourapp3.png)

# Sharing our App

Pergi ke docker HUB ``https://hub.docker.com/`` Lalu login lalu buat repo baru

![sharingourapp](/img/Tugas7/sharingourapp1.png)

Beri nama `101-todo-app` dan pastikan visibility `public`

![sharingourapp](/img/Tugas7/sharingourapp2.png)

Push ke TODO APP ke repo yang sudah dibuat dengan command ``docker push syahrulramadhan00/101-todo-app:tagname`` maka biasanya error karena docker image tidak ditemukan seperti dibawah

![sharingourapp](/img/Tugas7/sharingourapp3.png)

Cara fixnya login dengan command ``docker login -u YOUR-USER-NAME`` 

![sharingourapp](/img/Tugas7/sharingourapp4.png)

Tambahkan tag ke todo app dengan perintah: ``docker tag docker-101 YOUR-USER-NAME/101-todo-app``

![sharingourapp](/img/Tugas7/sharingourapp5.png)

Coba push lagi dengan command:``docker push YOUR-USER-NAME/101-todo-app``

![sharingourapp](/img/Tugas7/sharingourapp6.png)

Buat new instance pada menu PWD

![sharingourapp](/img/Tugas7/sharingourapp7.png)

Pull di instance baru (node2) TODO APP tadi dengan command: ``docker run -dp 3000:3000 YOUR-USER-NAME/101-todo-app``

![sharingourapp](/img/Tugas7/sharingourapp8.png)

# Persisting our DB

Jalankan ubuntu dengan perintah ``docker run -d ubuntu bash -c "shuf -i 1-10000 -n 1 -o /data.txt && tail -f /dev/null"``

![db](/img/Tugas7/db1.png)

Gunakan perintah ``docker ps`` untuk mengetahui id ubuntu 

![db](/img/Tugas7/db2.png)

Jalankan perintah ``docker exec <container-id> cat /data.txt`` sesuaikan dengan container id ubuntu tadi dan akan menampilkan angka random antara 1-10000

![db](/img/Tugas7/db3.png)

Jalankan container ubuntu untuk melihat apakah ada data.txt dengan perintah ``docker run -it ubuntu ls /`` ternyata tidak ada data.txt karena data.txt hanya ditulis untuk dari scartch (nol) hanya untuk container pertama.

![db](/img/Tugas7/db4.png)

Cek id container pertama dengan ``docker ps -a`` Remove dengan command ``docker rm -f <id container>`` lalu cek dengan ``docker ps -a``

![db](/img/Tugas7/db5.png)

Buat volume db baru dengan command ``docker volume create todo-db``

![db](/img/Tugas7/db6.png)

Jalankan TODO container dengan command ``docker run -dp 3000:3000 -v todo-db:/etc/todos docker-101`` pastikan tidak ada yang running di port 3000 jika ada jalankan ``docker ps -a`` dan stop container dengan perintah ``docker stop <id container>`` lalu baru jalankan command pertama   

![db](/img/Tugas7/db7.png)

Coba cek port 3000 maka akan tampil seperti berikut:

![db](/img/Tugas7/db8.png)

Remove container yang berjalan di port 3000 cek id dengan ``docker ps -a``Lalu remove container sesuai id container di port 3000 dengan command ``docker rm -f <id> ``

![db](/img/Tugas7/db9.png)

Maka hasil to do list akan sama jangan lupa remove container jika sudah dicentang semua todo listnya

![db](/img/Tugas7/db10.png)

# Using Bind Mounts

Pastikan dulu tidak ada docker-101 running jika ada 
Lalu coba jalankan perintah berikut:
        
    docker run -dp 3000:3000 \
    -w /app -v $PWD:/app \
    node:10-alpine \
    sh -c "yarn install && yarn run dev"


![bind](/img/Tugas7/bind1.png)

Cek log dengan id container yang berjalan pada port 3000``docker logs -f <container-id>. ``

![bind](/img/Tugas7/bind2.png)

Pergi ke ``vi src/static/js/app.js`` lalu ganti line 109

    -   {submitting ? 'Adding...' : 'Add Item'}
                Ubah dengan:
    +   {submitting ? 'Adding...' : 'Add'}


![bind](/img/Tugas7/bind3.png)


Maka hasilnya setelah di refresh akan seperti ini

![bind](/img/Tugas7/bind4.png)

Jalankan perinfah ``docker build -t docker-101 `` untuk build dengan setingan yang tadi

![bind](/img/Tugas7/bind5.png)


# Multi-Container Apps

Buat network baru dengan perintah: ``docker network create todo-app`` 

![multi-container](/img/Tugas7/multicontainer1.png)

Jalankan MySQL container denga perintah:

    docker run -d \
    --network todo-app --network-alias mysql \
    -v todo-mysql-data:/var/lib/mysql \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=todos \
    mysql:5.7


![multi-container](/img/Tugas7/multicontainer2.png)

Cek container yang berjalan dengan command ``docker ps -a`` dan cek id container mySQL lalu buka MYSQ dengan perintah: ``docker exec -it <mysql-container-id> mysql -p``

![multi-container](/img/Tugas7/multicontainer3.png)

Jalankan perintah: ``SHOW DATABASES;`` untuk melihat tabel dan akan ada tabel `todos`

![multi-container](/img/Tugas7/multicontainer4.png)

Jalankan container nicolaka/netshoot baru dengan perintah: ``docker run -it --network todo-app nicolaka/netshoot`` 

![multi-container](/img/Tugas7/multicontainer5.png)

jalankan ``dig mysql`` bisa dilihat di `ANSWER SECTION:` maka kita bisa lihat `mysql` tertaut dengan `172.23.0.2` itu karena menggunakan flag `--network-alias` sebelumnya sehingga ip tertaut dengan MySQL secara otomatis

![multi-container](/img/Tugas7/multicontainer6.png)

Jalankan container baru pastikan tidak ada container yang berjalan di port: `:3000` dengan command ``docker ps -a`` dan jika ada yang berjalan maka ``docker rm -f <id container>``

![multi-container](/img/Tugas7/multicontainer7.png)

Cek log container dengan perintah: ``docker logs <container-id>``pastikan terconnect seperti dibawah:

![multi-container](/img/Tugas7/multicontainer8.png)

Buka port ``3000`` dan tambahkan beberapa todo list 

![multi-container](/img/Tugas7/multicontainer9.png)

Sambungkan dengan mySQL dengan perintah: ``docker exec -ti <mysql-container-id> mysql -p todos`` 

![multi-container](/img/Tugas7/multicontainer10.png)

Jalankan perintah ``select * from todo_items;`` maka akan ada isi dari todo list yang di inputkan tadi

![multi-container](/img/Tugas7/multicontainer11.png)


# Using Docker Compose

Pertama buat file ``vi docker-compose.yml`` lalu tambahkan :
   
    version: "3.7"

    services:

![docker-compose](/img/Tugas7/dockercompose1.png)

Lalu jalankan docker dengan perintah:

    docker run -dp 3000:3000 \
    -w /app -v $PWD:/app \
    --network todo-app \
    -e MYSQL_HOST=mysql \
    -e MYSQL_USER=root \
    -e MYSQL_PASSWORD=secret \
    -e MYSQL_DB=todos \
    node:10-alpine \
    sh -c "yarn install && yarn run dev"


![docker-compose](/img/Tugas7/dockercompose2.png)

ganti isi dengan versi fullnya seperti berikut:

    version: "3.7"

    services:
    app:
        image: node:10-alpine
        command: sh -c "yarn install && yarn run dev"
        ports:
        - 3000:3000
        working_dir: /app
        volumes:
        - ./:/app
        environment:
        MYSQL_HOST: mysql
        MYSQL_USER: root
        MYSQL_PASSWORD: secret
        MYSQL_DB: todos


![docker-compose](/img/Tugas7/dockercompose3.png)

Coba Running mysSQL dengan perintah: (pastikan remove container mySQL jika berjalan)

    docker run -d \
    --network todo-app --network-alias mysql \
    -v todo-mysql-data:/var/lib/mysql \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=todos \
    mysql:5.7


![docker-compose](/img/Tugas7/dockercompose4.png)

Setelah itu lengkapi ``vi docker-compose.yml`` dengan konfigurasi berikut:

    version: "3.7"

    services:
    app:
        image: node:10-alpine
        command: sh -c "yarn install && yarn run dev"
        ports:
        - 3000:3000
        working_dir: /app
        volumes:
        - ./:/app
        environment:
        MYSQL_HOST: mysql
        MYSQL_USER: root
        MYSQL_PASSWORD: secret
        MYSQL_DB: todos

    mysql:
        image: mysql:5.7
        volumes:
        - todo-mysql-data:/var/lib/mysql
        environment: 
        MYSQL_ROOT_PASSWORD: secret
        MYSQL_DATABASE: todos

    volumes:
    todo-mysql-data:


![docker-compose](/img/Tugas7/dockercompose5.png)

Pastikan tidak ada APP/Mysql yang berjalan:

![docker-compose](/img/Tugas7/dockercompose6.png)

Jalankan APP stack dengan perintah ``docker-compose up -d`` maka akan tampil seperti dibawah berikut:

![docker-compose](/img/Tugas7/dockercompose7.png)

Cek log docker-compose dengan perintah ``docker-compose logs -f`` maka Mysql akan running di port `3306` dan APP running di port `3000`

![docker-compose](/img/Tugas7/dockercompose8.png)


# Image Building Best Practices

Jalankan perintah ``docker image history docker-101`` untuk melihat history

![image-building](/img/Tugas7/imagebuilding1.png)

jalankan perintah ``docker image history --no-trunc docker-101`` untuk mendapatkan semua output


![image-building](/img/Tugas7/imagebuilding2.png)

Edit Dockerfile dengan perintah ``vi Dockerfile`` seperti 

    FROM node:10-alpine
    WORKDIR /app
    COPY . .
    RUN yarn install --production
    CMD ["node", "/app/src/index.js"]


![image-building](/img/Tugas7/imagebuilding3.png)

Jalankan docker build pada container docker-101``docker build -t docker-101 .``

![image-building](/img/Tugas7/imagebuilding4.png)

Ganti Title untuk mengetes docker build apakah berjalan lancar

![image-building](/img/Tugas7/imagebuilding5.png)

Build docker dengan perintah ``docker build -t docker-101 .``

![image-building](/img/Tugas7/imagebuilding6.png)

Cek di port `3000` maka hasilnya TITLE akan berubah seperti berikut:

![image-building](/img/Tugas7/imagebuilding7.png)

