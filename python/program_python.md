[Home](../)
[back](./)

## Bab 3: Menyusun Program Python

### 3.1. Pernyataan (Statements)

Setelah mempelajari konsep dasar dan elemen-elemen Python di bab sebelumnya, kini saatnya kita melihat bagaimana elemen-elemen tersebut dapat disusun menjadi struktur yang lebih besar, hingga membentuk program Python yang utuh.

Program Python pada dasarnya adalah rangkaian pernyataan (*statements*). Untuk memahami berbagai jenis pernyataan dalam Python, mari kita tinjau kembali salah satu contoh program dari Bagian 1.2:

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

Program ini terdiri dari beberapa pernyataan. Beberapa di antaranya adalah pernyataan penugasan (*assignment*) dan pernyataan penugasan yang diperbesar (*augmented assignment*), yang masing-masing ditulis pada baris terpisah.

Jika sebuah pernyataan terlalu panjang untuk muat dalam satu baris, Anda bisa memecahnya ke beberapa baris menggunakan karakter garis miring terbalik (`\`) diikuti oleh enter, seperti ini:

```python
z = x * 4 + 4 * x * 3 * y + 6 * x * 2 * y * 2 \
    + 4 * x * y * 3 + y * 4
```

Namun, jika pemisahan baris terjadi di dalam tanda kurung (seperti kurung biasa, kurung siku, atau kurung kurawal), Anda tidak perlu menggunakan garis miring terbalik:

```python
z = round(x ** 4 + 4 * x * 3 * y + 6 * x * 2 * y * 2
          + 4 * x * y * 3 + y * 4)
```

Baris terakhir dari program contoh di atas juga merupakan pernyataan. Dalam hal ini, `print` adalah fungsi bawaan Python. Di contoh tersebut, fungsi `print` menerima argumen berupa bilangan desimal (*floating-point*), tetapi seperti yang kita lihat di Bagian 1.2, `print` juga bisa digunakan untuk menampilkan teks (*string*) atau berbagai tipe data lainnya. Fungsi `print` memang dirancang untuk menangani berbagai jenis data (*overloaded*).

Sebuah ekspresi di Python, jika berdiri sendiri, juga bisa dianggap sebagai pernyataan. Baris terakhir program di atas adalah contohnya. Namun, untuk ekspresi yang sudah kita pelajari sebelumnya, menjadikannya pernyataan tanpa tindakan lebih lanjut biasanya tidak berguna; interpreter Python hanya akan menghitung nilainya tanpa melakukan apa pun dengan hasilnya. Tetapi, beberapa ekspresi memiliki *efek samping* (*side effects*), yaitu dampak tambahan selain menghasilkan nilai, seperti menampilkan sesuatu ke layar.

Beberapa fungsi Python memang dirancang untuk digunakan sebagai pernyataan. Fungsi-fungsi ini tidak menghasilkan nilai (*return value*), melainkan hanya menghasilkan efek samping. Fungsi `print` adalah salah satu contohnya: efek satu-satunya adalah menampilkan nilai ke layar.

Pernyataan penugasan, penugasan yang diperbesar, dan ekspresi yang berdiri sendiri disebut *pernyataan sederhana* (*simple statements*). Sementara itu, baris yang dimulai dengan kata `for` dan tiga baris berikutnya dalam contoh di atas membentuk *pernyataan majemuk* (*compound statement*), yaitu pernyataan yang berisi pernyataan lain di dalamnya:

```python
for line in file:
    n = int(line)
    sum += n
    count += 1
```

Baris pertama dari pernyataan majemuk disebut *header*. Header ini selalu dimulai dengan kata kunci (*keyword*) yang menunjukkan jenis pernyataan majemuk, dan diakhiri dengan tanda titik dua (`:`). Python memiliki sejumlah kata kunci yang digunakan untuk keperluan khusus seperti ini. Dalam contoh di atas, `for` dan `in` adalah kata kunci yang menjadi bagian penting dari struktur header. Karena sifatnya yang khusus, kata kunci seperti ini tidak bisa digunakan sebagai nama variabel, jadi Anda tidak bisa membuat variabel bernama `for` atau `in`.

Baris-baris setelah header, yang disebut *body* pernyataan, harus diindentasi (diberi jarak ke dalam) relatif terhadap header. Indentasi ini adalah bagian penting dari sintaks Python untuk menunjukkan hierarki kode.

Seperti yang sudah kita lihat, program Python juga bisa berisi baris kosong. Baris kosong ini bukan pernyataan dan tidak memengaruhi jalannya program, tetapi ditambahkan untuk memudahkan pembaca memahami kode. Selain itu, semua bahasa pemrograman modern, termasuk Python, mendukung *komentar*. Komentar memungkinkan pemrogram menyisipkan catatan atau penjelasan langsung di dalam kode. Di Python, komentar dimulai dengan tanda pagar (`#`) dan berlanjut hingga akhir baris. Berikut adalah versi program rata-rata angka di atas dengan beberapa komentar:

```python
# Program ini menghitung dan menampilkan rata-rata
# angka dalam file bernama "observations".
# File diasumsikan berisi bilangan bulat, satu per baris.
sum = 0
count = 0

file = open("observations")
for line in file:
    n = int(line)  # Mengubah string angka menjadi bilangan bulat
    sum += n
    count += 1
    
print(sum/count)
```

### 3.2. Kondisional (Conditionals)

Dalam sebuah program, pernyataan biasanya dijalankan secara berurutan, satu demi satu, sesuai urutan kemunculannya. Kami menyebut pola ini sebagai *alur kendali* (*flow of control*) yang berjalan lurus dari satu pernyataan ke pernyataan berikutnya.

Namun, terkadang kita perlu mengubah alur kendali ini. Misalnya, kita mungkin ingin beberapa pernyataan hanya dijalankan jika kondisi tertentu terpenuhi. Untuk keperluan ini, Python menyediakan konstruk yang disebut *kondisional*.

Konstruk kondisional paling dasar di Python adalah pernyataan majemuk yang dimulai dengan kata kunci `if`, atau yang biasa disebut *pernyataan-if*. Bentuk paling sederhana dari pernyataan-if adalah sebagai berikut:

```python
if kondisi:
    pernyataan
```

Contohnya, seperti yang kita lihat di Bagian 1.2:

```python
if name == "John Davis":
    print(email)
```

Kondisi dalam header pernyataan-if biasanya berupa perbandingan, seperti pada contoh di atas. Hasil dari perbandingan adalah nilai bertipe *Boolean*, yang hanya memiliki dua kemungkinan: `True` (benar) atau `False` (salah). Nilai-nilai ini ditulis persis seperti itu di Python. Meskipun dalam beberapa konteks nilai Boolean berperilaku seperti angka 1 (`True`) dan 0 (`False`)—bahkan bisa digunakan dalam operasi aritmatika—fungsi utamanya adalah untuk mengendalikan alur program, terutama dalam pernyataan-if dan pernyataan-while (yang akan kita bahas nanti).

Python memiliki beberapa operator perbandingan. Operator yang menunjukkan "tidak sama dengan" (seperti ≠ dalam matematika) ditulis sebagai `!=`. Operator `<` dan `>` berarti "kurang dari" dan "lebih besar dari", sesuai dengan makna umumnya. Untuk "kurang dari atau sama dengan" (≤) dan "lebih besar dari atau sama dengan" (≥), Python menggunakan `<=` dan `>=`.

Ada juga operator `in`, yang sangat berguna untuk memeriksa keberadaan elemen dalam suatu koleksi. Misalnya, untuk memeriksa apakah sebuah karakter ada dalam string:

```python
if c in "aeiou":
    print("c adalah huruf vokal")
```

Lebih luas lagi, jika kedua operan dari `in` adalah string, operator ini memeriksa apakah operan kiri adalah *substring* (bagian dari string) dari operan kanan, yaitu apakah urutan karakter di operan kiri muncul dalam operan kanan. Kita akan menjelajahi lebih banyak kegunaan operator `in` di bab-bab berikutnya.

Python juga menyediakan operator untuk nilai Boolean: `and`, `or`, dan `not`. Operator `not` adalah operator tunggal (*unary*) yang mengembalikan `False` jika operannya `True`, dan sebaliknya. Operator `and` dan `or` bekerja seperti yang diharapkan, tetapi Python memiliki cara khusus dalam mengevaluasinya.

Untuk ekspresi seperti `A or B`, Python pertama-tama mengevaluasi `A`. Jika `A` bernilai `True`, maka seluruh ekspresi dianggap `True` tanpa perlu mengevaluasi `B`. Jika `A` bernilai `False`, baru Python mengevaluasi `B` untuk menentukan hasil akhir. Operator `and` bekerja serupa: Python hanya mengevaluasi operan kedua jika operan pertama bernilai `False`. Pendekatan ini disebut *short-circuit evaluation* dan bisa sangat berguna.

Perhatikan contoh berikut:

```python
if y != 0 and x / y > 1:
```

Jika `y` bernilai 0, Python akan langsung menyimpulkan bahwa ekspresi keseluruhan bernilai `False` tanpa mencoba menghitung `x / y > 1`. Ini penting karena pembagian oleh nol tidak valid di Python, sama seperti dalam matematika biasa.

Pernyataan-if juga memiliki bentuk yang lebih kompleks untuk menangani situasi yang lebih beragam. Misalnya, jika Anda ingin menjalankan satu set pernyataan ketika kondisi benar dan set lain ketika kondisi salah, Anda bisa menggunakan klausa `else`:

```python
if kondisi:
    pernyataan
else:
    pernyataan
```

Contoh sederhananya:

```python
if a > b:
    print("Saya pilih a")
else:
    print("Saya pilih b")
```

Untuk menangani lebih dari dua kemungkinan, Anda bisa menumpuk pernyataan-if, seperti ini:

```python
if testScore > medianScore:
    print("Di atas rata-rata.")
else:
    if testScore == medianScore:
        print("Rata-rata.")
    else:
        print("Di bawah rata-rata.")
```

Di sini, kita memiliki pernyataan-if yang bersarang (*nested*) di dalam pernyataan-if lain. Bersarang adalah hal yang umum dalam pemrograman, baik untuk pernyataan maupun ekspresi (misalnya, ekspresi di dalam ekspresi lain).

Karena pola seperti di atas sangat sering digunakan, Python menyediakan cara yang lebih ringkas dengan menggunakan klausa `elif` (singkatan dari *else if*):

```python
if kondisi:
    pernyataan
elif kondisi:
    pernyataan
else:
    pernyataan
```

Dengan `elif`, contoh sebelumnya bisa ditulis lebih singkat:

```python
if testScore > medianScore:
    print("Di atas rata-rata.")
elif testScore == medianScore:
    print("Rata-rata.")
else:
    print("Di bawah rata-rata.")
```

Anda bisa menggunakan lebih dari satu klausa `elif` untuk menangani lebih banyak kasus, dan klausa `else` bersifat opsional, baik dengan atau tanpa `elif`. Jadi, bentuk umum pernyataan-if adalah: satu klausa `if`, diikuti oleh nol atau lebih klausa `elif`, dan diakhiri dengan nol atau satu klausa `else`.

### 3.3. Iterasi (Iterations)

Salah satu pola yang sangat umum dalam pemrograman adalah menjalankan sekelompok kode berulang-ulang. Pola ini disebut *iterasi*.

Beberapa iterasi berjalan tanpa henti, setidaknya sampai program dihentikan atau komputer dimatikan. Namun, dalam bab ini, kita akan fokus pada iterasi yang menjalankan kode sebanyak yang diperlukan berdasarkan kondisi tertentu, lalu berhenti.

Mari kita lihat kembali contoh dari Bagian 1.1:

```python
file = open("names")
for line in file:
    if line.startswith("John"):
        print(line)
```

Pernyataan majemuk yang dimulai dengan kata kunci `for` adalah salah satu bentuk iterasi di Python, yang disebut *pernyataan-for*. Dalam contoh ini, pernyataan-for mengulang tubuhnya sebanyak jumlah baris dalam file. Karena buku ini menekankan struktur matematis, iterasi seperti ini—yang melintasi semua elemen dalam suatu urutan, himpunan, atau struktur matematis lainnya—akan menjadi fokus utama kita.

Bentuk umum pernyataan-for adalah:

```python
for nama in ekspresi:
    pernyataan
```

Ekspresi dalam header menyediakan nilai-nilai yang akan diiterasi. Sebagai contoh sederhana, ekspresi tersebut bisa berupa string, yang merupakan urutan karakter:

```python
sentence = "Look at me swimming!"
vowels = 0

for c in sentence:
    if c in "aeiou":
        vowels += 1
        
print("Ada " + str(vowels) + " huruf vokal dalam kalimat itu.")
```

Untuk setiap karakter `c` di dalam kalimat `"Look at me swimming!"`, program akan memeriksa apakah karakter tersebut termasuk dalam huruf vokal **kecil** `'a', 'e', 'i', 'o', 'u'`. Jika iya, maka nilai variabel `vowels` akan ditambah satu. Variabel `vowels` digunakan untuk menghitung jumlah huruf vokal dalam kalimat tersebut.

Ekspresi dalam header harus menghasilkan urutan nilai, baik secara langsung (seperti string) maupun melalui mekanisme lain. Untuk setiap nilai dalam urutan tersebut, Python mengikat nama di header ke nilai tersebut, lalu menjalankan tubuh pernyataan-for.

Pernyataan-for di Python sangat fleksibel dan bisa mengiterasi berbagai jenis data. Beberapa di antaranya adalah nilai komposit yang sudah ada, seperti string. Yang lain adalah urutan nilai yang dihasilkan secara dinamis oleh objek yang disebut *[[iterator]]*. Mari kita lihat kembali contoh ini:

```python
file = open("names")
for line in file:
    if line.startswith("John"):
        print(line)
```

Apa yang sebenarnya terjadi di sini adalah: fungsi `open` mengembalikan sebuah iterator. Pernyataan-for menggunakan iterator ini untuk menghasilkan nilai satu per satu. Setiap kali iterasi berjalan, iterator membaca satu baris dari file, mengembalikannya sebagai string, dan pernyataan-for mengikat string tersebut ke variabel `line` sebelum menjalankan tubuhnya.

Salah satu alat yang sangat berguna untuk iterasi adalah objek *range*. Pemanggilan fungsi `range(n)` menghasilkan objek range yang menghasilkan urutan bilangan bulat dari 0 hingga `n-1` tanpa harus menyimpan seluruh urutan di memori. Penggunaan paling umum dari `range` adalah dalam header pernyataan-for, seperti ini:

```python
for i in range(n):
```

Kode ini akan menjalankan tubuh pernyataan-for sebanyak `n` kali, dengan `i` mengambil nilai berurutan dari 0 hingga `n-1`, berfungsi sebagai penghitung. Berikut adalah contoh yang menampilkan pangkat dua dari 0 hingga 19:

```python
for i in range(20):
    print("2 pangkat " + str(i) + " adalah " + str(2 ** i))
```

Kita akan melihat lebih banyak contoh penggunaan pernyataan-for di bab-bab berikutnya, terutama saat membahas struktur matematis seperti himpunan atau daftar.

Selain pernyataan-for, Python juga memiliki pernyataan majemuk lain untuk iterasi: *pernyataan-while*. Bentuknya adalah:

```python
while kondisi:
    pernyataan
```

Pernyataan-while akan terus menjalankan tubuhnya selama kondisi dalam header bernilai `True`. Secara teknis, Python mengevaluasi kondisi terlebih dahulu. Jika kondisi bernilai `False`, eksekusi langsung melompat ke kode setelah pernyataan-while. Jika `True`, tubuh dijalankan, lalu kondisi dievaluasi kembali, dan proses ini berulang.

Dalam beberapa hal, pernyataan-while lebih mendasar daripada pernyataan-for karena setiap iterasi yang bisa dilakukan dengan `for` juga bisa dilakukan dengan `while`, meskipun mungkin lebih rumit. Mari kita bandingkan. Ingat contoh ini:

```python
for i in range(20):
    print("2 pangkat " + str(i) + " adalah " + str(2 ** i))
```

Berikut adalah versi yang sama menggunakan pernyataan-while:

```python
i = 0
while i < 20:
    print("2 pangkat " + str(i) + " adalah " + str(2 ** i))
    i += 1
```

Dalam versi `for`, seluruh mekanisme iterasi (inisialisasi, pengecekan, dan penambahan penghitung) ditangani dalam satu baris. Dalam versi `while`, kita perlu tiga baris: satu untuk menginisialisasi `i`, satu untuk menambah `i`, dan satu untuk memeriksa kondisi penghentian.

Pernyataan-while juga sering digunakan dalam situasi lain, misalnya untuk membaca baris demi baris dari file. Python menyediakan fungsi `readline` (tepatnya, sebuah *metode*, yang akan kita pelajari nanti) untuk membaca satu baris dari file:

```python
line = file.readline()
```

Setiap kali dipanggil, `readline` mengembalikan baris berikutnya dari file sebagai string. Jika tidak ada lagi baris, ia mengembalikan string kosong (`""`). Untuk memproses semua baris dalam file, kita bisa menggunakan pola seperti ini:

```python
line = file.readline()
while line != "":
    # Lakukan sesuatu dengan line
    line = file.readline()
```

Pola ini mencakup inisialisasi (panggilan pertama ke `readline`), pengecekan kondisi, dan langkah untuk maju ke baris berikutnya. Namun, seperti yang sudah kita lihat, pernyataan-for sering kali lebih sederhana untuk kasus ini:

```python
for line in file:
    # Lakukan sesuatu dengan line
```

Jadi, jika Anda bisa dengan mudah mengidentifikasi urutan atau koleksi yang akan diiterasi, pernyataan-for biasanya adalah pilihan yang lebih praktis. Namun, ada kasus di mana pernyataan-while lebih cocok karena tidak ada urutan yang jelas untuk diiterasi.

Sebagai contoh, berikut adalah program yang menghitung akar kuadrat sebuah angka menggunakan *Metode Newton*. Misalkan angka yang akan dihitung akarnya ada di variabel `n` (diasumsikan tidak negatif), dan kita ingin menyimpan hasil perkiraan akar kuadratnya di variabel `root`. Fungsi `abs` digunakan untuk menghitung nilai absolut:

```python
guess = 1.0
while abs(n - guess * guess) > 0.001:
    guess = guess - (guess * guess - n) / (2 * guess)
root = guess
```

Jika Anda pernah mempelajari kalkulus, Anda mungkin bisa memahami bagaimana Metode Newton bekerja: setiap iterasi membuat `guess * guess` semakin mendekati `n` hingga perbedaan antara keduanya cukup kecil (dalam hal ini, kurang dari 0.001). Yang menarik, iterasi ini tidak bergantung pada urutan nilai yang sudah ada sebelumnya, melainkan pada perhitungan dinamis dari nilai `guess` di setiap langkah.

**Istilah Penting dalam Bab Ini**

- Pernyataan (*statement*)
- Efek samping (*side effect*)
- Pernyataan sederhana (*simple statement*)
- Pernyataan majemuk (*compound statement*)
- Header
- Tubuh (*body*)
- Kata kunci (*keyword*)
- Komentar (*comment*)
- Alur kendali (*flow of control*)
- Kondisional (*conditional*)
- Pernyataan-if (*if-statement*)
- Boolean
- Substring
- Bersarang (*nesting*)
- Iterasi (*iteration*)
- Pernyataan-for (*for-statement*)
- Iterator
- Pernyataan-while (*while-statement*)

**Latihan**

1. Tulis program yang menghasilkan grafik batang berdasarkan data dari file bernama "data". File ini berisi bilangan bulat tidak negatif, satu angka per baris. Keluaran program Anda harus menyerupai contoh berikut (misalnya, untuk file yang berisi angka 7, 15, dan 11):

```
####### 7 
############### 15 
########### 11
```

2. Modifikasi program dari latihan sebelumnya agar memberlakukan panjang maksimum untuk batang. Jika sebuah angka dalam file lebih besar dari 25, program hanya akan menampilkan batang sepanjang 25. Contoh keluaran dengan data berbeda akan terlihat seperti ini:

```
####### 7 
######################### 25 
######################### 283
########### 11
```

3. Modifikasi lagi program dari latihan sebelumnya. Jika sebuah angka dalam file lebih besar dari 25, tampilkan batang sepanjang 25, tetapi tambahkan tanda elipsis ("//") di tengah batang, seperti ini:

```
####### 7
######################### 25
###########/ /########### 283
########### 11
```

4. Lakukan eksperimen dengan program akar kuadrat dari Bagian 3.3. Tambahkan pernyataan `print` di dalam tubuh pernyataan-while untuk menampilkan nilai `guess`. Amati berapa lama iterasi membutuhkan waktu untuk konvergen dengan berbagai nilai `n` dan tebakan awal yang berbeda. Apa yang terjadi jika `n` adalah bilangan negatif?
5. Baris pertama dalam program akar kuadrat adalah:

```python
guess = 1.0
```

Apa yang terjadi jika Anda mengubahnya menjadi:

```python
guess = 1
```

Coba jalankan programnya dan jelaskan apa yang Anda amati.

6. Jika Anda pernah mempelajari kalkulus, coba jelaskan cara kerja program akar kuadrat. (Petunjuk: Kita sedang mencari solusi `x` untuk persamaan `x^2 = n`, atau `x^2 - n = 0`, di mana `n` adalah konstanta. Turunan dari `x^2 - n` adalah `2x`. Gambarkan sketsa untuk membantu memahami.)

[back](./)

