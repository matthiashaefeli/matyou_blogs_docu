# Current user with rails without device

Add following code to application_controller:
```
  helper_method :current_user

  private

  def current_user
  @current_user ||= User.find(session[:user_id]) if session[:user_id]
  end
```

