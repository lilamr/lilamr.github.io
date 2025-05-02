[Home](../)

[back](./)

## Bab 1: Pendahuluan

### 1.1. Program, Data, dan Objek Matematis

Seorang programmer handal mampu memandang program dan data dari berbagai sudut, dengan tingkat detail yang berbeda sesuai kebutuhan. Kadang-kadang, fokusnya adalah pada bit, byte, kata mesin, dan instruksi mesin. Namun, lebih sering, jauh lebih efisien untuk berpikir dan bekerja dengan objek data serta struktur program yang lebih abstrak dan tingkat tinggi.

Pada dasarnya, di tingkat paling rendah, kode program yang dijalankan komputer hanyalah rangkaian bit yang tersusun dalam kata-kata mesin. Di masa awal perkembangan komputer, para programmer harus selalu bekerja dengan instruksi tingkat mesin ini. Kini, hampir semua programmer menggunakan bahasa pemrograman tingkat tinggi, yang memungkinkan mereka bekerja lebih cepat dan produktif.

Sama halnya dengan data. Pada tingkat terendah, semua data di komputer direpresentasikan sebagai bit yang dikelompokkan menjadi byte dan kata. Pemula dalam pemrograman perlu memahami representasi ini, dan memang seharusnya demikian. Namun, mereka juga harus tahu kapan saatnya melampaui cara pandang tingkat mesin dan mulai berpikir tentang data sebagai objek tingkat tinggi.

Inti dari buku ini adalah bahwa objek matematis sering kali menjadi objek data tingkat tinggi yang ideal. Beberapa objek matematis adalah angka, tetapi banyak lainnya—khususnya dalam matematika diskrit—memiliki sifat yang sangat berbeda, seperti yang akan kita jelajahi nanti.

Buku ini akan menyajikan pemrograman dari perspektif tingkat tinggi dengan nuansa matematis. Berikut cara kami memandang program dan data:

Program akan berupa teks yang ditulis dalam **sintaks**, suatu bentuk yang tidak terlalu mirip dengan rangkaian instruksi mesin. Sebaliknya, kami akan menggunakan bahasa pemrograman tingkat tinggi, yang sintaksnya dirancang agar mudah ditulis, dibaca, dan dipahami oleh manusia. Kami tidak akan terlalu memusingkan bagaimana konstruksi dalam bahasa pemrograman diterjemahkan ke dalam instruksi mesin.

Data dalam program kami akan disimpan di penyimpanan utama komputer—yang sering disebut sebagai “memori” secara kiasan. Meskipun memori ini bisa dianggap sebagai deretan panjang kata-kata mesin, kami biasanya tidak akan peduli bagaimana data kami direpresentasikan di sana. Dari sudut pandang kami, data akan tampak seperti **objek matematis**, seperti angka, himpunan, atau urutan. Kami menganggap memori cukup besar untuk menampung semua data yang kami butuhkan, meskipun tidak tak terbatas.

Kami juga berasumsi bahwa apa yang tampak sederhana dalam kode program juga relatif sederhana di tingkat bit, byte, dan instruksi mesin. Ada hubungan yang jelas antara kode tingkat tinggi dan implementasi tingkat rendahnya. Mahasiswa ilmu komputer atau programmer berpengalaman akan mempelajari cara membangun konstruksi tingkat tinggi dari komponen tingkat rendah, tetapi itu dibahas di buku lain, bukan di sini. Kami akan menjaga kejujuran: kami tidak akan memperkenalkan konstruksi program yang menyembunyikan proses komputasi rumit atau kompleksitas besar di balik tampilan sederhana. Dengan demikian, kami bisa sesekali mengomentari efisiensi program—mungkin tidak terlalu mendetail, tetapi tetap bermakna. Anda bisa yakin bahwa teknik pemrograman yang kami ajarkan praktis dan dapat diterapkan dalam program nyata.

Matematika adalah bahasa ilmu pengetahuan, seperti yang dikatakan banyak ilmuwan sejak zaman Galileo. Demikian pula, matematika adalah bahasa komputasi. Pendidikan ilmu komputer menjelaskan mengapa dan bagaimana ini terjadi, sekaligus membantu siswa menguasai aspek-aspek bahasa ini yang relevan bagi mereka. Buku ini mengambil langkah awal ke arah itu dengan memperkenalkan konsep-konsep matematika diskrit, menunjukkan kegunaannya dalam pemrograman, dan mendorong programmer untuk berpikir secara matematis saat bekerja.

### 1.2. Mengenal Python

