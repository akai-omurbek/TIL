For some reason, `nitrogen` refuses to work on my laptop. So I started looking for alternatives. Turns out, `feh`- a small image-viewing utility can do the job as well.

Setting the background is possible with a simple command:  
`feh --bg-scale /path/to/image.file`  
The dual-monitor setup can be managed as well:
`feh --bg-scale /path/to/image.file /path/to/image/for/second/monitor/`  
The setup will be saved to the `~/.fehbg` file, which you can initiate in `.xinitrc` for example. If you rather use a custom script, you can disable the creation of the file by `--no-fehbg` flag.  

Furthermore, one can combine the powers of `feh` and `sxiv|nsxiv` to get interactive wallpaper choices as in Windows. To do this simply put the following code in the `~/.config/nsxiv/exec/key-handler`:
``#!/bin/sh
case "$1" in
"w") while read file; do feh --bg-scale "$file"; done;;
esac`




