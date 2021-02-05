# How to get specific class names in Rails

first we have to load the class.
The example classes are in modules

```
Dir[Rails.root.to_s + '/app/module1/module2/*.rb].each { |file| load file }
```

then we can get the classnames

```
Module1::Module2.constants
```

This would return an array of symbols with the classnames

[:ThisIsTheFirstClass, :ThisIsTheSecondClass]
