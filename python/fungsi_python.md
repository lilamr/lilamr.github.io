## Bab 4: Fungsi dalam Python

### 4.1. Mendefinisikan Fungsi

Bab ini akan membahas cara mendefinisikan fungsi di Python dan berbagai hal menarik yang bisa kita lakukan dengan fungsi. 

Seperti yang sudah kita lihat, ada fungsi Python yang menghitung nilai, ada pula yang menghasilkan efek samping, seperti menampilkan sesuatu ke layar. Dalam beberapa bahasa pemrograman, fungsi yang menghasilkan efek samping disebut "subrutin" atau "prosedur", tetapi di Python, semua disebut "fungsi" dan didefinisikan dengan cara yang sama.

Mari kita mulai dengan contoh [[definisi fungsi]] (*function definition*). Python sebenarnya sudah punya fungsi untuk menghitung nilai absolut, tapi kalau tidak ada, kita bisa membuatnya sendiri seperti ini:

```python
def abs(n):
    if n >= 0:
        return n
    else:
        return -n
```

Definisi fungsi adalah pernyataan majemuk. Bagian kepalanya mencakup nama fungsi dan nama parameter yang akan digunakan. Saat pernyataan ini dijalankan, Python mengikat nama fungsi ke kode di dalam tubuh fungsi, bersama dengan detail lain seperti nama parameter. Namun, tubuh fungsi belum dijalankan pada tahap ini. Baru ketika fungsi dipanggil, parameter akan diikat ke nilai argumen yang diberikan, dan tubuh fungsi akan dieksekusi. Pernyataan `return`, yang mungkin disertai ekspresi, akan menghentikan eksekusi fungsi dan mengembalikan nilai dari ekspresi tersebut (jika ada) sebagai hasil dari pemanggilan fungsi.

Perhatikan, kita tidak perlu mendeklarasikan tipe data parameter. Argumen yang diterima fungsi ini bisa berupa nilai apa saja selama operasi `>=` dan tanda negatif (`-`) berlaku untuknya. Dengan kata lain, fungsi ini secara otomatis mendukung tipe data seperti bilangan bulat atau desimal tanpa perlu penanganan khusus.

Sebagai contoh lain, mari kita ambil perhitungan [[akar kuadrat]] dari bab sebelumnya dan ubah menjadi fungsi:

```python
def sqrt(n):
    guess = 1.0
    while abs(n - guess * guess) > 0.001:
        guess = guess - (guess * guess - n) / (2 * guess)
    return guess
```

Sejauh ini, semua fungsi yang kita lihat hanya punya satu parameter. Tapi, fungsi bisa memiliki lebih dari satu parameter. Misalnya, dalam fungsi `sqrt` di atas, iterasi berhenti ketika nilai `guess` cukup mendekati akar kuadrat sebenarnya dari `n`. Kriteria "cukup dekat" di sini adalah ketika kuadrat `guess` berbeda dari `n` kurang dari 0.001. Kita bisa membuat toleransi ini menjadi parameter tambahan, seperti ini:

```python
def sqrt2(n, tolerance):
    guess = 1.0
    while abs(n - guess * guess) > tolerance:
        guess = guess - (guess * guess - n) / (2 * guess)
    return guess
```

Dengan definisi ini, kita bisa memanggil `sqrt2` dengan dua argumen, misalnya `sqrt2(3, 0.00005)`, yang akan menghitung akar kuadrat dengan toleransi 0.00005.

Oh ya, mungkin kamu ingat sintaks pemanggilan fungsi lain dari Bab 1, Bagian 3.3, seperti:

```python
line.startswith("John")
line.split(",")
line = file.readLine()
```

Ini adalah sintaks untuk memanggil **metode (methode)**, sejenis fungsi khusus di Python yang akan kita pelajari lebih lanjut di Bab 11. Untuk saat ini, cukup tahu bahwa nilai sebelum tanda titik (`.`) bertindak sebagai argumen pertama, dan argumen tambahan (jika ada) ditulis dalam tanda kurung seperti biasa.

