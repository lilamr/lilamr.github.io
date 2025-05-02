[Home](../)
[back](./)

## Prakata

Misi saya dalam buku ini adalah mengajak para pemrogram untuk berpikir secara matematis saat mereka menciptakan program. 

Pemikiran seperti ini bukan hal asing bagi para pemrogram di bidang sains dan teknik, karena pekerjaan mereka sering kali berpijak pada matematika numerik dan bilangan real. Namun, matematika tidak hanya soal angka. 

Ada cabang matematika yang disebut [[matematika diskrit]], yang sangat relevan untuk pemrograman. Matematika diskrit mempelajari elemen-elemen terpisah, seperti simbol, rangkaian karakter, nilai kebenaran (benar atau salah), dan "objek" (dalam istilah pemrograman) yang merupakan kumpulan sifat-sifat tertentu. Cabang ini juga mengeksplorasi kumpulan elemen, seperti himpunan dan urutan, serta hubungan antar elemen dalam struktur seperti pemetaan dan relasi. Dalam banyak hal, matematika diskrit bahkan lebih penting untuk pemrograman dibandingkan matematika numerik—bukan hanya untuk jenis pemrograman tertentu, melainkan untuk semua jenis pemrograman.

Banyak pemrogram berpengalaman merancang program dengan mendeskripsikan input, output, dan objek data internalnya menggunakan istilah-istilah matematika diskrit: himpunan, urutan, pemetaan, relasi, dan sebagainya. Ini adalah kebiasaan yang sangat bermanfaat untuk kita kembangkan sebagai pemrogram. Pendekatan ini membantu menjernihkan pemikiran kita saat menghadapi masalah desain, dan sering kali solusi menjadi jelas dengan sendirinya. Selain itu, kita juga mendapatkan kosa kata yang sudah dikenal luas untuk menjelaskan, mendokumentasikan, dan mendiskusikan program kita dengan pemrogram lain. [^1]

Sebagai contoh, bayangkan sebuah masalah pemrograman sederhana. Misalkan kita sedang mengembangkan perangkat lunak untuk menganalisis halaman web, dan kita perlu membuat kode yang membaca dua halaman web lalu menemukan semua URL yang muncul di keduanya. Seorang pemrogram mungkin mendekati masalah ini dengan cara berikut:

> Pertama, saya akan membaca halaman web pertama dan menyimpan semua URL yang saya temukan dalam sebuah daftar. Lalu, saya akan membaca halaman web kedua dan, setiap kali menemukan URL, memeriksa apakah URL itu ada di daftar pertama. Tapi tunggu, saya tidak ingin URL yang sama muncul lebih dari sekali di hasil akhir. Jadi, saya perlu daftar kedua untuk mencatat URL yang sudah ditemukan di kedua halaman, dan memeriksanya sebelum mencari di daftar URL dari halaman pertama.

Namun, seorang pemrogram yang terbiasa berpikir dalam kerangka matematika diskrit mungkin langsung memikirkan pendekatan yang lebih sederhana:

> URL dalam sebuah halaman web dapat dianggap sebagai sebuah himpunan. Saya akan membaca setiap halaman web dan membangun himpunan URL-nya dengan operasi penyisipan himpunan. Setelah itu, saya tinggal mencari irisan himpunan dari kedua halaman untuk mendapatkan URL yang muncul di keduanya.

Kedua pendekatan ini bisa berhasil, tetapi pendekatan kedua jauh lebih sederhana secara konseptual dan kemungkinan besar lebih mudah diimplementasikan. Begitu masalah diterjemahkan ke dalam istilah matematis, sebagian besar pekerjaan desain sudah selesai.

Inilah cara berpikir yang ingin saya dorong melalui buku ini.

Sebagai alat untuk menjelaskan konsep-konsep ini, saya memilih bahasa pemrograman **Python**. Python adalah bahasa yang bersih, modern, dan dilengkapi dengan banyak struktur matematis yang kita butuhkan, seperti string, himpunan, berbagai jenis urutan, pemetaan terbatas (berupa dictionary, yang lebih fleksibel daripada array), dan fungsi yang diperlakukan sebagai nilai kelas satu. Semua fitur ini terintegrasi dalam inti bahasa, bukan sekadar tambahan dari pustaka eksternal seperti di banyak bahasa lain. Python mudah dipelajari, menjadikannya pilihan ideal sebagai bahasa pertama—jauh lebih baik daripada C, C++, atau Java, menurut saya. Singkatnya, Python adalah alat yang hebat untuk menyelesaikan pekerjaan dengan cepat dan tanpa kerumitan berlebihan. Saya sendiri sering menggunakannya dalam pekerjaan sehari-hari, dan banyak pembaca akan menemukan bahwa Python cukup untuk kebutuhan pemrograman mereka.

