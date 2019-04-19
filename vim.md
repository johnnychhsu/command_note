### Vim

#### personal .vimrc
First run this command : 

```commandline
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Then Save my .vimrc with plugin.
After add plugin into .vimrc, type `:PluginInstall`.

Here is some plugin note:
1. Nerdtree : 
    1. map Nerdtree into Ctrl+O. Type Ctrl+O in Vim to view file tree.
    2. `:t` to open the file in a new tab.
2. surround : 
    If `"Hello World"`,
    1. Type directly in the editor `cs"'` to change the surrounding `"` into `'`. Change the symbol accordingly. 
    2. Type directly in the editor `ds"` to delete the surrounding `"`. 
    3. Suppose now is `Hello World`, type `ysiw]` (iw is a text subject) cursor on Hello, it becomes `[Hello] World`.

#### Instant markdown for Vim
With this [vim extension](https://github.com/suan/vim-instant-markdown), we can see our markdown immediately on a web browser.
