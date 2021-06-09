# How to replace html with ajax and it runs the javascript scripts?

with the document.open .write and .close we run javascript after appending to the page

```
$.ajax({
  type: 'GET',
  url: url,
  data: {},
  success: function(response) {
    document.open();
    document.write(response);
    document.close();
  }
})
```
