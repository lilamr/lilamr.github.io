[Home](../)

## Macros
- Macro di Vim adalah rekaman dari rangkaian perintah yang bisa diputar ulang. Cocok untuk mengotomatiskan tugas berulang. Perintah akan disimpan dalam register.
- `q{register}` untuk mulai merekam macros. contoh, `qa` merekam macros ke register `a`, kemudian jalankan perintah-perintah vim seperti biasa. untuk mengakhiri rekaman tekan `q`.
- `@{register} untuk mulai menjalankan macros yang sudah direkam. contoh, `@a` akan menjalankan macros yang sudah disimpan di register `a`.
- `n@a` jalankan macros sebanyak n-kali
- `@@` mengulang macros terakhir

Contoh kasus: Hapus 3 baris berturut-turut lalu pindah ke bawah
1. `qa` mulai rekam di register `a`
2. `3dd` hapus 3 baris
3. `j` turun 1 baris
4. `q` selesai
5. Jalankan `@a` sebanyak yang dibutuhkan.

Macro bisa disimpan ke register `a` sampai `z`.

[back](./)
