# sed and wc

## How to find out how many lines a file contains without viewing it.

```
wc -l filename
```

## Delete the first n lines of a file without viewing it.

```
sed -i '1,100d' filename
```
