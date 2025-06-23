[Home](../)

[Back](./)


## Bab 13. Menjembatani kesenjangan

Berbeda dengan perjalanan kita yang relatif mulus menuju turunan, pengalaman kita dengan integral telah menjadi pendakian yang cukup melelahkan di medan yang curam dan berbatu. Kita dipandu untuk memperkenalkan notasi:

$$
\int_a^b f(x) dx
$$

untuk "luas bertanda" antara sumbu $x$, grafik fungsi $f$, dan garis vertikal $x=a$ dan $x=b$, dengan wilayah di bawah sumbu $x$ dihitung sebagai negatif. Tetapi saat ini kita hanya menunjukkan bagaimana seseorang mungkin menghitung angka ini dalam kasus khusus, dan perhitungan umum tampaknya hampir tanpa harapan.

![](attachment/Pasted%20image%2020250622195949.png)

Seperti yang kita tekankan di bab sebelumnya, huruf $x$ dalam notasi ini hanyalah "tempat penampung", dan seseorang bisa sama baiknya menggunakan huruf lain, seperti:

$$
\int_a^b f(t) dt \quad \text{ atau } \quad \int_a^b f(u) du \quad \text{ dll.}
$$

Dalam bab ini, kita hampir selalu akan menggunakan huruf-huruf lain, karena kita tidak lagi hanya memperhatikan angkanya, 

$$
\int_a^b f(t) dt
$$

melainkan bentuk ekspresinya.

$$
\int_a^x f(t) dt.
$$

Perhatikan bahwa di sini kita telah menggunakan $t$ sebagai penampung nilai, sementara $x$ telah digunakan sebagai pengganti $b$; kita melakukan ini untuk menekankan bahwa kita mempertimbangkan area

![](attachment/Pasted%20image%2020250622200623.png)

$$
\int_a^x f(t) dt
$$

untuk semua angka $x$, bukan hanya untuk nilai tertentu saja. Dengan kata lain, kita sekarang siap untuk mempertimbangkan fungsi

$$
A(x) = \int_a^x f(t) dt.
$$

Perhatikan bahwa sekarang kita memiliki dua penampung nilai. Pertama, $x$ adalah penampung nilai untuk definisi $A(x)$, memberikan cara yang masuk akal untuk mengatakan

$$
A(\text{ angka }) = \int_a^{\text{angka itu}} \ldots
$$

Lebih lanjut, dalam ekspresi $\int_a^{\text{angka itu}} \ldots$ ini, huruf $t$ adalah penampung nilai lain, sehingga jika kita mempertimbangkan contoh seperti:

$$
A(x) = \int_a^x t^2 dt,
$$

maka $t^2 dt$ akan menunjukkan fungsi $f$ dengan

$$
f(\text{ angka }) = \text{ kuadrat angka itu.}
$$

Bahkan terlepas dari semua kerumitan notasi tambahan ini, memperkenalkan fungsi $A$ mungkin tampak seperti latihan sia-sia. Lagipula, mengetahui fungsi $A$ berarti mengetahui $A(x)$ untuk semua $x$, dan kita umumnya tidak bisa bahkan mengetahui nilai tertentu

$$
A(b) = \int_a^b f(t) dt,
$$

kecuali untuk nilai khusus $b = a$. Meskipun demikian—dan ini adalah trik yang matematikawan telah berhasil gunakan selama ratusan tahun—mungkin ternyata kita dapat menetapkan beberapa sifat penting dari fungsi ini tanpa dapat menghitungnya langsung.

Sekarang sifat apa dari fungsi $A$ yang mungkin kita harapkan untuk diselidiki? Nah, ini adalah buku tentang kalkulus, dan kita telah menghabiskan waktu yang sangat lama untuk turunan, jadi mungkin kita coba saja melihat turunan $A^{\prime}(x)$ dari fungsi $A$ kita!

