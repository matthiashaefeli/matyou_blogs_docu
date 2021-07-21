# Add env file to rails app

Craete a file config/my_env.yml and add variables

```
MY_FIRST_VARIABLE: 'first'
MY_SECOND_VARIABLE: 'second'
```

add my_env.yml file to .gitignore

```
/config/my_env.yml
```

Add Code below to config/application.rb file to set the environment variables

```
config.before_configuration do
  env_file = File.join(Rails.root, 'config', my_env.yml')
  YAML.load(File.open(env_file).each do |key, value|
    ENV[key.to_s] = value
  end if File.exists?(env_file)
end
```

to get the env variables where you need it access like:

```
my_first-variable: ENV['MY_FIRST_VARIABLE']
my_second_variable: ENV['MY_SECOND_VARIABLE']
```

Or with a default value:

```
my_first-variable: ENV.fetch('MY_FIRST_VARIABLE', default_value')
my_second_variable: ENV.fetch('MY_SECOND_VARIABLE', second_default_value)
```
