## Bab 2: Sekilas tentang Python

### 2.1. Pendahuluan

Dalam bab ini dan dua bab berikutnya, kami akan memperkenalkan gambaran umum tentang bahasa pemrograman Python. Tujuannya adalah memberikan pemahaman yang cukup untuk mengikuti contoh-contoh Python yang akan muncul di bagian lain buku ini. Sepanjang pembahasan, kami akan memperkenalkan istilah-istilah penting terkait konsep Python. Banyak dari istilah ini bukan eksklusif untuk Python, melainkan bagian dari kosakata umum dalam ilmu komputer untuk membahas bahasa pemrograman. Istilah-istilah ini akan sering digunakan di bagian lain buku, jadi meskipun Anda sudah familiar dengan Python, ada baiknya Anda membaca sekilas bab-bab ini untuk memastikan Anda mengenal semua istilah yang kami gunakan.

Anda mungkin sudah melihat contoh program Python yang membaca data dari file. Menariknya, program Python itu sendiri juga berupa teks yang disimpan dalam file. Jika Anda memiliki skrip dari bab sebelumnya di komputer, masing-masing skrip akan tersimpan dalam file terpisah.

Di sebagian besar sistem komputer, Anda juga bisa menggunakan [[interpreter]] Python secara interaktif. Dengan mode ini, Anda dapat mengetik potongan kode Python kecil, dan interpreter akan langsung menampilkan hasilnya. Misalnya, Anda bisa menggunakannya seperti kalkulator sederhana. Coba ketik:

```
3 + 2
```

Interpreter akan menampilkan:

```
5
```

Jika Anda sedang membaca buku ini dengan komputer di dekat Anda, cobalah bereksperimen dengan fitur Python yang sedang dibahas. Ketik potongan kode ke interpreter dan amati apa yang terjadi. Silakan lakukan ini kapan saja selama membaca untuk memperdalam pemahaman Anda.

### 2.2. Nilai, Tipe, dan Nama

Mari kita mulai dengan konsep dasar Python yang menjadi fondasi cara berpikir tentang komputasi dalam bahasa ini.

Di Python, semua komputasi berpusat pada **nilai (values)**. Komputasi mengambil nilai sebagai masukan dan menghasilkan nilai baru sebagai keluaran. Misalnya, saat Anda mengetik `3 + 2` di interpreter Python, Python mengambil nilai `3` dan `2`, melakukan operasi penjumlahan, dan menghasilkan nilai `5`.

Kita sudah melihat beberapa jenis nilai. Angka seperti `3` dan `2` adalah nilai. Urutan karakter seperti `"John"` juga merupakan nilai. Bahkan objek yang lebih kompleks, seperti file yang dibuka dalam skrip dari Bab 1, adalah nilai. Nanti, kita akan melihat bahwa Python juga mendukung nilai berupa urutan lain, himpunan, pemetaan, dan banyak lagi.

Setiap nilai memiliki **tipe (types)**. Tipe dari angka seperti `3` dan `2` adalah **integer** (bilangan bulat). Tipe dari urutan karakter seperti `"John"` adalah **string** (teks). Python memiliki banyak tipe lain, yang akan kita jelajahi lebih lanjut di bab-bab berikutnya.

Tipe bukan sekadar label untuk jenis nilai. Tipe menentukan dua hal penting: **kumpulan nilai yang mungkin** dan **operasi yang bisa dilakukan pada nilai tersebut**. Misalnya, pada bilangan bulat, Anda bisa melakukan penjumlahan, sedangkan pada string, Anda bisa melakukan pemisahan berdasarkan karakter tertentu.

Terakhir, **nama (names)** memainkan peran sentral dalam pemrograman Python dan digunakan dalam berbagai cara. Salah satu penggunaan penting adalah **mengikat nama ke nilai**. Contohnya, dalam skrip yang menghitung rata-rata, kita menulis:

```
count = 0
```

Baris ini mengikat nama `count` ke nilai `0`. Istilah lain untuk tindakan ini adalah **penugasan (assignment)**: kita mengatakan bahwa nilai `0` ditugaskan ke `count`. Dalam program Python, baris seperti ini disebut **pernyataan penugasan (assignment statement)**. Ada beberapa cara untuk mengikat nama ke nilai di Python, tetapi penugasan adalah cara paling sederhana.

