One of the weird things in `vim` is that if you paste from clipboard register with `<c-r>+` it will add a newline at the end. This is not desirable behaviour. After searching through forums I realized that the best and simplest solution is a simple remap:
```
inoremap <c-v> <c-r>+<bs>
```
This remap pastes the clipboard content and then deletes the new line. Not elegant, but works!
