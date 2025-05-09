[Home](../)

[back](./)

## Bab 9: Pemetaan

### 9.1. Pemetaan dalam Matematika

Konsep pemetaan pertama kali kita sentuh di Bagian 1.3. Kali ini, kita akan menyelami pemetaan secara lebih mendalam. Seperti saat kita membahas himpunan, penjelasan tentang pemetaan di sini akan disampaikan secara santai, dengan fokus pada sifat-sifat pemetaan yang paling berguna bagi kita sebagai pemrogram.

Secara sederhana, pemetaan adalah kumpulan pasangan terurut di mana tidak ada dua pasangan yang memiliki elemen pertama yang sama. Dengan kata lain, pemetaan menghubungkan setiap elemen pertama dengan elemen kedua yang spesifik dalam pasangan tersebut. Dalam dunia matematika, “pemetaan” sering dianggap sinonim dengan “fungsi”. Kita bisa menggunakan notasi fungsi untuk mendefinisikan pemetaan. Misalnya, ketika kita bilang $$f(3) = 7$$, itu artinya pasangan terurut $$(3, 7)$$ ada dalam pemetaan $$f$$.

Sama seperti himpunan, ada banyak cara untuk mendefinisikan pemetaan. Salah satu cara yang paling lugas adalah dengan mencantumkan pasangan terurutnya secara eksplisit, seperti ini:

$$
\{(1, 1), (2, 2), (3, 6), (4, 24)\}
$$

Ada juga variasi notasi yang menggunakan tanda $$\mapsto$$ untuk menunjukkan bahwa elemen pertama “dipetakan” ke elemen kedua, seperti ini:

$$
\{1 \mapsto 1, 2 \mapsto 2, 3 \mapsto 6, 4 \mapsto 24\}
$$

Dalam notasi ini, setiap pasangan $$a \mapsto b$$ disebut *maplet*—istilah yang menggambarkan hubungan pemetaan dengan jelas.

Matematikawan punya banyak cara lain, baik formal maupun informal, untuk mendefinisikan pemetaan. Misalnya, jika kita ingin mendefinisikan $$f$$ sebagai fungsi faktorial, ada tiga cara yang umum digunakan:

1. $$f(n) = n!$$ untuk semua bilangan bulat positif $$n$$
2. $$f = \lambda n. n!$$ untuk semua bilangan bulat positif $$n$$
3. $$f = \{n \mapsto n! \text{ untuk semua bilangan bulat positif } n\}$$

Untuk setiap pemetaan $$f$$, kita bisa mendefinisikan *domain* (ditulis *dom $$f$$*) sebagai himpunan semua elemen pertama dari pasangan terurut dalam pemetaan tersebut. Sementara itu, *range (jangkauan)* (ditulis *ran $$f$$*) adalah himpunan semua elemen kedua.[^1] Menariknya, seperti dalam kasus fungsi faktorial, domain dan jangkauan sebuah pemetaan bisa berupa himpunan tak hingga.

Kadang-kadang, domain sebuah pemetaan sudah jelas dari konteks. Namun, ada kalanya kita harus menentukan domain secara eksplisit untuk menghindari kebingungan. Contohnya, ekspresi “$$\lambda x. x + 1$$”. Apakah ini mendefinisikan fungsi penerus untuk bilangan bulat non-negatif? Atau fungsi yang menambahkan 1 ke semua bilangan real? Atau mungkin sesuatu yang lain? Pilihan domain akan menentukan pasangan terurut mana yang termasuk dalam pemetaan, sehingga menghasilkan fungsi yang berbeda.

Baik dalam matematika maupun pemrograman, sebuah fungsi bisa memiliki lebih dari satu argumen. Dalam matematika, ada dua cara umum untuk membangun fungsi seperti ini. Cara pertama adalah mendefinisikan fungsi sebagai pemetaan dari tupel nilai ke satu nilai tunggal. Misalnya, fungsi yang menghitung hasil kali dua angka:

$$
p(x, y) = x y
$$

Fungsi ini bisa ditulis dengan notasi *maplet* sebagai:

$$
p = \{(x, y) \mapsto x y\}
$$

Dengan definisi ini, $$p(x, y)$$ adalah cara singkat untuk menulis $$p(\{x, y\})$$. Jadi, misalnya, $$p(2, 3) = 6$$, sesuai dengan yang kita harapkan.

Cara kedua adalah mendefinisikan fungsi sebagai rantai pemetaan, di mana setiap pemetaan menghubungkan satu argumen ke fungsi dari argumen yang tersisa. Untuk fungsi $$p$$ di atas, kita bisa menulisnya seperti ini:

$$
p = \{x \mapsto \{y \mapsto x y\}\}
$$

