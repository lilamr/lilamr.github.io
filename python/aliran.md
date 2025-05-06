[Home](../)

[back](./)

## Bab 7: Aliran (Streams)

### 7.1. Urutan yang Dibuat Secara Dinamis

Sebagian data urutan tersimpan dalam struktur statis, seperti string, tuple, atau list di Python. Urutan "statis" ini bisa saja bersifat mutable, seperti list Python, tetapi pada satu waktu, data tersebut ada sebagai struktur yang utuh dan lengkap. Namun, ada pula urutan yang dihasilkan secara dinamis, tidak tersedia sekaligus, melainkan muncul seiring waktu.

Bayangkan sebuah aliran masukan (*input stream*). Bagi sebuah program, aliran ini tampak seperti urutan nilai—entah itu baris teks, karakter, atau angka dari sensor—yang datang satu per satu, bukan sekaligus. Beberapa aliran masukan bahkan tidak punya akhir; data terus mengalir tanpa henti.

Kita akan menyebut urutan yang dihasilkan secara dinamis ini sebagai *stream* atau aliran. Jadi, ada dua jenis urutan: urutan statis dan aliran.

Di Python, aliran dihasilkan oleh dua jenis objek yang sudah kita kenal: iterator dan objek *range*. Objek *range* tidak sepenuhnya sama dengan iterator—ada beberapa fungsi tambahan yang bisa digunakan, seperti fungsi *len*, yang tidak berlaku untuk iterator. Namun, untuk keperluan kita, keduanya cukup mirip sehingga kita jarang perlu membedakannya. Kecuali disebutkan secara khusus bahwa objek *range* berbeda, apa yang kita bahas tentang iterator di sini juga berlaku untuk objek *range*.

Cara paling umum untuk menggunakan iterator adalah dengan pernyataan *for*:

```python
for nama in iterator:
    pernyataan
```

Berikut contoh sederhana yang mungkin sudah familiar (Contoh 1.1). Fungsi *open* mengembalikan sebuah iterator yang memungkinkan kita mengakses isi file baris demi baris.

```python
file = open("names")
for line in file:
    if line.startswith("John"):
        print(line)
```

Pertanyaannya, apa yang terjadi jika nilai setelah kata "in" bukan iterator, melainkan urutan statis, seperti dalam contoh berikut?

```python
for place in ("London", "Paris", "Istanbul"):
    print("Halo dari " + place + "!")
```

Inilah yang terjadi di balik layar: Python secara otomatis membuat iterator untuk menghasilkan nilai-nilai dari urutan statis tersebut. Pernyataan *for* kemudian menggunakan iterator itu, memanggilnya berulang-ulang hingga semua nilai telah diambil.

Seperti yang kita pelajari di bab sebelumnya, Python memiliki konstruksi bernama *generator expression* (ekspresi generator). Sekilas, ini mirip seperti *tuple comprehension*, tetapi sebenarnya ia menghasilkan urutan secara dinamis—dengan kata lain, sebuah aliran.

Ekspresi generator menggunakan sintaks yang mirip dengan *list comprehension*, tetapi dengan tanda kurung biasa `()` alih-alih kurung siku `[]`. Contohnya:

```python
(line[5:] for line in open("names") if line.startswith("John "))
```

Hasil dari ekspresi generator ini adalah sebuah iterator. Seperti yang kita tahu, iterator adalah objek yang bisa kita berikan nama, kita teruskan ke fungsi, atau kita gunakan untuk keperluan lain.

Ekspresi generator ini menarik karena didefinisikan menggunakan iterator lain, yaitu iterator yang dikembalikan oleh fungsi *open*. Faktanya, cukup umum untuk mendefinisikan iterator berdasarkan iterator lain, seperti yang akan kita lihat nanti. Mari kita perhatikan apa yang terjadi saat kita menggunakan ekspresi ini:

```python
surnames = (line[5:] for line in open("names") if line.startswith("John "))
for s in surnames:
    print(s)
```

Ketika ekspresi generator dievaluasi, ia menciptakan sebuah iterator, dan nama *surnames* diikatkan ke iterator tersebut. Pernyataan *for* kemudian memanggil iterator *surnames* untuk mengambil nilai satu per satu. Setiap kali dipanggil, iterator *surnames* meminta baris baru dari iterator file yang dibuka, sehingga sebuah baris dibaca dari file dan diikatkan ke variabel *line*. Selanjutnya, `line[5:]` dihitung, hasilnya diikatkan ke *s*, dan tubuh pernyataan *for* dijalankan.

Satu hal yang perlu diperhatikan: apa yang terjadi jika kita mencoba menggunakan iterator yang sama untuk kedua kalinya?

```python
surnames = (line[5:] for line in open("names") if line.startswith("John "))
for s in surnames:
    print(s)
for s in surnames:
    print(s)
```

