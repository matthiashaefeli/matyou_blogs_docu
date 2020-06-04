# Make your gmail username and passoword available as ENV['']

Create a file /config/gmail.yml:
```
MAIL_USERNAME: 'my_user_name'
MAIL_PASSWORD: 'my_password'
```
Add the created yml to .gitignore

```
/config/gmail.yml
```

Add code below to config/application.rb to have access to the yml file and sets environment
variables from gmail.yml:

```
config.before_configuration do
  env_file = File.join(Rails.root, 'config', 'gmail.yml')
  YAML.load(File.open(env_file)).each do |key, value|
    ENV[key.to_s] = value
  end if File.exists?(env_file)
end
```
And now you have access to the varibles like:

```
user_name: ENV['MAIL_USERNAME']
password: ENV['MAIL_PASSWORD']
```