Lalu, bagaimana dengan fungsi yang tidak mengembalikan nilai? Fungsi semacam ini biasanya digunakan untuk menghasilkan efek samping, seperti mencetak sesuatu. Contohnya, skrip dari Bab 1 yang menghitung dan menampilkan rata-rata angka dalam file (Contoh 1.3) bisa diubah menjadi fungsi seperti ini:

```python
def printAverageOfFile(fileName):
    total = 0
    count = 0
    file = open(fileName)
    for line in file:
        n = int(line)
        total += n
        count += 1
    print(f"Rata-rata angka dalam {fileName}:")
    print(total / count)
```

Di sini, nama file menjadi parameter fungsi. Dengan desain ini, kita bisa dengan mudah menghitung rata-rata dari beberapa file, seperti:

```python
printAverageOfFile("observations-April")
printAverageOfFile("observations-May")
printAverageOfFile("observations-June")
```

Meskipun mungkin untuk membuat fungsi yang menghasilkan efek samping sekaligus mengembalikan nilai, banyak ahli pemrograman menyarankan agar setiap fungsi punya satu tujuan jelas: entah mengembalikan nilai atau menghasilkan efek samping, tapi tidak keduanya. Dalam buku ini, kita akan berpegang pada prinsip itu.

### 4.2. Fungsi Rekursif

Seperti kebanyakan bahasa pemrograman modern, fungsi di Python bisa bersifat rekursif, artinya fungsi tersebut bisa memanggil dirinya sendiri di dalam tubuhnya. Dengan kata lain, fungsi didefinisikan sebagian berdasarkan dirinya sendiri.

Contoh klasiknya adalah fungsi faktorial. Untuk bilangan bulat positif `n`, faktorial `n` (ditulis `n!`) didefinisikan secara matematis sebagai:

```
n! = n × (n-1) × ... × 2 × 1
```

Tapi, ada juga definisi rekursif yang berbeda tapi menghasilkan hasil sama:

```
n! = 1, jika n = 1
n! = n × (n-1)!, jika tidak
```

Berikut adalah versi Python-nya:

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n-1)
```

Bayangkan kita memanggil `factorial(5)`. Fungsi ini akan memanggil dirinya sendiri berulang kali: `factorial(4)`, lalu `factorial(3)`, `factorial(2)`, dan akhirnya `factorial(1)`. Pada `n = 1`, fungsi langsung mengembalikan 1. Kemudian, pemanggilan rekursif akan selesai dalam urutan terbalik: `factorial(2)` mengembalikan `2 × 1 = 2`, `factorial(3)` mengembalikan `3 × 2 = 6`, `factorial(4)` mengembalikan `4 × 6 = 24`, dan akhirnya `factorial(5)` mengembalikan `5 × 24 = 120`.

Baris `return n * factorial(n-1)` tidak langsung mengembalikan nilai akhir. Sebaliknya, ia **memulai pemanggilan baru** (`factorial(n-1)`) dan menunda perhitungan hingga pemanggilan tersebut selesai. Python tidak bisa menghitung `5 * ...` sekarang karena `factorial(5-1)` adalah pemanggilan fungsi lain. Penghitungan `factorial(5)` menunggu hasil dari `factorial(4)`, dan begitu seterusnya sampai `factorial(1)` menghasilkan nilai `1`.

Fungsi rekursif yang baik memiliki dua ciri utama:
- **Kasus dasar (*basis case*)**: Setidaknya satu kasus didefinisikan tanpa rekursi, memberikan hasil langsung. Dalam faktorial, kasus dasar adalah `n = 1`, yang mengembalikan 1.
- **Kemajuan menuju kasus dasar**: Setiap pemanggilan rekursif harus membawa kita lebih dekat ke kasus dasar. Dalam faktorial, pemanggilan rekursif menggunakan `n-1`, sehingga akhirnya akan mencapai `n = 1` (dengan asumsi `n` adalah bilangan bulat positif).

Kita tidak akan membahas rekursi secara mendalam di buku ini, tapi kita akan menemui fungsi rekursif lagi nanti. Rekursi adalah teknik yang kuat dan sering berguna, jadi kamu mungkin akan menggunakannya banyak dalam perjalanan pemrogramanmu.

### 4.3. Fungsi sebagai Nilai

Di Python, [[nilai fungsi|fungsi bukan sekadar alat, tapi juga nilai]], seperti bilangan atau string. Ketika kita mendefinisikan fungsi, kita mengikat nama ke definisi fungsi tersebut, mirip seperti mengikat variabel ke nilai dengan pernyataan penugasan. Ini membuka banyak kemungkinan menarik.

Pertama, kita bisa mengikat nama lain ke fungsi yang sudah ada. Contohnya:

```python
def square(x):
    return x * x
