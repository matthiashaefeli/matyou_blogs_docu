# Date and Time picker with jquery

I assume you already have jquery working on your app.
Copy the files ```jquery.datetimepicker.full.min.js``` and ```jquery.datetimepicker.css``` from https://github.com/xdan/datetimepicker into your app.

In the page where you add the datetime picker add in the head:
```
<%= javascript_include_tag 'jquery.datetimepicker.full.min.js'%>
<%= stylesheet_link_tag 'jquery.datetimepicker.css' %>
```
Then in the view add the input field into your form:
```
<%= text_field :entry, :date, :size=> 15 %>
```
On the bottom of the view file add the jquery command:
```
$('#entry_date').datetimepicker();
```
