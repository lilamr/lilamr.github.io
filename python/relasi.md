[Home](../)

[back](./)

## Bab 10: Relasi

### 10.1. Istilah dan Notasi dalam Matematika

Konsep relasi pertama kali kita temui di Bagian 1.3, di mana relasi didefinisikan sebagai himpunan pasangan terurut. Namun, seperti yang telah dibahas pada Bagian 5.3, dalam matematika, relasi memiliki cakupan yang lebih luas, yaitu sebagai himpunan *n-tuple* untuk nilai *n* apa pun.  

Relasi yang terdiri dari pasangan terurut disebut *relasi biner*, seperti yang telah kita pelajari sebelumnya. Untuk relasi dengan *n-tuple* yang lebih besar, terdapat istilah khusus; misalnya, himpunan *3-tuple* disebut *relasi ternari*, dan himpunan *4-tuple* disebut *relasi kuaternari*. Istilah umum untuk ini adalah *relasi n-ari*. Seperti halnya *n-tuple*, kita dapat mengganti *n* dengan angka tertentu, sehingga *relasi ternari* sama dengan *relasi 3-ari*. Sebagai contoh, data dalam file *populations* pada Bagian 9.2 secara konseptual merupakan *relasi 3-ari*: himpunan *triple* yang masing-masing berisi nama kota, kota lain, dan jarak di antara keduanya.  

Ketika sebuah *n-tuple* termasuk dalam suatu relasi, kita sering mengartikan hal ini sebagai adanya hubungan tertentu di antara elemen-elemen dalam *n-tuple* tersebut. Misalnya, bayangkan sebuah relasi yang didefinisikan oleh data dalam file *emails* pada Contoh 1.2. Jika kita namakan relasi ini *E*, maka notasi *(x, e) ∈ E* menunjukkan bahwa seseorang bernama *x* memiliki alamat email *e*.  

Dalam matematika, relasi biner sering diperlakukan sebagai *operator biner*. Sebagai contoh, jika *(x, e) ∈ E*, kita juga bisa menulis *x E e*. Sebaliknya, sebuah *operator biner* yang menghasilkan nilai *benar* atau *salah*—yaitu *operator Boolean*—dapat mendefinisikan sebuah relasi biner. Contohnya, operator "=" dalam matematika menciptakan relasi yang berisi pasangan *(a, a)* untuk setiap *a* dalam *universum wacana*. (Jika *universum* ini tak hingga, maka relasinya juga tak hingga, menunjukkan bahwa relasi tidak selalu terbatas.) Kita bahkan bisa menggunakan operator itu sendiri sebagai nama relasi, sehingga menulis *(a, a) ∈ =*.  

Lebih jauh, sebuah *relasi n-ari* dapat dianggap mendefinisikan sebuah *predikat*, yaitu pernyataan tentang *n* objek yang bernilai *benar* jika *n-tuple* dari objek-objek tersebut ada dalam relasi, dan *salah* jika tidak. Sebaliknya, sebuah pernyataan seperti ini juga dapat mendefinisikan sebuah relasi. Notasi fungsi sering dipakai untuk predikat: misalnya, jika *P* adalah *relasi 3-ari* dan *(a, b, c) ∈ P*, maka *P(a, b, c)* bernilai *benar*. Sebaliknya, jika *(a, b, c) ∉ P*, maka *P(a, b, c)* bernilai *salah*.  

Terkadang, kita menggunakan nama yang lebih deskriptif ketimbang sekadar huruf atau simbol untuk relasi, operator, atau predikat. Matematikawan dan ilmuwan komputer memang dikenal cukup fleksibel dalam memilih notasi. Misalnya, kita bisa menulis *equals* alih-alih "=", atau *hasEmail* untuk relasi pada Contoh 1.2. Kita juga sering menggunakan notasi relasi, operator, dan predikat secara bergantian, sehingga dalam tabel berikut, setiap baris menunjukkan ekspresi dengan makna yang sama:  

| Relasi              | Operator       | Predikat         |
| ------------------- | -------------- | ---------------- |
| *(x, e) ∈ E*        | *x E e*        | *E(x, e)*        |
| *(a, b) ∈ =*        | *a = b*        | *= (a, b)*       |
| *(a, b, c) ∈ P*     |                | *P(a, b, c)*     |
| *(a, b) ∈ equals*   | *a equals b*   | *equals(a, b)*   |
| *(x, e) ∈ hasEmail* | *x hasEmail e* | *hasEmail(x, e)* |

*Relasi 1-ari* (himpunan *tuple* dengan satu elemen) jarang digunakan, tetapi *predikat* dengan satu argumen cukup umum dalam matematika. Predikat semacam ini biasanya diartikan sebagai sifat yang mungkin dimiliki atau tidak dimiliki oleh suatu objek, sehingga predikat tersebut mendefinisikan sebuah *himpunan*, bukan relasi. Misalnya, predikat *P* dengan satu argumen mendefinisikan himpunan semua *a* di mana *P(a)* bernilai *benar*. Sebagai contoh dari Bagian 8.1, misalkan *`smallOdd(n)`* berarti "*0 < n < 100* dan *n* adalah bilangan ganjil". Maka, *`smallOdd`* mendefinisikan himpunan bilangan yang memenuhi sifat tersebut, yaitu `{n | smallOdd(n)}`.  

