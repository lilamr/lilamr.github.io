[Home](../)

[back](./)

## Bab 6: Urutan

### 6.1. Sifat-sifat Urutan

Konsep "urutan" adalah sesuatu yang sering kita jumpai dalam dunia komputasi. Beberapa jenis urutan sudah pernah kita lihat, seperti:
- **String**, yaitu rangkaian karakter.
- **File**, yang dalam perspektif program Python dianggap sebagai rangkaian baris, di mana setiap barisnya sendiri merupakan rangkaian karakter.
- **Urutan dinamis**, yang dihasilkan oleh objek Python seperti iterator file yang dibuka atau objek `range`.

Mari kita telaah sifat-sifat umum yang dimiliki oleh urutan-urutan ini.

Pertama, penting untuk dicatat bahwa semua contoh urutan di atas bukan sekadar urutan sembarangan, melainkan urutan dari jenis elemen tertentu. Dalam dunia komputasi, urutan yang kita gunakan biasanya bersifat **homogen**, artinya semua elemennya memiliki jenis yang sama—orang setidaknya kita bisa memandangnya demikian dengan menentukan kategori yang cukup umum untuk mencakup semua elemen. Misalnya, sebuah baris dalam file mungkin berisi campuran angka, huruf, dan simbol lainnya, tetapi kita bisa menyederhanakannya sebagai rangkaian karakter.

Dengan demikian, istilah **n-tuple** dan **urutan** dalam penggunaan kita sehari-hari memiliki makna yang sedikit berbeda, meskipun keduanya adalah koleksi yang terurut. Urutan diharapkan bersifat homogen, sedangkan n-tuple tidak selalu demikian. Sebaliknya, n-tuple biasanya memiliki jumlah elemen yang tetap, sementara urutan tidak memiliki batasan seperti itu. Sebagai contoh, sebuah file bisa memiliki jumlah baris yang bervariasi, dari nol hingga tak terbatas.

Sekarang, mari kita dalami beberapa sifat matematis dari urutan, menggunakan string sebagai contoh utama, lalu melihat bagaimana sifat-sifat ini juga berlaku untuk jenis urutan lainnya.

Salah satu operasi kunci pada string adalah **konkatenasi**, yaitu proses menggabungkan dua string—misalnya, string $$A$$ dan $$B$$—dengan menyusun karakter-karakter $$A$$ diikuti oleh karakter-karakter $$B$$ secara berurutan. Konsep ini juga berlaku untuk urutan lain. Misalnya, menggabungkan dua file berarti menyusun semua baris dari file pertama diikuti oleh semua baris dari file kedua, menghasilkan urutan baru yang terdiri dari baris-baris.

Namun, konkatenasi hanya masuk akal jika kedua urutan memiliki jenis elemen yang sama, sehingga hasilnya tetap homogen. Menggabungkan urutan string dengan urutan bilangan bulat, misalnya, tidak akan logis. Tetapi, jika jenis elemennya sama, hasil konkatenasi akan menghasilkan urutan baru dengan elemen-elemen yang seragam.

Kita juga mengenal konsep **string kosong**, yang merupakan kasus khusus dari **urutan kosong**—yaitu urutan dengan panjang nol. Mari kita simbolkan urutan kosong ini sebagai $$e$$. Urutan kosong memiliki sifat unik: jika digabungkan dengan urutan lain $$a$$ (dengan operasi konkatenasi ditulis sebagai “+”), maka $$e + a = a$$ dan $$a + e = a$$. Dalam istilah matematika, $$e$$ disebut sebagai **identitas** untuk operasi konkatenasi.

Konkatenasi juga memiliki sifat **asosiatif**, yang berarti bahwa untuk setiap string $$a$$, $$b$$, dan $$c$$, berlaku $$(a + b) + c = a + (b + c)$$. Sifat ini tidak hanya berlaku untuk string, tetapi untuk semua jenis urutan. Namun, konkatenasi **tidak komutatif**, artinya $$a + b \neq b + a$$, kecuali jika $$a$$ dan $$b$$ sama atau salah satunya adalah urutan kosong.

Mari kita rangkum. Misalkan $$A$$ adalah himpunan semua urutan dari elemen jenis tertentu. Maka:
- Operasi konkatenasi “+” mengambil dua elemen dari $$A$$ dan menghasilkan elemen baru yang juga ada di $$A$$.
- Konkatenasi bersifat asosiatif, tetapi tidak komutatif.
- Himpunan $$A$$ mengandung elemen identitas $$e$$, yaitu urutan kosong, yang memenuhi sifat identitas untuk konkatenasi.

### 6.2. Monoid

Bukan kebetulan bahwa Python menggunakan tanda “`*`” (atau lebih tepatnya “`+`” dalam beberapa konteks) sebagai operator konkatenasi untuk string dan, seperti yang akan kita lihat, untuk jenis urutan lainnya. Pemilihan ini terasa pas karena konkatenasi sering diibaratkan sebagai “menambahkan” satu urutan ke ujung urutan lain. Namun, kesamaan antara konkatenasi dan penambahan tidak berhenti di situ. Mari kita bandingkan dengan bilangan bulat dan operasi penambahan. Menambahkan dua bilangan bulat selalu menghasilkan bilangan bulat lain. Penambahan bersifat asosiatif, dan memiliki elemen identitas, yaitu 0, karena $$0 + n = n + 0 = n$$ untuk setiap bilangan bulat $$n$$. Dalam banyak hal, string dengan konkatenasi berperilaku mirip seperti bilangan bulat dengan penambahan.

Baik string dengan konkatenasi maupun bilangan bulat dengan penambahan adalah contoh dari struktur matematis yang disebut **monoid**. Secara sederhana, monoid adalah himpunan yang dilengkapi dengan operasi biner yang asosiatif dan memiliki elemen identitas.