Jika ide awal memperkenalkan fungsi $A$ tampak konyol, ide untuk mempertimbangkan turunan $A^{\prime}(x)$ dari fungsi ini mungkin tampak benar-benar absurd. Di satu sisi, kita memiliki fungsi $A$ yang mana kita mungkin tidak bisa menghitung nilai apa pun (dan fungsi $A$ ini bahkan bukan fungsi spesifik, tetapi bergantung pada fungsi $f$ yang kita pilih untuk memulai). Di sisi lain, seperti yang dibuat sangat jelas di Bab 6, menemukan turunan bisa memerlukan banyak kerja bahkan untuk fungsi tertentu, yang relatif sederhana. Berusaha mencari turunan dari fungsi yang bahkan tidak dapat kita hitung sejak awal jelas terdengar gila!

Tetapi kita tidak akan membiarkan masalah kecil seperti itu menghentikan kita, bukan? Mari kita kembali ke definisi (tidak ada yang lain yang bisa kita lakukan):

$$
A^{\prime}(x) = \lim_{h \rightarrow 0} \frac{A(x+h) - A(x)}{h}.
$$

Ingat bahwa $A$ didefinisikan oleh:

$$
A(x) = \int_a^x f(t) dt,
$$

sehingga kita juga memiliki:

$$
A(x+h) = \int_a^{x+h} f(t) dt.
$$

Jadi kita mencoba menghitung:

$$
\begin{aligned}
A^{\prime}(x) & = \lim_{h \rightarrow 0} \frac{A(x+h) - A(x)}{h} \\
& = \lim_{h \rightarrow 0} \frac{\int_a^{x+h} f(t) dt - \int_a^x f(t) dt}{h}.
\end{aligned}
$$

Dalam persamaan ini, $x$ mewakili angka tertentu, yang akan tetap selama argumen—yang akan kita ubah adalah $h$, membiarkannya semakin mendekati 0. Seperti hampir selalu terjadi, kita memiliki situasi di mana pembilang dan penyebut keduanya memiliki nilai 0 ketika $h=0$, jadi beberapa manipulasi licik akan diperlukan.

Langkah pertama, setidaknya, tidak sulit. Sifat penjumlahan (A) dari integral berarti kita bisa menulis:

$$
\int_a^{x+h} f(t) dt - \int_a^x f(t) dt = \int_x^{x+h} f(t) dt.
$$

Akibatnya,

![](attachment/Pasted%20image%2020250622201929.png)

$$
A^{\prime}(x) = \lim_{h \rightarrow 0} \frac{\int_x^{x+h} f(t) dt}{h}.
$$

Tapi sekarang, setelah kita mendapatkan bentuk simbolik yang terlihat cukup sederhana, kita harus menghadapi kenyataan dan mengingat apa maknanya sebenarnya.

![](attachment/Pasted%20image%2020250622202138.png)

Seperti biasa, nilai limit hanya tergantung pada apa yang terjadi ketika $h$ sangat kecil, jadi gambar kita seharusnya seperti ini

![](attachment/Pasted%20image%2020250622202217.png)

di mana kita mengambil luas irisan sangat kecil, dan kemudian membaginya dengan angka kecil $h$.

Seperti di Bab 6, awalnya hampir tidak jelas bagaimana kita bisa membandingkan $h$ dengan luas irisan kecil ini, terutama karena luas tergantung pada fungsi tertentu $f$ yang kita kerjakan.

Gambar di bawah ini menunjukkan irisan (agak diperluas), bersama dengan persegi panjang, memiliki tinggi $m$, terletak di bawah grafik, dan persegi panjang lain, dengan tinggi $M$, terletak di atas grafik. 

![](attachment/Pasted%20image%2020250622202347.png)

Luas persegi panjang di bawah grafik hanyalah $h \cdot m$, sementara luas persegi panjang di atas grafik hanyalah $h \cdot M$. Karena luas di bawah kurva jelas terletak di antara kedua luas ini, kita memiliki (`*`)

![](attachment/Pasted%20image%2020250622203020.png)

