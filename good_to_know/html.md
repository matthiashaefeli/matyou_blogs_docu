# .html_save vs raw h to unescape html

if we have something like that:
```
@html_link = "<a href='#'>link</a>"
```

If we would use that in the view it would not work as a link.
So we can use .html_save, raw, or h like in the code below

```
<%= @html_link.html_save %>
```
html_safe actually "sets the string" as HTML Safe

```
<%= raw @html_link %>
<%== @html_link %> # is the same as above
```
raw is equivalent to calling to_s chained with html_safe on it

```
<%= h @html_link %>
```
h can only be used from within a controller or view, since it's from a helper. It will force the output to be escaped

The only difference between .html_save and raw:

```
"<a>Hello</a>".html_safe
#=> "<a>Hello</a>"

nil.html_safe
#=> NoMethodError: undefined method `html_safe' for nil:NilClass
```

```
raw("<a>Hello</a>")
#=> "<a>Hello</a>"

raw(nil)
#=> ""
```

