# Rails hash with indifferent access

```
2.7.0 :001 > hash = ActiveSupport::HashWithIndifferentAccess.new(foo: 1, bar: 2)
2.7.0 :002 > hash
 => {"foo"=>1, "bar"=>2}
2.7.0 :003 > hash[:foo]
 => 1
2.7.0 :004 > hash['foo']
 => 1
```

```
2.7.0 :005 > hash = {foo: 1, bar: 2}
2.7.0 :006 > hash
 => {:foo=>1, :bar=>2}
2.7.0 :007 > hash[:foo]
 => 1
2.7.0 :008 > hash['foo']
 => nil
```
