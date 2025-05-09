[Home](../)

[back](./)

## Bab 8: Himpunan

### 8.1. Himpunan dalam Matematika

Konsep himpunan pertama kali kita bahas di Bagian 1.3. Pada bab ini, kita akan menyelami himpunan secara lebih mendalam. Teori himpunan merupakan pilar utama dalam matematika tingkat lanjut, bahkan menjadi fondasi untuk mendefinisikan matematika itu sendiri. Ketika diterapkan secara formal, teori himpunan bisa menjadi topik yang abstrak dan menantang. Namun, di sini kita akan menjelaskan himpunan dengan cara yang lebih santai, berfokus pada konsep-konsep yang praktis dan relevan untuk pemrograman. Pada bagian ini, kita akan memperkenalkan definisi-definisi penting secara singkat dan tidak terlalu formal, disertai dengan beberapa fakta menarik dan berguna tentang himpunan.

Secara sederhana, himpunan adalah kumpulan benda-benda yang berbeda dan tidak terurut, yang kita sebut sebagai anggota himpunan. Benda-benda ini bisa berupa apa saja yang relevan dalam konteks tertentu—misalnya, angka, nama, orang, atau kota. Sebagai contoh, Anda bisa mendefinisikan satu himpunan yang berisi semua anggota keluarga Anda, dan himpunan lain yang berisi semua angka ganjil di bawah 100.

Dalam sebuah pembahasan tentang himpunan, kita bisa secara eksplisit menentukan *alam semesta wacana (universe of discourse)*, yaitu kumpulan semua benda atau elemen yang mungkin menjadi anggota himpunan yang sedang dibahas. Himpunan yang mencakup semua elemen ini disebut *himpunan universal (universal set)*. Namun, dalam beberapa kasus, kita membiarkan alam semesta wacana ditentukan secara implisit berdasarkan apa yang kita bicarakan, tanpa perlu mendefinisikan himpunan universal secara eksplisit.

Dalam matematika, alam semesta wacana sering kali mencakup himpunan itu sendiri, pasangan terurut (*tuple*), atau objek matematis kompleks lainnya. Dengan demikian, sebuah himpunan bisa berisi himpunan lain, pasangan terurut, dan sebagainya.

Sebuah himpunan ditentukan oleh anggotanya. Dua himpunan dianggap sama jika mereka memiliki anggota yang persis sama. Ada beberapa cara untuk mendefinisikan himpunan, di antaranya:
1. **Mencantumkan anggota secara eksplisit**. Untuk menunjukkan bahwa suatu kumpulan adalah himpunan, kita menggunakan tanda kurung kurawal. Misalnya, himpunan yang berisi angka 1, 3, dan 5 ditulis sebagai: ` {1, 3, 5}`

2. **Menyebutkan sifat yang dimiliki anggota**. Contohnya, “himpunan semua angka ganjil positif di bawah 100”. Kita bisa menuliskan ini sebagai: `{ n │ 0 < n < 100 and n is odd }`

   Di sini, tanda “|” dibaca sebagai “sehingga”. Sifat ini memilih anggota dari himpunan dasar yang lebih besar. Himpunan dasar ini bisa disebutkan secara eksplisit, misalnya: `{ n │ n is an integer and 0 < n < 100 and n is odd }`
   
   Atau, himpunan dasar bisa dibiarkan implisit, ditentukan oleh konteks atau dianggap sebagai himpunan universal.

3. **Menggunakan operasi himpunan**. Kita bisa membentuk himpunan baru dari himpunan lain dengan operasi seperti gabungan, irisan, atau selisih, yang akan dijelaskan lebih lanjut di bawah.

Ada juga himpunan khusus yang tidak memiliki anggota sama sekali, yang disebut *himpunan kosong*, ditulis sebagai $$\varnothing$$ atau kadang-kadang `{}`.

Jika elemen $$a$$ termasuk dalam himpunan $$S$$, kita tulis $$a \in S$$. Jika tidak, kita tulis $$a \notin S$$. Contohnya, $$1 \in \{0, 1, 2\}$$ dan $$1 \notin \{2, 4, 6, 8\}$$.

