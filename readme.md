# Writing & Presentation Test Week 4
##### Muh Zaki Choiruddin 
##### Backend Web Development Track | Skilvul Tech4Impact

Assalamu'alaikum Wr. Wb. Di markdown ini saya akan menjelaskan berbagai materi yang telah saya pelajari selama mengikuti kegiatan `Kampus Merdeka Skilvul Tech4Impact pada track Backend Web Development`.

## Table of Contents
  - [Fetch](#fetch)
    - [Pengertian](#pengertian)
    - [API](#api)
    - [Syntax Fetch](#syntax-fetch)
  - [Async/ Await](#async-await)
    - [Pengertian](#pengertian-1)
    - [Syntax](#syntax)
    - [Synchronous vs Asynchronous](#synchronous-vs-asynchronous)
  - [Git & Github Lanjutan](#git--github-lanjutan)
    - [Pengertian](#pengertian-2)
    - [Alur kerja](#alur-kerja)
    - [Praktek](#praktek)
  - [Responsive Web Design](#responsive-web-design)
    - [Pengertian](#pengertian-3)
    - [Karakteristik](#karakteristik)
    - [Manfaat](#manfaat)
    - [Penerapan](#penerapan)
  - [Boostrap 5](#boostrap-5)
    - [Pengertian](#pengertian-4)
    - [Instalasi](#instalasi)
    - [Component](#component)

## Fetch
### Pengertian
Fetch API menyediakan interface untuk mengambil resource dari suatu sumber. Dulu hal ini dapat dilakukan menggunakan XMLHttpRequest, tetapi API baru menyediakan serangkaian fitur yang lebih kuat dan fleksibel. Fetch memberikan definisi umum dari objek Request dan Response. Hal itu dapat digunakan untuk service worker, Cache API, dan hal serupa lainnya yang menangani atau mengubah permintaan dan tanggapan, atau segala jenis kasus penggunaan yang mungkin mengharuskan untuk menghasilkan response.

### API
API (Application Programming Interface) adalah sebuah interface yang berperan menjadi penghubung antara satu aplikasi dengan aplikasi lainnya baik dalam platform yang sama atau cross-platform. Ibaratkan API sebagai seorang pelayan di kafe. Tugas utama dari seorang pelayan adalah menghubungkan pengunjung kafe dengan barista. Pengunjung kafe hanya perlu memesan kopi yang telah terdaftar di menu tanpa perlu bertemu langsung dengan barista. Meskipun demikian, pelayan kafe akan membawakan pesanan minuman sesuai pesanan pengunjung kafe.

### Syntax Fetch
Setelah fetch terdapat promise yang diguanakan untuk melakukan resolve dari object response yang diterima.
```sh
fetch("https://api.themoviedb.org/3/discover/movie?page=1&sort_by=popularity.desc")
  .then((response) => {
    const data = response.json();
    return data.movies;
  }).catch((error) => {
      console.log(error.message)
  })
```


## Async/ Await
### Pengertian
Async/ await adalah fitur yang hadir sejak ES2017. Fitur ini mempermudah kita dalam menangani proses asynchronous. Async/Await merupakan sebuah syntax khusus yang digunakan untuk menangani Promise agar penulisan code lebih efisien dan rapih.
- async => Mengubah function menjadi asynchronous
- await => Menunda eksekusi hingga proses asynchronous selesai

### Syntax
```sh
async function getPosts () {
    let response = await fetch("https://api.osorateam.com/posts")
    let data = await response.json()
    console.log(data)
}
```
Dari kode di atas berarti let data tidak akan di eksekusi sebelum proses fetch di atasnya selesai. Await bisa digunakan berkali-kali di dalam function.

### Synchronous vs Asynchronous
Dalam dunia programming kedua istilah ini digunakan untuk membedakan tentang cara urutan eksekusi perintah-perintah yang ada dalam kode anda.
- Synchronous 
Setiap perintah di eksekusi satu persatu sesuai urutan kode yang anda tuliskan. Contoh:
```sh
console.log('Namaku')
console.log('Adalah')
console.log('Zaki')

// Namaku
// Adalah
// Zaki
```
Output dari kode diatas dijamin akan sesuai urutan, karena setiap perintah harus menunggu perintah sebelumnya selesai. Proses seperti ini disebut `blocking`.

- Asynchronous
Hasil eksekusi atau output tidak selalu berdasarkan urutan kode, tetapi berdasarkan waktu proses. Eksekusi dengan asynchronous tidak akan membloking atau menunggu suatu perintah sampai selesai. Daripada menunggu, asynchronous akan mengeksekusi perintah selanjutnya.
```sh
console.log('Namaku');
setTimeout(() => { console.log('Adalah')},100) // tunda selama 100 miliseconds
console.log('Zaki');

Namaku
Zaki
Adalah
```

## Git & Github Lanjutan
### Pengertian
Git merupakan tool open source sebagai Version Control System code. Git berfungsi untuk melacak perubahan setiap file dalam project, biasanya digunakan untuk mengelola code agar lebih rapi.

Github adalah layanan cloud yang berfungsi untuk menyimpan code. Dengan menggunakan github para programmer dapat berkolaborasi untuk mengerjakan suatu project dengan mudah.

### Alur kerja
1. Menginisialisasi project dengan git.
2. Menulis code program.
3. Masukkan perubahan ke staging area git.
4. Beri pesan untuk menandai perubahan.
5. Kirim code ke cloud repository.

### Praktek
#### Local
1. Buat folder project bernama `hello-git`.
2. Inisialisasi git.
```sh
git init .
```
3. Buat file baru, lalu tulis code.
```sh
<p>Hello GIT</p>
```
4. Ketik `git status` untuk melihat apakah ada perubahan di dalam project.
```sh
git status
```
5. Ketik `git add` untuk memasukkan perubahan ke staging area. Simbol titik (.) berarti memilih semua file.
```sh
git add .
```
5. Simpan perubahan di local secara permanen dengan perintah `git commit -m "isi pesan"`
```sh
git commit -m "fitur 1"
```

#### Cloud repository
1. Buat repository baru di github.com
2. Buat branch bernama `main` di local
```sh
git branch -M main
```
3. Selanjutnya tambahkan remote repository.
```sh
git remote add origin https://github.com/zakihaha/hello-git.git
```
4. Langkah terakhir adalah mengirim perubahan ke remote repository
```sh
git push -u origin main
```

#### Kolaborasi
Fungsi inti dari Github selain sebagai version control system yakni collaboration. Github memudahkan para developer untuk mengerjakan suatu project secara bersama-sama. Cara berkolaborasi:
1. Siapkan sebuah repository, masuk ke tab Settings -> Collaborators.
![image](https://user-images.githubusercontent.com/49114801/195991736-2aebdb8f-d045-4897-9be2-edef5f720137.png)

2. Klik tombol Add people, undang teman menggunakan email atau username Github.
![image](https://user-images.githubusercontent.com/49114801/195991748-95829178-6e6d-4a2a-bbe4-76a2ae038242.png)

3. Buat branch masing-masing sesuai dengan naming convention yang telah disepakati.
![image](https://user-images.githubusercontent.com/49114801/195991786-cb123f71-3896-42d1-80e4-ef020b57f86d.png)

4. Start coding.
5. Lakukan push di branch masing-masing.
6. Kirim pull request apabila ingin merge ke branch utama.
![image](https://user-images.githubusercontent.com/49114801/195991835-5729df5e-2307-420d-8605-9fcda231b542.png)

## Responsive Web Design
### Pengertian
Responsive web design artinya tampilan website yang responsif dan mampu menyesuaikan dengan perangkat (device) yang digunakan pengguna. Prinsip ini melibatkan proses merancang tampilan website Anda agar mampu disesuaikan dengan ukuran atau resolusi layar perangkat apa pun. 

### Karakteristik
1. Layout teratur di tampailan desktop, tablet, smartphone
2. Media tampil secara keseluruhan
3. Tipografi ideal

### Manfaat
1. Meningkatkan user experience
2. Lebih hemat biaya
3. Kemudahan dalam maintenance

### Penerapan
Untuk membuat sebuah website yang responsive diperlukan media query untuk memfilter style CSS yang sesuai dengan ukuran layar device.
```sh
# style.css
h1 {
    font-size: 72px;
}

@media screen and (max-width:768px) {
    h1 {
        font-size: 42px;
        color: red;
    }
}

@media screen and (max-width:576px) {
    h1 {
        font-size: 32px;
        color: blue;
    }
}
```
Hasilnya adalah ketika tampilan:
1. Desktop (lebih besar dari 768px) - Tag h1 memliki ukuran 72px.
![image](https://user-images.githubusercontent.com/49114801/195991908-2cf51a81-86f4-491a-9b2a-3266a0ed6ba1.png)

2. Tablet (antara 768px - 576px) - Tag h1 memliki ukuran 42px dan berwarna merah.
![image](https://user-images.githubusercontent.com/49114801/195991922-58bdaf54-07d8-4490-be22-ba0588cc560a.png)

3. Smartphone (dibawah 576px) - Tag h1 memliki ukuran 32px dan berwarna blue.
![image](https://user-images.githubusercontent.com/49114801/195991929-4f1d07c2-a916-4f64-a4da-26bda5f0cc54.png)

## Boostrap 5
### Pengertian
Bootstrap adalah library HTML, CSS, dan JavaScript yang berfungsi untuk mendesain website responsive dengan cepat dan mudah. Library open source ini diciptakan pada tahun 2011 oleh Mark Otto dan Jacob Thornton dari Twitter. Untuk membuat tampilan website kita tidak perlu menggunakan CSS lagi namun hanya tinggal memanggil berbagai classname yang sudah ada pada Bootstrap.

### Instalasi
#### CDN
```sh
# Masukkan di dalam tag head
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">

# Masukkan tepat sebelum tag penutup body
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script>
```

#### Package Manager
```sh
npm install bootstrap@5.2.2
```

#### Manual
Unduh file bootstrap di halaman resminya getbootstrap.com

### Component
Bootstrap memiliki banyak component yang siap digunakan untuk menyusun sebuah website.

#### Alert
Berikan pesan umpan balik kontekstual untuk tindakan pengguna biasa dengan beberapa pesan peringatan yang tersedia dan fleksibel.
```sh
<div class="alert alert-primary" role="alert">
    A simple primary alert—check it out!
</div>
<div class="alert alert-secondary" role="alert">
    A simple secondary alert—check it out!
</div>
<div class="alert alert-success" role="alert">
    A simple success alert—check it out!
</div>
<div class="alert alert-danger" role="alert">
    A simple danger alert—check it out!
</div>
```
#### Buttons
Gunakan tombol Bootstrap untuk action dalam form, dialog, dan lainnya dengan dukungan untuk berbagai ukuran, status, dan lainnya.
```sh
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
```

#### Cards
Kartu Bootstrap menyediakan wadah konten yang fleksibel dan dapat diperluas dengan berbagai varian dan opsi.
```sh
<div class="card" style="width: 18rem;">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
</div>
```

#### Navbar
Digunakan untuk membuat navigasi pada website.
```sh
<nav class="navbar navbar-expand-lg bg-light">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item">
                    <a class="nav-link active" aria-current="page" href="#">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Features</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Pricing</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link disabled">Disabled</a>
                </li>
            </ul>
        </div>
    </div>
</nav>
```