Ingat bahwa kita hanya tertarik pada apa yang terjadi ketika $h$ sangat kecil. Dalam kasus ini, karena $f$ kontinu di $x$, nilai minimum $m$ dan nilai maksimum $M$ dari $f$ pada interval kecil dari $x$ ke $x+h$ harus keduanya sangat dekat dengan nilai $f(x)$ yang dimiliki $f$ di ujung $x$. Jadi (`*`) menunjukkan bahwa untuk $h$ kecil, area pada gambar di bawah pastilah dekat ke $h.f(x)$.

![](attachment/Pasted%20image%2020250622202855.png)

Dalam istilah yang penuh warna, kita mungkin mengatakan bahwa untuk $h$ kecil irisan kita praktis persegi panjang dengan alas $h$ dan tinggi $f(x)!$ Tetapi untuk lebih tepat, mari kita bagi (`*`) dengan $h$ dan tulis dalam bentuk:

$$
m < \frac{\int_x^{x+h} f(t) dt}{h} < M.
$$

Kemudian kita lihat bahwa untuk $h$ kecil

$$
\frac{\int_x^{x+h} f(t) dt}{h} \quad \text{ harus dekat dengan } f(x).
$$

Ini berarti:

$$
A^{\prime}(x) = \lim_{h \rightarrow 0} \frac{\int_x^{x+h} f(t) dt}{h} = f(x).
$$

Jadi, meskipun kita mungkin tidak bisa menghitung $A(x)$, turunan $A^{\prime}(x)$ mudah dihitung—itu hanya nilai fungsi asli $f$ di $x$!

Dalam gambar, kita selalu mengasumsikan bahwa grafik $f$ terletak di atas sumbu $x$. Ketika $f$ terletak di bawah sumbu $x$, argumen yang pada dasarnya sama bekerja, mengingat bahwa dalam kasus ini semua area kita harus diambil sebagai negatif. Ketika detail kecil seperti ini diperhatikan, argumen kita—ditulis dengan sedikit lebih hati-hati—menetapkan:

**TEOREMA DASAR KALKULUS:**
Jika $f$ kontinu dan fungsi $A$ didefinisikan oleh:

$$
A(x) = \int_a^x f(t) dt,
$$

maka untuk semua $x$ kita memiliki:

$$
A^{\prime}(x) = f(x).
$$

Di era modern ini, ketika segala sesuatu dan semua orang dipuji sebagai yang terhebat, terbaik, dan paling terkenal (setidaknya selama 15 menit), Anda mungkin mengira bahwa nama yang melekat pada teorem ini hanyalah bagian dari hype, tidak dimaksudkan untuk diambil terlalu serius. Atau mungkin teorem ini benar-benar begitu mendasar?

Salah satu argumen bahwa teorem kita layak mendapat nama yang terhormat ini hanyalah fakta bahwa itu membangun koneksi antara dua konsep yang sangat berbeda dari integral dan turunan. Tetapi sekali lagi, argumen itu mungkin tidak terlalu meyakinkan ketika kita ingat bahwa integral ditemukan hanya sebagai penyimpangan dari rute utama kita.

Faktanya, ada alasan yang jauh lebih baik untuk memberikan teorem ini status yang sangat terhormat. Hingga saat ini integral hanyalah konsep, yang telah kita kaitkan dengan beberapa notasi yang menarik, tetapi yang kita belum bisa hitung dengan cara yang wajar. Tetapi, seperti yang akan segera kita lihat, dengan munculnya Teorema Dasar Kalkulus, ini menjadi permainan yang sama sekali baru.

Mari kita kembali ke luas:

$$
\int_a^b t^2 dt
$$

yang memulai diskusi kita tentang integral. Perhitungan integral ini adalah tugas besar. Kita tidak hanya harus mengerjakan rumus $\left(S_n\right)$ di bab 12, tetapi kita juga mengandalkan rumus khusus untuk jumlah $1^2 + 2^2 + 3^2 + \cdots + n^2$. Sekarang kita akan menggunakan Teorema Dasar untuk mengevaluasi integral ini dengan hampir tanpa perhitungan sama sekali!

