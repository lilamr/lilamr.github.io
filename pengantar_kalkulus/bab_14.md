[Home](../)

[Back](./)


## Bab 14. Mendekati akhir perjalanan kita

Upaya kita untuk menemukan luas di bawah grafik fungsi dimulai dengan beberapa persegi panjang spesifik untuk fungsi $f(x)=x^2$, dan kemudian berkembang menjadi jumlah umum untuk fungsi apa pun $f$,

$$
\text{(*)} \quad \sum_{i=1}^n f(x_i) \Delta x_i,
$$

yang pada gilirannya membawa pada pengenalan notasi $\int_a^b f(x) dx$. Tetapi keberhasilan utama kita dalam mengevaluasi integral adalah melalui Teorema Dasar Kalkulus, yang kita turunkan langsung dari sifat-sifat sederhana luas, terutama sifat penjumlahan (A) di bab 12. Jadi pengenalan penjumlahan (`*`) mungkin tampak seperti hiasan yang tidak perlu.

Matematikawan teoretis hampir tidak memandang masalah ini seperti itu, karena bagi mereka konsep area harus didefinisikan, dan definisi yang paling masuk akal adalah melalui penjumlahan (`*`).

Tetapi penjumlahan ini juga memainkan peran sangat penting lainnya. Karena ternyata banyak besaran selain luas yang dapat diekspresikan dalam bentuk penjumlahan semacam ini, dan dengan demikian dapat dihitung sebagai integral.

Misalnya, misalkan kita memiliki pelat logam tipis dengan lebar $W$, tinggi $H$, dan kedalaman $D$, seperti yang ditunjukkan pada gambar di sebelah kiri. 

![](Pasted%20image%2020250622210712.png)

Mari kita asumsikan, lebih lanjut, bahwa kepadatan logam di pelat ini bervariasi, tetapi hanya dengan cara yang bergantung pada $x$. Dengan kata lain, untuk setiap $x$, ada angka $\rho(x)$ yang merupakan kepadatan di seluruh bagian pada jarak $x$ dari asal, seperti yang diilustrasikan pada gambar di sebelah kanan.

Jika kepadatan $\rho$ konstan, maka berat pelat logam akan sederhana kali volume dengan $\rho$,

$$
\text{ berat } = D \cdot H \cdot W \cdot \rho.
$$

Masalahnya adalah menemukan rumus untuk berat ketika kepadatan bervariasi dengan $x$.

Pada gambar di bawah ini, kita telah memilih titik-titik:

$$
0 = t_0, t_1, \ldots, t_{i-1}, t_i, \ldots, t_n = W,
$$

bersama dengan titik $x_i$ antara $t_{i-1}$ dan $t_i$. Pada bagian yang diarsir, antara bagian pada $t_{i-1}$ dan $t_i$, kepadatan sangat dekat dengan $\rho(x_i)$. 

![](Pasted%20image%2020250622210843.png)


Jadi berat bagian pelat logam ini dekat dengan:

$$
D \cdot H \cdot (t_i - t_{i-1}) \cdot \rho(x_i),
$$

yang kita bisa tulis sebagai:

$$
D \cdot H \cdot \rho(x_i) \Delta x_i, \quad \Delta x_i = t_i - t_{i-1}.
$$

Ini berarti berat seluruh pelat dekat dengan:

$$
D \cdot H \cdot \sum_{i=1}^n \rho(x_i) \Delta x_i,
$$

melibatkan jumlah dalam bentuk (`*`) untuk fungsi $\rho$ pada interval dari 0 ke $W$. Dengan demikian, berat seluruh pelat pastilah

$$
\text{ berat } = D \cdot H \cdot \int_0^W \rho(x) dx.
$$

Tidak perlu membatasi perhatian kita pada pelat persegi panjang. Kita bisa mengasumsikan bahwa "profil" pelat kita adalah grafik fungsi apa pun $f$ dari $a$ ke $b$, seperti yang ditunjukkan di sebelah kiri gambar di bawah ini. 

![](Pasted%20image%2020250622211054.png)

Dalam kasus ini, kepadatan di seluruh bagian yang diarsir di sebelah kanan sangat dekat dengan $\rho(x_i)$, sementara tinggi bagian ini dekat dengan $f(x_i)$. Jadi berat bagian yang diarsir dekat dengan:

$$
D \cdot f(x_i) \cdot (t_i - t_{i-1}) \cdot \rho(x_i) = D \cdot \rho(x_i) f(x_i) \Delta x_i.
$$

Ini berarti berat seluruh pelat dekat dengan:

$$
D \cdot \sum_{i=1}^n \rho(x_i) f(x_i) \Delta x_i,
$$

dan akibatnya kita pastilah memperoleh

$$
\text{ berat } = D \cdot \int_a^b \rho(x) f(x) dx.
$$

Secara umum, integral akan terlibat kapan pun kita harus menentukan kuantitas fisik apa pun berdasarkan "kepadatan" di seluruh tubuh. Ini hampir tidak mengejutkan, karena, secara kasar, integrasi berarti menjumlahkan jumlah yang sangat besar dari elemen sangat kecil, di dalam mana kita bisa berpura-pura bahwa semuanya konstan.

Ada juga sejumlah konsep murni matematis yang nilai-nilainya dapat diekspresikan dalam hal integral. Beberapa kursus kalkulus mungkin mengabdikan cukup banyak waktu untuk rumus-rumus ini, karena mereka menyediakan lebih banyak peluang untuk mengasah keterampilan mengevaluasi integral. Kursus lain, dengan penekanan berbeda, mungkin hanya menyebutkannya sekilas. Setia dengan semangat perjalanan ini, kita tidak akan khawatir tentang perhitungan, tetapi hanya menyajikan rumus-rumus itu sendiri, sebagai suvenir akhir.

1. **Volume benda putar.** Pada gambar di bawah ini, kita telah mengambil grafik fungsi $f$, antara $a$ dan $b$, dan memutarnya mengelilingi sumbu $x$, untuk mendapatkan benda putar. 

![](Pasted%20image%2020250622211323.png)

Meskipun integral awalnya digunakan untuk menghitung luas, kita akan bisa menggunakannya untuk menentukan volume benda ini.

Kita mulai, seperti biasa, dengan memilih:

$$
a = t_0, t_1, \ldots, t_n = b,
$$

bersama dengan titik $x_i$ antara $t_{i-1}$ dan $t_i$, untuk setiap $i$. Gambar di sebelah kiri menunjukkan bagian benda kita antara bidang $x = t_{i-1}$ dan $x = t_i$. Dalam gambar di sebelah kanan kita telah mendekati bagian ini dengan silinder antara kedua bidang yang sama, dengan jari-jari silinder hanya $f(x_i)$. 

![](Pasted%20image%2020250622211406.png)

Volume silinder ini adalah:

$$
\pi [f(x_i)]^2 \cdot (t_i - t_{i-1}) = \pi [f(x_i)]^2 \Delta x_i.
$$

Kita dengan demikian bisa mendekati benda kita dengan kumpulan silinder, yang volume totalnya adalah:

$$
\pi \cdot \sum_{i=1}^n [f(x_i)]^2 \Delta x_i.
$$

Jadi volume benda putar kita harus angka yang jumlah ini mendekati ketika semua $\Delta x_i$ sangat kecil, yaitu:

$$
\text{ Volume } = \pi \int_a^b [f(x)]^2 dx.
$$

Dalam contoh ini kita mendapatkan jumlah dalam bentuk (`*`) di halaman 113 dengan sedikit kerja, tetapi dari sekarang ke depan hal-hal tidak akan begitu sederhana!

2. **Permainan kulit (The shell game).** Pada gambar berikut, area di bawah grafik fungsi $f$ dari $a$ ke $b$ telah diarsir. Jika area yang diarsir ini diputar mengelilingi sumbu $y$, bukan sumbu $x$, kita mendapatkan benda yang lebih rumit: benda ini diperoleh dengan memulai dengan silinder berjari-jari $b$ dan kemudian menghapus (mengeluarkan) bagian padat yang bertitik (yang berarsir titik-titik).

![](Pasted%20image%2020250622211544.png)

Mungkin tampak bahwa seharusnya mudah menghitung volume benda erarsir titik-titik itu. Lagipula, jika kita menukar nama sumbu $x$ dan $y$, maka benda ini hanyalah salah satu jenis yang dipertimbangkan sebelumnya, kecuali bahwa alih-alih fungsi $f$ kita harus mempertimbangkan fungsi $g$ yang grafiknya adalah grafik $f$ diputar 90°. Tetapi kita mungkin tidak bisa mengetahui rumus untuk fungsi $g$ ini, dan bahkan jika bisa, integral yang dihasilkan mungkin jauh lebih sulit dihitung. Selain itu, kita mungkin memiliki situasi seperti yang ditunjukkan di bawah ini (hanya setengah belakang benda rotasi penuh yang ditunjukkan).