Jika setiap anggota himpunan $$A$$ juga merupakan anggota himpunan $$B$$, kita katakan bahwa $$A$$ adalah *himpunan bagian (subset)* dari $$B$$, ditulis $$A \subseteq B$$. Misalnya, $$\{2, 4\} \subseteq \{1, 2, 3, 4, 5\}$$. Menariknya, menurut definisi ini, $$\{2, 4\} \subseteq \{2, 4\}$$ juga benar—artinya, setiap himpunan adalah himpunan bagian dari dirinya sendiri. Jika kita ingin menegaskan bahwa $$A \subseteq B$$ tetapi $$A \neq B$$, kita gunakan istilah *himpunan bagian sejati (proper subset)*, ditulis $$A \subset B$$.

*Gabungan* dua himpunan A dan B, ditulis $$A \cup B$$, adalah himpunan yang berisi semua elemen yang ada di A, di B, atau di keduanya. *Irisan* dua himpunan A dan B, ditulis $$A \cap B$$, adalah himpunan yang berisi elemen-elemen yang ada di kedua himpunan tersebut. *Selisih* himpunan $$A$$ dan $$B$$, ditulis $$A - B$$, adalah himpunan yang berisi elemen-elemen yang ada di $$A$$ tetapi tidak ada di $$B$$. Selisih ini kadang juga disebut *komplemen* $$B$$ terhadap $$A$$, ditulis $$A \backslash B$$. Contohnya, $$\{1, 2, 3, 4, 5\} - \{2, 4, 6\} = \{1, 3, 5\}$$.

Operasi gabungan dan irisan bersifat *asosiatif* $$A \cup (B \cup C) = (A \cup B) \cup C$$ dan $$A \cap (B \cap C) = (A \cap B) \cap C$$ serta *komutatif*. Sifat-sifat ini mudah dibuktikan, karena definisi gabungan dan irisan didasarkan pada operasi logika “atau” dan “dan”, yang juga bersifat asosiatif dan komutatif.

Himpunan kosong berperan sebagai elemen identitas untuk operasi gabungan, sehingga himpunan membentuk struktur matematis yang disebut *monoid* di bawah operasi gabungan, dengan himpunan kosong sebagai identitasnya. Jika ada himpunan universal, itu menjadi identitas untuk operasi irisan, dan himpunan membentuk monoid di bawah irisan. Tanpa himpunan universal, himpunan tetap membentuk *semigrup* di bawah irisan.

Dalam matematika, himpunan sering kali bersifat tak hingga, artinya memiliki jumlah anggota yang tak terbatas. Contohnya adalah himpunan semua bilangan bulat atau semua bilangan real, yang sering digunakan oleh matematikawan. Sebagian besar permasalahan menarik dalam teori himpunan berkaitan dengan himpunan tak hingga.

Matematikawan juga sering mendefinisikan himpunan berdasarkan sifat tertentu tanpa menjelaskan cara menemukan anggotanya. Misalnya, himpunan solusi dari persamaan seperti:

$$\{x \mid x^2 - 5x + 6 = 0\}$$

Bagi yang paham aljabar, menemukan anggota himpunan ini cukup mudah, tetapi definisinya sendiri tidak menyertakan metode tersebut. Contoh lain yang lebih kompleks adalah:

$$\{(a, b, c, n) \mid a, b, c \text{ adalah bilangan bulat positif}, n \text{ adalah bilangan bulat lebih besar dari } 2, \text{ dan } a^n + b^n = c^n\}$$

Menemukan anggota himpunan ini, jika ada, tidaklah mudah. Bahkan, hingga beberapa waktu lalu, tidak diketahui apakah himpunan ini kosong, terbatas, atau tak hingga. Namun, pada tahun 1995, matematikawan Andrew Wiles membuktikan bahwa persamaan ini tidak memiliki solusi dengan sifat tersebut, sehingga himpunan ini kosong. (Ini adalah bukti dari "Teorema Terakhir Fermat.")

