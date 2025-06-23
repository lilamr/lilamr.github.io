[Home](../)\n[Back](./)\n
## Bab 9. Permasalahan sinus

Sampai saat ini kita telah menemukan banyak konsep baru, tetapi, seperti biasa dalam proses penemuan semacam itu, ide-ide tersebut tidak selalu muncul dalam urutan yang paling logis. Jadi mungkin ide yang baik untuk merangkum perjalanan kita sejauh ini dengan cepat.

1. Ide pertama (secara logis berbicara) adalah konsep limit,

$$
\lim_{x \rightarrow a} f(x)=A.
$$

Konsep ini dapat digunakan untuk mendefinisikan kontinuitas,

$$
\lim_{x \rightarrow a} f(x)=f(a),
$$

persamaan yang menyatakan fakta bahwa fungsi $f$ tidak melonjak atau melakukan sesuatu yang liar di dekat angka $a$.

Tetapi limit juga digunakan untuk tujuan yang jauh lebih penting.

2. Untuk limit khusus:

$$
f^{\prime}(x)=\frac{df(x)}{dx}=\lim_{h \rightarrow 0} \frac{f(x+h)-f(x)}{h},
$$

yang kita sebut turunan, pembilang dan penyebut keduanya memiliki nilai 0 untuk $h=0$, sehingga tidak ada pertanyaan untuk mengevaluasi limit tanpa setidaknya sedikit trik aljabar.

Kita telah menyediakan cukup perhitungan untuk menemukan $f^{\prime}(x)$ untuk beberapa fungsi; menggunakan hasil tentang limit, dan trik aljabar yang tepat, maka memungkinkan untuk mendapatkan rumus untuk banyak fungsi lainnya.

3. Turunan ternyata memiliki interpretasi geometris yang penting: $f^{\prime}(a)$ adalah kemiringan garis singgung ke grafik $f$ di titik $(a, f(a))$.

4. Selain itu, turunan ternyata memiliki interpretasi fisik yang penting: ketika $s(t)$ mewakili posisi pada waktu $t$, turunan $s^{\prime}(t)$ mewakili kecepatan pada waktu $t$.

Kita tidak banyak menghabiskan waktu untuk menyatakan teorem tentang limit atau turunan, meskipun kita telah menyediakan cukup perhitungan untuk menemukan $f^{\prime}(x)$ untuk beberapa fungsi sederhana. Dalam semua kasus tersebut, perhitungan kita memungkinkan karena rumus untuk:

$$
\frac{f(x+h)-f(x)}{h}
$$

dapat disederhanakan secara aljabar dengan cara yang membuat hasilnya jelas. Sekarang kita akan lebih berani, dan mencoba menemukan turunan dari fungsi $f(x)=\sin x$.

Ingat bahwa grafik fungsi $f(x)=\sin x$ adalah kurva yang cukup menarik, memang cukup berliku. 

![](Pasted%20image%2020250622102121.png)

Lebih tepatnya, ia memiliki bentuk yang menyenangkan secara estetika ketika kita menggunakan ukuran radian. Ingat ini berarti bahwa untuk sebuah angka $h$, kita memilih titik $B$ pada lingkaran satuan sehingga busur $\widehat{A B}$ dari lingkaran ini memiliki panjang $h$; kemudian $\sin h$ adalah panjang garis tegak lurus $BC$, sementara $\cos h$ adalah panjang garis $OC$.

![](Pasted%20image%2020250622102141.png)

Ingat juga bahwa alih-alih mengukur panjang $\widehat{AB}$ kita bisa mengukur luas: sudut $AOB$ adalah sudut $h$ radian 

![](Pasted%20image%2020250622102256.png)

ketika sektor yang diarsir $AOB$ memiliki luas yang diberikan oleh:

$$
\text{(A) } \text{ luas } \triangle = \frac{h}{2}.
$$

Sekarang kita siap menangani masalah menemukan:

$$
\sin^{\prime}(x)=\lim_{h \rightarrow 0} \frac{\sin (x+h)-\sin x}{h}.
$$

Anda tidak perlu merasa harus dapat mereproduksi perhitungan berikut (saya harus melirik buku untuk menyegarkan ingatan saya). Tetapi layak membaca argumen ini sekali, hanya untuk mendapatkan gambaran tentang jenis manuver yang mungkin diperlukan untuk menemukan turunan—lagipula, Anda tidak ingin menjalani hidup dengan kesan keliru bahwa itu selalu hanya sekumpulan trik aljabar.