Fungsi yang didefinisikan dengan cara ini disebut *curried*, mengambil nama dari matematikawan Haskell Curry.[^2] Dalam definisi ini, $$p(x)$$ adalah fungsi yang mengalikan argumennya dengan $$x$$. Jadi, $$p(x, y)$$ sebenarnya adalah singkatan dari $$(p(x))(y)$$, dan sekali lagi, $$p(2, 3) = 6$$.

Keunggulan dari fungsi *curried* adalah bahwa $$p(x)$$ sendiri sudah memiliki makna yang berguna: ini seperti fungsi *multiplyBy* di Python yang kita bahas di Bagian 4.3, saat membicarakan aplikasi parsial. Secara umum, ketika sebuah fungsi didefinisikan dengan *currying*, aplikasi parsial dari argumennya (dari kiri ke kanan) otomatis terdefinisi.

Meskipun kita mendefinisikan pemetaan sebagai himpunan, operator himpunan standar seperti gabungan atau irisan biasanya kurang berguna untuk pemetaan. Misalnya, jika $$f$$ dan $$g$$ adalah dua pemetaan, $$f \cup g$$ menghasilkan himpunan pasangan terurut, tetapi ini hanya akan menjadi pemetaan jika domain $$f$$ dan $$g$$ tidak tumpang tindih. Sementara itu, $$f \cap g$$ dan $$f - g$$ memang menghasilkan pemetaan, tetapi biasanya tidak terlalu bermanfaat.

Namun, ada operator khusus untuk pemetaan yang lebih relevan. Kami akan membahas tiga di antaranya. Pertama, *pembatasan domain*. Untuk pemetaan $$f$$ dan himpunan $$A$$, notasi $$f\mid _A$$ menunjukkan pemetaan $$f$$ dengan domain yang dibatasi hanya pada elemen-elemen di $$A$$. Kita bisa mendefinisikannya sebagai:

$$
f\mid _A = \{a \mapsto b \mid a \mapsto b \in f \text{ dan } a \in A\}
$$

Operator kedua adalah *overriding union* atau sering disebut *override*. Untuk dua pemetaan $$f$$ dan $$g$$, $$f \oplus g$$ adalah pemetaan yang mengikuti $$g$$ di seluruh domain $$g$$, dan mengikuti $$f$$ di luar domain tersebut.[^3] Definisi formalnya adalah:

$$
f \oplus g = g \cup \left(\left.f\right|_{\text{ dom } f - \text{ dom } g}\right)
$$

Meskipun *override* tidak terlalu populer di kalangan matematikawan, konsep ini sangat penting dalam dunia komputasi. Bayangkan memori utama komputer sebagai pemetaan dari alamat memori ke nilai yang disimpan di alamat tersebut. Setiap operasi yang menyimpan nilai baru di memori adalah bentuk *override* pada pemetaan tersebut. Begitu pula, struktur data yang diakses dengan kunci atau indeks dapat dilihat sebagai pemetaan, dan operasi yang mengubah nilai dalam struktur data tersebut juga merupakan *override*.

Meskipun tidak langsung terlihat, operator *override* bersifat asosiatif, artinya $$(f \oplus g) \oplus h = f \oplus (g \oplus h)$$ untuk semua pemetaan $$f$$, $$g$$, dan $$h$$. Selain itu, ada pemetaan kosong (himpunan kosong) yang berfungsi sebagai identitas untuk $$\oplus$$. Dengan kata lain, pemetaan membentuk *monoid* di bawah $$\oplus$$, dengan pemetaan kosong sebagai elemen identitas. Namun, $$\oplus$$ tidak komutatif, karena *maplet* dalam operan kedua selalu mengambil precedence atas yang pertama.

Sifat asosiatif ini bisa kita manfaatkan untuk meningkatkan efisiensi saat memperbarui pemetaan besar, seperti yang sering ditemui dalam basis data atau sistem terdistribusi. Misalnya, jika kita punya urutan pembaruan $$g_0, g_1, \ldots, g_n$$ pada pemetaan $$f$$, hasil akhirnya adalah $$f \oplus g_0 \oplus g_1 \oplus \ldots \oplus g_n$$. Jika pembaruan ini relatif kecil dibandingkan $$f$$, kadang lebih efisien untuk menggabungkan semua pembaruan terlebih dahulu menjadi satu pemetaan besar, lalu menerapkannya ke $$f$$. Karena $$\oplus$$ tidak komutatif, kita harus memastikan urutan pembaruan tetap terjaga.

Operator ketiga adalah *komposisi*. Untuk dua pemetaan $$f$$ dan $$g$$, komposisi mereka ditulis $$g \circ f$$ dan didefinisikan sebagai:

$$
(g \circ f)(x) = g(f(x)).
$$

Atau dalam bentuk himpunan pasangan:

$$
g \circ f = \{\langle a, c \rangle \mid \langle a, b \rangle \in f \text{ dan } \langle b, c \rangle \in g\}
$$

