[Home](../)\n[Back](./)\n
## Bab 8. Kecepatan

Parabola, yang sering kita gunakan sebagai contoh, muncul secara alami di Bab 3, sebagai grafik dari fungsi non-linear paling sederhana. Tetapi kita juga melihatnya sepanjang waktu dalam kehidupan sehari-hari—setidaknya jika kehidupan sehari-hari mencakup olahraga (baik melalui partisipasi aktif, atau sebagai kentang sofa). Bola bisbol, bola basket, bola sepak, bola voli, bola golf, dan hampir segala sesuatu yang dilempar atau dipukul, bergerak dalam lintasan parabola, meskipun parabola ini "terbalik".

![](Pasted%20image%2020250622101645.png)

Lintasan parabola dari proyektil ini berkaitan langsung dengan hukum fisika yang menentukan laju sesuatu jatuh di bawah gaya gravitasi. Misalnya, jika sebuah bola dilempar secara horizontal dari menara, maka (mengabaikan hambatan udara) bola tersebut mempertahankan gerakan horizontal konstan, 

![](Pasted%20image%2020250622101709.png)

sementara jarak vertikal ke bawah $s(t)$ pada waktu $t$ meningkat sesuai aturan:

$$
s(t)=16 t^2,
$$

di mana $s(t)$ diukur dalam kaki dan $t$ dalam detik. Lintasan yang dihasilkan adalah bagian dari parabola, dengan menara sebagai ketinggian maksimum.

Kita biasanya melempar bola pada sudut, sehingga bola tidak hanya memiliki kecepatan horizontal, tetapi juga kecepatan ke atas awal. Dalam kasus ini kita lagi-lagi mendapatkan lintasan parabola, tetapi dengan ketinggian maksimum yang lebih besar; bagian lintasan sebelum ketinggian maksimum ini hanyalah kebalikan dari lintasan yang akan diikuti jika bola dilepaskan dari puncak ke arah lain.

![](Pasted%20image%2020250622101732.png)

Untuk berkonsentrasi pada satu fungsi, kita akan hanya mempertimbangkan jarak vertikal ke bawah $s(t)=16 t^2$ dan mengabaikan gerakan horizontal. Jadi kita pada dasarnya mempertimbangkan bola yang dijatuhkan dari ketinggian tertentu, bukan dilempar (atau mungkin bola yang dilempar langsung ke atas).

Segera setelah kita mempertimbangkan sesuatu yang bergerak, wajar untuk bertanya tentang kecepatannya. Misalnya, saat menangkap bola, kita belajar mengantisipasi kecepatannya, karena ini cenderung mengesankan diri kita dengan cukup kuat, mungkin memerlukan penggunaan alat khusus seperti sarung tangan bisbol. Eksperimen kasar semacam ini membuat jelas bahwa kecepatan tergantung pada ketinggian dari mana bola turun; kita dengan cepat belajar, bahkan sebagai balita, bahwa kecepatan akan lebih besar ketika ketinggian itu lebih besar.
Ketika kita memiliki rumus sederhana:

$$
s(t)=16 t^2
$$

untuk jarak yang ditempuh setelah waktu $t$, kita tentu seharusnya dapat menghitung kecepatan dengan mana bola bergerak pada waktu tertentu $t_0$, dan dengan demikian memprediksi seberapa besar dampak yang diharapkan. Masalahnya adalah definisi biasa kita tentang kecepatan,

$$
\text{ kecepatan } = \frac{\text{ jarak yang ditempuh }}{\text{ waktu }},
$$

benar-benar definisi kecepatan rata-rata. Jika sesuatu bergerak dengan "kecepatan seragam" (sehingga jarak memenuhi $s(t)=c \cdot t$ untuk konstanta $c$ tertentu), maka kecepatan seragam ini adalah konsep yang berguna, tetapi menjadi jauh kurang berguna secara umum.

Misalnya, ketika kita memiliki rumus:

$$
s(t)=16 t^2
$$

