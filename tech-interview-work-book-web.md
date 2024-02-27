# Web Module Questions

### Functional patterns

#### What is a callback function?
- A callback function is a function passed into another function as an argument,
  which is then invoked  inside the another function to complete some kind of routine or action.
#### What is ECMA script ? What is the difference between Javascript & ECMA script ?
Ecma International is an organization that creates standards for technologies.

ECMA-262 is a standard published by Ecma International. It contains the specification for a general purpose scripting language. _This specification is called ECMAScript_. (A scripting language is a programming language designed specifically for acting on an existing entity or system.)

_JavaScript is a general purpose scripting language_ that conforms to the ECMAScript specification.

By reading the ECMAScript specification, you learn how to _create_ a scripting language. By reading the JavaScript documentation, you learn how to _use_ a scripting language.

#### What is the difference between `let` & `var` ?
- The var is a function scoped variable, if we define it in a function we can access it 
  while the function is running.
  The let variable is only block scoped. It can’t be accessible outside the particular block. Both var and let can used to define global variables.
#### Write an example where using the `var` declaration instead of the `let` could create a hard to debug code.

  var a = 5;
      console.log(a); // 5
      {
          var a = 3;
          console.log(a); // 3
      }
      console.log(a); // 3

#### Give a practical example where you would use the `reduce` function in javascript.

- to get the sum of an array of numbers:
- on each iteration, it returns the sum of the accumulated value and the current number.

        const array1 = [1, 2, 3, 4];

        // 0 + 1 + 2 + 3 + 4
        const initialValue = 0;
        const sumWithInitial = array1.reduce(
          (accumulator, currentValue) => accumulator + currentValue,
          initialValue
        );

        console.log(sumWithInitial);
        // Expected output: 10


#### Give a practical example where you would use the `map` function in javascript.

- to get a new array with the square of all element values

        const numbers = [1, 3, 9];
        const square = numbers.map(number => number**2) 

#### Give a practical example where you would use the `filter` function in javascript.

- to get the numbers below 20 from an array

        const numbers = [32, 33, 16, 40];
        const numbersBelow20 = numbers.filter(number => number < 20)

### Web basics

#### What is a web server?
- On the hardware side, a web server is a computer that stores web server software and a website's component files.  A web server connects to the Internet and supports physical data interchange with other devices connected to the web.
#### Explain the client-server architecture.
- A server is the one who provides requested services.
- Clients are the ones who request services.

- The server hosts, delivers, and manages most of the resources and services requested by the client.

- The client software can send data requests to one or more connected servers. In turn, the servers can accept these requests, process them, and return the requested information to the client.

- Characteristics of a client  
  - Request sender is known as client  
  - Initiates requests  
  - Waits for and receives replies.  
  - Usually connects to a small number of servers at one time  
  - Typically interacts directly with end-users using a graphical user interface  
    
- Characteristics of a server  
  - Receiver of request which is send by client is known as server  
  - Passive (slave)  
  - Waits for requests from clients  
  - Upon receipt of requests, processes them and then serves replies  
  - Usually accepts connections from a large number of clients  
  - Typically does not interact directly with end-users
#### What is the difference between synchronous and asynchronous execution?

- Synchronous tasks happen in order — you must finish task one before moving on to the next.  
- Asynchronous tasks can be executed in any order, or even simultaneously.
#### What is `npm`? Why is it useful?

- Node Package Manager for javascript platform. It puts modules in place so that node can find them, and manages dependency conflicts. It is used to publish, discover, install, and develop node programs.

#### What is the difference between the `depdendencies` & `devDependencies` in a `package.json` file ?

- dependency is an object that contains the library, which your project requires for production environments and functioning effectively. (Modules which are also required at runtime.)
- devDependencies are those packages in the package.json file that you need only for project development purposes. (Modules which are only required during development.)
#### What would be the impact of javascript `fetch` if it was not asyncronous ?

- If fetch was not asynchronous, it would mean that the code execution would be blocked until the request is completed.
- It would make the user interface unresponsive while waiting for the network response, which would result in a poor user experience.
- It would impact the performance of the entire application, as the browser would be unable to execute any other JavaScript code while waiting for the fetch request to complete.
#### Why benefits would bring to a developer to use the `Postman` application ?

- Easy API testing: allowing developers to send requests, view responses, and debug any issues quickly and easily
- catch issues early on in the development process
- monitor APIs in real-time and receive alerts when something goes wrong
#### List the parts of the URL.

