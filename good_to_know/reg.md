# Get everything before certain char with regex

We need everything before the #

```
2.7.2 :001 > 'this_is_a_test#and_we_do_not_need_this'.match(/^[^\#]*/)[0]
 => "this_is_a_test"
2.7.2 :002 >
```
