[Home](../)

[back](./)

## Bab 11: Objek

### 11.1. Objek dalam Program

Istilah “objek” telah kita gunakan di bab-bab sebelumnya, tetapi belum kita definisikan secara jelas. Dalam dunia pemrograman, istilah ini memiliki makna spesifik yang diterima secara luas, meskipun detail definisi dan terminologinya dapat bervariasi antar penulis atau bahasa pemrograman. Di sini, kami akan menyajikan definisi dan istilah yang sederhana namun umum digunakan di kalangan pemrogram, khususnya yang sesuai dengan cara Python menangani objek.

Objek adalah kumpulan data yang biasanya memiliki sejumlah **atribut** (*attibutes*), yaitu properti yang diberi nama, mirip seperti kolom dalam tabel basis data relasional (lihat Bagian 10.5). Misalnya, sebuah objek yang merepresentasikan seseorang mungkin memiliki atribut seperti “nama”, “alamat”, dan “departemen”. Dalam sebuah program, objek sering kali mencerminkan entitas di dunia nyata, dan atribut-atributnya adalah karakteristik dari entitas tersebut.

Dengan demikian, dalam bahasa pemrograman, objek adalah salah satu jenis wadah data, tetapi berbeda dari struktur seperti daftar atau kamus karena elemen datanya diidentifikasi berdasarkan nama, bukan posisi atau kunci. Objek biasanya bersifat **mutable**, artinya nilai atributnya dapat diubah. Contohnya, sebuah program mungkin memungkinkan atribut “alamat” pada objek seseorang diperbarui. Kumpulan nilai dari semua atribut data sebuah objek pada suatu waktu disebut **keadaan** (*state*) objek. Jika sebuah objek mutable, keadaannya dapat berubah seiring waktu.

Selain atribut yang menyimpan data, sebuah objek juga memiliki atribut berupa operasi yang disebut **metode** (*methode*). Metode adalah fungsi yang “milik” objek tersebut dan biasanya bekerja dengan data yang ada di dalamnya. Metode dari objek yang berbeda, seperti halnya atribut datanya, mungkin memiliki nama yang sama tetapi dengan makna dan implementasi yang berbeda. Fakta ini adalah inti dari **pemrograman berorientasi objek**, yang akan kita jelajahi lebih lanjut di Bagian 11.4.

Dalam kebanyakan bahasa pemrograman, sebuah objek memiliki **tipe** tertentu atau termasuk dalam **kelas** tertentu. Bahasa pemrograman berorientasi objek menyediakan cara bagi pemrogram untuk mendefinisikan kelas mereka sendiri. Tipe atau kelas sebuah objek menentukan atribut apa saja—baik data maupun metode—yang dimiliki oleh objek tersebut.

Kita dapat membayangkan sebuah objek sebagai pemetaan dari nama atribut ke nilai, serupa dengan tuple dalam basis data relasional yang memetakan nama kolom ke nilai (lihat Bagian 5.3). Namun, sebaliknya, kita juga bisa melihat atribut sebuah kelas sebagai pemetaan dari objek kelas tersebut ke nilai tertentu. Misalnya, atribut “nama” dapat memetakan sebuah objek “seseorang” ke sebuah string yang berisi nama orang tersebut. Jika program kita membutuhkan pemetaan dari objek “seseorang” ke nama mereka, kita telah melihat dua pendekatan sebelumnya (Bagian 9.4): kita bisa membuat fungsi yang menerima objek “seseorang” sebagai parameter dan mengembalikan nama, atau membuat struktur data seperti kamus Python yang menggunakan objek “seseorang” sebagai kunci untuk menghasilkan nama. Sekarang, kita memiliki opsi ketiga: menyimpan nama sebagai atribut dari objek “seseorang” itu sendiri.

Namun, objek bukan sekadar kumpulan atribut. Dalam bahasa pemrograman pada umumnya, setiap objek memiliki **identitas** unik yang hanya dimiliki oleh objek tersebut. Identitas ini tidak pernah berubah, meskipun objeknya mutable. Di sisi lain, dua objek bisa memiliki tipe atau kelas yang sama, dengan semua atribut dan keadaan yang identik, tetapi tetap dibedakan berdasarkan identitasnya. (Biasanya, interpreter atau kompiler bahasa pemrograman menggunakan lokasi memori objek sebagai identitasnya.)

Dalam Python (dan banyak bahasa lain), sintaks untuk mengakses atribut sebuah objek adalah **objek.atribut**. Misalnya, jika **bos** adalah objek “seseorang”, maka **bos.nama** akan mengakses atribut “nama” dari objek tersebut.

Untuk metode, **objek.metode** adalah sebuah fungsi. Dalam Python, sintaks untuk memanggil metode adalah **objek.metode(argumen)**. Saat Python menjalankan panggilan ini, objek itu sendiri secara otomatis diteruskan sebagai salah satu argumen ke fungsi tersebut (kita akan lihat caranya di Bagian 11.2). Kita sering menyebutnya sebagai “menerapkan metode pada objek”, dengan argumen tambahan diberikan dalam tanda kurung.

Metode biasanya bekerja dengan atau memanipulasi atribut data objek. Misalnya, pemanggilan **bos.ubahAlamat(alamat)** mungkin akan mengubah atribut “alamat” dari **bos** menjadi **alamat** yang baru, sedangkan **bos.labelAlamat()** mungkin menghasilkan string yang berisi atribut data **bos** dalam format yang cocok untuk dicetak sebagai label alamat. Perhatikan bahwa dalam kasus terakhir, pemanggilan metode tidak memerlukan argumen tambahan, yang itu tidaklah aneh.

### 11.2. Mendefinisikan Kelas

Salah satu ciri utama bahasa pemrograman berorientasi objek adalah kemampuan pemrogram untuk mendefinisikan **kelas** (*class*) mereka sendiri. Kami akan menunjukkan bagaimana ini dilakukan dalam Python.

Definisi kelas adalah pernyataan majemuk yang dimulai dengan kepala seperti ini:

```python
class NamaKelas:
```

Bagian tubuh (*body*) dari definisi kelas berisi definisi fungsi yang menjadi metode kelas, dan mungkin juga pernyataan lain.

Saat definisi kelas dijalankan, Python secara otomatis menciptakan sebuah fungsi untuk membuat objek dari kelas tersebut; objek-objek ini disebut **instans** (*instances*) dari kelas. Fungsi ini disebut **konstruktor** (*constructor*) kelas, dan namanya sama dengan nama kelas.[^1]

Setiap instans dari sebuah kelas memiliki identitas yang berbeda. Operator biner `is` digunakan untuk membandingkan identitas dua objek; ekspresi seperti `a is b` bernilai **True** jika **a** dan **b** adalah objek yang sama, dan **False** jika tidak. Operator `is not` memiliki makna sebaliknya.

Definisi kelas dapat menyertakan metode khusus bernama `__init__`, yang digunakan untuk menginisialisasi objek yang baru dibuat. Ketika konstruktor dipanggil, ia pertama-tama membuat objek, lalu memanggil metode `__init__` jika ada. Fitur ini sangat berguna sehingga hampir semua kelas yang dibuat oleh pemrogram memiliki metode `__init__`.

Konstruktor meneruskan objek yang baru dibuat ke metode `__init__` sebagai argumen pertama. Jika konstruktor dipanggil dengan argumen tambahan, argumen tersebut juga diteruskan ke `__init__`.

Berikut adalah contoh sederhana definisi kelas:

```python
class Orang:

    def __init__(self, nama, dept, alamat):
        self.nama = nama
        self.departemen = dept
        self.alamat = alamat
```

