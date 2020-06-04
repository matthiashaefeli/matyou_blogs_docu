# Rails, How to redirect after sign in 

in app/controllers/application_controller.rb

```
def after_sign_in_path_for(resource)
  stored_location_for(resourse) || welcome_path
end
```
