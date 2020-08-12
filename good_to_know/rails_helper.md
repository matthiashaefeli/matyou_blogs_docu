# Helper for controllers in Rails
Keep your Rails controllers skinny!!

Yeahh, but how?

Create the folder 'services' in the app folder.

Create a new file in the folder.

Example: user_service.rb

Add to the file code below.
```
module ServiceUser

end
```    
Add your method in the file.

In the controller include the service like below and call your method where you want.
```
class WelcomeController < ApplicationController
  include ServiceUser

  ....
  ....
  ....

end
```  
and thats it !!