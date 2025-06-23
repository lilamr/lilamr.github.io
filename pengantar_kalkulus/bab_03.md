[Home](../)\n[Back](./)\n
## Bab 3. Menghadapi sesuatu yang baru

Di bab sebelumnya, kita hampir secara eksklusif bekerja dengan persamaan berbentuk

$$
y = ax + b
$$

(meskipun kita biasanya menggunakan $m$ alih-alih $a$). Karena grafik dari persamaan ini selalu berupa garis lurus, ekspresi $ax + b$ biasanya disebut ekspresi linear.

Segala sesuatu yang bukan linear disebut non-linear, tetapi seperti yang sering terjadi ketika kita mencoba membuat dikotomi seperti ini ("Ada dua jenis orang di dunia ini ... "), kelompok-kelompok yang ditentukan oleh kriteria ini hampir tidak sebanding dalam ukuran. Begitu kita mempertimbangkan persamaan yang melibatkan ekspresi non-linear, kita menemukan berbagai kemungkinan yang hampir membingungkan.

Mari kita mulai dengan yang paling sederhana dari semuanya,

$$
y = x^2.
$$

Jika kita memplot banyak titik $(x, y)$ yang memenuhi persamaan ini, yaitu banyak titik berbentuk $(x, x^2)$, kita mendapatkan gambar seperti

![](Pasted%20image%2020250621212527.png)

yang dapat diisi untuk memberikan kurva yang disebut parabola.

![](Pasted%20image%2020250621212546.png)

Kurva ini simetris terhadap sumbu-y, karena $(-x)^2 = x^2$. Selain itu, kurva ini tidak pernah berada di bawah sumbu-x, karena kita selalu memiliki $x^2 \geq 0$. Sebaliknya, persamaan

$$
y = -x^2
$$

akan menggambarkan kurva yang tidak pernah berada di atas sumbu-x.

![](Pasted%20image%2020250621212611.png)

Di sisi lain, persamaan $y = 2x^2$ menggambarkan kurva yang dua kali lebih "curam" daripada parabola pertama kita, sedangkan $y = \frac{1}{2}x^2$ menggambarkan kurva yang setengah kali lebih curam.

![](Pasted%20image%2020250621212636.png)

Secara umum, $y = cx^2$ akan menggambarkan kurva yang mirip dengan parabola pertama kita untuk $c > 0$, tetapi mirip dengan yang kedua untuk $c < 0$.

Hal-hal terlihat sangat berbeda untuk persamaan $y = x^3$. Ini adalah persamaan dari kurva yang terus meningkat melalui nilai-nilai negatif dan positif. 

![](Pasted%20image%2020250621212733.png)

Untuk setiap titik $P = (x, x^3)$ pada kurva ini, titik $Q = (-x, (-x)^3)$ juga berada pada kurva, dan titik ini

$$
\begin{aligned}
Q &= (-x, (-x)^3) \\
&= (-x, -x^3),
\end{aligned}
$$

berada di sisi berlawanan dari garis dari $O$ ke $P$. Dengan demikian, kurva ini "simetris terhadap titik asal."

Ini secara alami membawa kita untuk mempertimbangkan $y = x^4, y = x^5, \ldots$, dan masing-masing menghasilkan kurva yang khas. Namun, secara umum, kurva yang dijelaskan oleh $y = x^n$ untuk $n$ genap semuanya menyerupai parabola, sedangkan kurva yang dijelaskan oleh $y = x^n$ untuk $n$ ganjil semuanya tampak seperti yang untuk $n = 3$.

![](Pasted%20image%2020250621212814.png)

Daripada mempertimbangkan kurva yang ditentukan oleh persamaan, kita sering kali merujuk pada grafik yang ditentukan oleh fungsi. Fungsi $f$ hanyalah aturan untuk menetapkan bilangan lain ke setiap bilangan $x$, yang dilambangkan dengan $f(x)$; bilangan ini disebut "nilai" dari $f$ pada $x$, dan $f(x)$ hanya diucapkan sebagai "f dari x". Dengan grafik dari fungsi $f$, kita maksudkan kumpulan semua titik $(x, f(x))$. Misalnya, jika $f$ adalah fungsi yang ditentukan oleh aturan $f(x) = 3x^2 + 4$, maka grafiknya terdiri dari semua titik $(x, 3x^2 + 4)$.