Sesuai dengan strategi bab ini, kita cukup memperkenalkan fungsi:

$$
A(x) = \int_a^x t^2 dt,
$$

yang mana Teorema Dasar Kalkulus memberi tahu kita bahwa:

$$
A^{\prime}(x) = x^2.
$$

Sekarang hal menarik tentang persamaan kecil ini adalah kita juga bisa menamakan fungsi lain, cukup eksplisit, dengan turunan yang sama:

$$
\text{ Jika } F(x) = \frac{x^3}{3}, \text{ maka } F^{\prime}(x) = x^2.
$$

Jadi $A$, fungsi yang didefinisikan dalam hal luas, tanpa rumus eksplisit, memiliki turunan yang persis sama dengan fungsi $F$ dengan rumus sangat sederhana $F(x) = x^3 / 3$.

Fakta bahwa fungsi misterius kita $A$ dan fungsi eksplisit sederhana kita $F$ keduanya memiliki turunan yang sama tidak selalu berarti bahwa $A$ dan $F$ sama. Tetapi, seperti yang kita tunjukkan di bagian awal bab 11, itu berarti bahwa $A$ dan $F$ hanya berbeda oleh konstanta: ada angka $C$ sehingga:

$$
A(x) = F(x) + C \quad \text{ untuk semua } x;
$$

dengan kata lain,

$$
\text{(1)} \quad \int_a^x t^2 dt = \frac{x^3}{3} + C \quad \text{ untuk semua } x.
$$

Kita bisa dengan mudah mengetahui apa yang harus menjadi $C$ dengan memilih $x = a$ dalam (1): kita dapatkan

$$
0 = \int_a^a t^2 dt = \frac{a^3}{3} + C,
$$

sehingga kita harus memiliki

$$
C = -\frac{a^3}{3}.
$$

Akhirnya, memasukkan nilai $C$ ini kembali ke (1) kita peroleh:

$$
\int_a^x t^2 dt = \frac{x^3}{3} - \frac{a^3}{3}.
$$

Sekarang setelah kita mengerjakan rumus ini, kita mungkin juga memilih nilai spesifik $x = b$ sehingga kita bisa menulis:

$$
\int_a^b t^2 dt = \frac{b^3}{3} - \frac{a^3}{3}.
$$

Dengan demikian, kita telah mengetahui luas ini dengan hampir tanpa perhitungan sama sekali; kita hanya harus tahu turunan dari $F(x) = x^3$.

Ngomong-ngomong, perhatikan bahwa rumus kita memberi kita luas di bawah grafik $f(x) = x^2$ bahkan untuk $a < 0 < b$: dalam kasus ini, $a^3$ adalah negatif, jadi istilah $-a^3 / 3$ sebenarnya menambahkan jumlah positif lainnya.

![](attachment/Pasted%20image%2020250622204253.png)

Seperti yang mungkin Anda bayangkan, sekarang ada banyak integral lain yang bisa kita berikan rumus spesifik. Misalnya, kita bisa dengan mudah menghitung

$$
\int_a^b x^3 dx
$$

menggunakan fakta bahwa fungsi $F(x) = \frac{x^4}{4}$ memiliki turunan $F^{\prime}(x) = x^3$.

Karena jika kita mendefinisikan

$$
A(x) = \int_a^x t^3 dt
$$

maka:

$$
A^{\prime}(x) = x^3 = F^{\prime}(x),
$$

jadi ada angka $C$ sehingga:

$$
A(x) = F(x) + C,
$$

yaitu,

$$
\int_a^x t^3 dt = \frac{x^4}{4} + C.
$$

Memilih $x = a$ kemudian memberikan $C = -a^4 / 4$, sehingga, akhirnya,

$$
\int_a^b t^3 dt = \frac{b^4}{4} - \frac{a^4}{4}.
$$