Kode ini mendefinisikan kelas yang konstruktornya menerima tiga argumen: **nama**, **alamat**, dan **dept** (mungkin semuanya string). Konstruktor memanggil metode `__init__` dengan empat argumen: objek yang baru dibuat (disebut **self**) diikuti oleh tiga argumen yang diberikan. Dalam Python, **self** bukanlah kata kunci, tetapi merupakan konvensi umum di kalangan pemrogram Python untuk merujuk pada objek itu sendiri. Konvensi lain adalah menggunakan huruf kapital untuk nama kelas yang didefinisikan oleh pemrogram, seperti **Orang**.

Metode `__init__` dalam contoh ini mengatur nilai atribut data dari objek **Orang** berdasarkan argumen yang diterima; ini adalah tugas umum untuk metode `__init__`.

Dalam contoh ini, nama atribut seperti **alamat** sama dengan nama parameter di `__init__`. Tidak ada ambiguitas karena Python membedakan konteksnya. Setiap kelas memiliki **ruang nama** (*name space*) sendiri, yaitu pemetaan dari nama ke entitas yang terkait, seperti atribut data atau metode.[^2] Ruang nama kelas berisi nama-nama yang didefinisikan dalam tubuh kelas. Demikian pula, setiap fungsi (termasuk metode) memiliki ruang nama sendiri yang berisi parameter dan variabel lokal. Ruang nama ini terpisah dari ruang nama “global” yang berisi nama-nama seperti variabel dan fungsi yang didefinisikan di luar kelas atau fungsi.

Dalam pernyataan seperti `self.alamat = alamat`, operator titik (**.**) mencari atribut **alamat** dalam ruang nama kelas **Orang** (karena **self** adalah objek **Orang**). Sementara itu, **alamat** di sisi kanan pernyataan merujuk pada parameter dalam ruang nama `__init__`. Kedua “alamat” ini merujuk pada hal yang berbeda, seolah-olah pemrogram menggunakan nama yang berbeda.

Sekarang, misalkan kita membuat objek **Orang** seperti ini:

```python
bos = Orang("Malone", "IT", "127 Spring")
```

Konstruktor dipanggil, `__init__` dijalankan, dan nilai seperti **bos.nama** akan menjadi “Malone”.

Untuk mendefinisikan metode biasa dari sebuah kelas, kita menulis definisi fungsi lain dalam tubuh definisi kelas, seperti ini:

```python
class Orang:
    def __init__(self, nama, dept, alamat):
        self.nama = nama
        self.departemen = dept
        self.alamat = alamat
        
    def labelAlamat(self):
        return self.nama + "\n" \
        + self.departemen + " Departemen\n" \
        + self.alamat
```

Untuk menggunakan metode **labelAlamat**, kita menerapkannya pada objek **Orang**, misalnya:

```python
keBos = bos.labelAlamat()
```

Objek **bos** secara otomatis diteruskan sebagai parameter **self** ke **labelAlamat**; dalam contoh ini, tidak ada argumen tambahan. Seperti pada `__init__`, menggunakan **self** sebagai nama parameter pertama adalah konvensi, bukan keharusan.

Program yang sama mungkin mendefinisikan kelas lain, misalnya **Bangunan**, dengan atribut yang berbeda; contohnya, sebuah **Bangunan** mungkin memiliki nama dan alamat tetapi tidak memiliki departemen. **Bangunan** juga mungkin memiliki metode yang tidak dimiliki **Orang**, dan sebaliknya. Bahkan, **Bangunan** bisa memiliki metode **labelAlamat**, tetapi implementasinya mungkin berbeda dari yang ada di **Orang**. Tidak akan ada kebingungan karena setiap kelas memiliki ruang nama sendiri.

### 11.3. Pewarisan dan Hierarki Kelas

Fitur penting dari bahasa pemrograman berorientasi objek adalah **pewarisan** (*inheritance*), yang memungkinkan pemrogram membuat kelas baru berdasarkan kelas yang sudah ada, biasanya dengan menambahkan fitur baru. Sekali lagi, kita akan menggunakan Python untuk mengilustrasikan konsep ini.

Misalkan kita ingin mendefinisikan kelas bernama **Pelanggan**. Objek **Pelanggan** mirip dengan objek **Orang**, tetapi memiliki atribut tambahan: perusahaan yang diwakili oleh pelanggan tersebut.

Kita bisa mendefinisikan kelas ini dari awal, mirip dengan definisi **Orang**, tetapi dengan metode `__init__` yang menerima argumen tambahan dan mengatur atribut tambahan, seperti ini:

```python
class Pelanggan:

    def __init__(self, nama, perusahaan, dept, alamat):
        self.nama = nama
        self.perusahaan = perusahaan
        self.departemen = dept
        self.alamat = alamat
```

Namun, dengan pewarisan, kita dapat memanfaatkan definisi **Orang** yang sudah ada dengan merujuknya di kepala definisi kelas baru:

```python
class Pelanggan(Orang):
```

Dengan ini, kita mengatakan bahwa **Pelanggan** **mewarisi** dari **Orang**. **Pelanggan** adalah **subkelas** dari **Orang**, dan **Orang** adalah **superclass** dari **Pelanggan**.

Dalam metode `__init__` dari **Pelanggan**, kita memanggil `__init__` dari **Orang** untuk menangani inisialisasi atribut yang sama, lalu menambahkan inisialisasi untuk atribut spesifik **Pelanggan**. Untuk memanggil `__init__` dari **Orang**, kita menggunakan sintaks **Orang.__init__**, dengan memberikan objek yang baru dibuat dan argumen yang diharapkan.[^3] Berikut adalah contohnya:

```python
class Pelanggan(Orang):

    def __init__(self, nama, perusahaan, dept, alamat):
        Orang.__init__(self, nama, dept, alamat)
        self.perusahaan = perusahaan
```

Dengan ini, objek **Pelanggan** memiliki atribut data **perusahaan** dan semua atribut dari **Orang**, termasuk metode seperti **labelAlamat**, yang bekerja sama seperti pada objek **Orang**.

Namun, misalkan kita ingin metode **labelAlamat** pada **Pelanggan** menghasilkan output yang berbeda, misalnya menyertakan nama perusahaan. Kita dapat **mengganti** (*override*) metode ini dalam definisi **Pelanggan** dengan menambahkan definisi baru setelah `__init__`:

```python
def labelAlamat(self):
    return self.nama + "\n" \
    + self.perusahaan + ", " \
    + self.departemen + " Departemen\n" \
    + self.alamat
```

Dalam Python, setiap data adalah objek. Semua tipe bawaan, seperti **int**, **list**, dan **set**, sebenarnya adalah kelas. Fungsi seperti **int** atau **list**, yang kita sebut sebagai fungsi “konversi tipe”, sebenarnya adalah konstruktor untuk kelas-kelas tersebut.

Ada kelas yang lebih umum daripada yang lain, yaitu **object**. Instans dari **object** tidak memiliki properti khusus kecuali sebagai objek. Semua tipe bawaan Python mewarisi dari **object**. Begitu pula kelas yang didefinisikan oleh pemrogram tanpa superclass eksplisit, seperti **Orang**.

Setiap pemanggilan ke konstruktor **object()**, yang tidak menerima argumen, menghasilkan objek yang dijamin berbeda dari setiap objek lain dalam lingkungan Python. Objek seperti ini memiliki kegunaan praktis. Misalnya, ingat definisi fungsi generator **zip** dari Bagian 7.5:

```python
def zip(X, Y):
    it = iter(Y)
    for x in X:
        y = next(it, None)
        if y == None:
            return
        else:
            yield(x, y)
```

Di sini, kita menggunakan **None** sebagai penanda akhir untuk **next** ketika iterator **it** habis. Namun, ini bermasalah jika **None** bisa menjadi elemen dalam **Y**. Sekarang, kita bisa menulis versi **zip** yang lebih aman menggunakan **object()**:

```python
def zip(X, Y):
    it = iter(Y)
    penandaAkhir = object()
    for x in X:
        y = next(it, penandaAkhir)
        if y is penandaAkhir:
            return
        else:
            yield(x, y)
```