Jika sebuah relasi *R* terdiri dari *n-tuple* yang semua elemennya berasal dari himpunan yang sama, katakanlah *A*, kita menyebut *R* sebagai *relasi pada A*. Himpunan *A* ini merupakan sifat penting dari relasi tersebut. Sebagai contoh, banyak relasi biner yang signifikan dalam matematika dan ilmu komputer dilambangkan dengan *operator biner*, tetapi jika operator tersebut *overloaded* (memiliki makna berbeda tergantung konteks), kita perlu tahu himpunan tempat relasi tersebut didefinisikan untuk memahami relasi yang dimaksud. Misalnya, relasi "<" pada bilangan bulat berbeda dengan relasi "<" pada bilangan riil, karena keduanya adalah himpunan pasangan terurut yang berbeda.  

Perhatikan bahwa setiap relasi selalu didefinisikan pada suatu himpunan, baik secara eksplisit maupun implisit. Himpunan terkecil yang memenuhi definisi "pada" diimplikasikan oleh *n-tuple* dalam relasi tersebut. Jika relasi diberikan tetapi himpunannya tidak disebutkan, dan relasinya terbatas serta cukup kecil, kita dapat menentukan himpunan tersebut dari relasi itu sendiri.  

Para matematikawan telah mengidentifikasi beberapa sifat penting dari relasi biner, dan berikut adalah beberapa di antaranya. Relasi biner *R* bersifat *simetris* jika setiap kali pasangan *(a, b)* ada dalam *R*, maka *(b, a)* juga ada dalam *R*. Contohnya, relasi "=" pada bilangan bulat bersifat simetris, karena jika *a = b*, maka *b = a*.  

Sebaliknya, relasi biner *R* bersifat *antisimetris* jika setiap kali *(a, b)* ada dalam *R*, maka *(b, a)* tidak ada dalam *R*. Misalnya, relasi "<" pada bilangan bulat bersifat antisimetris. Namun, fakta bahwa *(b, a)* tidak ada dalam *R* tidak berarti *(a, b)* pasti ada dalam *R*; coba perhatikan relasi "<" untuk pasangan *(3, 3)*.  

Relasi biner *R* bersifat *transitif* jika setiap kali *(a, b) ∈ R* dan *(b, c) ∈ R*, maka *(a, c) ∈ R*. Relasi "=" dan "<" pada bilangan bulat keduanya bersifat transitif.  

Jika *R* adalah relasi pada himpunan *A*, maka *R* bersifat *refleksif* jika *(a, a) ∈ R* untuk setiap *a ∈ A*. Misalnya, relasi "=" pada bilangan bulat bersifat refleksif, tetapi "<" tidak.  

Relasi biner yang bersifat *simetris*, *transitif*, dan *refleksif* disebut *relasi ekuivalensi*. Contohnya adalah relasi "=" pada bilangan bulat atau "lahir pada tahun yang sama" untuk pasangan orang.  

Tidak sulit untuk membuktikan bahwa sebuah *relasi ekuivalensi R* pada himpunan *A* menghasilkan *partisi* pada *A*, yaitu kumpulan himpunan bagian dari *A* di mana setiap elemen *A* termasuk dalam tepat satu himpunan bagian. Relasi *R* memisahkan *A* menjadi kelompok-kelompok elemen yang dianggap ekuivalen menurut *R*.  

Relasi yang hanya berisi pasangan *(a, a)* untuk setiap *a ∈ A* disebut *relasi identitas* pada *A*, sering ditulis $$I_A$$. Relasi ini juga merupakan sebuah *pemetaan*, yang kadang disebut *pemetaan identitas* atau *fungsi identitas* pada *A*.  

*Komposisi* relasi biner didefinisikan seperti komposisi pemetaan (lihat Bagian 9.1). Untuk dua relasi *R* dan *S*,  

$$S \circ R = \{(a, c) \mid (a, b) \in R \text{ dan } (b, c) \in S\}$$

*Pangkat* relasi biner juga didefinisikan seperti pada pemetaan: untuk relasi *R*, kita tulis *R²* untuk *$$R \circ R$$*, *R³* untuk *$$R \circ R \circ R$$*, dan seterusnya. Kita mendefinisikan *R⁰* sebagai himpunan semua pasangan *(a, a)* dan *(b, b)* untuk setiap *(a, b) ∈ R*, yaitu *R⁰ = $$I_A$$* untuk *A* terkecil yang mendefinisikan *R*. Sedangkan *R¹* jelas sama dengan *R*.  

### 10.2. Representasi dalam Program  

Dalam pemrograman, relasi sering kali perlu direpresentasikan dan diproses. Saat mengimplementasikan relasi, seorang programmer menghadapi dilema yang mirip dengan saat mengimplementasikan pemetaan atau *multiset*. Haruskah relasi direpresentasikan sebagai struktur data, hasil perhitungan, atau kombinasi keduanya? Jika menggunakan struktur data, jenis apa yang paling sesuai?  

Dalam Python, cara paling langsung untuk merepresentasikan relasi adalah sesuai definisinya: sebagai himpunan *tuple*. Representasi ini memudahkan beberapa operasi, seperti mengiterasi semua *tuple* dalam relasi atau memeriksa apakah suatu *tuple* tertentu ada dalam relasi.  