Nama yang diikat melalui penugasan disebut **variabel**, karena nilai yang diikat ke nama tersebut bisa berubah. Misalnya, dalam skrip penghitung rata-rata, kita punya baris:

```
count += 1
```

Baris ini mengikat `count` ke nilai baru, yaitu satu lebih besar dari nilai sebelumnya. Sebuah program bisa mengubah pengikatan variabel berkali-kali. Dalam skrip rata-rata kita, pengikatan ini dilakukan sekali untuk setiap baris dalam file data.

Menariknya, dalam Python, Anda bahkan bisa melakukan hal seperti ini dalam program yang sama, meskipun biasanya tidak disarankan:

```
count = "Hello, John!"
```

Ini menunjukkan bahwa tipe variabel di Python tidak tetap. Tipe adalah sifat dari **nilai**, bukan nama. Ketika kita berbicara tentang “tipe variabel”, yang dimaksud adalah tipe dari nilai yang sedang diikat ke variabel tersebut.

Namun, dalam praktiknya, kebanyakan programmer Python menggunakan variabel dengan tipe yang konsisten sepanjang program, karena ini adalah cara yang paling alami dan mudah dipahami. Selain itu, programmer yang baik memilih nama yang mencerminkan kegunaan variabel. Misalnya, memberikan nama `count` untuk string seperti `"Hello, John!"` tidak masuk akal, meskipun Python mengizinkannya.

Perlu dicatat bahwa mengatakan penugasan mengikat nama ke nilai adalah sedikit penyederhanaan. Yang sebenarnya terjadi adalah [[nilai objek|nama diikat ke objek]], dan objek inilah yang menyimpan nilai. Kita akan membahas perbedaan ini lebih lanjut nanti. Untuk saat ini, Anda bisa menganggap nama diikat langsung ke nilai tanpa perlu memikirkan detail objek.

### 2.3. Bilangan Bulat

Bilangan bulat di Python mirip dengan bilangan bulat dalam matematika: yaitu, semua bilangan bulat positif, negatif, dan nol. Dalam python, bilangan bulat atau integers adalah tipe data bernama **int**.

Anda bisa melakukan operasi matematika dasar pada bilangan bulat, seperti penjumlahan, pengurangan, perkalian, dan pembagian, yang ditulis dengan simbol di antara dua angka, seperti ini:

```
3 + 2
3 - 2
3 * 2
3 / 2
```

Simbol-simbol ini disebut **[[operator]]**, dan angka-angka yang dioperasikan disebut **operan**. Operator seperti `+`, `-`, `*`, dan `/` adalah **operator biner** karena membutuhkan dua operan. (Catatan: Istilah “biner” di sini tidak berkaitan dengan sistem bilangan biner, melainkan jumlah operan.)

Dalam kode Python, urutan digit seperti `123`, `2`, atau `0` mewakili bilangan bulat non-negatif. Urutan digit ini adalah **konstanta**, yaitu simbol yang selalu mewakili nilai tertentu dan tidak bisa diikat ke nilai lain.

Untuk bilangan bulat negatif, kita menambahkan tanda minus di depan, seperti:

```
-123
```

Di sini, tanda minus adalah **operator unary**, yang hanya membutuhkan satu operan. Perhatikan bahwa tanda minus (`-`) bisa berfungsi sebagai operator biner (dalam `3 - 2`) atau unary (dalam `-123`), tergantung konteks.

Kombinasi operator dan operan membentuk **ekspresi (expression)**. Seperti di banyak bahasa pemrograman, Anda bisa membangun ekspresi yang lebih kompleks dengan menggabungkan ekspresi kecil menggunakan operator, dan tanda kurung bisa digunakan untuk mengatur urutan operasi. **Mengevaluasi ekspresi** berarti menghitung semua bagiannya untuk mendapatkan nilai akhir.

Jika operan dari operator `+`, `-`, atau `*` adalah bilangan bulat, hasilnya juga bilangan bulat. Namun, operator `/` berbeda: misalnya, `3 / 2` menghasilkan `1.5`, seperti dalam matematika. Nilai `1.5` ini bukan bilangan bulat karena memiliki bagian pecahan, melainkan **bilangan floating-point**, yang akan kita bahas di bagian berikutnya.

