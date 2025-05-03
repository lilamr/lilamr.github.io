[Home](../)

[back](./)

## Bab 5: Tupel

### 5.1. Pasangan Terurut dan n-Tupel

Di bab ini, kita akan mulai menjelajahi dunia struktur matematika dan bagaimana struktur tersebut dapat diterapkan dalam pemrograman. Beberapa struktur matematika ini sudah kita lihat sekilas pada contoh-contoh di Bab 1. Mari kita mulai dengan konsep pasangan terurut.

Kata "pasangan" di sini merujuk pada pengelompokan dua hal, sedangkan "terurut" menunjukkan bahwa urutan antara elemen pertama dan kedua sangat penting. Elemen-elemen ini bisa berbeda jenis, memiliki makna berbeda, atau perbedaan urutannya penting karena alasan tertentu. Dengan kata lain, pasangan terurut berbeda dari himpunan dua elemen, yang tidak mempedulikan urutan.

Salah satu kegunaan utama pasangan terurut adalah untuk menentukan posisi atau titik dalam ruang dua dimensi, seperti garis lintang dan bujur di permukaan Bumi, atau koordinat horizontal dan vertikal pada bidang datar. Bilangan kompleks juga memiliki kemiripan: bagian real dan imajiner biasanya divisualisasikan sebagai koordinat pada "bidang kompleks".

Konsep serupa dengan tiga elemen disebut "tripel terurut". Misalnya, untuk menentukan posisi titik dalam ruang tiga dimensi, kita memerlukan tiga koordinat, yang membentuk tripel terurut. Dalam konteks tertentu, kata "terurut" bisa dihilangkan karena sudah dianggap implisit, sehingga kita cukup menyebutnya "tripel" atau bahkan "pasangan" saja.

Untuk pengelompokan empat elemen, kita menyebutnya "kuadrupel terurut" atau hanya "kuadrupel". Jika elemennya lebih banyak, penamaannya mengikuti pola yang sama: kuintupel (lima), sekstupel (enam), septupel (tujuh), oktupel (delapan), dan seterusnya.

Namun, menggunakan awalan Latin untuk jumlah elemen yang besar bisa terasa merepotkan. Selain itu, kita membutuhkan istilah umum untuk merujuk pada pengelompokan dengan jumlah elemen berapa pun. Istilah matematika yang digunakan adalah *n-tupel*. Kita cukup mengganti *n* dengan angka tertentu saat merujuk pada jumlah elemen spesifik. Misalnya, 4-tupel sama dengan kuadrupel, dan 2-tupel sama dengan pasangan terurut.

Dalam matematika, n-tupel biasanya ditulis dengan elemen-elemen yang dipisahkan koma dan diapit tanda kurung, seperti (3, 4) atau (x, y, z). N-tupel sering digunakan untuk membangun objek matematika yang lebih kompleks dari elemen-elemen sederhana. Berikut adalah beberapa definisi umum dalam matematika dan ilmu komputer yang menggunakan n-tupel:

>Sebuah graf *G* didefinisikan sebagai pasangan (*V*, *E*), di mana *V* adalah himpunan simpul dan *E* adalah himpunan sisi.
>
>Sebuah tata bahasa didefinisikan sebagai 4-tupel (*N*, *T*, *P*, *S*), di mana *N* adalah himpunan simbol nonterminal (*nonterminal alphabet*), *T* adalah himpunan simbol terminal (*terminal alphabet*), *P* adalah himpunan aturan produksi (*productions*), dan *S* adalah simbol awal.

Dalam penggunaan matematis, n-tupel biasanya memiliki jumlah elemen yang terbatas, sering kali kecil. Elemen-elemennya tidak harus dari jenis yang sama, tetapi juga tidak harus berbeda seperti dalam himpunan.

### 5.2. Tupel dalam Python

Dalam Python, konsep n-tupel matematika diwujudkan melalui tipe data bernama *tuple*. Tupel dalam Python dibuat dengan menggunakan koma sebagai pemisah, seperti berikut:

```python
pasangan = 3, 4
kuadrupel = "Nomor cerita", 3, "adalah", True
```

Seperti terlihat pada contoh kedua, elemen-elemen dalam tupel Python tidak harus memiliki tipe yang sama.

Banyak pemrogram Python memilih untuk mengapit tupel dalam tanda kurung, seperti ini:

```python
pasangan = (3, 4)
kuadrupel = ("Nomor cerita", 3, "adalah", True)
```

Meskipun tanda kurung tidak wajib dalam notasi tupel Python, mereka sering diperlukan untuk kejelasan sintaksis. Misalnya, untuk mengirim tupel (3, 4) ke fungsi *f*, kita menulis *f((3, 4))*, karena *f(3, 4)* akan dianggap sebagai pengiriman dua argumen terpisah. Selain itu, penggunaan tanda kurung selaras dengan notasi matematika dan konsisten dengan notasi untuk tipe data lain di Python, seperti daftar (*list*) dan himpunan (*set*). Oleh karena itu, dalam buku ini, kita akan biasanya menggunakan tanda kurung untuk tupel.

Ada dua kasus khusus dalam notasi tupel. Pertama, tupel kosong ditulis sebagai *()*. Kedua, tupel dengan satu elemen ditulis dengan menambahkan koma setelah elemen tersebut, biasanya diapit tanda kurung, seperti *(3,)*. Koma ini penting untuk membedakan tupel satu elemen dari nilai biasa: misalnya, *(3,)* adalah tupel, sedangkan *(3)* hanyalah ekspresi bilangan dengan nilai 3. Meskipun tupel kosong dan tupel satu elemen tampak sederhana, keduanya memiliki kegunaan praktis, seperti yang akan kita lihat nanti.

Operator koma dalam Python "mengemas" beberapa nilai menjadi satu objek tupel. Untuk "membongkar" tupel, kita bisa menggunakan sintaks yang mencerminkan proses pengemasan, yaitu pernyataan penugasan dengan beberapa nama di sisi kiri, dipisahkan oleh koma. Misalnya, jika *pasangan* bernilai *(3, 4)*, pernyataan berikut akan membongkar tupel tersebut, memberikan nilai 3 ke *x* dan 4 ke *y*:

```python
x, y = pasangan
```

Kita juga bisa mengapit nama-nama di sisi kiri dalam tanda kurung untuk memperjelas bahwa kita sedang membongkar tupel:

```python
(x, y) = pasangan
```

Notasi ini membantu menegaskan bahwa kita tidak sekadar mengikat *x* dan *y* ke tupel secara keseluruhan.

Salah satu penggunaan populer sintaks pembongkaran tupel adalah penugasan simultan, seperti:

```python
x, y = y, x
```

Pernyataan ini mengevaluasi *y* dan *x*, mengemasnya menjadi tupel, lalu membongkar tupel tersebut untuk mengikat kembali nilai-nilai ke *x* dan *y*. Efeknya, nilai *x* dan *y* ditukar tanpa perlu variabel sementara, seolah-olah penugasan dilakukan secara bersamaan.

Kita juga bisa mengakses elemen tupel berdasarkan posisinya, dengan indeks dimulai dari 0. Misalnya, jika *x* bernilai *(7, 13)*, maka *x[0]* bernilai 7 dan *x[1]* bernilai 13. Sintaks ini mirip dengan notasi subskrip dalam matematika, di mana elemen-elemen tersebut akan ditulis sebagai *x₀* dan *x₁*.

### 5.3. File dan Basis Data

Banyak penerapan n-tupel dalam dunia komputasi melibatkan koleksi n-tupel yang seragam, yaitu tupel-tupel dalam koleksi memiliki jumlah elemen yang sama, dengan tipe dan makna yang konsisten untuk setiap posisi elemen. Kita sudah melihat contohnya di Bab 1 (Contoh 1.2): sebuah file yang berisi pasangan terurut, masing-masing berisi nama dan alamat email. Seperti dibahas sebelumnya, koleksi seperti ini sering dianggap sebagai himpunan atau urutan tupel.