Namun, dalam kasus tertentu, representasi lain mungkin lebih praktis. Misalnya, untuk relasi biner yang berisi pasangan *(a, b)*, jika operasi yang paling sering dilakukan adalah mencari semua nilai *b* yang terkait dengan *a* tertentu, maka merepresentasikan relasi sebagai pemetaan dari *a* ke himpunan nilai *b* bisa lebih efisien. Namun, pendekatan ini menyulitkan pencarian nilai *a* berdasarkan *b*, jika operasi tersebut juga diperlukan.  

Terkadang, representasi berbasis perhitungan lebih baik daripada struktur data, sama seperti pada pemetaan, dengan alasan yang serupa (lihat Bagian 9.4). Ada dua pendekatan utama untuk implementasi berbasis perhitungan:  
- Sebagai kode yang menghasilkan daftar *tuple* dalam relasi, misalnya melalui *fungsi generator* atau *ekspresi generator* di Python. Dalam beberapa kasus, program hanya memerlukan aliran atau urutan semua *tuple*. Bahkan jika relasinya sangat besar atau tak hingga, program mungkin hanya membutuhkan sebagian *tuple* dan bisa mengambil hanya sebagian awal dari urutan tersebut. Namun, pendekatan ini sering kali kurang fleksibel dibandingkan alternatif berikut:  
- Sebagai *predikat*, yaitu fungsi yang menerima *n* argumen atau sebuah *tuple* berisi *n* nilai, lalu mengembalikan nilai *True* atau *False* berdasarkan keberadaan *n-tuple* tersebut dalam relasi. Fungsi ini dapat melakukan perhitungan apa pun yang diperlukan untuk menentukan hasilnya.  

Seperti halnya pemetaan, menggabungkan struktur data dan perhitungan dalam sebuah predikat bisa sangat efektif. Misalnya, hasil perhitungan dapat disimpan (*memoized*) untuk mempercepat pemrosesan di masa depan.  

Kita juga bisa memanfaatkan sifat-sifat khusus relasi, seperti yang dijelaskan sebelumnya, untuk menyimpulkan keberadaan *tuple* tertentu tanpa menyimpannya secara eksplisit. Misalnya, jika relasi *r* bersifat *simetris*, kita bisa membuat himpunan Python bernama *rStored* yang hanya berisi pasangan *(a, b)* dalam satu arah, tanpa menyertakan pasangan *(b, a)*. Predikat untuk relasi ini dapat diimplementasikan dengan menambahkan logika ke *rStored*, seperti berikut:  

```python
# Predikat r(a, b):
# Apakah pasangan (a, b) ada dalam relasi simetris r?
def r(a, b):
    if (a, b) in rStored:
        return True
    elif (b, a) in rStored:
        return True
    return False
```  

Atau, secara lebih ringkas:  

```python
def r(a, b):
    return (a, b) in rStored or (b, a) in rStored
```  

Pendekatan ini mengurangi jumlah data yang perlu disimpan hingga setengahnya. Demikian pula, untuk relasi *refleksif*, kita tidak perlu menyimpan semua pasangan *(a, a)* untuk setiap *a* dalam himpunan yang menjadi basis relasi. Jika predikat hanya akan dipanggil untuk pasangan nilai dalam himpunan tersebut, kita bisa menulis: 

```python
# Predikat r(a, b):
# Apakah pasangan (a, b) ada dalam relasi refleksif r?
def r(a, b):
    return a == b or (a, b) in rStored
```  

Teknik serupa dapat diterapkan pada relasi yang bukan biner, tetapi memiliki sifat simetris atau refleksif dalam pengertian tertentu. Misalnya, pada contoh di Bagian 9.4 tentang jarak antar kota, kita bisa memandang data tersebut sebagai *relasi 3-ari* yang setiap *triple*-nya terdiri dari dua kota dan jarak di antara keduanya. Karena kebanyakan jalan antar kota bersifat dua arah, jaraknya biasanya sama dalam kedua arah, sehingga relasi ini bersifat simetris dalam hal ini. Selain itu, kita bisa menganggap jarak dari sebuah kota ke dirinya sendiri sebagai nol, yang merupakan semacam sifat refleksif.  

Dengan asumsi ini, kita bisa membuat struktur *dictionary-of-dictionaries* bernama *distanceStored* yang hanya menyimpan jarak antar kota berbeda dalam satu arah, lalu menulis fungsi jarak seperti pada Contoh 10.1 berikut. Implementasi ini mengurangi jumlah data yang disimpan dan mungkin juga usaha untuk menghasilkan data tersebut, meski dengan konsekuensi waktu komputasi yang lebih lama dan kode yang lebih kompleks. Pertimbangan seperti ini sering muncul dalam desain perangkat lunak.  

**Contoh 10.1. Jarak dengan Memanfaatkan Simetri dan Refleksivitas**  

```python
def distance(city, othercity):
    if city == othercity:
        return 0.0
    elif city in distanceStored and othercity in distanceStored[city]:
        return distanceStored[city][othercity]
    elif othercity in distanceStored and city in distanceStored[othercity]:
        return distanceStored[othercity][city]
    return float("inf")  # Tidak ada koneksi jalan yang datanya tersedia
```  

