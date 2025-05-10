# Web Programming & Framework 2 - ITE-5425-0NB
Lab 1 - React Foundation

#Curve and Challenges:
Some concepts in React were completely new to me, especially state, components, and props. At first, understanding how components are reused and how data is passed through props was a bit confusing. The idea of hooks, like useState, and how state allows a component to "remember" values over time took some time to fully understand.

Another challenge was how React re-renders components when state changes.Despite these challenges, I found the provided course materials and examples are very clear and helped me understand the basic concepts step by step. Very detailed explanations with practical examples.

The interesting thing i found like as we start using more modern concepts like declarative programming ,the need to write lengthy, step-by-step code is reduced. This makes the code more readable and cleaner, easier to understand, also reduced the amount of code I needed to write for complex tasks.

#Resources Used:
https://nextjs.org/learn/react-foundations

#Explanation
React & Next.js

React

React is a JavaScript library for building interactive user interfaces.

User interfaces (UI) means, the elements that users see and interact with on-screen basically, the parts of a website that users interact with like buttons, forms, navigation bars, etc.

By library means, React provides helpful functions (APIs) to build UI, but leaves it up to the developer where to use those functions in their application.

Next.js

Next.js is a React framework that gives building blocks to create web applications means it comes with built-in tools and features that make it easier to develop web applications.

Framework means Next.js handles the tooling and configuration needed for React, and provides additional structure, features, and optimizations for application.

React is used to build UI, then incrementally adopt Next.js features to solve common application requirements such as routing, data fetching, and caching - all while improving the developer and end-user experience.

So we can use React and Next.js to build fully interactive, highly dynamic, and performant web applications.

Rendering User Interfaces (UI)

When a user opens a web page, the browser gets an HTML file from the server.

The browser then creates a structure called the DOM (Document Object Model), which is a tree-like representation of all the HTML elements on the page.

JavaScript and DOM methods can be used to interact with this structure — like listening to clicks, updating content, or changing styles. This is what allows web apps to be interactive and dynamic.

Updating UI with JavaScript and React

To update the user interface (UI) using JavaScript, first we need to work with the DOM (Document Object Model). The DOM is a tree-like structure that represents the HTML elements on a web page.

index.html

Imperative Programming:

<div id="app"></div> <script type="text/javascript"> // Step 1: Select the div with id="app" const app = document.getElementById('app'); // Step 2: Create an <h1> element const header = document.createElement('h1'); // Step 3: Create the text node const text = 'Develop. Preview. Ship.'; const headerContent = document.createTextNode(text); // Step 4: Add the text to the <h1> element header.appendChild(headerContent); // Step 5: Add the <h1> to the page inside the <div> app.appendChild(header); </script>
After opening this file in a browser, I could see the <h1> on the screen, even though it wasn’t originally written in the HTML. This happened because JavaScript used DOM methods to create and insert elements dynamically.

This step-by-step coding is called imperative programming, where we tell the browser how to do each step.

But this process is hard to manage when building larger applications. So developers prefer a declarative approach, where we just describe what we want on the screen — and let the library (like React) handle the steps.

Declarative Programming:

<head> <script src="https://unpkg.com/react@17/umd/react.development.js"></script> <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script> <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script> </head> <body> <div id="app"></div> <script type="text/babel"> // React code (declarative) const App = () => { return <h1>Develop. Preview. Ship.</h1>; }; // Render the App component into the div with id="app" ReactDOM.render(<App />, document.getElementById('app')); </script>
So here, I didn’t have to manually create elements or text nodes. I just wrote what I want to display — an <h1> with some text — and React took care of updating the DOM.

Imperative: Tell the chef each step to make the pizza.
Using plain JavaScript, we manually update the DOM (imperative approach).

Declarative: Just say "I want a cheese pizza" — and it gets made.
Using React, we declare what we want to show, and it handles the DOM updates (declarative approach).

Using React with JSX:

React allows us to describe the UI in a cleaner way. But because browsers don’t understand JSX directly, we need Babel to convert JSX to regular JavaScript.

<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script> <script type="text/jsx"> JSX looks like HTML but is actually JavaScript. Browsers don’t understand JSX, so we need Babel to convert it. With React, I don’t need to worry about createElement, appendChild, etc. Just write <h1>Text</h1> and React handles the rest. Building UI with Components: There are three core concepts of React to start building React applications. These are: Components Props State Components: Components are like LEGO bricks: small, reusable, self-contained pieces of code that can be combined to create complex UIs. Each component represents a part of the user interface (UI), like a button, a header, or a form. When we want to make changes to UI, we can modify just the relevant component without affecting the whole application. This makes the code cleaner and easier to manage. For example: <div id="app"></div> <script type="text/jsx"> const app = document.getElementById("app"); function Header() { return <h1>Develop. Preview. Ship.</h1>; } const root = ReactDOM.createRoot(app); root.render(<Header />); </script>
The component is named Header, and it returns a heading element.

It must start with a capital letter to distinguish it from HTML tags.

ReactDOM.createRoot() and render() used to display the component in the browser.

Nesting Components

It allows to nest components inside other components.

For instance here, HomePage is a top-level component that includes the Header component inside it.

function Header() {
return <h1>Develop. Preview. Ship.</h1>;
}

function HomePage() {
return (
<div>
{/* Nesting the Header component inside HomePage */}
<Header />
</div>
);
}

Component Tree

A component tree is a structure where components are nested within each other. For example:

HomePage could contain:

Header (with child components like Logo, Title, and Nav)
Article
Footer

Displaying Data with Props:

Props act like parameters in functions, allowing us to pass data from one component to another.

Here, we are using the Header component twice, it just repeats the same message.

function Header() {
return <h1>Develop. Preview. Ship.</h1>;
}

function HomePage() {
return (
<div>
<Header />
<Header />
</div>
);
}

So, to show different text each time, we can pass a prop like this:

function HomePage() {
return (
<div>
<Header title="React" />
</div>
);
}

In the Header component, we can access this prop using the props object:

function Header(props) {
return <h1>{props.title}</h1>;
}

So in this way, whatever value we pass as title will be displayed in the <h1> tag. Now the component becomes dynamic and reusable.

function HomePage() {
return (
<div>
<Header title="React" />
<Header title="Welcome to My App" />
</div>
);
}

Iterating through lists:

In many apps, we often want to show lists — like user names or products. We can use .map() method to loop through an array and create elements.

In this example:

function HomePage() {
const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];

return (
<div>
<Header title="Develop. Preview. Ship." />
<ul>
{names.map((name) => (
<li key={name}>{name}</li>
))}
</ul>
</div>
);
}

Defining an array of names.

Using map() to go through each name and return a <li> element.

Using key prop to uniquely identify each item. This helps React update the DOM efficiently.

Adding Interactivity with State:

Interactivity means how users can engage with elements on the page and how those interactions cause changes in the user interface (UI). To handle user actions like clicks, React supports event handlers such as onClick.

To create a Like Button:

Create a Functional Component

Define a component HomePage using a function. It returns a list of names and a button.

function HomePage() {
const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];

return (
<div>
<ul>
{names.map(name => (
<li key={name}>{name}</li>
))}
</ul>
<button>Like</button>
</div>
);
}

Add Click Event Handler

To make the button interactive, add an onClick handler to the button element

function handleClick() {
console.log('Button clicked');
}

return (

<div> <button onClick={handleClick}>Like</button> </div> );
Use State to Track Likes

Here, using useState hook to keep track of how many times the button is clicked and initialize the likes state to 0.

function handleClick() {
setLikes(likes + 1); // Increase the count by 1
}

const [likes, setLikes] = React.useState(0);

useState(0) creates a likes variable with an initial value of 0.

setLikes() updates the value whenever the button is clicked.

Every time likes changes, React re-renders the component to show the new value.

 

  

   



