Kita bisa membaca $$g \circ f$$ sebagai “$$g$$ diterapkan setelah $$f$$”. Untuk nilai $$x$$ masuk dalam domain $$g \circ f$$, $$x$$ harus ada di *dom* $$f$$, dan $$f(x)$$ harus ada di *dom* $$g$$.

Sebuah pemetaan juga bisa dikomposisikan dengan dirinya sendiri, yang sangat berguna jika $$\text{ran} f \subseteq \text{dom} f$$. Kita sering menulis $$f \circ f$$ sebagai $$f^2$$, $$f \circ f \circ f$$ sebagai $$f^3$$, dan seterusnya untuk pangkat yang lebih tinggi.

### 9.2. Kamus di Python

Kita sudah mengenal beberapa konstruk Python yang berperan seperti pemetaan matematis. Yang paling jelas adalah fungsi Python yang mengembalikan nilai—ini adalah pemetaan. Tapi, urutan statis seperti tupel, daftar, bahkan string juga bisa dianggap sebagai pemetaan. Ingat, elemen dalam urutan statis `S` bisa diakses dengan indeks: `S[i]`, di mana `i` adalah bilangan bulat dari 0 hingga `len(s)-1`. Jadi, urutan ini bisa dilihat sebagai pemetaan dengan domain berupa rentang indeks tersebut.

Kamus Python adalah jenis wadah statis lain yang berfungsi sebagai pemetaan, tapi dengan domain yang tidak terbatas pada bilangan bulat. Elemen pertama dari setiap pasangan terurut (kunci) bisa berasal dari berbagai tipe data Python.

Untuk membuat kamus, kita bisa menggunakan *dictionary display*, yaitu cara menuliskan pasangan terurut secara eksplisit. Tampilan kamus mirip dengan tampilan himpunan, tapi pasangan ditulis dengan dua nilai yang dipisahkan oleh titik dua. Contohnya, kamus berikut memetakan nama-nama angka dalam bahasa Inggris ke nilai numeriknya:

```python
numberValue = {"one": 1, "two": 2, "three": 3}
```

Di sini, titik dua berperan seperti operator *maplet* $$\mapsto$$. Elemen pertama disebut *kunci*, dan untuk mengambil nilai yang terkait dengan kunci tertentu, kita gunakan sintaks mirip pengindeksan urutan: nama kamus diikuti kunci dalam tanda kurung siku. Jadi, `numberValue["two"]` akan menghasilkan 2.

Kunci kamus bisa berasal dari hampir semua tipe Python, tapi karena Python menggunakan *hashing* (lihat Bagian 8.2) untuk menyimpan pasangan dalam kamus, kunci harus berupa objek yang tidak dapat diubah (*immutable*), seperti string atau bilangan. Nilai yang terkait dengan kunci, sebaliknya, bisa berupa objek Python apa saja.

Python juga mendukung *dictionary comprehension*, mirip dengan *set comprehension*, tapi berisi pasangan terurut dengan titik dua. Contoh berikut mengaitkan setiap bilangan bulat dari 0 hingga 49 dengan faktorialnya (lihat Bagian 4.2):

```python
{n: factorial(n) for n in range(50)}
```

Ada beberapa operasi yang bisa dilakukan pada kamus Python. Misalnya, untuk setiap kamus `d`, *`items(d)`* menghasilkan iterator yang mengembalikan pasangan kunci-nilai sebagai tupel dua elemen, *`keys(d)`* menghasilkan iterator untuk kunci-kunci (domain kamus), *`values(d)`* menghasilkan iterator untuk nilai-nilai (jangkauan kamus), *`len(d)`* memberikan jumlah pasangan terurut dalam kamus.

Untuk mengubah nilai, pernyataan seperti `d[k] = v` akan mengaitkan nilai `v` dengan kunci `k`, menimpa nilai sebelumnya jika ada. Dalam istilah matematika, ini setara dengan mengganti $$d$$ dengan $$d \oplus \{k \mapsto v\}$$. Jika kita punya kamus lain `e`, metode `d.update(e)` akan menimpa `d` dengan semua pasangan dari `e`, atau secara matematis, mengganti $$d$$ dengan $$d \oplus e$$.

Beberapa operasi kamus dirancang untuk kenyamanan pemrogram. Misalnya, ekspresi *`k in d`* memeriksa apakah $$k$$ adalah kunci dalam $$d$$, menggunakan *hashing* untuk efisiensi. Ekspresi *`k not in d`* bekerja serupa. Saat mengiterasi kamus dengan pernyataan *`for`*, iterator akan melintasi kunci-kunci, bukan pasangan kunci-nilai. Contohnya, jika *`codes`* adalah kamus dengan nilai berupa string, kode berikut akan menggabungkan semua string dalam urutan acak:

```python
codesString = ""
for k in codes:
    codesString += codes[k]
```

Pemrogram sering membuat kamus dari data dalam file datar (*flat files*), mirip dengan cara kita membuat himpunan di Bagian 8.4. Kita bisa memanfaatkan fungsi pembangkit *`streamOfTuples`* dari Contoh 8.2 untuk membuat kamus dari file CSV. Berikut fungsinya lagi:

```python
def streamOfTuples(fileName):
    return (line.strip().split(", ") for line in open(fileName))
```

Misalnya, jika *`addressBook`* adalah file CSV yang berisi nama dan alamat email, kita bisa membuat kamus yang memetakan nama ke email seperti ini:

```python
address = {name: email for (name, email) in streamOfTuples("addressBook")}
```

Untuk efisiensi, kita juga bisa membuat pemetaan dua arah (nama ke email dan email ke nama) dengan hanya membaca file sekali:

```python
address = {}
owner = {}
for (name, email) in streamOfTuples("addressBook"):
    address[name] = email
    owner[email] = name
```

Bagaimana jika kita ingin kamus yang menggunakan pasangan nilai sebagai kunci? Misalnya, file CSV *`populations`* berisi triplet: nama negara, nama kota, dan populasi kota. Kita perlu kedua informasi (negara dan kota) untuk mendapatkan populasi yang benar, karena, misalnya, Perth di Australia berbeda dengan Perth di Skotlandia. Ada dua cara untuk membuat kamus seperti ini.

Cara pertama adalah menggunakan 2-tupel (negara, kota) sebagai kunci:

```python
population = {(country, city): pop for (country, city, pop) in streamOfTuples("populations")}
```

Dengan ini, kita bisa mengakses populasi Perth di Australia dengan *`population["Australia", "Perth"]`*. Koma di antara string otomatis membentuk tupel, jadi tanda kurung tidak diperlukan.

Jika Anda pernah bekerja dengan bahasa pemrograman lain, Anda mungkin mengira ini seperti array dua dimensi. Tapi sebenarnya bukan—ini adalah struktur satu dimensi yang diakses dengan kunci berupa 2-tupel.

Cara yang lebih umum di Python adalah membuat kamus dari kamus, mirip dengan fungsi *curried*. Kita bisa membuat kamus dengan kunci berupa nama negara, dan nilai berupa kamus yang memetakan nama kota ke populasi. Berikut caranya:

```python
population = {}
tuples = setOfTuples("populations")
for country in {co for (co, city, pop) in tuples}:
    population[country] = {}
for (country, city, pop) in tuples:
    population[country][city] = pop
```

Sekarang, populasi Perth di Australia diakses dengan *`population["Australia"]["Perth"]`*. Untuk kamus dengan lebih dari dua kunci, logikanya serupa, hanya butuh lebih banyak level kamus.

### 9.3. Studi Kasus: Mencari Kata dalam File Teks

Mari kita jeda sejenak untuk sebuah studi kasus, menggabungkan berbagai konsep yang sudah kita pelajari. Kita akan menyelesaikan sebuah masalah pemrograman dan memilih struktur matematika diskret yang tepat untuk solusinya.

Bayangkan kita mendapat tugas membuat program dengan spesifikasi berikut:

>“Saya butuh program yang bisa mencari sejumlah kata dalam dokumen elektronik. Untuk setiap kata, program harus menampilkan kata tersebut beserta nomor baris di dokumen tempat kata itu muncul.”
>
>Daftar kata yang mau dicari ada di file bernama *`targets`*, satu kata per baris, dan berkas dokumen elektonik disimpan di file bernama *`document`*. 

Mungkin klien adalah penulis yang sedang membuat indeks buku atau peneliti yang mencari istilah tertentu di halaman web. Mari kita analisis permintaan ini dengan kacamata matematika diskret.

Kata-kata yang dicari jelas membentuk sebuah himpunan. Informasi yang diinginkan klien adalah pemetaan dari kata ke kumpulan nomor baris tempat kata itu muncul. Kumpulan ini sebaiknya berupa himpunan, karena jika sebuah kata muncul dua kali di baris yang sama, klien tidak ingin nomor barisnya muncul dua kali.

Dokumen bisa dilihat dengan beberapa cara. Pertama, sebagai urutan baris, di mana setiap baris adalah urutan kata yang dipisahkan spasi. Kedua, sebagai urutan kata tanpa mempedulikan baris, seperti yang kita lakukan di Bagian 7.5. Tapi, karena kita perlu tahu nomor baris, cara ketiga lebih cocok: dokumen sebagai aliran pasangan terurut (*kata*, *nomor baris*), yang dibuat secara dinamis saat kita membaca file. Meskipun kita bisa memperlakukan dokumen sebagai himpunan pasangan, aliran lebih efisien untuk dokumen panjang.