Secara formal, monoid didefinisikan sebagai pasangan terurut $$(S, \otimes)$$, di mana $$S$$ adalah himpunan dan $$\otimes$$ adalah operasi biner, yang memenuhi tiga syarat berikut:

1. Untuk setiap $$a$$ dan $$b$$ dalam $$S$$, operasi $$a \otimes b$$ terdefinisi dan hasilnya juga ada di dalam $$S$$.
2. Operasi $$\otimes$$ bersifat asosiatif, sehingga untuk setiap $$a$$, $$b$$, dan $$c$$ dalam $$S$$, berlaku $$(a \otimes b) \otimes c = a \otimes (b \otimes c)$$.
3. Ada elemen $$e$$ dalam $$S$$ yang berperan sebagai identitas, sehingga untuk setiap $$a$$ dalam $$S$$, berlaku $$e \otimes a = a \otimes e = a$$.

Dengan kata lain, kita bisa menyebut $$S$$ sebagai monoid di bawah operasi $$\otimes$$, dengan $$e$$ sebagai identitasnya.

Meskipun istilah “monoid” mungkin terdengar asing atau rumit, konsepnya sebenarnya cukup sederhana dan banyak ditemukan baik dalam matematika maupun pemrograman. Berikut adalah beberapa contoh monoid yang telah kita singgung, ditambah beberapa lainnya:
- **Bilangan bulat matematis** membentuk monoid di bawah penambahan, dengan identitas 0. Mereka juga monoid di bawah perkalian, dengan identitas 1. Kedua operasi ini bersifat komutatif, dan bilangan bulat dalam Python memiliki sifat yang sama.
- **Bilangan real matematis** juga monoid di bawah penambahan (identitas 0) dan perkalian (identitas 1), dengan kedua operasi bersifat komutatif.
- **Bilangan floating-point Python** tidak sepenuhnya memenuhi syarat sebagai monoid di bawah penambahan atau perkalian karena kesalahan pembulatan. Misalnya, $$(a + b) + c$$ tidak selalu persis sama dengan $$a + (b + c)$$. Namun, dalam banyak aplikasi praktis, hasilnya cukup mendekati untuk dianggap setara.
- **Nilai Boolean dalam Python** membentuk monoid di bawah operasi `and` (dengan identitas `True`) dan `or` (dengan identitas `False`). Menariknya, sifat ini tetap berlaku meskipun Python terkadang menghasilkan nilai yang valid bahkan ketika operan kedua tidak terdefinisi atau bukan Boolean, karena definisi monoid tidak membatasi perilaku operasi di luar himpunan $$S$$.
- Misalkan `max` adalah fungsi yang mengembalikan nilai terbesar antara dua angka, sehingga $$\max(x, y) = x$$ jika $$x \geq y$$, dan $$y$$ sebaliknya. Operasi ini bisa ditulis sebagai $$x \max y$$. Operasi `max` bersifat asosiatif dan komutatif, dan bilangan bulat non-negatif membentuk monoid di bawah `max`, dengan identitas 0.
- Fungsi `min`, yang mengembalikan nilai terkecil, juga asosiatif dan komutatif. Bilangan floating-point Python membentuk monoid di bawah `min`, dengan identitas berupa nilai tak hingga (`float("inf")`).
- **Urutan elemen** dari suatu himpunan tertentu adalah monoid di bawah konkatenasi, dengan urutan kosong sebagai identitas.
- **String dalam Python** adalah monoid di bawah operasi `+`, dengan string kosong `""` sebagai identitas.

Nanti kita akan melihat bagaimana kesamaan antara monoid-monoid ini dapat dimanfaatkan dalam pemrograman.

Selain monoid, ada juga konsep yang lebih umum bernama **semigroup** dalam aljabar abstrak. Semigroup mirip dengan monoid, tetapi tidak mensyaratkan adanya elemen identitas. Dengan kata lain, semigroup hanya memerlukan operasi biner yang asosiatif. Setiap monoid adalah semigroup, tetapi tidak setiap semigroup adalah monoid.

Contoh semigroup yang bukan monoid adalah himpunan bilangan bulat positif di bawah penambahan. Karena 0 tidak termasuk dalam himpunan ini, tidak ada elemen identitas untuk penambahan. Kita akan menemui beberapa contoh lain dari semigroup tanpa identitas, tetapi kebanyakan semigroup yang akan kita bahas memiliki identitas dan karenanya juga termasuk monoid.

Sebagai catatan tambahan, ada pula struktur yang disebut **grup**, yaitu semigroup yang tidak hanya memiliki identitas, tetapi juga **invers** untuk setiap elemennya. Dalam grup, setiap elemen $$a$$ memiliki invers $$a^{-1}$$ sehingga $$a \otimes a^{-1} = e$$ dan $$a^{-1} \otimes a = e$$, di mana $$e$$ adalah identitas. Contohnya, bilangan bulat di bawah penambahan adalah grup, dengan invers setiap bilangan adalah negatifnya. Grup sangat penting dalam matematika dan bidang seperti fisika partikel, tetapi banyak monoid yang relevan dalam pemrograman—seperti string di bawah konkatenasi—bukan grup, karena sebagian besar string tidak memiliki invers. Tidak ada string yang bisa digabungkan dengan string tidak kosong untuk menghasilkan string kosong.

Beberapa monoid memiliki sifat tambahan di luar tiga syarat dasar monoid. Misalnya, bilangan bulat di bawah penambahan bukan hanya monoid, tetapi juga grup, dan operasi penambahan bersifat komutatif. Bilangan bulat juga memiliki operasi perkalian, yang terkait dengan penambahan melalui sifat distributif: $$a(b + c) = ab + ac$$. Selain itu, bilangan bulat memiliki urutan (relasi “kurang dari”), faktorisasi prima yang unik, dan banyak sifat lain. Dalam istilah matematika, bilangan bulat memiliki “struktur” yang jauh lebih kaya daripada sekadar monoid di bawah penambahan.

