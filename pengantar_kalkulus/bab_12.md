[Home](../)

[Back](./)


## Bab 12. Integral

Kejadian paling memalukan dari musim panas saya sebagai orang asing yang polos terjadi tak lama setelah saya memasuki Jerman. Saya telah mendapatkan peta jalan negara itu di perbatasan, dan tumpangan dari sopir yang ramah dari truk 18 roda. Karena dia hanya berbicara Jerman, dan saya tidak, saya memutuskan bahwa saya akan turun di beberapa kota yang terdengar menarik, dan melanjutkan dari sana.

Sesuai rencana, ketika tanda yang sesuai muncul di jalan, saya memberi isyarat niat saya, turun dari truk, melambai perpisahan, mengeluarkan peta saya, dan mulai mencari kota Ausfart. Pencarian ini ditakdirkan gagal sejak awal, karena—seperti yang saya ketahui kemudian—Ausfart hanyalah kata Jerman untuk keluar.

Namun, kota kecil Jerman tempat saya mendarat ternyata sama baiknya dengan tempat lain untuk memulai. Ketika Anda sedang naik becak di negeri asing, sebenarnya tidak terlalu penting jika Anda tahu ke mana Anda pergi—setiap tempat mungkin akhirnya menjadi menarik.

Itulah semangat yang akan membimbing kita di bab ini. Jalan yang telah kita tempuh telah membawa kita ke puncak. Sekarang kita akan menyimpang ke arah yang sama sekali berbeda, dan melihat apakah jalur baru ini juga membawa kita ke suatu tempat yang menarik.

Grafik fungsi $f(x)=x^2$ telah menjadi titik awal alami pada semua perjalanan kecil kita. Di satu sisi, ini hampir fungsi paling sederhana setelah fungsi linear, jadi wajar untuk mempertimbangkannya pertama kali ketika kita menyelidiki turunan. Karena ini juga fungsi yang muncul dalam fisika paling dasar, ini secara alami membawa kita pada diskusi tentang kecepatan.

Grafik fungsi ini, parabola, juga salah satu bentuk geometris paling sederhana, setelah poligon dan lingkaran, jadi menyenangkan bahwa kita bisa menggunakan turunan untuk menemukan garis singgung ke grafik.

Tetapi sejauh ini kita telah mengabaikan salah satu konsep paling penting yang terkait dengan figur geometris—luasnya. Hanya wajar untuk mencoba menemukan rumus untuk luas wilayah seperti berikut, dibatasi oleh grafik fungsi $f(x)=x^2$, sumbu $x$, dan garis vertikal $x=1$.

![](Pasted%20image%2020250622171451.png)

Pada titik ini kita harus mengevaluasi kembali dan mengingat jenis alat apa yang kita miliki untuk menentukan luas. Aturan dasar menyatakan bahwa luas persegi panjang adalah panjang kali lebar, sementara luas segitiga adalah setengah dari produk tersebut:

![](Pasted%20image%2020250622171512.png)

$$
\text{ luas } = \frac{1}{2} h \cdot b
$$

Dan, seperti yang diketahui setiap anak sekolah, luas lingkaran dengan jari-jari $r$ adalah $\pi r^2$. Ini adalah salah satu kasus langka di mana daya tarik tradisional kepada anak-anak sekolah yang berpengetahuan mungkin dibenarkan, karena rumus ini biasanya dihafal jauh sebelum Anda mengikuti kursus geometri. Memang, mungkin ide yang baik untuk mengingat bagaimana kita bisa benar-benar menetapkan rumus seperti itu.

Gambar di bawah ini menunjukkan lingkaran yang dikelilingi oleh poligon $P$ yang terdiri dari 10 segitiga kongruen, salah satunya telah diarsir. 

![](Pasted%20image%2020250622171608.png)

Tinggi segitiga yang diarsir, yaitu panjang garis putus-putus, hanyalah jari-jari $r$ lingkaran, sementara alasnya adalah panjang $AB$. Jadi segitiga memiliki luas:

$$
\frac{1}{2} r \cdot AB.
$$

Menjumlahkannya untuk semua segitiga, kita lihat bahwa:

$$
\text{ luas } P = \frac{1}{2} r \cdot \text{ keliling } P.
$$

Penalaran yang sama berlaku jika kita mempertimbangkan poligon dengan 100 sisi, atau poligon dengan 1.000 sisi, $\cdots$ . Untuk semua poligon $P$ seperti itu kita memiliki:

$$
\text{(*)} \quad \text{ luas } P = \frac{1}{2} r \cdot \text{ keliling } P.
$$

