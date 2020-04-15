source $VIMRUNTIME/vimrc_example.vim

set diffexpr=MyDiff()
function MyDiff()
  let opt = '-a --binary '
  if &diffopt =~ 'icase' | let opt = opt . '-i ' | endif
  if &diffopt =~ 'iwhite' | let opt = opt . '-b ' | endif
  let arg1 = v:fname_in
  if arg1 =~ ' ' | let arg1 = '"' . arg1 . '"' | endif
  let arg1 = substitute(arg1, '!', '\!', 'g')
  let arg2 = v:fname_new
  if arg2 =~ ' ' | let arg2 = '"' . arg2 . '"' | endif
  let arg2 = substitute(arg2, '!', '\!', 'g')
  let arg3 = v:fname_out
  if arg3 =~ ' ' | let arg3 = '"' . arg3 . '"' | endif
  let arg3 = substitute(arg3, '!', '\!', 'g')
  if $VIMRUNTIME =~ ' '
    if &sh =~ '\<cmd'
      if empty(&shellxquote)
        let l:shxq_sav = ''
        set shellxquote&
      endif
      let cmd = '"' . $VIMRUNTIME . '\diff"'
    else
      let cmd = substitute($VIMRUNTIME, ' ', '" ', '') . '\diff"'
    endif
  else
    let cmd = $VIMRUNTIME . '\diff'
  endif
  let cmd = substitute(cmd, '!', '\!', 'g')
  silent execute '!' . cmd . ' ' . opt . arg1 . ' ' . arg2 . ' > ' . arg3
  if exists('l:shxq_sav')
    let &shellxquote=l:shxq_sav
  endif
endfunction

"Syntax Highlighting
syntax enable
set t_Co=256

"Colorscheme
colorscheme dracula

"Line Numbers
set number

"Font
if has('gui_running')
	set guifont=DejaVu_Sans_Mono:h14
endif

"Working Directory
set autochdir

"Info Line
set laststatus=2

"Spellcheck
set spell
set spelllang=de,en_us

"Column to see how long lines are
set colorcolumn=80

"Plugins
call plug#begin('C:\Program\ Files\ (x86)\Vim\vimfiles\plugged')
	"Plug 'scrooloose/nerdtree'
	Plug 'itchyny/lightline.vim'
	Plug 'reedes/vim-colors-pencil'
	Plug 'morhetz/gruvbox'
	Plug 'jnurmine/Zenburn'
	Plug 'sjl/badwolf'
call plug#end()

colorscheme pencil
