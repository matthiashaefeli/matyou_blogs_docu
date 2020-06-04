# Define layout for controller in rails

How to set a specific layout for a specific controller in rails.

In the controller class:
```
class ItemsController < ApplicationController
  layout 'admin'

  #controller methods
end
```