Menangani relasi *transitif* jauh lebih rumit, dan pendekatan serupa tidak akan berhasil. Misalkan kita ingin membuat predikat *r* untuk relasi transitif berdasarkan data minimal dalam *rStored*. Kita harus mengembalikan *True* untuk pasangan *(a, c)* jika ada pasangan *(a, b)* dan *(b, c)* dalam *rStored* untuk suatu *b*. Namun, bagaimana cara menemukan *b* tersebut? Lebih sulit lagi, kita perlu mengembalikan *True* untuk pasangan *(a, d)* jika ada pasangan *(a, b)*, *(b, c)*, dan *(c, d)* dalam *rStored* untuk suatu *b* dan *c*, dan seterusnya untuk rantai yang lebih panjang. Kita akan membahas cara mengatasi tantangan ini di Bagian 10.4.  

### 10.3. Graf (Graphs)

Dalam matematika, *graf* adalah representasi visual berupa titik-titik (atau objek lain) yang dihubungkan oleh garis, atau sebagai objek matematis yang merepresentasikan diagram tersebut. Dalam bahasa sehari-hari, kita mungkin menganggap "graf" sebagai plot data seperti pada Gambar 1.1, tetapi dalam matematika, istilah ini memiliki makna khusus. Berikut adalah contoh graf dalam bentuk diagram.  

![](attachment/Pasted%20image%2020250510131808.png)

Secara matematis, graf biasanya didefinisikan sebagai pasangan terurut *(V, E)*, di mana *V* adalah himpunan *simpul* (atau *vertex*, bentuk tunggal dari *vertices*) dan *E* adalah kumpulan *sisi* (atau *edge*). Dari definisi dasar ini, terdapat berbagai variasi tergantung pada bagaimana *V* dan *E* didefinisikan. Penulis yang berbeda menggunakan definisi dan istilah yang berbeda, menghasilkan jenis graf dengan sifat yang beragam.[^1] Semua definisi yang akan kita bahas di sini menggunakan struktur matematika diskrit yang telah kita pelajari sepanjang buku ini, dan sangat menarik untuk melihat bagaimana struktur-struktur ini dapat dikombinasikan untuk mengekspresikan berbagai konsep.  

Dalam *graf tak berarah*, sisi tidak memiliki arah dan hanya berupa garis yang menghubungkan dua simpul, seperti pada contoh sebelumnya. Sebaliknya, dalam *graf berarah*, setiap sisi memiliki arah, seperti panah dari satu simpul ke simpul lain, seperti pada contoh berikut. Sisi dalam graf berarah sering disebut *sisi berarah* atau *busur* (*arc*).  

![](attachment/Pasted%20image%2020250510131840.png)

Baik pada graf berarah maupun tak berarah, *loop* adalah sisi yang menghubungkan simpul dengan dirinya sendiri. Dua graf sebelumnya tidak memiliki loop, tetapi graf berikut memiliki satu loop.  

![](attachment/Pasted%20image%2020250510131953.png)

Dalam salah satu definisi graf berarah, *E* adalah himpunan pasangan terurut dari simpul (elemen *V*). Dalam definisi graf tak berarah, *E* adalah himpunan dari himpunan dua elemen simpul, karena simpul-simpul tersebut tidak memiliki urutan.  

Namun, definisi terakhir ini tidak memungkinkan graf tak berarah memiliki *loop*, karena sebuah himpunan tidak dapat berisi dua elemen yang sama. Untuk mengizinkan *loop*, sisi harus didefinisikan sebagai *multiset* dua elemen, bukan himpunan biasa.  

Sejauh ini, sisi dalam graf hanya menunjukkan bahwa dua simpul terhubung. Namun, dalam beberapa kasus, graf perlu menunjukkan bahwa ada lebih dari satu koneksi antara dua simpul, yang disebut *sisi ganda* (*multiple edges*). Misalnya, dalam graf yang merepresentasikan Internet, simpul mungkin mewakili komputer atau situs komputasi, dan sisi (mungkin tak berarah) mewakili tautan komunikasi fisik atau virtual. Di beberapa tempat, Internet memiliki beberapa tautan antar situs untuk meningkatkan kapasitas atau keandalan. Graf yang digunakan untuk perutean pesan atau paket kemungkinan perlu menyertakan *sisi ganda* untuk mencerminkan tautan-tautan tersebut.  

Definisi graf (berarah atau tak berarah) yang menjadikan *E* sebagai himpunan sisi tidak mengizinkan *sisi ganda*. Salah satu solusi adalah mendefinisikan *E* sebagai *multiset* dari pasangan, himpunan, atau *multiset* simpul.  

Pendekatan lain yang diambil beberapa matematikawan adalah mendefinisikan graf berarah sebagai *4-tuple* *⟨V, E, head, tail⟩*. Di sini, *V* dan *E* adalah himpunan objek abstrak, sedangkan *head* dan *tail* adalah pemetaan dari sisi ke simpul. Untuk graf tak berarah, terdapat satu pemetaan dari sisi ke himpunan atau *multiset* dua elemen simpul. Definisi ini memungkinkan *sisi ganda*, karena setiap elemen *E* dianggap berbeda meskipun memiliki ujung yang sama.  

Perhatikan bahwa semua definisi ini memungkinkan graf memiliki kelompok simpul yang tidak terhubung oleh sisi apa pun, bahkan mungkin ada simpul yang *terisolasi*, tidak terhubung sama sekali. 

