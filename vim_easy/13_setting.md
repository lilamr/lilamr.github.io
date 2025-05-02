## Setting
- `:set number` atau `:set nu` menampilkan nomor baris
- `:set nonumber` atau `:set nonu` menonaktifkan tampilan nomor baris

- `:syntax on` mengaktifkan syntax highlight misanya pada file berekstensi `.md` atau `.py` atau file bahasa pemrograman lainnya

setting yang dilakukan di dalam vim hanya akan aktif pada sesi itu saja. agar permanen bisa disimpan pada file `.vimrc`
- `vim ~/.vimrc`

tambahkan baris misalnya:

```
set number            " Tampilkan nomor baris
syntax on             " Aktifkan syntax highlighting
set tabstop=4         " Lebar tab
set expandtab         " Gunakan spasi daripada tab
set shiftwidth=4      " Indentasi saat auto indent
set clipboard=unnamedplus " Pakai clipboard OS
```

[back](./)