Sebaliknya, urutan tidak memiliki struktur tambahan seperti itu. Untuk suatu himpunan $$S$$, himpunan semua urutan terbatas dari elemen-elemen $$S$$ (dengan operasi konkatenasi) membentuk apa yang disebut oleh matematikawan sebagai **monoid bebas**. Istilah “bebas” merujuk pada fakta bahwa monoid ini hanya mematuhi aturan yang tersirat dari definisi monoid, tanpa hukum atau batasan tambahan. Dalam konteks pemrograman, ini berarti tipe data seperti string dan **daftar (list)** adalah seperti kanvas kosong: mereka bisa digunakan untuk merepresentasikan hampir segala jenis data yang bisa kita bayangkan.

String dengan konkatenasi adalah contoh klasik monoid. Mengatakan bahwa suatu himpunan dan operasi membentuk monoid berarti himpunan dan operasi tersebut, setidaknya dalam beberapa hal, berperilaku seperti string dan konkatenasi. Mereka mungkin memiliki sifat tambahan, tetapi minimal memiliki sifat-sifat dasar string dan konkatenasi. Kita bisa menggunakan string sebagai acuan untuk memahami monoid. Jika mau, kita bahkan bisa menyebut monoid sebagai “objek mirip string” atau mengatakan bahwa sesuatu “bersifat seperti string” alih-alih “adalah monoid”. Namun, istilah “monoid” sendiri sudah cukup ringkas dan tepat dalam menggambarkan konsep ini.

Pengetahuan tentang string dan konkatenasi sering kali bisa kita terapkan pada monoid lain dalam pemrograman, dengan menyesuaikan istilah yang digunakan. Misalnya, bayangkan sebuah ekspresi yang melibatkan beberapa operasi konkatenasi string:

$$
s_0 + s_1 + s_2 + \dots + s_n
$$

Karena konkatenasi bersifat asosiatif, kita tidak perlu menambahkan tanda kurung untuk menentukan urutan konkatenasi mana yang dilakukan terlebih dahulu. Kita juga tidak perlu aturan yang menentukan apakah evaluasi dilakukan dari kiri ke kanan, kanan ke kiri, atau urutan lain. Urutan evaluasi menjadi tidak relevan; kita cukup melihat ekspresi ini sebagai rangkaian operan yang digabungkan dengan operator “+”.

Pemikiran ini membawa kita pada konsep operator **“big +”**, yang bukan hanya menggabungkan dua operan, melainkan mengambil seluruh urutan operan dan mengkonsatenasinya sekaligus. 

![](attachment/Pasted%20image%2020250426202236.png)

Tidak sulit membayangkan bagaimana kita bisa menulis kode Python untuk mengimplementasikan operasi “big +” ini—detailnya kita serahkan sebagai latihan.

Setelah memahami cara kerja “big +” untuk string, kita bisa menerapkan konsep yang sama ke monoid lain. Untuk setiap operator monoid $$\otimes$$, kita bisa mendefinisikan **“big $$\otimes$$”** yang bekerja dengan cara serupa. 

![](attachment/Pasted%20image%2020250426202353.png)

Kode Python yang mengimplementasikan “big +” bisa dijadikan cetak biru untuk mengimplementasikan “big $$\otimes$$” dalam konteks monoid lain.

Operator “big” seperti ini umum ditemukan dalam matematika, dan beberapa di antaranya memiliki simbol standar. Misalnya, “big +” untuk bilangan bulat dan bilangan real dilambangkan dengan $$\Sigma$$ (huruf Yunani kapital sigma, yang berarti “jumlah”), sedangkan “big *” untuk perkalian dilambangkan dengan $$\Pi$$ (huruf Yunani kapital pi, yang berarti “produk”).

Pemahaman tentang monoid memiliki implikasi penting bagi pemrogram, dan kita akan menjelajahi beberapa implikasi ini lebih lanjut di bagian dan bab berikutnya.

### 6.3. Urutan dalam Python

Kita sudah mengenal salah satu cara Python untuk merepresentasikan urutan, yaitu **tuple**. Ada pula tipe lain yang disebut **list**. Menariknya, baik tuple maupun list dalam Python bisa digunakan untuk merepresentasikan baik n-tuple matematis maupun urutan.

**Daftar** dibuat dengan menuliskan urutan nilai yang dipisahkan oleh koma, lalu mengelilinginya dengan tanda kurung siku, seperti ini:

```python
[2, 3, 5, 7, 11]
```

Konstruksi ini disebut **tampilan daftar** (*list display*). Daftar kosong ditulis sebagai `[]`. Jika daftar hanya memiliki satu elemen, kita bisa menulisnya tanpa koma, misalnya `["John"]`, karena sintaks ini tidak memiliki arti lain.

Kita mungkin menganggap `(2, 3, 5, 7, 11)` sebagai “tampilan tuple”, tetapi sebenarnya bukan. Seperti yang sudah kita pelajari, dalam konteks ini koma berfungsi sebagai operator biner, dan koma inilah—bukan tanda kurung—yang menciptakan tuple. Meski begitu, notasi tuple dengan tanda kurung dan notasi daftar dengan tanda kurung siku sangat mirip, dan pada akhirnya memiliki makna yang serupa. Ini adalah keuntungan dari desain sintaks Python.

Daftar dan tuple memiliki banyak kesamaan. Misalnya, elemen dalam daftar diindeks mulai dari 0, dan kita bisa memilih elemen tertentu dengan notasi subskrip. Jika variabel `a` terikat pada daftar `[2, 3, 5, 7, 11]`, maka `a[2]` akan menghasilkan nilai 5.

Seperti tuple, daftar juga bisa **dibongkar** (*unpacked*) menggunakan pernyataan penugasan dengan beberapa nama di sisi kiri. Contohnya, kita pernah melakukan ini dalam skrip pada Contoh 1.2:

```python
name, email = line.split(",")
```

Fungsi `split` mengembalikan daftar dengan dua elemen jika baris mengandung satu koma. Pernyataan penugasan ini membongkar daftar tersebut ke dalam dua variabel.

Perbedaan utama antara tuple dan daftar adalah bahwa **daftar bersifat mutable**—artinya nilai elemennya bisa diubah di tempat. Misalnya, kita bisa menggunakan notasi subskrip di sisi kiri penugasan untuk mengubah elemen daftar:

```python
a = [2, 3, 5, 7, 11]
a[2] = False
```

Setelah kode ini dijalankan, `a` masih merujuk pada objek daftar yang sama, tetapi nilai daftar telah berubah menjadi `[2, 3, False, 7, 11]`. Perhatikan bahwa, seperti tuple, daftar juga bisa bersifat **heterogen**, artinya elemen-elemennya tidak harus memiliki jenis yang sama.

Karena daftar adalah objek mutable, kita perlu memahami perbedaan antara objek dan nilai dalam Python. Nama variabel dalam Python terikat pada objek, bukan langsung pada nilai. Perhatikan contoh berikut:

```python
a = [2, 3, 5, 7, 11]
b = a
a[2] = False
```

Penugasan `b = a` membuat `b` merujuk pada objek yang sama dengan `a`, atau dengan kata lain, menciptakan **alias** untuk objek tersebut. Kita harus berhati-hati dengan alias pada objek mutable, karena perubahan pada objek melalui satu nama (misalnya `a`) juga akan memengaruhi nama lain (misalnya `b`). Dalam kasus ini, setelah `a[2] = False`, nilai `b` juga menjadi `[2, 3, False, 7, 11]`, meskipun kita tidak mengubah `b` secara eksplisit.

Anda mungkin mengenal konsep **pointer** dari bahasa pemrograman lain, Anda bisa menganggap pengikatan nama dalam Python seperti pointer ke objek. Baris pertama dalam contoh di atas membuat daftar dan mengatur `a` sebagai pointer ke daftar tersebut. Baris kedua menyalin pointer tersebut ke `b`, sehingga keduanya menunjuk ke objek yang sama.

![](attachment/Pasted%20image%2020250426205049.png)

Python juga memiliki fitur yang disebut **slicing**, yaitu generalisasi dari subskrip. Untuk tuple `x`, notasi `x[i:j]` menghasilkan tuple baru yang berisi elemen dari indeks `i` hingga (tetapi tidak termasuk) indeks `j`. Hal yang sama berlaku untuk daftar. Misalnya, jika `a = [2, 3, False, 7, 11]`, maka `a[0:2]` menghasilkan `[2, 3]`. Ada juga variasi slicing yang berguna, yaitu slicing tanpa batas atas (`x[i:]`), yang mengambil semua elemen dari indeks `i` hingga akhir urutan.

Karena string juga merupakan urutan, slicing dan subskrip juga bisa diterapkan pada string. Misalnya, jika `name = "John Davis"`, maka `name[0:4]` menghasilkan string `"John"`.

Untuk tuple, daftar, atau string `a`, fungsi `len(a)` mengembalikan panjangnya, yaitu jumlah elemen atau karakter yang dimilikinya.

Python juga menyediakan operasi lain untuk urutan melalui **metode** (*method*). Kita sudah mengenal metode `startswith` untuk string. Ada pula metode yang berlaku untuk semua jenis urutan, seperti `count`, yang menghitung jumlah kemunculan nilai tertentu. Misalnya, jika `a = "Look at me!"`, maka `a.count("o")` menghasilkan 2.

Untuk daftar, yang bersifat mutable, Python menyediakan metode untuk memodifikasi daftar di tempat. Contohnya adalah metode `append`, yang menambahkan elemen ke akhir daftar. Jika `b = [1, 2, 3]`, maka setelah `b.append(4)`, nilai `b` menjadi `[1, 2, 3, 4]`.

Operator `+` bisa digunakan untuk menggabungkan dua tuple atau dua daftar, menghasilkan urutan baru dengan jenis yang sama. Dengan demikian, himpunan semua tuple Python adalah monoid di bawah `+`, begitu pula himpunan semua daftar. Ini juga berlaku untuk himpunan tuple atau daftar dengan elemen dari jenis tertentu, seperti daftar string atau tuple nama kota Eropa. Namun, Python tidak mendukung konkatenasi antara jenis yang berbeda, seperti tuple dengan daftar atau daftar dengan string.

Secara umum, tuple dan daftar memiliki perilaku yang sangat mirip, kecuali bahwa daftar bersifat mutable. Pemrogram bisa memilih antara keduanya tergantung kebutuhan. Namun, dalam buku ini, kita akan lebih sering menggunakan tuple kecuali saat membutuhkan urutan yang bisa diubah.

Seperti fungsi konversi `int`, Python memiliki fungsi `tuple` dan `list` untuk mengubah urutan dari satu jenis ke jenis lain. Misalnya, `tuple([2, 3, 5, 7, 11])` menghasilkan `(2, 3, 5, 7, 11)`, dan `list("Hello")` menghasilkan `["H", "e", "l", "l", "o"]`. Fungsi ini juga bisa diterapkan pada objek yang menghasilkan urutan, seperti objek `range` atau iterator. Contohnya, `tuple(range(5))` menghasilkan `(0, 1, 2, 3, 4)`.

Pernyataan `for` dalam Python bisa mengiterasi elemen dari segala jenis urutan. Berikut adalah contoh menggunakan tuple:

```python
for place in ("London", "Paris", "Istanbul"):
    print("Hello from " + place + "!")
```

Mengiterasi tuple berisi konstanta seperti ini adalah cara praktis untuk melakukan operasi yang sama pada sekumpulan nilai tetap.

### 6.4. Fungsi Urutan Tingkat Tinggi

