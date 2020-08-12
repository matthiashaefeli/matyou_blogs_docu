# Pry is my must Gem in every Rails application
In 2017 I finished the Dev Bootcamp in Austin TX

Always when we asked an instructor for help, his first question was: do you have the Gem Pry?

Now my first added Gem in a Rails project is Pry

Pry:
Pry is a powerful alternative to the standard IRB shell for Ruby

Add Pry to the Gemfile
```
gem 'pry'
```
To use Pry
You can add Pry wherever you want with

```
def do_something
  binding.pry
  ....
  ....
end
```    
Or in the view
```
<%= binding.pry %>
```
Then Check out the console where the rails server is running

```
    5: def do_something
=>  6:   binding.pry
    7:   ....
    8:   ....
    9: end
```

```
[1] pry(#<ChatsController>)>
```   
Now you have access to everything you need

If you are using the Pry in a loop, to see next step in the loop just type exit

and thats it !!