[Home](../)

[back](./)

## Bab 12: Membangun Program Skala Besar

### 12.1. Berbagi Daftar Lagu

Pada bab ini, kita akan menjelajahi bagaimana konsep-konsep yang telah dibahas dalam buku ini dapat diterapkan untuk menangani masalah pemrograman yang lebih kompleks dan berskala besar. Alih-alih menyajikan kode program secara lengkap—yang akan memakan banyak ruang dan bisa terasa membosankan untuk dibaca secara utuh—kita akan menguraikan pendekatan desain program dan, khususnya, bagaimana struktur matematis dapat menjadi alat bantu yang kuat dalam proses desain tersebut.

Mari kita mulai dengan studi kasus pertama. Tujuannya adalah menciptakan sebuah program yang memudahkan sekelompok teman untuk saling berbagi daftar lagu favorit mereka, yang biasanya diputar di komputer atau perangkat seluler.

Program ini tidak hanya memungkinkan pengguna untuk mengirim rekomendasi lagu kepada teman-teman mereka, seperti yang mungkin sudah Anda duga, tetapi juga mampu melacak lagu-lagu yang dimainkan oleh seorang pengguna. Secara berkala, misalnya setiap minggu, program akan mengirimkan daftar lagu yang paling sering diputar oleh pengguna tersebut kepada semua temannya melalui koneksi nirkabel di perangkat mereka. Selain itu, program ini juga akan menerima daftar lagu dari teman-teman pengguna, menggabungkannya, dan menyusunnya menjadi satu daftar terurut berdasarkan tingkat popularitas. Pengguna kemudian dapat memanfaatkan daftar ini sebagai rekomendasi, mencari lagu-lagu tersebut di koleksi musik pribadi mereka, atau bahkan menjelajahi lagu-lagu lain dari artis yang sama.

Itulah gambaran singkat dari masalah yang ingin kita selesaikan. Sekarang, mari kita bahas bagaimana kita bisa merancang program ini. Sepanjang penjelasan, kita juga akan menyisipkan beberapa potongan kode Python untuk memperjelas ide-ide yang dibahas.

Daftar lagu dalam konteks ini adalah sebuah urutan (sequence) yang disusun berdasarkan ukuran popularitas tertentu, tetapi tidak harus berupa "list" dalam pengertian teknis Python. Setiap lagu memiliki sejumlah atribut, seperti nama artis, judul lagu, komposer, dan mungkin juga genre. Program kita hanya akan memproses atribut-atribut ini, bukan file audio lagu itu sendiri. Identitas sebuah lagu ditentukan oleh kombinasi atribut-atributnya. Jika semua lagu berasal dari satu sumber, misalnya toko musik daring milik perusahaan tertentu, kita bisa menggunakan nomor katalog toko sebagai pengenal lagu. Namun, dalam kasus ini, kita mengasumsikan lagu-lagu bisa berasal dari berbagai sumber, termasuk rekaman pribadi.

Untuk merepresentasikan lagu, kita akan menggunakan tuple di Python, dengan elemen pertama berisi nama artis, elemen kedua berisi judul lagu, dan seterusnya untuk setiap atribut yang ingin kita masukkan. Meskipun ada representasi lain yang mungkin digunakan (lihat latihan di akhir bab), tuple dipilih karena sifatnya yang sederhana dan mendukung desain yang ringkas. Tuple bersifat immutable (tidak dapat diubah), sehingga kita bisa menggunakannya sebagai anggota himpunan atau kunci dalam kamus. Kita akan menyebut tuple ini sebagai “tune-tuple”.

Setiap atribut dalam tune-tuple akan memiliki posisi yang tetap. Untuk mempermudah akses ke atribut berdasarkan nama, kita mendefinisikan sejumlah fungsi yang memetakan tune-tuple ke atribut tertentu:

```python
def artist(tune):
    return tune[0]

def title(tune):
    return tune[1]
```

dan seterusnya untuk setiap atribut yang ingin kita akses dengan nama.

Perpustakaan lagu seseorang akan direpresentasikan oleh himpunan tune-tuple, membentuk relasi jika kita ingin memikirkannya seperti itu. Data akan berasal dari file dalam varian format CSV: setiap baris mewakili sebuah lagu dan berisi atribut-atributnya yang dipisahkan oleh karakter batang vertikal (`|`). Format ini memungkinkan atribut seperti judul lagu mengandung koma, yang tidak terlalu jarang. Kami dapat membangun himpunan tune-tuple menggunakan varian dari fungsi setofTuples dari Bagian 8.4. Berikut adalah definisi yang kami gunakan; kami hanya membagi berdasarkan karakter batang vertikal, bukan koma. Perhatikan penggunaan *set comprehension*.

```python
def setofTuples(fileName):
    file = open(fileName)
    return { tuple(line.strip().split("|"))
             for line in file }
```

Jika file data bernama "myTunes", kita melakukan ini untuk membangun struktur set-of-tuples:

```python
myTunes = setofTuples("myTunes")
```