Saat kita memilih poligon dengan jumlah sisi yang semakin besar, luas di sisi kiri persamaan (`*`) akan semakin mendekati luas lingkaran. Di sisi lain, keliling $P$ di sisi kanan persamaan akan semakin mendekati keliling lingkaran. Akibatnya, kita harus memiliki:

$$
\begin{aligned}
\text{ luas lingkaran } & = \frac{1}{2} r \cdot \text{ keliling lingkaran } \\
& = \frac{1}{2} r \cdot 2\pi r = \pi r^2.
\end{aligned}
$$

Jadi angka misterius $\pi$ dalam rumus untuk keliling lingkaran juga muncul dalam rumus untuk luasnya.

Jenis argumen yang digunakan di sini, mendekati luas lingkaran dengan luas figur yang lebih sederhana, menunjukkan prosedur serupa untuk luas lainnya. Misalnya, dalam gambar di bawah, kita telah mengelilingi wilayah yang dibatasi oleh parabola dengan 10 persegi panjang. 

![](Pasted%20image%2020250622171822.png)

Panjang alas setiap persegi panjang adalah .1, sementara tinggi persegi panjang diberikan oleh:
	tinggi persegi panjang 1 = $.1^2$
	tinggi persegi panjang 2 = $.2^2$
	tinggi persegi panjang 3 = $.3^2$
	tinggi persegi panjang 10 = $1^2$.

Akibatnya, luas total persegi panjang adalah:

$$
\left(S_{10}\right) \quad .1 \times \left(.1^2 + .2^2 + .3^2 + .4^2 + .5^2 + .6^2 + .7^2 + .8^2 + .9^2 + 1^2\right).
$$

Menghitung ini jelas jauh lebih mudah dengan kalkulator, atau lebih baik lagi, kalkulator yang dapat diprogram, atau lebih baik lagi, program komputer yang sesuai. Tetapi apa pun cara kita menghitungnya, jawabannya tidak akan terlalu mendekati luas wilayah yang kita minati karena persegi panjang meluas jauh di luar wilayah.

Kita mungkin berharap mendapatkan jawaban yang lebih baik dengan mencoba 100 persegi panjang, yang akan lebih erat mengikuti wilayah di bawah parabola. Ini cukup sulit digambar, tetapi tidak terlalu sulit untuk ditulis. Sekarang kita memiliki 100 persegi panjang, masing-masing dengan alas panjang .01, dan kita ingin memperhitungkan jumlah:

$$
\left(S_{100}\right) \quad .01 \times \left(.01^2 + .02^2 + .03^2 + \cdots + .98^2 + .99^2 + 1^2\right).
$$

Sekarang, tentu saja, kita benar-benar membutuhkan kalkulator yang dapat diprogram atau komputer, dan kita pasti akan membutuhkannya untuk 1.000 persegi panjang. Saya mendapatkan jawaban berikut:

| jumlah persegi panjang | luas total |
|--------------------------------|------------|
| 10                          | .385       |
| 100                         | .33835     |
| 1,000                       | .3338335   |

Tetapi ketika saya mencoba 10.000 persegi panjang, jawabannya diberikan dalam bentuk $333,409 \times 10^{-3} (=.333409 \ldots)$, menunjukkan bahwa kesalahan pembulatan dari semua perhitungan mencegah jawaban diberikan dengan akurasi penuh.

Anda mungkin atau mungkin tidak melihat pola di sini, tetapi dalam hal apa pun jelas bahwa metode ini tidak tampak sangat efisien!

Daripada memilih jumlah persegi panjang tertentu, seperti 10, atau 100, atau 1.000, $\cdots$, mari kita pilih $n$ persegi panjang, seperti dalam gambar di bawah ini. 

![](Pasted%20image%2020250622172247.png)

Sekarang panjang alas setiap persegi panjang adalah $\frac{1}{n}$, sementara tinggi persegi panjang diberikan oleh:
	tinggi persegi panjang 1 = $\left(\frac{1}{n}\right)^2$
	tinggi persegi panjang 2 = $\left(\frac{2}{n}\right)^2$
	tinggi persegi panjang 3 = $\left(\frac{3}{n}\right)^2$
	$\cdots$
	tinggi persegi panjang $n$ = $\left(\frac{n}{n}\right)^2$.

Akibatnya, luas total persegi panjang adalah:

$$
\frac{1}{n} \cdot \left[ \left(\frac{1}{n}\right)^2 + \left(\frac{2}{n}\right)^2 + \left(\frac{3}{n}\right)^3 + \cdots + \left(\frac{n}{n}\right)^2 \right],
$$

