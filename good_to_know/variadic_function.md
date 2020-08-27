# Variadict function

A variadic function is a type of function which accepts a variable number of arguments


```
function average() {
  for (var i = 0, sum = 0, n = arguments.length, i++) {
    sum += arguments[i]
  }
  return sum/n
}
```

The function does not know how many arguments it will receive. se we just loop over the arguments.
