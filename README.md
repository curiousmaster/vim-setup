# VIM SETUP
## The Classic Power Stack
### Recommended minimum stack:
* **vim-plug** (plugin manager)
* **coc-nvim** (LSP + completion)
* **pyright** (Python language server)
* **black** (formatter)
* **fzf.vim** (fuzzy file server)
* **vim-fugitive** (Git)

## Install Core Tools
'''
pip install black isort
npm install -g pyright
sudo apt install fzf
'''

## Minimal .vimrc IDE Setup
'''
" ----------------------------
" Basics
" ----------------------------
set number
set tabstop=4
set shiftwidth=4
set expandtab
set smartindent
set hidden
set nowrap
set cursorline

syntax on
filetype plugin indent on

" ----------------------------
" vim-plug
" ----------------------------
call plug#begin('~/.vim/plugged')

Plug 'neoclide/coc.nvim', {'branch': 'release'}
Plug 'junegunn/fzf'
Plug 'junegunn/fzf.vim'
Plug 'tpope/vim-fugitive'

call plug#end()

" ----------------------------
" Format on save (Python)
" ----------------------------
autocmd BufWritePre *.py silent! execute '!black %'

" ----------------------------
" Keybindings
" ----------------------------
nnoremap <leader>f :Files<CR>
nnoremap <leader>g :G<CR>
nnoremap <leader>r :!python3 %<CR>

'''