Banyak file komputer dapat dipandang sebagai koleksi semacam ini. Umumnya, file tersebut terbagi menjadi baris-baris, dan setiap baris terbagi lagi menjadi bidang-bidang. Bidang-bidang ini bisa memiliki panjang karakter tetap, tetapi kini lebih sering dipisahkan oleh pembatas (*delimiter*), seperti koma pada file nama-dan-email di Contoh 1.2. Pembatas lain yang umum digunakan adalah karakter tab atau serangkaian spasi.

File seperti ini sering disebut *file datar* (*flat file*), karena tidak memiliki struktur kompleks selain pembagian ke dalam baris dan bidang. Jika pembatasnya adalah koma, file tersebut disebut dalam format CSV (*Comma-Separated Values*). Banyak aplikasi populer menyimpan data dalam format CSV atau dapat mengekspor datanya ke format ini untuk digunakan oleh program lain.

Basis data, pada dasarnya, juga sering kali merupakan koleksi n-tupel. Khususnya, basis data relasional didefinisikan secara eksplisit dalam kerangka matematika. Basis data relasional terdiri dari sekumpulan relasi, dan setiap relasi adalah himpunan tupel yang menyerupai n-tupel matematika. Di Bab 1, kita mendefinisikan relasi sebagai himpunan pasangan terurut, yang sebenarnya adalah kasus khusus yang disebut *relasi biner*. Dalam matematika, relasi didefinisikan lebih umum sebagai himpunan n-tupel untuk suatu *n* tertentu, dan relasi dalam basis data relasional mengikuti konsep ini.

Relasi dalam basis data dapat divisualisasikan sebagai tabel, dan istilah "tabel" sering digunakan secara bergantian dengan "relasi". Setiap elemen dalam tabel disebut "tupel" atau "rekaman", dan setiap komponen tupel disebut "bidang". Bidang-bidang ini diidentifikasi oleh nama, yang dalam visualisasi tabel ditampilkan sebagai judul kolom.

| nama    | proyek | lab |
|---------|--------|-----|
| Lambert | Alpha  | 221 |
| Torres  | Alpha  | 244 |
| Malone  | Beta   | 152 |
| Harris  | Beta   | 152 |
| Torres  | Beta   | 152 |

Namun, secara ketat, tupel dalam basis data relasional tidak sepenuhnya sama dengan n-tupel matematika. Dalam basis data, bidang diidentifikasi hanya oleh nama, bukan posisi, sehingga urutan kolom dalam tabel sebenarnya tidak relevan. Dengan demikian, tupel basis data lebih tepat digambarkan sebagai kumpulan bidang bernama atau pemetaan dari nama bidang ke nilai.

Pada sistem basis data relasional sederhana, relasi sering disimpan dalam file datar, satu file untuk setiap relasi. Banyak sistem basis data juga mendukung ekspor data ke format ini. Format yang umum adalah variasi CSV, dengan urutan bidang yang dipilih secara arbitrer. Baris pertama file biasanya berisi nama-nama bidang, dipisahkan oleh koma, diikuti oleh baris-baris yang merepresentasikan tupel. File seperti ini tidak sepenuhnya "datar" karena memiliki struktur minimal. Kita bisa memandang file tersebut sebagai pasangan terurut: komponen pertama adalah baris nama bidang, dan komponen kedua adalah urutan baris yang mewakili himpunan tupel.

Contoh isi file:

```
proyek,nama,lab
Alpha,Lambert,221
Alpha,Torres,244
Beta,Malone,152
Beta,Harris,152
Beta,Torres,152
```

Kita akan membahas lebih lanjut tentang file datar, file CSV, dan basis data relasional di bab-bab berikutnya.

**Istilah Baru yang Diperkenalkan di Bab Ini**  
- Tripel, kuadrupel, dan seterusnya  
- n-Tupel  
- Pembatas (*delimiter*)  
- File datar (*flat file*)  
- Format CSV  
- Basis data relasional  
- Relasi biner  

[back](./)
