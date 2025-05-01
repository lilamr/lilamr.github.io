## Plugin
`vim ~/.vimrc` edit file `.vimrc`. tambahkan daftar plugin seperti dibawah ini:
```
call plug#begin('~/.vim/plugged')
Plug 'plasticboy/vim-markdown' " Plugin untuk syntax highlighting Markdown
call plug#end()
```
`:PlugInstall` jalankan perintah di dalam vim