![](attachment/Pasted%20image%2020250510132023.png)

Sayangnya, literatur matematika dan ilmu komputer tidak konsisten dalam hal definisi dan terminologi graf. Dalam banyak buku teks matematika, "graf" merujuk pada *graf tak berarah* tanpa *loop* atau *sisi ganda*. Istilah *graf berarah* dan *graf tak berarah* pun sering kali hanya mencakup graf tanpa *loop* atau *sisi ganda*. Buku-buku ini mungkin tidak menyebutkannya secara eksplisit, tetapi definisinya menyiratkan hal tersebut. Graf yang mengizinkan *loop* atau *sisi ganda* biasanya disebut *multigraf* atau istilah lain.  

Sebaliknya, ada pula definisi yang mengizinkan *loop* dan *sisi ganda*, dan dalam kasus ini, graf tanpa keduanya disebut *graf sederhana* (*simple graph*).  

Ketidakseragaman ini kadang menyebabkan kesalahan dalam algoritma pemrograman. Misalnya, seorang programmer mungkin menggunakan definisi *graf* yang hanya cocok untuk *graf sederhana*, lalu membuat algoritma yang tidak menangani *loop* atau *sisi ganda* dengan benar. Oleh karena itu, penting untuk selalu memeriksa definisi dengan cermat!  

Ada hubungan erat antara graf dan relasi biner; keduanya sering kali hanya dua cara berbeda untuk menyampaikan informasi yang sama. Sebuah *graf berarah* *⟨V, E⟩* mendefinisikan *relasi ketetanggaan* pada *V*, yang berisi pasangan terurut *{a, b}* jika *E* memiliki sisi *{a, b}*. Sebaliknya, sebuah relasi biner mendefinisikan *graf berarah* yang memiliki sisi *⟨a, b⟩* jika relasi tersebut berisi *{a, b}*. Untuk *graf tak berarah*, relasinya bersifat *simetris*, dan sebaliknya. Namun, relasi ini tidak dapat menangkap *sisi ganda* yang mungkin ada dalam graf.  

Dalam program, himpunan sisi dari *graf berarah* tanpa *sisi ganda* dapat direpresentasikan seperti relasi biner, dengan pertimbangan desain yang sama. Jika graf memiliki *sisi ganda*, representasi serupa dapat digunakan dengan mengganti relasi biner dengan *multiset* pasangan terurut. Untuk *graf tak berarah*, representasinya bisa menyerupai *graf berarah simetris*, dengan sisi berarah di kedua arah untuk setiap sisi tak berarah. Representasi lain kadang diperlukan untuk mendukung perhitungan tertentu, seperti yang akan dibahas di Bagian 10.4, dan kita akan melihat pendekatan yang berbeda di Bagian 11.6.  

Graf juga dapat diperkaya dengan informasi tambahan. Misalnya, *graf berlabel* memiliki simpul atau sisi (atau keduanya) yang diberi label, seperti nama atau nomor. Dalam graf peta jalan, simpul mungkin diberi label nama kota, dan sisi diberi label nama jalan.  

Pada *graf berarah* dengan sisi berlabel, sisi dapat didefinisikan sebagai *triple* berisi dua simpul dan sebuah label. Jika setiap sisi memiliki label unik, masalah *sisi ganda* hampir teratasi: himpunan *E* dapat didefinisikan sebagai himpunan biasa, dan *sisi ganda* dibedakan oleh labelnya. Hal serupa berlaku untuk *graf tak berarah* berlabel. Jika simpul memiliki label unik, label tersebut bisa menjadi representasi simpul yang praktis dalam program.  

*Graf berbobot* adalah graf di mana setiap sisi memiliki angka yang disebut *bobot*. Makna bobot bergantung pada konteks graf. Misalnya, dalam graf dengan simpul sebagai kota, bobot sisi bisa mewakili jarak jalan (seperti pada Bagian 9.4) atau waktu tempuh dengan kereta atau pesawat. Struktur *dictionary-of-dictionaries* pada Contoh 10.1 menunjukkan salah satu cara merepresentasikan *graf berbobot* dalam program, yaitu dengan memetakan sisi ke bobotnya. Dalam contoh ini, sisi tampaknya tidak memiliki *sisi ganda*. Jika demikian, graf bisa direpresentasikan sebagai himpunan *triple* (dua simpul dan bobot). Namun, jika ada *sisi ganda*, representasi ini tidak akan berfungsi, karena bobot tidak dijamin unik.  

Sebuah graf bisa sekaligus *berlabel* dan *berbobot*. Graf seperti ini sangat umum dalam masalah komputasi.  

### 10.4. Jalur dan Penutupan Transitif

Dalam dunia komputasi, salah satu operasi paling umum pada graf (berarah atau tak berarah) adalah mencari *jalur* dari satu simpul ke simpul lain. *Jalur* dapat didefinisikan sebagai urutan simpul di mana setiap simpul terhubung ke simpul berikutnya oleh sisi, atau sebagai urutan sisi, yang akan menjadi definisi utama kita. Kita juga menganggap ada *jalur dengan panjang nol*—yaitu urutan sisi kosong—dari setiap simpul ke dirinya sendiri. Tidak semua matematikawan menerima *jalur kosong*, tetapi mengizinkannya membantu menyederhanakan algoritma dengan menghindari kasus khusus.  