1. Scheme: The scheme specifies the protocol used to access the resource. Common schemes include HTTP, HTTPS
2. Subdomain
3. Host: The host specifies the domain name or IP address of the server where the resource is located.
4. Port: The port specifies the network port number used to access the resource on the server. This is optional and is usually omitted if the default port number for the scheme is used.
5. Path: The path specifies the location of the resource on the server. It typically consists of a sequence of directories and filenames separated by slashes.
6. Query string: The query string allows additional parameters to be passed to the server when requesting the resource. It is separated from the path by a question mark and consists of one or more key-value pairs separated by ampersands.
7. Fragment identifier: The fragment identifier specifies a specific section of the resource to be displayed. It is separated from the rest of the URL by a hash symbol and is typically used with HTML documents to scroll to a specific section of the page.
#### What is query parameter?
- Query parameters are a defined set of parameters attached to the end of a url. They are extensions of the URL that are used to help define specific content or actions based on the data being passed.
#### What kind of HTTP status codes do you know?

- Informational responses (100 – 199)
- Successful responses (200 – 299)
  - 200 OK : The request succeeded
  - 201 Created : The request succeeded, and a new resource was created as a result. This is typically the response sent after POST requests, or some PUT requests.
- Redirection messages (300 – 399)
- Client error responses (400 – 499)
  - 400 Bad Request : The server cannot process the request due to client error
  - 401 Unauthorized: Although the HTTP standard specifies "unauthorized", semantically this response means "unauthenticated". That is, the client must authenticate itself to get the requested response.
  - 404 Not Found: The server cannot find the requested resource, URL is not recognized.
  - 429 Too Many Requests : The user has sent too many requests in a given amount of time ("rate limiting").
- Server error responses (500 – 599)
  - 500 Internal Server Error : the server encountered an unexpected condition that prevented it from fulfilling the request.

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?

- An HTTP request is a message sent by a client (such as a web browser) to a web server, requesting a specific action to be performed on the server. HTTP (Hypertext Transfer Protocol) is the protocol used for communication between clients and servers on the World Wide Web.
- HTTP requests are a fundamental part of web development and are used for a wide range of tasks, such as retrieving web pages, submitting form data, and interacting with web APIs.
- An HTTP request consists of three parts: the request line, the request headers, and the message body
- The most commonly-used HTTP methods are POST, GET, PUT, PATCH, and DELETE.
- fetch()
  - built-in JavaScript method that is used to make asynchronous network requests (HTTP requests) to web servers or APIs.
  - The fetch() method returns a Promise, which allows developers to handle the response data in a more elegant and efficient way than with traditional callback functions. The Promise can be resolved with a Response object, which includes information about the response, such as the status code, headers, and data.

        fetch('https://api.example.com/data')
        .then(response => response.json())
        .then(data => {
          // Do something with the data
        })
        .catch(error => {
          // Handle any errors
        });

  - In this example, fetch() is used to make a GET request to the URL 'https://api.example.com/data'. The response is then converted to JSON using the json() method, which returns a Promise that resolves with the parsed JSON data. Finally, the data is handled in the second then() method, or any errors are handled in the catch() method.
#### How does an HTTP Response look like? What are the most relevant HTTP header fields?

- An HTTP response is a message sent by a web server to a client (such as a web browser) in response to an HTTP request. The response typically contains the requested content or information about the status of the request.
- HTTP response parts:
  1. Status line: The first line of the response, which includes the HTTP version, a numeric status code indicating the result of the request, and a short textual description of the status.
  2. Headers: Optional additional information about the response, such as the type of data being returned, the length of the response, or caching instructions for the client.
  3. Body: The content of the response, such as HTML, JSON, or an image.
#### Why should you ignore the `node_modules` folder in `.gitignore` ?

- In Node.js projects, the node_modules folder typically contains a large number of third-party dependencies and libraries that are installed via a package manager such as npm or Yarn. This folder can easily become quite large and is not typically necessary to include in version control, as the dependencies can be installed from scratch on any machine by running npm install or yarn install.
- Ignoring the node_modules folder in .gitignore can help to reduce the size of the Git repository and avoid unnecessarily committing large binary files, which can slow down Git operations and increase the overall size of the repository.


### Rest API: Serve and Fetch

#### Why is it recommend for a developer to use the http methods `get`, `put`, `delete` ?

