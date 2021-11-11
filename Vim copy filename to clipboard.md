If for some reason you need to copy the filename to your clipboard to use in other applications or scripts, modify and use this line in your `vimrc`:

```
nnoremap <silent> <leader>yy :let @+=expand("%:p")<CR>
```