Sebagai pemrogram, kita menghadapi batasan yang jelas dibandingkan matematikawan. Pertama, kita tidak bisa membuat himpunan tak hingga dalam program. Kedua, seperti yang disebutkan di Bagian 2.3, kita harus menghindari pembuatan himpunan yang terbatas tetapi terlalu besar untuk disimpan di komputer. Ketiga, untuk membuat himpunan dalam program, kita harus tahu cara membangunnya. Meski ada batasan ini, himpunan tetap sangat berguna dalam pemrograman, seperti yang akan kita lihat.

### 8.2. Himpunan (Sets) dalam Python

Sama seperti pasangan terurut (*tuple*) dan daftar (*list*), himpunan (sets) dalam Python adalah struktur data yang dapat menyimpan berbagai nilai Python. Dalam terminologi Python, struktur seperti ini disebut *container*. Python juga memiliki satu jenis *container* bawaan lainnya, yaitu *dictionary* (kamus), yang akan dibahas di Bagian 9.2.

Himpunan dalam Python, seperti urutan statis atau aliran (*stream*), adalah objek yang bisa diiterasi menggunakan pernyataan *for* untuk memproses setiap anggotanya. Objek seperti ini disebut *iterable* dalam istilah Python.

Kita bisa membuat himpunan menggunakan *set display*, yang mirip dengan *list display* tetapi menggunakan kurung kurawal `{}` alih-alih tanda kurung siku `[]`. Bentuk yang secara eksplisit mencantumkan anggota himpunan sama dengan notasi matematis, misalnya: `{1, 3, 5}`

Ada juga *set comprehension*, yang mirip dengan *list comprehension* tetapi menggunakan kurung kurawal. Contohnya, untuk membuat himpunan angka ganjil positif di bawah 100:

```python
{n for n in range(100) if n % 2 == 1}
```

Dengan *set comprehension*, kita mendefinisikan himpunan berdasarkan sifat anggotanya. Namun, dalam Python, kita tidak bisa hanya menyebutkan sifatnya; kita harus mulai dengan *iterable* lain (seperti *range(100)* dalam contoh ini) dan memilih elemen yang memenuhi sifat tersebut.

Kita juga bisa membuat himpunan dari koleksi nilai dengan fungsi konversi *set*, ditulis sebagai `set(A)`, di mana `A` adalah *iterable* apa pun. Sebagai kasus khusus, `set()` akan menghasilkan himpunan kosong. (Catatan: *iterable* juga bisa digunakan sebagai argumen untuk fungsi konversi *tuple* dan *list*.)

Python menyediakan padanan untuk semua operasi himpunan yang telah kita bahas. Berikut adalah tabelnya:

**Tabel 8.1. Operasi Himpunan**

| Operasi                                   | Notasi Matematis | Python   |
| ----------------------------------------- | ---------------- | -------- |
| Anggota dari (*is a member of*)           | $$\in$$            | `in`     |
| Bukan anggota dari (*is not a member of*) | $$\notin$$         | `not in` |
| Himpunan bagian (*subset*)                | $$\subseteq$$      | `<=`     |
| Himpunan bagian sejati (*proper subset*)  | $$\subset$$        | `<`      |
| Gabungan (*union*)                        | $$\cup$$           | \|       |
| Irisan (*intersection*)                   | $$\cap$$           | `&`      |
| Selisih (*difference*)                    | $$-$$              | `-`      |

Dalam Python, `not in` diperlakukan sebagai satu operator. Operator `|` (gabungan) dan `&` (irisan) mungkin tidak terlihat mirip dengan simbol matematisnya, tetapi Anda bisa mengaitkannya dengan kata “atau” dan “dan”, yang sesuai dengan definisi gabungan dan irisan.

Menariknya, kita tidak bisa menggunakan `{}` untuk menandakan himpunan kosong di Python, karena `{}` menunjukkan *dictionary* kosong. Ini adalah keputusan historis, karena Python memiliki *dictionary* sebelum memiliki himpunan. Untuk membuat himpunan kosong, kita harus menulis `set()`.