Tes `y is penandaAkhir` akan selalu **False** untuk elemen **Y**, bahkan untuk objek lain yang dibuat oleh **object()**, sehingga versi **zip** ini benar-benar umum dan aman.

Pemrogram biasanya menggunakan pewarisan untuk membuat subkelas yang lebih spesifik daripada superclass-nya. Misalnya, **Orang** adalah kategori umum, dan **Pelanggan** adalah jenis **Orang** yang lebih spesifik. Program yang sama mungkin mendefinisikan kelas untuk jenis **Orang** lain, seperti **Pegawai**, yang juga mewarisi dari **Orang**. Selanjutnya, **Pegawai** bisa memiliki subkelas seperti **PegawaiPerJam** dan **PegawaiGajian**, masing-masing dengan atribut seperti **tarifPerJam** atau **gaji**.

Kelas **Bangunan** mungkin memiliki subkelas seperti **Kantor**, **Laboratorium**, dan **Toko**. Dengan demikian, kelas-kelas dalam program membentuk hierarki:

```
object
  tipe bawaan
  Orang
    Pelanggan
    Pegawai
      PegawaiPerJam
      PegawaiGajian
  Bangunan
    Kantor
    Laboratorium
    Toko
  kelas lain yang didefinisikan oleh pemrogram
```

Python menggunakan hierarki kelas untuk menemukan atribut objek, baik atribut data maupun metode. Misalnya, jika **peg** adalah instans dari **PegawaiGajian** dan program merujuk ke **peg.atribut**, Python akan mencari **atribut** di ruang nama **PegawaiGajian**. Jika tidak ditemukan, Python akan mencari di **Pegawai**, lalu ke atas hierarki hingga **object**, menggunakan ikatan pertama yang ditemukan.

### 11.4. Pemrograman Berorientasi Objek

Pemrograman berorientasi objek adalah gaya pemrograman yang sangat penting dalam pengembangan perangkat lunak modern. Topik ini cukup kompleks dan pembahasan menyeluruh berada di luar cakupan buku ini, tetapi di sini kita akan memperkenalkan konsep dasar yang relevan dengan materi yang telah dibahas.

Dalam pemrograman berorientasi objek, sebagian besar atau semua data utama dalam program disimpan dalam instans dari kelas yang didefinisikan oleh pemrogram. Setiap kelas mendefinisikan implementasi dari jenis objek tertentu, biasanya dalam bentuk variabel dan struktur data tingkat rendah yang menjadi atribut data kelas. Definisi kelas juga mencakup operasi pada objek, dalam bentuk kode yang bekerja dengan atribut data; operasi ini adalah metode kelas. Salah satu keuntungan pemrograman berorientasi objek adalah bahwa definisi kelas mengelompokkan data dan metode yang beroperasi pada data tersebut secara rapi.

Keuntungan lain adalah bahwa definisi kelas dapat mengisolasi keputusan implementasi dari sisa program. Misalnya, bayangkan kita menulis program yang memerlukan multiset. Kita bisa mendefinisikan kelas **Multiset** dengan metode untuk operasi seperti **sum** dan **count** (lihat Latihan 1). Struktur data yang menyimpan elemen multiset akan menjadi atribut data kelas, dan metode akan bekerja dengan atribut ini.

Seperti yang kita lihat di Bagian 9.5, ada setidaknya dua cara masuk akal untuk mengimplementasikan multiset di Python: menggunakan daftar atau kamus. Jika sisa program mengakses atribut data **Multiset** secara langsung, kode yang melakukannya akan berbeda tergantung pada implementasi yang dipilih. Namun, jika akses hanya dilakukan melalui metode kelas, hanya kode dalam tubuh metode yang bergantung pada implementasi. Kita bahkan bisa mengubah implementasi (misalnya, dari kamus ke daftar) tanpa mengubah kode di luar kelas, hanya dengan memperbarui tubuh metode.

Sebagian besar bahasa pemrograman berorientasi objek memungkinkan pemrogram untuk menandai atribut sebagai **pribadi**, artinya hanya dapat diakses dari dalam definisi kelas. Tubuh metode kelas dapat mengakses atribut pribadi, tetapi kode di luar kelas tidak bisa. Dalam Python, atribut dibuat pribadi dengan memberi nama yang diawali (tetapi tidak diakhiri) dengan dua garis bawah.[^4]

Jika semua atribut data sebuah kelas bersifat pribadi, satu-satunya cara untuk mengakses instans kelas dari sisa program adalah melalui metode. Pemrogram memiliki kebebasan penuh untuk mengubah kumpulan atribut data dan cara mereka merepresentasikan keadaan objek. Selama kumpulan metode dan maknanya tetap sama, kode yang menggunakan kelas tidak perlu diubah, meskipun perubahan pada atribut data sangat besar; hanya tubuh metode yang perlu diperbarui.

Studi kasus berikut akan mengilustrasikan ide-ide ini.

### 11.5. Studi Kasus: Rata-rata Bergerak

Sebagai studi kasus, mari kita kembangkan definisi kelas untuk mengimplementasikan **rata-rata bergerak** (*moving average*) dari aliran data. Meskipun masalah ini relatif sederhana, kita akan menggunakannya untuk menunjukkan proses berpikir seorang pemrogram berpengalaman dalam merancang kelas menggunakan pendekatan berorientasi objek.

Rata-rata bergerak dari aliran angka (setidaknya jenis yang akan kita bahas di sini) adalah rata-rata dari **n** angka terbaru untuk beberapa **n** tetap. Biasanya, data dalam rata-rata bergerak adalah **deret waktu** (*time series*), yaitu urutan nilai yang diambil pada interval waktu yang sama. Rata-rata bergerak membantu menghaluskan data, meminimalkan efek fluktuasi acak dan kesalahan pengukuran. Misalnya, di Amerika Serikat, statistik ekonomi seperti klaim pengangguran atau pembangunan perumahan sering dilaporkan setiap minggu atau bulan, baik sebagai angka saat ini maupun sebagai rata-rata bergerak selama periode seperti empat minggu atau tiga bulan. Beberapa ekonom menganggap rata-rata bergerak lebih bermakna.

Data suhu yang diplot dengan lingkaran hitam pada Gambar 1.1  adalah contoh deret waktu. Gambar 11.1 menunjukkan data yang sama dengan rata-rata bergerak ditampilkan sebagai garis putus-putus; di sini **n** adalah 4. Perhatikan bahwa rata-rata bergerak tidak ditampilkan sampai ada setidaknya **n** titik data. Juga, rata-rata bergerak tampak tertinggal dari titik data; ini karena rata-rata bergerak pada setiap hari adalah rata-rata dari data hari itu dan **n-1** hari sebelumnya. (Ada jenis rata-rata bergerak lain yang menggunakan jumlah titik data yang sama sebelum dan sesudah hari tersebut.)

**Gambar 11.1. Suhu selama satu bulan, dengan rata-rata bergerak**

![](attachment/Pasted%20image%2020250512134859.png)

Mari kita definisikan kelas Python untuk rata-rata bergerak. Kita mulai dengan memutuskan operasi apa yang diperlukan. Kita memutuskan bahwa kita memerlukan metode berikut:
- **Konstruktor**: Karena program mungkin memerlukan beberapa rata-rata bergerak dengan jumlah nilai berbeda, kita jadikan jumlah nilai sebagai parameter konstruktor.
- **Metode untuk menambahkan nilai** ke urutan.
- **Metode untuk mengembalikan nilai saat ini** dari rata-rata bergerak.

Dengan demikian, definisi kelas akan terlihat seperti ini secara garis besar:

```python
class RataRataBergerak:

    def __init__(self, nTitik):
        ...
    def tambah(self, nilaiBaru):
        ...
    def nilai(self):
        ...
```