Pada iterasi kedua, iterator tidak menghasilkan apa-apa! Ini karena nilai yang diambil dari iterator bersifat "sekali pakai". Setelah pernyataan *for* selesai mengiterasi semua nilai yang dihasilkan iterator, iterator tersebut menjadi "kosong".

### 7.2. Fungsi Generator

Python menyediakan satu lagi alat untuk menghasilkan urutan secara dinamis: *generator function* (fungsi generator). Ini adalah fungsi khusus yang mengembalikan iterator. Kita sudah mengenal salah satu contohnya, yaitu fungsi bawaan *open*, yang membuka file dan mengembalikan iterator untuk menghasilkan baris-baris teks dari file tersebut. Sekarang, kita akan belajar cara membuat fungsi generator sendiri.

Fungsi generator menghasilkan nilai melalui pernyataan *[yield](yield.md)*, yang bentuknya seperti ini:

```python
yield ekspresi
```

Setiap fungsi yang mengandung pernyataan *yield* secara otomatis dianggap sebagai fungsi generator oleh Python, bukan fungsi biasa. Berikut adalah contoh fungsi generator:

```python
def fibs(n):
    a = 1
    b = 1
    for i in range(n):
        yield a
        a, b = b, a + b
```

Fungsi *fibs* ini menghasilkan urutan sepanjang *n*, di mana dua nilai pertama adalah 1 dan 1, dan setiap nilai berikutnya adalah jumlah dari dua nilai sebelumnya. Ini adalah urutan Fibonacci yang terkenal. Misalnya, jika kita memanggil *fibs(7)*, hasilnya adalah 1, 1, 2, 3, 5, 8, 13.

Saat fungsi generator dipanggil, Python tidak langsung menjalankan tubuh fungsi. Sebaliknya, ia mengembalikan sebuah iterator yang akan menjalankan tubuh fungsi tersebut. Ketika iterator ini diminta untuk menghasilkan nilai pertama, ia mulai menjalankan tubuh fungsi. Saat eksekusi mencapai pernyataan *yield*, iterator mengembalikan nilai dari ekspresi yang ada di dalamnya sebagai salah satu elemen urutan. Setelah itu, eksekusi fungsi ditangguhkan tepat setelah pernyataan *yield*.

Ketika iterator diminta untuk menghasilkan nilai berikutnya, eksekusi dilanjutkan dari titik di mana ia terhenti, dengan semua variabel dan pengikatan tetap seperti sebelumnya, seolah-olah eksekusi tidak pernah terputus. Fungsi melanjutkan komputasinya, mungkin menghasilkan lebih banyak nilai melalui *yield*. Iterator akan berhenti ketika tubuh fungsi selesai dijalankan, yang juga mengakhiri urutan nilai yang dihasilkan.

Mari kita [bandingkan fungsi generator](yield%20vs%20return.md) *fibs* dengan fungsi serupa yang mengembalikan semua elemen urutan sekaligus dalam bentuk tuple atau list. Berikut adalah versi yang menghasilkan tuple:

```python
def fibsTuple(n):
    result = ()
    a = 1
    b = 1
    for i in range(n):
        result += (a,)
        a, b = b, a + b
    return result
```

Perhatikan bahwa proses ini boros. Operasi *result += (a,)* sebenarnya berarti *result = result + (a,)*. Setiap kali loop berjalan, fungsi membuat tuple baru yang merupakan salinan *result* dengan satu nilai tambahan di akhir. Semua tuple kecuali yang terakhir tidak pernah digunakan lagi, sehingga ini adalah pemborosan sumber daya.

Sekarang, lihat versi yang menggunakan list:

```python
def fibsList(n):
    result = []
    a = 1
    b = 1
    for i in range(n):
        result.append(a)
        a, b = b, a + b
    return result
```

Versi ini biasanya lebih efisien karena ia memodifikasi *result* di tempat tanpa membuat struktur data baru setiap kali loop berjalan. Ketika *n* cukup besar, perbedaan efisiensi ini bisa sangat terasa.

Namun, terlepas dari soal efisiensi, baik *fibsTuple* maupun *fibsList* mengembalikan seluruh urutan sekaligus sebagai objek tunggal. Sebaliknya, *fibs* menghasilkan iterator yang menghasilkan nilai satu per satu secara dinamis. Kita bisa membayangkan perbedaan ini seperti cara kerja dorong-tarik: pada *fibsTuple* atau *fibsList*, kode pemanggil "mendorong" nilai *n* ke fungsi, dan fungsi "mendorong" kembali seluruh urutan. 

![](attachment/Pasted%20image%2020250504065325.png)

Pada *fibs*, pemanggil "mendorong" *n* ke fungsi, lalu "menarik" nilai-nilai dari iterator sesuai kebutuhan.

![](attachment/Pasted%20image%2020250504065343.png)

Kita juga pernah membahas fungsi *map* di Bagian 6.4:

