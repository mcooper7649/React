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


### STYLING in REACT 
---

- JSX renders down to javaScript so when you add the class attribute to your html it gives an error.
    - In JS you can declare the attribute className, like we seen in our jQuery/DOM modules

- Inside the index.html we should update the script tags type attribute from "text/javascript" to "text/JSX"
```
    <script src="../src/index.js" type="text/javascript"></script>
    <script src="../src/index.js" type="text/JSX"></script>
```
- Attributes for HTML in REACT will always need to be in camelCase, for example contentEditable="true".  


### STYLING Challenge
---
(sandbox-challenge)[https://codesandbox.io/s/funny-merkle-fy4e8]
1. Find 3 images from Google and add to your index.js
2. Using classes make the dimensions of the images the same size.


### Properties in JSX
---

1. Properties, such as <h1 style="color:red"> will not render in JSX, as properties need to be passed as objects
    - Objects are just { key:value} so <h1 style={color:red}> is how the property needs to be passed in jsx
        - commas will seperate any additional properties in the object unlike the ; in traditional html
    - Because JSX ALREADY needs {curlybraces} to declare JS then you need to call another object for attributes you will get DOUBLE curly braces
        - <h1 style = {{color: "red"}}>Hello World</h1>

2. React recommends using CSS stylesheets over inline styling? So why would we need to use it?
    - Inline Styles allow for styles to be more dynamic for say user interactions or events.
    
        
3. When setting properties, unlike CSS, your value needs to be a string, even if its a number, truthy falsy, border, etc.



### React Styling Challenge 2
---

(codesandbox) [https://codesandbox.io/s/react-styling-practice-forked-kxtnm?file=/src/index.js]

//Create a React app from scratch.
//Show a single h1 that says "Good morning" if between midnight and 12PM.
//or "Good Afternoon" if between 12PM and 6PM.
//or "Good evening" if between 6PM and midnight.
//Apply the "heading" style in the styles.css
//Dynamically change the color of the h1 using inline css styles.
//Morning = red, Afternoon = green, Night = blue.


```
import React from "react";
import ReactDOM from "react-dom";

let date = new Date();
let time = date.getHours();
console.log(time);
let greeting = "";

const customStyle = {
  color: ""
};

if (time <= 12) {
  greeting = "Good morning";
  customStyle.color = "red";
} else if (time > 12 && time < 18) {
  greeting = "Good Afternoon";
  customStyle.color = "green";
} else {
  greeting = "Good evening";
  customStyle.color = "blue";
}

ReactDOM.render(
  <div>
    <h1 className="heading" style={customStyle}>
      {greeting}
    </h1>
  </div>,
  document.getElementById("root")
);
```

### React Components
---

(codesandbox)[https://codesandbox.io/s/elated-meadow-smxwt?file=/src/components/App.jsx]

- Creating components in React allows for your code to be more easily understood and modular. 
- When creating a component in react, were essentially just creating a function we can recall at a later time.
    - Use Pascal case, aka Capital case first letter when creating your components
    - React needs pascal case to interpret

- We can create these functions as seperate files with a .jsx extension.
    - make sure to import React from 'react" at the top of each component.
    - using es6 export we want to export our components
        - export default Heading or Footer or whatever the name of the function without () so it doesn't execute immediately

- Import our component back into a our index.js file to complete the connection
    - import Heading from "./Heading"

- APP is a common component people create to begin modularizing their project.
    - Replacing our <div> tags, we would add the <App /> to our ReactDOM.render()
    - Make sure to import the APP to our injdex.js file too


index.js
```
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("root"));
```

App.jsx
```
import React from "react";
import Heading from "./Heading";
import List from "./List";

function App() {
  return (
    <div>
      <Heading />
      <List />
    </div>
  );
}

export default App;
```



## ES6 IMPORT/EXPORT MODULES
--

- In order to understand how the import and export modules work we need to take a look at es6 JavaScript to understand it better

- Importing allows for us to import functionality to our application while keeping the code clean and simple
    - Example: import PI, {doublePi, triplePi} from "./math.js"
    - Importing vs Requiring
        - importing is only about 80% compatible as it is es6 code
            - without Reacts Babel importing would only hit 80%
            - When working with node, when in doubt about compatibility, use require

- Exporting allows us to export function, variables or other chunks of code using a couple export options
    - Default lets export one file as the default file exported and can be imported using a random variable name, if needed
        - export default defaultFunctionName
    - Export with curly braces lets you specify function names you want to export and can be imported using only those names
        - export {secondFunctionName, tripleFunctionName }

- Importing EVERYTHING as an object
    - You can Ex. import * as pi from "./math.js";
        - This would import an object that we can tap into using dot notation.
        - {pi.default} or {pi.triplePi} is how we tap into the object


## ES6 IMPORT/EXPORT Challenge
--

(complete-sandbox)[https://codesandbox.io/s/es6-importexport-practice-forked-b9dh6?file=/src/calculator.js]

//Import the add, multiply, subtract and divide functions
//from the calculator.js file.
//If successful, your website should look the same as the Final.png



## Local React Environment Setup
--

(udemy-mac-setup)[https://www.udemy.com/course/the-complete-web-development-bootcamp/learn/lecture/17038878#notes]

(changing-node-version)[https://stackoverflow.com/questions/63697030/how-to-i-change-node-version-in-windows]
*** NPM START in CHROME **** 

- Install Local IDE
    -  VSCODE installed already


1. We need to install NPM, if not already installed before we can setup REACT.
    - npm --version (installed)
2. Next we run a series of code in terminal 
    - npx create-react-app my-app
    - cd my-app
    - npm start

3. Create React APP doesn't handle backend logic databases, it just creates the frontend pipeline, so you can use it with any backend you like. 
    - under the hood it uses Babel and webpack

4. When your ready to deploy to production
    - npm run build
    
5. Remove unnecessary files
    - From public
        - remove everything but index.html
    - From src
        - remove everything but index.js

6. Remove unnecassary code
    - In head tag, from all the <link> tags
    - in the Body, from everything but the root <div>
    - In index.js delete everything but the two imports of React and ReactDOM

7. add the script tag to connect our index.js and type needs to be "text/jsx"