# Architecture Estimation
# Run Pass World Game

Game kami ini termasuk ke dalam game berjenis side-scrolling, Game side-scrolling adalah salah satu jenis game dengan sudut pandang kamera seolah-olah di samping karakter, dan mengikuti pergerakan pemain yang pada umumnya bergerak dari sisi kiri menuju sisi kanan layar untuk mencapai target atau lokasi yang telah ditentukan.

Tidak hanya bertipe side-scrolling, game yang akan dibuat ini juga berjenis "Running Game" yaitu pemain akan berlari melewati rintangan yang disediakan lalu menuju spot terakhir untuk menyelesaikannya.

Berdasarkan Game Architecture Lecture dari thegamedesigninitiative Cornell University, ada beberapa hal yang perlu diperhatikan untuk membuat arsitektur sebuah game, yaitu:

<img align="middle" src="https://user-images.githubusercontent.com/30854454/31384038-775eda76-ade7-11e7-9664-4e31d5efb7ef.png">

* Game Content

  Di dalam Game Content ini berisikan model atau asset yang dibutuhkan game untuk menampilkan bermacam hal seperti Character Scripts, Character Data, UI Elements, Model and Textures, dan Sounds. Progammer menyediakan class-class yang dibutuhkan desainer untuk memasukkan data-data yang diperlukan untuk menampilkan model yang digunakan
  
* Game Engine

  Di bagian ini berisikan class-class yang diperlukan untuk mengontrol berbagai macam perhitungan dan logika yang diperlukan untuk sebuah permainan. Seperti pengaturan Input yang dilakukan pemain, pengaturan simulasi physics yang terjadi di dalam game, pengelolaan model yang ada, dan pengaturan sebuah GUI untuk ditampilkan nantinya untuk pemain. Itu semua telah diatur didalam class-class dari Game Engine yang dibuat oleh programmer
  
Adapun pola yang digunakan di dalam sebuah game, yaitu MVC (Model, View Controller). MVC memudahkan kita untuk memisahkan class-class yang akan digunakan lalu memberikan class tersebut bermacam implementasi sesuai dengan pola yang digunakan adalah Model, View, ataupun Controller.

* Model

  Model ini mendefinisikan data-data dari unsur dalam sebuah permainan, lalu memberikan respon dari permintaan controller. Jadi di dalam Model berisikan mengenai data-data yang digunakan.
  
* View

  View menampilkan model-model yang sudah disediakan untuk pemain dan juga menyediakan interface untuk controller yang nantinya akan diolah oleh controller untuk melakukan komputasi dan logika.
  
* Controller

  Controller melakukan update model dalam sebuah respon untuk events, maksudnya jika seorang pemain melakukan sebuah event seperti input, maka controller harus mengolahnya sesuai dengan apa yang dimasukkan pemain untuk dikelola nantinya di dalam controller. Controller juga akan mengupdate view sesuai model yang telah diubah jika pemain melakukan event.
  
Sampai disana saja penjelasannya, untuk mendukung game side-scrolling yang kami buat, kami menggunakan aplikasi third-party *Overlap2D* untuk penempatan model-model yang dibuat dan membuat world yang akan digunakan di game tersebut.

Setelah mengikuti sedikit tutorial dari Overlap2D, kami membangun arsitektur sederhana yang akan digunakan nantinya untuk mengembangkan game ke tingkat yang lebih lanjut.

## Run Pass World Game Architecture

| Model | View | Controller |
| ----- | -----|-----      |
|PlatformComponent|GDXRoot|PlatformSystem|
|UIStage||PlayerController|

### Model

* PlatformComponent

  Class untuk memberikan informasi dari platform, mengenai posisi dan timepass pada saat platform tersebut berada
  
* UIStage

  Class UIStage untuk memberikan tombol-tombol yang akan digunakan oleh pemain untuk memainkan game dan untuk memberikan UI yang lainnya jika diperlukan
  
### View

* GDXRoot

  Class utama dari LibGDX
  
### Controller

* PlatformSystem

  Class untuk memberikan platform sebuah logika seperti, otomatis bergerak secara vertikal
  
* PlayerController

  Class untuk menggerakan Player. Untuk game kami player bisa melakukan jump dan shoot
  
  
## Conclusion

Arsitektur yang kami gunakan merupakan source code dari contoh game platformer side-scrolling menggunakan aplikasi third-party Overlap2D. Kami masih berlatih menggunakannya untuk menjembatani desainer/artist untuk memasukkan modelnya ke dalam projek Game LibGDX kami. Pada saat ini untuk melakukan test game, kami masih menggunakan application desktop, karena jauh lebih cepat untuk compile daripada melakukan run build di Android.

First Project Code : [Run Pass World Game](https://github.com/frdiansyah11/RunPassWorld)