- These methods provide a clear and standardized way of interacting with resources on the web.
  - GET: This method is used to retrieve a representation of a resource, such as a web page or a data record. GET requests should be safe and idempotent, meaning that they should not modify or have any side effects on the resource being retrieved.
  - PUT: This method is used to update or replace a resource with a new representation. The request body of a PUT request typically contains the updated representation of the resource, and the server replaces the existing resource with the new representation.
  - DELETE: This method is used to delete a resource. The server should remove the resource identified by the URL from the system, and a DELETE request should only be sent if the requester has the appropriate permissions to do so.
#### How does a `POST` request look like when it is made from a web browser (on the front end written) ?

 const data = {
        name: 'John Doe',
        email: 'johndoe@example.com',
        message: 'Hello, world!'
        };

        fetch('https://api.example.com/messages', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify(data)
        })
        .then(response => response.json())
        .then(data => {
          console.log('Message sent successfully:', data);
        })
        .catch(error => {
          console.error('Error sending message:', error);
        });
  - In this example, we are making a POST request to the URL 'https://api.example.com/messages' with JSON data containing a name, email, and message.
  - The fetch() method takes two arguments: the URL to make the request to, and an options object that includes the method, headers, and body of the request. We set the method to 'POST' to indicate that we want to send data to the server, and we set the 'Content-Type' header to 'application/json' to indicate that the body of the request will contain JSON data.
  - The data object is then converted to a JSON string using the JSON.stringify() method and passed as the body of the request.
  - Once the server responds, the response data is converted to JSON using the json() method, and the data is handled in the second then() method. In this example, we simply log the response data to the console if the message was sent successfully, or log an error if there was an issue sending the message.
  - (Authorization: Specifies any authentication credentials that the client is using to access the resource.)
  - (Content-Type: Specifies the format of the data being sent in the request message body.)

#### What is an API?

- An API (Application Programming Interface) is a set of protocols, routines, and tools for building software applications. It provides a standardized way for different software applications to communicate and exchange data with each other, regardless of the programming language, operating system, or platform used.
- APIs define how the components of software interact with each other, including requests and responses between them. They allow developers to create software applications that can leverage functionality or data from other software services without needing to know the details of how those services work internally.
- APIs let your product or service communicate with other products and services without having to know how they’re implemented. This can simplify app development, saving time and money.

#### What is REST API?

- API stands for Application Programming Interface, which is a general term used to describe a set of protocols, routines, and tools that enable different software applications to communicate with each other. APIs can use different protocols for communication, such as SOAP, XML-RPC, and JSON-RPC.
- REST (Representational State Transfer) API, on the other hand, is a specific type of API that uses HTTP protocols for communication. RESTful APIs use a uniform set of operations, such as GET, POST, PUT, DELETE, and PATCH, to manipulate resources and are designed to be stateless and cacheable.
- RESTful principles are a set of guidelines and constraints for designing web services that use the REST architecture style. These principles help to ensure that the web service is simple, scalable, and easy to use. The key principles of RESTful API design include:
1. Resource identification: Resources should be identified with unique URIs (Uniform Resource Identifiers).
2. Resource manipulation through representations: Clients should manipulate resources by sending representations to the server.
3. Self-descriptive messages: Messages sent between clients and servers should be self-descriptive, containing all the information necessary to process the message.
4. Hypermedia as the engine of application state (HATEOAS): Responses from the server should contain links to related resources, allowing clients to navigate through the application.
5. Stateless interaction: Each request from a client should contain all the information necessary to complete the request, without requiring the server to store any session information.

#### What is JSON and how do we use it?

- JSON (JavaScript Object Notation) is a lightweight data-interchange format that is easy for humans to read and write and easy for machines to parse and generate. It is a text format that uses a syntax similar to JavaScript object literals, making it popular for data exchange between web services and client-side applications.
- JSON data is composed of key-value pairs, with keys enclosed in double quotes and values as either a string, number, boolean, null, array, or object.
- JSON is a popular and flexible format for data exchange between different systems and programming languages.
- In JavaScript, you can use the JSON object to encode and decode JSON data:

        // Serialize a JavaScript object to a JSON string
        const data = {name: "John Doe", age: 35, email: "john.doe@example.com"};
        const json_string = JSON.stringify(data);

        // Deserialize a JSON string to a JavaScript object
        const data = JSON.parse(json_string);
        console.log(data.name);  // Output: John Doe

#### What is API versioning ?

