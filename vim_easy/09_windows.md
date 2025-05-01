## Windows
**Split windows**
- `:split` atau `:sp` split windows horizontal
- `:vsplit` atau `:vsp` split windows vertikal

- `Ctrl + w` lalu arah (`h/j/k/l`) untuk pindah antar jendela windows
- `Ctlr + w + w` berpindah-pindah windows

- `:new` horizontal split dengan file baru
- `:vnew` vertikal split dengan file baru

Keduanya akan membelah jendela sekarang menjadi dua **buffer kosong** (kalau tidak diikuti nama file).  

Kalau mau langsung buka file saat split:
- `:sp nama_file.py`
- `:vsp nama_file.py`

**Tab**
Kalau kamu ingin membuka **tab baru** dengan **file kosong** di Vim atau Neovim, perintahnya adalah:
- `:tabnew`

Atau jika mau langsung buat tab baru dengan nama file tertentu (misal file kosong baru):
- `:tabnew nama_file_baru.py`

Kalau mau cepat berpindah antar tab:
- `gt` pindah ke tab berikutnya
- `gT` pindah ke tab sebelumnya