```python
def map(f, sequence):
    result = ()
    for a in sequence:
        result += (f(a),)
    return result
```

Implementasi *map* ini mengembalikan tuple, mirip seperti *fibsTuple*, dan memiliki masalah efisiensi yang sama. (Apakah Anda menyadari masalah efisiensi ini saat kita pertama kali membahas definisi *map*?)

Seperti yang disebutkan di Bagian 6.4, Python sudah memiliki fungsi bawaan *map* yang sebenarnya adalah fungsi generator. Implementasinya lebih mirip seperti ini:

```python
def map(f, sequence):
    for a in sequence:
        yield f(a)
```

Kita bisa menggunakan definisi ini dalam program kita sebagai pengganti versi tuple. Selain lebih sederhana dan mudah dipahami, versi ini juga lebih efisien. Namun, sebenarnya tidak perlu mendefinisikan ulang *map*—kita bisa langsung menggunakan versi bawaan Python.

Sama seperti *map*, fungsi bawaan dan pustaka Python lainnya seperti *filter* yang bekerja dengan urutan sebenarnya adalah fungsi generator. Fungsi-fungsi ini menerima urutan statis atau aliran sebagai masukan dan menghasilkan aliran sebagai keluaran.

Fungsi generator tidak terbatas pada komputasi sederhana seperti contoh di atas. Mereka bisa menangani komputasi yang lebih kompleks dan bahkan memiliki beberapa pernyataan *yield* di tempat yang berbeda untuk menggabungkan hasil dari berbagai komputasi menjadi satu aliran. Berikut adalah contohnya.

Fungsi generator *combinations* (Contoh 7.1) menerima bilangan bulat non-negatif *n* dan sebuah urutan nilai unik, lalu menghasilkan semua kombinasi yang mungkin (dalam bentuk tuple) dari elemen urutan yang diambil sebanyak *n* elemen. Ada tiga kasus:
- Jika *n = 0*, hanya ada satu hasil: tuple kosong.
- Jika *n > 0* tetapi urutan kosong, tidak ada hasil. (Pernyataan *pass* di Python hanyalah penanda yang tidak melakukan apa-apa.)
- Jika tidak, fungsi secara rekursif menghasilkan dua jenis kombinasi: kombinasi tanpa elemen pertama urutan, dan kombinasi yang menyertakan elemen pertama.

**Contoh 7.1. Kombinasi dengan Fungsi Generator**

```python
def combinations(n, seq):
    if n == 0:
        yield ()
    elif len(seq) == 0:
        pass
    else:
        first = seq[0]
        rest = seq[1:]
        for a in combinations(n, rest):
            yield a
        for a in combinations(n-1, rest):
            yield (first,) + a
```

Perhatikan kode ini dengan saksama untuk memahami cara kerjanya, terutama pada kasus rekursif. Pastikan Anda melihat mengapa kode ini menghasilkan kombinasi yang benar. Perhatikan bahwa setiap panggilan rekursif mendekati kasus dasar, baik karena *n* semakin kecil atau karena urutan *seq* semakin pendek.

Komputasi ini adalah contoh yang bagus untuk menunjukkan bahwa rekursi sering kali lebih mudah daripada iterasi untuk masalah tertentu. Cobalah menulis solusi menggunakan iterasi saja, dan Anda akan melihat tantangannya.

### 7.3. Aliran Tanpa Akhir

Dengan fungsi generator, kita bisa dengan mudah membuat aliran yang tidak pernah berakhir. Contoh sederhananya adalah fungsi *endlessstream*, yang menerima nilai apa pun dan menghasilkan aliran berulang tanpa henti dari nilai tersebut:

```python
def endlessstream(x):
    while True:
        yield x
```

Contoh lain adalah fungsi *integers*, yang menghasilkan bilangan bulat berurutan mulai dari nilai awal tertentu:

```python
def integers(n):
    while True:
        yield n
        n += 1
```

Aliran ini bisa berlangsung selamanya—atau setidaknya hingga nilai *n* terlalu besar untuk disimpan Python. Untuk keperluan praktis, kita anggap aliran ini "tanpa akhir".

Kami menggunakan istilah "tanpa akhir" (*endless*) alih-alih "tak terbatas" (*infinite*) untuk menghindari kesan bahwa kita berurusan dengan objek berukuran tak terbatas. Dalam komputasi seperti yang kita kenal, itu tidak mungkin. Aliran tanpa akhir dalam Python hanyalah urutan yang bisa kita ambil elemennya tanpa batas waktu.

Jelas bahwa *endlessstream* menghasilkan aliran tanpa akhir. Namun, secara umum, tidak selalu mudah menentukan apakah aliran dari sebuah fungsi generator akan berakhir atau tidak hanya dengan melihat kodenya.

