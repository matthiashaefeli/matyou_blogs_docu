# convert JSON object to ruby hash

If we have a json response from a API

```
res = JSON.parse(response.body)
res.deep_symbolize_keys
```
