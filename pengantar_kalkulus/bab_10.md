[Home](../)\n[Back](./)\n
## Bab 10. Pemandangan dari ketinggian

Sejauh ini, perjalanan kita mungkin terasa seperti pendakian terus-menerus ke atas. Akan menyenangkan mengetahui bahwa kita telah mencapai puncak, dan mulai sekarang kita bisa dengan gembira mengantisipasi bahwa semuanya akan menurun.

![](Pasted%20image%2020250622161241.png)

Atau, bahkan jika itu tidak ada dalam rencana, mungkin kita setidaknya bisa mengantisipasi bahwa akan menurun untuk sementara waktu!

![](Pasted%20image%2020250622161256.png)

Jika kita membayangkan rute perjalanan ini sebagai grafik fungsi $f$, puncak $P$ disebut titik maksimum dari $f$ dalam kasus pertama; dalam kasus kedua, di mana $P$ hanya titik maksimum di dekatnya, kita berbicara tentang titik maksimum lokal.

Sebenarnya, kita biasanya hanya fokus pada koordinat pertama $x_0$ dari titik $P$: 

![](Pasted%20image%2020250622161346.png)

kita mengatakan bahwa $f$ memiliki maksimum di $x_0$, atau bahwa $x_0$ adalah titik maksimum dari $f$ jika:

$$
f(x_0) > f(x) \text{ untuk semua } x \neq x_0.
$$

Dalam kasus kedua, di mana kita setidaknya dapat memilih angka $a < x_0 < b$ 

![](Pasted%20image%2020250622161441.png)

sehingga kita memiliki:

$$
f(x_0) > f(x) \text{ untuk semua } x \text{ yang memenuhi } a < x < b \text{ dan } x \neq x_0,
$$

kita mengatakan bahwa $f$ memiliki maksimum lokal di $x_0$, atau bahwa $x_0$ adalah titik maksimum lokal dari $f$. Nilai $f(x_0)$ itu sendiri disebut nilai maksimum atau nilai maksimum lokal dari $f$.

Demikian pula, kita dapat mendefinisikan minimum atau minimum lokal dari $f$ (dan nilai minimum atau nilai minimum lokal).

![](Pasted%20image%2020250622161516.png)

Buku-buku kalkulus penuh dengan gambar seperti ini karena kalkulus memiliki sesuatu yang sederhana dan menarik untuk dikatakan tentang titik-titik (lokal) maksimum dan minimum: di titik tersebut, garis singgung ke grafik adalah horizontal; dengan kata lain, $f^{\prime}(x_0)=0$.

![](Pasted%20image%2020250622161541.png)

Pertama kali saya membaca pernyataan ini di buku kalkulus, saya agak terganggu, tetapi bukan karena saya tidak mempercayainya. Bahkan, saya menemukan pernyataan ini sangat mudah dipercaya—tentu saja terlihat benar dalam gambar. Tetapi matematikawan begitu sangat detail, selalu mengangkat poin halus yang terlewatkan, dan selalu menuntut bukti untuk pernyataan yang tampaknya jelas, sehingga saya tidak merasa sangat aman mendasarkan penerimaan saya pada beberapa gambar. Dan ada tak terbatas banyak gambar berbeda yang bisa digambar untuk mengilustrasikan poin yang sama. Bagaimana mungkin benar-benar jelas bahwa garis singgung akan horizontal di semua kasus?

![](Pasted%20image%2020250622161625.png)

Sebenarnya, ide bahwa kita harus memiliki garis singgung horizontal di titik maksimum atau minimum sudah muncul, tersamar, sebagai masalah di akhir Bab 4, di mana kita mempertimbangkan garis singgung grafik $f(x)=x^2$ melalui $(0,0)$, yang kebetulan titik minimumnya. Pada saat itu kita belum melakukan perhitungan sama sekali, jadi Anda harus membayangkan melihat grafik melalui kaca pembesar bertenaga tinggi, dan menyadari bahwa garis singgung akan menjadi sumbu $x$.

![](Pasted%20image%2020250622161658.png)

Ini mungkin secara visual jelas (terutama karena grafik simetris tentang sumbu $y$, sehingga gambar yang diperbesar juga harus simetris). Lebih penting lagi, kesimpulan ini mudah diikuti dari fakta bahwa $(0,0)$ adalah titik minimum. Lagipula, jika grafik yang diperbesar malah terlihat seperti:

![](Pasted%20image%2020250622161728.png)