![](Pasted%20image%2020250622211616.png)

Jika kita mencoba hanya menukar sumbu $x$ dan $y$ di sini, kita harus berhadapan dengan kurva yang bukan grafik fungsi, sehingga kita harus membagi wilayah menjadi dua atau lebih potongan. Metode "cangkang" dirancang untuk mengatasi masalah ini.

Gambar di sebelah kiri menunjukkan (setengah belakang) bagian benda kita, cincin atau "kulit/cangkang" yang kita dapatkan ketika kita memutar bagian grafik dari $t_{i-1}$ ke $t_i$. Dalam gambar di sebelah kanan kita telah mendekati cangkang ini dengan cangkang silinder yang tingginya hanya $f(x_i)$. 

![](Pasted%20image%2020250622211645.png)

Volume cangkang silinder ini adalah:

$$
\begin{aligned}
\pi \cdot f(x_i) \cdot [(t_i)^2 - (t_{i-1})^2] & = \pi \cdot f(x_i) (t_i + t_{i-1}) (t_i - t_{i-1}) \\
& = \pi \cdot f(x_i) (t_i + t_{i-1}) \Delta x_i.
\end{aligned}
$$

Kita dengan demikian bisa mendekati benda kita dengan kumpulan cangkang silinder, yang volume totalnya adalah:

$$
\pi \cdot \sum_{i=1}^n f(x_i) (t_i + t_{i-1}) \Delta x_i.
$$

Sekarang jumlah ini tidak dalam bentuk (`*`) untuk fungsi baru $g$, jadi kita akan harus bekerja sedikit lebih keras. Hal pertama yang mungkin kita perhatikan adalah jumlah kita akan terlihat jauh lebih baik jika kita menulisnya sebagai dua jumlah,

$$
\pi \cdot \sum_{i=1}^n f(x_i) t_i \Delta x_i + \pi \cdot \sum_{i=1}^n f(x_i) t_{i-1} \Delta x_i.
$$

Jika kita memilih:

$$
x_i = t_i \quad \text{ untuk setiap } i,
$$

maka jumlah pertama akan dalam bentuk yang diinginkan (`*`), untuk fungsi $g(x) = x f(x)$. Demikian pula, jika kita memilih semua $x_i = t_{i-1}$, maka jumlah kedua akan dalam bentuk ini. Sayangnya, kita tidak bisa memilih $x_i$ untuk keduanya!

Tetapi karena kita hanya tertarik pada apa yang terjadi ketika semua $\Delta x_i$ kecil, yaitu, ketika setiap $t_{i-1}$ sangat dekat dengan $t_i$ yang sesuai, Anda mungkin berharap ini seharusnya tidak terlalu masalah, sehingga kita seharusnya memiliki rumus:

$$
\text{ Volume } = 2\pi \int_a^b x f(x) dx.
$$

Rumus ini memang benar, meskipun beberapa detail yang tidak menyenangkan harus ditangani untuk membuktikannya dengan ketat.

3. **Panjang.** Pada gambar berikut kita telah menggunakan titik-titik $a = t_0, t_1, \ldots, t_n = b$ untuk menghasilkan garis poligonal, terdiri dari segmen garis lurus:

$$
L_i \text{ dari } (t_{i-1}, f(t_{i-1})) \text{ ke } (t_i, f(t_i)).
$$

Panjang grafik $f$ dari $(a, f(a))$ ke $(b, f(b))$ harus angka yang panjang garis poligonal seperti itu mendekati ketika kita membuat semua $\Delta x_i$ kecil.

![](Pasted%20image%2020250622211824.png)

Anda mungkin berpikir panjang seharusnya lebih mudah dihitung daripada luas, tetapi sebenarnya melibatkan rumus yang jauh lebih rumit, karena bahkan rumus untuk panjang segmen $L_i$ lebih rumit:

$$
\begin{aligned}
\text{ panjang } L_i & = \sqrt{(t_i - t_{i-1})^2 + [f(t_i) - f(t_{i-1})]^2} \\
& = \sqrt{1 + \left[\frac{f(t_i) - f(t_{i-1})}{t_i - t_{i-1}}\right]^2} \cdot (t_i - t_{i-1}).
\end{aligned}
$$

Untuk melakukan apa pun dengan ekspresi ini kita perlu menggunakan Teorema Nilai Rata-rata (ya!, Teorema Nilai Rata-rata di halaman 84, dari Bab 11, yang Anda pikir hanya untuk pecinta matematika teoretis). Ini memungkinkan kita menulis:

$$
\sqrt{1 + \left[\frac{f(t_i) - f(t_{i-1})}{t_i - t_{i-1}}\right]^2} = \sqrt{1 + [f^{\prime}(x_i)]^2} \quad \begin{aligned}
& \text{ untuk beberapa } x_i \text{ dengan } \\
& t_{i-1} < x_i < t_i.
\end{aligned}
$$

Akibatnya, seluruh kurva poligonal memiliki panjang:

$$
\sum_{i=1}^n \sqrt{1 + [f^{\prime}(x_i)]^2} (t_i - t_{i-1}) = \sum_{i=1}^n \sqrt{1 + [f^{\prime}(x_i)]^2} \Delta x_i,
$$

yang merupakan jumlah dalam bentuk (`*`). Dengan demikian, panjang grafik melengkung harus diberikan oleh:

$$
\text{ Panjang } = \int_a^b \sqrt{1 + [f^{\prime}(x)]^2} dx.
$$

4. **Permukaan benda putar.** Contoh terakhir kita menggabungkan kesulitan dari 2. dan 3. dan beberapa persiapan tambahan juga diperlukan!

Gambar di sebelah kiri menunjukkan permukaan piramida yang terdiri dari (sepuluh) segitiga sama kaki kongruen; daerah yang diarsir, yang berada di antara dua bidang sejajar, terdiri dari jajaran perangkap (trapesium) kongruen, salah satunya ditunjukkan dalam gambar di sebelah kanan. 

![](Pasted%20image%2020250622212038.png)

Jika trapesium ini memiliki tinggi $h$ dan alas $l_1$ dan $l_2$, maka luasnya adalah $h (l_1 + l_2) / 2$. Jadi luas wilayah yang diarsir bisa ditulis sebagai:

$$
\text{(*)} \quad \text{ luas } = \frac{h (p_1 + p_2)}{2},
$$

di mana $p_1$ adalah keliling bagian atas wilayah dan $p_2$ adalah keliling bagian bawah.

Piramida jenis ini dengan sangat banyak sisi akan mendekati kerucut, dengan luas yang diarsir mendekati yang ditunjukkan di bawah ini. 

![](Pasted%20image%2020250622212143.png)

Jika lingkaran atas wilayah ini memiliki jari-jari $r_1$ dan lingkaran bawah memiliki jari-jari $r_2$, sementara $s$ adalah "tinggi miring" wilayah ini, maka (*) menunjukkan bahwa luas harus diberikan oleh:

$$
\text{ luas } = \frac{s (2\pi r_1 + 2\pi r_2)}{2} = \pi s (r_1 + r_2).
$$

Permukaan volume sekarang bisa didekati oleh potongan kerucut seperti ini. 

![](Pasted%20image%2020250622212214.png)

Untuk potongan dari $t_{i-1}$ ke $t_i$, jari-jarinya adalah $f(t_{i-1})$ dan $f(t_i)$ dan luasnya adalah:

$$
\pi [f(t_{i-1}) + f(t_i)] \cdot s = \pi [f(t_{i-1}) + f(t_i)] \sqrt{(t_i - t_{i-1})^2 + [f(t_i) - f(t_{i-1})]^2}.
$$

Seperti sebelumnya, kita menggunakan Teorema Nilai Rata-rata untuk menulis total luas ini sebagai:

$$
\pi \sum_{i=1}^n [f(t_{i-1}) + f(t_i)] \sqrt{1 + [f^{\prime}(x_i)]^2} \Delta x_i,
$$

dan kemudian akhirnya kita menggunakan argumen tambahan dari 2. untuk menyimpulkan bahwa:

$$
\text{ Luas permukaan } = 2\pi \int_a^b f(x) \sqrt{1 + [f^{\prime}(x)]^2} dx.
$$

[Back](./)