sq = square
```

Sekarang, `sq` merujuk ke fungsi yang sama dengan `square`. Jadi, memanggil `sq(3)` akan menghasilkan 9, sama seperti `square(3)`.

Lebih menarik lagi, kita bisa meneruskan fungsi sebagai argumen ke fungsi lain. Lihat contoh ini:

```python
def twice(f, a):
    return f(f(a))
```

Fungsi `twice` mengambil sebuah fungsi `f` dan nilai `a`, lalu menerapkan `f` dua kali pada `a`. Misalnya, jika kita panggil `twice(square, 3)` yaitu `twice(f, a)`, Python akan menghitung `square(square(3))` yaitu `f(f(a))`. Karena `square(3) = 9`, maka `square(9) = 81`. Jadi, `twice(square, 3)` menghasilkan 81. Demikian pula, `twice(sqrt, 3)` akan menghitung akar kuadrat dari akar kuadrat 3, atau akar pangkat empat dari 3.

Contoh yang lebih praktis adalah menghitung perkiraan [[turunan]] suatu fungsi. (Bagi yang belum belajar kalkulus: turunan adalah tingkat perubahan suatu fungsi, atau kemiringan kurva pada titik tertentu.) Pertimbangkan sebuah fungsi dengan satu argumen, f(x). Bayangkan sebuah grafik dari f(x) pada arah vertikal, terhadap x pada arah horizontal. Turunan dari fungsi pada nilai tertentu dari x adalah kemiringan kurva pada nilai x tersebut.

![](Pasted%20image%2020250424150342.png)
![[Pasted image 20250424150342.png]]

Fungsi di bawah ini melakukan tugas tersebut. Fungsi mengambil fungsi `f`, titik `x`, dan interval kecil `dx`, lalu menghitung perubahan nilai `f` dibagi panjang interval untuk memperkirakan turunan. 

```python
def derivAt(f, x, dx):
    return (f(x + dx) - f(x)) / dx
```

Misalnya, turunan dari fungsi `square` atau `x²` adalah `2x`, jadi di `x = 3`, turunannya adalah 6. Jika kita panggil `derivAt(square, 3, 0.00001)`, kita akan mendapatkan nilai yang sangat mendekati 6. Artinya, **kemiringan kurva $x^2$** di titik manapun $x$ adalah **2 kali nilai $x$** itu sendiri.

Fungsi ini menghitung pendekatan turunan $f(x)=x^2$ pada $x=3$ dengan dx=0.00001. Turunan fungsi $f(x)$ pada titik $x$, ditulis $f′(x)$, adalah **laju perubahan** fungsi pada titik tersebut, atau kemiringan garis singgung pada kurva $f(x)$ di $x$. Secara matematis, turunan didefinisikan sebagai limit: 
$$f'(x) = \lim_{dx \to 0} \frac{f(x + dx) - f(x)}{dx}​$$

Substitusi ke rumus: 
$$\frac{f(3.00001) - f(3)}{0.00001} = \frac{9.0000600001 - 9}{0.00001}​ $$
$$= \frac{0.0000600001}{0.00001} = 6.00001$$

Dalam Python, sebuah fungsi bahkan bisa mengembalikan fungsi lain sebagai nilai. Sebuah fungsi dapat menjalankan pernyataan definisi fungsi, menciptakan sebuah fungsi baru dan mengikat fungsi tersebut ke sebuah nama, lalu mengembalikan nilai yang terikat pada nama itu. Berikut adalah contohnya. Fungsi `multiplyBy` menerima sebuah angka sebagai parameter dan mengembalikan sebuah fungsi yang mengalikan dengan angka tersebut.

```python
def multiplyBy(n):
    def times(m):
        return m * n
    return times