maka titik $(0,0)$ tidak akan menjadi titik minimum, karena di titik seperti $Q$ fungsi akan memiliki nilai yang lebih kecil. Dan dengan alasan yang sama, grafik yang diperbesar tidak bisa terlihat seperti:

![](Pasted%20image%2020250622161809.png)

karena kemudian fungsi akan memiliki nilai yang lebih kecil di titik seperti $R$. (Karena grafik yang diperbesar tidak persis garis lurus, akan lebih tepat untuk mengatakan bahwa akan ada titik pada grafik sangat dekat dengan $Q$ atau $R$ di mana fungsi akan memiliki nilai yang lebih kecil.)

Akibatnya, grafik yang diperbesar harus terlihat seperti garis horizontal.

Lebih lanjut, mudah untuk mengubah argumen ini yang melibatkan gambar yang diperbesar menjadi bukti sederhana yang melibatkan definisi dalam hal limit:

**Teorem.** Jika $f$ memiliki minimum atau maksimum di $x_0$ (atau bahkan minimum lokal atau maksimum lokal) dan $f$ dapat diturunkan di $x_0$, maka:

$$
f^{\prime}(x_0) = 0.
$$

**Bukti:** Jika $f$ memiliki minimum di $x_0$, maka:

$$
f(x_0+h) > f(x_0)
$$

sehingga:

$$
f(x_0+h) - f(x) > 0.
$$

Bahkan jika $f$ hanya memiliki minimum lokal di $x_0$, ini tetap berlaku untuk $h$ kecil yang tidak sama dengan 0.

Karena $f(x_0+h) - f(x)$ selalu positif, ini berarti ketika kita membagi dengan $h$ kita mendapatkan hasil berbeda, tergantung pada tanda $h$:

$$
\text {(*) }\frac{f(x_0+h) - f(x)}{h} \text{ adalah } \begin{cases}
> 0 & \text{jika } h > 0 \\
< 0 & \text{jika } h < 0.
\end{cases}
$$

Tetapi turunan $f^{\prime}(x_0)$ adalah:

$$
f^{\prime}(x_0) = \lim_{h \rightarrow 0} \frac{f(x_0+h) - f(x)}{h},
$$

khususnya, pecahan di sebelah kanan harus mendekati $f^{\prime}(x_0)$ baik untuk $h > 0$ maupun $h < 0$. Dan menurut (`*`), ini berarti $f^{\prime}(x_0)$ harus mendekati baik angka positif maupun negatif. Satu-satunya cara ini mungkin adalah jika $f^{\prime}(x_0) = 0$.

Bukti ketika $f$ memiliki maksimum atau maksimum lokal di $x_0$ hampir sama, kecuali bahwa semua ketidaksamaan dibalik. **Q.E.D.**

Meskipun kita biasanya hati-hati menghindari detail, ada beberapa alasan baik untuk menyertakan teorem dan bukti formal ini. Pertama-tama, selalu menyenangkan memiliki bukti yang mudah, terutama ketika kita telah menjanjikan bagian menurun dalam perjalanan kita. Dan tentu saja memuaskan bahwa sesuatu yang intuitif jelas ternyata memiliki bukti yang mudah—seperti yang akan kita lihat nanti, kita tidak selalu seberuntung ini.

Tetapi ada alasan lain untuk menekankan pengamatan singkat dan elegan ini: ini adalah dasar untuk serangkaian masalah yang tidak elegan dan membosankan yang Anda pasti akan hadapi di kursus kalkulus Anda.

Sebagai contoh masalah semacam itu, misalkan kita ingin membuat kaleng timah dengan volume tetap $V$. Misalnya, kita mungkin ingin $V$ tepat 14 ons cair atau $13\frac{1}{4}$ ons atau $14\frac{3}{4}$ ons (hanya untuk memilih beberapa contoh yang saya temukan di rak toko kelontong). Jika ujung-ujung kaleng memiliki jari-jari $r$, dan dengan demikian luas $\pi r^2$, dan kaleng memiliki tinggi $h$, maka volume diberikan oleh rumus:

![](Pasted%20image%2020250622162205.png)

$$
\text{ volume } = \pi r^2 h.
$$

Karena kita ingin:

$$
\pi r^2 h = V,
$$

ini berarti bahwa setelah kita memilih jari-jari $r$, tinggi $h$ ditentukan oleh rumus:

$$
\text{(*) }h = \frac{V}{\pi r^2}.
$$

