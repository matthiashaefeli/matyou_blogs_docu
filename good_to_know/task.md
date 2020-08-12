# Create a rake task with rails and heroku
I will use the example of cleaning a chat every day
Create a file called chat.rake in /lib/tasks
```
namespace :chat do
    task clear_history: :environment do
       oldest_chats = Chat.where("created_at < ?", 15.days.ago)
       for chat in oldest_chats
          chat.delete
       end
    end
end
```
Run code below from terminal
```
$ rake chat:clear_history
```
This should do what the method should do
On Heroku:
Add Heroku Scheduler

Add new job

Choose day, time etc and the command from above

and thats it !!