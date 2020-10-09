# How to send text message from sql server

```
send text by sql example

USE [msdb]
GO
EXEC msdb.dbo.sp_send_dbmail
@recipients = “1235550000@vtext.com”,
@subject = “Test SMS”,
@body = “This is only a test”
GO
```