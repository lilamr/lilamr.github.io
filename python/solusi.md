[Home](../)

[back](./)

## Solusi untuk Latihan Terpilih

### Bab 2: Sekilas tentang Python

2. Di komputer saya, interpreter Python berjalan sekitar dua setengah menit sebelum akhirnya menampilkan pesan, di antaranya:  

`MemoryError`

Ini menandakan bahwa interpreter telah menghabiskan seluruh memori utama yang tersedia, namun tetap tidak mampu menyelesaikan komputasi.  

4. Untuk bilangan bulat positif $$n$$, $$\log_{10} n$$ memberikan perkiraan jumlah digit desimal yang dibutuhkan untuk menuliskan $$n$$, sesuai dengan definisi logaritma. Perkiraan ini cukup akurat untuk $$n$$ yang sangat besar. 

Kita tahu bahwa $$\log_{10} n = (\log_2 n) / (\log_2 10)$$. Jika $$n = 2^{2^{100}}$$, maka $$\log_2 n = 2^{100}$$, dan  $$\log_2 10 \approx 3.32$$.

Jadi, jumlah digit untuk menuliskan $$n = 2^{2^{100}}$$ kira-kira adalah $$2^{100} / 3.32$$. Dengan bantuan interpreter Python atau kalkulator, kita menemukan bahwa $$2^{100}$$ adalah:  

$$1,267,650,600,228,229,401,496,703,205,376$$

Angka ini, bila dibagi 3.32, memberikan perkiraan jumlah digit yang diperlukan. Sekarang, dapatkah Anda bayangkan betapa besarnya $$2^{2^{100}}$$? Angka ini jelas terlalu besar untuk ditangani oleh kebanyakan komputer!  

5. Ya; tidak. Coba uji dengan beberapa contoh. Kita akan membahas sifat-sifat deret secara lebih mendalam di Bagian 6.1.  

6. Dengan menggabungkan ide dari dua skrip pertama di bab ini, kita bisa membuat sesuatu seperti ini:  

```python
file = open("names")
for line in file:
    firstname, lastname = line.split(" ")
    if firstname == "John":
        print(line)
```  

Mungkin Anda tidak langsung terpikir solusi ini jika tidak tahu bahwa `" "` di Python mewakili spasi. Tapi memang benar, spasi – karakter yang muncul saat Anda menekan tombol spasi di keyboard – adalah karakter seperti huruf, angka, atau tanda baca lainnya.  

### Bab 3: Program Python

1. Berikut salah satu solusi:  

```python
file = open("data")
for line in file:
    n = int(line)
    print("#" * n + " " + str(n))
```  

2. Berikut solusi lainnya:  

```python
file = open("data")
for line in file:
    n = int(line)
    if n > 20:
        barLength = 20
    else:
        barLength = n
    print("#" * barLength + " " + str(n))
```  

3. Berikut satu solusi:  

```python
file = open("data")
for line in file:
    n = int(line)
    if n > 20:
        print "#########/ /######## " + str(n)
    else:
        print "#" * barLength + " " + str(n)
```  

### Bab 6: Deret

3. Tidak. Operasi eksponensiasi tidak bersifat asosiatif. Misalnya, `2 ** (2 ** 3)` = $$2^8$$ = 256, tetapi `(2 ** 2) ** 3` = $$4^3$$ = 64. Selain itu, tidak ada elemen identitas untuk operator `**`. Angka 1 bisa berfungsi sebagai identitas di sisi kanan karena `n ** 1 = n` untuk semua $$n$$, tetapi tidak di sisi kiri, karena $$1 ** n \neq n$$ untuk kebanyakan nilai $$n$$. 

4. Berikut dua kemungkinan solusi:  
```python
def filter(test, sequence):
    result = ()
    for a in sequence:
        if test(a):
            result += (a,)
    return result
```  

```python
def filter(test, sequence):
    result = [a for a in sequence if test(a)]
    return tuple(result)
```  

Menurut Anda, mana yang lebih baik? Apa alasannya?  