Perhatikan bahwa dalam kasus ini kita harus sedikit lebih berhati-hati tentang tanda $a$ dan/atau $b$. Jika $a < 0 < b$, maka istilah $-a^4 / 4$ negatif, dan mewakili jumlah luas di bawah sumbu, yang kita kurangi.

![](attachment/Pasted%20image%2020250622204455.png)

Di sisi lain, jika $a < b < 0$, maka $a^4 > b^4$, jadi:

$$
\frac{b^4}{4} - \frac{a^4}{4} < 0
$$

angka ini adalah area negatif di bawah grafik $f(x) = x^3$ antara $a$ dan $b$.

![](attachment/Pasted%20image%2020250622204616.png)

Metode yang berhasil dalam dua contoh ini bisa digunakan secara umum: Misalkan kita memiliki fungsi $F$ sehingga:

$$
F^{\prime}(x) = f(x). \quad \text{(HIPOTESIS)}
$$

Kemudian jika kita mendefinisikan:

$$
A(x) = \int_a^x f(t) dt,
$$

Teorema Dasar memberi tahu kita bahwa:

$$
A^{\prime}(x) = f(x).
$$

Jadi $A^{\prime}(x) = F^{\prime}(x)$ untuk semua $x$, yang berarti untuk angka konstan tertentu $C$ kita memiliki:

$$
A(x) = F(x) + C,
$$

yaitu,

$$
\int_a^x f(t) dt = F(x) + C.
$$

Memilih $x = a$ dalam persamaan ini memberikan:

$$
C = -F(a),
$$

sehingga kita peroleh akhirnya:

$$
\int_a^b f(t) dt = F(b) - F(a).  \quad \text{(KESIMPULAN)}
$$

Sisi kanan persamaan ini kadang-kadang ditulis sebagai:

$$
\left. F \right|_a^b \quad \text{ atau } \quad \left. F(x) \right|_{x=a}^{x=b},
$$

sehingga kita bisa menulis:

$$
\int_a^b f(t) dt = \left. F(x) \right|_{x=a}^{x=b} \quad \text{ untuk } F^{\prime}(x) = f(x).
$$

Persamaan ini kadang-kadang disebut **Teorema Dasar Kedua Kalkulus**. Meskipun hanya merupakan akibat langsung dari Teorema Dasar, hal ini tetap layak untuk disorot secara khusus karena perannya yang sangat penting dalam menghitung integral.

Harus jelas bahwa kita sekarang dalam posisi untuk menulis berbagai macam rumus luas yang cukup spektakuler hanya dengan "membalik" rumus diferensiasi. Sebagai kasus yang sangat menarik, kita bisa bertanya tentang

![](attachment/Pasted%20image%2020250622205219.png)

$$
\int_a^b \sin t dt.
$$

Kita bisa mengevaluasi integral ini karena kita bisa dengan mudah menemukan fungsi yang turunannya adalah $\sin$: karena $\cos^{\prime}(x) = -\sin x$ (tanda minus itu penting!), kita memiliki:

$$
(-\cos)^{\prime}(x) = \sin x.
$$

Akibatnya,

$$
\begin{aligned}
\int_a^b \sin t dt & = -\left. \cos x \right|_{x=a}^{x=b} \\
& = -\cos b - (-\cos a) \\
& = \cos a - \cos b.
\end{aligned}
$$

Untuk menemukan luas di bawah satu lengkungan kurva sin, 

![](attachment/Pasted%20image%2020250622205331.png)

kita cukup memilih $a = 0$ dan $b = \pi$, untuk mendapatkan hasil mengejutkan:

$$
\begin{aligned}
\int_0^\pi \sin t dt & = \cos 0 - \cos \pi \\
& = 1 - (-1) \\
& = 2.
\end{aligned}
$$

Jika kita mempertimbangkan luas bertanda dari 0 ke $2\pi$, maka kita akan mengharapkan jawabannya 0, karena lengkungan kedua memiliki luas yang sama dengan yang pertama, kecuali bahwa itu terletak di bawah sumbu $x$, dan dengan demikian dihitung sebagai negatif. 