Kita juga bisa menggambarkan ini sebagai kumpulan titik $(x, y)$ yang memenuhi $y = f(x) = 3x^2 + 4$, sehingga grafik dari $f$ adalah kurva yang sama yang sebelumnya kita gambarkan dalam bentuk persamaan $y = 3x^2 + 4$. Jadi, mungkin tampak bahwa berbicara tentang "fungsi" daripada "persamaan" hanyalah perubahan kosa kata, tetapi ada beberapa perbedaan penting yang harus dibuat.

Pertama-tama, sebuah fungsi mungkin merupakan aturan yang tidak dapat diberikan oleh persamaan. Misalnya, anggap kita mempertimbangkan fungsi $f$ yang diberikan oleh aturan

$$
f(x) = \begin{cases} 
x & \text{jika } x \geq 0 \\
-x & \text{jika } x \leq 0 
\end{cases}
$$

dengan grafik yang ditunjukkan di bawah; perhatikan bahwa kita selalu memiliki $f(x) \geq 0$, berdasarkan definisinya, sehingga grafik tidak pernah berada di bawah sumbu-x. Grafik ini juga simetris terhadap sumbu-y, karena $f(-x) = f(x)$.

![](Pasted%20image%2020250621212903.png)

Simbol $|x|$ (nilai absolut dari $x$) didefinisikan sebagai

$$
|x| = \begin{cases} 
x & \text{jika } x \geq 0 \\
-x & \text{jika } x \leq 0.
\end{cases}
$$

Tentu saja, ini berarti bahwa grafik kita sebenarnya adalah grafik dari sebuah persamaan, yaitu persamaan $y = |x|$! Tetapi jelas bahwa ini hanya karena kita memutuskan untuk memperkenalkan simbol baru untuk menulis persamaan. Ada banyak fungsi $f$ yang grafiknya akan sangat sulit untuk dijelaskan sebagai grafik dari sebuah persamaan secara alami. Misalnya, gambar di bawah menunjukkan grafik dari sebuah fungsi $f$ di mana aturan untuk $f(x)$ adalah campuran rumit dari berbagai formula.

![](Pasted%20image%2020250621213017.png)

Meskipun grafik dari fungsi memungkinkan banyak bentuk yang sulit dijelaskan sebagai grafik dari persamaan, kadang-kadang hal-hal berjalan sebaliknya. Misalnya, grafik dari persamaan

$$
x^2 + y^2 = 1
$$

hanyalah lingkaran dengan jari-jari 1 di sekitar titik asal $O$, karena $\sqrt{x^2 + y^2}$ hanyalah jarak dari $O = (0,0)$ ke $(x, y)$. 

![](Pasted%20image%2020250621213057.png)

Grafik ini tidak bisa menjadi grafik dari sebuah fungsi, karena grafik dari sebuah fungsi terdiri dari titik-titik berbentuk $(x, f(x))$, di mana $f(x)$ hanya bisa satu bilangan—grafik dari sebuah fungsi tidak bisa memiliki dua titik berbeda pada garis vertikal yang sama.

![](Pasted%20image%2020250621213125.png)

Di sisi lain, kita dapat mendefinisikan dua fungsi berbeda yang grafiknya bersama-sama memberikan lingkaran. 

![](Pasted%20image%2020250621213210.png)

Bahkan, kita biasanya harus menggunakan trik seperti ini setiap kali kita ingin menggunakan kalkulus untuk menyelidiki kurva seperti lingkaran, karena kalkulus hampir sepenuhnya berfokus pada analisis fungsi dan grafiknya.

