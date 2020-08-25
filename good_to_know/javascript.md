# Javascript function, method, and constructor

## function
This does exactly what it looks like: It calls the hello function and binds the username parameter to its given argument:

```
function hello(username) {
  return 'hello ' + username;
}
hello('Ralf Tats') // 'hello Ralf Tats'
```

## methods
Methods in JavaScript are nothing more than object properties that happen to be functions:

```
let obj = {
  hello: function() {
    return 'hello ' + this.username;
  },
  username: 'Ralf Tats'
};
obj.hello() // 'hello Ralf Tats'
```

Notice how hello refers to this to access the properties of obj.
What happens in a method call is that the call expression itself determines the binding of this, also known as the call's receiver.

## constructors

Constructors are just like methods and plain functions.
```
function User(name, password) {
  this.name = name;
  this.password = password;
}
let u = new User('Ralf', 'password')
u.name // Ralf
u.password // password
```
Unlike function calls and method calls, a constructor call passes a brand new object as the value of this, and impicitly returns the new object as its result. The constructor functions primary role is to initialize the object.


- Method call provide the object in which the method property is looked up as their receiver.
- Constructors are called with new and receive a fresh object as their receiver.