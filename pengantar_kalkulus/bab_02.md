[Home](../)\n[Back](./)\n
## Bab 2. Mengemas hal-hal penting

Ada berbagai macam prasyarat matematika untuk kalkulus—pada suatu waktu, sebagian besar teknik aljabar, trigonometri, dan geometri analitik akan digunakan. Namun, hal utama yang kita perlukan dalam perjalanan kita adalah beberapa ide paling sederhana dari geometri analitik.

Dalam geometri analitik, kita memperkenalkan sistem koordinat dengan menggambar dua garis yang saling tegak lurus, yaitu dua sumbu, di mana kita mengukur jarak; secara konvensional, bilangan positif mewakili jarak ke kanan pada sumbu horizontal, dan jarak ke atas pada sumbu vertikal.

![](Pasted%20image%2020250621210901.png)

Kemudian, kita mengaitkan sepasang bilangan $(a, b)$ ke setiap titik di bidang sesuai dengan skema di bawah ini, dengan $a$ menunjukkan jarak horizontal dan $b$ menunjukkan jarak vertikal. Titik yang sesuai dengan $(0,0)$ adalah titik asal $O$, yaitu perpotongan kedua sumbu kita.

![](Pasted%20image%2020250621210924.png)

Setelah kita memiliki metode untuk mengaitkan titik-titik dengan pasangan bilangan, dan sebaliknya, kita dapat melihat kurva-kurva yang sesuai dengan persamaan. Misalnya, anggap saja kita mengambil kurva paling sederhana, yaitu garis lurus $L$ yang melalui titik asal. 

![](Pasted%20image%2020250621211005.png)

Jika $P = (x, y)$ adalah titik apa pun pada garis ini, maka segmen garis $OA$ memiliki panjang $x$, sedangkan segmen $AP$ memiliki panjang $y$. Akibatnya, rasio

$$
\frac{y}{x} = \frac{AP}{OA}
$$

(di sini $AP$ menunjukkan panjang segmen dari $A$ ke $P$, dan begitu pula untuk $OA$)

selalu sama dengan bilangan $m$, tidak peduli titik $P$ mana yang kita pilih: rasio ini adalah tangen dari sudut $\theta$ yang dibentuk oleh garis lurus kita dengan sumbu horizontal; kita juga menyebutnya kemiringan (*slope*) dari garis $L$.

Jadi, setiap titik $(x, y)$ pada $L$ memenuhi

$$
\frac{y}{x} = m.
$$

atau persamaan yang setara

$$
\text {(1) }y = mx
$$

(yang memiliki keunggulan bahwa persamaan ini masih masuk akal dan benar bahkan untuk $x = 0$). Kita mengungkapkan ini dengan mengatakan bahwa (1) adalah persamaan dari garis lurus $L$.

Karena kita cenderung menggunakan $(x, y)$ sebagai nama untuk titik sembarang (dan karena itu mencari persamaan antara $x$ dan $y$), bilangan $x$ biasanya mewakili jarak di sepanjang sumbu horizontal, sedangkan bilangan $y$ biasanya mewakili jarak di sepanjang sumbu vertikal. Akibatnya, sumbu horizontal sering disebut sumbu-x, sedangkan sumbu vertikal sering disebut sumbu-y.

Perhatikan bahwa satu kasus dari (1) bersifat khusus: jika $m = 0$, maka kita hanya memiliki "persamaan"

$$
y = 0,
$$

yang tidak mengandung $x$ sama sekali. Tetapi tetap benar bahwa "persamaan" ini mewakili garis lurus—yaitu persamaan untuk sumbu horizontal, karena titik $(x, y)$ memenuhi $y = 0$ tepat ketika $(x, y)$ terletak pada sumbu horizontal; dengan kata lain, pada sumbu-x, nilai $x$ sembarang, sedangkan $y$ harus 0.

Bagaimana dengan garis lurus $L$ yang tidak melalui titik asal? Salah satu cara sederhana untuk menemukan persamaan $L$ adalah dengan menggambar garis $L'$ yang sejajar dengan $L$ tetapi melewati titik asal.

![](Pasted%20image%2020250621211310.png)

Kemudian, setiap titik pada $L$ terletak tepat di atas titik pada $L'$, dan jarak antara kedua titik ini selalu sama dengan bilangan $b$. Akibatnya, untuk setiap titik $(x, mx)$ pada $L'$, kita memiliki titik $(x, y)$ pada $L$ dengan