Secara matematis, buku ini dimulai dari tingkat yang cukup dasar. Saya tidak mengasumsikan pembaca memiliki latar belakang matematika di luar aljabar dan logaritma. Di beberapa bagian, saya menggunakan contoh dari kalkulus dasar, tetapi pembaca yang belum mempelajari kalkulus bisa melewatinya tanpa masalah. Saya juga tidak mengharapkan pembaca telah mengambil kursus matematika diskrit sebelumnya; konsep-konsep matematika diskrit akan diperkenalkan secara bertahap sepanjang buku. Beberapa konsep ini sederhana namun sangat kuat, dan sayangnya, banyak pemrogram tidak pernah mempelajarinya. Kita akan melihat bagaimana konsep-konsep ini dapat digunakan untuk menciptakan solusi pemrograman yang sederhana dan elegan.

Salah satu tema berulang dalam buku ini adalah konsep [[monoid]]. Ternyata, monoid—lebih dari struktur lain seperti grup atau semigroup—hadir di mana-mana dalam tipe data dan struktur data yang paling sering digunakan oleh pemrogram. Saya akan menyoroti bagaimana semua monoid memiliki sifat-sifat yang serupa, serta bagaimana konsep dan algoritma dapat diterapkan dari satu monoid ke monoid lainnya dengan mudah.

Buku ini cocok untuk kursus tingkat universitas pertama, atau bahkan kursus lanjutan di sekolah menengah, terutama untuk siswa yang tertarik pada matematika dan telah memiliki sedikit pengalaman dengan komputer dan pemrograman. Bagi siswa yang sama sekali belum terpapar pemrograman, buku ini bisa dilengkapi dengan buku teks pengantar pemrograman (menggunakan Python atau bahasa lain) atau dengan materi kuliah dan tutorial tambahan tentang teknik pemrograman. Buku ini juga bisa digunakan dalam kursus lanjutan setelah kursus pengantar pemrograman standar.

Pembaca ideal untuk buku ini adalah mereka yang sudah memiliki pengalaman pemrograman, baik dengan Python maupun bahasa lain. Bahkan, saya berharap beberapa pembaca adalah pemrogram berpengalaman yang belum pernah mengikuti pendidikan ilmu komputer modern yang berorientasi pada matematika. Jika Anda termasuk dalam kelompok ini, Anda akan menemukan banyak ide baru yang kemungkinan besar akan memperkaya cara Anda memprogram.

Di akhir setiap bab, terdapat latihan-latihan yang dapat digunakan oleh instruktur untuk sesi laboratorium, tugas rumah, atau sebagai bahan diskusi kelas. Banyak instruktur mungkin ingin menambahkan tugas pemrograman yang lebih kompleks untuk melengkapi latihan-latihan ini.

Di beberapa bagian, saya memperkenalkan suatu topik lalu berkata, “...detailnya di luar cakupan buku ini.” Buku ini memang bisa diperluas untuk mencakup hampir seluruh kurikulum ilmu komputer, tetapi saya harus membatasi ruang lingkupnya. Saya berharap para pembaca, terutama siswa, akan tertarik untuk mendalami topik-topik seperti penanganan pengecualian, komputasi paralel, komputasi terdistribusi, struktur data dan algoritma lanjutan, pemrograman berorientasi objek, atau mesin keadaan, baik dengan bimbingan instruktur maupun melalui kursus lanjutan.

Demikian pula, saya bisa saja memasukkan lebih banyak topik matematika diskrit, tetapi saya harus menentukan batasnya. Beberapa ilmuwan komputer atau matematikawan mungkin tidak setuju dengan pilihan topik saya, tetapi saya berusaha memilih yang paling relevan untuk pemrograman sehari-hari. Bagi mahasiswa ilmu komputer, Anda mungkin akan mempelajari matematika diskrit lebih mendalam di masa depan, dan saya harap buku ini menunjukkan betapa pentingnya matematika ini untuk pekerjaan pemrograman Anda, sekaligus memotivasi Anda untuk menekuni kelas matematika diskrit dengan lebih serius.

