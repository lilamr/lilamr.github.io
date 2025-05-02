[Home](../)

[back](./)

### **Ringkasan Buku**
Buku ini, diterbitkan oleh The New Mexico Tech Press pada tahun 2014, bertujuan untuk mendorong pemrogram berpikir secara matematis saat mengembangkan program, dengan menekankan konsep-konsep matematika diskrit seperti himpunan (*sets*), urutan (*sequences*), pemetaan (*mappings*), relasi (*relations*), dan struktur data lainnya. Buku ini menggunakan Python sebagai bahasa pemrograman utama karena kesederhanaannya, desain yang bersih, dan dukungan bawaan untuk struktur matematis seperti himpunan, kamus (*dictionaries*), dan fungsi kelas satu (*first-class functions*). 

Buku ini ditujukan untuk pembaca dengan sedikit pengalaman pemrograman, tetapi tidak memerlukan latar belakang matematika diskrit sebelumnya. Penulis memperkenalkan konsep matematika secara bertahap melalui contoh-contoh pemrograman praktis, menunjukkan bagaimana pemikiran matematis dapat menyederhanakan desain program dan menghasilkan solusi yang elegan. Buku ini juga mencakup studi kasus yang mengilustrasikan penerapan konsep-konsep ini dalam proyek-proyek nyata, seperti berbagi daftar lagu, survei biologis, dan manajemen kartu catatan untuk penulis.

---

### **Struktur Buku**
Buku ini terdiri dari 12 bab, ditambah pendahuluan, epilog, solusi latihan terpilih, dan indeks. Setiap bab membahas konsep matematika diskrit tertentu dan bagaimana konsep tersebut diimplementasikan dalam Python. Berikut adalah ringkasan isi setiap bab:

1. **Introduction**  
   - Memperkenalkan gagasan bahwa pemrograman tingkat tinggi sering kali melibatkan objek matematis seperti himpunan, urutan, dan relasi.
   - Memberikan gambaran awal tentang Python melalui tiga skrip sederhana: mencari nama, mencari alamat email, dan menghitung rata-rata pengamatan.
   - Memperkenalkan istilah matematika dasar seperti *set*, *sequence*, *ordered pair*, *relation*, *mapping*, dan *multiset*.

2. **An Overview of Python**  
   - Menjelaskan dasar-dasar Python: nilai (*values*), tipe (*types*), nama (*names*), dan operasi seperti penugasan (*assignment*).
   - Membahas tipe data seperti bilangan bulat (*integers*), bilangan desimal (*floating-point numbers*), dan string, serta operator seperti `+`, `-`, `*`, `/`, `//`, dan `%`.

3. **Python Programs**  
   - Memperkenalkan pernyataan (*statements*), kondisional (*if*), dan iterasi (*for* dan *while*).
   - Menekankan pentingnya penulisan kode yang terstruktur dan mudah dibaca.

4. **Python Functions**  
   - Membahas definisi fungsi, fungsi rekursif, fungsi sebagai nilai (*first-class functions*), dan ekspresi *lambda*.
   - Menunjukkan bagaimana fungsi dapat digunakan untuk abstraksi dan pemrograman fungsional.

5. **Tuples**  
   - Memperkenalkan konsep matematis *ordered pairs* dan *n-tuples*, serta implementasinya di Python sebagai *tuple*.
   - Menjelaskan penggunaan *tuple* dalam file dan basis data relasional.

6. **Sequences**  
   - Membahas sifat matematis urutan, termasuk konsep *monoid* (struktur aljabar dengan operasi asosiatif dan elemen identitas).
   - Menjelaskan urutan di Python (seperti daftar dan *tuple*), fungsi urutan tingkat tinggi (*higher-order functions* seperti `map` dan `filter`), dan *comprehensions*.
   - Memperkenalkan pemrosesan paralel menggunakan urutan.