Python tidak mendukung pembuatan himpunan universal yang berisi semua nilai Python yang mungkin. Dalam banyak kasus pemrograman, alam semesta wacana (jika ada) biasanya terlalu besar atau tak hingga—misalnya, himpunan semua string atau semua bilangan bulat Python. Namun, jika anggota himpunan dalam konteks program Anda berasal dari himpunan terbatas yang kecil, Anda mungkin bisa menggunakannya sebagai himpunan universal.

Seperti daftar, himpunan Python bersifat *mutable* (dapat diubah). Mirip dengan metode *append* pada daftar, ada metode *add* untuk menyisipkan elemen ke himpunan. Contoh:

```python
setA = {2, 4}
setA.add(3)
```

Setelah kode ini dijalankan, `setA` akan berisi `{2, 3, 4}`. Jika 3 sudah ada di `setA`, perintah *add* tidak akan mengubah apa pun.

Python juga memiliki metode lain untuk himpunan, seperti `discard(x)`, yang menghapus elemen `x` dari himpunan (tanpa efek jika `x` tidak ada), dan fungsi *len*, yang mengembalikan jumlah elemen dalam himpunan (`len(A)`).

Sama seperti dalam matematika, himpunan Python tidak terurut. Ketika Anda mengiterasi himpunan, Anda akan mendapatkan semua anggotanya, tetapi urutannya tidak dijamin. Contoh:

```python
cities = {"London", "Paris", "Vienna", "Istanbul"}
for place in cities:
    print(place)
```

Hasilnya bisa berupa:

```
Paris
London
Istanbul
Vienna
```

atau urutan lain yang berbeda.

Himpunan Python dirancang untuk pengujian keanggotaan yang sangat efisien, yang penting karena operasi seperti `in`, `not in`, irisan, dan gabungan bergantung pada pengujian ini. Untuk irisan `A & B`, Python memeriksa setiap anggota $$A$$ untuk melihat apakah ada di $$B$$. Untuk gabungan `A | B`, Python menggabungkan anggota `A` dan menambahkan anggota `B` yang belum ada di `A`.

Efisiensi ini dicapai melalui teknik *hashing*. Secara sederhana, *hashing* menggunakan nilai objek untuk menghitung lokasinya dalam struktur data, sehingga pengujian keanggotaan menjadi jauh lebih cepat dibandingkan membandingkan nilai dengan setiap anggota himpunan. Namun, karena *hashing* bergantung pada nilai yang tetap, himpunan Python hanya bisa berisi objek yang *immutable* (tidak dapat diubah), seperti angka atau string, tetapi tidak daftar (*list*).

Sayangnya, himpunan Python juga tidak bisa berisi himpunan lain, karena himpunan bersifat *mutable*. Untuk mengatasi ini, Python menyediakan *frozenset*, yaitu himpunan yang *immutable*. Mirip seperti hubungan antara *list* dan *tuple*, *frozenset* berperilaku seperti himpunan tetapi tidak bisa diubah. Kita bisa membuat *frozenset* dengan fungsi *frozenset(A)*, di mana *A* adalah himpunan atau koleksi lain, atau *frozenset()* untuk *frozenset* kosong.

Dengan *frozenset*, kita bisa memasukkan himpunan ke dalam himpunan lain. Misalnya, dalam matematika, kombinasi dua angka dari `{0, 1, 2}` adalah:

$$\{\{0, 1\}, \{0, 2\}, \{1, 2\}\}$$

Dalam Python, kita harus menggunakan *frozenset* untuk himpunan dalamnya:

```python
{frozenset(c) for c in ((0, 1), (0, 2), (1, 2))}
```

### 8.3. Studi Kasus: Menemukan Mahasiswa untuk Pekerjaan

Mari kita jeda sejenak untuk sebuah studi kasus sederhana, menerapkan apa yang telah kita pelajari ke masalah pemrosesan data.

