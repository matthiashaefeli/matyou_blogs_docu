# Kill and clean Sessions
Add to Gemfile
```
gem 'activerecord-session_store'
```
```
$ bundle install
```
Run the migration generator:
```
rails generate active_record:session_migration
```
Run the migration:
```
rails db:migrate
```
Add file session_store.rb
config/initializers/session_store.rb:

Add code below
```
Rails.application.config.session_store :active_record_store, :key => '_my_app_session'
```
Create a file called session.rake in /lib/tasks
Add code below
```
namespace :sessions do

    desc "Clear the sessions table"
    task :clear => [:environment, 'db:load_config'] do
       ActiveRecord::Base.connection.execute "TRUNCATE TABLE #{ActiveRecord::SessionStore::Session.table_name}"
    end
   
    desc "Trim old sessions from the table (default: > 30 days)"
    task :trim => [:environment, 'db:load_config'] do
       cutoff_period = (ENV['SESSION_DAYS_TRIM_THRESHOLD'] || 30).to_i.days.ago
       ActiveRecord::SessionStore::Session.
       where("updated_at < ?", cutoff_period).
       delete_all
    end
end
```
Run code below from terminal
```
$ rake session:clear_history $ rake session:trim $ rake session:create
```
This should do what the method should do
On Heroku:
Add Heroku Scheduler

Add new job

Choose day, time etc and the command from above

and thats it !!