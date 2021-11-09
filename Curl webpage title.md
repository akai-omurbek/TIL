For some reason I had to write a CLI command to get a webpage title, I've decided to turn to Google, but couldn't find anything working for a while. Finally, with the help of [this post](https://stackoverflow.com/questions/3833088/extract-title-of-a-html-file-using-grep) I managed to put together this:
```
#!/bin/sh

curl "$1" 2>/dev/null | # curl site, STDOUT to devnull
grep "</title>" | #works better than <title>
# sed getting rid of title, tabs, newlines and replacing htmlisms
sed -E -e "s/<.?title>//g" \
  -e "s/\&#39;/\'/g" \
  -e "s/\&amp;/\&/g" \
  -e "s/\t//g" \
  -e "s/\n//g"
```
This one worked for the needs I have at the moment, but the `sed` part should be extended in the future to include all *htmlisms*. 
