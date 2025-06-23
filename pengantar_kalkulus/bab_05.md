[Home](../)

[Back](./)


## Bab 5. Beralih ke perhitungan

Sekarang kita ingin mulai menghitung kemiringan $m$ dari garis lurus yang kita peroleh ketika kita memperbesar grafik dari $f(x)=x^2$ di dekat titik $P=(1,1)$, salah satu masalah besar kita adalah bahwa grafik yang diperbesar ini sebenarnya sama sekali bukan garis lurus.

![](attachment/Pasted%20image%2020250622094512.png)

Pertama, kita akan membentuk sebuah garis lurus yang nyata, hanya dengan memilih titik lain $Q$ pada grafik, dan menggambar garis lurus antara $P$ dan $Q$. Tentu saja, Anda tidak dapat melihat dua garis yang berbeda dalam gambar kita, karena kurva asli sangat dekat dengan garis lurus baru melalui $P$ dan $Q$, jadi Anda hanya perlu mengingat bahwa mereka sebenarnya berbeda.

![](attachment/Pasted%20image%2020250622094557.png)

Perhatikan bahwa kita mendeskripsikan koordinat $Q$ sebagai $\left(1+h,(1+h)^2\right)$. Kita melakukan ini sebagai pengingat bahwa koordinat $x$ dari titik baru kita dekat dengan koordinat $x$ dari titik pertama: Ingat bahwa gambar kita menunjukkan bagian yang sangat diperbesar dari bagian yang sangat kecil dari grafik $f(x)=x^2$; akibatnya, titik $Q$ sangat dekat dengan $P$, yang berarti bahwa $h$ sangat kecil. (Huruf $h$ tidak dimaksudkan untuk mewakili sesuatu secara khusus, ini hanya huruf yang nyaman yang tidak terlalu sering digunakan untuk hal lain.)

Sekarang kita memiliki garis lurus yang spesifik, yaitu garis melalui $P=(1,1)$ dan $Q=\left(1+h,(1+h)^2\right)$, mudah untuk menuliskan kemiringan garis lurus ini:

$$
\text{(1) }m=\frac{(1+h)^2-1}{(1+h)-1}=\frac{(1+h)^2-1}{h}.
$$

Ini dapat disederhanakan lebih lanjut, menjadi:

$$
\text{(2) }m=\frac{1+2h+h^2-1}{h}=\frac{2h+h^2}{h}=2+h.
$$

Jawaban ini tidak langsung memberikan angka $m$ yang kita cari. Bahkan, ini tidak memberikan angka spesifik sama sekali—itu tergantung pada $h$, yang tidak mengherankan, karena itu tergantung pada pilihan kita untuk titik $Q$. Tetapi ketika kita mempertimbangkan pembesaran yang semakin besar, kita harus memilih $Q$ semakin dekat dengan $P$, dan dengan demikian memilih $h$ semakin dekat ke 0, sehingga kemiringan, $2+h$, dari garis-garis lurus ini akan semakin mendekati 2. Akibatnya, meskipun kurva yang diperbesar tidak pernah benar-benar menjadi garis lurus, itu menjadi semakin dekat dengan garis lurus melalui $P=(1,1)$ yang memiliki kemiringan $m=2$.

Pada bab sebelumnya, kita berbicara tentang garis lurus yang "hampir menjadi" grafik dari fungsi $f(x)=x^2$ ketika kita melihat bagian yang diperbesar di dekat titik $P=(1,1)$. Perhitungan sederhana kita sekarang telah membuat frasa yang memalukan itu jauh lebih jelas: Jika kita melihat garis-garis lurus aktual dari $P$ ke titik-titik terdekat, maka garis-garis ini semakin mendekati (yaitu, kemiringannya semakin mendekati kemiringan) garis melalui $P$ dengan kemiringan sama dengan 2.