10. Fungsi `reduceRight` dalam versi ini akan meneruskan argumen ke `f` dalam urutan terbalik. Hasilnya hanya akan benar jika `f` bersifat komutatif.  

### Bab 7: Aliran

2. Berikut satu solusi:  

```python
def prefix(n, stream):
    i = 0
    for a in stream:
        if i >= n:
            return
        else:
            yield a
            i += 1
```  

6. Tidak, setidaknya tidak dengan cara yang jelas, karena operasi rata-rata tidak asosiatif. Misalnya, jika $$\#$$ adalah operator rata-rata biner dengan $$a \# b = (a + b) / 2$$, maka $$(a \# b) \# c \neq a \# (b \# c)$$. Anda bisa membuktikannya dengan mencoba beberapa contoh. Secara umum, rata-rata dari beberapa rata-rata tidak sama dengan rata-rata keseluruhan nilai.  

Sebagai latihan tambahan, pikirkan bagaimana Anda bisa mengatasi masalah ini dalam konteks stasiun cuaca. Asumsikan Anda ingin meminimalkan jumlah data yang dikirim antar komputer, sehingga mengirim semua data ke pusat untuk diolah bukanlah solusi ideal.  

### Bab 8: Himpunan

1. Anda perlu menerapkan operasi "irisan besar" pada kumpulan himpunan. Gunakan fungsi reduce yang Anda buat untuk Latihan 9 di Bab 6. Apakah fungsi itu menggunakan perulangan for untuk mengiterasi urutan? Jika ya, fungsi tersebut seharusnya bisa digunakan untuk himpunan operan sama baiknya seperti untuk urutan operan. Bisakah Anda memahami mengapa?  

### Bab 9: Pemetaan

1. Pasangan nilai $$x$$ dan $$y$$ dari tipe yang operator biner `*` telah di-overload.  
2. Ketika domain $$c$$ dan $$d$$ tidak memiliki elemen yang sama, yaitu ketika $$\text{dom } c \cap \text{dom } d = \varnothing$$.  

### Bab 10: Relasi

2. Kita bisa mendefinisikan himpunan simpul graf sebagai himpunan semua $$a$$ dan $$b$$ dari pasangan $$(a, b)$$ dalam relasi. Namun, kita juga bisa menambahkan elemen lain ke himpunan tersebut; elemen ini akan menjadi simpul terisolasi, tetapi graf tetap akan mempertahankan relasi aslinya sebagai relasi ketetanggaannya. Definisi yang umum dan logis biasanya tidak menyertakan simpul terisolasi.  

3. Tidak, karena definisi monoid mensyaratkan bahwa setiap dua jalur dalam graf dapat digabungkan, terlepas dari apakah mereka memiliki titik akhir yang sama. Namun, himpunan semua jalur dalam graf berarah, bersama dengan operasi penggabungan, membentuk struktur matematis lain yang disebut "kategori."  

4. Kami hanya memberikan solusi untuk $$\sigma_p(X)$$ (bagian yang lebih sederhana). Misalkan $$Y = \sigma_p(X)$$, dan kita memilih urutan atribut yang sama untuk representasinya seperti pada $$X$$. Maka, $$A_Y = A_X$$, $$\text{col}_Y = \text{col}_X$$, dan $$R_Y = \{ x \in R_X \mid P(x) \}$$.  

**Bab 11: Objek**  
5. a. Ambil salah satu versi `ancestorNames` dari Bagian 11.6, ubah nama metode menjadi `ancestors`, dan ganti `self.name` dengan `self` di semua tempat.  

b. Manfaatkan operasi himpunan! Jika orangnya adalah $$p$$, himpunan yang Anda cari adalah 

$$\text{ancestors}(p) - \{p\}$$

c. Gunakan pemahaman himpunan, tentu saja. Bentuknya akan seperti ini:  

```python
{ ... for a in ancestors(p) }
```  

Saya yakin Anda bisa menyelesaikan latihan yang tersisa.

[back](./)