Kadang-kadang, apakah aliran berakhir atau tidak tergantung pada faktor eksternal. Misalnya, berikut adalah fungsi generator yang menghasilkan baris dari masukan program, mungkin dari seseorang yang mengetik di keyboard. Fungsi bawaan *input* mengembalikan baris berikutnya tanpa karakter "baris baru". Jika pengguna memasukkan baris kosong, aliran berhenti.

```python
def inputLines():
    while True:
        line = input()
        if line == "":
            return  # aliran berhenti
        else:
            yield line
```

Kita tidak bisa memprediksi dari kode ini saja apakah aliran akan berakhir. Itu sepenuhnya bergantung pada pengguna, bukan pada program.

Bahkan ketika terminasi sepenuhnya ditentukan oleh program, menentukan apakah aliran akan berakhir bisa jadi sulit, bahkan tidak mungkin. Contoh sederhananya adalah algoritma Collatz, yang diusulkan oleh seorang matematikawan bernama Collatz. Algoritma ini dimulai dengan bilangan bulat positif *n* dan melakukan langkah berikut secara berulang:
- Jika *n* genap, bagi dengan 2.
- Jika *n* ganjil, kalikan dengan 3 dan tambahkan 1.
- Berhenti jika *n* mencapai 1.

Berikut adalah fungsi generator Python yang mengimplementasikan algoritma Collatz, menghasilkan aliran nilai yang diambil *n* dari nilai awal tertentu:

```python
def Collatz(n):
    yield n
    while n != 1:
        if n % 2 == 0:
            n = n // 2
        else:
            n = 3 * n + 1
        yield n
```

Misalnya, jika *n* adalah 3, aliran yang dihasilkan adalah 3, 10, 5, 16, 8, 4, 2, 1.

Menariknya, hingga buku ini ditulis pada tahun 2014, masih belum ada bukti matematis bahwa algoritma Collatz akan selalu berhenti untuk setiap nilai awal *n*. Urutan ini berhenti untuk setiap *n* yang pernah dicoba, tetapi belum ada yang bisa membuktikan bahwa ini berlaku untuk semua *n*.

Pertanyaan tentang terminasi komputasi adalah topik penting dalam teori ilmu komputer, yang mungkin akan Anda pelajari lebih lanjut jika Anda menekuni bidang ini. Untuk saat ini, cukup katakan bahwa menentukan apakah sebuah algoritma akan selalu berhenti bisa sangat sulit, bahkan tidak mungkin, hanya dari deskripsi algoritmanya. Ini salah satu alasan mengapa pemrograman bisa begitu menantang.

### 7.4. Menggabungkan Aliran

Meskipun aliran dihasilkan secara dinamis dan bisa tanpa akhir, dalam banyak hal mereka berperilaku seperti urutan lainnya. Mari kita fokus pada bagaimana aliran bekerja ketika digabungkan (*concatenation*).

Kita definisikan penggabungan dua aliran, *X* dan *Y*, sebagai aliran baru yang dihasilkan dengan cara yang sederhana: pertama menghasilkan semua elemen *X*, lalu semua elemen *Y*.

Berikut adalah fungsi generator Python yang mengimplementasikan ide ini:

```python
def concat(X, Y):
    for a in X:
        yield a
    for b in Y:
        yield b
```

Perhatikan bahwa fungsi *concat* ini fleksibel; ia bisa bekerja dengan segala jenis urutan yang bisa diiterasi oleh pernyataan *for*, seperti string, tuple, list, objek *range*, atau iterator. Fungsi ini bisa menggabungkan dua aliran, dua urutan statis, atau kombinasi keduanya. Namun, setiap loop *for* dalam fungsi ini sebenarnya menggunakan iterator untuk mengiterasi *X* atau *Y*, jadi pada dasarnya *concat* selalu menggabungkan dua aliran. Dan hasilnya selalu berupa aliran, bukan urutan statis.

Apa yang terjadi jika *A* adalah aliran tanpa akhir? Hasil dari *concat(A, B)* tetap terdefinisi dengan baik; hanya saja elemen *B* tidak pernah tercapai karena *A* tidak pernah selesai. Dengan kata lain, *concat(A, B)* sama dengan *A*—keduanya menghasilkan aliran yang sama.

Lalu, apakah operasi penggabungan ini asosiatif? Ya, tentu saja. Kita bisa menunjukkan bahwa *concat(A, concat(B, C)) = concat(concat(A, B), C)* untuk setiap aliran *A*, *B*, dan *C*, baik yang terbatas maupun tanpa akhir. Mari kita lihat alasannya.

Jika *A*, *B*, dan *C* semuanya adalah aliran terbatas, maka *concat(A, concat(B, C))* menghasilkan elemen *A* diikuti oleh (elemen *B* diikuti oleh elemen *C*). Di sisi lain, *concat(concat(A, B), C)* menghasilkan (elemen *A* diikuti oleh elemen *B*) diikuti oleh elemen *C*. Karena penggabungan urutan terbatas bersifat asosiatif, kedua ekspresi ini menghasilkan urutan yang sama.

