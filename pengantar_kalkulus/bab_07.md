[Home](../)

[Back](./)


## Bab 7. Keluar dari jalur

Berbeda dengan mayoritas teman sekelas saya di sekolah menengah, saya menikmati sebagian besar kelas matematika saya, dan saya sangat menyukai geometri (baiklah, matematikawan memang orang-orang yang lucu, Anda sudah tahu itu). Saya sangat terkesan ketika sebuah ide intuitif bisa diberikan definisi yang tepat. Misalnya, saya cukup terkejut dengan senang hati ketika sudut siku-siku $\angle ABC$ hanya didefinisikan sebagai sudut yang sama dengan sudut pelengkapnya $\angle DBC$—definisi singkat ini jelas mengekspresikan dengan tepat ide bahwa garis tegak lurus tidak condong lebih ke satu sisi daripada sisi lainnya.

![](attachment/Pasted%20image%2020250622100435.png)

Namun, saya tidak begitu nyaman kemudian ketika garis singgung (*tangent line*) ke lingkaran didefinisikan sebagai garis lurus yang hanya memotong lingkaran sekali.

![](attachment/Pasted%20image%2020250622100535.png)

Saya mungkin tidak akan bisa mengungkapkan ketidaknyamanan saya dalam kata-kata pada saat itu, tetapi jelas ada sesuatu yang kurang memuaskan dari definisi ini. Misalnya, siapa pun bisa melihat bahwa garis lurus dalam gambar di bawah ini adalah garis singgung ke lingkaran, meskipun hanya sebagian kecil lingkaran yang digambar, sehingga kita tidak berada dalam posisi untuk memeriksa bahwa garis tersebut tidak memotong lingkaran di tempat lain. 

![](attachment/Pasted%20image%2020250622100641.png)

Demikian pula, garis lurus dalam gambar berikutnya jelas bukan garis singgung ke lingkaran, meskipun titik potong lainnya tidak ada dalam gambar, dan bahkan berada di luar halaman sepenuhnya. 

![](attachment/Pasted%20image%2020250622100701.png)

Kriteria ini, yaitu memotong lingkaran hanya sekali, tampaknya tidak menangkap ide intuitif bahwa garis singgung hanya "menggosok" lingkaran.

Memang benar, meskipun definisi ini tidak tampak mengekspresikan ide intuitif kita, definisi tersebut benar, dan seseorang dapat menggunakannya untuk membuktikan semua hasil yang diharapkan dalam geometri datar. Tetapi keberatan kita menjadi jauh lebih substansial ketika kita mempertimbangkan kurva selain lingkaran.

Misalnya, bagaimana dengan parabola? Garis lurus dalam gambar ini, yang tentu saja tampaknya menjadi garis yang akan kita pilih sebagai garis singgung, memang memiliki sifat bahwa ia memotong parabola hanya sekali. 

![](attachment/Pasted%20image%2020250622100816.png)

Masalahnya, garis ini bukan satu-satunya yang memiliki sifat ini: faktanya, garis vertikal melalui titik ini juga memiliki sifat ini, dan kita tentu tidak ingin menyebutnya garis singgung!

![](attachment/Pasted%20image%2020250622100832.png)

Masalah menjadi semakin akut ketika kita mempertimbangkan kurva yang sedikit lebih rumit, misalnya grafik dari $f(x)=x^3$. Sepertinya masuk akal untuk menyebut garis lurus tebal dalam gambar ini sebagai garis singgung—ia tampak "menggosok" kurva dengan cara yang sama seperti garis singgung ke lingkaran atau parabola—tetapi garis lurus ini memotong kurva di lebih dari satu titik. Berbagai garis lurus lain yang memang memotong kurva hanya sekali (garis putus-putus dalam gambar) tentu tidak boleh disebut garis singgung!

![](attachment/Pasted%20image%2020250622100916.png)

Meskipun kita telah menggunakan kata "menggosok" yang agak samar dalam diskusi ini, kita dapat memberikan substansi pada konsep ini dengan menggunakan teknik yang sama persis yang kita gunakan di Bab 4. Notion bahwa garis lurus "menggosok" kurva di titik tertentu $P$ adalah satu yang melibatkan perilaku kurva sangat dekat dengan $P$, bukan di titik yang jauh. Jadi kita akan meletakkan kaca pembesar di atas titik ini, dan melihat jenis gambar apa yang kita dapatkan.

![](attachment/Pasted%20image%2020250622100942.png)

Mari kita pertimbangkan lagi parabola $f(x)=x^2$, bersama dengan titik $P=(1,1)$ pada parabola, dan garis lurus vertikal melalui titik ini.

![](attachment/Pasted%20image%2020250622101004.png)

Jika kita meletakkan kaca pembesar yang memperbesar segalanya dengan faktor 5 di atas titik $P$, kita mendapatkan gambar:

![](attachment/Pasted%20image%2020250622101024.png)

Garis lurus vertikal tetap lurus, tentu saja, sementara bagian parabola yang diperbesar menunjukkan hanya sedikit kelengkungan.

Ketika kita memperbesar segalanya dengan faktor besar, seperti 100, garis lurus vertikal kita tetap sama, dan parabola kita menjadi hampir seperti garis lurus:

![](attachment/Pasted%20image%2020250622101053.png)

Hal-hal tampak cukup berbeda, bagaimanapun, jika kita memulai dengan garis singgung ke parabola di $P=(1,1)$.

![](attachment/Pasted%20image%2020250622101118.png)

Memperbesar segalanya dengan faktor 5 menghasilkan gambar:

![](attachment/Pasted%20image%2020250622101131.png)

Tentu saja, garis singgung lurus tetap menjadi garis lurus, tetapi karena garis singgung menggosok parabola, versi yang diperbesar masih menggosok bagian parabola yang diperbesar, yang lagi-lagi menunjukkan hanya sedikit kelengkungan.

Apa yang terjadi, lalu, ketika kita memperbesar segalanya dengan faktor 100? Parabola kita menjadi hampir garis lurus, dan garis lurus ini bertepatan dengan gambar yang diperbesar dari garis singgung kita. Dengan kata lain, garis singgung adalah garis lurus yang pertama kali kita temukan kembali di Bab 4, ketika kita memperbesar kurva kita dengan jumlah yang sangat besar. Lebih tepatnya, kita mungkin juga cukup mendefinisikan garis singgung sebagai garis ini.

![](attachment/Pasted%20image%2020250622101241.png)

Jadi, untuk mengatur hal-hal dalam urutan logis, untuk sebuah fungsi $f$ kita mendefinisikan:

$$
f^{\prime}(a)=\lim_{h \rightarrow 0} \frac{f(a+h)-f(a)}{h},
$$

dan kemudian kita mendefinisikan garis singgung ke grafik $f$ di titik $(a, f(a))$ sebagai garis melalui titik ini dengan kemiringan $f^{\prime}(a)$. Karena kita sekarang telah mendefinisikan garis singgung berdasarkan titik yang dilaluinya dan kemiringannya, kita dapat menuliskan persamaan eksplisit untuk garis lurus ini dengan menggunakan bentuk titik-kemiringan dari Bab 2.

Semua itu dikatakan dengan cara yang sangat umum, jadi mari kita lebih spesifik, dan mencari persamaan garis singgung parabola $f(x)=x^2$ di titik $P=(1,1)$. Di Bab 5 kita menemukan bahwa kemiringan garis ini adalah:

$$
f^{\prime}(1)=2 \cdot 1=2.
$$

Karena garis ini melalui titik $P=(1,1)$, garis ini oleh karena itu memiliki bentuk titik-kemiringan:

$$
y-1=2(x-1),
$$

atau bentuk kemiringan-sistem koordinat:

$$
\text {(1) }y=2x-1.
$$

![](attachment/Pasted%20image%2020250622101358.png)

Sekarang setelah kita memiliki persamaan garis singgung ini, kita dapat dengan mudah memeriksa bahwa itu benar-benar memotong parabola $f(x)=x^2$ hanya sekali, seperti dalam gambar. Bahkan, jika sebuah titik $(x, y)$ memenuhi keduanya:

$$
\begin{cases}
y=x^2 & \text{sehingga titik itu ada pada grafik } f(x)=x^2, \\
y=2x-1 & \text{sehingga titik itu ada pada garis singgung, dengan persamaan (1)}
\end{cases}
$$

maka kita memiliki:

$$
x^2=2x-1,
$$

atau:

$$
0=x^2-2x+1.
$$

Dan memang benar, persamaan ini hanya memiliki solusi $x=1$, karena dapat ditulis sebagai:

$$
0=x^2-2x+1=(x-1)^2.
$$

Tidak perlu kita mempertahankan perhatian kita pada titik $P=(1,1); kita bisa juga mempertimbangkan titik sembarang $P=\left(a, a^2\right)$ pada parabola $f(x)=x^2$. Kita tahu bahwa:

$$
f^{\prime}(a)=2a,
$$

jadi persamaan garis singgung, yang melalui $\left(a, a^2\right)$ dan memiliki kemiringan $2a$, adalah:

$$
y-a^2=2a(x-a),
$$

atau:

$$
y=2ax-a^2.
$$

### Menguap dan Merenggangkan Badan Setelah Istirahat

1. Periksa bahwa garis lurus ini memotong parabola hanya di titik $\left(a, a^2\right)$.
2. (a) Untuk fungsi $f(x)=x^3$, tunjukkan bahwa persamaan garis singgung melalui titik $\left(a, a^3\right)$ adalah:

$$
y=3a^2x-2a^3.
$$

(b) Tunjukkan bahwa jika $(x, y)$ ada pada perpotongan garis singgung ini dan grafik $f(x)=x^3$, maka:

$$
x^3-3a^2x+2a^3=0.
$$

(c) Persamaan ini secara alami memiliki akar $x=a$, sehingga $x^3-3a^2x+2a^3$ dapat dibagi oleh $(x-a)$. Tunjukkan bahwa:

$$
\begin{aligned}
x^3-3a^2x+2a^3 & =(x-a)(x^2+ax-2a^2) \\
& =(x-a)(x-a)(x+2a).
\end{aligned}
$$

(d) Di titik apa lagi garis singgung ini memotong grafik $f(x)=x^3$? Pastikan jawaban Anda terlihat masuk akal dalam gambar.

[Back](./)