Seperti yang kita tunjukkan di akhir bab sebelumnya, kemiringan ini biasanya dilambangkan dengan $f^{\prime}(1)$, sehingga kita dapat merangkum perhitungan kita dalam persamaan singkat:

$$
f^{\prime}(1)=2.
$$

(Ingat bahwa dalam notasi $f^{\prime}(1)$, angka 1 adalah koordinat pertama dari titik yang kita minati, koordinat kedua adalah $f(1)$; untuk $f(x)=x^2$, dengan $f(1)=1$, kita sedang melihat titik $(1,1)$.)

Fakta bahwa kemiringan dalam persamaan (1) semakin mendekati 2 saat kita membuat $h$ semakin mendekati 0 biasanya ditulis:

$$
\text{(3) }\lim_{h \rightarrow 0} \frac{(1+h)^2-1}{h}=2,
$$

dan secara umum, $\lim_{h \rightarrow 0} g(h)$ menunjukkan angka yang didekati oleh $g(h)$ saat kita memilih $h$ semakin mendekati 0. Jadi persamaan:

$$
\lim_{h \rightarrow 0} g(h)=A,
$$

yang dibaca "limit dari $g(h)$ saat $h$ mendekati 0 sama dengan $A$," hanya berarti bahwa $g(h)$ semakin mendekati $A$ saat kita memilih $h$ semakin mendekati 0. Untuk merangkum, kita mendefinisikan $f^{\prime}(1)$ sebagai:

$$
f^{\prime}(1)=\lim_{h \rightarrow 0} \frac{(1+h)^2-1}{h},
$$

dan kita telah menghitung bahwa limit ini bernilai 2.

Jika kita sebaliknya melihat titik $P=(2,4)$ pada grafik $f(x)=x^2$ dan memilih titik $Q$ yang dekat dengan $P$, dalam bentuk $\left(2+h,(2+h)^2\right)$ untuk $h$ kecil, 

![](attachment/Pasted%20image%2020250622094826.png)

maka kemiringan garis lurus melalui $P$ dan $Q$ adalah:

$$
\text{(4) }m=\frac{(2+h)^2-2^2}{(2+h)-2}=\frac{\left(4+4h+h^2\right)-4}{h}=\frac{4h+h^2}{h}=4+h.
$$

Saat kita memilih $h$ semakin mendekati 0 (atau setara, saat kita memilih $Q$ semakin mendekati $P$), kemiringan ini mendekati 4, dalam simbol:

$$
\text{(5) }\lim_{h \rightarrow 0} \frac{(2+h)^2-2^2}{h}=4,
$$

yang berarti bahwa kurva yang diperbesar menjadi semakin dekat dengan garis lurus melalui $(2,4)$ dengan kemiringan 4. Jadi:

$$
f^{\prime}(2)=4.
$$

Perlu ditekankan bahwa persamaan seperti (5) hanya berarti bahwa:

$$
\frac{(2+h)^2-2^2}{h}
$$

dekat dengan 4 ketika $h$ dekat dengan 0; itu tidak mengatakan apa-apa tentang nilai ekspresi ini ketika $h=0$. Bahkan, untuk $h=0$ kita mendapatkan ekspresi yang tidak bermakna $0/0$. Satu-satunya alasan kita dapat memprediksi perilaku ekspresi ini ketika $h$ dekat dengan 0 adalah karena kita dapat menulis ulang dalam bentuk:

$$
\frac{(2+h)^2-2^2}{h}=4+h.
$$

Pada Bab 9 kita akan melihat contoh di mana trik aljabar sederhana seperti ini tidak berhasil, sehingga diperlukan lebih banyak pekerjaan.

Ngomong-ngomong, perhatikan bahwa huruf $h$ (yang kita pilih secara agak sembarangan) tidak memiliki makna khusus dalam persamaan seperti (5), dan huruf lain apa pun juga bisa digunakan. Sama seperti huruf $x$ dalam definisi "$f(x)=x^2$," huruf $h$ dalam (5) hanyalah "penampung nilai," dan persamaan (5) bisa saja ditulis sebagai:

$$
\lim_{u \rightarrow 0} \frac{(2+u)^2-2^2}{u}=4,
$$

atau sesuatu yang serupa.

Setelah perhitungan awal ini, kita mungkin juga bertanya apa yang terjadi pada titik sembarang pada grafik $f(x)=x^2$, yang bisa kita sebut $P=\left(a, a^2\right)$. Sekali lagi kita mengambil titik $Q=\left(a+h,(a+h)^2\right)$ yang dekat dengan $P$ dan menghitung bahwa kemiringan garis lurus melalui $P$ dan $Q$ adalah:

$$
\text{(6) }\frac{(a+h)^2-a^2}{(a+h)-a}=\frac{a^2+2ah+h^2-a^2}{h}=\frac{2ah+h^2}{h}=2a+h.
$$

Karena kita jelas memiliki:

$$
\lim_{h \rightarrow 0} 2a+h=2a,
$$

ini berarti bahwa garis lurus yang kita cari, melalui $P=\left(a, a^2\right)$, memiliki kemiringan $2a$. Jadi kita memiliki rumus umum:

$$
f^{\prime}(a)=2a.
$$

Ngomong-ngomong, kita juga bisa menulis ini sebagai:

$$
f^{\prime}(x)=2x
$$

kita hanya menggunakan $a$ untuk menekankan bahwa kita sedang melihat titik tetap $\left(a, a^2\right)$ pada grafik $f(x)=x^2$. Merangkum:

$$
\text{Jika } f(x)=x^2, \text{ maka } f^{\prime}(x)=2x.
$$

Ingat sekali lagi, bahwa kita mendefinisikan:

$$
f^{\prime}(x)=\lim_{h \rightarrow 0} \frac{f(x+h)-f(x)}{h},
$$

dan kita telah menghitung bahwa $f^{\prime}(x)=2x$. Poin ini bahkan lebih penting daripada semua pekerjaan yang terlibat dalam "diferensiasi" ini, seperti yang biasa disebut perhitungan turunan. Konsep limitlah yang memungkinkan kita untuk mengatasi fakta bahwa tidak peduli seberapa banyak kita memperbesar grafik, itu tidak benar-benar menjadi garis lurus: alih-alih khawatir tentang itu, kita hanya menghitung kemiringan garis-garis lurus melalui titik tertentu $P$ dan titik-titik terdekat $Q$ dan kemudian melihat angka yang didekati oleh kemiringan ini saat kita memilih $Q$ semakin dekat dengan $P$.

Untuk mendapatkan gambaran yang sedikit lebih baik tentang jenis perhitungan apa yang mungkin diperlukan dalam diferensiasi, mari kita alihkan perhatian ke fungsi yang sedikit lebih rumit $f(x)=x^3$. 

![](attachment/Pasted%20image%2020250622095142.png)

Mari kita lagi-lagi mempertimbangkan titik $P=(1,1)$, yang juga kebetulan berada pada grafik fungsi baru $f$. 

![](attachment/Pasted%20image%2020250622095302.png)

Mengambil titik $Q=\left(1+h,(1+h)^3\right)$ di dekat $P$, kita menghitung bahwa kemiringan garis lurus yang melewati titik-titik $P$ dan $Q$ adalah:

$$
\begin{aligned}
\frac{(1+h)^3-1}{(1+h)-1} & =\frac{\left(1+3h+3h^2+h^3\right)-1}{h} \\
& =\frac{3h+3h^2+h^3}{h} \\
& =3+3h+h^2.
\end{aligned}
$$