Jika *A* adalah aliran tanpa akhir, maka *concat(A, concat(B, C))* hanya menghasilkan elemen *A* tanpa pernah mencapai *B* atau *C*. Demikian pula, *concat(concat(A, B), C)* sama dengan *concat(A, C)*, yang juga hanya menghasilkan *A*. Kita bisa memeriksa kasus lain—misalnya, ketika *B* tanpa akhir tetapi *A* terbatas—dan hasilnya tetap sama: operasi ini asosiatif.

Cara lain untuk memahami asosiativitas *concat* adalah dengan melihat kodenya. Ketika kita menulis:

```python
for e in E:
    yield e
```

Ini sebenarnya setara dengan kode di dalam tubuh fungsi generator *E*, dengan argumen yang sesuai disubstitusikan. Dengan kata lain, pernyataan *for* hanya meneruskan nilai yang dihasilkan oleh *E*. Jadi, *concat(A, concat(B, C))* setara dengan:

```python
for a in A:
    yield a
for b in B:  # ini adalah bagian dari concat(B, C)
    yield b
for c in C:
    yield c
```

Dan *concat(concat(A, B), C)* setara dengan:

```python
for a in A:  # ini adalah bagian dari concat(A, B)
    yield a
for b in B:
    yield b
for c in C:
    yield c
```

Kedua segmen kode ini jelas identik dan menghasilkan urutan yang sama. Jadi, *concat* memang asosiatif.

Selain itu, *concat* memiliki elemen identitas: aliran kosong. Jika *X* adalah aliran kosong, loop pertama dalam *concat(X, Y)* selesai tanpa menghasilkan apa-apa, dan loop kedua menghasilkan semua elemen *Y*. Jadi, *concat(X, Y)* sama dengan *Y*. Sebaliknya, jika *Y* kosong, *concat(X, Y)* sama dengan *X*.

Aliran kosong ini bisa dihasilkan oleh berbagai objek—string kosong, tuple kosong, atau fungsi generator yang selesai tanpa *yield*—tetapi di Python, semua aliran kosong ini dianggap sama. Kesimpulannya, aliran membentuk struktur matematis yang disebut *monoid* di bawah operasi *concat*, dengan aliran kosong sebagai identitas. Sekarang, Anda mungkin sudah tidak terkejut lagi menemukan *monoid* lain dalam pemrograman!

### 7.5. Pemrograman dengan Aliran

Seperti halnya pemrograman fungsional, pemrograman dengan aliran membuka berbagai teknik baru yang bisa Anda tambahkan ke keahlian Anda. Di bagian ini, kita akan menjelajahi beberapa di antaranya.

Ketika Anda perlu menghasilkan urutan nilai untuk diiterasi oleh komputasi lain, pertimbangkan untuk menggunakan aliran. Anda bisa mengemas komputasi tersebut ke dalam fungsi generator.

Misalnya, fungsi generator sangat berguna untuk mengambil nilai dari sebuah objek yang terstruktur berbeda dari yang kita inginkan. Katakanlah kita ingin memproses setiap karakter dalam sebuah file. Di Python, file adalah urutan baris, dan setiap baris adalah urutan karakter. Namun, yang kita inginkan adalah urutan karakter secara langsung, bukan baris.

Berikut adalah fungsi generator yang menghasilkan aliran karakter dari sebuah file:

```python
def chars(file):
    for line in file:
        for char in line:
            yield char
```

Kita bisa menggunakan fungsi ini dalam komputasi utama seperti ini:

```python
f = open(nama_file)
for char in chars(f):
    # lakukan komputasi dengan char
```

Contoh yang sedikit lebih kompleks: misalkan kita memiliki file teks dan ingin menghasilkan urutan semua kata di dalamnya. Struktur ini berbeda dari struktur asli file, yang terdiri dari baris-baris teks.

Kita bisa menggunakan metode *split* untuk memisahkan setiap baris menjadi kata-kata. Ketika *split* dipanggil tanpa argumen, ia memisahkan string berdasarkan "spasi kosong" (seperti spasi, karakter baris baru, atau tab). Ini adalah cara standar untuk memecah teks menjadi kata-kata.

Selain itu, katakanlah kita ingin kata-kata ini bersih dari tanda baca, seperti koma atau tanda kutip, yang mungkin ada di awal atau akhir kata. Python menyediakan metode *strip* untuk ini. Jika *punctuation* adalah string berisi karakter tanda baca, maka *word.strip(punctuation)* akan menghapus semua karakter tersebut dari awal dan akhir *word*. (Catatan: dokumentasi Python menyebutkan bahwa *strip* memperlakukan karakter dalam *punctuation* sebagai sebuah set.)