Garis vertikal gagal menjadi grafik dari sebuah fungsi dengan cara yang paling buruk, tetapi garis horizontal hanyalah grafik dari sebuah fungsi yang didefinisikan oleh aturan $f(x) = C$ untuk semua $x$. Fungsi seperti ini disebut fungsi konstan.

![](Pasted%20image%2020250621213257.png)

Meskipun tidak semua fungsi dapat dijelaskan dengan persamaan, tetap benar bahwa berbagai macam fungsi dapat dijelaskan hanya dengan memberikan formula untuk $f(x)$, seperti $f(x) = x^2$ atau $f(x) = x^3$. Fungsi biasanya dijelaskan secara singkat dengan cara ini, daripada mengatakan hal-hal yang rumit seperti "fungsi yang ditentukan oleh aturan $f(x) = x^2$," dll. Bahkan, kadang-kadang kita hanya mengatakan "fungsi $x^2$," dll. Hal penting yang perlu diperhatikan tentang semua notasi ini adalah bahwa huruf $x$ tidak mewakili bilangan tertentu. Kita bisa saja mengatakan $f(a) = a^2$, untuk semua bilangan $a$; atau $f(t) = t^2$, untuk semua bilangan $t$. Huruf $x$ atau $a$ atau $t$ hanya berfungsi sebagai "penampung nilai" (*place-holder*), memberikan cara yang masuk akal untuk mengatakan

$$
f(\text{bilangan}) = \text{kuadrat dari bilangan itu}.
$$

Kita bahkan bisa mengatakan $f(y) = y^2$, meskipun biasanya kita merasa nyaman untuk menyisihkan $y$ untuk nilai $f(x)$. Singkatnya, penggunaan huruf tertentu hanyalah konvensi. Jika kita akan menyebut sumbu horizontal sebagai sumbu-x, dan memberikan nama bilangan seperti $x_0, x_1$, dll., maka kita mungkin akan menggunakan notasi seperti $f(x)$; jika kita memikirkan sumbu-t, mungkin untuk mewakili waktu, maka kita mungkin akan menggunakan notasi seperti $f(t)$.

Sejauh ini, kita hanya mempertimbangkan beberapa fungsi seperti $f(x) = cx^2, f(x) = x^3$, dll., dan sudah menemukan bahwa ada variasi yang cukup besar. Hal-hal benar-benar mulai menjadi menarik ketika kita mempertimbangkan jumlah sembarang, seperti

![](Pasted%20image%2020250621213353.png)

Dan itu baru permulaan. Segala macam komplikasi baru muncul jika kita mulai membagi. Kita mendapatkan grafik yang terlihat sangat berbeda dari yang sebelumnya ketika kita mempertimbangkan hasil bagi sederhana:

![](Pasted%20image%2020250621213422.png)

Dalam contoh ini, kita tidak perlu khawatir tentang pembagian dengan 0, karena kita selalu memiliki $1 + x^2 > 0$. 

Contoh sederhana $f(x) = 1/x$, yang hanya didefinisikan untuk $x \neq 0$, menunjukkan apa yang bisa terjadi ketika penyebut kita bisa memiliki nilai 0.

![](Pasted%20image%2020250621213452.png)

Demikian pula, grafik dari

$$
f(x) = x^2 + \frac{1}{x}
$$

tampak seperti ini (di mana grafik dari $x^2$ muncul sebagai garis putus-putus):

![](Pasted%20image%2020250621213516.png)

Meskipun fungsi-fungsi yang telah kita temui sudah menunjukkan begitu banyak fitur baru, mereka hampir belum mewakili keragaman fungsi begitu kita mengizinkan hal-hal yang lebih menarik, seperti fungsi yang berasal dari trigonometri.

Ingat bahwa untuk segitiga siku-siku $\triangle OCB$ dengan $\theta = \angle BOC$, 

![](Pasted%20image%2020250621213635.png)

sinus dan kosinus dari sudut $\theta$ didefinisikan oleh