Beberapa bagian dari solusi ini sudah kita kenal. Untuk membuat himpunan kata-kata dari file *`targets`*, kita bisa gunakan *set comprehension* sederhana, seperti di Bagian 8.3:

```python
targets = {line.strip() for line in open("targets")}
```

Di Bagian 7.5, kita membuat fungsi pembangkit untuk menghasilkan aliran kata dari file, sambil menghapus tanda baca:

```python
def words(fileName):
    punctuation = ".., ;'" + '"'
    for line in open(fileName):
        words = line.strip().split()
        for word in words:
            yield word.strip(punctuation)
```

Kita bisa memodifikasi fungsi ini untuk menghasilkan pasangan (*kata*, *nomor baris*):

```python
def wordsAndLineNumbers(fileName):
    punctuation = ".., ;'" + '"'
    lineno = 0
    file = open(fileName)
    for line in file:
        lineno += 1
        words = line.strip().split()
        for word in words:
            yield (word.strip(punctuation), lineno)
```

Kamus Python adalah pilihan ideal untuk menyimpan pemetaan yang kita buat. Kata-kata dari *targets* akan menjadi kunci, dan setiap kunci dipetakan ke himpunan nomor baris. Kita inisialisasi kamus ini, yang kita namakan *linesFoundOn*, dengan *dictionary comprehension*:

```python
linesFoundOn = {t: set() for t in targets}
```

Proses utama sangat sederhana dengan operasi himpunan:

```python
for (word, lineno) in wordsAndLineNumbers("document"):
    if word in targets:
        linesFoundOn[word].add(lineno)
```

Sekarang, kita tinggal menampilkan hasilnya. Tantangannya adalah memformat himpunan nomor baris dengan rapi. Misalkan kita punya fungsi *`formatted`* untuk tugas ini, yang akan kita definisikan nanti. Dengan fungsi ini, menampilkan hasil jadi mudah:

```python
for t in targets:
    print(t + " " + formatted(linesFoundOn[t]))
```

Tugas terakhir adalah mendefinisikan *`formatted`*. Klien tidak menyebutkan urutan nomor baris, tapi urutan menaik sepertinya paling logis. Python punya fungsi *`sorted`* yang mengurutkan elemen iterable menjadi daftar. Kita akan gunakan itu. Jadi, *`formatted`* akan bekerja dengan *`sorted(numberSet)`*, di mana *`numberSet`* adalah parameter.

Python juga punya fungsi *join* untuk menggabungkan urutan string dengan pemisah tertentu. Kita pilih koma dan spasi sebagai pemisah. Karena *`sorted(numberSet)`* menghasilkan daftar angka, kita ubah ke string dengan:

```python
map(str, sorted(numberSet))
```

Jadi, kita bisa membuat fungsi *`formatted`* seperti berikut:

```python
def formatted(numberSet):
    separator = ", "
    return separator.join(map(str, sorted(numberSet)))
```

Gabungkan semua bagian, dan kita dapatkan program seperti di Contoh 9.1.

Perhatikan bagaimana program ini menggunakan contoh dari semua konstruksi matematika dan Python berikut:
- Aliran (*streams*) dan fungsi pembangkit (*generator*)
- Tupel dua elemen (*2-tuples*)
- Pemrograman fungsional dengan *map*
- Himpunan (*sets*) dan *set comprehensions*
- Pemetaan (*mappings*), kamus (*dictionary*), dan *dictionary comprehensions*

Setiap bagian program sangat ringkas dan jelas. Hanya *`wordsAndLineNumbers`* yang agak rumit, tapi itu wajar karena memproses input sering kali memang bagian yang paling berantakan. Total, program ini hanya 19 baris, tanpa menghitung baris kosong.

**Contoh 9.1. Mencari Kata dalam Dokumen**

```python
def wordsAndLineNumbers(fileName):
    punctuation = ".., ;'" + '"'
    lineno = 0
    file = open(fileName)
    for line in file:
        lineno += 1
        words = line.strip().split()
        for word in words:
            yield (word.strip(punctuation), lineno)

def formatted(numberSet):
    separator = ", "
    return separator.join(map(str, sorted(numberSet)))

targets = {line.strip() for line in open("targets")}
linesFoundOn = {t: set() for t in targets}
for (word, lineno) in wordsAndLineNumbers("document"):
    if word in targets:
        linesFoundOn[word].add(lineno)
for t in targets:
    print(t + " " + formatted(linesFoundOn[t]))
```

Misalkan file *document* berisi teks singkat ini:

>Wants pawn term dare worsted ladle gull hoe lift wetter murder inner ladle cordage honor itch offer lodge, dock, florist. Disk ladle gull orphan worry putty ladle rat cluck wetter ladle rat hut, an fur disk raisin pimple colder Ladle Rat Rotten Hut.[^4]