Banyak program perlu menjawab pertanyaan seperti:  
- Dalam graf tertentu, apakah ada jalur dari simpul *a* ke *b*?  
- Jika ada, berapa panjang *jalur terpendek* (dengan jumlah sisi paling sedikit)?  
- Untuk graf berbobot, berapa panjang *jalur dengan bobot minimum* (jumlah bobot terkecil)?  
- Apakah graf memiliki *siklus* (jalur tak kosong dari simpul ke dirinya sendiri)? Apakah ada siklus yang melibatkan simpul tertentu?  
- Jika graf berlabel, apa urutan label untuk jalur yang menjawab pertanyaan di atas?  
- Apakah graf *terhubung*, yaitu apakah ada jalur dari setiap simpul ke setiap simpul lain?  

Contoh nyata termasuk aplikasi navigasi yang memberikan rute tercepat antar kota atau sistem perutean pesan di Internet.  

Untuk memahami pertanyaan-pertanyaan ini, kita bisa mengalihkan perhatian dari graf ke *relasi ketetanggaannya* dan mempelajari *penutupan transitif (transitive closure)* dari relasi tersebut. *Penutupan transitif* sebuah relasi *R*, dilambangkan *R⁺*, adalah relasi terkecil yang mengandung *R* dan bersifat transitif, yaitu relasi yang diperoleh dengan menambahkan semua pasangan terurut yang diimplikasikan oleh sifat transitif.  

Salah satu cara menghitung *penutupan transitif* adalah dengan pendekatan iteratif. Mulai dari *R*, kita hitung *R²*: untuk setiap pasangan *(a, b)* dalam *R*, cari semua pasangan *(b, c)*, dan himpunan pasangan *(a, c)* membentuk *R²*. Tambahkan *R²* ke hasil, sehingga kita punya *R ∪ R²*. Lanjutkan dengan menghitung *R³* dari *R* dan *R²*, tambahkan ke hasil, dan seterusnya, hingga mendapatkan *R⁺ = R ∪ R² ∪ R³ ∪ …*.  

Jika *R* adalah relasi terbatas (himpunan pasangan terbatas), kita tidak perlu menghitung gabungan tak hingga. Pada akhirnya, tidak ada pasangan baru yang ditambahkan, karena jumlah pasangan yang mungkin terbatas. Kita bisa berhenti ketika *Rᵏ⁺¹* tidak menambahkan pasangan baru ke *R ∪ R² ∪ … ∪ Rᵏ*. Ini adalah sketsa *Algoritma Jelas* untuk menghitung *penutupan transitif*, yang dijamin selesai untuk *R* terbatas.  

Jika *R* adalah *relasi ketetanggaan* graf *G*, pasangan dalam *R²* adalah ujung jalur panjang 2, *R³* untuk jalur panjang 3, dan seterusnya. Maka, *R⁺* berisi semua pasangan simpul *(a, b)* yang memiliki jalur panjang tak nol dari *a* ke *b* dalam *G*.  

Untuk graf terbatas, menghitung *R⁺* memberikan jawaban untuk banyak pertanyaan tentang jalur. Variasi *Algoritma Jelas* dapat disesuaikan dengan kebutuhan. Misalnya, untuk jalur dari simpul *a*, kita hanya perlu menghitung relasi *{(a, b) | (a, b) ∈ R}* yang dikomposisikan berulang dengan *R*. Untuk graf berlabel atau berbobot, algoritma dapat dimodifikasi untuk mencatat label atau bobot jalur.  

Namun, *Algoritma Jelas* tidak selalu efisien, terutama untuk graf besar. Ilmuwan komputer telah mengembangkan algoritma dan struktur data yang lebih baik, yang berada di luar cakupan buku ini. Jika Anda perlu membuat program untuk graf besar, pelajari literatur terkait terlebih dahulu.  

**Penutupan Lain**  

Selain *penutupan transitif*, ada *penutupan simetris* (menambahkan *(b, a)* untuk setiap *(a, b) ∈ R*) dan *penutupan refleksif* (menambahkan *(a, a)* dan *(b, b)* untuk setiap *(a, b) ∈ R*).  

*Penutupan refleksif transitif*, dilambangkan *R**, adalah *penutupan refleksif* dari *R⁺*, yaitu *R* = R⁰ ∪ R¹ ∪ R² ∪ …*. Jika *R* adalah *relasi ketetanggaan* graf *G*, *R** berisi pasangan *(a, b)* untuk setiap jalur (kosong atau tidak) dari *a* ke *b*.  

*Penutupan transitif* dan *refleksif transitif* memiliki banyak aplikasi dalam matematika dan ilmu komputer, tetapi di luar cakupan buku ini. Tujuan bagian ini adalah memperkenalkan konsep-konsep ini agar Anda dapat mengenali masalah pemrograman yang dapat diselesaikan dengan *penutupan* atau jalur dalam graf.  

Sebagai catatan, simbol *+* dan *** adalah idiom umum dalam ilmu komputer, masing-masing berarti “satu atau lebih” dan “nol atau lebih”. Jadi, *+* atau *** tidak selalu merujuk pada catatan kaki!  

### 10.5. Operasi Basis Data Relasional 

