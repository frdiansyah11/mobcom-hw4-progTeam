# Physics Engine

<strong>Box2D C++ tutorials - Forces and impulses</strong>

<strong>Forces and impulses</strong>

Untuk memindahkan hal-hal di sekitar, Anda harus menerapkan kekuatan atau impuls ke tubuh. Pasukan bertindak secara bertahap dari waktu ke waktu untuk mengubah kecepatan tubuh sementara impuls dapat mengubah kecepatan tubuh segera.

<strong>Linear movement</strong>

Kita perlu beberapa cara untuk mempengaruhi badan-badan ini tanpa menggunakan mouse. Sekarang akan menjadi waktu yang baik untuk memeriksa fitur input keyboard dari testbed. Menimpa fungsi Keyboard dari kelas Test untuk menggunakan metode yang berbeda untuk masing-masing tubuh

<strong>Angular</strong>

gerakan sudut dapat dikontrol dengan menggunakan pasukan sudut (torsi) dan impuls sudut. Ini berperilaku mirip dengan rekan-rekan linear mereka berlaku yang bertahap dan impuls adalah segera.

Gerakan sudut juga dapat dikontrol oleh kekuatan-kekuatan dan dorongan, dengan bertahap / karakteristik langsung sama dengan versi linear mereka. Gaya sudut disebut torsi.

<strong>Box2D C++ tutorials - Fixtures</strong>

<li>Perlengkapan</li>
<li>Bentuk</li>
<li>Massa Jenis</li>
<li>Perlengkapan Berganda</li>
<li>Gesekan</li>
<li>Restitusi</li>
<li>Pergantian Perlengkapan Atribut pada saat Run-Time</li>
<li>Iterasi Perlengkapan di Tubuh</li>
<li>Pembersih</li>

<strong>Box2D C++ tutorials - Collision callbacks</strong>

<strong>Callback</strong>

Ketika tubuh bergerak dalam adegan fisika dan terpental satu sama lain, Box2D akan menangani semua tabrakan yang diperlukan dan respon sehingga kita tidak perlu khawatir tentang itu. Tapi seluruh titik membuat permainan fisika adalah bahwa kadang-kadang sesuatu terjadi dalam permainan sebagai hasil dari beberapa mayat memukul satu sama lain misalnya. ketika pemain menyentuh sebuah rakasa ia harus mati, atau bola memantul di tanah harus membuat suara dll Kita perlu cara untuk mendapatkan informasi ini kembali dari mesin fisika. 

Ini adalah fungsi  untuk mengambil beberapa tindakan ketika dua entitas bertabrakan. Belum tahu apa yang dua entitas akan, sehingga mereka harus melewati fungsi sebagai parameter ketika tabrakan benar-benar terjadi. Kemudian diberikan fungsi ini untuk Box2D seolah-olah mengatakan "ketika tabrakan terjadi, memanggil kembali ke fungsi ini".

<strong>Timing</strong>

Tabrakan antara entitas di dunia akan terdeteksi selama fungsi b2World :: Langkah () yang disebut setiap kali langkah. Seperti yang kita lihat di topik di dunia , yang b2World :: fungsi Langkah kemajuan simulasi, bergerak semua badan sekitar dan sebagainya. Begitu tabrakan terdeteksi, aliran program akan diberikan kepada fungsi callback Anda untuk melakukan sesuatu, dan kemudian kembali ke b2World :: Langkah untuk melanjutkan dengan lebih pengolahan. Sangat penting untuk dicatat bahwa sejak callback Anda sedang dipanggil tepat di tengah-tengah proses loncatan, tidak harus melakukan apa pun untuk mengubah tempat kejadian langsung - mungkin ada lebih tabrakan terjadi dalam waktu yang sama langkah.

<div align="center"><img src="https://www.iforce2d.net/image/collision-callbacks-flow.png" /></div>

<strong>Information</strong>

Dalam contoh ini tubuh yang dinamis memiliki empat perlengkapan, salah satu yang baru saja dimulai untuk menghubungi fixture tunggal tubuh statis di bawahnya. Parameter kontak yang diberikan untuk BeginContact akan kembali salah satu perlengkapan tersebut dengan GetFixtureA (), dan yang lainnya dengan GetFixtureB (). Kita tidak tahu yang mana, jadi kita akan perlu memeriksa.

<div align="center"><img src="https://www.iforce2d.net/image/collision-callbacks-contacts.png" /></div>