![](attachment/Pasted%20image%2020250622205427.png)

Dan memang kita menemukan bahwa:

$$
\begin{aligned}
\int_0^{2\pi} \sin t dt & = \cos 0 - \cos 2\pi \\
& = 1 - 1 = 0.
\end{aligned}
$$

Menemukan luas di bawah satu lengkungan fungsi cos sebenarnya tidak seharusnya memerlukan perhitungan sama sekali, karena grafik cos hanyalah grafik $\sin$ yang digeser ke kiri sebesar $\pi/2$. 

![](attachment/Pasted%20image%2020250622205453.png)

Akibatnya, area ini, yang diberikan oleh integral

$$
\int_{-\pi/2}^{\pi/2} \cos t dt
$$

seharusnya sama dengan luas di bawah lengkungan kurva sin. Namun, hanya untuk memeriksa, Anda seharusnya mengevaluasi integral ini menggunakan Teorema Dasar Kedua (perhitungannya bahkan lebih mudah, karena $\sin^{\prime} = \cos$, dan kita tidak perlu khawatir tentang tanda minus).

Seperti yang diilustrasikan oleh contoh-contoh ini, meskipun Teorema Dasar memungkinkan kita menulis berbagai rumus untuk integral, ini tidak benar-benar menyelesaikan masalah mengevaluasi integral: ketika kita diberi integral tertentu:

$$
\int_a^b f(t) dt
$$

yang ingin kita evaluasi, kita harus menebak fungsi $F$ untuk mana kita memiliki $F^{\prime}(x) = f(x)$.

Misalnya, misalkan kita ingin menemukan:

$$
\int_a^b \sin t \cos t dt
$$

Jika kita perhatikan bahwa:

$$
\begin{aligned}
\frac{d}{dx} \sin^2 x & = \frac{d}{dx} [(\sin x) \cdot (\sin x)] \\
& = \sin x \cos x + \cos x \sin x \\
& = 2 \sin x \cos x
\end{aligned}
$$

(ini memerlukan aturan untuk turunan produk fungsi), maka kita bisa menyimpulkan bahwa:

$$
\begin{aligned}
\int_a^b \sin t \cos t dt & = \left. \frac{\sin^2 x}{2} \right|_{x=a}^{x=b} \\
& = \frac{\sin^2 b}{2} - \frac{\sin^2 a}{2}.
\end{aligned}
$$

Tetapi bagaimana kita akan dipandu untuk memperhatikan ini!? Berbeda dengan kasus diferensiasi, yang hanya memerlukan penerapan metodis aturan dasar, menemukan fungsi $F$ dengan $F^{\prime} = f$ bisa menjadi seni sejati.

Seberapa banyak waktu yang dikhususkan kursus kalkulus untuk seni ini tergantung, sampai batas tertentu, pada tujuan kursus. Ada beberapa aturan penting, dan beberapa aplikasi standar dari aturan ini, yang hampir setiap kursus akan bahas. Setelah aturan standar ini dikuasai, mungkin cukup untuk berkonsultasi dengan "tabel integral" khusus yang memberikan banyak rumus seperti itu, atau seseorang dapat menggunakan program komputer khusus yang mengevaluasi integral, atau seseorang dapat memperluas repertoar aturan dan trik sehingga semakin banyak integral bisa dievaluasi "dengan tangan."

Dalam perjalanan Anda melalui kalkulus, seni integrasi mungkin ternyata menjadi kunjungan singkat di penginapan pedesaan yang menyenangkan, kerja keras yang melelahkan di kebun anggur, atau tur kilat melalui museum teknologi tinggi. Sayangnya, *The Hitchhiker's Guide* tidak bisa membantu Anda pada titik ini! Kita hanya harus menunggu sampai episode ini selesai, dan kemudian mengacungkan jempol kita sekali lagi untuk melanjutkan perjalanan.

[Back](./)