Ada satu masalah lagi: jika ada spasi kosong di awal atau akhir baris, *split* bisa menghasilkan string kosong, yang tidak kita inginkan. Untungnya, *strip* juga bisa digunakan tanpa argumen untuk menghapus spasi kosong, termasuk karakter baris baru yang selalu ada di akhir baris.

Berikut adalah fungsi generator yang menghasilkan aliran kata dari sebuah file, lengkap dengan operasi pembukaan file:

```python
def words(fileName):
    punctuation = ",.;?!" + '"' + "'"
    f = open(fileName)
    for line in f:
        for word in line.strip().split():
            yield word.strip(punctuation)
```

Sekarang, mari kita lihat contoh lain. Berikut adalah fungsi generator yang menghasilkan baris dari masukan pengguna:

```python
def inputLines():
    while True:
        line = input()
        if line == "":
            return  # aliran berhenti
        else:
            yield line
```

Fungsi ini menghasilkan baris pada waktu yang tidak bisa diprediksi oleh program, terutama jika masukan berasal dari seseorang yang mengetik di keyboard.

Misalkan kita ingin mencatat waktu setiap baris dimasukkan, selain menyimpan baris itu sendiri. Kita membutuhkan cara untuk mendapatkan waktu saat ini dari dalam program. Pustaka Python menyediakan berbagai fungsi untuk menangani waktu, tetapi untuk contoh ini, anggap saja kita punya fungsi *time()* yang mengembalikan waktu saat ini dalam format yang sesuai dan cukup akurat.

Berikut adalah fungsi generator yang menghasilkan aliran tuple, masing-masing berisi waktu saat baris dimasukkan dan baris itu sendiri:

```python
def timedInputLines():
    for line in inputLines():
        t = time()
        yield (t, line)
```

Kode ini sederhana, tetapi yang menarik adalah bagaimana waktu berperan. Kode yang menggunakan *timedInputLines* akan memanggil fungsi ini untuk mendapatkan iterator, lalu "menarik" nilai dari iterator sesuai kebutuhan. Setiap kali nilai diminta, *timedInputLines* harus menunggu hingga tubuh loop *for*-nya dijalankan lagi. Ini memaksa *inputLines* untuk meminta baris baru dari pengguna. Jika pengguna belum mengetik apa-apa, semua kode ini akan menunggu.

Begitu pengguna memasukkan baris (dan baris itu tidak kosong), *inputLines* segera menghasilkan baris tersebut. Ini memungkinkan *timedInputLines* untuk melanjutkan, mengambil waktu saat ini (*t*), dan menghasilkan tuple (*t, line*) kembali ke kode pemanggil.

Kita juga bisa bekerja dengan beberapa aliran sekaligus. Salah satu contohnya adalah fungsi bawaan Python *zip*, yang mengambil dua urutan (statis atau dinamis) *X* dan *Y* dan menghasilkan aliran pasangan dalam bentuk tuple dua elemen. Misalnya, *zip((1, 2, 3), ("a", "b", "c"))* menghasilkan aliran *(1, "a"), (2, "b"), (3, "c")*.

Aliran dari *zip* berhenti ketika salah satu urutan (*X* atau *Y*) selesai. Ini berarti *zip* tetap berfungsi meskipun salah satu urutan tanpa akhir, selama urutan lainnya terbatas. Kita bisa memanfaatkan ini untuk keperluan menarik, seperti menomori elemen urutan dengan menggabungkannya dengan aliran dari *integers*. Jika *y* adalah *("a", "b", "c", "d")*, maka *zip(integers(1), y)* menghasilkan *(1, "a"), (2, "b"), (3, "c"), (4, "d")*.

Mari kita terapkan teknik ini. Ingat contoh di Bagian 1.2 yang memproses file pengamatan suhu. Misalkan kita perlu menemukan semua nilai dalam file *observations* yang melebihi batas tertentu (*threshold*), dan kita ingin setiap nilai dipasangkan dengan nomor baris tempat nilai itu ditemukan. Kita bisa melakukannya dengan kode biasa menggunakan *for* dan *if*, tetapi mari coba pendekatan fungsional dengan aliran.

Seperti yang kita tahu, *map(int, open("observations"))* mengubah aliran baris dari file menjadi aliran bilangan bulat. Kita bisa meng-zip aliran ini dengan aliran dari *integers(1)* untuk memasangkan setiap pengamatan dengan nomor barisnya, lalu menyaring pasangan yang memenuhi syarat. Berikut adalah kode lengkapnya dalam satu ekspresi:

```python
filter(lambda a: a[1] > threshold,
       zip(integers(1),
           map(int, open("observations"))))
```

Bayangkan aliran dalam ekspresi ini seperti pipa yang mengalirkan nilai dari satu fungsi ke fungsi berikutnya.

![](attachment/Pasted%20image%2020250504065515.png)