- API versioning is the practice of managing changes to an API and ensuring that these changes are made without disrupting clients. A good API versioning strategy clearly communicates the changes made and allows API consumers to decide when to upgrade to the latest version at their own pace.
- As an API evolves, new features may be added, and existing features may be changed or removed. If these changes are not handled carefully, they can break existing clients that rely on the API's previous behavior. API versioning helps to mitigate this problem by providing a way to manage different versions of an API and allow clients to specify which version they want to use.

#### Give 3 examples of HTTP response status codes ? Explain what each number means.

  - 201 Created : The request succeeded, and a new resource was created as a result. This is typically the response sent after POST
  - 429 Too Many Requests : The user has sent too many requests in a given amount of time ("rate limiting").
  - 200 OK: This response status code indicates that the request has succeeded, and the server has returned the requested data in the response body. This is the most common status code for successful HTTP requests.
  - 404 Not Found: This response status code indicates that the requested resource could not be found on the server. This could happen if the URL is incorrect, the resource has been removed, or the user does not have the necessary permissions to access the resource.
  - 500 Internal Server Error: This response status code indicates that the server has encountered an unexpected condition that prevented it from fulfilling the request. This could happen due to a software bug, a misconfiguration, or a problem with the server infrastructure.

- Each HTTP response status code is a three-digit number that is included in the response header to indicate the status of the request. The first digit indicates the general category of the status code, with the following meanings:

  - 1xx (Informational): The request has been received, and the server is continuing to process it.
  - 2xx (Successful): The request has succeeded, and the server has returned the requested data in the response body.
  - 3xx (Redirection): The request requires further action to complete, such as following a redirect.
  - 4xx (Client Error): The request could not be completed due to an error on the client side, such as an invalid request or insufficient permissions.
  - 5xx (Server Error): The request could not be completed due to an error on the server side, such as an unexpected condition or infrastructure problem.

### Advanced JavaScript

#### How does the `ternary operator` looks like in javascript?

- Its a shorthand way of writing an if-else statement. It has the following syntax:

      condition ? expressionIfTrue : expressionIfFalse

- The condition is evaluated to a boolean value, and if it is true, the expressionIfTrue is executed. If the condition is false, the expressionIfFalse is executed instead.

#### How to import a function from another module in JavaScript?

- you can use the import statement

      import { myFunction } from './myModule.js';

- In this example, we are importing myFunction from a file called myModule.js in the same directory. The curly braces {} indicate that we are importing a named export from the module.
- If the module has a default export, you can import it without the curly braces, like this:

      import myFunction from './myModule.js';

- Here, we are importing the default export of myModule, which is assigned to the variable myFunction.
- Note that the file extension .js is required in the import statement, and the file path must be relative to the current file. Also, it's important to ensure that the module has been exported using the correct syntax before trying to import it in another module.

#### What is a shallow copy on an object?
- a new object that has the same properties as the original object, but the values of those properties are references to the same objects as the original
- the new object shares the same properties with the original object, but the values of those properties are not copied; they are only referenced.
- To create a shallow copy of an object, you can use the spread operator ... or the Object.assign() method. Here's an example:

      const original = { a: 1, b: 2, c: { d: 3 } };
      const copy = { ...original };
      // or: const copy = Object.assign({}, original);

- If we modify the c property of original, the c property of copy will also be affected, because they reference the same object:

      original.c.d = 4;
      console.log(copy.c.d); // Output: 4
- When you update the state in React, it is important to create a new object that represents the updated state. This is because React uses a shallow comparison to determine if the state has changed, and if the state has not changed, it will not trigger a re-render.
- If you update the state using the same object reference, React will not detect the change and will not trigger a re-render. This can lead to unexpected behavior in your application.
- To avoid this problem, it is important to create a new object reference when updating the state. A shallow copy is a simple way to achieve this, as it creates a new object that shares the same properties with the original object. When you update the state using the new object reference, React will detect the change and trigger a re-render.

      import { useState } from 'react';

      function MyComponent() {
        const [person, setPerson] = useState({ name: 'John', age: 30 });

        function handleClick() {
          // create a new object that is a shallow copy of person
          const updatedPerson = { ...person };
          // update the age property of the new object
          updatedPerson.age = 31;
          // update the state with the new object reference
          setPerson(updatedPerson);
        }

        return (
          <div>
            <p>Name: {person.name}</p>
            <p>Age: {person.age}</p>
            <button onClick={handleClick}>Update Age</button>
          </div>
        );
      }
