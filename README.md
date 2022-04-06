# vim-bundle

### Install Plugin Manager
```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

### .  
### .  
### .  

### make file
~/.vimrc
```
set nocompatible
filetype off

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'slim-template/vim-slim.git'
Plugin 'maciakl/vim-neatstatus'
call vundle#end()

call plug#begin('~/.vim/plugged')
Plug 'preservim/nerdtree'
Plug 'pangloss/vim-javascript'
Plug 'leafgarland/typescript-vim'
Plug 'peitalin/vim-jsx-typescript'
Plug 'mhartington/oceanic-next'
call plug#end()

" Backup files
set backupcopy=yes
set expandtab    " Turn tab into spaces
set number       " Turn on numbering of lines
set showmatch    " Show matching brackets.
set matchtime=5  " Bracket blinking.
set noshowmode   " Shows vim mode
" Set status line
set laststatus=2 " Always show status line.
" Match and search
set hlsearch    " highlight search
set ignorecase  " Do case in sensitive matching with
set smartcase   " be sensitive when there's a capital letter
set incsearch   " Search incrementally
" Color scheme
set t_Co=256
set termguicolors
colorscheme OceanicNext
" Set shell
set shell=/bin/zsh
" Test shortcuts
nmap <silent> t<C-n> :TestNearest<CR>
nmap <silent> t<C-f> :TestFile<CR>
nmap <silent> t<C-s> :TestSuite<CR>
nmap <silent> t<C-l> :TestLast<CR>
nmap <silent> t<C-g> :TestVisit<CR>
" Search shortcuts
nnoremap <silent> <C-z> :FZF<CR>
nnoremap <silent> <C-x> :Rg<CR>
" Fast comment shortcuts
noremap \ :Commentary<CR>
autocmd FileType ruby setlocal commentstring=#\ %s
" Save current buffer shortcuts
noremap  <silent> <C-w> :w<CR>
inoremap <silent> <C-w> <ESC>:w<CR>i
" Close current buffer shortcuts
noremap  <silent> <C-a> :q<CR>
inoremap <silent> <C-a> <ESC>:q<CR>
" Use ctrl+Left / Right to go between tabs
nnoremap <C-Left> :tabprevious<CR>
nnoremap <C-Right> :tabnext<CR>
" Enable mouse
set mouse=a
" Prev/next tab ctrl + left or right arrow (Remember to disable global mac os ctrl+ left or right key) 
map <C-Left> :tabprevious<CR>
map <C-Right> :tabnext<CR>
" Enable NerdTree when opening VIM on empty file input
autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
" Syntax highlight
autocmd BufEnter *.{js,jsx,ts,tsx} :syntax sync fromstart
autocmd BufLeave *.{js,jsx,ts,tsx} :syntax sync clear
" Fix identitation on filetypes
autocmd FileType javascriptreact setlocal ts=4 sts=4 sw=4 expandtab
autocmd FileType typescriptreact setlocal ts=4 sts=4 sw=4 expandtab
autocmd FileType javascript setlocal ts=4 sts=4 sw=4 expandtab
autocmd FileType typescript setlocal ts=4 sts=4 sw=4 expandtab
autocmd FileType conf setlocal ts=4 sts=4 sw=4 expandtab
autocmd FileType json setlocal ts=4 sts=4 sw=4 expandtab
```

### .  
### .  
### .  

### Install Plugin
```
vim

:PluginInstall
:PlugInstall
```


reference by [https://byteable.dev/using-vim-for-react-rails-node-development-80cc27bdd80b](https://byteable.dev/using-vim-for-react-rails-node-development-80cc27bdd80b)