Bayangkan sebuah perusahaan ingin merekrut mahasiswa dari universitas untuk bekerja setelah mereka lulus. Perusahaan ini mencari mahasiswa tahun keempat yang mengambil jurusan ilmu komputer atau teknik elektro, dengan rata-rata nilai minimal B.

Kita juga asumsikan universitas menyediakan file data: file *cs* berisi nama mahasiswa ilmu komputer, *ee* berisi nama mahasiswa teknik elektro, *year4* berisi nama mahasiswa tahun keempat, dan *goodGrades* berisi nama mahasiswa dengan rata-rata nilai B atau lebih baik.

Kita akan mencari tahu cara menemukan nama mahasiswa yang memenuhi kriteria ini. Meski masalah ini terlihat sederhana, kita akan berusaha mencari solusi terbaik, mulai dari pendekatan pemula hingga solusi yang lebih elegan dengan memanfaatkan konsep yang telah kita pelajari.

Pemrogram pemula sering diajarkan struktur dasar program:
1. Baca semua masukan.
2. Lakukan perhitungan.
3. Tampilkan hasil.

Pendekatan ini mungkin terlalu sederhana untuk beberapa masalah, tetapi cukup cocok untuk kasus ini.

Untuk membaca masukan, seorang pemula mungkin menggunakan pendekatan kuno: membaca file baris demi baris dengan pernyataan *while*, memanggil *readline*, dan memeriksa string kosong (seperti contoh di Bagian 3.3).

**Wawasan #1**: Kita tidak perlu repot seperti itu. Menggunakan pernyataan *for* untuk membaca file jauh lebih mudah, dan pembaca buku ini pasti sudah tahu.

Jadi, kita bisa membaca baris dari file dan menyimpan nama-nama ke dalam struktur data. Struktur yang pertama muncul di pikiran mungkin adalah daftar, terutama bagi pemrogram yang terbiasa dengan bahasa yang kurang canggih dibandingkan Python. Kita bisa memulai dengan daftar kosong dan menambahkan nama satu per satu:

```python
names = []
for line in file:
    names.append(line.strip())
```

**Wawasan #2**: Kita bisa lebih efisien. Untuk tugas seperti ini, *list comprehension* adalah alat yang tepat. Kita bisa menulis:

```python
names = [line.strip() for line in file]
```

Kita bisa menerapkan pendekatan ini untuk setiap file:

```python
year4 = [line.strip() for line in open("year4")]
cs = [line.strip() for line in open("cs")]
ee = [line.strip() for line in open("ee")]
goodGrades = [line.strip() for line in open("goodGrades")]
```

**Wawasan #3**: Kode ini memiliki banyak pengulangan yang bisa disederhanakan dengan fungsi. Memisahkan logika umum ke dalam fungsi tidak hanya membuat kode lebih rapi, tetapi juga praktik yang baik. Dalam Python, ini mudah dilakukan dengan *comprehension*:

```python
def listofNames(filename):
    return [line.strip() for line in open(filename)]
year4 = listofNames("year4")
cs = listofNames("cs")
ee = listofNames("ee")
goodGrades = listofNames("goodGrades")
```

Setelah semua data tersimpan dalam struktur data, kita lanjut ke perhitungan utama. Kita perlu menemukan “mahasiswa tahun keempat yang mengambil jurusan ilmu komputer atau teknik elektro dan memiliki rata-rata nilai B atau lebih baik”. Berikut adalah cara sederhana untuk menerjemahkan ke Python:

```python
candidates = []
for student in year4:
    if (student in cs or student in ee) and student in goodGrades:
        candidates.append(student)
```

**Wawasan #4**: Kita bisa lebih efisien dengan himpunan. Operasi *in* jauh lebih cepat pada himpunan dibandingkan daftar. Kita perlu mengubah kode pembacaan file untuk menghasilkan himpunan, bukan daftar, tetapi perubahannya cukup jelas:

```python
candidates = set()
for student in year4:
    if (student in cs or student in ee) and student in goodGrades:
        candidates.add(student)
```

**Wawasan #5**: Kita bisa lebih ringkas lagi dengan *set comprehension*:

```python
candidates = {student for student in year4
              if (student in cs or student in ee) and student in goodGrades}
```

**Wawasan #6**: Bahkan ini masih bisa disederhanakan. Dengan data dalam bentuk himpunan, kita bisa langsung menggunakan operasi himpunan:

```python
candidates = year4 & (cs | ee) & goodGrades
```

Ekspresi ini mencerminkan kebutuhan kita dengan jelas dan efisien: menemukan mahasiswa tahun keempat yang mengambil jurusan ilmu komputer atau teknik elektro dan memiliki nilai B atau lebih baik. Dengan menambahkan pernyataan *for* sederhana untuk menampilkan hasil, kita mendapatkan program yang singkat dan elegan:

**Contoh 8.1. Mencari Kandidat Pekerjaan dengan Operasi Himpunan**

```python
def setofNames(fileName):
    return {line.strip() for line in open(fileName)}
year4 = setofNames("year4")
cs = setofNames("cs")
ee = setofNames("ee")
goodGrades = setofNames("goodGrades")
candidates = year4 & (cs | ee) & goodGrades
for student in candidates:
    print(student)
```

Coba bayangkan program yang akan kita miliki jika kita tetap menggunakan pendekatan pemula di setiap langkah—pasti jauh lebih panjang dan berbelit-belit!

### 8.4. File Datar, Himpunan, dan Pasangan Terurut

Kembali ke topik file datar yang kita bahas di Bagian 5.3, banyak file datar mewakili himpunan atau urutan nilai, sering kali berupa angka atau string. Dalam studi kasus sebelumnya atau Contoh 1.1, file-file berisi nama (satu per baris), yang secara konseptual adalah himpunan.

Biasanya, program yang memproses file seperti ini akan menggunakan semua data di dalamnya. Langkah pertama yang logis adalah memasukkan data ke dalam struktur data dalam program. Fungsi *setofNames* di bagian sebelumnya melakukan hal itu: menerima nama file dan mengembalikan himpunan nama-nama di dalamnya. Berikut adalah versi yang sedikit dimodifikasi:

```python
def setofValues(fileName):
    file = open(fileName)
    return {line.strip() for line in file}
```

Nama fungsi ini lebih umum, sehingga cocok untuk file yang berisi string apa pun, tidak hanya nama. Kami memisahkan perintah *open* untuk kejelasan, meskipun bisa juga dimasukkan langsung ke dalam *comprehension*. (Catatan: seperti semua contoh dalam buku ini, kami tidak menyertakan penanganan kesalahan jika file gagal dibuka.)

Fungsi ini menghasilkan himpunan, tetapi kita juga bisa membuat daftar:

```python
def listofValues(fileName):
    file = open(fileName)
    return [line.strip() for line in file]
```

atau aliran:

```python
def streamofValues(fileName):
    file = open(fileName)
    return (line.strip() for line in file)
```

atau pasangan terurut dengan mematerialisasi aliran:

```python
def tupleofValues(fileName):
    file = open(fileName)
    return tuple(line.strip() for line in file)
```

Nanti, di Bagian 9.5, kita akan membahas *multiset* dan cara menangani data file sebagai *multiset* alih-alih himpunan atau urutan.

Bagaimana jika file berisi baris yang terbagi menjadi beberapa bidang, seperti file CSV (nilai yang dipisahkan koma) yang kita lihat di Bagian 5.3? Untuk file seperti ini, struktur data yang logis adalah himpunan (atau urutan) pasangan terurut.

Kita bisa memisahkan baris menjadi bidang dengan metode *split*:

```python
line.split(",")
```

Mungkin terlihat seperti kita bisa membuat himpunan pasangan terurut dengan:

```python
{line.strip().split(",") for line in file}
```

Namun, ini tidak akan berhasil, karena *split* menghasilkan daftar, bukan pasangan terurut, dan himpunan Python tidak bisa berisi daftar (*mutable*). Solusinya adalah mengonversi hasil *split* menjadi pasangan terurut:

```python
{tuple(line.strip().split(",")) for line in file}
```