Sekarang misalkan kita ingin luas permukaan silinder ini sekecil mungkin, sehingga kita akan menggunakan sedikit timah mungkin. Luas permukaan terdiri dari tiga bagian: bagian atas dan bawah yang berbentuk lingkaran, masing-masing memiliki luas $\pi r^2$, dan sisi silinder. Tinggi sisi silinder ini adalah $h$, sementara kelilingnya adalah keliling, $2\pi r$, dari bagian lingkaran. Jadi luas total $A(r)$ adalah:

![](Pasted%20image%2020250622162418.png)

$$
2\pi r^2 + 2\pi r \cdot h,
$$

atau, menurut (`*`):

$$
\begin{aligned}
A(r) & = 2\pi r^2 + 2\pi r \cdot \frac{V}{\pi r^2} \\
& = 2\pi r^2 + \frac{2V}{r}.
\end{aligned}
$$

Jadi masalahnya adalah memilih $r$ sehingga $A(r)$ sekecil mungkin.

Sekarang, di lubuk hati, Anda mungkin tidak terlalu peduli untuk memproduksi kaleng dengan jumlah timah terkecil (meskipun pemikiranC ini mungkin tidak politis). Bahkan, pembuat kaleng timah juga tidak peduli, karena harga timah (sebenarnya baja dengan lapisan timah tipis) tidak signifikan dibandingkan dengan semua biaya lain yang terlibat (dan mereka mungkin juga tidak khawatir tentang menjadi politis). Lebih sederhana memiliki mesin yang memproduksi kaleng dengan beberapa lebar tetap, tetapi tinggi yang bervariasi, terutama karena penting untuk membuat kaleng yang muat dengan mudah di peti kemasan dan rak toko kelontong.

Tetapi ini setidaknya contoh dari jenis masalah yang Anda, atau seseorang, mungkin benar-benar ingin selesaikan suatu hari nanti; dan karena masalah semacam ini dapat diselesaikan dengan kalkulus, Anda pada dasarnya terdoomed untuk menghadapinya. Jadi, meskipun ini hanya "masalah mainan", kita ingin melihat bagaimana kalkulus membantu kita menyelesaikannya.

Menurut Teorem, di titik di mana fungsi:

$$
A(r) = 2\pi r^2 + \frac{2V}{r}
$$

memiliki minimum kita harus memiliki $A^{\prime} = 0$. Menemukan $A^{\prime}$ seharusnya tidak menjadi masalah pada tahap kursus kalkulus Anda. Bahkan, di Bab 5 kita sudah menemukan turunan dari $f(r)=r^2$ dan $f(r)=1/r$, jadi kita hanya perlu menggunakan aturan sederhana tentang jumlah turunan dan produk dengan konstanta. Kita menemukan bahwa:

$$
\begin{aligned}
A^{\prime}(r) = \frac{dA}{dr} & = (2\pi) \cdot 2r + (2V) \cdot -\frac{1}{r^2} \\
& = 4\pi r - \frac{2V}{r^2}.
\end{aligned}
$$

Jadi $A^{\prime}(r) = 0$ setara dengan:

$$
\begin{aligned}
4\pi r & = \frac{2V}{r^2}, \\
2\pi r^3 & = V, \\
r^3 & = \frac{V}{2\pi}.
\end{aligned}
$$

Dengan demikian, kita mendapatkan kaleng dengan volume $V$ dengan luas permukaan terkecil ketika kita memilih:

$$
r = \sqrt[3]{V / 2\pi}.
$$

Ini mengilustrasikan ide dasar di balik aplikasi Teorem, meskipun dalam praktiknya mungkin melibatkan lebih banyak kerja: mungkin ada lebih dari satu titik di mana turunan adalah 0, kita harus membedakan antara titik maksimum dan minimum, dll.

Lebih lanjut, seperti yang sudah disinggung, mungkin ada beberapa komplikasi yang mengintai di belakang layar. Bahkan, kita hanya perlu melihat fungsi $f(x)=x^3$, dengan $f^{\prime}(0)=0$, untuk menyadari bahwa kebalikan dari teorem tidak benar: jika $f$ memiliki (lokal) maksimum atau minimum di $x$, maka $f^{\prime}(x)$ harus 0, tetapi hanya karena $f^{\prime}(x)=0$, kita tidak bisa menyimpulkan bahwa $x$ adalah titik maksimum lokal atau minimum.

![](Pasted%20image%2020250622162551.png)

Untungnya, komplikasi ini tidak mengurangi nilai Teorem dalam menyelesaikan masalah "max-min"—tetap benar bahwa kita dapat menemukan semua kemungkinan untuk maksimum atau minimum dengan menemukan semua $x$ untuk mana $f^{\prime}(x)=0$; masalahnya hanyalah semua $x$ tersebut adalah kandidat, yang kemudian harus diperiksa lebih cermat untuk menentukan kesesuaiannya.

