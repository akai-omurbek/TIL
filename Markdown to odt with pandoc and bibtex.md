I've tried to use BetterBibTex plugin for Zotero, but for some reason it refuses to work for me. That's why I needed to set up another way to convert my .md files into .odt files. 

I've exported a library with Zotero (it can be betterbibtex export too), then got a csl file (I've had it from somewhere before), and voila. 

Only things remaining is use pandoc with the `--citeproc` option (it won't work otherwise):
```
pandoc --citeproc --bibliography=/path/to/file --csl=/path/to/csl file.md -o file.odt
```
This setup may seem a more of a hassle than using the BetterBibTex setup, but I want to learn more about `bibtex` files, do a bit of scripting, thus this setup might be for the best. Additionally, if I reconsider and fix Zotero problem, I can always switch in no time. 
