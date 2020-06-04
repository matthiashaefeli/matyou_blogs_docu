# SQL Time minus x days

Get the today time with:
```
GETDATE()
```

Store time minus 30 days in a varible:
```
declare @time date
set @time = DATEADD(DAY, -30, GETDATE())
```

Set time without hours and seconds:
```
set = @time = DATEADD(day, DATEDIFF(day, 0, GETDATE()), 0)
```

This technique is also extendable.

Yesterday:
```
DATEADD(day, DATEDIFF(day, 0, GETDATE()), -1)
```
Start of the month:
```
DATEADD(month, DATEDIFF(month, 0, GETDATE()), 0)
```
End of last month:
```
DATEADD(month, DATEDIFF(month, 0, GETDATE()), -1)
```
Start of next month:
```
DATEADD(month, DATEDIFF(month, 0, GETDATE()), 31)
```