Saat seseorang memainkan lagu, lagu-lagu tersebut dikomunikasikan ke program kami (dengan cara yang berada di luar cakupan buku ini) sebagai aliran tune-tuple. Program kami mengakumulasikan tune-tuple dalam sebuah multiset. Kami menggunakan multiset, bukan himpunan, karena tentu saja seseorang bisa memainkan lagu yang sama lebih dari sekali, dan salah satu tujuan kami adalah menghitung seberapa sering setiap lagu dimainkan.

Kami mendefinisikan sebuah kelas multiset, karena (seperti yang akan Anda lihat) kami akan membutuhkan beberapa di antaranya. Kami mengimplementasikan multiset sebagai pemetaan dari nilai ke jumlah, menggunakan kamus seperti yang kami lakukan di Bagian 9.5; kami menyimpan kamus dalam atribut data pribadi. Kami menyediakan metode tally seperti fungsi dengan nama yang sama yang kami definisikan di Bagian 9.5.

```python
class Multiset:

    def __init__(self):
        self.__count = {}
        
    def tally(self, value):
        if value in self.__count:
            self.__count[value] += 1
        else:
            self.__count[value] = 1
```

Kami membuat objek Multiset bernama `plays`, dan saat seseorang memainkan lagu, tune-tuple dimasukkan ke dalamnya:

```python
plays.tally(tune)
```

Dalam kelas Multiset, kami menyediakan metode lain untuk mengekstrak daftar lagu dari multiset plays. Metode ini disebut topN, dan mengembalikan $$n$$ lagu dengan jumlah pemutaran terbanyak, tertinggi terlebih dahulu. Di sini $$n$$ adalah argumen, untuk memungkinkan pengguna mengatur jumlah sesuai preferensi; tidak ada yang ajaib tentang angka sepuluh. Bagaimanapun, untuk mendapatkan daftar putar dari 10 lagu teratas, kita akan menulis sesuatu seperti ini:

```python
playList = plays.topN(10)
```

Ada beberapa cara topN dapat menghasilkan daftar yang diperlukan. Berikut adalah dua di antaranya:

1. Menghasilkan isi `__count` sebagai urutan pasangan terurut di mana jumlahnya berada di depan dan tune-tuple di belakang:

```python
byCount = ((count, tune)
           for (tune, count) in items(self.__count))
```

Mengurutkan urutan itu menggunakan fungsi bawaan `sorted`, yang menghasilkan daftar dalam urutan menaik berdasarkan jumlah (dan, dalam sub-urutan dengan jumlah yang sama, dalam urutan menaik tune-tuple, tetapi itu tidak terlalu penting). Membalikkan hasilnya (perpustakaan Python memiliki metode daftar `reverse`), mengambil irisan dari $$n$$ elemen pertama dari urutan yang dihasilkan, dan menghasilkan urutan hanya dari tune-tuple dari pasangan terurut menggunakan comprehension.

2. Fungsi bawaan `sorted` dapat, dengan argumen tambahan, melakukan sebagian besar pekerjaan dan menghasilkan daftar yang diurutkan berdasarkan jumlah dalam urutan terbalik dalam satu langkah. Metode ini membutuhkan beberapa Python yang belum kami bahas dalam buku ini, tetapi jika Anda tertarik, Anda dapat melihat dokumentasi Python untuk fungsi sorted dan frasa "keyword argument".

Apapun cara yang digunakan, hasilnya adalah urutan lagu yang paling sering diputar oleh pengguna. Urutan ini kemudian dikirimkan ke teman-teman pengguna dalam format CSV yang sama dengan yang digunakan untuk menyimpan koleksi lagu pengguna. (Seperti halnya mekanisme pengiriman data lain, kita tidak akan membahas detail teknis pengiriman atau penerimaan daftar lagu di sini.) Daftar teman pengguna direpresentasikan sebagai sebuah himpunan, mungkin berisi alamat daring atau objek yang memiliki alamat daring sebagai atribut.

Di sisi lain, program juga akan menerima daftar lagu dan rekomendasi dari teman-teman pengguna (sekali lagi, mekanisme penerimaannya tidak dibahas). Sebuah rekomendasi terdiri dari sebuah *tune-tuple* dan sebuah pesan (mungkin berupa komentar tentang lagu) dalam format yang sesuai. Dalam program, rekomendasi ini direpresentasikan sebagai pasangan terurut (*tuple*) yang berisi *tune-tuple* dan sebuah string. Daftar lagu dari teman-teman dikumpulkan dalam sebuah himpunan bernama `friendsLists`, sedangkan rekomendasi disimpan dalam himpunan lain bernama `friendsRecommendations`.

Program ini mampu menampilkan semua daftar lagu dan rekomendasi yang diterima. Lebih dari itu, program juga dapat mengolah data ini untuk menghasilkan daftar lagu yang diagregasi. Mirip dengan data pemutaran pengguna, data ini awalnya disimpan sebagai *multiset* sebelum diubah menjadi urutan yang diurutkan. Sayangnya, Python tidak mendukung *multiset comprehension*, tetapi kita tetap bisa membangun *multiset* dengan mudah menggunakan perulangan `for` dan metode `tally`. Misalnya, untuk menghasilkan daftar 10 lagu yang paling sering disebut dalam daftar lagu teman-teman, kita bisa menulis kode seperti ini:

```python
allMentions = Multiset()
for fList in friendsLists:
    for tune in fList:
        allMentions.tally(tune)
topTenMentions = allMentions.topN(10)
```

Untuk menghasilkan daftar 10 lagu yang menempati posisi pertama di daftar lagu teman-teman paling banyak, kodenya akan seperti ini:

```python
allMostPopular = Multiset()
for fList in friendsLists:
    allMostPopular.tally(fList[0])
topTenMostPopular = allMostPopular.topN(10)
```

Atau, untuk menghasilkan daftar 10 lagu yang paling banyak direkomendasikan oleh teman-teman (ingat, elemen pertama dari pasangan rekomendasi adalah *tune-tuple*):

```python
allRecommended = Multiset()
for rec in friendsRecommendations:
    allRecommended.tally(rec[0])
topTenRecommended = allRecommended.topN(10)
```

Kita juga bisa membuat daftar lagu agregasi berdasarkan lagu-lagu yang paling sering diputar oleh teman-teman, dengan bobot berdasarkan jumlah pemutaran setiap lagu. Untuk ini, kita perlu data jumlah pemutaran dari setiap teman, bukan hanya daftar lagu. Misalnya, setiap teman bisa mengirimkan pasangan lagu dan jumlah pemutarannya, mungkin hanya untuk 10 lagu teratas mereka, yang pada dasarnya adalah sebuah *multiset*. Kita kemudian bisa menggabungkan semua *multiset* ini untuk menghasilkan daftar lagu agregasi, baik dengan menjumlahkan jumlah pemutaran atau mengambil gabungan (*union*). Daftar seperti ini mungkin kurang berguna jika didominasi oleh teman yang paling sering mendengarkan musik, tetapi tetap bisa menjadi fitur tambahan yang menarik untuk dipertimbangkan.

Pengguna kemudian bisa memutar lagu-lagu dari daftar agregasi ini atau mencari lagu serupa di koleksi mereka. Untuk memeriksa apakah sebuah lagu ada di koleksi pengguna, kita cukup menggunakan ekspresi boolean sederhana:

```python
t in myTunes
```

Jika pengguna ingin mencari lagu-lagu dari artis yang sama dengan lagu tertentu dalam koleksi mereka, kita bisa menggunakan *set comprehension*:

```python
{t for t in myTunes 
    if t.artist() == tune.artist()}
```

Perhatikan bahwa operasi ini mirip dengan seleksi relasional yang dibahas di Bagian 10.5. Anda mungkin bisa membayangkan operasi serupa lainnya yang bisa ditambahkan ke program ini.

Mari kita tinjau struktur matematis yang digunakan dalam studi kasus ini: *multiset* untuk menghitung frekuensi, himpunan (*set*) dan *set comprehension* untuk mengelola koleksi lagu, *n-tuple* untuk merepresentasikan lagu, berbagai jenis urutan (*sequence*), pemetaan (*mapping*) seperti fungsi `artist`, `title`, dan metode `topN`, serta relasi untuk mengorganisasi data. Dalam setiap kasus, struktur matematis yang dipilih terasa alami dan sangat sesuai dengan kebutuhan tugas yang dihadapi.

### 12.2. Survei Biologi

Studi kasus berikutnya adalah sebuah program untuk mencatat dan mengelola data dari survei biologi.

Dalam konteks ini, survei biologi adalah kegiatan menghitung jumlah organisme dari berbagai jenis di lokasi tertentu, pada waktu tertentu, atau kombinasi keduanya. Contoh nyata adalah *Christmas Bird Count* di Amerika Utara, di mana peserta mencatat jumlah burung yang diamati. Contoh lain mungkin adalah penghitungan jenis rumput atau bunga liar di sebuah padang rumput, atau jumlah ikan yang melintasi bendungan tertentu selama periode waktu tertentu.

Biasanya, peserta survei mencatat jenis organisme yang mereka amati dan jumlah masing-masing jenis. Program kita akan mengumpulkan dan mengelola data jumlah ini. Dalam beberapa kasus, seperti saat menghitung tanaman rumput, peserta mungkin tidak menghitung individu secara langsung, tetapi program tetap bisa mencatat, misalnya, berapa banyak peserta yang mengamati jenis tanaman tertentu. Atau, jika padang rumput dibagi menjadi kotak-kotak grid, program bisa menghitung jumlah kotak tempat suatu organisme ditemukan. Intinya, seperti program daftar lagu di bagian sebelumnya, program ini berfokus pada pengumpulan dan pengolahan jumlah. Namun, kali ini kita tidak akan secara eksplisit menggunakan *multiset* (himpunan dengan elemen yang bisa muncul lebih dari sekali) untuk menyimpan data, karena ada struktur lain yang lebih penting untuk kebutuhan ini, seperti yang akan kita jelaskan nanti.

