[Home](../)\n[Back](./)\n
## Bab 6. Kontinuitas

Pada bab sebelumnya, kita menemukan konsep limit, bersamaan dengan notasi:

$$
\lim_{h \rightarrow 0} g(h)=A.
$$

Ingat bahwa huruf $h$ hanyalah sebuah "penampung nilai," sehingga kita juga bisa menulis:

$$
\lim_{x \rightarrow 0} g(x)=A.
$$

Secara lebih umum, kita menulis:

$$
\lim_{x \rightarrow a} g(x)=A
$$

("limit dari $g(x)$ saat $x$ mendekati $a$ sama dengan $A$") untuk menyatakan fakta bahwa $g(x)$ semakin mendekati $A$ saat kita memilih $x$ semakin mendekati $a$.

Dalam kursus kalkulus Anda, Anda mungkin akan menemukan beberapa aturan sederhana tentang limit, seperti:

$$
\lim_{x \rightarrow a} f(x)+g(x)=\lim_{x \rightarrow a} f(x)+\lim_{x \rightarrow a} g(x),
$$

$$
\lim_{x \rightarrow a} f(x) \cdot g(x)=\lim_{x \rightarrow a} f(x) \cdot \lim_{x \rightarrow a} g(x),
$$

yang digunakan dalam membuktikan aturan-aturan untuk turunan yang disebutkan di akhir bab sebelumnya. Ada juga aturan:

$$
\lim_{x \rightarrow a} \frac{f(x)}{g(x)}=\frac{\lim_{x \rightarrow a} f(x)}{\lim_{x \rightarrow a} g(x)},
$$

yang berlaku dengan syarat bahwa $\lim_{x \rightarrow a} g(x) \neq 0$. Kondisi tambahan ini bukanlah hal kecil, karena semua limit yang kita temui dalam menghitung turunan justru berbentuk:

$$
\lim_{h \rightarrow 0} \frac{A(h)}{B(h)},
$$

di mana baik $A(0)$ maupun $B(0)$ adalah 0; sehingga kita tidak bisa hanya memasukkan nilai $h=0$, dan sebaliknya harus bergantung pada trik aljabar.

Masalah yang sama persis terjadi dengan limit seperti:

$$
\lim_{x \rightarrow a} \frac{x^2-a^2}{x-a},
$$

di mana lagi-lagi kita tidak bisa hanya memasukkan nilai $x=a$, tetapi harus menggunakan semacam penyederhanaan aljabar. Ngomong-ngomong, perhatikan bahwa ekspresi ini sebenarnya hanya cara lain untuk menulis:

$$
\lim_{h \rightarrow 0} \frac{(a+h)^2-a^2}{(a+h)-a}
$$

—kita hanya mengganti $x-a$ dengan $h$ dalam ekspresi ini.

Tetapi kita juga bisa mempertimbangkan hal-hal yang lebih sederhana seperti:

$$
\lim_{x \rightarrow a} x^2, \quad \lim_{x \rightarrow a} x^3, \quad \text{dll.,}
$$

yang jelas memiliki nilai:

$$
a^2, \quad a^3, \quad \text{dll.}
$$

Bahkan, seseorang mungkin tergoda untuk mengatakan bahwa kita selalu memiliki:

$$
\lim_{x \rightarrow a} g(x)=g(a),
$$

selama $g(a)$ benar-benar masuk akal.

Namun, ini bisa dengan mudah tidak benar untuk fungsi-fungsi tertentu yang muncul secara alami. Misalnya, fungsi:

$$
P(x)=\left\{\begin{array}{ll}
32 & \text{untuk } 0<x \leq 1, \\
55 & \text{untuk } 1<x \leq 2, \\
78 & \text{untuk } 2<x \leq 3, \\
\ldots & \ldots
\end{array}\right.
$$

![](Pasted%20image%2020250622095737.png)

digunakan oleh Kantor Pos untuk menentukan ongkos kirim surat berdasarkan berat dalam ons (setidaknya fungsi itu digunakan ketika buku ini ditulis; siapa tahu apa yang akan digunakan pada saat Anda membacanya). Di sini:

dinyatakan dengan pasti bahwa pernyataan $\lim_{x \rightarrow 1} P(x) = P(1) = 32$ salah.

Benar bahwa $P(x)$ akan mendekati 32 (bahkan sama dengan 32) untuk nilai $x$ yang mendekati 1 tetapi lebih kecil dari 1; tetapi ketika kita memilih $x$ yang mendekati 1 tetapi lebih besar dari 1, nilai $P(x)$ tidak akan mendekati 32 (akan menjadi 55). Bahkan, dalam kasus ini $\lim_{x \rightarrow 1} P(x)$ tidak masuk akal, atau seperti yang biasanya kita katakan, "limit tersebut tidak ada."

Fungsi semacam ini mengundang berbagai pertanyaan filosofis yang mungkin tidak ingin dianggap terlalu serius oleh Kantor Pos (dapatkah setetes tinta tambahan pada surat benar-benar mengubah ongkos kirim?), tetapi apakah fungsi $P$ masuk akal di dunia nyata atau tidak, itu harus diperhitungkan dalam dunia matematika. Jadi, kita ingin mengadopsi beberapa terminologi untuk membedakan fungsi-fungsi "masuk akal" dari keanehan seperti itu. Kita mengatakan bahwa sebuah fungsi $f$ kontinu di $a$ jika:

$$
\lim_{x \rightarrow a} f(x)=f(a).
$$

Dengan demikian, fungsi $P$ tidak kontinu di 1.

Fungsi pertama yang ditunjukkan di bawah ini adalah modifikasi dari $P$ yang jelas juga tidak kontinu di 1, dan fungsi-fungsi yang menyertainya juga jelas tidak kontinu di 1 (dalam kasus ketiga $\lim_{x \rightarrow 1} f(x)$ ada, tetapi itu $\neq f(1)$). 

![](Pasted%20image%2020250622100117.png)

Sebenarnya, ada berbagai cara mengerikan lainnya bagi sebuah fungsi untuk tidak kontinu di $a$, 

![](Pasted%20image%2020250622100140.png)

tetapi sebagian besar waktu kita akan mengabaikan semua masalah tersebut. Kita biasanya hanya akan mempertimbangkan fungsi-fungsi $f$ yang memenuhi kondisi:

$$
f \text{ kontinu di } a \text{ untuk semua } a;
$$

untuk singkatnya, fungsi-fungsi seperti itu hanya disebut kontinu.

Ada banyak situasi di mana fungsi-fungsi tidak kontinu dapat dipertimbangkan dalam kalkulus, tetapi aspek-aspek terpenting dari kalkulus semuanya dapat diilustrasikan dan dipahami hanya dalam hal fungsi-fungsi kontinu. Bahkan, dari sudut pandang kalkulus, bahkan fungsi-fungsi kontinu bisa jadi tidak masuk akal.

Misalnya, fungsi $f(x)=|x|$ (halaman 13) adalah kontinu, tetapi jika kita menempatkan kaca pembesar kita di atas titik $(0,0)$ pada grafik, 

![](Pasted%20image%2020250622100228.png)

gambar yang diperbesar terlihat persis sama dengan aslinya—jadi dalam kasus ini itu tidak pernah terlihat seperti garis lurus! Memang, jika kita mencoba menghitung:

$$
\begin{aligned}
f^{\prime}(0)=\lim_{h \rightarrow 0} \frac{f(h)-f(0)}{h} & =\lim_{h \rightarrow 0} \frac{f(h)}{h} \\
& =\lim_{h \rightarrow 0} \left\{\begin{array}{ll}
\frac{h}{h} & h>0 \\
\frac{-h}{h} & h<0
\end{array}\right. \\
& =\lim_{h \rightarrow 0} \left\{\begin{array}{ll}
1 & h>0 \\
-1 & h<0,
\end{array}\right.
\end{aligned}
$$

kita segera melihat bahwa limit ini tidak ada. Secara umum, kita mengatakan bahwa $f$ dapat diturunkan di $a$ jika $f^{\prime}(a)$ ada (yaitu, jika limit yang digunakan untuk mendefinisikan $f^{\prime}(a)$ ada); jika $f$ tidak dapat diturunkan di $a$, maka simbol $f^{\prime}(a)$ bahkan tidak masuk akal.
[Back](./)