#### What is a callback function? Tell some examples of its usage.

- a function that is passed as an argument to another function and is called inside that function
- The purpose of a callback function is to allow for asynchronous or event-driven programming
1. Event listeners: you can specify a callback function that will be called when the event occurs, add an event listener to a button element and specifies a callback function that will be called when the button is clicked
2. Array methods:  map, filter, and reduce, take a callback function as an argument that is called for each element in the array
3. Asynchronous functions: typically take a callback function as an argument that will be called when the function completes. For example, the setTimeout function takes a callback function and a time delay as arguments

#### What is object destructuring in javascript?

 Object destructuring is a feature in JavaScript that allows you to extract properties from an object and assign them to variables, making it more convenient and readable to work with objects. It's commonly used in React when extracting properties from component props and also useful in function parameter as well.

#### What is array destructuring in javascript?

Array destructuring is a powerful feature in JavaScript that allows you to extract elements from an array and assign them to variables, making it more convenient and readable to work with arrays. It's commonly used when working with returned values from functions and also useful in function parameter as well.

#### What is the spread operator in `js` ?

- spread operator is denoted by three dots (...)
- When used with arrays, the spread operator allows you to expand an array into individual elements. For example:

      const myArray = [1, 2, 3];
      console.log(...myArray); // output: 1 2 3

- The spread operator can also be used to concatenate arrays:

      const array1 = [1, 2, 3];
      const array2 = [4, 5, 6];
      const concatenatedArray = [...array1, ...array2];
      console.log(concatenatedArray); // output: [1, 2, 3, 4, 5, 6]

- When used with objects, the spread operator allows you to create new objects by merging properties from existing objects:

      const obj1 = { a: 1, b: 2 };
      const obj2 = { c: 3, d: 4 };
      const mergedObj = { ...obj1, ...obj2 };
      console.log(mergedObj); // output: { a: 1, b: 2, c: 3, d: 4 }

- The spread operator can also be used to create shallow copies of arrays and objects:

      const originalArray = [1, 2, 3];
      const copyOfArray = [...originalArray];
      console.log(copyOfArray); // output: [1, 2, 3]

      const originalObj = { a: 1, b: 2 };
      const copyOfObj = { ...originalObj };
      console.log(copyOfObj); // output: { a: 1, b: 2 }

#### What are the differences between the `arrow` function and the regular `function`?

- Syntax: The syntax of the arrow function is more concise than the regular function syntax. An arrow function is declared using an arrow (=>) between the function parameters and the function body, while a regular function uses the function keyword, followed by the function name, parameters in parentheses, and the function body in curly braces.
- Return value: In an arrow function, if the function body is a single expression, that expression is automatically returned. In a regular function, you must use the return keyword to explicitly return a value.

      // regular function
      function add(a, b) {
        return a + b;
      }

      // arrow function
      const add = (a, b) => a + b;
  ```
#### What is the `import` keyword used for?

- to import functionality from other modules, which can be used in the current module
- When you use import, you are essentially telling the browser or Node.js environment to load the specified module and make its exported functionality available to the current module

      // in file math.js
      export function add(a, b) {
        return a + b;
      }

      // in file main.js
      import { add } from './math.js';

      console.log(add(1, 2)); // output: 3

- The import statement can also import all the exported values from a module using the * syntax:

      import * as math from './math.js';

      console.log(math.add(1, 2)); // output: 3

- It's worth noting that import statements can only be used in module scripts, which are JavaScript files that use the type="module" attribute in their < script > tag. Additionally, the module system is not supported in older browsers and versions of Node.js, so it's important to check for compatibility before using import in your code.

#### What is the `required` used for?

In NodeJS, require() is a built-in function to include external modules that exist in separate files. require() statement basically reads a JavaScript file, executes it, and then proceeds to return the export object. require() statement not only allows to add built-in core NodeJS modules but also community-based and local modules.

#### What are template literals?

Template literals are literals delimited with backtick (`) characters, allowing for multi-line strings, string interpolation with embedded expressions, and special constructs called tagged templates.

### Testing basics

#### What is code coverage? Why is it used?
#### What is a test case? What is an assertion? Give examples!
#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)
#### What is arrange/act/assert pattern?
#### How do you test asynchronous code with `jest` ?
#### What is `setup` & `teardown` in jest ?
#### Give an example when you would use in `jest` the `toBe` & `toEqual` assertions.