Dan file *targets* berisi:

```
ladle
gull
hut
```

Keluaran program mungkin seperti ini:

```
hut 3
gull 1, 2
ladle 1, 2, 3
```

Urutan keluaran tidak terjamin. Jika kita ingin urutan alfabetis, kita bisa ubah loop terakhir menjadi:

```python
for t in sorted(targets):
    print(t + " " + formatted(linesFoundOn[t]))
```

### 9.4. Kamus atau Fungsi?

Kita sudah melihat bahwa pemetaan bisa diimplementasikan sebagai struktur data (misalnya, urutan atau kamus di Python) atau melakukan komputasi (misalnya, fungsi Python). Kedua pendekatan ini sering kali setara, terutama dari sudut pandang kode yang menggunakan pemetaan. Di Python, notasi untuk mengakses pemetaan juga mirip: `f[a]` untuk urutan atau kamus, dan `f(a)` untuk fungsi.

Memilih antara struktur data dan fungsi bergantung pada beberapa pertimbangan:
- Struktur data harus berukuran terbatas dan praktis (lihat Bagian 2.3). Jika domain pemetaan sangat besar, seperti semua bilangan bulat atau string Python, fungsi mungkin satu-satunya pilihan yang masuk akal.
- Beberapa pemetaan dalam sebuah program perlu bisa diubah (*mutable*). Ini mudah dengan struktur data seperti daftar atau kamus. Kode fungsi biasanya tidak bisa diubah oleh program, tapi kita bisa membuat fungsi yang hasilnya bergantung pada data dalam variabel atau struktur data yang dapat diubah.
- Kamus Python sangat efisien untuk mencari nilai berdasarkan kunci, sering kali lebih cepat daripada komputasi lain.
- Tergantung situasi, salah satu pendekatan mungkin lebih mudah diprogram. Untuk fungsi, kita perlu tahu cara menghitung pemetaan dengan metode yang sederhana. Jika pemetaan tampak arbitrer, struktur data dengan data eksplisit mungkin lebih praktis.
  
  Data untuk struktur data bisa berasal dari kode program (misalnya, *dictionary display*) atau sumber eksternal seperti file atau basis data. Kita sudah melihat cara membuat kamus dari file. Namun, kadang lebih efisien membuat fungsi yang hanya membaca sebagian data dari file, meskipun kita tidak membahas teknik ini di buku ini.

Bahkan jika ada cara komputasi yang jelas untuk pemetaan, kadang lebih baik menghitung hasilnya terlebih dahulu dan menyimpannya dalam struktur data. Contohnya, misalkan sebuah program memiliki kamus-dari-kamus bernama `distance` yang memetakan pasangan kota ke jarak antar kota melalui jalan (dalam kilometer, misalnya). Mungkin kamus `distance` ini dibuat dari sebuah file datar, seperti cara pembuatan kamus `population` pada konstruksi kedua di Bagian 9.2. Untuk mendapatkan jarak antara dua kota, program akan menggunakan ekspresi seperti `distance[city][otherCity]`.

Jika program perlu menemukan kota terdekat untuk sebuah kota, kita bisa membuat fungsi seperti ini:

```python
def nearest(city):
    # neighborDistance: kamus yang memetakan tetangga kota ke jaraknya
    neighborDistance = distance[city]
    nearest = None
    minDistance = float("Infinity")
    for otherCity in neighborDistance:
        if neighborDistance[otherCity] < minDistance:
            nearest = otherCity
            minDistance = neighborDistance[otherCity]
    return nearest
```

Fungsi ini menarik karena: Menggunakan aplikasi parsial untuk mendapatkan *neighborDistance*; Mengembalikan *None* jika tidak ada tetangga, memastikan hasil yang terdefinisi, dan; Menggunakan *float("Infinity")* sebagai nilai awal untuk mencari minimum.

Tapi, fungsi ini lambat jika setiap kota punya banyak tetangga (katakanlah rata-rata $$n$$ tetangga). Satu panggilan *nearest* butuh waktu sebanding dengan $$n$$. Jika dipanggil $$m$$ kali, total waktunya sebanding dengan $$m \cdot n$$, yang bisa jadi masalah untuk $$m$$ dan $$n$$ besar.

Solusinya adalah menghitung *nearest* untuk semua kota dan menyimpannya:

```python
nearestStored = {city: nearest(city) for city in distance.keys()}
```

Akses ke *`nearestStored[city]`* jauh lebih cepat daripada memanggil *`nearest(city)`*. Meskipun membuat *`nearestStored`* butuh waktu (sebanding dengan $$k \cdot n$$ untuk $$k$$ kota), hasilnya sepadan jika $$m$$ jauh lebih besar dari $$k$$.