Berikut adalah kode sederhana yang menggunakan kelas **RataRataBergerak**. Fungsi generator **halus** mengiterasi aliran data dan menghasilkan aliran kedua, yaitu rata-rata bergerak. Jumlah titik dalam rata-rata bergerak adalah parameter kedua dari **halus**.

```python
def halus(data, nTitik):
    rata = RataRataBergerak(nTitik)
    for nilai in data:
        rata.tambah(nilai)
        yield rata.nilai()
```

Sebelum mengisi tubuh metode dari kelas **RataRataBergerak**, kita perlu memutuskan representasi data yang akan digunakan.

Secara konseptual, data yang masuk adalah urutan; kita akan memberikan nilai data ke objek **RataRataBergerak** melalui serangkaian pemanggilan ke metode **tambah**. Sebagai data yang disimpan oleh objek, nilai-nilai ini akan menjadi urutan yang dapat diubah, sehingga daftar Python adalah pilihan yang jelas untuk menyimpannya.

Haruskah kita menyimpan semua nilai data? Jika ya, daftar akan terus bertambah tanpa batas. Ini mungkin tidak menjadi masalah dalam banyak kasus, tetapi kode kita bisa digunakan dalam program yang berjalan sangat lama. Merupakan praktik baik untuk menghindari penggunaan memori yang terus bertambah tanpa batas jika memungkinkan, dan kita hanya perlu **n** nilai data terbaru. Jadi, kita akan merencanakan untuk menyimpan hanya **n** nilai paling banyak.

Berikut adalah pertanyaan yang perlu segera dijawab: rata-rata bergerak akan terdefinisi dengan baik setelah **n** nilai ditambahkan, tetapi apa yang terjadi sebelum itu? Kita bisa mendefinisikan rata-rata bergerak sebagai rata-rata dari jumlah titik yang ada jika kurang dari **n**, tetapi apa yang terjadi jika belum ada titik sama sekali? Untuk saat ini, kita asumsikan bahwa rata-rata bergerak tidak terdefinisi sampai ada setidaknya **n** titik data.

Kemudian, kita akan menggunakan atribut data untuk menyimpan urutan hingga **n** titik data; atribut ini akan berupa daftar, yang awalnya kosong. Kita beri nama atribut `__titik`; dua garis bawah di awal menjadikannya pribadi untuk kelas. Kita juga perlu menyimpan nilai **n**; kita simpan sebagai atribut pribadi `__nTitik`. Maka metode `__init__` terlihat seperti ini:

```python
def __init__(self, nTitik):
    self.__titik = []
    self.__nTitik = nTitik
```

Untuk mengimplementasikan metode **tambah**, kita menghapus nilai dari depan daftar jika sudah berisi **n** nilai, lalu menambahkan nilai baru di akhir daftar.

![](attachment/Pasted%20image%2020250512135127.png)

Berikut adalah kode paling sederhana untuk melakukan kedua perubahan tersebut. Perhatikan bahwa setiap pernyataan penugasan menciptakan daftar baru.

```python
def tambah(self, nilaiBaru):
    if len(self.__titik) == self.__nTitik:
        self.__titik = self.__titik[:]
    self.__titik = self.__titik + [nilaiBaru]
```

Namun, lebih efisien untuk memodifikasi daftar di tempat jika memungkinkan, dan kita bisa menggunakan metode **append** daftar alih-alih konkatenasi untuk menambahkan nilai baru. Python juga memiliki metode `pop(i)` untuk menghapus elemen di posisi `i`. Menggunakan **append** dan **pop**, metode **tambah** menjadi:

```python
def tambah(self, nilaiBaru):
    if len(self.__titik) == self.__nTitik:
        self.__titik.pop(0)
    self.__titik.append(nilaiBaru)
```

Kita bisa menyederhanakan kode ini dengan membuat alias untuk **self.__titik**. Ingat (lihat Bagian 6.3) bahwa alias **titik** merujuk pada objek daftar yang sama seperti **self.__titik**, sehingga memodifikasi **titik** juga memodifikasi **self.__titik**.

```python
def tambah(self, nilaiBaru):
    titik = self.__titik
    if len(titik) > self.__nTitik:
        titik.pop(0)
    titik.append(nilaiBaru)
```

Versi awal metode **nilai** mungkin terlihat seperti ini. Kita mengembalikan **None** jika rata-rata bergerak tidak terdefinisi; kode yang menggunakan kelas harus menguji **None** dan menangani kasus ini.

```python
def nilai(self):
    titik = self.__titik
    panjang = len(titik)
    if panjang == self.__nTitik:
        return sum(titik) / panjang
    else:
        return None
```

Sekarang perhatikan fakta menarik: kode ini sebagian besar akan bekerja dengan baik jika **panjang** kurang dari **self.__nTitik**, selama **panjang** tidak nol. Dalam kasus ini, kita akan mengembalikan rata-rata dari nilai yang lebih sedikit dari **n**, yang mungkin berguna untuk beberapa tujuan.

```python
def nilai(self):
    titik = self.__titik
    panjang = len(titik)
    if panjang > 0:
        return sum(titik) / panjang
    else:
        return None
```

Gambar 11.2 adalah versi dari Gambar 11.1 dengan rata-rata bergerak yang ditampilkan sesuai definisi yang diperluas ini.

**Gambar 11.2 Temperatur dengan definisi rata-rata bergerak yang diperluas.**

![](attachment/Pasted%20image%2020250512135234.png)

Mari kita buat satu perbaikan lagi. Baik **tambah** maupun **nilai** menghitung **len(titik)** setiap kali dipanggil. Ini sering kali perhitungan yang tidak perlu; setelah daftar berisi **n** nilai, panjangnya tidak akan berubah lagi. Kita bisa menyimpan panjang sebagai atribut pribadi lain, menginisialisasinya dengan tepat dan memperbaruinya saat panjang daftar berubah, lalu menggunakannya alih-alih menghitung ulang panjang. Taktik ini mirip dengan teknik **memoization** dari Bagian 9.4.

Dengan modifikasi ini, kita mendapatkan definisi kelas seperti ditunjukkan di Contoh 11.1. Perhatikan dokumentasi dalam komentar; ini adalah jenis dokumentasi yang biasanya menyertai definisi kelas. Komentar sebelum definisi kelas menjelaskan antarmuka eksternal kelas, yaitu hal-hal yang perlu diketahui pemrogram untuk menggunakannya. Komentar dalam definisi kelas menjelaskan detail internal, seperti atribut pribadi.

**Contoh 11.1. Kelas RataRataBergerak**

```python
# RataRataBergerak: rata-rata bergerak dari urutan angka.
# RataRataBergerak(n) konstruktor, di mana n = jumlah nilai untuk dirata-rata
# tambah(self, a) menambahkan a ke urutan
# nilai(self) rata-rata dari n nilai yang paling baru ditambahkan,
# atau dari semua jika kurang dari n; None jika tidak ada
class RataRataBergerak:

    # atribut pribadi:
    # __nTitik jumlah nilai untuk dirata-rata
    # __titik daftar hingga sebanyak itu nilai
    # __panjang panjang dari __titik, dipertahankan saat ini
    
    def __init__(self, nTitik):
        self.__titik = []
        self.__panjang = 0
        self.__nTitik = nTitik
        
    def tambah(self, nilaiBaru):
        titik = self.__titik
        if self.__panjang == self.__nTitik:
            titik.pop(0)
        else:
            self.__panjang += 1
        titik.append(nilaiBaru)
        
    def nilai(self):
        titik = self.__titik
        panjang = self.__panjang
        if panjang > 0:
            return sum(titik) / panjang
        else:
            return None
```

Implementasi ini cukup baik untuk banyak tujuan. Namun, apakah cukup efisien untuk semua kasus? Kita mungkin bisa mengetahuinya jika kita tahu bagaimana kelas ini akan digunakan.

