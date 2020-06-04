# Ruby string group by same chars

This regex groups the chars by same chars
```
2.7.0 :012 > "aaaaaaabbbbbbbbcaaaaBBBBBDD".scan(/((.)\2*)/)
 => [["aaaaaaa", "a"], ["bbbbbbbb", "b"], ["c", "c"], ["aaaa", "a"], ["BBBBB", "B"], ["DD", "D"]]
2.7.0 :013 > "aaaaaaabbbbbbbbcaaaaBBBBBDD".scan(/((.)\2*)/).map(&:first)
 => ["aaaaaaa", "bbbbbbbb", "c", "aaaa", "BBBBB", "DD"]
2.7.0 :014 >
```

this example groups same chars together

```
2.7.0 :014 > "aaaaaaabbbbbbbbcaaaaBBBBBDD".chars.group_by(&:itself).values.map { |e| [e.join] }
 => [["aaaaaaaaaaa"], ["bbbbbbbb"], ["c"], ["BBBBB"], ["DD"]]
2.7.0 :015 >
```

this example does the same as above

```
2.7.0 :015 > "aaaaaaabbbbbbbbcaaaaBBBBBDD".chars.sort.slice_when { |a, b| a != b }.map { |element| element.join.split }
 => [["BBBBB"], ["DD"], ["aaaaaaaaaaa"], ["bbbbbbbb"], ["c"]]
2.7.0 :016 >
```
