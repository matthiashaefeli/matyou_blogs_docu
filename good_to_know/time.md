# What is the difference between Time and Date in ruby

Initialize a Time Object.
- with the current time
- with given numbers (format: year/month/day)
- using an Unix timestamp

```
2.7.0 :058 > Time.now
 => 2020-02-06 09:37:00.562723 -0700
2.7.0 :059 > Time.new(2020, 2, 6)
 => 2020-02-06 00:00:00 -0700
2.7.0 :060 > Time.at(1580972400)
 => 2020-02-06 00:00:00 -0700
```

You can ask a time object for its components:
```
2.7.0 :061 > time = Time.now
2.7.0 :062 > time
 => 2020-02-06 09:40:00.172427 -0700
2.7.0 :063 > time.year
 => 2020
2.7.0 :064 > time.month
 => 2
2.7.0 :065 > time.day
 => 6
2.7.0 :066 > time.hour
 => 9
2.7.0 :067 > time.min
 => 40
2.7.0 :068 > time.sec
 => 0
```
You can ask for a certain week day:
```
2.7.0 :076 > time.monday?
 => false
2.7.0 :077 > time.thursday?
 => true
```
The time object has a time zone associated with it:
```
2.7.0 :078 > time.zone
 => "MST"
2.7.0 :079 > Time.new.utc
 => 2020-02-06 16:47:21.983248 UTC
2.7.0 :080 > time.zone
 => "MST"
2.7.0 :081 > time = Time.new.utc
2.7.0 :082 > time.zone
 => "UTC"
```
You can format the time in any format you need:
```
2.7.0 :092 > time = Time.now
2.7.0 :093 > time.strftime('%d/%m/%Y')
 => "06/02/2020"
2.7.0 :094 > time.strftime('%k:%M')
 => " 9:51"
2.7.0 :095 > time.strftime('%I:%M %p')
 => "09:51 AM"
2.7.0 :096 > time.strftime('%A')
 => "Thursday"
2.7.0 :097 > time.strftime('%A of %B, %Y')
 => "Thursday of February, 2020"
```
The internal representation is in seconds. You can add seconds to the time:
```
2.7.0 :101 > time
 => 2020-02-06 09:51:40.367753 -0700
2.7.0 :102 > time + 3600
 => 2020-02-06 10:51:40.367753 -0700
```

Initialize a Date Object.
- with .new returns a negative date
- with the current date
```
2.7.0 :106 > Date.new
 => #<Date: -4712-01-01 ((0j,0s,0n),+0s,2299161j)>
2.7.0 :107 > Date.today
 => #<Date: 2020-02-06 ((2458886j,0s,0n),+0s,2299161j)>
```

You can ask a time object for its components:
```
2.7.0 :108 > date = Date.today
2.7.0 :109 > date
 => #<Date: 2020-02-06 ((2458886j,0s,0n),+0s,2299161j)>
2.7.0 :110 > date.day
 => 6
2.7.0 :111 > date.month
 => 2
2.7.0 :112 > date.year
 => 2020
```

You can add days:
```
2.7.0 :113 > date
 => #<Date: 2020-02-06 ((2458886j,0s,0n),+0s,2299161j)>
2.7.0 :114 > date + 1
 => #<Date: 2020-02-07 ((2458887j,0s,0n),+0s,2299161j)>
```
Date.parse will try to parse any string that looks like a date:
```
2.7.0 :128 > Date.parse('06/02/2020')
 => #<Date: 2020-02-06 ((2458886j,0s,0n),+0s,2299161j)>
2.7.0 :129 > Date.parse('february 6')
 => #<Date: 2020-02-06 ((2458886j,0s,0n),+0s,2299161j)>
2.7.0 :130 > Date.parse('may i have a beer please')
 => #<Date: 2020-05-01 ((2458971j,0s,0n),+0s,2299161j)>
```