Meskipun argumen ini mungkin tampak panjang, sebenarnya ini hanya kombinasi dari beberapa langkah yang relatif singkat.

**Langkah 1.** Untuk fungsi seperti $f(x)=x^2$, kita dapat menggunakan aljabar untuk mengembangkan ekspresi seperti $(x+h)^2$. Dalam kasus ini kita memiliki rumus penjumlahan penting dari trigonometri:

$$
\sin (x+y)=\sin x \cos y + \cos x \sin y.
$$

Menggunakan ini (dengan $y=h$) kita dapat menulis:

$$
\begin{aligned}
\sin^{\prime}(x) & = \lim_{h \rightarrow 0} \frac{\sin (x+h)-\sin x}{h} \\
& = \lim_{h \rightarrow 0} \frac{\sin x \cos h + \cos x \sin h - \sin x}{h} \\
& = \lim_{h \rightarrow 0} \left( \frac{\cos x \sin h}{h} + \frac{\sin x \cos h}{h} - \frac{\sin x}{h} \right).
\end{aligned}
$$

Menggunakan fakta sederhana tentang limit, yang disebutkan secara singkat di Bab 6, kita kemudian dapat menulis:

$$
\begin{aligned}
\text{(C) }\sin^{\prime}(x) & = \lim_{h \rightarrow 0} \left( \frac{\cos x \sin h}{h} \right) + \lim_{h \rightarrow 0} \left( \frac{\sin x \cos h}{h} - \frac{\sin x}{h} \right) \\
& = \lim_{h \rightarrow 0} \left( \frac{\cos x \sin h}{h} \right) + \lim_{h \rightarrow 0} \left( \frac{\sin x (\cos h-1)}{h} \right) \\
& = \left[ \lim_{h \rightarrow 0} \frac{\sin h}{h} \right] \cos x + \left[ \lim_{h \rightarrow 0} \frac{\cos h-1}{h} \right] \sin x.
\end{aligned}
$$

Sekarang ini mungkin sama sekali tidak terlihat seperti kemajuan. Memang, alih-alih satu limit yang melibatkan pecahan yang pembilang dan penyebutnya keduanya memiliki nilai 0 ketika $h=0$, kita sekarang memiliki dua limit seperti itu! (Ingat bahwa $\cos 0=1$.)

Tetapi sudah ada satu fitur yang menggembirakan dari ekspresi akhir ini. Tentu saja $\sin^{\prime}(x)$ bergantung pada $x$, seperti halnya ekspresi akhir (C). Perhatikan, bagaimanapun, bahwa limit dalam ekspresi akhir ini tidak bergantung pada $x$. Setelah kita berhasil mencari tahu dua limit spesifik:

$$
\begin{aligned}
\text{(L1) }& \lim_{h \rightarrow 0} \frac{\sin h}{h} = ? \\
\text{(L2) }& \lim_{h \rightarrow 0} \frac{\cos h-1}{h} = ?
\end{aligned}
$$

(asalkan kita bisa menemukannya), kita akan tahu $\sin^{\prime}(x)$ untuk semua $x$.

**Langkah 2a.** Mari kita tangani $\left(L_1\right)$ terlebih dahulu. Pada titik ini kita tidak memiliki rumus atau manipulasi aljabar yang dapat menyelamatkan kita; kita hanya akan harus mengingat apa arti semuanya! Gambar di bawah ini menunjukkan, sekali lagi, sudut $h$ (busur lingkaran $\widehat{A B}$ memiliki panjang $h$), dan $\sin h$ (panjang garis tegak lurus $BC$). 

![](Pasted%20image%2020250622103304.png)

Tentu saja, kita benar-benar hanya tertarik pada situasi ketika $h$ sangat kecil, sehingga gambar kita seharusnya benar-benar merupakan bagian yang sangat sangat kecil dari lingkaran, dengan garis $BC$ yang sangat sangat pendek yang sesuai.

![](Pasted%20image%2020250622103324.png)

Tetapi entah kita menggambarnya besar atau kecil, tentu saja tidak terlihat jelas bagaimana kita bisa mengatakan sesuatu tentang panjang $BC$ dalam hal $h$, dan untuk saat ini akan lebih sederhana untuk menggambar gambar dengan $h$ cukup besar, hanya agar kita bisa melihat apa yang kita bicarakan.

Ingat bahwa alih-alih menentukan titik $B$ dengan kondisi bahwa busur $\widehat{AB}$ memiliki panjang $h$, kita bisa sama baiknya menggunakan kondisi alternatif (A), bahwa sektor $OAB$ 

![](Pasted%20image%2020250622103453.png)