Berikut adalah fungsi untuk membaca file CSV dan menghasilkan himpunan pasangan terurut:

```python
def setofTuples(fileName):
    file = open(fileName)
    return {tuple(line.strip().split(",")) for line in file}
```

Kita juga bisa membuat versi untuk daftar, aliran, atau pasangan terurut dengan cara serupa (kami anggap fungsi seperti *listofTuples*, *streamofTuples*, dan *tupleofTuples* tersedia).

Setelah data tersimpan, kita bisa mengiterasinya dengan pernyataan *for*. Misalnya, jika file *directory* adalah CSV yang berisi nama, nomor telepon, dan email, kita bisa memprosesnya seperti ini:

```python
directory = setofTuples("directory")
for entry in directory:
    (name, phone, email) = entry
```

Kita juga bisa membongkar (*unpack*) pasangan terurut langsung di header *for*:

```python
directory = setofTuples("directory")
for (name, phone, email) in directory:
```

Kita bisa menggunakan teknik yang sama dalam *comprehension*. Misalnya, untuk membuat himpunan berisi hanya nama dan email:

```python
directory = setofTuples("directory")
emailDirectory = {(entry[0], entry[2]) for entry in directory}
```

Atau, dengan pembongkaran untuk kejelasan:

```python
directory = setofTuples("directory")
emailDirectory = {(name, email) for (name, phone, email) in directory}
```

Dengan *comprehension* yang menyertakan filter (*for ... in ... if ...*), kita bisa memilih data tertentu. Kembali ke studi kasus sebelumnya, misalkan kita tidak memiliki file *cs* dan *ee*, tetapi satu file *students* dengan format:

```
John Baez, math
Jude Collins, CS
Joan Denver, CS
Joan Denver, EE
Roberta Dylan, physics
...
```

Mahasiswa dengan lebih dari satu jurusan (seperti Joan Denver) akan muncul di beberapa baris. File ini mewakili relasi, bukan pemetaan, tetapi itu tidak masalah untuk kasus ini. Kita bisa membuat himpunan *cs* dan *ee*:

```python
students = setofTuples("students")
cs = {name for (name, major) in students if major == "CS"}
ee = {name for (name, major) in students if major == "EE"}
```

Kode ini mudah dibaca dan jelas. Kita bisa menyederhanakan lebih lanjut dengan membuat satu himpunan *csOrEE*:

```python
students = setofTuples("students")
csOrEE = {name for (name, major) in students if major == "CS" or major == "EE"}
```

Dengan ini, kita tidak perlu operasi gabungan di perhitungan utama:

```python
candidates = year4 & csOrEE & goodGrades
```

Perbaikan terakhir: karena kita hanya menggunakan *students* sekali, kita tidak perlu menjadikannya himpunan. Kita bisa membiarkannya sebagai aliran:

```python
def streamofTuples(fileName):
    return (line.strip().split(",") for line in open(fileName))
csOrEE = {name for (name, major) in streamofTuples("students")
          if major == "CS" or major == "EE"}
```

Berikut adalah program lengkapnya:

**Contoh 8.2. Kandidat Pekerjaan dengan File Masukan Berbeda**

```python
def setofNames(fileName):
    return {line.strip() for line in open(fileName)}
def streamofTuples(fileName):
    return (line.strip().split(",") for line in open(fileName))
year4 = setofNames("year4")
csOrEE = {name for (name, major) in streamofTuples("students")
          if major == "CS" or major == "EE"}
goodGrades = setofNames("goodGrades")
candidates = year4 & csOrEE & goodGrades
for student in candidates:
    print(student)
```

Program ini mudah diadaptasi untuk format file lain (lihat Latihan 3).

### 8.5. Representasi Alternatif untuk Himpunan

Meski Python memiliki himpunan bawaan dengan sintaks yang nyaman, kita tidak selalu harus menggunakan himpunan Python untuk setiap koleksi data yang secara konseptual adalah himpunan. Contohnya adalah file *students* di bagian sebelumnya. Secara konseptual, nama-nama di file itu adalah himpunan (tanpa urutan atau duplikat), tetapi dalam file diwakili sebagai urutan, dan dalam program sebagai aliran. Representasi ini sangat sesuai untuk kebutuhan kita.