Misalkan dalam program tertentu, metode **nilai** dipanggil jauh lebih sering daripada **tambah**. Mungkin aliran data menghasilkan nilai baru cukup jarang, seperti statistik ekonomi mingguan atau bulanan. Namun, kode ini mungkin bagian dari situs web populer yang menerima banyak permintaan per detik untuk nilai rata-rata bergerak.

Dalam situasi ini, metode **nilai** sering menghitung ulang rata-rata secara tidak perlu ketika data tidak berubah. Kita bisa menghilangkan perhitungan ini dengan menghitung rata-rata setiap kali **tambah** dipanggil dan menyimpannya sebagai atribut pribadi lain, yang kemudian digunakan oleh **nilai**. Ini adalah bentuk lain dari **memoization**, dan sekarang **nilai** hanya mengakses data alih-alih menghitung.

Dengan modifikasi ini, **RataRataBergerak** didefinisikan seperti ditunjukkan di Contoh 11.2. Atribut data baru adalah **__nilai**; perhatikan bahwa atribut ini tidak ada sampai **self.__panjang** lebih besar dari nol, tetapi kita tidak menggunakannya sebelum itu.

Versi 2 dari **RataRataBergerak** tidak selalu lebih baik daripada versi asli. Misalkan sekarang **tambah** dipanggil jauh lebih sering daripada **nilai**, mungkin karena aliran data adalah pengukuran fisik dari sensor yang tiba ribuan kali per detik, tetapi nilai rata-rata hanya diperlukan sekali per detik atau menit. Maka **tambah** menghitung rata-rata berkali-kali tanpa digunakan.

Berkat pemrograman berorientasi objek, kedua versi **RataRataBergerak** sepenuhnya dapat dipertukarkan dalam program. Antarmuka eksternal kelas, seperti didokumentasikan dalam komentar sebelum definisi kelas, identik di kedua versi. Kita bisa mengukur efisiensi program dan mengganti versi 2 dengan versi asli, atau sebaliknya, untuk meningkatkan efisiensi kapan saja tanpa mengubah kode yang menggunakan kelas, seperti fungsi **halus**.

**Contoh 11.2. Kelas RataRataBergerak, versi 2**

```python
# RataRataBergerak: rata-rata bergerak dari urutan angka.
# RataRataBergerak(n) konstruktor, di mana n = jumlah nilai untuk dirata-rata
# tambah(self, a) menambahkan a ke urutan
# nilai(self) rata-rata dari n nilai yang paling baru ditambahkan

class RataRataBergerak:

    # atribut pribadi:
    # __nTitik jumlah nilai untuk dirata-rata
    # __titik daftar hingga sebanyak itu nilai
    # __panjang panjang titik
    # __nilai rata-rata dari nilai dalam __titik
    # justifikasi untuk memoizing __nilai: nilai() 
    # dipanggil jauh lebih sering daripada tambah()
    
    def __init__(self, nTitik):
        self.__titik = []
        self.__panjang = 0
        self.__nTitik = nTitik
        
    def tambah(self, nilaiBaru):
        titik = self.__titik
        if self.__panjang == self.__nTitik:
            titik.pop(0)
        else:
            self.__panjang += 1
        titik.append(nilaiBaru)
        self.__nilai = sum(titik) / self.__panjang
        
    def nilai(self):
        if self.__panjang > 0:
            return self.__nilai
        else:
            return None
```

### 11.6. Objek yang Didefinisikan Secara Rekursif: Pohon (trees)

Dalam contoh-contoh sebelumnya, nilai atribut data kelas yang didefinisikan oleh pemrogram adalah tipe bawaan Python, tetapi atribut juga bisa berupa instans dari kelas lain yang didefinisikan oleh pemrogram. Misalnya, atribut **alamat** dalam kelas **Orang** dan **Pelanggan** (Bagian 11.2 dan 11.3) adalah string, tetapi jika kita memiliki kelas **Alamat** dengan atribut seperti jalan, kota, dan sebagainya, nilai **alamat** bisa menjadi objek **Alamat** (dengan perubahan pada metode **labelAlamat**, tentu saja).

Lebih menarik lagi, nilai sebuah atribut bisa menjadi instans dari kelas yang sama yang sedang didefinisikan. Misalnya, dalam kelas **Orang**, atribut **ibu** dan **ayah** orang tersebut bisa berupa objek **Orang** lainnya.

Dengan demikian, kelas **Orang** didefinisikan sebagian berdasarkan dirinya sendiri, seperti fungsi rekursif. Kita menyebut instans dari kelas ini sebagai **objek yang didefinisikan secara rekursif**. Objek seperti ini sangat penting dalam ilmu komputer, dan kemampuan untuk bekerja dengannya adalah keterampilan pemrograman yang berharga.

Mari kita pertimbangkan satu jenis objek yang didefinisikan secara rekursif: **pohon**. Kita telah melihat pohon secara singkat di Bagian 6.6. Ada beberapa cara untuk mendeskripsikan pohon dalam matematika dan ilmu komputer, dan kita akan menjelajahi beberapa di antaranya, termasuk deskripsi rekursif.

Dalam teori graf, pohon adalah jenis graf, baik terarah maupun tidak terarah. Kita akan fokus pada pohon terarah dengan simpul terpilih yang disebut **akar** (*root*), dari mana jalur-jalur memancar. Pohon jenis ini dapat didefinisikan dengan dua sifat:
- Ada satu dan hanya satu simpul tanpa sisi yang mengarah ke sana. Simpul ini adalah akar pohon.
- Setiap simpul lain memiliki satu dan hanya satu sisi yang mengarah ke sana.

Sifat-sifat ini memastikan bahwa untuk setiap simpul, ada jalur dari akar ke simpul tersebut, dan hanya satu jalur. Jalur dalam pohon tidak pernah bertemu.

Jika pohon bersifat terbatas (dan kita hanya akan mempertimbangkan pohon terbatas), ia harus memiliki **daun**, yaitu simpul tanpa sisi yang mengarah darinya.

Berikut adalah contoh sebuah pohon. Pohon ini tidak diberi label, dan kali ini akarnya berada di bagian atas gambar, sedangkan daunnya mengarah ke bagian bawah.

![](attachment/Pasted%20image%2020250512135401.png)

Berikut adalah definisi rekursif yang mendefinisikan pohon jenis yang sama:

**Pohon** adalah salah satu dari berikut:
- sebuah daun, atau
- sebuah simpul (akar) dengan sisi ke satu atau lebih **subpohon**, yang merupakan pohon yang didefinisikan dengan cara yang sama.

![](attachment/Pasted%20image%2020250512135425.png)

Mari kita lihat variasi pada definisi rekursif pohon. Berikut adalah salah satunya:

**Pohon** adalah sebuah daun, atau sebuah objek yang berisi satu atau lebih subpohon, yang merupakan pohon yang didefinisikan dengan cara yang sama.

Di sini, alih-alih berbicara tentang sisi ke subpohon, kita berbicara tentang subpohon yang terkandung dalam pohon yang lebih besar. Pohon-pohon ini bersarang, seperti ekspresi atau pernyataan majemuk dalam Python yang bersarang.

![](attachment/Pasted%20image%2020250512135507.png)

Ini adalah pandangan yang sering kita ambil dalam pemrograman, terutama saat bekerja dengan objek. Alih-alih memandang pohon sebagai graf dengan sisi, pohon adalah objek yang memiliki pohon lain sebagai atribut. Sisi mungkin ada sebagai ikatan atau penunjuk, tergantung pada implementasi objek pohon. Kadang-kadang kita memikirkan sisi secara eksplisit saat memvisualisasikan pohon, tetapi sering kali tidak.

Berikut adalah definisi lain yang sedikit berbeda:

**Pohon** adalah kosong, atau adalah objek yang berisi satu atau lebih subpohon, yang merupakan pohon yang didefinisikan dengan cara yang sama.