memiliki luas:

$$
\text{ luas } \triangle = \frac{h}{2}.
$$

Gambar di bawah ini menunjukkan segitiga yang diarsir $\triangle OAB$ dalam sektor ini. 

![](Pasted%20image%2020250622103616.png)

Tinggi segitiga ini adalah segmen $BC$, yang sama dengan $\sin h$, sementara alasnya adalah garis $OA$, yang memiliki panjang 1, karena ini adalah lingkaran satuan. Jadi luas segitiga yang diarsir adalah:

$$
\text{ luas } \Delta = \frac{1}{2} \sin h \cdot 1 = \frac{\sin h}{2}.
$$

Karena jelas kita memiliki:

$$
\text{ luas } \Delta < \text{ luas } \triangle,
$$

maka mengikuti bahwa kita memiliki:

$$
\frac{\sin h}{2} < \frac{h}{2}.
$$

Membagi dengan $h$ kita sehingga memiliki:

$$
\text{(a) }\frac{\sin h}{h} < 1.
$$

Sebenarnya tidak terlalu perlu menggunakan luas untuk mendapatkan ketidaksamaan ini. Lagipula, $\sin h$ adalah panjang $BC$, dan panjang garis tegak lurus ini lebih kecil daripada panjang garis miring $AB$, sementara panjang garis ini $AB$ pada gilirannya lebih kecil daripada panjang busur melengkung $\widehat{AB}$ yang sebesar $h$.

![](Pasted%20image%2020250622104327.png)

**Langkah 2b.** Tetapi luas akan benar-benar berguna untuk informasi kita berikutnya. Dalam gambar di bawah ini, kita akan melihat segitiga $\triangle OAB'$, yang mengelilingi sektor asli kita. 

![](Pasted%20image%2020250622104358.png)

Karena $\triangle OAB'$ serupa dengan $\triangle OCB$, kita memiliki:

$$
\frac{B'A}{OA} = \frac{BC}{OC} = \frac{\sin h}{\cos h},
$$

dan karena $OA$ memiliki panjang 1, ini berarti:

$$
B'A = \frac{\sin h}{\cos h}.
$$

Oleh karena itu luas $\triangle OAB'$ adalah:

$$
\text{ luas } \triangle = \frac{1}{2} \cdot OA \cdot B'A = \frac{1}{2} \cdot 1 \cdot B'A = \frac{1}{2} \cdot \frac{\sin h}{\cos h}.
$$

Karena jelas kita memiliki:

$$
\text{ luas } \Delta < \text{ luas } \triangle,
$$

maka mengikuti bahwa:

$$
\frac{h}{2} < \frac{1}{2} \cdot \frac{\sin h}{\cos h},
$$

yang memberikan:

$$
\text{(b) }\cos h < \frac{\sin h}{h}.
$$

**Langkah 3.** Nah, itu sedikit memakan tenaga, tetapi sekarang kita pada dasarnya selesai. Menggabungkan (a) dan (b) kita memiliki:

$$
\text{(*) }\cos h < \frac{\sin h}{h} < 1.
$$

Ingat bahwa ketika $h$ kecil, angka $\cos h$ mendekati 1. Jadi (`*`) menunjukkan bahwa:

$$
\frac{\sin h}{h}
$$

berada di antara 1 dan sesuatu yang semakin mendekati 1 saat kita membuat $h$ semakin kecil. Ini berarti:

$$
\frac{\sin h}{h} \text { itu sendiri}
$$

harus semakin mendekati 1 saat kita membuat $h$ semakin kecil. Dengan kata lain, kita telah menetapkan:

$$
\text{(L1) }\lim_{h \rightarrow 0} \frac{\sin h}{h} = 1.
$$

**Langkah 4.** Setelah semua kerja keras ini, Anda mungkin tidak antusias dengan ide untuk menyerang limit kedua $\left(L_2\right)$. Untungnya, kita tidak lagi harus menggunakan trik geometris. Setelah menetapkan $\left(L_1\right)$, kita dapat menemukan limit $\left(L_2\right)$ dengan trik aljabar yang cukup standar:

$$
\begin{aligned}
\lim_{h \rightarrow 0} \frac{\cos h-1}{h} & = \lim_{h \rightarrow 0} \frac{\cos h-1}{h} \cdot \frac{\cos h+1}{\cos h+1} \\
& = \lim_{h \rightarrow 0} \frac{(\cos h-1)(\cos h+1)}{h(\cos h+1)} \\
& = \lim_{h \rightarrow 0} \frac{\cos^2 h-1}{h(\cos h+1)} \\
& = \lim_{h \rightarrow 0} \frac{-\sin^2 h}{h(\cos h+1)} \quad \text{ (ingat halaman 21) } \\
& = \lim_{h \rightarrow 0} \frac{\sin h}{h} \cdot \lim_{h \rightarrow 0} \frac{-\sin h}{\cos h+1}.
\end{aligned}
$$

Sekarang limit pertama adalah limit $\left(L_1\right)$ yang sudah kita temukan. Bagaimana dengan limit kedua? Nah, seperti yang sering terjadi, pembilang memiliki nilai 0 ketika $h=0$; tetapi dalam kasus ini penyebut tidak! Ketika $h$ mendekati 0, pembilang hanya mendekati 2, sehingga seluruh pecahan mendekati 0. Ini berarti limit produk juga 0. Dengan kata lain, kita telah menetapkan:

$$
\text{(L2) }\lim_{h \rightarrow 0} \frac{\cos h-1}{h} = 0.
$$

**Langkah 5.** Akhirnya, kita cukup menyisipkan limit $\left(L_1\right)$ dan $\left(L_2\right)$ kembali ke (C) dan kita mendapatkan rumus yang diinginkan:

$$
\sin^{\prime}(x) = \cos x.
$$

Meskipun langkah-langkah yang mengarah kepadanya mungkin dianggap agak rumit, Anda harus mengakui bahwa hasil akhir itu sendiri adalah rumus paling sederhana yang bisa diharapkan! Meski begitu, mungkin ide yang baik untuk memeriksa bahwa rumus ini benar-benar memberikan hasil yang tampak masuk akal.

Pertama-tama, kita memiliki:

$$
\sin^{\prime}(0) = \cos 0 = 1.
$$

Ini berarti garis singgung ke grafik $f(x)=\sin x$ di titik $(0,0)$ memiliki kemiringan 1, yang tampak masuk akal dari grafik. 

![](Pasted%20image%2020250622105232.png)

Di titik $\pi/2$, sebuah "puncak" grafik, kita memiliki:

$$
\sin^{\prime}(\pi/2) = \cos \pi/2 = 0,
$$

sementara di $\pi$ kita memiliki:

$$
\sin^{\prime}(\pi) = \cos \pi = -1,
$$

dan kemudian di $3\pi/2$, sebuah "lembah," kita sekali lagi memiliki:

$$
\sin^{\prime}(3\pi/2) = \cos (3\pi/2) = 0.
$$

Ketika grafik sin dan cos disajikan bersama, Anda seharusnya dapat meyakinkan diri sendiri bahwa cos memiliki setidaknya penampilan dasar yang tepat untuk turunan $\sin^{\prime}$: yaitu, cos positif di tempat-tempat di mana $\sin^{\prime}$ seharusnya positif, negatif di tempat-tempat di mana $\sin^{\prime}$ seharusnya negatif, dan nol di tempat yang tepat.

![](Pasted%20image%2020250622105336.png)

Setelah menemukan turunan fungsi sin, wajar untuk bertanya tentang turunan fungsi cos. Prosedur langsung adalah dengan memulai dengan definisi:

$$
\cos^{\prime}(x) = \lim_{h \rightarrow 0} \frac{\cos (x+h)-\cos x}{h},
$$

dan menggunakan rumus penjumlahan lain dari trigonometri:

$$
\cos (x+y) = \cos x \cos y - \sin x \sin y.
$$

Kita dengan cepat menemukan bahwa:

$$
\cos^{\prime}(x) = \left( \lim_{h \rightarrow 0} \frac{\sin h}{h} \right) \cdot (-\sin x) + \left( \lim_{h \rightarrow 0} \frac{\cos h-1}{h} \right) \cdot \cos x,
$$

dan limit $\left(L_1\right)$ dan $\left(L_2\right)$ dengan demikian langsung mengarah pada hasil:

$$
\cos^{\prime}(x) = -\sin x.
$$

Ingat tanda minus di sini—itu penting.

Sekali lagi, ketika grafik cos dan sin disajikan bersama, Anda seharusnya dapat meyakinkan diri sendiri bahwa fungsi $f(x)=-\sin x$ memiliki setidaknya penampilan dasar yang tepat untuk turunan $\cos^{\prime}$: yaitu, sin negatif di tempat-tempat di mana $\cos^{\prime}$ seharusnya positif, positif di tempat-tempat di mana $\cos^{\prime}$ seharusnya negatif, dan nol di tempat yang tepat.

![](Pasted%20image%2020250622105444.png)
[Back](./)