Untuk contoh-contoh dalam buku ini, kami memilih **Python**, sebuah bahasa pemrograman yang populer. Ada beberapa alasan di balik pilihan ini. Python banyak digunakan untuk mengembangkan berbagai jenis perangkat lunak, tersedia di hampir semua jenis komputer, dan memiliki desain yang bersih serta intuitif. Cara menulis kode di Python umumnya sederhana, dengan sedikit kata atau tanda baca yang membingungkan. Kami yakin Anda akan menikmati belajar dan menggunakan Python.

Python termasuk dalam beberapa kategori bahasa pemrograman yang sering dibicarakan:

- **Bahasa skrip**: Meskipun tidak ada definisi pasti, istilah ini biasanya merujuk pada bahasa yang cocok untuk menulis program kecil, atau **skrip**, yang menyerupai perintah yang diketik di jendela baris perintah. Misalnya, skrip bisa digunakan untuk memanipulasi file atau mengekstrak data secara cepat. Skrip juga sering digunakan untuk mengotomatisasi tugas sistem operasi. Kami akan melihat contoh skrip Python sebentar lagi. (Contoh bahasa skrip lain: Perl dan Ruby.)
- **Bahasa berorientasi objek**: Orientasi objek adalah konsep penting dalam pemrograman, yang akan kami bahas lebih lanjut di Bab 11. Untuk saat ini, cukup tahu bahwa konsep ini sangat berguna untuk proyek pemrograman besar. (Contoh bahasa berorientasi objek lain: Java dan C++.)
- **Bahasa tingkat sangat tinggi**: Python sering disebut demikian karena menyediakan objek matematis sebagai bagian inti bahasanya, lebih dari kebanyakan bahasa lain. Kami juga bisa bekerja dengan objek ini menggunakan notasi yang mirip dengan matematika. Aspek ini akan kami manfaatkan sepanjang buku.

Tergantung cara penggunaannya, Python bisa berperan sebagai salah satu atau semua jenis bahasa ini sekaligus.

Mari kita lihat beberapa program Python sederhana untuk memberi gambaran tentang seperti apa bahasa ini.

Program pertama adalah contoh skrip pendek yang mungkin ditulis untuk sekali pakai lalu dibuang. Misalkan Anda baru menghadiri sebuah kuliah dan bertemu seseorang bernama John, tapi lupa nama belakangnya. Beruntung, dosen kuliah menyediakan file berisi nama-nama peserta, yang sudah Anda simpan di komputer dengan nama `names`. File ini berisi ratusan nama, jadi Anda ingin komputer mencari nama yang dimulai dengan “John” untuk Anda. Contoh 1.1 menunjukkan skrip Python untuk menampilkan semua baris yang dimulai dengan “John”.

**Contoh 1.1. Mencari Nama**

```python
file = open("names")
for line in file:
    if line.startswith("John"):
        print(line)
```

Jika Anda pernah memprogram sebelumnya, mungkin Anda bisa menebak apa yang dilakukan skrip ini. Tapi, mari kita jelaskan baris demi baris secara sederhana, tanpa terlalu memusingkan detail seperti tanda baca di Python—itu akan dipelajari nanti.

```python
file = open("names")
```

Baris ini membuka file bernama `names` dari sistem file komputer Anda, membuatnya siap untuk dibaca oleh program. Kami menamakan hasilnya `file`. Operasi ini sebenarnya cukup kompleks, tapi intinya sederhana: ambil file dan persiapkan untuk diproses.

Kami tidak akan membahas apa yang terjadi jika file tidak ditemukan atau tidak bisa dibaca. Dalam skrip sederhana seperti ini, programmer biasanya tidak memasukkan kode untuk menangani masalah tersebut, karena itu hanya akan mempersulit.[^1] Dalam program serius, tentu saja, Anda perlu mempertimbangkan kasus seperti ini, tapi untuk contoh kami, kami sengaja membuatnya simpel.

```python
for line in file:
```

Baris ini berarti: “Untuk setiap baris dalam `file`, lakukan perintah berikutnya.” Lebih tepatnya, ambil setiap baris satu per satu, beri nama `line`, lalu jalankan kode yang diindentasi di bawahnya.

```python
if line.startswith("John"):
```

Ini memeriksa apakah baris dimulai dengan kata “John”. Jika ya, jalankan perintah berikutnya.

```python
print(line)
```

Perintah `print` pada baris ini menampilkan baris yang dimulai dengan “John” ke layar, biasanya dalam jendela tempat Anda menjalankan program.