Dengan definisi ini, daun adalah pohon yang semua subpohonnya kosong.

Definisi ini memungkinkan pohon menjadi tidak ada sama sekali, yang mungkin tidak masuk akal dalam banyak konteks. Namun, pohon kosong bisa berguna dalam pemrograman, seperti yang akan kita lihat.

Dalam ilmu komputer, simpul pohon sering diberi **label**; bahkan, simpul mungkin memiliki lebih dari satu data yang terlampir. Jika pohon diprogram sebagai objek, setiap simpul diwakili oleh objek pohon, dan atributnya adalah label, data lain, serta subpohon.

Data yang dilampirkan pada simpul yang berbeda bisa berbeda jenisnya. Berikut adalah contoh pohon ilmu komputer: pohon yang mewakili ekspresi.

![](attachment/Pasted%20image%2020250512135553.png)

Ekspresi tersebut adalah **x + y * z**, mungkin bagian dari program. Daun-daun diberi label dengan nama variabel, dan simpul lain diberi label dengan operator. Interpreter dan kompiler sering menggunakan pohon serupa untuk mewakili ekspresi dan bagian lain dari program.

Pohon sangat ideal untuk mewakili struktur bersarang seperti ekspresi. Pohon juga berguna untuk informasi lain, termasuk hubungan hierarki. Pohon berikut mewakili hierarki kelas dan subkelas seperti yang disajikan di Bagian 11.3. (Ini adalah contoh pohon yang bukan biner.)

![](attachment/Pasted%20image%2020250512135623.png)

Dalam bahasa Inggris sehari-hari, ada “pohon” yang benar-benar pohon dalam pengertian matematis: **pohon keluarga**.

Ada dua jenis pohon keluarga: satu menunjukkan leluhur seseorang, dan yang lain menunjukkan keturunan seseorang. Kita akan fokus pada yang pertama, yang kita sebut **pohon leluhur**.

Gambar 11.3 menunjukkan pohon leluhur untuk seseorang bernama William. Dalam diagram ini, orang yang lebih tua berada di atas, dan yang lebih muda di bawah, sehingga akar pohon berada di bawah. Sisi menunjuk dari seseorang ke ayah (ke atas dan ke kiri) dan ibu (ke atas dan ke kanan). Tentu saja, pohon ini tidak menunjukkan semua leluhur William; ada orang-orang (daun pohon) yang ayah dan ibunya tidak diwakili dalam pohon.

**Gambar 11.3. Pohon leluhur**

![](attachment/Pasted%20image%2020250512135644.png)

Perhatikan subpohon, yang juga merupakan pohon jenis yang sama. Misalnya, pohon yang akarnya diberi label “Charles” adalah pohon leluhur untuk Charles.

Sekarang mari kita lihat bagaimana kita bisa mewakili struktur seperti ini sebagai objek yang didefinisikan secara rekursif dalam program.

Menggunakan Python, kita definisikan kelas **Orang**. Setiap instans kelas akan mewakili seseorang dalam pohon leluhur, dengan atribut **nama**, **ayah**, dan **ibu**. Berikut adalah kepala kelas dan konstruktornya:

```python
class Orang:

    def __init__(self, nama, ayah, ibu):
        self.nama = nama
        self.ayah = ayah
        self.ibu = ibu
```

Kemudian, kita bisa membangun pohon leluhur William dengan kode berikut. Kita buat objek **Orang** untuk orang tua terlebih dahulu, sehingga bisa digunakan sebagai nilai atribut **ayah** dan **ibu** untuk orang yang lebih muda. Kita gunakan **None** untuk **ayah** dan **ibu** dari orang-orang di daun pohon; ini berarti pohon tidak mengandung informasi tentang orang tua mereka, bukan bahwa mereka tidak punya orang tua.

```python
george = Orang("George", None, None)
elizabeth = Orang("Elizabeth", None, None)
elizabeth2 = Orang("Elizabeth", george, elizabeth)
philip = Orang("Philip", None, None)
charles = Orang("Charles", philip, elizabeth2)
diana = Orang("Diana", None, None)
william = Orang("William", charles, diana)
```

Kode ini hanya untuk ilustrasi. Dalam praktik, terutama untuk pohon besar, kita mungkin ingin membaca data dari file daripada mengkodekannya langsung (lihat Latihan 4).

Sekarang, setelah memiliki pohon atau objek rekursif lainnya, bagaimana kita memprosesnya? Berikut prinsip penting:

>Perhitungan yang memproses objek data yang didefinisikan secara rekursif kemungkinan besar bersifat rekursif, dengan struktur yang mengikuti definisi rekursif dari objek tersebut.

Misalnya, berikut adalah struktur umum untuk banyak perhitungan yang memproses pohon:

**Untuk memproses pohon:**
- jika itu daun:
  - lakukan sesuatu dengan data di daun
- jika tidak:
  - lakukan sesuatu, mungkin berbeda, dengan data di akar
  - proses secara rekursif setiap subpohon
  - gabungkan hasilnya

Tidak semua perhitungan pada pohon mengikuti pola ini, tetapi jika memungkinkan, pola ini cenderung menghasilkan kode yang lebih sederhana dan jelas benar.

Sebagai contoh, mari tulis metode untuk kelas **Orang** yang membangun himpunan nama-nama dalam pohon leluhur seseorang.

Kita akan mengikuti pola rekursif. Baik orang tersebut daun atau bukan, kita mulai dengan mengambil nama orang tersebut sebagai himpunan satu elemen. Jika ayah orang tersebut ada dalam pohon, kita tambahkan nama-nama dari pohon leluhur ayah, dan begitu pula untuk ibu. Operator `+=` adalah gabungan himpunan.

```python
def namaLeluhur(self):
    hasil = {self.nama}
    if self.ayah != None:
        hasil += namaLeluhur(self.ayah)
    if self.ibu != None:
        hasil += namaLeluhur(self.ibu)
    return hasil
```

Solusi ini cukup baik, tetapi kita bisa menyederhanakannya. Ingat definisi rekursif pohon yang memungkinkan pohon kosong. Tidak masuk akal jika pohon leluhur seseorang kosong—setidaknya mencakup orang itu sendiri—tetapi misalkan kita biarkan atribut **ayah** atau **ibu** menjadi pohon kosong? Maka **None** mewakili subpohon kosong, bukan hanya penanda informasi yang hilang.

Dengan pendekatan ini, kita tidak perlu menguji setiap subpohon untuk **None**; pohon kosong menjadi kasus dasar untuk rekursi. Himpunan nama dalam pohon kosong adalah himpunan kosong. Berikut solusinya:

```python
def namaLeluhur(self):
    if self == None:
        return set()  # himpunan kosong
    else:
        return {self.nama} \
        + namaLeluhur(self.ayah) \
        + namaLeluhur(self.ibu)
```

Kode ini lebih sederhana dan lebih dekat dengan pola fungsi rekursif seperti faktorial (Bagian 4.2). Kasus dasar dan rekursif dipisahkan dengan jelas, membuatnya lebih mudah dipahami.

Contoh ini mengilustrasikan dua prinsip:
1. Tidak apa-apa memilih definisi matematis yang mempermudah pemrograman, atau menyesuaikan definisi untuk keuntungan Anda.
2. Jangan menyesuaikan kode tanpa memperhatikan definisi matematis! Pilih definisi, pastikan sesuai dengan kebutuhan, lalu tulis kode yang mencerminkannya.

### 11.7. Mesin Keadaan

Keadaan sebuah objek adalah informasi yang dipertahankan dari satu pemanggilan metode ke pemanggilan berikutnya. Sebuah metode dapat mengubah keadaan objek (seperti **tambah** pada **RataRataBergerak**), dan hasil pemanggilan metode dapat bergantung pada keadaan (seperti **nilai**).