Dalam dunia biologi, “jenis” organisme disebut *takson* (jamak: *taksa*). Setiap takson diidentifikasi oleh nama ilmiah, yang biasanya berasal dari bahasa Latin, dan sering kali juga memiliki nama umum dalam bahasa lokal, seperti bahasa Inggris. Taksa diorganisir dalam hierarki peringkat (*rank*), dari yang paling umum hingga yang paling spesifik. Untuk burung, misalnya, peringkat utama adalah sebagai berikut (nama ilmiah ditulis dalam huruf miring):
- **Kelas**: *Aves* (burung).
- **Ordo**: *Strigiformes* (burung hantu).
- **Famili**: *Strigidae* (burung hantu tipikal, bukan burung hantu lumbung).
- **Genus**: *Bubo* (burung hantu bertanduk).
- **Spesies**: *Bubo virginianus* (Burung Hantu Bertanduk Besar).

Ada juga peringkat tambahan, seperti superordo atau subfamili, terutama untuk kelompok seperti burung. Program kita dirancang agar fleksibel, tidak terpaku pada peringkat tertentu, melainkan menggunakan peringkat apa pun yang ada dalam data yang diberikan.

Setiap takson, kecuali yang berada di peringkat terendah, mencakup satu atau lebih taksa pada peringkat di bawahnya. Misalnya, kelas *Aves* mencakup ordo *Strigiformes* (burung hantu), *Gaviiformes* (loon), *Sphenisciformes* (penguin), dan sekitar dua lusin ordo lainnya.

Program ini perlu merepresentasikan hierarki taksa ini dengan baik, karena peserta survei tidak selalu bisa mengidentifikasi organisme hingga ke tingkat spesies. Misalnya, seseorang mungkin hanya bisa mengatakan, “Itu elang, tapi saya tidak tahu jenis apa.” Dalam survei tertentu, seperti survei serangga, mengidentifikasi spesimen hingga ke tingkat spesies bisa sangat sulit, bahkan untuk peserta yang terlatih. Oleh karena itu, program harus siap menangani data taksa di berbagai peringkat, baik spesies maupun peringkat yang lebih tinggi.

Sekarang, mari kita rancang program ini. Struktur inti dari program adalah kelas `Taxon`, yang memiliki atribut-atribut berikut:
- **Nama ilmiah** (`scientific`): Nama resmi takson, seperti *Bubo virginianus*.
- **Nama umum** (`common`): Nama dalam bahasa sehari-hari, misalnya “Great Horned Owl” (opsional, bisa kosong).
- **Peringkat** (`rank`): Posisi takson dalam hierarki, seperti genus atau spesies.
- **Jumlah** (`count`): Jumlah kemunculan takson yang dilaporkan.
- **Takson induk** (`super`): Takson di peringkat lebih tinggi yang mencakup takson ini. Bisa bernilai `None` jika tidak ada data untuk takson di atasnya (misalnya, *Aves* dalam survei burung). Setiap takson hanya dimiliki oleh satu takson induk.
- **Himpunan taksa anak** (`sub`): Kumpulan taksa pada peringkat langsung di bawah takson ini. Untuk keperluan kita, urutan taksa anak dalam himpunan ini tidak penting.

Objek `Taxon` dengan atribut `sub`-nya adalah struktur rekursif, mirip dengan pohon keturunan yang dibahas di Bagian 11.6. Dengan kata lain, setiap takson adalah akar dari sebuah pohon atau subpohon. Kita tidak mensyaratkan semua takson berada dalam satu pohon besar dengan akar tunggal. Misalnya, dalam survei padang rumput, mungkin ada pohon terpisah untuk rumput dan bunga liar. Namun, setiap takson pasti merupakan akar dari pohon tertentu.

Atribut `super` menambahkan lapisan kompleksitas pada struktur ini. Seperti yang dijelaskan di Bagian 11.6, kita bisa membayangkan pohon sebagai *graf berarah*, di mana setiap sisi mewakili hubungan dari sebuah objek ke atributnya (misalnya, dari takson ke taksa anaknya). 

![](attachment/Pasted%20image%2020250514101934.png)

Atribut `sub` menciptakan sisi ke arah bawah, sedangkan atribut `super` menciptakan sisi ke arah atas. Dengan demikian, struktur ini bisa dilihat sebagai *graf berarah* yang bukan pohon murni. Namun, lebih mudah membayangkannya sebagai *pohon tak berarah*, di mana hubungan antara takson dan taksa anaknya bersifat dua arah, seperti jalur yang bisa dilalui ke atas atau ke bawah.

![](attachment/Pasted%20image%2020250514102000.png)

Data hierarki taksa diambil dari file dalam format CSV. Setiap baris file mendefinisikan sebuah takson dengan bidang-bidang berikut:
- Nama ilmiah, untuk atribut `scientific`.
- Nama umum, bisa kosong, untuk atribut `common`.
- Peringkat, untuk atribut `rank`.
- Nama ilmiah takson induk, bisa kosong, untuk atribut `super`.