Python memiliki operator pembagian lain, `//`, yang selalu menghasilkan bilangan bulat. Misalnya, `4 // 2` menghasilkan `2` (bilangan bulat), dan `14 // 3` menghasilkan `4` (dibulatkan ke bawah dengan mengabaikan sisanya). Operator `%` digunakan untuk mendapatkan sisa pembagian, seperti `14 % 3` yang menghasilkan `2`.

Python juga punya operator lain untuk bilangan bulat, seperti `**` untuk eksponensiasi. Contohnya, `2 ** 8` berarti `2^8`.

Selain itu, Python memiliki **operator penugasan tambahan (augmented assignment)** yang menggabungkan operasi aritmatika dan penugasan. Kita sudah melihat `+=` dalam:

```
count += 1
```

Baris ini menambahkan `1` ke nilai `count` dan mengikat hasilnya kembali ke `count`. Python juga memiliki operator seperti `-=` dan `*=`, tetapi `+=` adalah yang paling sering digunakan.

Satu keunggulan Python adalah bilangan bulat tidak memiliki batasan ukuran bawaan. Anda bisa menghitung `2 ** 2 ** 8`, yang menghasilkan angka sangat besar, dan itu tetap valid sebagai bilangan bulat. Namun, ada batasan praktis: misalnya, menghitung `2 ** 2 ** 100` akan menghasilkan angka yang terlalu besar untuk disimpan atau diproses oleh komputer dalam waktu yang wajar.

Dalam matematika, bilangan seperti `2^(2^100)` adalah angka terbatas (*finite*) yang valid, dan kita bahkan bisa mendefinisikan angka yang lebih besar. Matematika juga memiliki konsep bilangan tak terbatas/ tak hingga (*infinite*), yang berbeda dari bilangan terbatas. Python menyediakan representasi untuk “tak terbatas” dalam bilangan floating-point, seperti yang akan kita lihat nanti, meskipun kegunaannya terbatas.[^1]

Dalam pemrograman, selain bilangan terbatas dan tak terbatas, ada kategori ketiga: bilangan yang **terbatas tapi terlalu besar** untuk dihitung secara praktis, seperti  `2^(2^100)` . Keterbatasan ini juga berlaku untuk struktur data lain, seperti himpunan atau urutan, yang akan kita bahas di bab berikutnya. Pemrogram harus menghindari operasi yang menghasilkan nilai atau struktur data yang terlalu besar untuk ditangani komputer.

Jadi, jika matematika membedakan antara terbatas dan tak terbatas, dalam pemrograman kita juga harus membedakan antara yang **praktis** dan **tidak praktis**. Menentukan batas ini dan mengelompokkan nilai atau komputasi berdasarkan kelayakan praktis adalah inti dari ilmu komputer, yang akan Anda pelajari lebih lanjut jika Anda menekuni bidang ini.

### 2.4. Bilangan Pecahan

Di Python, bilangan pecahan/ **[[floating-point]]** adalah tipe data bernama **float**, yang digunakan untuk mewakili bilangan dengan bagian pecahan, seperti hasil dari `3 / 2` yang menghasilkan `1.5`. Jika bilangan bulat Python menyerupai bilangan bulat matematika, bilangan floating-point berupaya mewakili **bilangan real** dalam matematika. Namun, floating-point hanya merupakan **perkiraan** dari bilangan real, dan ada perbedaan penting yang akan kita bahas.

Python memiliki dua cara untuk menulis konstanta floating-point:
- **Desimal biasa**: Urutan digit dengan titik desimal, seperti `3.14` atau `.001`.
- **Notasi ilmiah**: Misalnya, `6.02 x 10^23` ditulis sebagai `6.02E23` di Python. Huruf `E` (atau `e`) diikuti angka menunjukkan pangkat sepuluh, yang bisa positif atau negatif (contoh: `1e-6`, yang merepresentasikan satu per sejuta).

Operasi aritmatika pada bilangan floating-point mirip dengan bilangan bulat, tetapi jika operannya adalah floating-point, hasilnya juga floating-point. Anda bisa mencampur bilangan bulat dan floating-point dalam satu ekspresi; Python akan mengonversi bilangan bulat ke floating-point sebelum melakukan operasi. Misalnya, `3 + 2.5` menghasilkan `5.5`.