Jika Anda menjalankan skrip ini, hasilnya mungkin seperti ini, tergantung isi file `names`:

```
John Atencio

John Atkins

Johnson Cummings

John Davis

John Hammerstein
```

Hasil ini cukup sesuai harapan, meski ada beberapa hal yang mungkin mengejutkan. Mengapa teksnya berjarak ganda? Itu karena setiap baris di file diakhiri dengan karakter “baris baru”, dan perintah `print` menambahkan satu lagi. (Nanti, Anda akan belajar cara membuatnya berjarak tunggal jika diinginkan.) Lalu, mengapa ada nama “Johnson” di hasil? Itu karena skrip hanya mencari baris yang **dimulai dengan “John”**, bukan memeriksa nama depan secara spesifik. Meski begitu, untuk skrip sekali pakai, hasil ini cukup membantu, terutama jika mengingatkan Anda bahwa orang yang dicari adalah John Davis.

Sekarang, misalkan Anda ingin menghubungi John Davis. Beruntung lagi, dosen menyediakan file lain berisi nama dan alamat email peserta, dengan format nama dan email dipisahkan koma. Anda menyimpan file ini sebagai `emails`. Contoh 1.2 menunjukkan skrip Python untuk menemukan dan menampilkan alamat email John Davis.

**Contoh 1.2. Mencari Alamat Email**

```python
file = open("emails")
for line in file:
    name, email = line.split(",")
    if name == "John Davis":
        print(email)
```

Mari kita bedah skrip ini.

```python
file = open("emails")
for line in file:
```

Dua baris ini mirip dengan skrip sebelumnya, hanya nama filenya berbeda. Pola ini umum digunakan untuk membaca file baris demi baris.

```python
name, email = line.split(",")
```

Baris ini memecah setiap baris di file pada tanda koma, menghasilkan dua bagian: teks sebelum koma (nama) dan teks sesudah koma (email). Kami memberi nama `name` untuk bagian pertama dan `email` untuk bagian kedua.

```python
if name == "John Davis":
```

Baris ini memeriksa apakah `name` sama persis dengan “John Davis”. Python menggunakan `==` untuk membandingkan kesetaraan, karena tanda `=` sudah digunakan untuk mengaitkan nama dengan nilai (seperti di baris sebelumnya).

```python
print(email)
```

Jika nama cocok, baris ini menampilkan alamat email yang sesuai.

Sebagai contoh terakhir, mari kita coba tugas komputasi sederhana: menghitung rata-rata sekumpulan angka. Angka-angka ini bisa jadi data apa saja—misalnya, pengukuran aliran air, saldo rekening bank, atau berat kotak sereal. Untuk contoh, anggap saja ini adalah suhu harian yang Anda catat setiap hari selama sebulan, dibulatkan ke bilangan bulat. Anda menyimpan data ini dalam file bernama `observations`. Di akhir bulan, Anda ingin menghitung rata-rata suhu. Contoh 1.3 menunjukkan skrip Python untuk tugas ini.

**Contoh 1.3. Menghitung Rata-Rata Pengamatan**

```python
sum = 0
count = 0

file = open("observations")
for line in file:
    n = int(line)
    sum += n
    count += 1
    
print(sum/count)
```

Mari kita jelaskan langkah demi langkah.

```python
sum = 0
count = 0
```

Untuk menghitung rata-rata, kita perlu menjumlahkan semua angka (`sum`) dan menghitung berapa banyak angka yang ada (`count`). Kedua variabel ini dimulai dari nol.

```python
file = open("observations")
for line in file:
```

Seperti skrip sebelumnya, baris ini membuka file dan memerintahkan program untuk memproses setiap baris.

```python
n = int(line)
```

Setiap baris di file adalah teks (misalnya, “23” untuk suhu 23°C). Perintah `int(line)` mengubah teks ini menjadi bilangan bulat, yang kami simpan sebagai `n`.

```python
sum += n
count += 1
```

Dalam Python, "`+=`" berarti "tambahkan hal di sebelah kanan ke hal di sebelah kiri". Jadi, "`sum += n`" berarti "tambahkan n ke sum" dan "`count += 1`" berarti "tambahkan 1 ke count". Ini adalah cara untuk mengakumulasikan **jumlah** suhu dan **banyak** suhu yang tercatat pada file.

```python
print(sum/count)
```

Setelah semua baris diproses, baris ini menghitung rata-rata (`sum` dibagi `count`) dan menampilkannya.