Buku ini bukanlah buku teks lengkap atau manual referensi untuk Python. Saya akan memperkenalkan banyak konstruksi Python dan menjelaskannya cukup rinci agar pembaca yang baru mengenal Python dapat memahami apa yang terjadi. Namun, saya tidak akan menjelaskan setiap konstruksi secara menyeluruh atau mencakup semua kemungkinan penggunaannya. Beberapa fitur Python juga sengaja diabaikan karena terlalu lanjutan atau tidak relevan untuk tujuan buku ini, seperti:
- Tipe data seperti `complex` dan `byte`.
- Beberapa operator serta banyak fungsi dan metode bawaan.
- Pemformatan string dan detail input/output.
- Pustaka standar yang luas dan pustaka eksternal lainnya.
- Pernyataan seperti `break`, `continue`, atau klausa `else` pada pernyataan `while` dan `for`.
- Variasi parameter dan argumen fungsi, seperti nilai default atau parameter kata kunci.
- Pengecualian dan penanganan pengecualian.
- Atribut dan metode “khusus” (dengan nama yang diawali dan diakhiri garis bawah ganda) yang mengungkap detail internal objek.
- Variasi definisi kelas, seperti pewarisan ganda dan dekorator.

Pemrogram yang ingin menggunakan Python secara mendalam harus mempelajari fitur-fitur ini melalui buku teks atau manual referensi Python yang komprehensif.[^2]

Jika Anda bertanya-tanya, “Saya bisa melakukan X dengan Python, apakah saya juga bisa melakukan Y?” jawabannya mungkin ya—dan Anda bisa mencari tahu di sumber referensi Python.

Buku ini menggunakan **Python 3**, versi paling modern dari bahasa ini. Jika Anda menggunakan Python 2 (misalnya, Python 2.3 atau 2.7), ada beberapa perbedaan kecil yang perlu diperhatikan, seperti:
- Di Python 2, `print` adalah pernyataan, bukan fungsi, tetapi sintaks `print(e)` (dengan e sebagai ekspresi tunggal) berfungsi di kedua versi.
- Python 2 memiliki tipe “bilangan bulat panjang” yang ditampilkan dengan akhiran “L” untuk bilangan besar, sedangkan Python 3 hanya memiliki satu tipe bilangan bulat tanpa batas ukuran.
- Pembagian bilangan bulat di Python 2 menghasilkan bilangan bulat (bukan desimal), sedangkan di Python 3 menghasilkan bilangan desimal.
- Di Python 2, string defaultnya adalah ASCII, bukan Unicode, dan ada tipe Unicode terpisah.

Versi Python sebelum 2.7 memiliki lebih banyak perbedaan, jadi pastikan untuk memeriksa dokumentasi versi yang Anda gunakan.

Dalam buku ini, saya menggunakan kata “kami” sebagai ganti orang pertama, kecuali saat menyampaikan pendapat pribadi, pengalaman saya sendiri, atau hal-hal serupa, di mana saya menggunakan “saya”. Saya juga mengikuti konvensi tanda baca ala Inggris: tanda baca hanya diletakkan di dalam tanda kutip jika itu bagian dari kutipan. Ini lebih logis (menurut saya) dan menghindari ambiguitas. Misalnya, banyak panduan gaya Amerika menulis:

> Untuk menambah satu ke 1, Anda akan menulis “1 = 1 + 1.”

Apakah titik (.) itu bagian dari apa yang ditulis? Ini bisa membingungkan, terutama bagi pemrogram. Dengan cara ini, tidak ada keraguan:

> Untuk menambah satu ke 1, Anda akan menulis “1 = 1 + 1”.

Saya berterima kasih kepada teman dan kolega yang telah memberikan bantuan, saran, dan dukungan dalam proyek penulisan ini, terutama Lisa Beinhoff, Horst Clausen, Jeff Havlena, Peter Henderson, Daryl Lee, Subhashish Mazumdar, Angelica Perry, Steve Schaffer, John Shipman, dan Steve Simpson.

Terakhir, saya ingin mengakui inspirasi besar dari buku teks klasik *Structure and Interpretation of Computer Programs* (SICP) karya Abelson dan Sussman.[^3] Saya meminjam beberapa ide darinya, terutama untuk pembahasan fungsi tingkat tinggi dan aliran data. Saya juga berusaha menjadikan buku ini sebagai panggung untuk memamerkan keunggulan Python, seperti SICP memamerkan bahasa Scheme. Yang terpenting, SICP telah menjadi teladan bagi saya tentang bagaimana pemrograman dapat diajarkan dengan serius dan mendalam.

[back](./)

---

[^1]: Paragraf ini dan contoh berikut ini diadaptasi dari buku sebelumnya: Allan M. Stavely, Toward Zero-Defect Programming (Reading, Mass.: Addison Wesley Longman, 1999), 142–143.

[^2]: Pada saat penulisan, dokumentasi Python yang komprehensif, termasuk manual referensi resmi, dapat ditemukan di http://docs.python.org.

[^3]: Harold Abelson and Gerald Jay Sussman with Julie Sussman, Structure and Interpretation of Computer Programs (Cambridge, Mass.: The MIT Press, 1985).