Atribut `sub` tidak perlu disertakan dalam file, karena dapat diturunkan dari atribut `super` pada taksa lain. Misalnya, baris untuk genus *Bubo* mungkin terlihat seperti ini:

```
Bubo,horned owl,genus,Strigidae
```

File taksa diurutkan berdasarkan peringkat, dari yang tertinggi ke yang terendah, sehingga baris untuk *Strigidae* akan muncul sebelum baris untuk *Bubo*. Selain urutan peringkat ini, baris-baris dalam file tidak memiliki urutan khusus. Karena adanya urutan parsial ini, file tersebut tidak sepenuhnya mewakili relasi matematis murni, melainkan struktur yang dikenal sebagai *partially ordered set* (himpunan terurut sebagian), yang tidak dibahas secara mendalam dalam buku ini.

Konstruktor kelas `Taxon` menerima bidang-bidang dari baris file sebagai argumen. Metode `__init__` mengisi atribut `scientific`, `common`, dan `rank`, serta menginisialisasi `count` ke nol. Jika bidang `super` tidak kosong, `__init__` juga harus mencari objek `Taxon` untuk takson induk, mengatur atribut `super` ke objek tersebut, dan menambahkan takson saat ini ke himpunan `sub` milik takson induk. Pertanyaannya, bagaimana kita menemukan objek takson induk?

Untuk ini, kita menggunakan sebuah kamus bernama `taxon` yang memetakan nama ilmiah ke objek `Taxon`. Selain itu, kita juga menyimpan kamus `taxonByCommon` untuk memetakan nama umum ke objek `Taxon` (kegunaannya akan dijelaskan nanti). Setiap kali objek `Taxon` baru dibuat, metode `__init__` menambahkan entri ke kamus-kamus ini.

Karena file taksa diurutkan berdasarkan peringkat, saat `__init__` dipanggil untuk sebuah takson, objek `Taxon` untuk takson induknya sudah ada di kamus `taxon`. (Catatan: Dalam studi kasus ini, kita tidak membahas penanganan kesalahan, seperti baris file yang salah urutan atau data yang hilang.) Untuk atribut `sub`, kita menginisialisasinya sebagai himpunan kosong, yang kemudian akan diisi saat baris-baris berikutnya dari file diproses.

Berikut adalah kode awal yang kita miliki sejauh ini:

```python
taxon = {}
taxonByCommon = {}

class Taxon:

    def __init__(self, scientific, common, rank, super):
        self.scientific = scientific
        self.common = common
        self.rank = rank
        self.count = 0
        self.sub = set()
        
        if super != "":
            superObject = taxon[super]
            self.super = superObject
            superObject.sub.add(self)
        else:
            self.super = None
            
        taxon[scientific] = self
        if common != "":
            taxonByCommon[common] = self
```

Kita juga memberikan kelas `Taxon` metode sederhana bernama `add` untuk mencatat jumlah kemunculan takson yang dilaporkan oleh peserta survei:

```python
def add(self, n):
    self.count += n
```

Ketika peserta melaporkan jumlah untuk sebuah takson, kita menggunakan kamus `taxon` atau `taxonByCommon` (tergantung apakah mereka memberikan nama ilmiah atau nama umum) untuk menemukan objek `Taxon` yang sesuai, lalu memanggil metode `add`.

Sekarang, kita sampai pada fitur utama program ini: metode `total`. Metode ini menghitung jumlah total kemunculan sebuah takson, termasuk jumlah yang dicatat langsung untuk takson itu sendiri (*self.count*) dan jumlah dari semua taksa anaknya hingga ke peringkat terendah dalam hierarki. Perhitungan ini bersifat rekursif: kita menjumlahkan `count` takson saat ini dengan hasil dari pemanggilan `total` pada setiap takson dalam `sub`. Berikut kodenya, yang ternyata sangat sederhana:

```python
def total(self):
    return self.count + \
           sum(t.total() for t in self.sub)
```

Rekursi ini tidak perlu mendefinisikan kasus dasar secara eksplisit. Kasus dasar terjadi secara alami ketika `sub` kosong, yaitu pada taksa di peringkat terendah, sehingga tidak ada panggilan rekursif lebih lanjut.

Dalam kode di atas, `sum` adalah fungsi yang menjumlahkan elemen-elemen dalam sebuah urutan. Berikut adalah definisi sederhana dari fungsi ini, mirip dengan yang dibahas di Bagian 6.4, menggunakan fungsi `reduce`:

```python
def sum(seq):
    return reduce(lambda x, y: x + y, seq, 0)
```

Dengan metode `total`, kita bisa menghasilkan laporan yang menunjukkan jumlah kemunculan sebuah takson dan semua taksa anaknya hingga ke bawah hierarki. Misalnya, dalam survei burung, laporan untuk ordo *Strigiformes* setelah beberapa waktu mungkin terlihat seperti ini:

```
8 Strigiformes (owl)
  7 Strigidae (typical owl)
    2 Asio (eared owl)
      1 Asio otus (Long-eared Owl)
      1 Asio flammeus (Short-eared Owl)
    0 Athene ()
      0 Athene cunicularia (Burrowing Owl)
    5 Bubo (horned owl)
      5 Bubo virginianus (Great Horned Owl)
  1 Tytonidae (barn owl)
    1 Tyto (barn owl)
      1 Tyto alba (Common Barn Owl)
```

Untuk menghasilkan laporan seperti ini, kita menambahkan metode rekursif bernama `report` ke kelas `Taxon`. Metode ini mencetak satu baris untuk takson saat ini, lalu secara rekursif memanggil dirinya sendiri untuk setiap takson anak, dengan indentasi yang bertambah dua spasi untuk setiap level hierarki. Berikut kodenya:

```python
def report(self, indent): 
    print(indent + self.total() \ 
                 + " " + self.scientific 
                 + " (" + self.common + ")) 
    for sub in self.sub: 
        sub.report(indent + " ")
```

Setelah program selesai membaca file taksa, kita bisa mengakses semua objek `Taxon` melalui `taxon.values()`. Ini sebenarnya adalah aliran (*stream*), tetapi karena tidak memiliki urutan tertentu, kita bisa memperlakukannya sebagai himpunan. Kita bisa mengiterasinya, memfilternya, atau melakukan operasi lain seperti mengubahnya menjadi himpunan.

Salah satu kegunaan `taxon.values()` adalah untuk menemukan akar-akar dari semua pohon taksa. Dalam beberapa survei, seperti survei burung, mungkin ada satu pohon besar dengan akar *Aves*. Namun, dalam kasus lain, seperti survei padang rumput, mungkin ada beberapa pohon (misalnya, satu untuk rumput dan satu untuk bunga liar). Dalam matematika, kumpulan pohon seperti ini disebut *forest* (hutan). Kita bisa mendapatkan himpunan akar semua pohon ini dengan *comprehension* sederhana:

```python
allTrees = { order in values(taxon)
     if order.super == None }
```

Kemudian, kita bisa menghasilkan laporan lengkap untuk semua taksa, dikelompokkan berdasarkan pohonnya:

```python
for t in allTrees:
    t.report("")
```

Seperti program daftar lagu, Anda mungkin bisa memikirkan fitur tambahan yang berguna untuk program ini.

Bayangkan Anda diminta untuk mengembangkan program ini. Setelah menyelesaikan desain sesuai uraian di atas dan mengirimkannya untuk ditinjau, ternyata atasan Anda meminta beberapa perubahan karena ada persyaratan tambahan yang terlewat.

**Persyaratan pertama**: Taksa anak dari sebuah takson ternyata memiliki urutan resmi, yang disebut *taxonomic sequence* (urutan taksonomi). Laporan yang dihasilkan oleh metode `report` saat ini tidak akan diterima oleh ahli biologi, karena baris-barisnya harus mengikuti urutan taksonomi ini.

**Persyaratan kedua**: Beberapa taksa memiliki lebih dari satu nama umum. Ini bisa terjadi karena nama umum berubah seiring waktu, dan beberapa peserta mungkin menggunakan nama lama dari panduan lapangan yang sudah usang. Selain itu, dalam beberapa kasus, survei mungkin ingin menganggap dua nama umum sebagai setara, misalnya “Snow Goose” dan “Blue Goose” (yang sebenarnya adalah spesies yang sama, dengan “Blue Goose” sebagai varian warna).

Atasan Anda meminta maaf karena tidak menyampaikan detail ini sebelumnya dan meminta Anda untuk merevisi program.

Untungnya, perubahan yang diperlukan ternyata cukup sederhana. Untuk memenuhi persyaratan pertama, kita mengganti himpunan (`set`) untuk atribut `sub` dengan daftar (`list`), karena daftar mempertahankan urutan elemen. Kita hanya perlu mengubah dua baris dalam metode `__init__`:

```python
self.sub = set()
```

dan

```python
superObject.sub.add(self)
```

menjadi:

```python
self.sub = []
```

dan

```python
superObject.sub.append(self)
```

Kemudian, kita mensyaratkan bahwa baris-baris dalam file taksa diurutkan sesuai urutan taksonomi. Dengan demikian, objek `Taxon` akan dibuat dan ditambahkan ke daftar `sub` dalam urutan yang benar. Akibatnya, metode `report` akan secara otomatis menghasilkan baris-baris dalam urutan taksonomi, tanpa perlu perubahan pada kode perulangannya, karena sekarang mengiterasi daftar alih-alih himpunan.

Untuk persyaratan kedua, kita menambahkan file data baru bernama `synonyms` dalam format CSV, yang memetakan nama-nama umum tambahan ke nama ilmiah. Setiap baris file diubah menjadi tuple menggunakan fungsi `setofTuples` dari Bagian 8.4. Kita mencari nama ilmiah di kamus `taxon` untuk mendapatkan objek `Taxon` yang sesuai, lalu menambahkan entri ke `taxonByCommon` untuk nama umum baru. Kodenya sangat sederhana:

```python
for (common, scientific) in streamOfTuples("synonyms"):
    t = taxon[scientific]
    taxonByCommon[common] = t
```