$$
\text{(2) }y = mx + b.
$$

Jadi, (2) adalah persamaan dari garis lurus kita $L$. Dalam persamaan ini, $m$ kembali disebut kemiringan (*slope*) dari $L$ (tetap saja merupakan tangen dari sudut $\theta$ yang dibentuk $L$ dengan sumbu horizontal). Bilangan $b$ disebut intersep-y (*y-intercept*), karena ini adalah jarak di mana garis $L$ memotong sumbu-y, dan persamaan (2) disebut bentuk intersep-kemiringan (*slope-intercept form*) dari persamaan garis lurus.

Sekali lagi, kasus $m = 0$ bersifat khusus: kita mendapatkan "persamaan"

$$
y = b,
$$

yang hanya mewakili garis yang sejajar dengan sumbu-x.

![](Pasted%20image%2020250621211420.png)

Tampaknya persamaan (2) adalah persamaan paling umum yang kita butuhkan untuk menggambarkan garis lurus, tetapi sebenarnya kita telah melewatkan satu kelompok, yaitu garis-garis lurus yang vertikal. Namun, mudah dilihat bahwa garis-garis tersebut hanya memiliki "persamaan" berbentuk

$$
x = a,
$$

yaitu "persamaan" dari garis lurus vertikal yang memotong sumbu-x di $(a, 0)$.

![](Pasted%20image%2020250621211445.png)

Kritik yang lebih signifikan terhadap persamaan intersep-kemiringan adalah bahwa persamaan ini hanya berguna ketika kita kebetulan menggambarkan garis berdasarkan kemiringan dan intersep-y-nya, yang mungkin bukan data yang menarik bagi kita. Misalnya, pertanyaan pertama yang mungkin muncul di pikiran adalah bagaimana menemukan persamaan garis lurus yang melewati dua titik yang diberikan, $P$ dan $Q$, di mana kita tidak diberikan kemiringan maupun intersep-y.

Daripada menjawab pertanyaan ini secara langsung, kita akan terlebih dahulu mempertimbangkan pertanyaan lain, yang nantinya akan sangat berguna: Bagaimana kita menemukan persamaan garis lurus yang melewati titik tertentu $P = (x_0, y_0)$ dan memiliki kemiringan $m$ yang diberikan?

![](Pasted%20image%2020250621211520.png)

Ada cara yang sangat lugas dan tidak imajinatif untuk menyelesaikan masalah ini: Karena kemiringannya adalah $m$, kita tahu bahwa garis lurus tersebut memiliki persamaan berbentuk

$$
\text{(a) }y = mx + b
$$

Jadi, kita hanya perlu mencari tahu apa itu $b$. Dan untuk melakukan ini, kita hanya perlu menggunakan fakta bahwa $P = (x_0, y_0)$ terletak pada garis tersebut: ini berarti bahwa $(x_0, y_0)$ memenuhi (a), dan dengan demikian

$$
y_0 = mx_0 + b.
$$

Kita bisa menyelesaikan persamaan ini untuk $b$,

$$
b = y_0 - mx_0,
$$

sehingga (a) menjadi

$$
\text{(b) }y = mx + [y_0 - mx_0].
$$

Ini benar-benar benar, tetapi tidak terlalu menarik, juga tidak mudah diingat. Penalaran geometris yang lebih banyak dengan mudah memperbaiki kedua kekurangan ini: Dalam gambar di bawah, segmen vertikal memiliki panjang $y - y_0$ dan segmen horizontal memiliki panjang $x - x_0$. 

![](Pasted%20image%2020250621211915.png)

Karena garis memiliki kemiringan $m$, ini berarti bahwa

$$
m = \frac{y - y_0}{x - x_0},
$$

atau

$$
\text{(3) }y - y_0 = m(x - x_0).
$$

Persamaan ini disebut bentuk titik-kemiringan (*point-slope form*) dari persamaan garis lurus. Mudah dilihat bahwa persamaan ini setara dengan (b), tetapi menunjukkan hubungan antara data yang diberikan dengan jauh lebih jelas.

### Melenturkan Otot

**Dua latihan untuk mempersiapkan kita menghadapi kerasnya perjalanan ke depan.**