yang juga dapat ditulis dalam bentuk:

$$
\frac{1}{n} \cdot \left[ \frac{1^2}{n^2} + \frac{2^2}{n^2} + \frac{3^2}{n^2} + \cdots + \frac{n^2}{n^2} \right],
$$

atau sederhananya:

$$
\left(S_{n}\right) \quad \frac{1}{n^3} \cdot \left[ 1^2 + 2^2 + 3^2 + \cdots + n^2 \right].
$$

Sebagian besar kerumitan rumus ini telah disembunyikan dalam $\cdots$ dari jumlah $1^2 + 2^2 + 3^2 + \cdots + n^2$. Tetapi juga kebetulan ada rumus yang sangat ringkas untuk jumlah ini, yaitu:

$$
1^2 + 2^2 + 3^2 + \cdots + n^2 = \frac{n(n+1)(2n+1)}{6}.
$$

Anda mungkin bertanya-tanya dari mana rumus ini berasal! Tetapi jangan khawatir tentang itu sekarang (ini bukan rumus yang biasanya Anda diharapkan tahu). Kita hanya ingin mencatat bahwa sekali kita memiliki rumus ini kita dapat menulis luas total $\left(S_n\right)$ persegi panjang kita sebagai:

$$
\begin{aligned}
\frac{1}{n^3} \cdot \frac{n(n+1)(2n+1)}{6} & = \frac{1}{n^2} \cdot \frac{(n+1)(2n+1)}{6} \\
& = \frac{1}{6} \cdot \frac{n+1}{n} \cdot \frac{2n+1}{n}
\end{aligned}
$$

Alasan menulis jawaban kita dalam bentuk akhir ini adalah kita sekarang dapat melihat apa yang terjadi ketika $n$ besar: pecahan pertama $\frac{n+1}{n}$ mendekati 1, sementara pecahan kedua $\frac{2n+1}{n}$ mendekati 2. Akibatnya, seluruh jawaban mendekati:

$$
\frac{1}{6} \cdot 1 \cdot 2 = \frac{1}{3}.
$$

Dan ini berarti, akhirnya, bahwa luas gambar pertama tadi pasti benar-benar $1/3$.

Untuk wilayah yang dibatasi oleh parabola dan garis vertikal $x=a$, luasnya ternyata:

![](Pasted%20image%2020250622172729.png)

$$
\text{ luas } = \frac{a^3}{3}.
$$

Kita bisa menetapkan ini dengan cara yang hampir sama, memilih $n$ persegi panjang dengan titik-titik $\frac{a}{n}, \frac{2a}{n}, \frac{3a}{n}, \ldots$. Tetapi kita akan melewatkan penderitaan halus perhitungan ini, karena kita sudah membuat poin kita: Dibutuhkan banyak kerja hanya untuk menemukan luas satu wilayah! (Dan kita akan bingung tanpa mengetahui rumus untuk $1^2 + 2^2 + 3^2 + \cdots + n^2$.)

Seseorang merinding memikirkan apa yang diperlukan untuk menemukan luas wilayah di bawah grafik $f(x)=x^3$ atau $f(x)=x^4$, atau bahkan hal-hal yang lebih rumit seperti $f(x)=1/(1+x^2)$, apalagi sesuatu seperti grafik $f(x)=\sin x$!

Pada titik ini kita harus mengingat bahwa ketika matematika menjadi sulit, matematikawan tangguh memperkenalkan notasi baru.

Kita ingin mempertimbangkan luas yang dibatasi oleh grafik fungsi $f$, sumbu $x$, dan garis vertikal $x=a$ dan $x=b$. Untuk kenyamanan, kita akan selalu mengasumsikan bahwa $f$ kontinu.

![](Pasted%20image%2020250622172835.png)

Dalam perhitungan sebelumnya kita menggunakan persegi panjang yang alasnya semua memiliki panjang yang sama, tetapi tidak ada alasan khusus untuk membuat pembatasan ini. Mari kita bagi interval dari $a$ ke $b$ menjadi $n$ potong ukuran sewenang-wenang dengan titik-titik:

![](Pasted%20image%2020250622172855.png)

$$
a=t_0, t_1, \ldots, t_n=b.
$$

Kita telah menomori titik-titik dengan cara khusus ini sehingga panjang alas:
	persegi panjang pertama akan $t_1 - t_0$
	persegi panjang kedua akan $t_2 - t_1$
	persegi panjang ketiga akan $t_3 - t_2$
	$\cdots$
	persegi panjang ke-$i$ akan $t_i - t_{i-1}$