kita mungkin mencoba mencari tahu dampak yang diharapkan pada waktu $t_0$ dengan menghitung kecepatan rata-rata yang akan dimiliki bola jika dibiarkan bergerak selama satu detik lagi. Dengan demikian, kita akan menggunakan (*) pada interval waktu dari $t_0$ ke $t_0+1$, dan mendapatkan:

$$
\begin{aligned}
\text{ kecepatan rata-rata } & = \frac{16(t_0+1)^2-16 t_0^2}{1} \\
& = \frac{16 t_0^2+32 t_0+1-16 t_0^2}{1} \\
& = 32 t_0 + 1.
\end{aligned}
$$

Di sisi lain, jika kita menghitung kecepatan rata-rata yang akan dimiliki bola jika dibiarkan bergerak hanya selama 0,1 detik lagi, maka kita akan mendapatkan:

$$
\begin{aligned}
\text{ kecepatan rata-rata } & = \frac{16(t_0+0,1)^2-16 t_0^2}{0,1} \\
& = \frac{16 t_0^2+3,2 t_0+0,01-16 t_0^2}{0,1} \\
& = \frac{3,2 t_0+0,01}{0,1} \\
& = 32 t_0 + 0,1.
\end{aligned}
$$

Tidak boleh terlalu mengejutkan bahwa kita mendapatkan jawaban yang lebih kecil ketika kita menghitung kecepatan rata-rata pada interval waktu yang lebih kecil, hanya 0,1 detik setelah waktu saat ini $t_0$. Karena bola jatuh semakin cepat, interval waktu yang lebih lama mencakup periode di mana bola akan bergerak lebih cepat jika kita tidak menangkapnya pada waktu $t_0$; merata-rata pada interval waktu yang lebih lama sehingga memberikan jawaban yang terlalu besar untuk menentukan gaya dengan mana bola akan mengenai pada waktu $t_0$.

Tentu saja, keberatan yang sama berlaku bahkan untuk interval waktu 0,1 detik: kita akan mendapatkan jawaban yang lebih baik dengan mempertimbangkan interval waktu yang bahkan lebih kecil, katakanlah 0,01 detik:

$$
\begin{aligned}
\text{ kecepatan rata-rata } & = \frac{16(t_0+0,01)^2-16 t_0^2}{0,01} \\
& = \frac{16 t_0^2+0,32 t_0+0,0001-16 t_0^2}{0,01} \\
& = \frac{0,32 t_0+0,0001}{0,01} \\
& = 32 t_0 + 0,01.
\end{aligned}
$$

Sekarang seharusnya jelas bahwa kita mungkin juga mempertimbangkan interval waktu kecil sewenang-wenang $h$ dan menghitung bahwa pada waktu sewenang-wenang, yang akan kita kembali sebut $t$, kecepatan rata-rata pada interval waktu dari $t$ ke $t+h$ adalah:

$$
\begin{aligned}
\text{ kecepatan rata-rata } & = \frac{16(t+h)^2-16 t^2}{h} \\
& = \frac{16 t^2+32 h t+h^2-16 t^2}{h} \\
& = \frac{32 h t+h^2}{h} \\
& = 32 t + h.
\end{aligned}
$$

Perhitungan ini seharusnya terlihat cukup akrab—ini hanya perhitungan untuk turunan dari fungsi $s(t)=16 t^2$—dan memberikan jawaban yang semakin baik untuk kecepatan pada waktu $t$ saat kita memilih $h$ semakin kecil. Ini jelas berarti bahwa "terbaik" atau "tepat" jawaban untuk kecepatan seharusnya adalah $32 t$, hasilnya ketika kita mengambil limit dari kuota-kuota ini. Dengan kata lain, jika kita mempertimbangkan sesuatu yang bergerak sepanjang garis sesuai aturan:

$$
s(t)=16 t^2,
$$

maka kita seharusnya mendefinisikan kecepatan pada waktu $t$ sebagai turunan, $32 t$.
Lebih umum, jika gerakan sepanjang garis diberikan oleh fungsi apa pun $s$, maka kita mendefinisikan "kecepatan (instan)" pada waktu $t$ sebagai:

$$
s^{\prime}(t)=\lim_{h \rightarrow 0} \frac{s(t+h)-s(t)}{h}.
$$