1. Kami dengan mudah mengelak dari masalah menemukan persamaan garis lurus yang melalui dua titik yang diberikan $P = (x_0, y_0)$ dan $Q = (x_1, y_1)$, sehingga bisa dijadikan latihan yang menarik.

   (a) Kita mencari persamaan berbentuk

   $$
   y = mx + b,
   $$

   di mana $m$ dan $b$ saat ini belum diketahui. Yang kita tahu adalah bahwa $P$ dan $Q$ terletak pada garis ini, yang berarti kita memiliki dua persamaan

   $$
   y_0 = mx_0 + b
   $$
   $$
   y_1 = mx_1 + b.
   $$

   Selesaikan kedua persamaan ini untuk $m$ dan $b$, untuk mendapatkan persamaan yang diinginkan. (Ingat bahwa $x_0, x_1, y_0,$ dan $y_1$ hanyalah empat bilangan yang diketahui—jadi ini hanya masalah sederhana yang melibatkan dua persamaan dengan dua variabel tak diketahui $m$ dan $b$.)

   (b) Daripada pendekatan lugas dan tidak imajinatif ini, dengan hasil yang tidak terlalu mudah diingat, sekarang kita akan mencoba solusi yang lebih elegan. Jawab dua pertanyaan berikut:
      (i) Berapa kemiringan $m$ yang harus digunakan?
      (ii) Sekarang terapkan bentuk titik-kemiringan, menggunakan nilai $m$ ini dan fakta bahwa garis melewati $P$, untuk mendapatkan persamaan yang diinginkan.

   (c) Tentu saja, kita juga bisa menggunakan bentuk titik-kemiringan bersama dengan fakta bahwa garis melewati $Q$. Periksa bahwa persamaan yang Anda peroleh dengan cara ini sesuai dengan yang diperoleh pada bagian (b).

2. Latihan kedua ini pada dasarnya hanya lelucon, meskipun ini adalah jenis lelucon yang hanya akan dianggap lucu oleh seorang matematikawan. Namun demikian, latihan ini memiliki poin serius, dan ada alasan mengapa latihan ini mengikuti latihan sebelumnya.

   (a) Anda berada di sebuah ruangan dengan kompor gas yang berfungsi dan sudah dinyalakan, bersama dengan sebuah meja, dan sebuah panci berisi air di atas meja. Anda membutuhkan air mendidih. Apa yang Anda lakukan? Bagian ini tidak dimaksudkan untuk rumit—berikan saja jawaban yang jelas.

   (b) Sekarang Anda berada di ruangan yang sama, dengan kompor gas yang sama, masih berfungsi dan sudah dinyalakan, bersama dengan meja yang sama, dan panci air yang sama, tetapi panci air itu ada di lantai. Anda membutuhkan air mendidih. Apa yang Anda lakukan? Bagian ini dimaksudkan untuk rumit—Anda seharusnya memberikan jawaban yang "elegan" daripada jawaban yang jelas.

**Jawaban.**

**Soal 1(a).** Mengurangi persamaan kedua dari persamaan pertama langsung menghilangkan $b$, memberikan rumus untuk $m$. Mengalikan persamaan pertama dengan $x_1$ dan persamaan kedua dengan $x_0$, lalu menguranginya, memberikan rumus untuk $b$.

**1(b).** Kemiringan $m$ jelas harus $\frac{y_1 - y_0}{x_1 - x_0}$, menggunakan penalaran yang sama seperti pada persamaan (3) (dan seperti yang kita hitung pada bagian (a)). Kemudian bentuk titik-kemiringan memberikan

$$
y - y_0 = \frac{y_1 - y_0}{x_1 - x_0} (x - x_0).
$$

**1(c).** Kita juga mendapatkan

$$
y - y_1 = \frac{y_0 - y_1}{x_0 - x_1} (x - x_1),
$$

yang setelah dikembangkan ternyata setara.

**Soal 2(a).** Letakkan panci air di atas kompor.

**2(b).** Letakkan panci air di atas meja. (Karena sekarang Anda telah mereduksi masalah menjadi masalah yang sudah Anda tahu cara menyelesaikannya, dengan cara yang sama seperti Latihan 1 mereduksi masalah menemukan persamaan garis melalui dua titik menjadi bentuk titik-kemiringan, yang merupakan jawaban untuk masalah yang berbeda.)
[Back](./)
