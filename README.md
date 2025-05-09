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

The browser then creates a structure called the DOM (Document Object Model), which is a tree-like representation of all the HTML elements on the page.
 
JavaScript and DOM methods can be used to interact with this structure — like listening to clicks, updating content, or changing styles. This is what allows web apps to be interactive and dynamic.

Updating UI with JavaScript and React

To update the user interface (UI) using JavaScript, first we need to work with the DOM (Document Object Model). The DOM is a tree-like structure that represents the HTML elements on a web page.

index.html

Imperative Programming:

<div id ="app"></div>
<script type="text/javascript">

 Step 1: Select the div with id="app"
  const app = document.getElementById('app');

   Step 2: Create an <h1> element
  const header = document.createElement('h1');

   Step 3: Create the text node
   const text = 'Develop. Preview. Ship.';
   const headerContent = document.createTextNode(text);

   Step 4: Add the text to the <h1> element
   header.appendChild(headerContent);

   Step 5: Add the <h1> to the page inside the <div>
   app.appendChild(header);
   </script>


 

 

  

   



