$$
\sin \theta = \frac{BC}{OB}, \quad \cos \theta = \frac{OC}{OB}.
$$

Definisi ini tidak bergantung pada segitiga yang kita pilih, karena jika segitiga $\triangle OC'B'$ juga memiliki sudut $\theta$ di $O$, maka itu serupa dengan $\triangle OCB$, 

![](Pasted%20image%2020250621213717.png)

dan akibatnya

$$
\frac{B'C'}{OB'} = \frac{BC}{OB}, \quad \frac{OC'}{OB'} = \frac{OC}{OB}.
$$

Lebih nyaman untuk memilih segitiga kita sehingga titik sudut $O$ berimpit dengan titik asal $O$ dari sistem koordinat kita, dengan $OC$ terletak di sepanjang sumbu-x. Selain itu, karena ukuran segitiga tidak relevan, kita juga dapat menentukan $B$ dengan mengharuskan itu terletak pada lingkaran satuan, sehingga jarak $BO = 1$, dan kemudian kita hanya memiliki $\sin \theta = BC$ dan $\cos \theta = OC$. 

![](Pasted%20image%2020250621214000.png)

Lebih ringkas lagi, jika $B = (x, y)$, maka

$$
\sin \theta = y, \quad \cos \theta = x.
$$

Jika kita mengukur sudut dalam derajat, maka sudut $\theta$ dalam gambar di atas memenuhi $0 < \theta < 90^\circ$, tetapi kita dapat mendefinisikan $\sin \theta$ untuk semua nilai $\theta$ lainnya, baik positif maupun negatif, dengan skema yang seharusnya sudah Anda kenal.

![](Pasted%20image%2020250621214032.png)

Jadi, kita sekarang memiliki fungsi $\sin$ ("fungsi sinus"), yang nilai pada $\theta$ adalah $\sin \theta$, serta fungsi $\cos$ ("fungsi kosinus"). Grafik dari fungsi sinus terlihat seperti

![](Pasted%20image%2020250621214054.png)

Perhatikan bahwa dalam gambar ini kita menggunakan skala yang berbeda pada kedua sumbu; tanpa distorsi ini, tidak banyak yang bisa dilihat dalam grafik kita kecuali kita membuatnya sangat lebar.

Selain dari kekurangan estetis ini, mengukur sudut dalam derajat tampaknya agak sewenang-wenang—lagipula, apa yang begitu spesial tentang 90 atau 360? Cara yang jauh lebih alami secara konseptual untuk mengukur sudut adalah dengan menggunakan panjang busur lingkaran satuan dari titik $A = (1,0)$ ke $B$.

![](Pasted%20image%2020250621214123.png)

Jika busur ini memiliki panjang $\theta$, maka $\angle AOB$ adalah sudut sebesar $\theta$ radian, atau memiliki "ukuran radian" sebesar $\theta$.

Sudut yang mengelilingi penuh ($360^\circ$) memiliki ukuran radian $2\pi$, yaitu keliling lingkaran satuan; sudut siku-siku memiliki ukuran radian

$$
\frac{1}{4} \cdot 2\pi = \frac{\pi}{2}
$$

sudut $45^\circ$ dengan demikian memiliki ukuran radian $\pi/4$, dll. Dengan kata lain, sudut sebesar $\theta$ radian adalah

$$
\frac{\theta}{2\pi} \text{ dari sudut yang mengelilingi penuh.}
$$

Meskipun kita mendefinisikan ukuran radian berdasarkan panjang busur lingkaran satuan dari $A = (1,0)$ ke $B$, kita bisa dengan mudah menentukannya berdasarkan luas sektor $OAB$: 

![](Pasted%20image%2020250621214359.png)

Karena sudut sebesar $\theta$ radian adalah

$$
\frac{\theta}{2\pi} \text{ dari sudut yang mengelilingi penuh,}
$$

luas dari $OAB$ diberikan oleh

$$
\begin{aligned}
\text{luas } OAB &= \frac{\theta}{2\pi} \cdot \text{luas lingkaran satuan} = \frac{\theta}{2\pi} \cdot \pi \\
&= \frac{\theta}{2}.
\end{aligned}
$$

Jadi, $\angle AOB$ adalah sudut sebesar $\theta$ radian ketika sektor $OAB$ memiliki luas $\theta/2$ (yang dengan nyaman menghilangkan penyebutan $\pi$).

Jika kita sekarang membiarkan $\sin \theta$ menjadi sinus dari sudut sebesar $\theta$ radian, maka grafik dari $\sin$ terlihat seperti

![](Pasted%20image%2020250621214454.png)

sedangkan grafik dari $\cos$ terlihat seperti

![](Pasted%20image%2020250621214511.png)

Mulai sekarang, kita pada dasarnya bisa melupakan pengukuran derajat, setidaknya sejauh menyangkut fungsi dan grafiknya. Ketika matematikawan merujuk pada fungsi $\sin$, mereka selalu bermaksud fungsi yang Anda dapatkan dengan menggunakan ukuran radian.

Ada sejumlah fungsi trigonometri lain, seperti $\tan$, $\cot$, dll., tetapi mereka tidak terlalu penting, karena mereka dapat diungkapkan dalam bentuk $\sin$ dan $\cos$,

$$
\tan \theta = \frac{\sin \theta}{\cos \theta}, \text{dll.}
$$

Sebenarnya, kita bahkan bisa mengungkapkan $\cos$ dalam bentuk $\sin$. Karena kita memiliki

![](Pasted%20image%2020250621214604.png)

$$
(OC)^2 + (CB)^2 = 1,
$$

yaitu,

$$
(\cos \theta)^2 + (\sin \theta)^2 = 1,
$$

yang biasanya ditulis hanya sebagai

$$
\cos^2 \theta + \sin^2 \theta = 1,
$$

dan karenanya

$$
\cos \theta = \pm \sqrt{1 - \sin^2 \theta}.
$$

Pilihan tanda $+$ atau $-$ yang tepat tergantung pada nilai $\theta$. 

![](Pasted%20image%2020250621214653.png)

Misalnya, untuk $0 < \theta < \pi/2$ (antara 0 dan sudut siku-siku), kita harus memilih tanda $+$; untuk $\pi/2 < \theta < \pi$ (antara sudut siku-siku dan sudut lurus), kita harus memilih tanda $-$, karena $\cos$ negatif, sedangkan $\sin$ masih positif; dll. Karena komplikasi tambahan yang melibatkan penentuan tanda ini, biasanya lebih nyaman untuk menganggap $\cos$ dan $\sin$ sebagai sama-sama fundamental.

Setelah kita menambahkan $\sin$ dan $\cos$ ke dalam repertoar kita, berbagai macam fungsi baru menjadi tersedia.

![](Pasted%20image%2020250621214755.png)

Dan masih ada cara lain untuk membuat fungsi. Misalnya, kita bisa mempertimbangkan grafik dari fungsi seperti

![](Pasted%20image%2020250621214826.png)

dan

![](Pasted%20image%2020250621214844.png)

dan kemudian segala macam kombinasi baru seperti

![](Pasted%20image%2020250621214905.png)

dan

![](Pasted%20image%2020250621214922.png)

Tetapi kita sudah melihat cukup banyak untuk menegaskan poin utama—ada sangat banyak fungsi.

Kita telah tiba di dunia baru, penuh dengan hal-hal menakjubkan, tetapi pada saat yang sama mungkin sedikit menakutkan. Sementara geometri analitik mungkin puas dengan menganalisis garis lurus dan lingkaran, dan mungkin beberapa kurva khusus lainnya, kalkulus berupaya untuk menyelidiki fungsi secara umum. Tetapi ini mungkin tampak hampir sia-sia. Jika fungsi begitu beragam, dan menunjukkan fitur yang begitu berbeda, bagaimana kita bisa berharap untuk mengatakan sesuatu yang menarik tentang semuanya?
[Back](./)
