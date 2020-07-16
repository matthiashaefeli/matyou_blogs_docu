# Rails encrypted file with secretes

Open credential file with:

```
EDITOR='code --wait' rails credentials:edit
```

And this is how you get the value from credentials:

```
Rails.application.credentails.aws[:secrete_access_key]
```

Rails 6 Specify and manage credentials file for each environment

The credentials command supports passing an --environment option to create an environment specific override file with variables. That override will take precedence over the global config/credentials.yml.env file when running in that environment.

```
rails credentials:edit --environment development
```