Nama umum resmi tetap disimpan dalam atribut `common` objek `Taxon`, tetapi semua nama sinonim akan memetakan ke objek `Taxon` yang sama melalui `taxonByCommon`. Dengan demikian, semua nama umum tersebut akan dihitung sebagai bagian dari takson yang sama. Atasan Anda pun puas dengan solusi ini.

Dalam studi kasus ini, struktur matematis utama adalah hierarki taksa, yang pada dasarnya adalah pohon atau, dalam kasus umum, sekumpulan pohon (*forest*). Struktur ini dibangun dari objek-objek rekursif. Dengan adanya atribut `super`, hierarki ini bisa dilihat sebagai *graf berarah*, tetapi juga bisa dianggap sebagai *pohon tak berarah*. Pemetaan (*mapping*) juga memainkan peran penting, seperti kamus `taxon` dan `taxonByCommon`, metode rekursif `total`, dan file `synonyms`. Selain itu, program ini menggunakan himpunan, tuple, dan urutan tuple untuk mengelola data.

### 12.3. Kartu Catatan untuk Penulis

Studi kasus terakhir kita adalah sebuah program untuk membantu penulis mengelola fragmen-fragmen teks, seperti garis besar, catatan, potongan draf, teks jadi, atau kutipan. Program ini ditujukan untuk pelajar yang sedang menulis makalah atau tesis, serta penulis akademik dan profesional yang bekerja pada artikel atau bahkan buku.

Program ini mengadopsi metafora *note card* (kartu catatan), alat tradisional yang digunakan oleh pelajar dan penulis untuk mencatat ide atau referensi selama penelitian. Dalam program ini, kartu-kartu tersebut akan ditampilkan sebagai jendela di layar komputer, memberikan pengalaman visual yang intuitif.

![](attachment/Pasted%20image%2020250514102949.png)

Kita bergabung dengan proyek pengembangan perangkat lunak ini di tahap awal. Tim pengembang belum sepenuhnya memutuskan fitur-fitur apa yang akan disertakan atau bagaimana program akan bekerja secara detail, tetapi mereka sudah memiliki beberapa ide awal. Berikut adalah beberapa di antaranya.

Pengguna dapat membuat **tautan** antar kartu catatan, mirip dengan tautan antar halaman web. Tautan ini tidak terbatas pada kartu catatan lain, tetapi juga bisa menunjuk ke:
- Halaman web.
- Dokumen digital (misalnya dalam format PDF atau Postscript), bahkan hingga ke bagian tertentu dalam dokumen.
- Entri dalam basis data bibliografi.

Pengguna juga dapat menambahkan **kata kunci** ke kartu catatan, serta **pasangan kunci-nilai**. Misalnya, sebuah kartu mungkin memiliki dua kata kunci dan satu pasangan kunci-nilai, di mana nilainya bisa berupa tautan, seperti ke entri dalam basis data bibliografi.

![](attachment/Pasted%20image%2020250514103037.png)

Program ini memungkinkan pengguna untuk **mencari** kartu berdasarkan kata kunci tertentu atau nilai yang terkait dengan kunci tertentu. Selain itu, pengguna juga bisa melakukan pencarian lain, seperti mencari kartu yang berisi teks tertentu.

Beberapa kata kunci digunakan untuk mengkategorikan kartu berdasarkan perannya, seperti “outline” (garis besar), “synopsis” (sinopsis), atau “draft” (draf). Operasi tertentu lebih sering dilakukan pada kartu dengan peran yang sama, misalnya: Membagi satu kartu menjadi beberapa kartu yang lebih pendek; Menggabungkan beberapa kartu menjadi satu kartu yang lebih panjang; Menentukan urutan antar kartu.

Seiring pengguna mengerjakan dokumen, mengatur dan menggabungkan fragmen teks menjadi semakin penting. Tujuan akhirnya adalah menghasilkan dokumen sebagai urutan teks yang utuh, mungkin disusun dari isi kartu-kartu dengan peran seperti “draft” atau “final”. Namun, selama proses penulisan, pengguna mungkin ingin melihat gambaran sementara dokumen mereka, misalnya dengan menyusun garis besar, sinopsis, atau draf dari beberapa atau semua kartu catatan.

Sebagai contoh, bayangkan kartu-kartu dengan peran “outline”. Misalkan satu kartu berisi garis besar tingkat atas dari sebuah dokumen, dengan tautan ke kartu-kartu lain yang berisi garis besar lebih rinci untuk bagian-bagian tertentu. Kartu-kartu tersebut mungkin juga memiliki tautan ke kartu lain dengan peran serupa, dan seterusnya. Struktur ini membentuk sebuah **pohon**:

![](attachment/Pasted%20image%2020250514103205.png)

Pengguna mungkin ingin menggabungkan semua kartu ini menjadi satu garis besar yang terstruktur, dengan indentasi seperti laporan survei burung di Bagian 12.2. Operasi ini bisa diprogram secara rekursif, mirip dengan metode `report` pada studi kasus sebelumnya.