### React basics

#### What benefits does it bring for a developer to use `components` (opposed of writing all the code in a single file) ?

- Easier to understand them
- Components are easily reusable and modifiable
- Multiple people can work on different components at the same time

#### What is the difference between Element and Component?

- Element is a plain JavaScript object that describes a component instance or HTML tag and its properties, while a Component is a function or class that returns an Element.
- An Element is a description of what you want to render, whereas a Component is the code that creates and renders that description.
- Elements are immutable objects, while Components are functions or classes that can take in props and state and return a new Element based on those inputs.

      // Element
      const element = <div>Hello, World!</div>;

      // Component
      function Greeting() {
        return <div>Hello, World!</div>;
      }

#### How do you pass values between components in `react`?

Props are inputs to a React component. They are data passed down from a parent component to a child component. They get collected into a properties object (props) which then is passed to the component function as the first argument. Props are readonly

#### What is `key` prop?

A key prop is needed when creating elements from an array. The key prop should be unique for each element (preferably not the index). It helps React keep track of elements in DOM, should the order change, for example.

#### How does a child component pass data to it's parent component ?

1. Define an event handler function in the parent component and pass it to the child component as a property. The event handler function is called in the child component and accept an argument which is data from the child component.

2. Define a state in the parent component and pass it to the child component as a property. When the state gets set in the child component, it also gets set in the parent component. This is called state lifting.

#### Write the code to create in JSX an HTML DIV element that has the innerText the contents of the variable `let name = 'Andrew'`

let name = 'Andrew';

const myDiv = <div>{name}</div>

#### Write the code to create in JSX an unordered list from the array `let names = ["Mathew", "John", "Maverik"]`

```js
let names = ["Mathew", "John", "Maverik"];

const nameList = (
  <ul>
    {names.map((name,index) => (
      <li key={index}>{name}</li>
    ))}
  </ul>
);
```
#### Write the code to set the background color red of a div in JSX.


    import React from 'react';

    function App() {
      return (
        < div style={{ backgroundColor: 'red' }}>
          Hello, World!
        </ div>
      );
    }

    export default App;

### Testing react

#### What are unit tests, integration tests? What is the major difference between these two?
#### What is unit testing?
#### What does `mocking` mean from a testing perspective ? Give an example when you would use it.
#### How do you test that function was called `at least` 2 times using `jest` ?
#### Name 4 benefits a developer gets from writing tests.

### React patterns

#### What is the difference between Real DOM and Virtual DOM?

#### Real DOM

Whenever a user requests a webpage, the browser receives an HTML document for that page from the server. The browser then constructs a logical, tree-like structure from the HTML to show the user the requested page in the client.

This tree-like structure is called the Document Object Model, also known as the DOM. It is a structural representation of the web document as nodes and objects.

#### Virtual DOM

In React, for every DOM object, there is a corresponding “virtual DOM object.” A virtual DOM object is a representation of a DOM object, like a lightweight copy.

React first creates a Virtual DOM tree, where it keeps track of all info, for example which components does each element belong to. Then it will use this virtual tree to create the actual, real DOM tree that gets displayed in the browser, keeping only the info necessary for displaying the tree.

When you render a JSX element, the whole Virtual DOM object gets updated. Then React compares the virtual DOM with a virtual DOM snapshot that was taken right before the update, determines what element was changed, and updates only that element on the real DOM. This is one method the virtual DOM employs to optimize performance.

#### When adding an item to an array, why is it necessary to pass a new array to the `useState` hook ?

- In React, when you want to update the state of a component, you typically use the useState hook. When working with arrays, you need to pass a new array to the useState hook when you want to add an item to the array, because React uses referential equality to determine whether the state has changed.
- When you pass a new array to the useState hook, React compares the new array to the previous one using referential equality. If the new array is different from the previous one, React knows that the state has changed and triggers a re-render of the component.
- If you modify the existing array directly and pass it to the useState hook, React may not recognize the change, because the array reference has not changed. This can lead to unexpected behavior and bugs in your code.
- To add an item to an array using the useState hook, you can use the spread operator to create a new array with the original items and the new item added to it, like this:

      const [items, setItems] = useState(['item1', 'item2']);

      const addItem = (newItem) => {
        setItems([...items, newItem]);
      };
#### Describe what techniques or tools you use to debug a react app.

- console.log()
- The browsers debugger

#### What is the difference between a react `class` component & a `functional` component ?