Meskipun ekspresi ini sedikit lebih rumit daripada ekspresi $2+h$ yang muncul dalam (2), sama mudahnya untuk melihat apa yang terjadi ketika $h$ semakin kecil: produk $3h$ semakin mendekati 0, dan hal yang sama berlaku untuk $h^2$ (jika $h$ kecil, maka $h^2$ juga kecil, bahkan, $h^2$ biasanya lebih dekat ke 0 daripada $h$!). Jadi jumlahnya juga semakin mendekati 0, yang berarti:

$$
\lim_{h \rightarrow 0} 3+3h+h^2=3.
$$

Jadi garis lurus yang kita cari, melalui titik $P=(1,1)$, memiliki kemiringan 3. Dengan kata lain, untuk $f(x)=x^3$, kita memiliki:

$$
f^{\prime}(1)=\lim_{h \rightarrow 0} \frac{f(1+h)-f(1)}{h}=\lim_{h \rightarrow 0} 3+3h+h^2=3.
$$

Daripada memilih titik khusus lain pada grafik, kita akan segera mempertimbangkan titik umum $P=\left(a, a^3\right)$ pada grafik $f(x)=x^3$. Kita mengambil titik terdekat $Q=\left(a+h,(a+h)^3\right)$, dan menghitung bahwa kemiringan garis lurus melalui $P$ dan $Q$ adalah:

$$
\begin{aligned}
\frac{(a+h)^3-a^3}{(a+h)-a} & =\frac{a^3+3a^2h+3ah^2+h^3-a^3}{h} \\
& =\frac{3a^2h+3ah^2+h^3}{h} \\
& =3a^2+3ah+h^2.
\end{aligned}
$$

Jadi untuk $f(x)=x^3$ kita memiliki:

$$
\begin{aligned}
f^{\prime}(a) & =\lim_{h \rightarrow 0} \frac{(a+h)^3-a^3}{(a+h)-a} \\
& =\lim_{h \rightarrow 0} 3a^2+3ah+h^2 \\
& =3a^2.
\end{aligned}
$$

Sekali lagi, kita juga bisa menulis ini sebagai $f^{\prime}(x)=3x^2$, sehingga kita memiliki hasil:

$$
\text{Jika } f(x)=x^3, \text{ maka } f^{\prime}(x)=3x^2.
$$

Kita harus menyebutkan bahwa notasi $f^{\prime}(x)$ digunakan secara bergantian dengan notasi lama untuk turunan:

$$
f^{\prime}(x)=\frac{df(x)}{dx}
$$

(dibaca "turunan dari $f(x)$ terhadap $x$"), atau bahkan:

$$
f^{\prime}(x)=\frac{d}{dx} f(x).
$$

Seharusnya cukup jelas bahwa dalam notasi seperti itu simbol $d$ tidak mewakili angka (yang bisa saja dibatalkan di pembilang dan penyebut)—ini benar-benar simbol "diferensiasi" secara keseluruhan:

$$
\frac{d}{dx}
$$

yang memiliki makna, yaitu "ambil turunan dari."

Alasan untuk notasi yang aneh ini adalah bahwa dalam definisi:

$$
f^{\prime}(x)=\lim_{h \rightarrow 0} \frac{f(x+h)-f(x)}{h}
$$

simbol:

$$
h \text{ kadang-kadang digantikan oleh } \Delta x,
$$

menggunakan huruf Yunani Delta untuk "Perbedaan dalam $x$" (yaitu, perbedaan antara koordinat $x$ dari titik tetap kita $P$ dan titik lain kita $Q$), dan dengan cara yang sama kita dapat menulis:

$$
f(x+h)-f(x)=\Delta f,
$$

di mana $\Delta f$ sekarang mewakili perbedaan nilai $f$ di $P$ dan $Q$. Dengan singkatan ini, kita kemudian dapat menulis:

$$
f^{\prime}(x)=\lim_{\Delta x \rightarrow 0} \frac{\Delta f}{\Delta x}.
$$