Kita bisa melakukan berbagai komputasi pada urutan dengan cara yang elegan dan efisien menggunakan **fungsi tingkat tinggi** (*higher-order functions*). Mari kita perkenalkan tiga fungsi klasik—`map`, `filter`, dan `reduce`—dan jelajahi cara menggunakannya.

**Map** menerapkan fungsi satu argumen ke setiap elemen urutan, dan memproduksi tuple sebagai hasilnya. Bentuk pemanggilannya adalah:

```python
map(f, sequence)
```

Misalnya, jika kita memiliki fungsi `double` dan `square` seperti yang didefinisikan sebelumnya, maka `map(double, (2, 3, 5, 7, 11))` menghasilkan `(4, 6, 10, 14, 22)`, dan `map(square, range(10))` menghasilkan `(0, 1, 4, 9, 16, 25, 36, 49, 64, 81)`.

Berikut adalah implementasi sederhana dari `map`:

```python
def map(f, sequence):
    result = ()
    for a in sequence:
        result += (f(a),)
    return result
```

Mungkin Anda bertanya-tanya, bukankah `result += ...` mencoba mengubah tuple yang bersifat immutable? Tidak perlu khawatir. Dalam Python, `result += ...` sebenarnya sama dengan `result = result + ...`, sehingga kita tidak benar-benar mengubah `result` di tempat, melainkan menciptakan tuple baru.

Perhatikan bahwa `sequence` bisa berupa `tuple`, `list`, `range`, atau `iterator`—apa saja yang bisa diiterasi oleh pernyataan `for`.

Python sebenarnya memiliki fungsi `map` bawaan, tetapi cara kerjanya sedikit berbeda, dan kita akan membahasnya di bab berikutnya.

Fungsi berikutnya, **Filter** mengambil fungsi satu argumen yang mengembalikan nilai Boolean dan sebuah urutan, lalu menghasilkan tuple berisi hanya elemen-elemen yang membuat fungsi tersebut mengembalikan `True`. Bentuk pemanggilannya adalah:

```python
filter(test, sequence)
```

Contohnya, `filter(lambda x: x > 0, (2, 3, 0, -5, 7, -11))` menghasilkan `(2, 3, 7)`.

Kita bisa dengan mudah mendefinisikan versi `filter` kita sendiri—tugas ini kita serahkan sebagai latihan.

Fungsi **[Reduce](reduce.md)** mengambil fungsi dua argumen dan sebuah urutan, lalu “mereduksi” urutan tersebut menjadi satu nilai dengan menggabungkan elemen-elemennya menggunakan fungsi tersebut. Pemanggilannya berbentuk:

```python
reduce(f, sequence, initial)
```

Fungsi `f` bertindak seperti operator biner, dan `reduce` menggunakannya untuk menggabungkan pasangan elemen secara berurutan, dimulai dari nilai `initial`. Jika urutan kosong, `initial` dikembalikan sebagai hasil default.

Misalkan kita mendefinisikan fungsi `plus` sebagai:

```python
plus = lambda x, y: x + y
```

Jika `a` adalah urutan bilangan bulat $$(a_0, a_1, a_2, \dots)$$ dan `i` adalah nilai awal, maka `reduce(plus, a, i)` menghasilkan:

$$
i + a_0 + a_1 + a_2 + \dots
$$

Khususnya, `reduce(plus, a, 0)` menghitung jumlah semua elemen dalam `a`, yang sebenarnya adalah operasi “big +” yang kita bahas di Bagian 6.2.

Berikut adalah implementasi `reduce`:

```python
def reduce(f, sequence, initial):
    result = initial
    for a in sequence:
        result = f(result, a)
    return result
```

Menariknya, `reduce` bisa digunakan pada setiap monoid, dengan identitas monoid sebagai nilai awal. Ini memungkinkan kita mendefinisikan operasi “big” seperti yang dijelaskan sebelumnya.

Misalkan $$A$$ adalah monoid di bawah operasi $$\otimes$$, dengan identitas $$e$$, dan fungsi $$f$$ mengimplementasikan $$\otimes$$ sehingga $$f(x, y) = x \otimes y$$. Jika $$S$$ adalah urutan $$(a_0, a_1, a_2, \dots)$$ dari elemen-elemen $$A$$, maka:

$$reduce(f, S, e) = e \otimes a_0 \otimes a_1 \otimes a_2 \otimes \dots $$
$$= a_0 \otimes a_1 \otimes a_2 \otimes \dots$$

Ini adalah operasi “big $$\otimes$$” untuk urutan $$S$$.

Contohnya, untuk urutan angka `s`, `reduce(plus, s, 0)` menghitung jumlah elemennya. Kita bisa mendefinisikan fungsi `sum` sebagai:

```python
sum = lambda S: reduce(plus, S, 0)
```

Fungsi ini bertindak sebagai “big +”. Dengan cara serupa, kita bisa mendefinisikan produk elemen urutan:

```python
product = lambda S: reduce(lambda x, y: x * y, S, 1)
```

Untuk urutan string `S`, konkatenasi semua string di dalamnya adalah:

```python
cat = lambda S: reduce(lambda x, y: x + y, S, "")
```

Karena `plus` sudah mendukung konkatenasi string, kita juga bisa menulisnya sebagai `reduce(plus, S, "")`.

Implementasi `reduce` kita di atas melakukan evaluasi dari kiri ke kanan:

$$reduce(f, S, e) = (...((e \otimes a_0) \otimes a_1) \otimes a_2) \otimes ...)$$

Ini memungkinkan penggunaan `reduce` untuk operasi yang tidak harus asosiatif, selama evaluasi dari kiri ke kanan sesuai kebutuhan. Namun, jika kita membutuhkan evaluasi dari kanan ke kiri, kita bisa mendefinisikan `reduceRight`:

```python
def reduceRight(f, sequence, initial):
    if len(sequence) == 0:
        return initial
    else:
        return f(sequence[0], reduceRight(f, sequence[1:], initial))
```

Untuk operasi asosiatif seperti pada monoid, urutan evaluasi tidak masalah, sehingga `reduce` dan `reduceRight` bisa digunakan secara bergantian.

Dengan `map`, `filter`, dan `reduce`, kita bisa menyelesaikan berbagai tugas pemrograman dengan cara yang ringkas. Misalnya, kita bisa menulis ulang skrip dari Bagian 1.2 menggunakan satu ekspresi Python untuk setiap skrip.

Berikut adalah skrip pertama (Contoh 1.1), yang menampilkan setiap baris dari file `names` yang dimulai dengan “John”:

```python
file = open("names")
for line in file:
    if line.startswith("John"):
        print(line)
```

Contoh 6.1 menunjukkan cara menulis ulang skrip ini dengan gaya fungsional. Iterator `open("names")` menghasilkan urutan string, masing-masing diakhiri dengan karakter baris baru. Kita gunakan `filter` untuk memilih string yang dimulai dengan “John”, lalu `cat` (didefinisikan menggunakan `reduce`) untuk menggabungkan string-string tersebut menjadi satu. Karakter baris baru memastikan hasilnya ditampilkan dalam baris terpisah saat dicetak dengan `print`.

**Contoh 6.1. Mencari Nama dengan Gaya Fungsional**

```python
print(cat(filter(lambda x: x.startswith("John"), open("names"))))
```

Tugas menulis ulang skrip kedua (Contoh 1.2) kita serahkan sebagai latihan. Sekarang, berikut adalah skrip ketiga (Contoh 1.3), yang menghitung rata-rata bilangan bulat dalam file `observations`:

```python
sum = 0
count = 0
file = open("observations")
for line in file:
    n = int(line)
    sum += n
    count += 1
print(sum / count)
```

Untuk menulis ulangnya, kita gunakan `map` dengan fungsi `int` untuk mengubah baris file menjadi tuple bilangan bulat, lalu menerapkan fungsi yang membagi jumlah elemen (dihitung dengan `sum`) dengan panjang tuple (dihitung dengan `len`). Berikut adalah program lengkapnya:

**Contoh 6.2. Rata-rata Pengamatan dengan Gaya Fungsional**

```python
print((lambda a: sum(a) / len(a))(map(int, open("observations"))))
```

Pendekatan ini disebut **pemrograman fungsional**. Dalam pemrograman fungsional, kita menulis sarang pemanggilan fungsi alih-alih urutan pernyataan. Hasil sementara tidak disimpan dalam variabel, melainkan langsung digunakan sebagai argumen untuk pemanggilan fungsi lain. Iterasi digantikan dengan rekursi dan fungsi tingkat tinggi seperti `map`, `filter`, dan `reduce`.

Ada bahasa yang dirancang khusus untuk pemrograman fungsional, seperti LISP (dan variannya seperti Scheme), ML, dan Haskell. Namun, Python juga mendukung pemrograman fungsional dengan baik, menjadikannya alat yang fleksibel untuk menambah teknik ini ke dalam keahlian Anda.

## 6.5. Komprehensi

Python menyediakan cara lain untuk membuat daftar melalui **komprehensi daftar** (*list comprehension*), yang merupakan bentuk lain dari tampilan daftar. Komprehensi daftar membangun daftar dari satu atau lebih urutan dengan cara yang mirip dengan `map` dan `filter`, tetapi dengan sintaks yang lebih langsung menggambarkan struktur hasilnya.

Bentuk paling sederhana dari komprehensi daftar adalah:

```python
[expression for name in sequence]
```

Ini mengikat `name` ke setiap elemen dalam `sequence`, mengevaluasi `expression` untuk setiap pengikatan, dan menghasilkan daftar dari hasilnya. Contoh:

```python
[2 * n for n in range(5)]
```

Ekspresi ini menghasilkan daftar `[1, 2, 4, 8, 16]`, yaitu lima pangkat pertama dari 2. Ini setara dengan:

```python
list(map(lambda n: 2 * n, range(5)))
```

Komprehensi daftar lebih fleksibel daripada `map` karena bisa mencakup beberapa klausa `for ... in`. Contohnya:

```python
[(a, b) for a in range(6) for b in range(5)]
```

Ini menghasilkan daftar berisi 30 pasangan terurut $$(a, b)$$, dengan $$a$$ dari 0 hingga 5 dan $$b$$ dari 0 hingga 4.

Komprehensi juga mendukung penyaringan dengan sintaks:

```python
[expression for name in sequence if test]
```

Ini mirip dengan `map(expression, filter(test, sequence))`, tetapi `expression` dan `test` ditulis sebagai ekspresi, bukan fungsi, dan hasilnya adalah daftar. Contoh:

```python
[line[5:] for line in open("names") if line.startswith("John ")]
```

Ini menghasilkan daftar string berisi nama belakang dari baris dalam file `names` yang dimulai dengan “John ”, dengan asumsi setiap baris berisi nama depan dan nama belakang.

Bagaimana dengan **[komprehensi tuple](komprehensi%20tuple.md)**? Anda mungkin berpikir kita bisa menulis:

```python
(line[5:] for line in open("names") if line.startswith("John "))
```

dan mendapatkan tuple berisi nama belakang. Namun, di Python, sintaks ini menghasilkan **ekspresi generator**, bukan tuple, yang menghasilkan iterator untuk menghasilkan nilai secara dinamis. Kita akan bahas lebih lanjut tentang ekspresi generator di bab berikutnya. Untuk saat ini, anggap saja ekspresi generator sering bisa digunakan seperti komprehensi tuple dalam banyak kasus.

Python juga mendukung komprehensi untuk himpunan dan pemetaan, yang akan kita pelajari nanti.

