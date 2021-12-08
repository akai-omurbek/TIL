One of the things that I keep forgetting in my `Linux` setup is updating python apps installed with `pip`. As it turns out there is no built-in command or flag to do that (in bulk). So I've found a simple pipey solution:
```
pip3 list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip3 install -U
```
It would be a good idea to check the outdated apps list first. If there are apps you no longer want, you can tinker with the `grep` part of this one-liner. 
