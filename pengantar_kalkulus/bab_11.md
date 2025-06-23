[Home](../)\n[Back](./)\n
## Bab 11. Mengamati para ahli bermain

Rencana perjalanan saya melalui kota-kota Belgia seperti Bruges, Ghent, Brussels, dan Namur akhirnya membawa saya ke wilayah pegunungan Ardennes. Berkemah di sini selama beberapa hari, saya berhasil melakukan panjat tebing, penyimpangan menarik, dan tentu saja hal yang memuaskan secara maskulin untuk dilakukan.

Tetapi saya cukup puas bergabung dengan turis lain yang menonton para pendaki sejati mendaki tebing tinggi yang hampir vertikal di tepi sungai, dengan hati-hati mencari pegangan yang aman untuk bergerak sedikit lebih tinggi.

Seperti panjat tebing, yang tampaknya memiliki daya tarik cukup terbatas (saya sudah lama meninggalkannya), membuktikan teorem bukanlah salah satu olahraga paling populer. Bahkan orang-orang yang bersukacita dalam kekuatan perhitungan sering lebih suka meninggalkan bukti matematika kepada jenis orang yang, ... ya, kepada mereka yang menikmati geometri di sekolah menengah. Meskipun bukti di bab terakhir mudah, banyak yang ternyata jauh lebih rumit. Jadi di bab ini Anda mungkin ingin mengadopsi peran pengamat turis.

Bahkan jika Anda suka membuktikan teorem, mencoba membuktikan prinsip yang dinyatakan pada halaman 78 mungkin terasa seperti mendaki langsung ke dinding vertikal yang mulus—tidak tampak ada cara untuk mendapatkan pegangan yang baik pada masalah. Pertimbangkan, misalnya, prinsip ketiga, dan paling sederhana:

Jika $f^{\prime}(x)=0$ untuk $a<x<b$, maka $f$ konstan untuk $a<x<b$.

Sulit membayangkan bagaimana ini bisa salah. Bahkan, fungsi $f$ yang tidak konstan apa pun yang Anda bayangkan pasti akan memiliki tempat di mana turunannya bukan 0. Masalahnya, kita hanya bisa membayangkan sejumlah fungsi yang terbatas, bukan semuanya, dan mungkin imajinasi kita tidak cukup baik; kegagalan membayangkan bagaimana pernyataan itu bisa salah tidak, sayangnya, merupakan bukti matematika bahwa itu benar (alasan, mungkin, mengapa matematikawan sering tidak disambut di juri).

Sebelum khawatir tentang bukti, kita ingin menunjukkan satu konsekuensi sederhana dari prinsip ini: Jika $f$ dan $g$ memiliki turunan yang sama di mana-mana, yaitu $f^{\prime}(x)=g^{\prime}(x)$ untuk semua $x$, maka $g(x)=f(x)+C$ untuk konstanta $C$ tertentu, sehingga grafik $g$ sejajar dengan grafik $f$. Untuk melihat ini, kita hanya mempertimbangkan fungsi $h(x)=g(x)-f(x)$. Kemudian kita memiliki $h^{\prime}(x)=g^{\prime}(x)-f^{\prime}(x)=0$. Jadi, menurut prinsip, $h$ adalah konstan, $h(x)=C$ untuk semua $x$, yang berarti $g(x)-f(x)=C$, atau $g(x)=f(x)+C$.

![](Pasted%20image%2020250622164846.png)

Jika kita bertekad memberikan bukti untuk prinsip dasar kita, maka ternyata, seperti halnya dengan panjat tebing, tujuan kita harus didekati dari jalur yang agak berputar. Untuk memulai, mari kita pertimbangkan fungsi $f$ yang memenuhi kondisi:

![](Pasted%20image%2020250622164916.png)

$$
f(a)=f(b)
$$

untuk dua angka $a<b$. Kita ingin mengasumsikan bahwa $f$ kontinu di $x$ untuk semua $a \leq x \leq b$ (fungsi kontinu adalah hampir satu-satunya jenis yang pernah kita pertimbangkan), dan kita juga ingin mengasumsikan bahwa $f$ dapat diturunkan di $x$ untuk $a<x<b$ (kita tidak terlalu peduli apakah itu dapat diturunkan di $a$ atau $b$).

Pertama-tama mari kita pertimbangkan titik $x$ yang merupakan maksimum untuk $f$, pada interval dari $a$ hingga $b$. Teorem sederhana kita dari bab sebelumnya mengatakan bahwa kita memiliki $f^{\prime}(x)=0$, jadi kita telah menemukan tempat di mana turunan $f$ adalah 0.

