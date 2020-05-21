Hello, today I will tell you about React. In next 10-12 minutes I will try to explain the main aspect of React. So, agenda of my presentation is following:

What is react? React components. JSX. State & Props. And virtual Dom.

So, what is React? React is a JavaScript library for creating user interfaces. It was created by Facebook in 2013 in order to solve a number of problems associated with large-scale data-driven websites. React allows you to create complex User Interfaces from small and isolated pieces of code that are called “components”. React is used for the so-called Single Page Application. A single-page application is a site, all the actions in which take place on one page, without its full update.

**Components.**

In React, each block is called a component. Each component can contain smaller components, those in turn are even smaller and so on.
Components allow you to break the interface into independent parts, which are easy to think separately about. The main advantage of components is that they can be reused many times.

Usually, development starts with the main component that is called App, which contains the rest.

Conceptually, components are similar to JavaScript functions. They take data (called props) and return React elements that describe what should appear on the screen.

In React, components can be statefull or stateless, and functional or class components.

Stateless components (usually it is functional components) are functions that take properties and return a DOM element. Stateless components only know how to display the received data. They allow you to achieve simplicity of the code and greatly simplifies its testing.

To create a statefull component, you must inherit from the React.Component class. A statefull component should always call the base constructor with props.

The required component method is the render() method. What the render() method returns will be the result of the component. The result of the rendering cannot be several tags: if you want return several tags, they must be wrapped in some common tag.

**JSX.**

JSX is a separate technology from React, and using JSX is optional.

In most cases, JSX looks like ordinary HTML.
The essence of JSX is the following: HTML tags are correct JavaScript code and we can simply add them directly in the script without quoting it.

Each component has its own tag. Using this tag, you can insert the result of the component on the page.
The tag has the same name as the component class name. For example, we have the Card component, then the tag <Card /> corresponds to it.
Please note that this tag is capitalized and closes with a backslash.

After compilation, JSX expressions become regular JavaScript objects.
This means that you can use JSX inside conditional statements or loops, assign it to variables, accept as an argument, and return from functions. In general, you can do everything what you can do with a regular JavaScript object.

As I had already mentioned, pieces of HTML code can be written into variables. We can insert the value of this variable in any piece of HTML code by writing it in curly brackets. Inside curly brackets, you can not only insert variables, but also run any JavaScript code.

When you working with JSX, you should pay attention to following moments:
- In JSX is used className attribute instead of class-attribute.
- Style-attribute in JSX takes a javascript object as a value.
- We cannot use ‘if () {} else {}’ statement in JSX in curly brackets, instead we can use conditional (ternary) expressions.
- Camel-case is used for properties in JSX.

**State.**

The basic concept of React is state.

State is a property of the class component that is set in the constructor. The state stores the current state of the component in the form of an object with keys and values.

But what is included in the concept of the current state?

Firstly, it is data. For example, a component displays a list of user names on the screen. These names should initially be stored somewhere, usually in some sort of array. This array should be stored in state.

Secondly, it is current state of the component. For example: some block may be in the expanded or collapsed position. So, state also stores the state of this block: for example, true – when the block is expanded, and false – when it is collapsed.

The state is accessed through this.state.StateName.
However, changing the value of State directly is not possible. The constructor is the only place where you can assign the value of State directly.
For other cases, you should use special built-in method setState(). This method does not need to be created in our class - it inherits from the React.Component class and is available in any component by default.
If there are several values in the State, then in the setState()  method we pass only those that we want to change.

Each time State was changed, all changes are instantly displayed on the page. This behavior is called reactivity.
The important point is that the values from the State must be used when rendering. If some object is not used in the component rendering, there is no sense to save it in state.

**Props.**

Props are used to get data from the parent component to the child component. We can access them using props or this.props, depending on whether it is class or functional component. To get the child elements passed from above, you can use props.children or this.props.children.

Thus, the components allow us to make a separation: displaying data separately from receiving this data. Each component simply receives some data from the outside and displays it in the form we need. This is convenient and simplifies further support of our code.
A component declared as a function or class should never modify its Props.

Such functions are called “pure”. Because they do not change their arguments and always return the same result for the same arguments.
React is very flexible, but it has one strict rule: all React components should work as pure functions in relation to their Props.

State vs Props

So, now we know, that the component can have states and props. The states are the data of the component itself, and the props are the data transferred from the parent component. You can see the main differences mentioned above on this slide.

**Virtual DOM.**

Virtual DOM is representation of a real DOM. You can think about it like it is lightweight copy of real DOM.

Very often, when you work directly with real DOM, you update the DOM much more often than you have to. Inefficient updating is a serious problem for performance. So virtual DOM helps us to deal with it.

Instead of manipulating the browsers DOM directly, React creates a Virtual DOM in memory where it does all necessary manipulating, before making the changes in the browsers DOM. React finds out what changes have been made, and changes only what needs to be changed. This improve the performance a lot.

In addition to this, in order to increase productivity, as well as for convenience, React uses its own system of synthetic events. It also helps events to work the same in all browsers and solve the problem of browser incompatibility.


**Conclusion.**

Now, I hope, you know a little bit more about React and it will help you with creating React Apps. That is all I wanted to tell you. Thanks for watching. Goodbye.
