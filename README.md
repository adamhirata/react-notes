# React Notes

Before talking about **React**:

- Have you started a React project already?
- Have you built a website before? (knowledge of html/css/js)
- Is this for a mobile app?
- React relies on Node.js
  - Node is a JavaScript runtime environment/compiler for building full-size JavaScript projects
  - npm (node package manager) helps us build and run projects, including react projects
  - Pros: frameworks running on Node make development much easier + good documentation
  - Cons: Node projects can take up a lot of space and may not be optimal for older systems

React is a framework on top of Node that makes it easier to make front-ends for websites. Makes it easier by:

1. Consolidating html/css/js all into just javascript
2. Making web development into an object oriented programming approach
   - You create reusable React Components that can be easily refactored into many parts of a website

## Starting a React Project

First, ensure node is installed and navigate to the folder which you want to create the React App within. Open terminal by typing 'cmd' in the navigation bar:

![](https://example.com/your-image.png)

```sh
npx create-react-app app-name
```

```sh
cd app-name
```

```sh
npm start
// [!] Use this command whenever you want to start working on your react application
```

Wait for the application to show in your browser and start coding.

## App.js

A react app can be broken down into it's different components. The very top-level component is App.js, without it you have no application. Any component you create and render to the screen ultimately is a child component of App.js. I typically start a React App by figuring out what screens I need to include in the application and begin making components for them. For example, the home screen of my React website might be a component, and I have a button component referenced in my HomeScreen component. A hierarchy is formed:

- App.js (top-level component)
- HomeScreen.js (child component of App.js)
- Button.js (child component of HomeScreen.js)

## Typical anatomy of a Component

Component.js:

```js
// import statements are put at the top of the document, example
// shown imports css file (styles.css) from the same sub-folder
// tailwind would probably need to be imported if you use tailwind
import "./styles.css";
import OtherComponent from "./modules/OtherComponent.js";
import { useState, useEffect } from "react";

// note that a component is actually just a javascript function in modern React
export default function Component(props) {
  // props are values passed down from parent components and
  // should be declared as variables if you want to use them
  const [prop1, prop2, etc] = [props.prop1, props.prop2, props.etc];
  // can also be declared individually with const or let or var
  const prop3 = props.prop3;

  // useState and useEffect are the two most commonly used built-in react functions
  // which you will probably use in a lot of components.
  //  useState allows you to update data that is rendered by a component
  // useEffect allows you to trigger a block of code when a component is re-rendered or when a state changes
  // Example usage:
  const [stateName, setStateName] = useState(); // Documentation: https://reactjs.org/docs/hooks-state.html
  useEffect(() => {
    // Put code here
  }, []); // Documentation: https://reactjs.org/docs/hooks-effect.html

  // the return statement is where you put html + other React components that are
  // shown on screen when the component is rendered
  return (
    <div>
      <OtherComponent prop1={prop1} prop2={prop2} />
    </div>
  );
}
```

Without Comments:

```js
import "./styles.css";
import OtherComponent from "./modules/OtherComponent.js";
import { useState, useEffect } from "react";

export default function Component(props) {
  const [prop1, prop2, etc] = [props.prop1, props.prop2, props.etc];
  const prop3 = props.prop3;

  const [stateName, setStateName] = useState();
  useEffect(() => {
    // Put code here
  }, []);

  return (
    <div>
      <OtherComponent prop1={prop1} prop2={prop2} />
    </div>
  );
}
```

Example problem: create two components in same js file, one parent and one child. The child is a button which increments a value in the parent component

Material UI
useEffect
useState
VS Code
prettier + other extensions
