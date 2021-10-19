# 💡 Motivation

A lot of people have been mapping `jk` or `kj` or `kk` to <kbd>ESC</kbd> in
order to escape insert mode quickly. However, when we press the first key in
these mappings, Vim/Nvim will wait for [`timeoutlen`](https://neovim.io/doc/user/options.html#'timeoutlen')
milliseconds before writing this char to buffer. The apparent lag caused by
this behaviour is annoying.

Better-escape.vim is created to help Vim/Nvim users escape insert mode quickly
using their customized key combinations, **without experiencing the lag**.

# 🚀 Quickstart

## Requirements

+ Neovim: 0.4.4 and above
+ Vim: 8.0 and above (not tested on Vim 7.4)

## Install

Use your favorite plugin manager to install it:

+ [packer.nvim](https://github.com/wbthomason/packer.nvim): `use {'jdhao/better-escape.vim'， event = 'InsertEnter'}`
+ [vim-plug](https://github.com/junegunn/vim-plug): `Plug 'jdhao/better-escape.vim'`
+ [dein](https://github.com/Shougo/dein.vim): `call dein#add('jdhao/better-escape.vim')`
+ [vim-packager](https://github.com/kristijanhusak/vim-packager): `call packager#add('jdhao/better-escape.vim')`
+ [minpac](https://github.com/k-takata/minpac): `call minpac#add('jdhao/better-escape.vim')`

## How to use?

This plugin works out of the box. The default shortcut for escaping insert mode
is `jk`, that is, pressing `j` first, then pressing `k` **quickly**, you will
leave insert mode.

# 🔧 Configuration

## How to change shortcut

If you want to use other shortcuts, you can customize via option `g:better_escape_shortcut`:

```vim
" use jj to escape insert mode.
let g:better_escape_shortcut = 'jj'
```

## Adjust time interval threshold

By default, the time interval threshold between pressing `j` and `k` is 150 ms.
That is, if the time interval between pressing `k` and `j` is above the
threshold, `jk` will be inserted literally. Otherwise, we assume you want to
leave insert mode. The threshold can be customized via option `g:better_escape_interval`:

```vim
" set time interval to 200 ms
let g:better_escape_interval = 200
```

## Using multiple shortcuts?

Some people may prefer to use multiple shortcuts. This is also supported:

```vim
# non-ASCII shortcuts are also supported for non-English keyboard.
let g:better_escape_shortcut = ['jk', 'jj', 'kj', 'лл']
```

# 📚 Documentation

See [`:h better-escape.txt`](doc/better-escape.txt).

# 📝 License

This plugin is released under the MIT License.

# ❤️  Similar projects

+ https://github.com/zhou13/vim-easyescape
+ https://github.com/max397574/better-escape.nvim (a lua re-implementation of this plugin)