7. **Streams**  
   - Memperkenalkan *streams* sebagai urutan yang dihasilkan secara dinamis, diimplementasikan menggunakan fungsi *generator* dan ekspresi *generator*.
   - Membahas *endless streams* dan penggabungan (*concatenation*) *streams*, serta aplikasi dalam pemrosesan terdistribusi.

8. **Sets**  
   - Menjelaskan himpunan matematis dan implementasinya di Python menggunakan tipe `set`.
   - Menyajikan studi kasus tentang mencocokkan mahasiswa dengan pekerjaan menggunakan operasi himpunan seperti persimpangan (*intersection*) dan perbedaan (*difference*).

9. **Mappings**  
   - Membahas pemetaan matematis dan implementasinya sebagai kamus (*dictionaries*) di Python.
   - Menyajikan studi kasus tentang mencari kata dalam dokumen teks menggunakan kamus.
   - Memperkenalkan *multisets* (koleksi dengan elemen berulang) dan teknik *memoization*.

10. **Relations**  
    - Memperkenalkan relasi matematis, termasuk sifat seperti refleksif, simetris, dan transitif.
    - Membahas representasi relasi dalam program, graf (*graphs*), dan operasi basis data relasional seperti *join* dan *projection*.

11. **Objects**  
    - Memperkenalkan pemrograman berorientasi objek (*object-oriented programming*) di Python, termasuk kelas (*classes*), pewarisan (*inheritance*), dan atribut.
    - Menyajikan studi kasus tentang rata-rata bergerak (*moving averages*) dan struktur rekursif seperti pohon (*trees*) dan mesin keadaan (*state machines*).

12. **Larger Programs**  
    - Menyajikan tiga studi kasus yang mengintegrasikan konsep dari bab sebelumnya:
      - **Sharing Tune Lists**: Mengelola daftar lagu menggunakan himpunan, *multisets*, dan urutan.
      - **Biological Surveys**: Merepresentasikan hierarki taksonomi sebagai pohon dan graf untuk menghitung data survei.
      - **Note Cards for Writers**: Mengelola fragmen teks sebagai kartu catatan dengan struktur seperti graf terarah (*directed graphs*) dan pohon.

**Afterword**  
   - Menggarisbawahi pentingnya matematika diskrit dalam pemrograman dan mendorong pembaca untuk menerapkannya dalam pekerjaan sehari-hari.
   - Menyebutkan topik lanjutan seperti logika, bahasa formal, dan kombinatorika yang relevan untuk ilmu komputer.

**Solutions to Selected Exercises**  
   - Menyediakan jawaban untuk latihan terpilih dari setiap bab, membantu pembaca memahami konsep melalui contoh praktis.

**Index**  
   - Daftar istilah teknis dan konsep yang dibahas dalam buku, seperti *monoid*, *set comprehension*, dan *recursion*.

---

### **Poin-Poin Kunci**
1. **Pemikiran Matematis dalam Pemrograman**:
   - Matematika diskrit (himpunan, urutan, pemetaan, relasi) memberikan kosa kata yang jelas untuk mendesain dan mendokumentasikan program.
   - Contoh: Mencari URL yang sama di dua halaman web lebih mudah dengan operasi persimpangan himpunan dibandingkan pendekatan berbasis daftar.

2. **Fokus pada Python**:
   - Python dipilih karena sintaksnya yang sederhana, dukungan bawaan untuk struktur matematis, dan fleksibilitas sebagai bahasa skrip, berorientasi objek, dan tingkat tinggi.
   - Buku ini menggunakan Python 3, dengan catatan tentang perbedaan dengan Python 2 (misalnya, `print` sebagai fungsi, pembagian bilangan bulat menghasilkan *float*).