![](Pasted%20image%2020250622173248.png)

Angka-angka ini sering ditandai dengan:

$$
\begin{aligned}
\Delta x_1 & = t_1 - t_0 \\
\Delta x_2 & = t_2 - t_1 \\
\Delta x_3 & = t_3 - t_2 \\
& \cdots \\
\Delta x_i & = t_i - t_{i-1}
\end{aligned}
$$

di mana penggunaan $\Delta$ analog dengan penjelasan tentang *Delta* di bab 5.

Ada beberapa cara kita mungkin memilih tinggi persegi panjang. Misalnya, untuk persegi panjang pertama (yang diarsir) dalam gambar di bawah ini kita memilih nilai maksimum $f$ di atas alas pertama, sehingga persegi panjang menonjol di atas grafik.

![](Pasted%20image%2020250622173516.png)

Persegi panjang kedua belum digambar, tetapi untuk persegi panjang ketiga (yang bertitik) kita memilih nilai minimum $f$ di atas alas ketiga, sehingga persegi panjang ini sepenuhnya berada di bawah grafik.

Akhirnya, di atas persegi panjang ke-$i$ kita hanya memilih sembarang titik $x_i$ antara $t_{i-1}$ dan $t_i$, dan membuat persegi panjang dengan tinggi $f(x_i)$, sehingga persegi panjang ini sebagian di bawah dan sebagian di atas grafik.

Apakah itu kita memilih $x_i$ sebagai sembarang titik antara $t_{i-1}$ dan $t_i$, atau titik maksimum atau minimum untuk $f$, kita sekarang dapat mempertimbangkan jumlah:

$$
f(x_1)(t_1 - t_0) + f(x_2)(t_2 - t_1) + \cdots + f(x_n)(t_n - t_{n-1}),
$$

yang juga dapat kita tulis sebagai:

$$
f(x_1) \Delta x_1 + f(x_2) \Delta x_2 + \cdots + f(x_n) \Delta x_n,
$$

menggunakan notasi yang diperkenalkan di atas.

Lebih ringkas lagi, kita dapat menggunakan notasi $\sum$ ("notasi Sigma") untuk menulis ini sebagai:

$$
\text{(*)} \quad \sum_{i=1}^n f(x_i) \Delta x_i
$$

(dibaca "jumlah dari $i=1$ hingga $n$ dari $f(x_i) \Delta x_i$"). Di sini $\sum$ menunjukkan jumlah kuantitas yang diperoleh dari ekspresi berikutnya, $f(x_i) \Delta x_i$, dengan memilih $i=1, 2, \ldots, n$.

Ketika semua $\Delta x_i$ kecil, ini mewakili luas total persegi panjang yang semua terletak dekat dengan grafik $f$. Jadi kita mendapatkan luas yang diinginkan dengan menentukan apa jumlah ini semakin mendekati saat kita membuat semua $\Delta x_i$ semakin kecil (mudah diucapkan daripada dilakukan!).

![](Pasted%20image%2020250622174041.png)

Perhatikan, bagaimanapun, bahwa di tempat-tempat di mana $f$ memiliki nilai negatif, istilah $f(x_i) \Delta x_i$ adalah negatif. 

![](Pasted%20image%2020250622174140.png)

Jadi wilayah di bawah sumbu $x$ menyumbang jumlah negatif. Dengan demikian kita sebenarnya mempertimbangkan "area bertanda"—jika $f$ sebagian di atas sumbu $x$ dan sebagian di bawahnya, kita mencoba menghitung selisih antara jumlah luas yang terletak di atas sumbu $x$ dan jumlah luas yang terletak di bawahnya.

![](Pasted%20image%2020250622174204.png)

Area bertanda ini disebut *integral* fungsi $f$ dari $a$ ke $b$, dan ditandai dengan:

$$
\int_a^b f(x) dx.
$$

Simbol ini seharusnya mengingatkan kita pada jumlah:

$$
\text{(*)} \quad \sum_{i=1}^n f(x_i) \Delta x_i
$$

dan berasal dari ekspresi ini dengan cara yang sama seperti notasi $\frac{df(x)}{dx}$ untuk turunan berasal dari ekspresi $\frac{\Delta f}{\Delta x}$ (lihat bagian atas bab 5)—kita mengganti semua $\Delta x_i$ dengan $dx$ untuk menunjukkan bahwa kita mempertimbangkan apa yang terjadi ketika semua $\Delta x_i$ sangat kecil. Pada saat yang sama, tanda $\sum$ berubah menjadi tanda $\int$ (pada dasarnya $S$ yang memanjang) untuk menunjukkan bahwa kita menjumlahkan jumlah yang sangat besar dari persegi panjang yang sangat sempit.