Sekarang, bagaimana jika kita ingin membuat fungsi *zip* sendiri? Versi bawaan Python bisa menangani banyak urutan, tetapi untuk kesederhanaan, kita akan buat versi untuk dua urutan saja. Kita ingin *zip(X, Y)* mengiterasi *X* dan *Y* bersamaan, menghasilkan pasangan elemen pertama, kedua, dan seterusnya.

Tantangannya adalah Python tidak punya cara langsung untuk mengiterasi dua urutan secara bersamaan. Jika *X* dan *Y* adalah urutan statis, kita bisa menggunakan pengindeksan (*X[i]*, *Y[i]*), tetapi ini tidak berlaku untuk aliran.

Untungnya, Python menyediakan fungsi *next* untuk mengambil elemen berurutan dari iterator:

```python
next(iterator, endMarker)
```

Di sini, *iterator* adalah iterator yang menghasilkan elemen urutan, dan *endMarker* adalah nilai khusus (biasanya *None*) yang menandakan akhir urutan. Untuk membuat iterator, kita gunakan fungsi *iter*, yang mengonversi urutan atau aliran menjadi iterator. Jika *X* sudah iterator, *iter(X)* sama dengan *X*, tetapi untuk amannya, kita selalu gunakan *iter*.

Berikut adalah cara menulis *zip* untuk dua urutan, dengan asumsi *None* bukan nilai dalam *Y*:

```python
def zip(X, Y):
    it = iter(Y)
    for x in X:
        y = next(it, None)
        if y is None:
            return
        else:
            yield (x, y)
```

Fungsi ini berhenti ketika *X* atau *Y* selesai, mana yang lebih dulu. Jika keduanya tanpa akhir, hasilnya juga tanpa akhir.

Seperti kita bisa mengubah urutan statis menjadi aliran dengan *iter*, kita juga bisa mengubah aliran menjadi urutan statis dengan *tuple* atau *list*. Proses ini, yang disebut *mematerialisasi* aliran, memaksa aliran menghasilkan semua nilainya sekaligus untuk disimpan dalam struktur statis.

Mengapa kita perlu mematerialisasi aliran? Mungkin untuk melakukan operasi yang hanya bisa dilakukan pada urutan statis, seperti pengindeksan atau modifikasi elemen di tempat (pada list). Kita juga mungkin perlu mematerialisasi aliran jika ingin mengiterasinya lebih dari sekali.

Namun, kita harus berhati-hati dengan aliran tanpa akhir. Misalnya, *list(integers(0))* tidak akan pernah selesai karena *integers(0)* menghasilkan aliran tanpa akhir. Demikian juga, *tuple(inputLines())* akan menunggu selamanya kecuali pengguna memasukkan baris kosong.

Jika kita tahu berapa banyak elemen yang dibutuhkan dari aliran tanpa akhir, kita bisa mematerialisasi hanya sejumlah itu. Misalnya, untuk *n* elemen pertama, kita bisa membuat aliran terbatas dan mengubahnya menjadi tuple atau list (lihat Latihan 2 di akhir bab).

Dalam banyak kasus, kita tidak perlu mematerialisasi aliran sama sekali. Komputasi bisa langsung mengiterasi aliran dan mengontrol berapa banyak elemen yang digunakan, seperti pada definisi *zip* kita.

Bahkan, kadang-kadang membuat aliran tanpa akhir justru menghasilkan kode yang lebih sederhana. Kode yang menggunakan aliran bisa menentukan sendiri berapa banyak elemen yang diambil. Contohnya, untuk menomori elemen aliran *S* mulai dari 0, kita bisa menulis:

```python
zip(integers(0), S)
```

Alternatifnya, jika kita ingin menghindari aliran tanpa akhir, kita bisa menggunakan *range*, tetapi ini memerlukan panjang *S* diketahui terlebih dahulu, yang berarti mematerialisasi *S*:

```python
zip(range(len(tuple(S))), S)
```

Kode ini lebih rumit, kurang efisien, dan tidak akan berfungsi jika *S* tidak bisa dimaterialisasi.

### 7.6. Pemrosesan Terdistribusi

Seperti yang kita bahas di Bagian 6.6, pemrosesan paralel semakin umum di sistem komputer modern. Namun, ada bentuk lain yang sudah lama menjadi bagian dari kehidupan kita: pemrosesan terdistribusi. Dalam model ini, komputer-komputer yang terpisah berkomunikasi dan bekerja sama untuk menjalankan komputasi yang lebih besar. Kita menggunakan pemrosesan terdistribusi setiap kali berinteraksi dengan Internet atau Web, yang berfungsi seperti satu komputer raksasa dengan jutaan prosesor. Aplikasi seperti pencarian web atau permainan multipemain sering kali adalah komputasi tunggal yang didistribusikan ke seluruh dunia.