## 6.6. Pemrosesan Paralel

Permintaan akan komputer yang mampu memproses data lebih banyak dan lebih cepat terus meningkat. Selama ini, produsen komputer memenuhi kebutuhan tersebut dengan meningkatkan kecepatan, efisiensi, dan mengurangi ukuran prosesor tradisional—yang menjalankan satu operasi pada satu data pada satu waktu. Namun, pendekatan ini mulai mencapai batas fisik, seperti ukuran molekul, kecepatan cahaya, dan panas yang dihasilkan oleh chip yang beroperasi pada frekuensi tinggi.

Masa depan komputasi jelas terletak pada **pemrosesan paralel**: menjalankan banyak operasi pada banyak data secara bersamaan. Teknologi ini sudah ada di sekitar kita:
- Banyak komputer desktop dan laptop kini dilengkapi **prosesor multi-core**, yang memiliki beberapa unit pemrosesan dalam satu chip atau kelompok chip. Jumlah inti terus bertambah setiap tahun.
- **Unit Pemrosesan Grafis (GPU)** kini cukup terjangkau untuk digunakan di komputer, konsol game, bahkan ponsel. GPU modern memiliki banyak elemen komputasi yang bekerja secara paralel, dan paralelisme ini terus meningkat.

Pemrosesan paralel akan menjadi tantangan besar bagi pemrogram di masa depan. Gaya pemrograman tradisional kita bersifat sekuensial, dengan alur kontrol yang linier. Bagaimana kita bisa menulis kode yang menghasilkan hasil sama, tetapi lebih cepat, dengan menjalankan banyak komputasi secara bersamaan?

Tantangan ini tidak mudah. Komputasi paralel harus saling berkoordinasi, dan salah satu kesulitan utama adalah mencegahnya saling mengganggu, yang bisa menyebabkan hasil yang salah. Bayangkan dua program mencoba menulis ke file yang sama secara bersamaan, misalnya.

Selama beberapa dekade, komunitas ilmu komputer telah mengembangkan teknik untuk mengatur dan menyinkronkan komputasi paralel agar tidak saling mengganggu. Topik ini sangat kompleks dan di luar cakupan buku ini. Namun, ada satu prinsip sederhana yang penting:

**Dua komputasi bisa dijalankan secara paralel jika keduanya independen, yaitu jika hasil satu komputasi tidak memengaruhi yang lain.**

Misalnya, perhatikan dua pernyataan penugasan:

```python
x = E
y = F
```

Jika ekspresi $$F$$ tidak mengakses `x`, $$E$$ tidak mengakses `y`, dan evaluasi keduanya tidak memiliki efek samping yang saling memengaruhi, maka kedua pernyataan ini independen dan bisa dijalankan secara paralel. Jika tidak, mereka harus dijalankan secara berurutan.

Menganalisis kode untuk menemukan bagian yang independen atau menulis kode yang menjamin independensi tidak selalu mudah. Namun, ada kabar baik: dalam **pemrograman fungsional**, banyak bagian dari komputasi kita secara otomatis independen, memberikan banyak peluang untuk pemrosesan paralel.

Mari kita pertimbangkan program atau bagian program yang hanya terdiri dari evaluasi ekspresi dan pemanggilan fungsi tanpa efek samping. Dalam kasus ini, peluang untuk paralelisme mudah ditemukan:
- Untuk pemanggilan fungsi seperti `f(P, Q)` atau ekspresi seperti $$P \otimes Q$$, evaluasi $$P$$ dan $$Q$$ bersifat independen, sehingga bisa dilakukan secara paralel. Ini juga berlaku untuk fungsi dengan lebih dari dua argumen.
- Dalam operasi `map(f, S)`, penerapan `f` pada setiap elemen `S` bersifat independen, sehingga semua penerapan bisa dilakukan secara paralel.
- Hal yang sama berlaku untuk `filter(test, S)`: pengujian pada setiap elemen `S` bersifat independen dan bisa dilakukan secara paralel.
- Untuk `reduce(f, S, e)`, di mana `f` adalah operasi monoid yang asosiatif dengan identitas `e`, kita bisa memecah `S` menjadi dua sub-urutan, $$S_1$$ dan $$S_2$$, sehingga $$S = S_1 + S_2$$. Karena asosiativitas, kita punya:

```python
reduce(f, S, e) = f(reduce(f, S_1, e), reduce(f, S_2, e))
```

Kita bisa mereduksi $$S_1$$ dan $$S_2$$ secara paralel, lalu menggabungkan hasilnya dengan `f`. Kita bahkan bisa memecah sub-urutan ini lebih lanjut untuk lebih banyak paralelisme.

Misalkan `S` memiliki delapan elemen $$(a_0, \dots, a_7)$$, dan `f` mengimplementasikan operasi monoid $$\otimes$$. Maka `reduce(f, S, e)` menghitung:

$$
E = a_0 \otimes a_1 \otimes a_2 \otimes a_3 \otimes a_4 \otimes a_5 \otimes a_6 \otimes a_7
$$

Karena $$\otimes$$ asosiatif, kita bisa menulis ulang $$E$$ sebagai:

$$
((a_0 \otimes a_1) \otimes (a_2 \otimes a_3)) \otimes ((a_4 \otimes a_5) \otimes (a_6 \otimes a_7))
$$

Kita bisa menghitung empat pasangan $$(a_0 \otimes a_1)$$, $$(a_2 \otimes a_3)$$, $$(a_4 \otimes a_5)$$, dan $$(a_6 \otimes a_7)$$ secara paralel, lalu menghitung dua pasangan hasilnya secara paralel, dan akhirnya menggabungkan dua hasil terakhir.

![](attachment/Pasted%20image%2020250426211351.png)

Struktur ini disebut **pohon biner** dalam matematika dan ilmu komputer, dengan “daun” (elemen urutan) di atas dan “akar” (hasil akhir) di bawah. Setiap simpul operator terhubung ke dua operan.

