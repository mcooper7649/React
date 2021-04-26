## React
--

(Code-Sandbox-REACT)[https://codesandbox.com]

- What is React?
    - A JavaScript Library for building user interfaces
        - A Frontend Framework

- Why?
    - To make it easier and faster to build build beautiful interfaces
    - React allows you to create components
        
- Components
    - You can put components inside other components
    - You can re-use the same component for quick creation of elements
    - Component trees help you visually understand the component heirarchy
    - Components can be called like html tags ``<MyHeader />``
        - We are essentially creating custom html tags
    - Components keep the code clean and modular

- Component Usefulness
    - Components load their own html/css/js files  
        - This allows the components to update and refresh individually vs the whole page
            - This makes the app loadfaster and be more interactive
            - This allows platforms to dynamically refresh their components so, things like notifications will pop up now without the need for a user to hit refresh.


### Introduction to JSX and Babel
---

(Completed-CodeSandbox)[https://codesandbox.io/s/condescending-brook-xk1cg?file=/public/index.html]

- Getting Started
    - Head over to codesandbox.io
    - Create a React BoilerPlate
        - Inside the body you will have a div with the id of "root"
        - a ``<script>`` tag linking your javascript   
            - This should be at the closing body tag
        - Thats IT, we will now create the rest of our code in the index.js and leave the html file alone

- Configuring the index.js
    - Add the latest dependencies for react and react-dom
    - import react and react-dom
        ```
        import React from "react";
        import ReactDOM from "react-dom";
        ```
- ReactDOM's structure 
    - ReactDOM.render(WHAT TO SHOW, WHERE TO SHOW IT)
    - ReactDOM.render(<h1>Hello World!</h1>, document.getElementById("root"))


- What is JSX?
    - React COMPILES JSX that is HTML passed through the body of JavaScript.
    - Inside REACT is a compiler called BABEL

- What is BABEL?
    - Babel converts modern code, es6, es7, etc and converts it to older browser compatible code.
    - Babel converts JSX into plain JavaScript
        - If you go to babeljs.io you can see how babel converts the jsx into javascript via their web based compiler

- Importing
    - Import is an es6 release of how we import modules vs declaring vars
        - Old Style of Import
        ```Var React = require("react");```
        ```Var ReactDOM = require("react-dom)```
        - New Style of Import
        ```import React from "react"```
        ```import ReactDOM from "react-dom";```
    - This makes the dependencies more modular
    - This also makes the code organized

- The Render Method
    - ReactDom.render() 
        - It can only render one tag
            - Wrap your code in a DIV to render all your tags as one!

- React CHALLENGE CodeSandbox
    - Create a react app from Scratch
        - It should have an h1
        - It should display an unordered list
        - It should contain 3 list elements
    - https://codesandbox.io/s/blue-wood-6zz4p?file=/src/index.js:0-248

```
import React from "react";
import ReactDOM from "react-dom";

ReactDOM.render(
  <div>
    <h1>This is my heading</h1>
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>

  </div>, document.getElementById("root")
)
```


### What else can JSX do?
---

(Sandbox)[https://codesandbox.io/s/javascript-expressions-in-jsx-practice-forked-wl6x9?file=/src/index.js:366-402]

- JSX is HTML that is injected into the JavaScript code
    - It can also inject JS inside the HTML too 
        - The code needs to be wrapped in {code}
    - ANY JS EXPRESSION can be added using the curly braces in JSX
    - JSX curly braces cannot render STATEMENTS, like IF,ELSEIF

- Using CodeSandbox
    - Declare a number for the var "Lucky Number"
    - Call your var using JSX, see if you can get it to render
    ```
    let luckyNumber = 7;

    ReactDOM.render(
    <div>
        <h1>Hello Michael</h1>
        <p>Your Lucky Number is {luckyNumber}</p>
    </div>,
    document.getElementById("root")
    )
    ```

- Template Literals and JSX
    - in ES6 we learned about template literals which allow you to use backticks `code` 
    - if Combined with JSX we can interpolate multiple JSX Vars using $ dollar sign
        `` <h1>Hello {`${fName} ${lName}`}</h1> ``


### JSX PRACTICE
---
(Sandbox)[https://codesandbox.io/s/javascript-expressions-in-jsx-practice-forked-wkxii?file=/src/index.js:0-207]
Challenge - 
        //Create a react app from scratch.
        //It should display 2 paragraph HTML elements.
        //The paragraphs should say:
        //Created by YOURNAME.
        //Copyright CURRENTYEAR.
        //E.g.
        //Created by Angela Yu.
        //Copyright 2019.

```
import React from "react";
import ReactDOM from "react-dom";

let fName = "Michael";
let lName = "Cooper";
let d = new Date();
let date = d.getFullYear();

ReactDOM.render(
  <div>
    <p>Created by {`${fName} ${lName}`}</p>
    <p>Copyright {date}</p>
  </div>,
  document.getElementById("root")
);
```