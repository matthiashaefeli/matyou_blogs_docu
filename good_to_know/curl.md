# Curl command and redirection

If you have a curl command like that:

```
curl https://mydomain.com/do_something
```

On the page do_something redirects to another path.

In curl's tradition of only doing the basics unless you tell it differently, it does not follow HTTP redirects by default.

Use the -L, --location to tell it to do that.

```
curl -L https://mydomain.com/do_something
```

When following redirects is enabled, curl will follow up to 50 redirects by default. There's a maximum limit mostly to avoid the risk of getting caught in endless loops. If 50 is not sufficient for you, you can change the maximum number of redirects to follow with the --max-redirs option.