Untuk mengonversi tipe secara eksplisit, Python menyediakan **fungsi**. Fungsi di sini berperilaku seperti fungsi matematika: mengambil nilai masukan, yang disebut **argumen (argument)** dan menghasilkan nilai keluaran. Untuk memanggil fungsi, kita menulis **[[function call|pemanggilan fungsi (function call)]]**, terdiri dari nama fungsi, diikuti oleh sebuah ekspresi dalam tanda kurung; ekspresi tersebut adalah argumen. Ketika interpreter Python mengevaluasi sebuah pemanggilan fungsi, kita mengatakan bahwa interpreter memanggil fungsi tersebut (*calls*), kemudian memberikan argumen (*passing*) kepada fungsi itu. Fungsi mengembalikan nilai (*returns*), yang kemudian menjadi nilai dari ekspresi pemanggilan fungsi.

Contoh fungsi konversi:
- `float(n)`: Mengubah bilangan bulat atau string ke floating-point. Misalnya, `float(3)` menghasilkan `3.0`.
- `int(x)`: Mengubah floating-point ke bilangan bulat dengan memotong pecahan. Misalnya, `int(2.7)` menghasilkan `2`.
- `round(x)`: Membulatkan floating-point ke bilangan bulat terdekat. Misalnya, `round(2.7)` menghasilkan `3`.

Python juga bisa merepresentasikan “tak terbatas” menggunakan `float("inf")` atau `float("Infinity")` untuk tak terbatas positif, dan `float("-inf")` untuk tak terbatas negatif. Nilai ini berguna karena selalu lebih besar (atau lebih kecil) dari bilangan lain, tetapi kegunaannya terbatas dan tidak akan banyak dibahas di buku ini.

