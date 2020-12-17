# Ruby dig

```
2.7.0 :008 > hash = { people: { person: { first: { name: 'Jeff', last_name: 'Bo' } } } }
2.7.0 :009 > hash
 => {:people=>{:person=>{:first=>{:name=>"Jeff", :last_name=>"Bo"}}}}
2.7.0 :010 > hash.dig(:people, :person, :first)
 => {:name=>"Jeff", :last_name=>"Bo"}
2.7.0 :011 >
```
