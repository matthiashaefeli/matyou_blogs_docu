# Rspec test with Ajax in controller
Do you have to test a controller with xhr request?

This is an example of my controller

```
def create
  if request.xhr?
  .....
  .....
end
```    
My rspec
Add xhr: true to test

```
it "creates a ........" do 
  post :create, xhr: true, params {...........}
  expect(........).to eq ...
end
```    
and thats it !!