## Register
Dalam Vim, _register_ adalah tempat penyimpanan sementara untuk teks yang Anda salin, potong, atau ketik.
`"` register default (otomatis digunakan saat copy/cut/paste)
`0` menyimpan teks terakhir yang di copy bukan di cut/delete. jika ingin kembali ke hasil copy, gunakan: `:put 0`
`1-9` menyimpan riwayat teks yang di cut/delete. `1` berisi potongan terakhir, `2` berisi potongan sebelumnya, dan seterusnya hingga `9`. contoh, `:put 3` atau `"3p` untuk menampilkan isi register ke-3 
`a-z` untuk menyimpan teks ke register tertentu secara manual. contoh:`"ay` akan menyimpan teks hasil copy ke register `a`. untuk menempelkan teks dari register `a` gunakan `"ap`
`A-Z` sama dengan `a-z`, **tapi digunakan untuk menambahkan** teks ke register tersebut (append). contoh, `"Ay` akan **menambahkan** hasil `yank` ke register `a`
`_` semua teks yang dikirim ke sini akan dibuang dan tidak akan mengubah isi register lainnya. contoh, ingin menghapus/cut satu baris, tanpa mengganti isi copy clipboard sebelumnya, `"_dd`
`.` menyimpan teks yang terakhir diketik dalam mode insert. misalnya setelah keluar dari mode insert, Anda bisa menempelkan ulang teks tersebut dengan `".p`
`%` menyimpan **nama file aktif** saat ini. contoh penggunaan,`:e %` membuka ulang file saat ini
`#` menyimpan **nama file yang dibuka sebelumnya**. contoh, `:e #` akan membuka kembali ke file sebelumnya
`:register` atau `:reg` untuk melihat isi semua register