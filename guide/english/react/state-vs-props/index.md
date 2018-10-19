---
title: State vs Props
---
## State vs Props

When we start working with React components, we frequently hear two terms. They are `state` and `props`. So, in this article we will explore what are those and how they differ.

## State:

* State is something that a component owns. It belongs to the particular component upon which it is defined.
For example, a person's age is a state of that person.
* State is mutable. But it can be changed only by the component that owns it. Just as I can only change my age, not anyone else.
* You can change a state by using `this.setState()`

See the below example to get an idea of state:

#### Person.js

```javascript
  import React from 'react';

  class Person extends React.Component{
    constructor(props) {
      super(props);
      this.state = {
        age:0
      this.incrementAge = this.incrementAge.bind(this)
    }

    incrementAge(){
      this.setState({
        age:this.state.age + 1;
      });
    }

    render(){
      return(
        <div>
          <label>My age is: {this.state.age}</label>
          <button onClick={this.incrementAge}>Grow me older !!<button>
        </div>
      );
    }
  }

  export default Person;
```
In the above example, `age` is the state of the `Person` component. 

## Props:

* Props are similar to method arguments. They are passed to a component where that component is used.
* Props is immutable. They are read-only.

See the below example to get an idea of Props:

#### Person.js

```javascript
  import React from 'react';

  class Person extends React.Component{
    render(){
      return(
        <div>
          <label>I am a {this.props.character} person.</label>
        </div>
      );
    }
  }

  export default Person;

  const person = <Person character = "good"></Person>
```

In the above example, `const person = <Person character = "good"></Person>`, we are passing the `character = "good"` prop to the `Person` component. This results in an output of "I am a good person" (and, in fact, I am).

There is lot more to learn on state and props. Many things can be learnt by actually diving into coding. So get your hands dirty by coding!

Reach me out on [twitter](https://twitter.com/getifyJr) if needed.

Happy Coding !!!