Sebagai fakta, alih-alih hanya menentukan titik-titik maksimum dan minimum relatif dari fungsi $f$, kita dapat menggunakan turunan untuk mendapatkan gambaran umum tentang bentuk grafiknya.

Untuk melakukan ini, kita mengandalkan dua prinsip sederhana:

![](Pasted%20image%2020250622163022.png)

$$
\text{ Jika } f^{\prime}(x) > 0 \text{ untuk } a < x < b, \text{ maka } f \text{ meningkat } \text{ untuk } a < x < b.
$$

![](Pasted%20image%2020250622163047.png)

$$
\text{ Jika } f^{\prime}(x) < 0 \text{ untuk } a < x < b, \text{ maka } f \text{ menurun } \text{ untuk } a < x < b.
$$

Sebaliknya, kita juga memiliki prinsip sederhana:

![](Pasted%20image%2020250622163418.png)

$$
\text{ Jika } f^{\prime}(x) = 0 \text{ untuk } a < x < b, \text{ maka } f \text{ konstan } \text{ untuk } a < x < b.
$$

Misalnya, mari kita pertimbangkan sekali lagi fungsi:

$$
A(x) = 2\pi x^2 + \frac{2V}{x},
$$

dengan:

$$
\begin{aligned}
A^{\prime}(x) = \frac{dA}{dx} & = 4\pi x - \frac{2V}{x^2} \\
& = \frac{2(2\pi x^3 - V)}{x^2}.
\end{aligned}
$$

Kita sudah melihat bahwa $A^{\prime}(x) = 0$ hanya untuk $x = \sqrt[3]{V / 2\pi}$. Rumus akhir untuk $A^{\prime}(x)$ menunjukkan bahwa $A^{\prime}(x) > 0$ tepat ketika:

$$
2\pi x^3 - V > 0, \text{ yaitu, } x^3 > V / 2\pi.
$$

Jika kita sementara hanya mempertimbangkan $x > 0$ (satu-satunya nilai yang menarik untuk masalah asli kita), ini setara dengan $x > \sqrt[3]{V / 2\pi}$. Jadi $A$ meningkat untuk $x > \sqrt[3]{V / 2\pi}$, tetapi menurun dari 0 ke $\sqrt[3]{V / 2\pi}$. Dalam gambar di bawah ini kita telah menggambarkan grafik. Grafik $f(x) = 2\pi x^2$ digambar sebagai panduan putus-putus, karena untuk $x$ besar nilai $A(x)$ hanya sedikit lebih dari $2\pi x^2$; untuk $x$ kecil, di sisi lain, bagian $2V/x$ yang paling penting.

![](Pasted%20image%2020250622163529.png)

Untuk $x < 0$ kita memiliki $x^3 < 0$, jadi tentu $A^{\prime}(x) < 0$. Dengan demikian, fungsi $A$ harus menurun untuk $x < 0$; sedikit pemikiran menunjukkan bahwa seluruh grafik harus terlihat seperti berikut.

![](Pasted%20image%2020250622163555.png)

Jika gambar ini terlihat akrab, itu karena kita menggambarkan fungsi $f(x) = x^2 + 1/x$ di Bab 3. Grafik itu dibuat oleh program komputer yang memplot banyak titik, jadi semua nilainya sangat tepat. Seperti yang Anda lihat, bagaimanapun, pengetahuan tentang turunan memungkinkan kita untuk menggambarkan bentuk umum grafik dengan hampir tanpa perhitungan titik spesifik.

Contoh kita juga menunjukkan bahwa bahkan fungsi yang relatif sederhana dapat memiliki beberapa fitur menarik dalam grafiknya. Itulah mengapa "menggambar grafik" ternyata menjadi fitur yang cukup menonjol di semua kursus kalkulus, di mana waktu yang cukup banyak dikhususkan. Dengan sikap santai khas kita, kita akan meninggalkan semua detail menjijikkan untuk kursus Anda, dan merasa puas dengan pemahaman ide-ide utama.

Masih tetap untuk membenarkan prinsip yang kita nyatakan di atas, tetapi mungkin itu tidak tampak seperti tugas yang sangat mendesak. Tentu prinsip-prinsip ini jelas, bukan? Dan jika tidak, apakah ini sesuatu yang benar-benar ingin kita khawatirkan?
[Back](./)
