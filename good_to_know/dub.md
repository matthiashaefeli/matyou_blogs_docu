# Ruby .dup vs .clone

In Ruby we can copy an array with .dup or .clone

Here is the difference of .dup and .clone:

```
2.7.2 :001 > a = [1,2,3,4].freeze
 => [1, 2, 3, 4]
2.7.2 :002 > a << 5
Traceback (most recent call last):
        4: from /Users/matyou/.rbenv/versions/2.7.2/bin/irb:23:in `<main>'
        3: from /Users/matyou/.rbenv/versions/2.7.2/bin/irb:23:in `load'
        2: from /Users/matyou/.rbenv/versions/2.7.2/lib/ruby/gems/2.7.0/gems/irb-1.2.6/exe/irb:11:in `<top (required)>'
        1: from (irb):2
FrozenError (can't modify frozen Array: [1, 2, 3, 4])
2.7.2 :003 > a.frozen?
 => true
2.7.2 :004 > b = a.clone
 => [1, 2, 3, 4]
2.7.2 :005 > b << 5
Traceback (most recent call last):
        4: from /Users/matyou/.rbenv/versions/2.7.2/bin/irb:23:in `<main>'
        3: from /Users/matyou/.rbenv/versions/2.7.2/bin/irb:23:in `load'
        2: from /Users/matyou/.rbenv/versions/2.7.2/lib/ruby/gems/2.7.0/gems/irb-1.2.6/exe/irb:11:in `<top (required)>'
        1: from (irb):5
FrozenError (can't modify frozen Array: [1, 2, 3, 4])
2.7.2 :006 > b.frozen?
 => true
2.7.2 :007 > c = a.dup
 => [1, 2, 3, 4]
2.7.2 :008 > c << 5
 => [1, 2, 3, 4, 5]
2.7.2 :009 > c.frozen?
 => false
```