Perhatikan bahwa kami menggunakan baris kosong untuk memisahkan bagian-bagian logis dalam kode. Ini tidak memengaruhi cara kerja program, tapi membuat kode lebih mudah dibaca.

Ketiga skrip ini adalah contoh sederhana dari Python. Namun, mereka hanya menunjukkan fitur dasar bahasa ini. Python memiliki banyak kemampuan lain yang akan kita jelajahi di bab-bab berikutnya.

### 1.3. Sekilas tentang Terminologi Matematis

Sekarang, mari kita kenali beberapa istilah matematis yang akan sering muncul dalam buku ini. Kami tidak akan melakukan perhitungan rumit atau membuktikan teorema, tetapi kami akan menggunakan istilah-istilah ini sebagai cara berbicara tentang program dan masalah yang bisa diselesaikannya.

Istilah pertama adalah **Himpunan (Set)**: Kumpulan benda yang tidak terurut dan semuanya berbeda. Contohnya, himpunan orang di ruangan, himpunan buku yang Anda baca tahun ini, atau himpunan barang di toko tertentu.

![](attahcment/Pasted%20image%2020250416145436.png)

Istilah berikutnya adalah **Urutan (Sequence)**: Kumpulan benda yang terurut, di mana urutan kemunculannya penting. Berbeda dengan himpunan, elemen dalam urutan bisa berulang. Urutan tidak memiliki sifat bahwa semua hal di dalamnya harus berbeda. Contohnya, urutan digit dalam nomor telepon atau urutan huruf dalam nama Anda.

![](attahcment/Pasted%20image%2020250416153657.png)

Kedua istilah ini mungkin terdengar familiar, tapi dalam matematika, mereka memiliki makna khusus. Urutan, misalnya, punya sifat matematis yang akan berguna nanti. Untuk saat ini, perhatikan saja perbedaan antara konsep "set" dan "sequence".

Mari kita coba terapkan konsep ini pada skrip-skrip tadi. Data apa yang diolah oleh masing-masing skrip, dan jenis objek matematis apa itu?

Pertama, setiap skrip bekerja dengan berkas/file, yang oleh Python isinya dilihat sebagai **urutan baris**. 

Kode seperti ini sangat umum untuk membaca file baris demi baris:

```python
file = open("observations")
for line in file:
```

Secara umum, konstruksi Python `for element in sequence:` adalah cara untuk memproses setiap elemen dalam urutan, satu per satu. Selain itu, setiap baris dalam file adalah **urutan karakter**. Jadi, file bisa dianggap sebagai **urutan dari urutan**.

Mari kita lihat lebih dalam.

Pada **Skrip 1 (Nama, Contoh 1.1)**: File `names` berisi daftar nama. Dari sudut pandang kita, urutan nama dalam file tidak penting; kita hanya ingin nama yang dimulai dengan “John”. Jika tidak ada nama yang berulang (misalnya, karena kesalahan dosen), data ini adalah **himpunan**. Inputnya adalah himpunan nama peserta kuliah, dan outputnya adalah himpunan nama yang dimulai dengan “John”—dalam istilah matematis, **subset** dari himpunan input. Meski nama mungkin diurutkan (misalnya, alfabetis), urutan itu tidak relevan untuk tujuan kita.
  
Pada **Skrip 2 (Email, Contoh 1.2)**: File `emails` berisi baris-baris dengan nama dan email, dipisahkan koma. Setiap baris adalah **pasangan terurut** `(nama, email)`, karena urutan (nama dulu, lalu email) penting—`(nama, email)` tidak sama dengan `(email, nama)`. Pasangan terurut tidak sama dengan himpunan yang terdiri dari dua elemen.

![](attahcment/Pasted%20image%2020250416150951.png)

Sekarang bagaimana dengan file secara keseluruhan? Seperti file input untuk program pertama, ini adalah sebuah **set**. Kita tidak peduli apakah file diurutkan berdasarkan nama atau alamat email, atau tidak diurutkan sama sekali; kita hanya ingin menemukan pasangan terurut di mana elemen pertama adalah "John Davis" dan menampilkan elemen kedua yang sesuai (sebagai pasangan dari elemen pertama). Secara keseluruhan, file ini adalah **himpunan pasangan terurut**.

![](attahcment/Pasted%20image%2020250416151647.png)

Ada istilah matematis lain untuk himpunan dari pasangan terurut yaitu disebut **relasi (relation)**. Kita dapat melihat himpunan pasangan terurut sebagai struktur matematis yang menghubungkan pasangan-pasangan elemen satu sama lain. Dalam hal ini menghubungkan nama dengan email. 

