# Ruby's cover
```
[1] pry(main)> (Date.yesterday..Date.tomorrow).cover?(Date.today)
=> true
[2] pry(main)> (Time.now..Time.now+4).cover?(Time.now)
=> true
[3] pry(main)>
```