Namun, bagaimana jika tautan-tautan ini membentuk **graf berarah** yang bukan pohon—yaitu, jika ada kartu yang ditunjuk oleh lebih dari satu tautan? 

![](attachment/Pasted%20image%2020250514103243.png)

Apa yang harus dilakukan program dengan kartu seperti itu? Haruskah isi kartu dimasukkan saat pertama kali ditemukan, setelah semua tautan yang menunjuk ke kartu itu diproses, atau bahkan beberapa kali? Bagaimana jika pengguna secara tidak sengaja membuat **siklus** dalam graf (misalnya, kartu A menunjuk ke B, B ke C, dan C kembali ke A)? Ini adalah beberapa pertanyaan desain yang masih diperdebatkan oleh tim pengembang.

Dalam beberapa kasus, solusi terbaik mungkin adalah menyerahkan pengurutan kepada pengguna. Misalnya, program bisa menampilkan kartu-kartu seolah-olah tersebar di atas meja, dan pengguna bisa menggeser atau menyusunnya melalui antarmuka grafis program. 

![](attachment/Pasted%20image%2020250514103315.png)

Pendekatan ini juga bisa digunakan saat pengguna melakukan pencarian: program menampilkan kartu-kartu yang memenuhi kriteria pencarian seperti kartu di atas meja, lalu pengguna bisa mengatur urutan atau melakukan operasi lain.

Jelas, tim pengembang masih memiliki banyak pekerjaan dan keputusan yang harus dibuat. Namun, berdasarkan gambaran yang sudah ada, mari kita analisis program ini dari perspektif struktur matematis diskret.

Kita bisa mendefinisikan sebuah kartu catatan sebagai **4-tuple** dengan komponen berikut:
- **Judul**: Urutan karakter (string).
- **Isi**: Teks yang mungkin berisi tautan.
- **Kata kunci**: Himpunan kata kunci (bisa kosong), dengan setiap kata kunci berupa urutan karakter.
- **Pasangan kunci-nilai**: Relasi (bisa kosong), di mana setiap kunci adalah urutan karakter dan setiap nilai adalah teks yang mungkin berisi tautan.

Tim pengembang belum memutuskan bagaimana merepresentasikan “teks yang mungkin berisi tautan”. Salah satu opsi adalah menggunakan pendekatan seperti HTML, di mana tautan direpresentasikan sebagai urutan karakter khusus, misalnya `<a href="next">Next</a>`. Dalam kasus ini, teks dengan tautan hanyalah urutan karakter biasa. Alternatifnya, tautan bisa direpresentasikan sebagai objek Python terpisah, sehingga teks menjadi urutan elemen dari gabungan dua himpunan: himpunan string dan himpunan objek tautan. Dalam kedua kasus, representasinya tetap berupa urutan.

Kumpulan semua kartu catatan membentuk sebuah **himpunan**. Tautan antar kartu menciptakan struktur tambahan: sebuah **graf berarah**, dengan kartu sebagai simpul (*vertex*) dan tautan sebagai sisi (*edge*). Beberapa bagian graf, seperti yang membentuk garis besar, mungkin berupa pohon. Jika kita juga mempertimbangkan tautan ke objek eksternal (misalnya halaman web), graf ini menjadi lebih besar. Pengguna bisa mengubah bagian dari graf atau pohon ini menjadi urutan teks dengan berbagai cara.

Hasil dari sebuah pencarian adalah **subset** dari himpunan kartu catatan. Pengguna bisa mengubah subset ini menjadi urutan, misalnya untuk menyusun dokumen.

Secara keseluruhan, dari deskripsi yang ada, program ini sudah melibatkan beberapa struktur matematis: *tuple* untuk kartu catatan, *urutan* untuk teks dan tautan, *himpunan* untuk kartu dan kata kunci, *relasi* untuk pasangan kunci-nilai, *pohon* untuk garis besar, dan *graf berarah* untuk tautan. Seperti studi kasus sebelumnya, program ini memanfaatkan hampir semua struktur matematis yang telah dibahas dalam buku ini. Pengetahuan tentang struktur-struktur ini pasti akan membantu tim pengembang dalam merancang dan menyempurnakan program.

**Latihan**
1. Dalam program daftar lagu (Bagian 12.1), kita merepresentasikan lagu sebagai tuple. Sebagai alternatif, kita bisa mendefinisikan kelas `Tune` dan merepresentasikan setiap lagu sebagai instance kelas tersebut. Apa kelebihan dan kekurangan pendekatan ini dibandingkan dengan penggunaan tuple?

2. Alternatif lain adalah merepresentasikan lagu sebagai kamus yang memetakan nama atribut (misalnya “artist”, “title”) ke nilai atributnya. Apa kelebihan dan kekurangan representasi ini?

3. Pilih salah satu program yang dibahas dalam bab ini. Usulkan sebuah fitur baru yang memanfaatkan struktur matematis yang belum digunakan oleh program tersebut. Pastikan struktur matematis yang Anda pilih sesuai dengan kebutuhan fitur tersebut.

[back](./)