Saat merancang objek, kadang-kadang berguna untuk berpikir secara eksplisit tentang keadaan dan transisi antar keadaan. Ini sangat relevan ketika jumlah keadaan yang mungkin terbatas dan kecil. Kita bisa memberi nama untuk setiap keadaan.

Kita juga bisa menunjukkan perilaku objek dengan **diagram transisi**, yaitu graf terarah berlabel di mana simpul diberi label nama keadaan, dan sisi diberi label nama stimulus atau masukan yang menyebabkan transisi dari satu keadaan ke keadaan lain.

![](attachment/Pasted%20image%2020250512135824.png)

Diagram transisi mendefinisikan **mesin keadaan**, sebuah konsep matematis dalam ilmu komputer. Sebagian besar sifat matematis mesin keadaan berada di luar cakupan buku ini, tetapi kita akan menggunakannya untuk mendeskripsikan dan merancang objek. Perancang perangkat lunak dan perangkat keras sering melakukan ini.

Misalnya, pertimbangkan tombol tekan listrik yang diklik sekali untuk menyalakan dan diklik lagi untuk mematikan. Kita bisa mendeskripsikannya sebagai mesin keadaan dengan dua keadaan, **mati** dan **nyala**, dan stimulus tunggal “klik” yang menyebabkan transisi antar keadaan.

![](attachment/Pasted%20image%2020250512135846.png)

Sekarang pertimbangkan perangkat yang lebih kompleks. Ketika diklik, ia bekerja seperti tombol sebelumnya. Namun, tidak ada cara untuk melihat apakah tombol nyala atau mati, jadi ditambahkan fitur “reset”: menahan tombol beberapa detik mematikannya, baik nyala maupun mati sebelumnya.

![](attachment/Pasted%20image%2020250512135915.png)

Kita bisa mendefinisikan kelas Python yang berperilaku seperti perangkat ini, menggunakan diagram transisi sebagai panduan. Keadaan objek disimpan dalam atribut pribadi. Karena hanya ada dua keadaan, atribut hanya perlu dua nilai. Nilai boolean adalah pilihan alami: kita beri nama atribut **__nyala**, dengan **True** untuk **nyala** dan **False** untuk **mati**.

Metode `__init__` mengatur **__nyala** ke nilai awal; kita pilih **False**. Stimulus “klik” diimplementasikan oleh metode **klik**, yang membalikkan nilai **__nyala** menggunakan operator **not**. Stimulus “reset” ditangani oleh metode **reset**, yang mengatur **__nyala** ke **False**. Metode **isNyala** mengembalikan nilai atribut. Kode ini sangat sederhana, seperti ditunjukkan di Contoh 11.3.

Sekarang mari kita lihat contoh mesin keadaan untuk tugas pemrograman umum: menemukan kolom dalam string. String mungkin adalah baris dari file datar (Bagian 8.4), tetapi kolom dipisahkan oleh satu atau lebih spasi, bukan koma seperti CSV; mungkin juga ada spasi di awal atau akhir string. Kolom bisa berisi karakter apa pun kecuali spasi. Kita ingin menghasilkan kolom sebagai urutan, mungkin sebagai aliran.

**Contoh 11.3. Kelas TombolTekan**

```python
class TombolTekan:

    def __init__(self):
        self.__nyala = False
        
    def klik(self):
        self.__nyala = not self.__nyala
        
    def reset(self):
        self.__nyala = False
        
    def isNyala(self):
        return self.__nyala
```

Ada beberapa cara untuk melakukan ini, tetapi kita akan menggunakan mesin keadaan. Mesin akan menerima satu karakter pada satu waktu dan melacak apakah karakter saat ini berada dalam kolom atau spasi; ini menjadi dua keadaan. Keadaan penting karena karakter memiliki makna berbeda tergantung konteks; misalnya, spasi setelah spasi lain diabaikan, tetapi spasi setelah karakter non-spasi menandakan akhir kolom.

Notasi diagram transisi memiliki variasi, dan kita akan menggunakan dua di sini:
- Panah dari luar graf ke salah satu keadaan, menunjukkan keadaan awal mesin saat dibuat.
- Label tambahan pada setiap transisi, yaitu nama respons terhadap stimulus. Respons adalah apa yang dilakukan mesin dalam keadaan tertentu saat menerima stimulus.

![](attachment/Pasted%20image%2020250514093052.png)

Dalam mesin keadaan kita, stimuli adalah karakter dari string, dan respons adalah “makna” karakter dalam konteks karakter sebelumnya. Respons yang kita perlukan adalah:
- **sertakan**: karakter adalah bagian dari kolom.
- **abaikan**: karakter tidak berarti apa-apa dan diabaikan.
- **akhiri**: karakter menandakan akhir kolom, tetapi bukan bagian dari kolom.

Berikut adalah diagram transisi. Dua keadaan adalah **di spasi** dan **di kolom**. Karena string bisa dimulai dengan spasi, keadaan awal adalah **di spasi**. Dalam keadaan ini, spasi membuat mesin tetap di **di spasi** dengan respons **abaikan**. Karakter lain memulai kolom, sehingga mesin pindah ke **di kolom** dengan respons **sertakan**. Di **di kolom**, karakter non-spasi membuat mesin tetap di **di kolom** dengan respons **sertakan**, sedangkan spasi mengembalikan ke **di spasi** dengan respons **akhiri**.

![](attachment/Pasted%20image%2020250514093138.png)

Sekarang kita menerjemahkan diagram transisi ke kode Python. Kita harus memutuskan bagaimana mewakili keadaan dan respons. Keduanya seperti himpunan: tidak berurutan dan elemennya berbeda. Namun, kita hanya perlu membandingkan untuk kesetaraan, jadi kita bisa menggunakan nilai integer kecil (lihat Bagian 8.5).

```python
diKolom = 0
diSpasi = 1

sertakan = 0
akhiri = 1
abaikan = 2
```

Kode untuk mesin keadaan ditunjukkan di Contoh 11.4. Keadaan disimpan di **self.keadaan**, dan konstruktor mengaturnya ke **diSpasi**. Metode **maju** menerima karakter, melakukan transisi keadaan, dan mengembalikan respons berdasarkan keadaan lama dan karakter.

**Contoh 11.4. Mesin keadaan untuk menemukan kolom dalam string**

```python
class MesinKeadaanKolom:

    def __init__(self):
        self.keadaan = diSpasi
        
    def maju(self, karakter):
        if self.keadaan == diKolom:
            if karakter == " ":
                self.keadaan, respons = diSpasi, akhiri
            else:
                self.keadaan, respons = diKolom, sertakan
        else: # self.keadaan = diSpasi
            if karakter == " ":
                self.keadaan, respons = diSpasi, abaikan
            else:
                self.keadaan, respons = diKolom, sertakan
        return respons
```

Kode yang menggunakan mesin keadaan ditunjukkan di Contoh 11.5. Fungsi generator **kolom** menghasilkan kolom satu per satu. Setiap karakter dimasukkan ke mesin keadaan. Kita akumulasikan karakter dalam variabel **kolom** jika respons adalah **sertakan**. Jika respons **akhiri**, kita hasilkan kolom dan mulai yang baru. Di akhir string, kolom terakhir mungkin belum diakhiri oleh spasi; kita hasilkan jika ada.

**Contoh 11.5. Kode yang menggunakan MesinKeadaanKolom**

```python
mesin = MesinKeadaanKolom()

def kolom(string):
    kolom = ""
    
    for c in string:
        respons = mesin.maju(c)
        if respons == sertakan:
            kolom += c
        elif respons == akhiri:
            yield kolom
            kolom = ""
        # else: respons == abaikan: pass
    if kolom != "":
        yield kolom
```

Contoh ini sederhana, dan tugas ini bisa dilakukan lebih mudah dengan metode **split** Python. Sekarang mari tambahkan komplikasi atau “fitur”.