- Class components are defined using ES6 classes and extend the React.Component class. They have a render() method that returns the JSX to be rendered on the page. Class components also have access to the component lifecycle methods, such as componentDidMount() and componentDidUpdate(), which allow you to perform actions when the component is mounted or updated.
- Functional components, on the other hand, are defined using a JavaScript function. They receive props as their first argument and return the JSX to be rendered on the page. They don't have access to the component lifecycle methods or the this keyword, which means that they can be simpler and more lightweight than class components.
- differences:
  1. Syntax: Class components are defined using the class keyword and extend React.Component, while functional components are defined using a JavaScript function.
  2. State: Class components have access to state and can modify it using this.setState(), while functional components don't have state.
  3. Lifecycle methods: Class components have access to the component lifecycle methods, such as componentDidMount(), componentDidUpdate(), and componentWillUnmount(), while functional components don't.
  4. Performance: Functional components are generally more lightweight than class components and can offer better performance in some cases.

#### Name 3 lifecycle states in a react `functional` component.

- Mounting - element gets added to the DOM
- Updating - element changes
- Unmounting - element gets removed from the DOM

#### What is conditional rendering in `react` ? Give an example.

You can use conditional rendering to add an element to the DOM tree only if a certain condition is met.
```
  return (
    <div>
      {somethingThatsTrueOrFalse && <p>Rendered!</p>}
    </div>
  )

#### Write the code that prints to the console `component destroyed` when the component it is part of is removed from the DOM tree.

import { useEffect } from 'react';

function MyComponent() {
  useEffect(() => {
    return () => console.log("component destroyed");
  }, []);
  
  return <div>My Component</div>;
}
#### Why is there an infinite loop in this code
```function App() {
  const [count, setCount] = useState(0); //initial value of this 
  useEffect(() => {
    setCount((count) => count + 1); //increment this Hook
  }); //no dependency array.
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```

In this code, there is an infinite loop caused by the useEffect hook. When the component is first rendered, the count state variable is set to 0. The useEffect hook is then called, and inside it, the setCount function is called to increment the count variable. However, because there is no dependency array provided to the useEffect hook, it will run on every render of the component, including re-renders caused by the setCount function inside the effect.

This creates an infinite loop, where the component is continuously re-rendering, and the count state variable is continuously being incremented. The displayed value of the count on the screen doesn't change and the component can not finish its lifecycle.

To fix this issue, it is necessary to pass a dependency array to useEffect that includes the value of count, so that it only runs when the count value changes.

#### Why is there an infinite loop in this code
```
  async function App() {
  const [count, setCount] = useState("");
  setCount(count + 1);
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```

The useState hook is called to set the initial value of count state variable to an empty string, and then, right after that, the function setCount(count + 1) is being invoked which causes the component to re-render, updating the value of the count state variable.

However, because count state variable is updated during render phase and component is re-rendered, the component will re-execute setCount(count + 1) and then again component re-renders and so on. This creates an infinite loop, where the component is continuously re-rendering, and the count state variable is continuously being incremented. The component can not finish its lifecycle.

To fix this issue, you should move setCount(count + 1); inside an useEffect hook that only runs once and also you need to pass the dependencies.

### Mongo & mongoose

#### What is a database schema ?

A schema is an object with key-value pairs. The keys correspond to the indentically named fields in the document. The values contain the data type (e.g. String, Number, Boolean...) and other optional properties, like required, or a default value. If we define other parameters besides the data type, we use nested objects in the values.

Example:

const BlogSchema = new Schema({
  title:  {type: String, required: true }, // required means title must be entered
  author: String, // String is shorthand for {type: String}
  body:   String,
  comments: [{ body: String, date: Date }],
  date: { type: Date, default: Date.now },
});

#### Why is the `id` unique in a database ?

Because then the documents can be identified by a property which is unique to them. When you create a new document, Mongoose automatically adds a unique `_id` property to your document.

#### What are the advatanges & disadvatages of using `lean()` function in a mongo query ?

Mongoose documents represent a one-to-one mapping to documents as stored in MongoDB. Each document is an instance of its Model. By default, Mongoose queries return an instance of the Mongoose Document class. Documents are much heavier than vanilla JavaScript objects, because they have a lot of internal state for change tracking.

The `lean()` function tells Mongoose to skip instantiating a full Mongoose document and just give you a plain JavaScript object. 

```js
const docs = await Model.find().lean();
```

Advantages: JS objects are smaller than a Mongoose document and faster to work with.

Disadvantages: JS objects are not connected with the MongoDB anymore, so cannot be used to manipulate the DB.

#### Write the code to store the object `{name: "Andrew", age: 10}` to a mongo database. You can ignore the part of connection parameters.

async function main() {
  // method 1
    const dbUser = new User({name: "Andrew", age: 10});
    dbUser.save();

  // method 2
    await User.create({name: "Andrew", age: 10});
};

main();

#### Write the code to delete from a mongo database all employees that are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.

  const mongoose = require('mongoose');

    // Define the schema for the data you want to store
    const EmployeeSchema = new mongoose.Schema({
      name: String,
      age: Number,
    });

    // Create a model based on the schema
    const Employee = mongoose.model('Employee', EmployeeSchema);

    // Connect to the MongoDB database
    mongoose.connect('mongodb://localhost/my_database');

    // Delete all employees over 18 years old
    Employee.deleteMany({ age: { $gt: 18 } }, (err, result) => {
      if (err) {
        console.error(err);
      } else {
        // log the number of employees that were deleted
        console.log(`${result.deletedCount} employees deleted from database`);
      }
    });


#### Write the code to display in the console from a mongo database the employees who are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.


async function main() {
  console.log( await Employee.find({ age: { $gt: 18 } }));
};

main();

#### Write the code to update from a mongo database the employees with name='John' and set the new age to 8. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.

 const mongoose = require('mongoose');

    // Define the schema for the data you want to store
    const EmployeeSchema = new mongoose.Schema({
      name: String,
      age: Number,
    });

    // Create a model based on the schema
    const Employee = mongoose.model('Employee', EmployeeSchema);

    // Connect to the MongoDB database
    mongoose.connect('mongodb://localhost/my_database', { useNewUrlParser: true, useUnifiedTopology: true });

    // Update all employees with name='John' to have age=8
    Employee.updateMany({ name: 'John' }, { age: 8 }, (err, result) => {
      if (err) {
        console.error(err);
      } else {
        console.log(`Updated ${result.nModified} employees`);
      }
    });


### Authentication (cookies + google)

#### How to properly store passwords?
#### What is encryption and decryption?
#### What is hashing?
#### What is OAuth2?
#### What is the difference between encryption and hashing? When would you use which?
#### How/where would you store sensitive data (like db password, API key, ...) of your application?
#### What would you use a session for?
#### What would you use a cookie for?

### Mern stack

#### What does `MERN` stand for in the context of web development ?

- `M`ongoDB - document database
- `E`xpress - web server framework
- `R`eact - frontend JS framework
- `N`ode - JS web server

#### What is routing in the context of a `react` app ?

`react` routing is a client side routing, meaning it can display different pages based on the URL without sending request to the server

#### What is routing in the context of an `express` app ?

Routing in `express` means that a server will run different operations based on the request's URL and method, which result in different responses

#### What is `CORS` policy ?

`C`ross-`O`rigin `R`esource `S`haring is a policy which decides whether the browser can access resources form a server that's different form the website origin, or not

#### What advantages does a developer have for using `bootstrap` or `material ui` ?
Using Bootstrap or Material UI can help developers to save time, improve the user experience, and create more accessible and consistent web applications.
- Pre-designed UI components: Both Bootstrap and Material UI offer a wide range of pre-designed UI components, such as buttons, forms, menus, cards, and more, that can be easily customized and integrated into a web application. This saves developers time and effort in designing and implementing UI components from scratch.
- Responsive design: Both Bootstrap and Material UI are designed with responsive web design in mind, which means that their UI components automatically adjust to fit different screen sizes and resolutions. This ensures that web applications built with these frameworks look great and are easy to use on all devices, including desktops, tablets, and mobile phones.
- Consistent design language: Both Bootstrap and Material UI follow a consistent design language and visual style, which makes it easy for developers to create a cohesive and consistent UI for their web applications. This can improve the user experience and help to build trust and credibility with users.
- Accessibility: Both Bootstrap and Material UI are designed with accessibility in mind, which means that they offer features and best practices to make web applications more accessible to users with disabilities. This includes support for screen readers, keyboard navigation, and more.
- Active development and community support: Both Bootstrap and Material UI are actively developed and have large communities of users and contributors. This means that developers can benefit from ongoing improvements, bug fixes, and new features, as well as access to support and resources from other users and contributors.