Setelah memahami relasi lebih dalam, mari kembali ke *basis data relasional*.  

Seperti disebutkan di Bagian 5.3, relasi dalam basis data relasional mirip dengan relasi matematika, yaitu himpunan *tuple*. Bedanya, elemen *tuple* diidentifikasi dengan nama, bukan posisi.  

Dalam istilah basis data, sebuah relasi memiliki *atribut*—nama-nama yang mengidentifikasi elemen *tuple*. Setiap *tuple* adalah kumpulan nilai atribut yang dinamai.  

Kita bisa merepresentasikan relasi basis data dengan *n* atribut sebagai *triple* *(R, A, col)*, di mana *R* adalah *relasi n-ari* matematis, *A* adalah himpunan *n* nama atribut, dan *col* (kependekan dari “column”) adalah pemetaan dari nama atribut ke posisi (bilangan bulat 0 hingga *n-1*). Untuk relasi *X*, komponennya disebut *R_X*, *A_X*, dan *col_X*.  

Dalam representasi ini, atribut-atribut diurutkan, dan nilai dalam *tuple* di *R* mengikuti urutan tersebut, menyerupai tabel dengan *tuple* sebagai baris dan atribut sebagai kolom. Urutan atribut menentukan pemetaan *col*.  

Pada basis data kecil dan sederhana, relasi bisa diimplementasikan sesuai representasi ini, misalnya sebagai himpunan *tuple* dalam program atau file datar di sistem berkas. Namun, sistem basis data relasional berkualitas produksi jauh lebih kompleks, dengan struktur data dan algoritma tambahan untuk efisiensi. Kompleksitas ini di luar cakupan buku, tetapi kita akan menggunakan representasi *(R, A, col)* untuk membahas relasi dan operasinya secara abstrak.  

Operasi basis data relasional memungkinkan pengguna—seperti manajer atau staf IT—untuk menggabungkan dan mengekstrak informasi dari relasi. Berikut adalah beberapa operasi utama, dijelaskan secara informal:  

*Gabungan* (*union*), *irisan* (*intersection*), dan *selisih* (*difference*) relasi mirip dengan operasi himpunan pada *tuple*. Operasi ini hanya berlaku jika kedua relasi memiliki atribut yang sama (*A_X = A_Y*).  

Bayangkan kita mengurutkan ulang “kolom” relasi *Y* menjadi *Y'* agar sesuai dengan urutan atribut *X*. Maka, *A_Y’ = A_X*, *col_Y’ = col_X*, dan *R_Y’* adalah *R_Y* dengan nilai *tuple* yang diurutkan ulang sesuai *col_X*.  

*Gabungan* relasi *X* dan *Y* menghasilkan relasi *Z* dengan *R_Z = R_X ∪ R_Y’*, *A_Z = A_X*, dan *col_Z = col_X*. *Irisan* dan *selisih* didefinisikan serupa.  

Dalam implementasi, kita bisa memilih untuk mengurutkan ulang *X* alih-alih *Y*. Namun, akan lebih sederhana jika tidak ada pengurutan ulang. Untuk itu, kita bisa menetapkan urutan atribut standar, seperti urutan alfabetis berdasarkan nama atribut.  

*Seleksi* adalah operasi umum untuk memilih *tuple* yang memenuhi kriteria tertentu, mirip dengan fungsi *filter* (Bagian 6.4) atau penyaringan dengan *if* dalam Python. Dalam notasi matematika, seleksi ditulis *σ_P(X)*, dengan *X* sebagai relasi dan *P* sebagai predikat Boolean. Hasilnya adalah relasi baru. Contoh, untuk relasi *X* berikut (dari Bagian 5.3):  

| nama    | proyek | lab |
| ------- | ------ | --- |
| Lambert | Alpha  | 221 |
| Torres  | Alpha  | 244 |
| Malone  | Beta   | 152 |
| Harris  | Beta   | 152 |
| Torres  | Beta   | 152 |

Jika *P* adalah “proyek = 'Alpha'”, maka *σ_P(X)* menghasilkan:  

| nama    | proyek | lab |
| ------- | ------ | --- |
| Lambert | Alpha  | 221 |
| Torres  | Alpha  | 244 |

*Proyeksi* menghasilkan relasi baru dengan hanya sebagian atribut dari relasi asli, ditulis *π_S(X)*, di mana *S* adalah himpunan nama atribut yang diinginkan. Misalnya, jika *S = {“nama”, “lab”}* untuk *X* di atas, maka *π_S(X)* adalah:  

| nama    | lab |
| ------- | --- |
| Lambert | 221 |
| Torres  | 244 |
| Malone  | 152 |
| Harris  | 152 |
| Torres  | 152 |

Untuk menggabungkan informasi dari dua relasi, *gabungan alami* (*natural join*), ditulis *Y ⋈ Z*, menggabungkan pasangan *tuple* dari *Y* dan *Z* yang memiliki nilai sama pada atribut bersama. Relasi hasil berisi *tuple* dengan atribut gabungan dari *Y* dan *Z*. Contoh, untuk *X* di atas dan relasi *W*:  

| lab | peralatan |
| --- | --------- |
| 221 | 400913-C  |
| 152 | 400697-A  |
| 152 | 19472832  |

Maka *X ⋈ W* menghasilkan:  