Pohon ini bisa diatur dengan cara lain, seperti evaluasi kiri-ke-kanan 

![](attachment/Pasted%20image%2020250503234751.png)

atau kanan-ke-kiri, 

![](attachment/Pasted%20image%2020250503234819.png)

tetapi struktur di atas adalah **pohon seimbang**, yang memiliki jumlah level minimum untuk jumlah daun tertentu. Untuk $$n$$ daun, pohon seimbang memiliki $$\lceil \log_2 n \rceil$$ level. Dalam contoh kita dengan 8 elemen, $$\log_2 8 = 3$$, sehingga ada 3 level operasi.

Jika kita melakukan **evaluasi paralel seimbang**—menjalankan semua operasi pada level yang sama secara paralel—dan menganggap satu operasi $$\otimes$$ memakan satu unit waktu, kita bisa mengevaluasi ekspresi ini dalam $$\lceil \log_2 n \rceil$$ unit waktu, asalkan kita bisa menjalankan sebanyak mungkin operasi secara paralel.

Tentu saja, ini mengabaikan **overhead**, seperti waktu untuk mengalokasikan tugas ke prosesor, mengirim hasil, dan mengoordinasikan komputasi. Overhead ini bisa signifikan, tetapi jika $$\otimes$$ adalah operasi yang mahal, evaluasi paralel seimbang bisa sangat mempercepat proses.

Kita bisa membayangkan versi `reduce` yang dirancang untuk evaluasi paralel seimbang, dengan syarat fungsi `f` bersifat asosiatif.

Kami tidak akan membahas detail teknis untuk mengimplementasikan paralelisme di Python atau platform lain, karena ini bergantung pada teknologi dan lingkungan tertentu. Namun, prinsip bahwa **komputasi independen bisa dijalankan secara paralel** adalah ide universal yang relevan di mana saja.

Menyesuaikan diri dengan dunia pemrosesan paralel memang menantang, tetapi pemrogram yang memahami sifat matematis data dan operasi, serta mahir menggunakan fungsi tingkat tinggi dan pemrograman fungsional, akan memiliki keunggulan besar.

Di bab-bab berikutnya, kita akan terus mengeksplorasi peluang untuk menerapkan pemikiran matematis dalam komputasi paralel.

**Istilah Baru dalam Bab Ini**
- Identitas (**Identity**)
- Monoid (**Monoid**)
- Alias (**Alias**)
- Pemrograman Fungsional (**Functional Programming**)
- Semigroup (**Semigroup**)
- Grup (**Group**)
- Tampilan Daftar (**List Display**)
- Objek Mutable (**Mutable Object**)
- Komprehensi Daftar (**List Comprehension**)
- Pemrosesan Paralel (**Parallel Processing**)
- Pohon (**Tree**)
- Pohon Biner (**Binary Tree**)

**Latihan**
1. Dalam aritmatika floating-point Python, coba prediksi beberapa nilai $$a$$, $$b$$, dan $$c$$ di mana $$(a + b) + c$$ tidak persis sama dengan $$a + (b + c)$$. Jelaskan alasan Anda, lalu verifikasi prediksi Anda menggunakan interpreter Python.

2. Apakah bilangan real antara 0 dan 1 (inklusif) membentuk monoid di bawah penambahan? Bagaimana dengan perkalian?

3. Apakah bilangan bulat Python membentuk monoid di bawah operasi eksponensiasi (`**`)? Jika ya, apa identitasnya?

4. Apakah operator `and` dan `or` dalam Python bersifat komutatif?

5. Dalam aljabar abstrak, ada hasil menarik: sebuah monoid hanya bisa memiliki satu elemen identitas. Artinya, jika $$e_1$$ dan $$e_2$$ keduanya adalah identitas dalam monoid yang sama, maka $$e_1 = e_2$$. Buktikan mengapa ini benar. (*Petunjuk*: Pertimbangkan $$e_1 \otimes e_2$$, dengan $$\otimes$$ sebagai operasi monoid.)

6. Tulis versi Anda sendiri dari fungsi `filter` tanpa menggunakan fungsi bawaan Python dengan nama yang sama. Pastikan fungsi Anda mengembalikan tuple.

7. Fungsi `map` dan `filter` sebenarnya adalah kasus khusus dari `reduce`. Tulis versi `map` dan `filter` menggunakan `reduce`, tanpa iterasi atau rekursi.

8. Buat fungsi tingkat tinggi `big` yang mengambil fungsi dan elemen identitas sebagai argumen, lalu menghasilkan fungsi satu argumen yang bertindak seperti versi “big” dari fungsi tersebut (lihat Bagian 6.2). Misalnya, jika `plus` didefinisikan seperti di Bagian 6.4, maka `big(plus, 0)` menghasilkan fungsi yang mengambil urutan angka dan mengembalikan jumlahnya.

9. Tulis versi `reduce` dengan hanya dua parameter, tanpa parameter `initial`. Gunakan elemen pertama urutan sebagai nilai awal. Fungsi ini hanya bisa digunakan pada urutan dengan setidaknya satu elemen, dan mengembalikan elemen tunggal untuk urutan satu elemen. Ini cocok untuk semigroup tanpa identitas.

10. Misalkan ada fungsi `reverse` yang membalikkan urutan, sehingga `reverse((1, 2, 3))` menghasilkan `(3, 2, 1)`. Seorang siswa mengusulkan definisi `reduceRight` sebagai berikut:

```python
def reduceRight(f, sequence, initial):
    return reduce(f, reverse(sequence), initial)
```

Apa masalah dengan solusi ini? Dalam situasi apa solusi ini menghasilkan hasil yang salah?

11. Tulis ulang skrip kedua dari Bagian 1.2 (yang menampilkan alamat email John Davis) sebagai satu ekspresi Python.

[back](./)