Ada teknik lain yang disebut *memoization*—bukan typo, tapi “memo-ization”, dari kata “memo”. Ide *memoization* adalah menyimpan hasil komputasi agar bisa digunakan lagi tanpa menghitung ulang. Fungsi yang dimemoize menyimpan hasilnya dalam tabel (biasanya kamus) dengan argumen sebagai kunci. Jika dipanggil lagi dengan argumen sama, fungsi mengambil hasil dari tabel.

Contohnya, mari kita lihat fungsi untuk menghitung bilangan Fibonacci ke-$$n$$. Di Bagian 7.2, kita membuat fungsi untuk urutan Fibonacci. Sekarang, kita ingin fungsi yang hanya mengembalikan bilangan ke-$$n$$, dengan indeks mulai dari 0.

Versi iteratifnya seperti ini:

```python
def fib(n):
    a = 1
    b = 1
    for i in range(n):
        a, b = b, a + b
    return a
```

Fungsi ini efisien untuk satu bilangan, tapi jika dipanggil berulang kali, ia menghitung ulang banyak nilai. Misalnya, *`fib(1000)`* menjalankan loop 1000 kali, padahal bisa lebih cepat jika *`fib(999)`* dan *`fib(998)`* sudah tersedia.

Versi rekursifnya lebih sederhana tapi sangat lambat:

```python
def rfib(n):
    if n == 0 or n == 1:
        return 1
    else:
        return rfib(n-2) + rfib(n-1)
```

Fungsi ini menghitung ulang nilai seperti *`rfib(n-2)`* berkali-kali, membuatnya sangat tidak efisien.

Sekarang, versi yang dimemoize:

**Contoh 9.2. Fungsi Memoized: Bilangan Fibonacci ke-$$n$$**

```python
fibStored = {}
def mfib(n):
    if n in fibStored:
        return fibStored[n]
    elif n == 0 or n == 1:
        return 1
    else:
        result = mfib(n-2) + mfib(n-1)
        fibStored[n] = result
        return result
```

Ketiga versi menghitung semua bilangan Fibonacci hingga ke-$$n$$. Versi iteratif hanya menghitung sekali. Versi memoized juga hanya menghitung sekali per nilai, sambil menyimpan hasilnya. Jadi, ia seefisien versi iteratif untuk satu panggilan, tapi lebih baik untuk panggilan berulang karena hasil sebelumnya tersimpan.

### 9.5. Multiset

Kita pertama kali bertemu multiset di Bagian 1.3, saat membahas file pengamatan suhu sebagai multiset. Multiset (atau kadang disebut “bag”) mirip dengan himpunan, tapi juga punya kesamaan dengan pemetaan, seperti yang akan kita lihat.

Dalam matematika, tidak ada notasi standar untuk multiset. Kadang ditulis seperti himpunan, misalnya $$\{2, 2, 3\}$$ untuk multiset dengan dua 2 dan satu 3. Di buku ini, kita gunakan tanda kurung khusus $$\{2, 2, 3\}$$ untuk membedakannya dari himpunan $$\{2, 3\}$$. Ini memudahkan kita membedakan multiset dari himpunan.

Multiset jarang dibahas di kelas matematika, karena himpunan jauh lebih dominan. Tapi, multiset punya peran penting. Misalnya, faktor prima dari 360 ($$2 \cdot 2 \cdot 2 \cdot 3 \cdot 3 \cdot 5$$) adalah multiset $$\{2, 2, 2, 3, 3, 5\}$$. Atau, akar persamaan kuadrat seperti $$x^2 - 4x + 4 = 0$$ (yang bisa ditulis $$(x-2)(x-2) = 0$$) adalah multiset $$\{2, 2\}$$.

Contoh lain: daftar barang berbeda di toko adalah himpunan, tapi inventaris barang di rak adalah multiset, karena kita perlu menghitung jumlah setiap barang.

Multiset bisa dilihat sebagai pemetaan dari elemen ke jumlah kemunculannya. Misalnya, $$\{2, 2, 2, 3, 3, 5\}$$ setara dengan $$\{2 \mapsto 3, 3 \mapsto 2, 5 \mapsto 1\}$$. Jika multiset ini adalah $$m$$, jumlah 3 adalah $$m(3) = 2$$.

Kita definisikan fungsi *count*: untuk multiset $$m$$ dan nilai $$a$$, *count($$m$$, $$a$$)* adalah $$m(a)$$ jika $$a$$ ada di domain $$m$$, dan 0 jika tidak.[^5]

Dengan *count*, kita bisa definisikan operasi multiset:
- *Jumlah multiset* ($$m \uplus n$$): jumlah elemen adalah jumlah dari kedua multiset.
- *Gabungan multiset* ($$m \cup n$$): jumlah elemen adalah maksimum dari kedua multiset.
- *Irisan multiset* ($$m \cap n$$): jumlah elemen adalah minimum dari kedua multiset.