Notasi $\frac{d}{dx}$ dimaksudkan sebagai semacam singkatan simbolis untuk limit ini: mengganti $\Delta$ dengan $d$ dimaksudkan untuk menunjukkan bahwa kita mengambil limit saat $\Delta \rightarrow 0$.

Meskipun notasi "$d$-notasi" ini mungkin tampak jauh lebih rumit daripada $f^{\prime}$, dalam banyak kasus ini sebenarnya jauh lebih singkat. Misalnya,

$$
\begin{aligned}
& \frac{dx^2}{dx} \text{ berarti: } f^{\prime}(x), \text{ ketika } f(x)=x^2 \\
& \frac{dx^3}{dx} \text{ berarti: } f^{\prime}(x), \text{ ketika } f(x)=x^3 \\
& \text{dll.,}
\end{aligned}
$$

sehingga seseorang dapat menulis:

$$
\begin{aligned}
& \frac{dx^2}{dx}=2x, \\
& \frac{dx^3}{dx}=3x^2,
\end{aligned}
$$

tanpa pernah harus menamai fungsi. Alasan untuk ekonomi notasi ini jelas karena fakta bahwa notasi $\frac{d}{dx}$ menggunakan $x$ sebagai "penampung nilai" dengan cara yang sama seperti $x$ berfungsi sebagai "penampung nilai" ketika kita mendefinisikan $f$ dengan mengatakan "$f(x)=x^2$." Jadi seseorang juga bisa menulis:

$$
\begin{aligned}
& \frac{dt^2}{dt}=2t, \\
& \frac{dt^3}{dt}=3t^2,
\end{aligned}
$$

dan persamaan ini akan berarti persis sama dengan yang sebelumnya.

Satu tempat di mana notasi $\frac{df(x)}{dx}$ menjadi lebih rumit adalah ketika kita perlu menunjukkan turunan pada titik tertentu, seperti $a$. Dalam kasus ini kita menggunakan sesuatu seperti:

$$
\left.\frac{df(x)}{dx}\right|_{x=a},
$$

yang menunjukkan bahwa kita pertama-tama menemukan $f^{\prime}(x)$, sebagai rumus yang melibatkan $x$, dan kemudian mengatur $x=a$ dalam rumus ini untuk mendapatkan $f^{\prime}(a)$.

Sebagai ilustrasi terakhir dari diferensiasi, kita akan mempertimbangkan:

$$
f(x)=\frac{1}{x}
$$

(yang hanya didefinisikan untuk $x \neq 0$). Sekarang kita memiliki:

$$
\begin{aligned}
f^{\prime}(x) & =\lim_{h \rightarrow 0} \frac{f(x+h)-f(x)}{h} \\
& =\lim_{h \rightarrow 0} \frac{\frac{1}{x+h}-\frac{1}{x}}{h} \\
& =\lim_{h \rightarrow 0} \frac{\frac{x-(x+h)}{x(x+h)}}{h} \\
& =\lim_{h \rightarrow 0} \frac{-h}{x(x+h)h} \\
& =\lim_{h \rightarrow 0} \frac{-1}{x(x+h)} \\
& =\frac{-1}{x^2}.
\end{aligned}
$$

Kita dapat menulis ini sebagai:

$$
\frac{dx^{-1}}{dx}=-\frac{1}{x^2}=-1x^{-2},
$$

yang membuatnya sesuai dengan pola dengan:

$$
\begin{aligned}
& \frac{dx^2}{dx}=2x, \\
& \frac{dx^3}{dx}=3x^2.
\end{aligned}
$$

Bahkan, secara umum kita memiliki:

$$
\frac{dx^n}{dx}=nx^{n-1}.
$$

Tetapi detail perhitungan tersebut akan diserahkan kepada kursus kalkulus Anda, di mana Anda juga akan mempelajari aturan-aturan diferensiasi penting untuk fungsi-fungsi yang dibangun dari fungsi-fungsi lain.

[Back](./)