Pemrosesan terdistribusi sering digambarkan sebagai "pengiriman pesan": misalnya, komputer A mengirim permintaan data ke komputer B, dan komputer B membalas dengan data. Namun, banyak komunikasi dalam sistem ini sebenarnya berbasis aliran, bukan pesan tunggal. Misalnya, komputer B mungkin adalah server yang menerima aliran permintaan dan memprosesnya satu per satu, seperti contoh-contoh dalam bab ini. Atau, data yang dikembalikan mungkin dipecah menjadi aliran "paket", yang diiterasi oleh komputer A. Beberapa aliran, seperti streaming audio, video, atau umpan RSS, bahkan bisa tanpa akhir.

Pemrosesan terdistribusi sering digunakan karena data berada di lokasi berbeda dari tempat ia dibutuhkan. Alasan lain adalah untuk memanfaatkan daya komputasi banyak komputer untuk satu masalah.

Namun, tidak semua komputasi cocok untuk didistribusikan. Mentransfer data antar komputer melalui jaringan jauh lebih lambat dibandingkan komputasi di satu komputer. Jadi, jika setiap komputer hanya melakukan sedikit komputasi pada data besar yang dikirim, distribusi justru bisa memperlambat proses.

Distribusi lebih masuk akal jika setiap komputer sudah memiliki datanya sendiri. Misalnya, bayangkan kita perlu memproses file atau halaman web yang tersebar di banyak komputer. Setiap komputer bisa mencari dan mengumpulkan data lokalnya menggunakan operasi seperti *map*, *filter*, atau *reduce*, lalu mengirimkan hasil yang relatif kecil ke komputer pusat untuk digabungkan. Alternatifnya, penggabungan bisa dilakukan bertahap, seperti reduksi yang kita bahas di Bagian 6.6, dengan beberapa komputer bertindak sebagai pengumpul sementara sebelum hasil akhir digabungkan.

Penalaran matematis bisa membantu merancang sistem terdistribusi yang efisien. Jika operasi penggabungan bersifat asosiatif, kita bisa mendistribusikan tugas dengan lebih fleksibel dan mengerjakannya secara paralel. Jika operasi juga komutatif, komputer pengumpul bisa memproses hasil dalam urutan apa pun, yang sangat berguna ketika data tiba secara acak.

**Istilah Baru dalam Bab Ini**
- *stream* (aliran)
- *generator expression* (ekspresi generator)
- *generator function* (fungsi generator)
- *yield-statement* (pernyataan yield)
- *materialize* (mematerialisasi)
- *distributed processing* (pemrosesan terdistribusi)

**Latihan**
1. Cobalah bereksperimen dengan fungsi *fibs*, *fibsTuple*, dan *fibsList* dari Bagian 7.2. Temukan nilai *n* di mana *fibsTuple(n)* terasa lebih lambat dibandingkan *fibs(n)*, atau sebaliknya. Ulangi perbandingan antara *fibsList* dan *fibs*. Jika sistem Anda memungkinkan pengukuran waktu eksekusi program Python, gunakan alat itu; jika tidak, jalankan secara interaktif dan amati perbedaannya.

2. Tulis fungsi generator *prefix(n, stream)* yang menghasilkan *n* elemen pertama dari sebuah aliran, atau seluruh aliran jika panjangnya kurang dari *n*. Fungsi ini harus berfungsi untuk aliran tanpa akhir maupun terbatas, jadi mematerialisasi aliran bukanlah solusi. Perhatikan bahwa aliran yang dihasilkan *prefix* selalu terbatas dan bisa dimaterialisasi jika diperlukan.

3. Tinjau kembali fungsi *integers* dari Bagian 7.3. Apakah kita benar-benar bisa menyebut aliran yang dihasilkannya "tanpa akhir"? Pikirkan kembali jawaban Anda untuk dua latihan pertama di Bab 2.

4. Apa hasil dari ekspresi berikut? Jelaskan jawaban Anda dengan tepat, misalnya dengan membedakan aliran dan urutan lainnya. Tulis kode untuk menguji jawaban Anda. Asumsikan *map* adalah fungsi bawaan, *double* didefinisikan seperti di Bagian 4.3, dan *integers* seperti di Bagian 7.3.
   - a. *map(double, range(5))*
   - b. *map(double, integers(0))*
   - c. *map(integers, integers(0))*

5. Pada contoh *timedInputLines* di Bagian 7.5, kita mengasumsikan kode akan menunggu setiap baris masukan dari pengguna. Bagaimana jika masukan datang lebih cepat, misalnya dari program lain, bukan dari keyboard? Bagaimana perilaku *timedInputLines* dalam kasus ini?

6. Kembali ke skrip pengaveragan suhu di Bagian 1.2. Misalkan kita punya banyak stasiun cuaca di lokasi berbeda, masing-masing mengukur suhu sendiri. Bisakah kita mendistribusikan proses pengaveragan ke komputer di stasiun-stasiun tersebut, lalu mengirim hasilnya ke komputer pusat untuk menghitung rata-rata akhir?

[back](./)
