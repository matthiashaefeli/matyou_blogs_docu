# How to kill a running rails server

If the rails server was running on localhost:3000

```
$ sudo lsof -i :3000
```
If you get no output with sudo lsof, try this:
```
ps aux | grep rails
```

This can give you something like that:
```
COMMAND     PID USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
...
...
ruby      19267 user   14u  IPv4 0x117d47d17c069c81      0t0  TCP *:hbci (LISTEN)
ruby      19267 user   29u  IPv4 0x117d47d174a62321      0t0  TCP localhost:hbci->localhost:52559 (ESTABLISHED)
ruby      19267 user   33u  IPv4 0x117d47d17d940f41      0t0  TCP localhost:hbci->localhost:52631 (CLOSE_WAIT)
ruby      19267 user   34u  IPv4 0x117d47d17c4b1f41      0t0  TCP localhost:hbci->localhost:52577 (ESTABLISHED)
ruby      19267 user   35u  IPv4 0x117d47d17e042f41      0t0  TCP localhost:hbci->localhost:52777 (CLOSE_WAIT)
ruby      19267 user   42u  IPv4 0x117d47d17dcb05e1      0t0  TCP localhost:hbci->localhost:52787 (CLOSE_WAIT)
ruby      19267 user   43u  IPv4 0x117d47d17c097f41      0t0  TCP localhost:hbci->localhost:53050 (CLOSE_WAIT)
ruby      19267 user   45u  IPv4 0x117d47d173b64c81      0t0  TCP localhost:hbci->localhost:52464 (CLOSE_WAIT)
ruby      19267 user   46u  IPv4 0x117d47d17c4b15e1      0t0  TCP localhost:hbci->localhost:52176 (ESTABLISHED)
```
We can see that the server has the PID number 19267

Run from the console: kill -9 {PID number}. In this case see code below

```
$ kill -9 19267
```

Now you can see something like this

```
........
[1]+  Killed: 9               rails s
```

Run Rails server again
```
$ rails s
```

