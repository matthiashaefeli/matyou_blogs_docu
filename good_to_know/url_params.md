## How to extract URL params from a URL

I have different URL's and i need to extract the parameters.

Let's say we have this URL:
```
http://www.ups.com/something?param1=value1&param2=value2&param3=value3
```

There are different ways to do that.

-
```
url = 'http://www.ups.com/something?param1=value1&param2=value2&param3=value3'
query_params = URI(url).query
```
and then we parse the query_params
```
params = Rack::Utils.parse_query(query_params)
=> {"param1"=>"value1", "param2"=>"value2", "param3"=>"value3"}
```

-
```
url = 'http://www.ups.com/something?param1=value1&param2=value2&param3=value3'
query_params = URI(url).query
```
and parse with Common Gateway Interface
```
require 'cgi'
CGI::parse(query_params)
=> {"param1"=>["value1"], "param2"=>["value2"], "param3"=>["value3"]}
```

-
```
url = 'http://www.ups.com/something?param1=value1&param2=value2&param3=value3'
uri= URI(uri)
URI::decode_www_form(uri.query)
=> [["param1", "value1"], ["param2", "value2"], ["param3", "value3"]]
```

or as a hash:
```
Hash[URI::decode_www_form(uri.query)]
=> {"param1"=>"value1", "param2"=>"value2", "param3"=>"value3"}
```
-

```
require 'addressable/uri'
url = 'http://www.ups.com/something?param1=value1&param2=value2&param3=value3'
uri = Addressable::URI.parse(url)
=> #<Addressable::URI:0x3ffecc032770 URI:http://www.ups.com/something?param1=value1&param2=value2&param3=value3>
```
parse:

```
uri.query_values
=> {"param1"=>"value1", "param2"=>"value2", "param3"=>"value3"}
```