Perhatikan bahwa kita belum membuktikan teorem, karena hingga sekarang konsep kecepatan (berbeda dengan kecepatan rata-rata) belum didefinisikan: tetapi kita telah menunjukkan bahwa definisi ini adalah yang paling masuk akal! Dengan demikian kita melihat bahwa turunan (dan limit, yang digunakan untuk mendefinisikannya) memiliki tempat alami dalam fisika. Bahkan, turunan awalnya muncul dalam fisika untuk tujuan ini.

Perhatikan juga bahwa dengan notasi $\frac{d}{dt}$ kita akan menulis:

$$
\text{ kecepatan } = s^{\prime}(t) = \frac{ds}{dt},
$$

yang menjelaskan mengapa kita menandakan jarak yang ditempuh dengan $s$ (yang merupakan singkatan dari situs Latin = posisi) daripada dengan $d$.

Hanya ada dua klarifikasi kecil yang perlu dibuat terkait diskusi sebelumnya.

Pertama-tama, dengan definisi kita, kecepatan bisa positif atau negatif. Jika kita mengukur jarak dari permukaan bumi ke atas, sehingga objek yang jatuh memenuhi persamaan bentuk:

$$
s(t)=H-16 t^2
$$

untuk ketinggian awal tertentu $H$, maka:

$$
s^{\prime}(t)=-32 t,
$$

yang hanya menyatakan bahwa objek yang jatuh bergerak ke bawah. Kadang-kadang kecepatan didefinisikan sebagai nilai absolut $\left|s^{\prime}(t)\right|$.

Perhatikan juga bahwa definisi kita tentang kecepatan kini hanya dibuat untuk objek yang bergerak sepanjang garis lurus. Ini berlaku untuk kasus objek yang jatuh, tetapi tidak untuk objek yang dilempar, yang bergerak sepanjang kurva datar.

Pertanyaan umum tentang kecepatan untuk objek yang bergerak di bidang, atau di ruang, adalah subjek yang tepat dari kalkulus lanjutan (atau setidaknya sedikit lebih maju dari kalkulus yang kita pertimbangkan), tetapi kita setidaknya dapat menyebutkan jawabannya dalam kasus objek yang dilempar, sehingga kecepatan horizontalnya konstan $c$, sementara jarak vertikal ke bawahnya adalah $s(t)$, sehingga pada waktu $t$ objek berada di titik $(c \cdot t, s(t))$.

![](Pasted%20image%2020250622101840.png)

Dalam kasus ini, kita memiliki "kecepatan horizontal," yang diwakili oleh panah horizontal sepanjang $c$, dan "kecepatan vertikal," yang diwakili oleh panah vertikal sepanjang $s^{\prime}(t)$. Dua panah ini adalah sisi persegi panjang, dan diagonal dari persegi panjang ini memberikan panah baru. Sekarang panah ini adalah yang kita sebut kecepatan dalam kasus ini. 

![](Pasted%20image%2020250622101912.png)

Jadi kecepatan, secara ketat, adalah panah, bukan hanya angka. Namun, kita kemudian dapat mendefinisikan kecepatan sebagai panjang panah ini, yang dalam kasus ini akan menjadi:

$$
\sqrt{c^2 + [s^{\prime}(t)]^2}.
$$

### Sesuatu untuk Dikhawatirkan

1. Berapa detik yang Anda miliki untuk menghindar dari koin sen yang jatuh dari gedung setinggi 400 kaki? Jika Anda tidak berhasil, seberapa cepat koin itu akan mengenai Anda? (Semua perhitungan kita telah mengabaikan hambatan udara. Dalam beberapa kasus ini dapat membatasi kecepatan akhir secara signifikan (tidak ada yang khawatir tentang ketinggian dari mana tetesan hujan jatuh), dan bahkan koin sen pada akhirnya akan terbatas pada kecepatan terminal. Koin sen yang dijatuhkan bisa mematikan, begitu pula dengan peluru kosong yang ditembakkan ke udara dan jatuh kembali ke bawah.)
[Back](./)