Meskipun simbolisme yang menarik mungkin menyenangkan, poin yang benar-benar penting tentang notasi ini hanyalah bahwa:

$$
\int_a^b f(x) dx
$$

mengandung semua informasi penting, yaitu fungsi $f$ dan angka $a$ dan $b$. Ini juga mengandung huruf $x$, tetapi huruf ini hanyalah kenyamanan untuk menamakan fungsi. Misalnya,

$$
\int_a^b x^2 dx
$$

berarti angka yang jumlah (`*`) mendekati ketika kita memilih fungsi:

$$
f(x) = x^2;
$$

dengan demikian, seperti yang telah kita hitung dengan susah payah,

$$
\int_0^1 x^2 dx = \frac{1}{3}.
$$

Lebih umumnya,

$$
\int_0^a x^2 dx = \frac{a^3}{3}
$$

seperti yang kita sebutkan di atas (ketika kita bertanya dari mana rumus ini datang), meskipun kita tidak melanjutkan detail perhitungannya.

Meskipun biasanya menggunakan huruf $x$ dalam persamaan ini, seperti kita biasanya berbicara tentang "sumbu $x$," ini tidak perlu, dan seseorang bisa sama baiknya menggunakan huruf lain. Misalnya, kita dapat menulis:

$$
\int_0^a t^2 dt = \frac{a^3}{3}.
$$

Perhatikan bahwa sisi kiri persamaan ini hanya merujuk pada fungsi $f(t) = t^2$, yang hanyalah cara lain untuk menamakan fungsi $f(x) = x^2$. Seperti dalam definisi " $f(x) = x^2$," notasi:

$$
\int_a^b f(x) dx
$$

hanya menggunakan huruf $x$ sebagai "penampung nilai," yang dapat diganti dengan huruf lain (kecuali $a$ atau $b$ atau $f$ tentu saja!).

Kita telah melihat betapa sulitnya menghitung integral, tetapi setidaknya kita selalu tahu nilainya ketika $b = a$: Untuk fungsi apa pun $f$ kita memiliki:

$$
\int_a^a f(t) dt = 0.
$$

(Satu nilai mungkin tidak terlihat banyak, tetapi kita mungkin juga berpegang teguh pada setiap potong informasi kecil yang bisa kita dapatkan!)

Ada juga hubungan geometris yang jelas yang akan berguna untuk dinyatakan secara eksplisit:

**Sifat penjumlahan (*additivity property*) dari integral.** Jika $a < b < c$, maka:

$$
\text{(A)} \quad \int_a^c f(x) dx = \int_a^b f(x) dx + \int_b^c f(x) dx.
$$

Persamaan ini hanya menyatakan fakta geometris bahwa dalam gambar di bawah luas seluruh wilayah adalah jumlah luas dua wilayah $R_1$ dan $R_2$ (ini benar-benar mengatakan sesuatu yang sedikit lebih rumit dari itu, karena integral mewakili luas bertanda).

![](Pasted%20image%2020250622175158.png)

Sebagai penggunaan khas properti ini, kita dapat memulai dengan:

$$
\int_0^b x^2 dx = \int_0^a x^2 dx + \int_a^b x^2 dx, \quad 0 < a < b,
$$

dan kemudian mengurangkan $\int_0^a x^2 dx$ dari kedua sisi untuk mendapatkan:

$$
\int_a^b x^2 dx = \int_0^b x^2 dx - \int_0^a x^2 dx.
$$

Menggunakan rumus untuk $\int_0^b x^2 dx$ sebelumnya, kita kemudian melihat bahwa:

![](Pasted%20image%2020250622175327.png)

$$
\int_a^b x^2 dx = \frac{b^3}{3} - \frac{a^3}{3}.
$$

Tetapi kita tidak tahu lebih banyak lagi dari ini. Kita telah memperoleh beberapa notasi yang cukup—simbol:

$$
\frac{df(x)}{dx} \text{ dan } \int_a^b f(x) dx
$$

adalah notasi misterius utama dari kalkulus—tetapi itu saja. Ausfart kita memang telah membawa kita pada masalah baru yang menarik, tetapi tidak jelas apakah masalah ini akan membuka pandangan baru atau ternyata menjadi jalan buntu.

[Back](./)
