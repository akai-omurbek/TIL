In vim (or nvim) you can execute multiple Ex commands in one line by using the `|` separator. Binding two commands in `vimrc` is also possible by replacing it with `<bar>` :
```
nnoremap <leader>*key* :ExCommand <bar> :ExCommand <cr>
``` 


