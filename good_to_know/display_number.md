# Add to number th, st, nd, rd

```
def ordinal(n)
  return "th" if (11..13).include? n%100
  case n%10
  when 1 then "st"
  when 2 then "nd"
  when 3 then "rd"
  else        "th"
  end
end
```