Pilihan representasi himpunan tergantung pada operasi yang akan dilakukan. Jika kita hanya perlu mengiterasi elemen-elemennya (seperti pada file *students* atau Contoh 1.1 dan 1.2), urutan sudah cukup. Himpunan Python lebih cocok jika kita perlu menguji keanggotaan atau melakukan operasi seperti gabungan dan irisan, karena sintaksnya elegan dan implementasinya efisien.

Dalam bahasa tanpa himpunan bawaan, pemrogram mungkin perlu membuat struktur data sendiri untuk himpunan. Ilmuwan komputer telah mengembangkan berbagai struktur dan algoritma untuk ini, yang akan dipelajari lebih lanjut oleh mahasiswa ilmu komputer. Banyak bahasa juga menyediakan pustaka untuk himpunan, meski tidak sepraktis fitur Python.

Namun, menggunakan struktur data canggih tidak selalu diperlukan. Misalnya, jika kita membutuhkan himpunan dengan *n* elemen yang hanya perlu berbeda satu sama lain (tanpa operasi himpunan lain), kita bisa merepresentasikannya sebagai bilangan bulat dari 0 hingga *n-1*. Jika perlu iterasi, kita bisa menggunakan objek *range*. Jika tidak, kita mungkin tidak perlu merepresentasikan himpunan secara eksplisit sama sekali. Pendekatan ini sangat sederhana dan efisien.

**Istilah Baru dalam Bab Ini**
- Anggota
- Alam semesta wacana
- Himpunan universal
- Himpunan kosong
- Himpunan bagian
- Himpunan bagian sejati
- Gabungan
- Irisan
- Selisih
- *Container*
- *Iterable*
- *Set display*
- *Set comprehension*
- *Hashing*

**Latihan**
1. Tulis fungsi Python yang menerima himpunan nama file (tidak kosong) sebagai argumen. File-file ini berisi nama-nama orang, seperti dalam contoh di Bagian 8.2. Fungsi Anda harus mengembalikan himpunan nama yang ada di semua file. Misalnya, file-file ini bisa berupa daftar kehadiran mahasiswa di kelas pada hari yang berbeda, dan fungsi Anda akan menemukan mahasiswa dengan kehadiran sempurna. Tulis kode yang sesederhana dan seanggun mungkin.

2. Buat *set comprehension* yang menghasilkan himpunan faktor berbeda dari bilangan bulat *n* (bilangan yang membagi *n* secara merata, kecuali 1 dan *n*). Gunakan *comprehension* ini untuk membuat fungsi *isPrime(n)* yang mengembalikan *True* jika *n* prima dan *False* jika tidak. (Bilangan prima adalah bilangan tanpa faktor selain 1 dan dirinya sendiri.)
   - Bisakah Anda modifikasi *isPrime* untuk hanya menguji faktor prima? (Jika *n* punya faktor, pasti ada faktor prima. Juga, jika ada faktor, setidaknya satu di antaranya ≤ akar kuadrat *n*.)
   - Versi mana yang lebih efisien? Uji dengan mengukur waktu eksekusi keduanya.

3. Tulis ulang program dari Contoh 8.1 dan 8.2 dengan asumsi masukan berupa file CSV berikut:
   - *students*: setiap baris berisi nama, jurusan, dan tahun studi (bilangan bulat, 4 untuk tahun keempat).
   - *grades*: setiap baris berisi nama dan rata-rata nilai (angka desimal, skala 0.0–4.0, di mana 3.0 adalah B).
   Jika latihan ini terasa terlalu mudah setelah memahami Contoh 8.1 dan 8.2, mungkin itulah intinya!

4. Pikirkan situasi dalam program di mana Anda memerlukan himpunan *n* elemen yang hanya perlu berbeda, tanpa sifat lain (seperti di akhir Bagian 8.5). Berikan beberapa contoh.

[back](./)