![](Pasted%20image%2020250622164953.png)

Sebenarnya, gambar ini mungkin salah—karena grafik $f$ mungkin tidak pernah melampaui nilai $f(a)=f(b)$. Tetapi kita juga dapat mempertimbangkan titik $x$ yang merupakan minimum untuk $f$, dan kemudian kesimpulan yang sama berlaku: $f^{\prime}(x)=0$.

![](Pasted%20image%2020250622165025.png)

Akhirnya, bisakah kedua gambar ini salah? Artinya, bisakah terjadi bahwa grafik $f$ tidak pernah melampaui nilai $f(a)=f(b)$ dan juga tidak pernah di bawahnya? Tentu saja bisa, tetapi hanya jika $f$ memiliki nilai konstan $f(a)=f(b)$, dan dalam kasus itu kita memiliki $f^{\prime}(x)=0$ untuk setiap $x$ dengan $a<x<b$.

Anehnya, pengamatan sederhana ini telah diberikan status Teorem (dan yang lebih aneh lagi, dinamai setelah seorang matematikawan yang tidak ada hubungannya dengan kalkulus):

**Teorem Rolle.** Misalkan $f$ kontinu di $x$ untuk $a \leq x \leq b$ dan dapat diturunkan di $x$ untuk $a<x<b$ dan misalkan selanjutnya bahwa:

$$
f(a)=f(b).
$$

Kemudian ada beberapa $x$ yang memenuhi $a<x<b$ untuk mana kita memiliki:

$$
f^{\prime}(x)=0.
$$

Gambar di bawah ini menunjukkan grafik fungsi $f$, didefinisikan untuk $a \leq x \leq b$, di mana kita tentu saja tidak memiliki $f(a)=f(b)$, sehingga Teorem Rolle tidak berlaku. 

![](Pasted%20image%2020250622165142.png)

Garis lurus $L$ yang melewati dua ujung $(a, f(a))$ dan $(b, f(b))$ dari kurva kita memiliki kemiringan:

$$
\text{ kemiringan } L = \frac{f(b)-f(a)}{b-a}.
$$

Daripada mencari maksimum atau minimum $f$, kita malah akan mencari titik $P$ di mana grafik $f$ paling jauh dari $L$. Dalam gambar terlihat seolah-olah garis singgung di titik ini sejajar dengan $L$.

![](Pasted%20image%2020250622165259.png)

Memang, jika kita meletakkan kaca pembesar di atas grafik $f$ di titik $P$, kita tidak bisa mendapatkan gambar seperti:

![](Pasted%20image%2020250622165329.png)

karena maka titik seperti $Q$ akan lebih jauh dari $L$ daripada $P$.

Jadi benar-benar harus benar bahwa garis singgung di $P=(x, f(x))$ sejajar dengan $L$, yang berarti:

$$
f^{\prime}(x) = \text{ kemiringan } L = \frac{f(b)-f(a)}{b-a}.
$$

Jika kita memikirkan $f(t)$ sebagai posisi beberapa objek pada waktu $t$, maka kemiringan ini mewakili kecepatan rata-rata objek ini dari waktu $a$ ke waktu $b$. Dengan kata lain, kita telah menemukan $x$ dengan $a<x<b$ sehingga kecepatan (instan) $f^{\prime}(x)$ persis sama dengan kecepatan rata-rata, atau "rata-rata" kecepatan, dari waktu $a$ ke waktu $b$. Hasil ini dikenal sebagai:

**Teorem Nilai Rata-rata.** Jika $f$ kontinu di $x$ untuk $a \leq x \leq b$ dan dapat diturunkan di $x$ untuk $a<x<b$, maka ada beberapa $x$ dengan $a<x<b$ untuk mana kita memiliki:

$$
f^{\prime}(x) = \frac{f(b)-f(a)}{b-a}.
$$

Argumen kaca pembesar kita untuk Teorem Nilai Rata-rata mungkin terasa sedikit tidak memuaskan, tetapi itu sesuatu yang akan kita khawatirkan nanti. Yang penting adalah hanya mengingat pernyataan, dan memahami makna, dari hasil ini, yang ternyata menjadi salah satu hasil teoretis terpenting dalam kalkulus. Jika seseorang pernah menanyakan pertanyaan yang terdengar teoretis tentang kalkulus dan Anda tidak tahu jawabannya, coba katakan "Ini mengikuti dari Teorem Nilai Rata-rata" dan Anda akan benar 90% dari waktu (10% sisanya Anda mungkin akhirnya terlihat cukup konyol).

Hanya untuk membuktikan ini, kita sekarang akan menetapkan prinsip yang sebelumnya tampak sangat sulit.

