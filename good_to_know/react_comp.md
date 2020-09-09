# React functional Component / Clase base Component


A functional component is just a plain JavaScript function which accepts props as an argument and returns a React element.

```
import React from 'react';

const App = () => {
  <section>
    <p>This is a functional component</p>
  </section>
}
```

A class component requires you to extend from React.Component and create a render function which returns a React element.

```
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <section>
        <p>This is a class based component</p>
      </section>
    )
  }
}
```


If you need a state in your component you will either need to create a class component or you lift the state up to the parent component and pass it down the functional component via props.


Why would i use functional components?

- Functional component are much easier to read and test because they are plain JavaScript functions

- less code

- They help you to use best practices. It will get easier to separate container and presentational components because you need to think more about your component’s state if you don’t have access to setState() in your component

- The React team mentioned that there may be a performance boost for functional component in future React versions