![](attahcment/Pasted%20image%2020250416152003.png)

Jika setiap nama hanya punya satu email, maka disebut dengan istilah **pemetaan (mapping)**, yaitu relasi di mana setiap elemen pertama (nama) hanya terkait dengan satu elemen kedua (email). Dalam matematika, pemetaan sering disebut dengan istilah "fungsi". Anda mungkin tahu tentang fungsi matematis seperti akar kuadrat dan fungsi trigonometri. Tapi kami akan menggunakan istilah “pemetaan” untuk menghindari kebingungan dengan istilah fungsi dalam pemrograman. Kami tidak tahu apakah file ini benar-benar pemetaan—mungkin ada nama dengan beberapa email—tapi untuk saat ini kita abaikan dulu: jika program kami menampilkan lebih dari satu alamat email untuk "John Davis", itu tidak masalah.

![](attahcment/Pasted%20image%2020250416152118.png)

Pada **Skrip 3 (Rata-Rata, Contoh 1.3)**: File `observations` berisi angka suhu. Saat menghitung rata-rata, urutan angka tidak penting, karena penjumlahan mengikuti dua sifat dasar penjumlahan bilangan bulat:
- **Sifat asosiatif**: `(a + b) + c = a + (b + c)` untuk setiap bilangan bulat  a, b, dan c
- **Sifat komutatif**: `a + b = b + a` untuk setiap bilangan bulat a dan b

Namun, angka bisa berulang (misalnya, suhu 23°C muncul lebih dari sekali). Karena itu, data ini bukan himpunan, melainkan **multihimpunan (multiset)**, yaitu kumpulan tak terurut yang boleh berisi elemen berulang. Elemen apa pun dapat muncul dalam multiset lebih dari sekali. Tetapi multiset, seperti himpunan, adalah kumpulan tak terurut.

![](attahcment/Pasted%20image%2020250416153227.png)

Tapi, jika kita ingin memplot suhu untuk melihat tren (seperti Gambar 1.1), urutan data menjadi penting, dan kami akan memandangnya sebagai **urutan**.

**Gambar 1.1. Suhu Selama Sebulan dengan Garis Tren**

![](attahcment/Pasted%20image%2020250416153311.png)

Intinya di sini adalah bahwa jenis objek matematis apa yang menjadi kumpulan data, dari sudut pandang seorang programmer, tidak hanya bergantung pada sifat-sifat data tetapi juga pada apa yang ingin dilakukan programmer dengan data tersebut. Jenis objek matematis yang mewakili data tergantung pada **sifat data** dan **apa yang ingin kita lakukan dengannya**.

Berikut ringkasan objek matematis yang telah kita bahas sejauh ini:
- Himpunan (set)
- Multihimpunan (multiset)
- Urutan (sequence)
- Pasangan terurut (ordered pair)
- Relasi (relation)
- Pemetaan (mapping)

Dan berikut penerapannya dalam skrip-skrip contoh kita:
- File secara umum: **urutan dari urutan**.
- Data skrip 1 (nama): **himpunan**.
- Data skrip 2 (email): **himpunan pasangan terurut**, membentuk **relasi**, mungkin **pemetaan**.
- Data skrip 3 (rata-rata): **multihimpunan**; jika untuk tren, **urutan**.

Di bab-bab berikutnya, kita akan menjelajahi sifat-sifat objek matematis ini dan bagaimana mereka terhubung dengan data dan komputasi dalam program. Untuk saat ini, dua poin penting:
- Data dalam program biasanya bisa dilihat sebagai himpunan, urutan, pemetaan, atau objek matematis lain yang sudah dikenal.
- Satu kumpulan data bisa dipandang sebagai lebih dari satu jenis objek matematis, tergantung tujuan penggunaannya.

**Istilah yang Diperkenalkan di Bab Ini**
- Skrip (script)
- Himpunan (set)
- Urutan (sequence)
- Pasangan terurut (ordered pair)
- Relasi (relation)
- Pemetaan (mapping)
- Sifat asosiatif (associative property)
- Sifat komutatif (commutative property)
- Multihimpunan (multiset)

[back](./)

---

[^1]: Istilah untuk kode tersebut adalah "penanganan pengecualian/ exception handling", jika Anda ingin mencari topik dalam dokumentasi Python. Penanganan pengecualian dengan benar bisa rumit, kadang -kadang melibatkan keputusan desain yang sulit, itulah sebabnya kami memilih untuk memperlakukan topik sebagai di luar ruang lingkup buku saat ini.