```

Ingat, definisi fungsi adalah pernyataan yang dapat dijalankan ( *executable statement* ). Di sini, definisi dari `times` dijalankan ketika tubuh dari `multiplyBy` dijalankan. Nilai yang digunakan untuk `n` dalam fungsi baru adalah nilai yang terikat pada `n` saat itu, yaitu nilai dari argumen yang diberikan ke `multiplyBy`. Karena `m` adalah parameter dari fungsi baru tersebut, maka nilainya belum terikat sampai fungsi tersebut dipanggil.

```python
double = multiplyBy(2)
triple = multiplyBy(3)
```

Fungsi `multiplyBy` menerima parameter `n`, yang akan digunakan sebagai pengali tetap. Misalnya, ketika `multiplyBy(2`) dipanggil, `n` diikat ke `2`. Fungsi dalam `times` menerima parameter `m`, yang akan dikalikan dengan `n`. Nilai `n` bukan parameter dari `times`, melainkan variabel dari lingkup luar (`multiplyBy`). Karena `times` mengakses `n`, Python menyimpan nilai `n` untuk digunakan oleh `times` di masa depan. `multiplyBy` tidak menghitung apa pun, ia hanya mengembalikan fungsi `times` sebagai objek. Fungsi `times` yang dikembalikan membawa serta nilai `n` dari lingkup `multiplyBy`. Pada `double = multiplyBy(2)`, `times` dikembalikan dan disimpan dalam `double`. Variabel `double` sekarang adalah fungsi `times` yang menghitung `m*n` dengan `n = 2`. Ketika `double(7)` dipanggil, `m` diikat ke `7`. Fungsi `times` menghitung `m * n = 7 * 2 = 14`.

Sekarang, `double(7)` menghasilkan 14 (karena `7 × 2`), dan `triple(33)` menghasilkan 99 (karena `33 × 3`).

Teknik tersebut adalah contoh kasus dari apa yang biasa disebut dengan *[[partial application]]*, yaitu mengikat sebagian argumen sebuah fungsi untuk menghasilkan fungsi baru dengan argumen lebih sedikit. Berikut adalah versi umumnya:

```python
def partial(f, x):
    def f_x(y):
        return f(x, y)
    return f_x
```

Fungsi `partial` mengambil fungsi dua argumen `f(x, y)` dan nilai untuk `x`, lalu mengembalikan fungsi satu argumen yang "mengunci" `x` pada nilai tertentu. Misalnya, jika `mult` adalah fungsi yang mengalikan dua angka, maka `partial(mult, 2)` sama dengan `multiplyBy(2)`.

Sebagai contoh, kita bisa membuat fungsi yang mengembalikan fungsi turunan. Alih-alih menghitung turunan di satu titik, fungsi ini menghasilkan fungsi baru yang bisa menghitung turunan di titik mana pun:

```python
def deriv(f, dx):
    def d(x):
        return derivAt(f, x, dx)
    return d
```

Kita memanggil `deriv` dengan sebuah fungsi yang memiliki satu argumen, misalnya `square`, dan sebuah angka yang digunakan sebagai ukuran interval. Fungsi baru `d` menggunakan nilai-nilai tersebut untuk `f` dan `dx` dalam pemanggilan `derivAt`, tetapi fungsi baru tersebut tetap merupakan fungsi dengan satu argumen, yaitu `x`. Kita bisa menggunakannya seperti ini:

```python
derivOfSquare = deriv(square, 0.00001)
```

Sekarang, `derivOfSquare(3)` akan menghasilkan nilai mendekati 6, seperti sebelumnya.

Sebuah fungsi yang menerima fungsi lain sebagai argumen, atau mengembalikan sebuah fungsi, atau keduanya, disebut *higher-order function*. Fungsi seperti `twice`, `derivAt`, `partial`, dan `deriv` adalah contohnya.

### 4.4. Ekspresi Lambda

Karena fungsi adalah nilai di Python, adakah cara untuk membuat fungsi langsung dalam sebuah ekspresi? Jawabannya ya, dengan *lambda expression*. Istilah "lambda" berasal dari huruf Yunani λ dan konsep matematika.

Dalam matematika, fungsi yang menambahkan 1 ke argumennya ditulis:

```
λx.x+1
```

Ini berarti "fungsi dari x yang menghasilkan x + 1". Fungsi ini tidak punya nama; ia hanya ada sebagai ekspresi.

Di Python, kita menulisnya sebagai:

```python
lambda x: x + 1
```

Ekspresi lambda bisa diikat ke nama, diteruskan sebagai argumen, atau dikembalikan oleh fungsi, sama seperti fungsi yang didefinisikan dengan `def`. Misalnya, fungsi `square` dari sebelumnya:

```python
def square(x):
    return x * x
```

Bisa ditulis ulang sebagai:

```python
square = lambda x: x * x
```

Kedua definisi ini sama saja dalam praktiknya.

Ekspresi lambda sangat berguna untuk membuat fungsi secara singkat, terutama saat fungsi itu akan diteruskan atau dikembalikan. Contohnya, kita bisa menulis ulang `deriv` dengan lebih ringkas:

```python
def deriv(f, dx):
    return lambda x: derivat(f, x, dx)
```

Kita juga bisa menggunakannya untuk membuat fungsi sementara. Misalnya, untuk menghitung turunan dari `x²` tanpa mendefinisikan `square` terlebih dahulu:

```python
derivOfSquare = deriv(lambda x: x * x, 0.0001)
```

Dalam matematika, kita sering memperlakukan operator (seperti `+`) dan fungsi dua argumen secara bergantian. Tapi di Python, kita tidak bisa langsung meneruskan operator seperti `*` ke *higher-order function*. 

Dalam matematika, kita kadang-kadang menggunakan istilah dan notasi dari **operator biner** dan **fungsi dengan dua argumen** secara bergantian. Misalnya, kita mungkin mengatakan bahwa fungsi $f$ bersifat asosiatif jika: $f(f(x,y),z)=f(x,f(y,z))$. Kita bahkan bisa menuliskan $x f y$ sebagai ganti dari $f(x,y)$, atau menuliskan $∗(x,y)$ sebagai ganti dari $x∗y$. (**Catatan:** kita kadang akan menggunakan kebebasan seperti ini dalam notasi matematika di bab-bab berikutnya). Namun, kita **tidak bisa sebebas itu menggunakan notasi semacam ini di Python**. Misalnya, kita **tidak bisa langsung memberikan operator seperti `*` ke fungsi tingkat tinggi** (higher-order function). Solusinya adalah menggunakan lambda, misalnya `lambda x, y: x * y`.

Kita akan melihat lebih banyak kegunaan ekspresi lambda di bab-bab berikutnya.

**Istilah Baru di Bab Ini**

- Definisi fungsi (function definition)
- Parameter
- Pernyataan `return` (return-statement)
- Fungsi rekursif (recursive function)
- Kasus dasar (*basis case*)
- *Partial application*
- *Higher-order function*
- Ekspresi lambda (lambda expression)

**Latihan**

1. **Untuk yang paham kalkulus**: Cobalah bereksperimen dengan fungsi `deriv` dari bab ini dan fungsi turunan yang dihasilkannya. Gunakan `deriv` pada `square` atau fungsi lain yang turunannya kamu tahu. Coba gunakan nilai `dx` yang semakin kecil, bahkan sangat kecil. Apakah hasilnya semakin mendekati nilai turunan yang benar secara matematis? Jelaskan apa yang kamu amati.

2. Apa yang terjadi jika definisi fungsi menggunakan nama yang tidak didefinisikan di dalamnya? Misalnya:

```python
def f(n):
    return n + a
```

Ini jelas akan gagal jika `a` tidak didefinisikan. Tapi, bagaimana dengan ini?

```python
a = 1
def f(n):
    return n + a
```

Sekarang `f` akan menambahkan 1 ke argumennya. Lalu, bagaimana dengan kasus ini?

```python
a = 1
def f(n):
    return n + a
a = 3
```

Apakah `f` akan menambahkan 1 atau 3? Jika perlu, coba di interpreter Python. Bisakah kamu menjelaskan apa yang terjadi? Lihat lagi halaman pertama bab ini untuk petunjuk.