Secara formal:

$$
\text{count}(m \uplus n, a) = \text{count}(m, a) + \text{count}(n, a)
$$

$$
\text{count}(m \cup n, a) = \max(\text{count}(m, a), \text{count}(n, a))
$$

$$
\text{count}(m \cap n, a) = \min(\text{count}(m, a), \text{count}(n, a))
$$

Di Python, multiset bisa diimplementasikan sebagai urutan (tupel atau daftar) atau kamus. Urutan memungkinkan duplikasi tapi lambat untuk menghitung jumlah (*m.count(a)* harus memeriksa seluruh urutan). Kamus lebih cepat untuk mengakses jumlah, dengan *`m[a]`* jika $$a$$ ada, atau:

```python
def count(m, a):
    return m[a] if a in m else 0
```

Untuk membuat multiset dari file, kita bisa gunakan *`streamOfValues`*:

```python
def multisetOfValues(fileName):
    m = {}
    for a in streamOfValues(fileName):
        m[a] = m.get(a, 0) + 1
    return m
```

Untuk bilangan bulat:

```python
def multisetOfIntegers(fileName):
    m = {}
    for a in streamOfValues(fileName):
        n = int(a)
        m[n] = m.get(n, 0) + 1
    return m
```

Pola umum untuk menghitung adalah fungsi *`tally`*:

```python
def tally(m, x):
    m[x] = m.get(x, 0) + 1
```

Contoh program yang menggunakan multiset untuk menghitung jumlah siswa per jurusan:

**Contoh 9.3. Jumlah Siswa per Jurusan**

```python
counts = {}
for (name, major) in streamOfTuples("students"):
    tally(counts, major)
for major in counts:
    print(f"{major}: {counts[major]}")
```

**Istilah Baru di Bab Ini**
- *Maplet*
- Domain
- Jangkauan
- Fungsi *curried*
- Pembatasan domain
- *Overriding union* atau *override*
- Komposisi
- Pangkat pemetaan
- *Dictionary display*
- *Dictionary comprehension*
- Kunci
- *Memoization*
- Jumlah, gabungan, dan irisan multiset

**Latihan**
1. Lihat fungsi Python berikut:

```python
def p(x, y):
    return x * y
```
Python tidak membatasi domain $$p$$. Apa domainnya dalam bentuk ini?

2. Buktikan bahwa $$\oplus$$ bersifat asosiatif dengan contoh atau bukti matematis.

3. Kapan $$c \oplus d = d \oplus c$$ untuk pemetaan $$c$$ dan $$d$$?

4. Tulis fungsi Python yang mengembalikan komposisi dua fungsi satu argumen.

5. Tulis fungsi Python yang mengembalikan komposisi dua kamus.

6. Apakah $$f^0$$ masuk akal untuk fungsi $$f$$? Jika ya, apa artinya?

7. Apakah komposisi fungsi asosiatif? Apakah ada identitasnya? Apakah ini monoid lain?

8. Bandingkan efisiensi kamus dengan kunci tupel vs. kamus dari kamus di Python. Faktor apa lagi yang memengaruhi pilihan?

9. Tulis ulang *wordsAndLineNumbers* menggunakan *zip*. Mana yang lebih baik?

10. Modifikasi program di Bagian 9.3 agar tidak peka huruf besar-kecil.

11. Apakah *float("Infinity")* sebagai nilai awal di *nearest* terkait dengan monoid? Apa nilai awal untuk maksimum? Bisakah *nearest* ditulis ulang dengan *reduce*?

12. Bandingkan efisiensi *fib*, *rfib*, dan *mfib* dengan berbagai nilai $$n$$.

13. Coba memoize fungsi seperti *nearest*, *factorial*, atau *isPrime*. Uji efisiensinya.

14. Tulis fungsi Python untuk gabungan dan irisan multiset sebagai daftar.

15. Tulis fungsi Python untuk jumlah, gabungan, dan irisan multiset sebagai kamus, tanpa kunci bernilai nol.

[back](./)

---

[^1]: In mathematics there are a variety of terms and definitions for these and related concepts, but these are the definitions that we will use in this book. Be aware, though, that you might see somewhat different vocabulary in other books.

[^2]: Yes, feel free to make the obvious puns. Chutney, anyone?

[^3]: The symbol ⊕ is from the Z notation. Z is a mathematical notation, developed at Oxford University, for writing specifications of programs.

[^4]: Howard L. Chace, Anguish Languish, Prentice-Hall, 1956. At the time of writing, available at http://www.justanyone.com/allanguish.html, which asserts that the copyright of the book has expired. (Try reading the sample text aloud with a bit of a drawl.)

[^5]: In mathematics the term “multiplicity” is often used instead of “count”, but we will use the shorter word.
