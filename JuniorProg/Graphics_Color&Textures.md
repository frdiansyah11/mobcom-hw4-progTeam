# Graphics : Color & Texture

<strong>Mesh</strong>

Konstruktor kelas Mesh memiliki beberapa parameter. Yang pertama menentukan apakah jala itu statis. Setting ini ke true akan memungkinkan optimasi OpenGL bermanfaat bagi mesh yang tidak banyak berubah (yaitu setiap frame). Parameter kedua dan ketiga menentukan jumlah simpul dan indeks mesh ini. Karena jala mewakili segitiga, ia memiliki tiga simpul. Setiap simpul digunakan sekali dalam rendering segitiga, sehingga Mesh membutuhkan tiga indeks.

Contoh:
Vertex 1 terletak di 0.5 (x), -0,5 (y), 0 (z). Untuk memvisualisasikan di mana titik ini ada di layar, bayangkan bahwa bagian tengah layar berada pada 0 (x), 0 (y), 0 (z). Tepi kiri layar berada pada -1 (x), tepi kanan 1 (x). Bagian bawah layar ada di -1 (y), bagian atas 1 (y). Inilah gambaran konsepnya:

<div align="center"><img src="https://camo.githubusercontent.com/a98444db35aaa5b44aac998a8bc69d9626e30a49/687474703a2f2f692e696d6775722e636f6d2f794c6e4d5275352e706e67" /></div>

<strong>Color</strong>

Jika kita ingin mesh ini diwarnai, kita hanya perlu menambahkan VertexAttribute lain dan menentukan informasi warna untuk simpul. Anda perlu mengimpor kelas com.badlogic.gdx.graphics.Color.

Dalam konstruksi mesh, kami menambahkan VertexAttribute untuk warna. Ini berisi 4 komponen (R, G, B, Alpha) dan kami berikan itu nama. Kami kemudian menambahkan informasi warna ke array float. Saat kita menjalankan aplikasi, seharusnya terlihat seperti ini

<div align="center"><img src="https://camo.githubusercontent.com/630c78b71e71cb51fd979c5282bcbdc864cb22ba/687474703a2f2f692e696d6775722e636f6d2f6d5043643230572e706e67" /></div>


<strong>Texture</strong>

Untuk memasang tekstur pada jala, kita perlu meletakkan file gambar di ruang kerja kita, buat objek tekstur dalam kode kita yang mereferensikan gambar itu, lalu tambahkan tekstur VertexAttribute ke mesh kita.

Untuk memulai, di dalam proyek tekstur warna mesh, buatlah sebuah folder bernama data pada tingkat yang sama dengan folder src dan libs. Salin gambar apapun ke dalam folder, dalam contoh ini kita akan menggunakan [http://i.imgur.com/joJOP1R.jpg]. Penting untuk dicatat bahwa setiap gambar yang digunakan untuk membuat tekstur harus memiliki lebar dan tinggi masing-masing menjadi dua kekuatan. Contoh:

<div align="center"><img src="https://camo.githubusercontent.com/bb327d2d4e473cb1dd25f13ca71905ffca03c337/687474703a2f2f692e696d6775722e636f6d2f6a6f4a4f5031522e6a7067" /></div>
