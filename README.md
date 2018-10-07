# React Questions

### What is the Virtual DOM and what does React use it for?

The Virtual DOM is an abstraction of the DOM where corresponding properties are copied to a Javascript object. The Virtual DOM is much lighter than the actual DOM and is quicker to update. React (also Vue.js) uses the Virtual DOM to make comparisons between the Virtual DOM and the DOM to determine if its necessary to update the DOM therefore preventing unnecessary updates to the actual DOM.

### Why does React require the key property to be specified for certain components?

In React, the key property is used as the index of the specified component, further defining the component-to-DOM Element relation.  It is important the key always remains unique. Without the key property your React app could suffer from performance issues due to unnecessary re-renders.

### What's wrong with the ReactJS code below?
#### this.setState({ score: this.state.score - 1 })

this.state is always equal to the state last rendered and should not be trusted to hold the correct immediate state. It is best to use the prevState arg passed by this.setState. Ex. this.setState((prevState) => {})

### What is a higher order component? Provide some examples.

Higher order components are a technique to reuse component logic without repeating code. Components that share same functionality can be extended from a higher order component to create composition and reusable code. One example is using a high order component to manage users authentication state and sharing that functionality among other components without having to repeat code.

### What is the difference between a presentational and a container component?

Most often, React high order components are used to separate presentational components from container components.

### In a React/Redux application, where do you make API requests to the backend?

In a React/Redux application where state functionality is separated in actions, reducers and views, the most appropriate place to make API requests would be in an action.

### Why is immutability important in React/Redux applications?

### Describe some strategies to improve the performance of React components.

Prevent unnecessary rerenders. Make sure children components are given a proper index.

### Describe some strategies to speed up webpack build times during development and production.

### Describe some tools, strategies and plugins to make webpack builds smaller.

### What is the purpose of the yarn.lock and package-lock.json files?

In order to get consistent installs across machines, Yarn and NPM need more information than the dependencies you configure in your package.json. Yarn / NPM needs to store exactly which versions of each dependency were installed.

### What happens if you don't handle a rejected promise in NodeJs? How can you debug this issue?

(node:48446) UnhandledPromiseRejectionWarning: Unhandled promise rejection. This error originated either by throwing inside of an async function without a catch block, or by rejecting a promise which was not handled with .catch(). (rejection id: 1)
(node:48446) [DEP0018] DeprecationWarning: Unhandled promise rejections are deprecated. In the future, promise rejections that are not handled will terminate the Node.js process with a non-zero exit code.

To debug unhandled rejections you can create a listener using `process.on('unhandledRejection')` to observer unhandled rejections.

• Always handle promise rejections. Listen to unhandled rejection events for crash reporting. And always use errors to reject promises in order to get stack traces!
• Always handle the error event for streams!
• Wrap JSON.parse() and any Sync() function in a try-catch block or inside a Promise. Well, in general any function that can throw errors.

### What happens if you don't handle the 'error' event in a NodeJs stream?

### Can JSON.parse() crash your application?

JSON.parse() should be wrapped in a try-catch block or inside a Promise to prevent your app from crashing. If the input string passed to the JSON.parse() function is not proper JSON the output will throw an error.

### Desribe a way to handle a CPU-intensive task in NodeJs.

Node.js is single-threaded and therefore can pose a problem when running CPU-intensive tasks. To handle CPU-intensive tasks, Node has the ability to spawn multiple child processes by setting up a queue and a pool of workers.

### What happens when you invoke the following function?
#### async function() { return "hello" }

Async function generates a function that returns a promise.

function () { return new Promise(r => r("hello")) }

### How do you evaluate two promises in parallel in an async function?

### What are the main differences between a regular function and an arrow function?
