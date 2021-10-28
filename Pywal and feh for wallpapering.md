Today after a bit of tweaking I learned how to setup wallpapers and color-schemes with `pywal` and `feh`.

I had little line in my `.xinitrc` to make `feh` randomly choose two pictures as wallpapers for my two monitors:
`feh --bg-scale --randomize ~/Pictures/wallpapers/* ~/Pictures/wallpapers/* &`

The `wal` command will choose the color palette according to the image you point it to. This image could be found in the `$HOME.fehbg` file. The only problem was that that file contained a long space-delimited list of wallpapers (because of me pointing `feh` to a directory). This is however easily solvable with `awk`.

Anyways, my end-result line (which I put in `zshrc`) is following:
`awk '{ print $4 }' $HOME/.fehbg | xargs wal -n -i`

So, the `awk` cmd is used for getting the 4th column (the name of the wallpaper for the first(main) monitor). Then I pipe it as an argument to the `wal` with the `-n` flag (which tells it that I already use another wallpaper-setter, so no need for setting the wallpaper, just extract the color palette info). 