| nama    | proyek | lab | peralatan |
| ------- | ------ | --- | --------- |
| Lambert | Alpha  | 221 | 400913-C  |
| Malone  | Beta   | 152 | 400697-A  |
| Malone  | Beta   | 152 | 19472832  |
| Harris  | Beta   | 152 | 400697-A  |
| Harris  | Beta   | 152 | 19472832  |
| Torres  | Beta   | 152 | 400697-A  |
| Torres  | Beta   | 152 | 19472832  |

Operator *⋈* kadang disebut **bowtie operator** (operator dasi kupu-kupu).  

Dengan *gabungan alami* dan *proyeksi*, kita bisa melakukan operasi mirip *komposisi* relasi matematis. Misalnya, gabungkan *π_S(X)* dan *W* dengan *gabungan alami*:  

| nama    | lab | peralatan |
| ------- | --- | --------- |
| Lambert | 221 | 400913-C  |
| Malone  | 152 | 400697-A  |
| Malone  | 152 | 19472832  |
| Harris  | 152 | 400697-A  |
| Harris  | 152 | 19472832  |
| Torres  | 152 | 400697-A  |
| Torres  | 152 | 19472832  |

Lalu, lakukan *proyeksi* untuk menghapus atribut bersama (*lab*), menghasilkan:  

| nama    | peralatan |
| ------- | --------- |
| Lambert | 400913-C  |
| Malone  | 400697-A  |
| Malone  | 19472832  |
| Harris  | 400697-A  |
| Harris  | 19472832  |
| Torres  | 400697-A  |
| Torres  | 19472832  |

Ini setara dengan *W ∘ π_S(X)* dalam basis data relasional.  

**Istilah yang Diperkenalkan dalam Bab Ini**  
- Relasi _n-ari_ (_n-ary relation_)
- Predikat (_predicate_)
- Relasi pada himpunan (_relation on a set_)
- _Loop_ (_loop_)
- _Sisi ganda_ (_multiple edges_)
- Relasi ketetanggaan (_adjacency relation_)
- Relasi simetris (_symmetric relation_)
- Relasi antisimetris (_antisymmetric relation_)
- Relasi transitif (_transitive relation_)
- Relasi refleksif (_reflexive relation_)
- Relasi ekuivalensi (_equivalence relation_)
- Partisi (_partition_)
- Relasi identitas (_identity relation_)
- Pemetaan/fungsi identitas (_identity mapping/function_)
- Komposisi relasi (_relation composition_)
- Pangkat relasi (_power of a relation_)
- Graf (_graph_)
- Simpul (_vertex_)
- Sisi (_edge_)
- Graf berarah (_directed graph_)
- Graf tak berarah (_undirected graph_)
- Graf dari relasi (_graph of a relation_)
- Graf berlabel (_labeled graph_)
- Graf berbobot (_weighted graph_)
- Jalur (_path_)
- Penutupan transitif (_transitive closure_)
- Penutupan simetris (_symmetric closure_)
- Penutupan refleksif (_reflexive closure_)
- Penutupan refleksif transitif (_reflexive transitive closure_)
- Atribut (_attribute_)
- Gabungan, irisan, selisih (_relational union, intersection, difference_)
- Seleksi (_selection_)
- Proyeksi (_projection_)
- Gabungan alami (_natural join_)

**Latihan**  
1. Jelas bahwa *I_A* bersifat refleksif untuk setiap himpunan *A*. Apakah *I_A* bersifat transitif? Apakah itu relasi ekuivalensi?  

2. Di Bagian 10.3, kami mendefinisikan “graf dari relasi” secara informal, tetapi hanya menyebutkan himpunan sisi. Apa himpunan simpulnya? Apakah ada lebih dari satu kemungkinan?  

3. Tulis fungsi Python yang menghasilkan *penutupan transitif* sebuah relasi, dengan relasi dan hasilnya sebagai himpunan Python berisi *tuple* dua elemen.

4. Untuk graf terbatas *G* dengan relasi ketetanggaan *R*, jika *R⁺* dihitung dengan *Algoritma Jelas*, berapa *k* (jumlah pangkat *R* yang dihitung sebelum algoritma selesai)? Bisakah Anda menemukan nilai perkiraan, batas atas, atau nilai pasti? Nyatakan jawaban dalam konteks jalur di *G*. Biasanya, *k* jauh lebih kecil dari jumlah pasangan yang mungkin dalam *R⁺*.  

5. Dalam graf berarah, jika ujung satu jalur sama dengan awal jalur lain, kedua jalur bisa digabungkan menjadi jalur baru. Apakah himpunan semua jalur dalam graf berarah membentuk *monoid* di bawah operasi penggabungan?  

6. Nyatakan *σ_P(X)* sebagai *triple* (*R*, *A*, *col*). Asumsikan *P* dapat digunakan sebagai predikat, seperti *P(x)*. Ulangi untuk *π_S(X)* dan *X ⋈ Y*. Ini lebih sulit jika menggunakan notasi matematika sepenuhnya.  

7. Apa sifat-sifat operasi *gabungan alami*? Apakah *⋈* asosiatif? Komutatif? Apakah ada elemen identitas? Apakah ini membentuk *monoid* lain?  

[back](./)

---

[^1]: As always, whatever you're reading, read the definitions carefully!
