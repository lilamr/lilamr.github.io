[Home](../)

## Shell
Dari dalam Vim, kamu bisa menjalankan hampir semua **perintah shell** dengan awalan `:!`. Berikut ini beberapa contoh perintah shell umum yang sering dipakai langsung dari Vim:

| Perintah Vim          | Fungsi                                                          |
| --------------------- | --------------------------------------------------------------- |
| `:!ls`                | Menampilkan daftar file dan folder.                             |
| `:!pwd`               | Menampilkan direktori kerja saat ini.                           |
| `:!date`              | Menampilkan waktu dan tanggal sekarang.                         |
| `:!clear`             | Membersihkan layar terminal (walau tidak selalu tampak di Vim). |
| `:!whoami`            | Menampilkan nama pengguna saat ini.                             |
| `:!echo Hello`        | Mencetak teks “Hello”.                                          |
| `:!mkdir folderku`    | Membuat folder baru.                                            |
| `:!rm file.txt`       | Menghapus file.                                                 |
| `:!python3 script.py` | Menjalankan skrip Python.                                       |

`:sh` untuk keluar sebentar ke shell (terminal interaktif). setelah selesai, ketik `exit` untuk kembali ke Vim.

Untuk menggunakan **output perintah shell** (seperti `ls`, `date`, dll.) **langsung ke dalam file** di Vim, kamu bisa pakai perintah `:r !perintah`, contoh:
- `:r !ls` menyisipkan hasil `ls` ke dalam file di bawah baris kursor
- `:r !cat file.txt` menyisipkan isi file lain
- `:r !curl -s https://example.com` menyisipkan hasil curl atau wget

[back](./)
