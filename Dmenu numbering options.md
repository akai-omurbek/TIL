I was tinkering with the new clipboard manager I got - `greenclip`. It is nice, can use both `rofi` and `dmenu`. But as soon as I started using it I remembered why I didn't utilize such managers in the first place. They don't number the options. Oftentimes selecting in `dmenu` with numbered options is much much faster than trying to fuzzy match your desired selection.

So I tinkered a bit and got a good way of automatically numbering options given to dmenu and then getting rid of the numbers after choosing:

1. Pipe whatever you want to give to `dmenu` to `nl -w2 -s'. '`. It enumerates the lines, leaves two holder spaces for numbers and then puts some sort of a separator, in my case `.`. 

2.  Pipe the dmenu output to `sed E 's/^[0-9]*\. //g'`. This command gets rid of any number of numbers before a dot and space - i.e. basically restoring the pristine form of our selection. 

In my case, the whole command that I've bound looks like this:
```
greenclip print | sed '/^$/d' | nl -w2 -s'. ' | dmenu -i -l 20 -p "Choose a selection: " | sed -E 's/^[0-9]*\. //g'
```
It might seem like a hassle, but for my specific case it is a lifesaver. 
