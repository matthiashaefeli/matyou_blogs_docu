# Tests and devise login

If you have a rails app with login functions, in some point you need to write tests that logs the user in before 
you can do other tests.

The devise Docs have a good solution:
```
RSpec.configure do |config|
  config.include Warden::Test::Helpers
end
```
Add this to spec/rails_helper

And then in any place you need to login just do:
```
login_as(FactoryBot.create(:user))
```