**Teorem.** Jika $f^{\prime}(x) > 0$ untuk $a<x<b$, maka $f$ meningkat dari $a$ ke $b$. Jika $f^{\prime}(x) < 0$ untuk $a<x<b$, maka $f$ menurun dari $a$ ke $b$. Dan jika $f^{\prime}(x) = 0$ untuk $a<x<b$, maka $f$ konstan untuk $a<x<b$.

**Bukti:** Pertimbangkan dua titik apa pun $x_0$ dan $x_1$ antara $a$ dan $b$ dengan:

$$
x_0 < x_1.
$$

Kita ingin membandingkan nilai $f(x_0)$ dan $f(x_1)$, dan untuk melakukan ini, kita akan menerapkan Teorem Nilai Rata-rata pada interval dari $x_0$ ke $x_1$.

![](Pasted%20image%2020250622165534.png)

Ini memberi tahu kita bahwa:

$$
\frac{f(x_1) - f(x_0)}{x_1 - x_0} = f^{\prime}(x),
$$

atau:

$$
\text{(*) }f(x_1) - f(x_0) = f^{\prime}(x) \cdot (x_1 - x_0)
$$

untuk beberapa $x$ antara $x_0$ dan $x_1$, dan dengan demikian juga antara $a$ dan $b$.

Sekarang jika $f^{\prime}(x)$ selalu positif, maka (`*`) menunjukkan bahwa $f(x_1) - f(x_0)$ juga positif (faktor $x_1 - x_0$ positif, karena kita memilih $x_0 < x_1$). Dengan kata lain, jika $f^{\prime}(x)$ selalu positif, maka $f(x_1) > f(x_0)$ untuk $x_1 > x_0$, sehingga $f$ meningkat.

Demikian pula, jika $f^{\prime}(x)$ selalu negatif, maka $f(x_1) - f(x_0)$ juga negatif, sehingga $f(x_1) < f(x_0)$. Dengan demikian, $f$ menurun.

Akhirnya, jika $f^{\prime}(x)$ selalu 0, maka $f(x_1) - f(x_0) = 0$, yaitu, $f(x_0) = f(x_1)$ untuk dua titik apa pun $x_0, x_1$ antara $a$ dan $b$, sehingga fungsi $f$ konstan untuk $a < x < b$. **Q.E.D.**

Setelah keberhasilan ini, Anda mungkin menginginkan bukti yang lebih analitis dari Teorem Nilai Rata-rata, tidak bergantung pada gambar kaca pembesar. Di sini, untuk turis yang lebih petualang, adalah argumen standar, yang mendasarkan Teorem Nilai Rata-rata langsung dari Teorem Rolle. Bukan menemukan titik yang diinginkan dengan kriteria geometris, kita hanya menggunakan beberapa manipulasi aljabar yang sedikit rumit.

**Bukti Teorem Nilai Rata-rata:** Kita akan menggunakan $m$ untuk rasio:

$$
m = \frac{f(b) - f(a)}{b - a}.
$$

Pertimbangkan fungsi $g$ yang didefinisikan berdasarkan $f$ dengan:

$$
\begin{aligned}
g(x) & = f(x) - m(x - a) \\
& = f(x) - \left[ \frac{f(b) - f(a)}{b - a} \right] (x - a).
\end{aligned}
$$

Meskipun mungkin terlihat sedikit rumit, kita telah sengaja membuat $g$ sehingga memiliki sifat sederhana.

Pertama-tama, kita memiliki:

$$
g(a) = f(a).
$$

Kemudian yang kedua,

$$
\begin{aligned}
g(b) & = f(b) - m(b - a) \\
& = f(b) - \left[ \frac{f(b) - f(a)}{b - a} \right] (b - a) \\
& = f(b) - [f(b) - f(a)] \\
& = f(a).
\end{aligned}
$$

Dengan kata lain, kita memiliki:

$$
\text{(1)}\quad g(b) \equiv g(a).
$$

Juga perhatikan dalam definisi:

$$
g(x) = f(x) - m(x - a) = f(x) - m x + m a,
$$

bahwa $m$ hanyalah konstanta, sehingga kita memiliki:

$$
\text{(2)} \quad g^{\prime}(x) = f^{\prime}(x) - m.
$$

Sekarang karena (1), Teorem Rolle berlaku untuk $g$, sehingga kita memiliki:

$$
g^{\prime}(x) = 0
$$

untuk beberapa $x$. Tetapi menurut (2) ini berarti:

$$
f^{\prime}(x) - m = 0,
$$

yang persis apa yang ingin kita buktikan. **Q.E.D.**
[Back](./)