3. **Konsep Matematika Diskrit**:
   - **Himpunan**: Koleksi tidak terurut tanpa duplikat, diimplementasikan sebagai `set`.
   - **Urutan**: Koleksi terurut, diimplementasikan sebagai daftar (*list*) atau *tuple*.
   - **Pemetaan**: Hubungan satu-ke-satu, diimplementasikan sebagai kamus (*dictionary*).
   - **Relasi**: Hubungan antar elemen, direpresentasikan sebagai himpunan pasangan terurut atau graf.
   - **Multiset**: Koleksi dengan elemen berulang, diimplementasikan menggunakan kamus untuk menghitung kemunculan.
   - **Monoid**: Struktur aljabar yang muncul di banyak tipe data (misalnya, konkatenasi string, penjumlahan bilangan).
   - **Graf dan Pohon**: Digunakan untuk merepresentasikan hierarki atau hubungan kompleks, seperti taksonomi biologis atau struktur catatan.

4. **Pendekatan Praktis**:
   - Setiap konsep diilustrasikan dengan contoh kode Python, sering kali dalam bentuk skrip sederhana atau studi kasus.
   - Latihan di akhir setiap bab mendorong pembaca untuk menerapkan konsep secara langsung.

5. **Studi Kasus**:
   - Menunjukkan bagaimana konsep matematika diskrit diterapkan dalam proyek nyata, seperti:
     - Mengelola daftar lagu dengan *multisets* dan *set comprehensions*.
     - Merepresentasikan hierarki taksonomi sebagai pohon rekursif.
     - Mengelola kartu catatan sebagai graf terarah dengan operasi pencarian dan pengurutan.

6. **Relevansi untuk Ilmu Komputer**:
   - Buku ini menjembatani pemrograman dan matematika diskrit, mempersiapkan pembaca untuk topik lanjutan seperti bahasa formal, kombinatorika, dan analisis algoritma.
   - Konsep seperti *monoid* dan *recursion* sangat relevan untuk desain algoritma dan struktur data.

---

### **Gaya Penulisan**
- **Jelas dan Terstruktur**: Penulis menggunakan pendekatan bertahap, memperkenalkan konsep matematika dan Python secara bersamaan dengan contoh yang relevan.
- **Berbasis Contoh**: Setiap bab menyertakan skrip atau program yang menunjukkan penerapan konsep, sering kali disertai penjelasan baris demi baris.
- **Inklusif**: Ditulis untuk pembaca dengan berbagai tingkat pengalaman, dari pemula hingga pemrogram berpengalaman yang ingin mempelajari pendekatan matematis.
- **Inspiratif**: Terinspirasi oleh *Structure and Interpretation of Computer Programs* (SICP), buku ini menjadikan Python sebagai platform untuk menunjukkan keindahan pemrograman matematis.

---

### **Target Pembaca**
- **Mahasiswa Ilmu Komputer**: Cocok untuk kursus tingkat universitas atau sekolah menengah atas yang berfokus pada pemrograman dan matematika diskrit.
- **Pemrogram Berpengalaman**: Ideal untuk mereka yang belum memiliki latar belakang matematika diskrit tetapi ingin meningkatkan keterampilan desain program.
- **Ilmuwan Data atau Peneliti**: Relevan untuk mereka yang menggunakan Python untuk analisis data dan membutuhkan pemahaman tentang struktur matematis.
- **Pemula dengan Latar Belakang Pemrograman**: Meskipun tidak dirancang untuk pemula absolut, buku ini dapat digunakan dengan suplemen pengantar pemrograman.

---

### **Kesimpulan**
*Programming and Mathematical Thinking* adalah buku yang sangat berharga bagi siapa saja yang ingin memahami bagaimana matematika diskrit dapat meningkatkan kualitas pemrograman. Dengan pendekatan yang jelas, contoh praktis, dan studi kasus yang relevan, buku ini menunjukkan bahwa konsep seperti himpunan, pemetaan, dan relasi bukan hanya teori abstrak, tetapi alat praktis untuk menyelesaikan masalah pemrograman. Python digunakan secara efektif untuk mengilustrasikan konsep-konsep ini, menjadikan buku ini cocok untuk pelajar, pemrogram, dan profesional yang ingin memperdalam pemahaman mereka tentang pemrograman melalui lensa matematika.

[back](./)