Bilangan floating-point disimpan di komputer menggunakan format mirip notasi ilmiah, dengan tanda, eksponen, dan digit signifikan (mantissa). Pada kebanyakan komputer, Python menggunakan format **double precision** (64 bit). Yang penting, eksponen dan mantissa memiliki jumlah bit yang tetap, yang berarti [[floating-point#Representasi floating-point|hanya sejumlah terbatas bilangan floating-point yang bisa direpresentasikan]]. Akibatnya, dalam Python, ada **lebih banyak bilangan bulat** daripada bilangan floating-point—kebalikan dari matematika, di mana bilangan real jauh lebih banyak daripada bilangan bulat.

Karena keterbatasan jumlah bit, floating-point memiliki dua batasan utama:
- **Batasan magnitudo**: Eksponen membatasi seberapa besar atau kecil bilangan yang bisa direpresentasikan. Namun, batasan ini jarang menjadi masalah, karena bilangan floating-point bisa sangat besar (hingga sekitar `1.8 x 10^308`).
- **Batasan presisi**: Mantissa hanya menyimpan sejumlah digit signifikan tertentu (sekitar 15-17 digit desimal). Ini berarti banyak bilangan real, seperti `pi` atau `1/3`, hanya bisa diaproksimasi. Misalnya, `1/3` menghasilkan `0.3333333333333333`, bukan desimal tak terbatas seperti dalam matematika.

Akibatnya, komputasi dengan floating-point harus dilakukan dengan hati-hati. Misalnya, `1/3 + 1/3 + 1/3` mungkin tidak persis sama dengan `1.0` karena **kesalahan pembulatan (roundoff error)**. Dalam **perhitungan yang panjang**, galat pembulatan ini dapat **menumpuk** dan menyebabkan hasil perhitungan menjadi **tidak akurat** secara signifikan..

### 2.5. String

Seperti yang sudah disebutkan, urutan karakter dalam Python disebut **string** atau **str**. String bisa berisi tidak hanya karakter dari keyboard Anda, tetapi juga semua karakter dalam set **Unicode**, yang mencakup huruf dari berbagai bahasa (seperti Cina, Arab, atau Cherokee), simbol matematika, dan banyak lagi. Namun, untuk keperluan buku ini, karakter keyboard sudah cukup.

Konstanta string ditulis dengan mengapit teks dalam tanda kutip ganda (`"`) atau tunggal (`'`). Contoh:

```
"Here's one"
'His name is "John"'
```

String dengan tanda kutip ganda bisa berisi tanda kutip tunggal, dan sebaliknya. String juga bisa kosong, seperti `""`, yang disebut **string kosong** (*empty string*) atau **"null string"** dan memiliki kegunaan tertentu.

Python tidak memiliki tipe khusus untuk karakter tunggal (*character*); karakter dianggap sebagai string dengan panjang satu. Untuk mengonversi nilai lain ke string, gunakan fungsi `str`. Misalnya, `str(3)` menghasilkan `"3"`.

Salah satu operasi penting pada string adalah **konkatenasi (concatenation)**, yaitu menggabungkan dua string ujung ke ujung. Python menggunakan operator `+` untuk ini. Contoh:

```
"python" + "interpreter"
```

menghasilkan `"pythoninterpreter"`. Jadi, operator `+` di Python memiliki tiga makna: penjumlahan bilangan bulat, penjumlahan floating-point, dan konkatenasi string. Ini disebut **overloading**.

Operator `*` juga bisa digunakan pada string jika salah satu operannya adalah bilangan bulat, untuk mengulang string beberapa kali. Misalnya:

```
3 * "Hello"
```

menghasilkan `"HelloHelloHello"`. Bilangan bulat bisa berada di kiri atau kanan operator. Namun, Python tidak mengizinkan operasi seperti `+` antara string dan bilangan bulat, meskipun Anda mungkin berpikir itu akan mengonversi bilangan ke string secara otomatis.

**Istilah yang Diperkenalkan di Bab Ini:**
- **tipe** (_type_)
- **nama** (_name_)
- **pengikatan** (_binding_)
- **penugasan** (_assignment_)
- **pernyataan penugasan** (_assignment statement_)
- **variabel** (_variable_)
- **bilangan bulat** (_integer_)
- **operator** (_operator_)
- **operan** (_operand_)
- **operator biner** (_binary operator_)
- **konstanta** (_constant_)
- **operator unary** (_unary operator_)
- **ekspresi** (_expression_)
- **mengevaluasi** (_evaluating_)
- **floating-point** (_floating-point_)
- **penugasan tambahan** (_augmented assignment_)
- **fungsi** (_function_)
- **argumen** (_argument_)
- **panggilan fungsi** (_function call_)
- **memanggil fungsi** (_calling a function_)
- **mengoper argumen** (_passing an argument_)
- **mengembalikan** (_return_)
- **string kosong** (_empty string_)
- **konkatenasi** (_concatenation_)
- **kelebihan beban** (_overloading_)

**Latihan**

1. Kami menyebutkan bahwa `2^(2^8)` adalah nilai Python yang valid, tetapi `2^(2^100) `terlalu besar. Untuk ekspresi seperti `2 ** 2 ** n`, nilai `n` berapa yang membuat hasilnya terlalu besar untuk dihitung secara praktis? Coba eksperimen dengan interpreter Python Anda. Mulai dari nilai `n` kecil, lalu coba nilai yang lebih besar. Apa yang terjadi?
2. Apa yang terjadi jika Anda mencoba mengevaluasi `2 ** 2 ** 100` di interpreter Python? Biarkan berjalan lama jika perlu. Bisakah Anda menjelaskan hasilnya?
3. Perkirakan berapa banyak digit desimal yang dibutuhkan untuk menulis `2^(2^100)`. Petunjuk: gunakan logaritma. Anda bisa menggunakan komputer untuk membantu.
4. Perbandingan seperti `1.0 == 1` menghasilkan `True` atau `False`. Coba di interpreter Python: Anda mungkin mendapatkan `True` untuk `1.0 == 1`. Lalu coba `1/3 + 1/3 + 1/3 == 1.0`; hasilnya bisa `True` atau `False`, tergantung pembulatan di komputer Anda. Temukan perbandingan yang seharusnya `True` dalam matematika, tetapi menghasilkan `False` di Python.
5. Apakah konkatenasi string bersifat asosiatif seperti penjumlahan bilangan bulat? Apakah bersifat komutatif?
6. Tingkatkan skrip yang membaca file dan mencari baris yang dimulai dengan `"John"`. Ubah agar hanya mencocokkan nama depan `"John"`, bukan kata seperti `"Johnson"`. Anda sudah cukup belajar Python untuk menebak caranya. Asumsikan setiap baris file berisi nama depan, spasi, dan nama belakang. Uji solusi Anda dengan interpreter Python.

---

[^1]: Ya, dalam matematika ada angka tak terbatas yang berbeda. Misalnya, jumlah titik pada garis lebih besar dari jumlah bilangan bulat: sebenarnya lebih besar, pada kenyataannya.