Misalkan kolom boleh mengandung spasi, seperti nama kota “Los Angeles” atau “East St. Louis”. Kolom ini diapit tanda kutip ganda, seperti **"East St. Louis"**, dan tanda kutip tidak dianggap bagian dari data kolom.

Mesin keadaan perlu keadaan baru dan transisi baru. Dalam **di spasi**, tanda kutip ganda menyebabkan transisi ke **di kutip**, yang berarti di dalam kolom yang dikutip; tanda kutip diabaikan. Mesin tetap di **di kutip** hingga tanda kutip lain diterima, yang mengakhiri kolom.

![](attachment/Pasted%20image%2020250514093716.png)

Kode yang direvisi ditunjukkan di Contoh 11.6. Perubahan mudah dilakukan setelah kita memiliki diagram transisi baru: tambahkan kode untuk keadaan dan transisi baru. Tubuh **maju** mungkin terlihat panjang, tetapi strukturnya teratur, dan kita bisa membandingkannya dengan diagram transisi untuk memastikan kebenaran.

Sebagai catatan, ilmuwan komputer telah mengamati bahwa **monoid** dapat didefinisikan dari transisi mesin keadaan, dan teori ilmu komputer mengembangkan implikasi dari fakta ini. Hasil ini tidak langsung relevan untuk pemrograman sehari-hari, jadi kita tidak akan membahas detailnya. Namun, ini memperkuat gagasan bahwa monoid ada di mana-mana dalam komputasi.

**Contoh 11.6. Mesin keadaan untuk menemukan kolom, versi 2**

```python
diKolom = 0
diSpasi = 1
diKutip = 2

sertakan = 0
akhiri = 1
abaikan = 2

class MesinKeadaanKolom:

    def __init__(self):
        self.keadaan = diSpasi
        
    def maju(self, karakter):
        if self.keadaan == diKolom:
            if karakter == " ":
                self.keadaan, respons = diSpasi, akhiri
            else:
                self.keadaan, respons = diKolom, sertakan
        elif self.keadaan == diKutip:
            if karakter == '"':
                self.keadaan, respons = diSpasi, akhiri
            else:
                self.keadaan, respons = diKutip, sertakan
        else: # self.keadaan = diSpasi
            if karakter == " ":
                self.keadaan, respons = diSpasi, abaikan
            elif karakter == '"':
                self.keadaan, respons = diKutip, abaikan
            else:
                self.keadaan, respons = diKolom, sertakan
        return respons
```

**Istilah yang Diperkenalkan dalam Bab Ini**
- Atribut objek (_attributes of an object_)
- Keadaan objek (_state of an object_)
- Kelas (_class_)
- Identitas objek (_identity of an object_)
- Instans (_instance_)
- Superkelas (_superclass_)
- Mengganti metode (_overriding a method_)
- Atribut pribadi (_private attribute_)
- Objek yang didefinisikan secara rekursif (_recursively defined object_)
- Akar (_root_)
- Konstruktor (_constructor_)
- Ruang nama (_name space_)
- Pewarisan (_inheritance_)
- Subkelas (_subclass_)
- Daun (_leaf_)
- Subpohon (_subtree_)
- Mesin keadaan (_state machine_)
- Diagram transisi (_transition diagram_)

**Latihan**
1. Tulis kelas Python **Multiset** berbasis kamus, dengan metode **isEmpty**, **count**, **intersection**, **union**, dan **sum**. Dalam Python, kelas yang didefinisikan oleh pemrogram dapat mewarisi dari kelas bawaan, jadi Anda mungkin ingin membuat **Multiset** mewarisi dari **dict**. Apa keuntungan dan kerugian dari pendekatan ini?

2. Tulis kelas Python **Monoid** dengan metode berikut:
   - `__init__` yang menerima dua argumen: fungsi dua argumen untuk operasi monoid dan nilai identitas monoid. Contoh pemanggilan:

     ```python
     penjumlahanInteger = Monoid(lambda x, y: x + y, 0)
     ```

   - **apply** yang menerima dua parameter, menerapkan operasi monoid, dan mengembalikan hasilnya.
   - **reduce** yang menerima iterable nilai dan mereduksinya menjadi satu nilai menggunakan operasi monoid dan identitas, seperti metode **reduce** di Bagian 6.4.

3. Tulis varian kelas **RataRataBergerak** untuk data yang tidak berjarak sama dalam waktu. Argumen konstruktor bukan jumlah titik data, melainkan durasi (misalnya, detik atau hari) untuk menghitung rata-rata bergerak. Argumen metode **tambah** adalah pasangan terurut (waktu, nilai) sesuai waktu tersebut.

4. Rancang struktur file yang dapat dibaca program untuk membangun pohon leluhur seperti di Bagian 11.6. Perhatikan bahwa nama tidak selalu unik mengidentifikasi seseorang dalam pohon. Tulis metode untuk kelas **Orang** untuk membaca file ini.

5. a. Tulis metode **leluhur** untuk kelas **Orang** yang mengembalikan himpunan semua leluhur seseorang (termasuk orang itu sendiri), bukan hanya nama mereka. Mungkin ada beberapa orang dengan nama sama tetapi berbeda dalam atribut lain seperti tanggal lahir.

   b. Bagaimana menemukan himpunan leluhur tanpa orang itu sendiri, tanpa menulis metode khusus?

   c. Menggunakan metode **leluhur**, bagaimana membangun himpunan nama leluhur dengan satu ekspresi Python?

6. Tambahkan atribut **lahir** dan **meninggal** ke objek **Orang** (Bagian 11.6); nilainya adalah integer tahun, dengan **None** untuk orang yang masih hidup. Tulis metode yang menerima **self** dan tahun, mengembalikan himpunan leluhur (termasuk orang itu) yang hidup pada tahun tersebut.

7. Modifikasi kelas **Orang** (Bagian 11.6) untuk pohon keturunan, dengan atribut anak-anak alih-alih orang tua. Bagaimana merepresentasikan kumpulan anak-anak? Tulis metode untuk membangun himpunan keturunan seseorang, termasuk orang itu.

8. Modifikasi kelas `FieldsStateMachine` pada Bagian 11.7 untuk menambahkan satu fitur lagi: Sebuah _field_ (kolom) yang diapit tanda kutip sekarang dapat berisi karakter tanda kutip ganda sebagai bagian dari data yang diwakilinya. Urutan dua karakter `\"` sekarang merepresentasikan satu karakter tanda kutip ganda di dalam _field_. Selain itu, agar _field_ yang diapit tanda kutip masih dapat memuat karakter `\` sebagai bagian dari datanya, maka urutan dua karakter `\\` sekarang mewakili satu karakter `\` di dalam _field_. Bahkan, untuk menyederhanakan, kita nyatakan bahwa sebuah karakter `\` yang diikuti oleh karakter apa pun akan merepresentasikan karakter kedua tersebut. Gambarlah diagram transisi keadaan (state transition diagram) yang baru, kemudian tulislah kode yang sesuai dengan perubahan tersebut.

9. Rancang struktur file untuk mengkodekan diagram transisi seperti di Bagian 11.7: keadaan, keadaan awal, stimuli, respons, dan transisi. Tulis program yang membaca file ini dan menghasilkan metode **maju** seperti di Contoh 11.6. Program “penghasil kode” seperti ini digunakan dalam pengembangan interpreter dan kompiler untuk menghasilkan kode untuk menemukan nama, kata kunci, konstanta, operator, dan tanda baca.

[back](./)

---

[^1]: This description is a slight simplification of what really happens in Python, but it will be good enough for our purposes.

[^2]: Python uses its own dictionaries to construct the mappings for its name spaces.

[^3]: When used in this way, _ _init_ _ is an example of what Python calls a “class method”. We will not discuss class methods further here.

[^4]: A devious programmer can access a private attribute in Python, but not in an obvious or convenient way.
