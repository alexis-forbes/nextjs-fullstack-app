## Javascript refresher
Case sensitive: Javascript is case sensitive, meaning that it differentiates between uppercase and lowercase letters.
- Javascript can be executed in many invironments:
Browser (client-side): as part of the website, the code gets executed inside the browser (i.e., on the machine of the user)
Any computer (server-side):  thanks to Node.js or Deno, it can be executed directly on the machine.
Mobile devices: through embedded websites with extra tech like Capacitor or React Native you can execute code on mobile devices.

Javascript is a dynamic language, which means that it's executed at runtime.
This means that the code is executed line by line, and the result of each line can affect the next one.

- Adding Javascript to a website:
1. Inline: inside the HTML file, using the <script> tag.
Tradeoff: it's not recommended to use inline scripts because it makes the code harder to maintain.
Add it to HTML code.
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My first website</title>
    <script>
      console.log('Hello World!');
    </script>
  </head>
</html>
```
2. External: in a separate file, using the <script> tag  import with the src attribute.
Benefits: it's easier to maintain and reuse the code.

Add it to HTML code.
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My first website</title>
    <script src="script.js"></script>
  </head>
</html>
```
Extra attributes:
- async: the script is executed asynchronously.
- defer: the script is executed after the rest of the HTML is read and parsed. Ensures if script needs to load HTML code makes sure they are available. For e.g. if script needs to load a button, it makes sure the button is available.
- type: the type of the script (e.g., "text/javascript" or "module"). Type module makes sure this JS file is a module and can be imported in other files.
import code from script a into script b.
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My first website</title>
    <script src="script-a.js" type="module"></script>
    <script src="script-b.js" type="module"></script>
  </head>
</html>
```
## React Projects
In a React project we would never use the <script> tag to add Javascript to the project. Instead, we would use the import/export syntax to import the code we need.
Why? Because React projects use a build process which compiles the code and bundles it together (injecting script tags into html out of the box). This process is called transpiling and bundling.
It makes the code more efficient and easier to maintain.

- Build process: the process of transforming the code from the development environment to the production and executed in the browser.
The build process includes:
1. Transpiling: transforming the code from a high-level language to a lower-level language.
2. Bundling: combining multiple files into a single file.
3. Minification: removing unnecessary characters from the code (e.g., spaces, comments).
4. Source maps: mapping the code in the browser to the original code in the development
environment.

react-scripts: provides tool that take code and transform it before it is injected in the HTML file as a script tag and then into the browser.
You can see this in the browser inspect element, in the sources tab, you can see the original code in the src folder.

Raw, unprocessed React code won't execute in the browser.
To enable JSX syntax in the browser, a build process needs to happen through tools like Vite.
Node.js is necessary because it is used to run the build process.
We need to use the Babel transpiler. Babel is a tool that converts JSX code into regular JavaScript code.
Code is also minified and bundled together to make it more efficient and serve less code to the user.

The build process also adds the file extensions to the imports, so you don't have to specify them.

## Import and Export
For these import and export keywords to work, the files need to be modules. Specified in package.json normally.
```json
{
  "type": "module"
}
```
Modules: are files that contain code that can be imported and exported.

Benefits of modules:
1. Encapsulation: allows you to encapsulate code in separate files.
2. Reusability: allows you to reuse code across multiple files.
3. Maintainability: makes it easier to maintain code by splitting it into smaller files.
4. Scalability: makes it easier to scale code by adding new files.
5. Collaboration: makes it easier to collaborate with other developers by sharing files.
6. Organization: makes it easier to organize code by grouping related files together.

Best practice to split code between files.
- Export: allows you to export a variable, function, or class from a file.
- Import: allows you to import a variable, function, or class from another file.
Types of exports:
1. Default export: allows you to export a single variable, function, or class from a file.
Only one default export per file, used when you want to export a single value from a file.
Then, when you import it, you can name it whatever you want and you don't need to use curly braces.
2. Named export: allows you to export multiple variables, functions, or classes from a file.
3. Mixed export: allows you to export a default export and named exports from a file.
4. Re-export: allows you to export a variable, function, or class that was previously exported from another file.

Types of imports:
3. Dynamic import: allows you to import a module only when it's needed.
4. Import.meta.url: allows you to get the URL of the current module.
5. Import maps: allows you to map import paths to URLs.
6. Import assertions: allows you to specify the type of the imported module.
7. Import.meta.glob: allows you to import multiple modules using a glob pattern.
8. Import.meta.globEager: allows you to import multiple modules using a glob pattern eagerly.
9. Import.meta.globSync: allows you to import multiple modules using a glob pattern synchronously.
10. Import.meta.resolve: allows you to resolve a module URL.
11. Import.meta.resolveSync: allows you to resolve a module URL synchronously.

## Variables and values
Variables: are containers that store values.
Values: are data that can be stored in variables.
Types of values:
1. Primitive values: are immutable values that are stored directly in memory.
2. Reference values: are mutable values that are stored by reference in memory.

- String: a sequence of characters enclosed in single or double quotes.
- Number: a numeric value without quotes.
- Boolean: a logical value that is either true or false.
- Null: a special value that represents the absence of a value. Resetting a variable to null is a good practice.
- Undefined: a special value that represents the absence of a value.

Rules and recommendations for naming variables:
1. Case sensitivity: variables are case-sensitive.
2. Naming conventions: use camelCase for variable names.
3. Keywords: avoid using reserved keywords as variable names like let, const, var, function, return, if, else, etc.
4. Meaningful names: use descriptive names for variables.
5. Consistency: use consistent naming conventions for variables.
6. Readability: use readable names for variables.
7. Scope: use variables with the appropriate scope.
8. Must not contain whitespace or special characters except for underscores and $.
9. Must not start with a number.
10. Should describe what the thing it identifies contains or does.

const: are variables that cannot be reassigned. Read only variables.
let: allows you to declare a variable that can be reassigned.


## Operators:
Symbols that perform operations on values.
### 1. Arithmetic Operators
**Explanation**: Perform mathematical calculations.
```javascript
let a = 10;
let b = 5;
console.log(a + b);  // Addition: 15
console.log(a - b);  // Subtraction: 5
console.log(a * b);  // Multiplication: 50
console.log(a / b);  // Division: 2
console.log(a % b);  // Modulus (remainder): 0
```

### 2. Assignment Operators
**Explanation**: Assign values to variables.
```javascript
let x = 10;     // Basic assignment
x += 5;         // Same as: x = x + 5, result: 15
x -= 3;         // Same as: x = x - 3, result: 12
x *= 2;         // Same as: x = x * 2, result: 24
x /= 4;         // Same as: x = x / 4, result: 6
```

### 3. Comparison Operators
**Explanation**: Compare values and return true or false.
```javascript
let a = 5, b = 10;
console.log(a == b);   // Equal to: false
console.log(a != b);   // Not equal to: true
console.log(a < b);    // Less than: true
console.log(a > b);    // Greater than: false
console.log(a <= b);   // Less than or equal to: true
console.log(a >= b);   // Greater than or equal to: false
console.log(a === b);  // Strict equal (value and type): false
console.log(a !== b);  // Strict not equal: true
```

### 4. Logical Operators
**Explanation**: Combine multiple conditions.
```javascript
let x = true, y = false;
console.log(x && y);  // Logical AND: false (both must be true)
console.log(x || y);  // Logical OR: true (at least one must be true)
console.log(!x);      // Logical NOT: false (inverts the value)
```

### 5. Bitwise Operators
**Explanation**: Perform operations on individual bits of numbers.
```javascript
let a = 5;  // 101 in binary
let b = 3;  // 011 in binary

console.log(a & b);   // Bitwise AND: 1 (001 in binary)
console.log(a | b);   // Bitwise OR: 7 (111 in binary)
console.log(a ^ b);   // Bitwise XOR: 6 (110 in binary)
console.log(~a);      // Bitwise NOT: -6
console.log(a << 1);  // Left shift: 10 (1010 in binary)
console.log(a >> 1);  // Right shift: 2 (010 in binary)
```

### 6. String Operators
**Explanation**: Combine strings.
```javascript
let firstName = "John";
let lastName = "Doe";
let fullName = firstName + " " + lastName;  // Concatenation
console.log(fullName);  // Output: John Doe

// Template literals (ES6)
let greeting = `Hello, ${firstName}!`;
console.log(greeting);  // Output: Hello, John!
```

### 7. Conditional (Ternary) Operator
**Explanation**: Shorthand for if-else statements.
```javascript
let age = 20;
let message = age >= 18 ? "You can vote" : "Too young to vote";
console.log(message);  // Output: You can vote
```

### 8. Comma Operator
**Explanation**: Evaluates multiple expressions and returns the last one.
```javascript
let x = (1, 2, 3, 4, 5);
console.log(x);  // Output: 5

// Often used in for loops
for (let i = 0, j = 10; i < 5; i++, j--) {
    console.log(i, j);  // Outputs pairs: 0,10  1,9  2,8  3,7  4,6
}
```

### 9. Unary Operators
**Explanation**: Act on a single operand.
```javascript
let x = 5;
console.log(+x);    // Unary plus: 5 (converts to number)
console.log(-x);    // Unary minus: -5 (negates the value)
console.log(++x);   // Pre-increment: 6 (increments then returns)
console.log(x++);   // Post-increment: 6 (returns then increments)
console.log(x);     // 7 (after post-increment)
```

### 10. Relational Operators
**Explanation**: Compare relationships between values.
```javascript
let arr = [1, 2, 3];
let obj = { name: "John" };

console.log("name" in obj);    // true (property exists in object)
console.log(2 in arr);         // true (index exists in array)
console.log(arr instanceof Array);  // true (arr is instance of Array)
```

### 11. Exponentiation Operator
**Explanation**: Raises a number to the power of another.
```javascript
let result = 2 ** 3;  // 2 raised to power 3
console.log(result);  // Output: 8

let base = 10;
let exponent = 2;
console.log(base ** exponent);  // Output: 100
```

### 12. Nullish Coalescing Operator
**Explanation**: Returns right-hand value only if left is null/undefined.
```javascript
let user = {
    name: "John",
    age: 0
};

let name = user.name ?? "Anonymous";  // "John"
let age = user.age ?? 18;            // 0 (not null, so used)
let city = user.city ?? "Unknown";   // "Unknown" (user.city is undefined)
```

### 13. Optional Chaining Operator
**Explanation**: Safely access nested properties without errors.
```javascript
let user = {
    profile: {
        name: "John"
    }
};

// Without optional chaining (can cause errors)
// let city = user.profile.address.city; // Error!

// With optional chaining
let city = user.profile?.address?.city;  // undefined (no error)
let name = user.profile?.name;  // "John"
```

### 14. Destructuring Assignment
**Explanation**: Extract values from arrays or objects into variables.
```javascript
// Array destructuring
let [a, b] = [1, 2];
console.log(a, b);  // 1 2

// Object destructuring
let {name, age} = {name: "John", age: 30};
console.log(name, age);  // John 30

// With default values
let [x, y, z = 3] = [1, 2];
console.log(x, y, z);  // 1 2 3
```

### 15. Spread Syntax
**Explanation**: The spread operator (`...`) expands an iterable (like an array or string)
into individual elements. It's like unpacking a collection into its parts.
```javascript
// In arrays - combines arrays
let fruits = ['apple', 'banana'];
let moreFruits = ['orange', 'grape'];
let allFruits = [...fruits, ...moreFruits];
console.log(allFruits); // ['apple', 'banana', 'orange', 'grape']

// Copy arrays (creates a new array, not just a reference)
let originalArray = [1, 2, 3];
let copyOfArray = [...originalArray];
originalArray.push(4);
console.log(copyOfArray); // [1, 2, 3] (unchanged)

// In objects - merges properties
let personBasics = {name: 'John', age: 30};
let personDetails = {job: 'Developer', country: 'USA'};
let fullPerson = {...personBasics, ...personDetails};
console.log(fullPerson); // {name: 'John', age: 30, job: 'Developer', country: 'USA'}

// Override properties
let defaults = {theme: 'dark', fontSize: 12};
let userPreferences = {theme: 'light'};
let settings = {...defaults, ...userPreferences}; // Later properties override earlier ones
console.log(settings); // {theme: 'light', fontSize: 12}

// With function arguments
function makeRainbow(color1, color2, color3) {
    return `Rainbow: ${color1}, ${color2}, ${color3}`;
}
let colors = ['red', 'yellow', 'blue'];
console.log(makeRainbow(...colors)); // "Rainbow: red, yellow, blue"
```

### 16. Rest Syntax
**Explanation**: The rest operator (`...`) collects multiple elements and "condenses" them
into a single array. It's like packing elements together.
```javascript
// In function parameters - gather remaining arguments
function sum(first, second, ...others) {
    console.log('First:', first);
    console.log('Second:', second);
    console.log('Others:', others); // An array of remaining arguments

    return first + second + others.reduce((sum, num) => sum + num, 0);
}

console.log(sum(1, 2, 3, 4, 5)); // First: 1, Second: 2, Others: [3,4,5], Result: 15

// In array destructuring - collect remaining elements
let [winner, runnerUp, ...participants] = ['Alice', 'Bob', 'Charlie', 'Dave', 'Eve'];
console.log(winner); // 'Alice'
console.log(runnerUp); // 'Bob'
console.log(participants); // ['Charlie', 'Dave', 'Eve']

// In object destructuring - collect remaining properties
let {id, name, ...details} = {
    id: 123,
    name: 'Laptop',
    price: 999,
    brand: 'TechBrand',
    inStock: true
};
console.log(id); // 123
console.log(name); // 'Laptop'
console.log(details); // {price: 999, brand: 'TechBrand', inStock: true}
```

### 17. Typeof Operator
```javascript
console.log(typeof "hello");    // "string"
console.log(typeof 42);         // "number"
console.log(typeof true);       // "boolean"
console.log(typeof undefined);  // "undefined"
console.log(typeof {});         // "object"
console.log(typeof function(){}); // "function"
```

### 18-30: Additional JavaScript Concepts
These include operations like deleting properties, creating instances, and working with async code:

```javascript
// Delete operator
let person = {name: "John", age: 30};
delete person.age;  // Removes the age property
console.log(person);  // {name: "John"}

// New operator
class Person {
  constructor(name) {
    this.name = name;
  }
}
let john = new Person("John");  // Creates a new Person instance

// Async/Await example
async function fetchData() {
  let response = await fetch('https://api.example.com/data');
  let data = await response.json();
  return data;
}
```

### 31-40: Data Structures
JavaScript provides built-in data structures with specific use cases:

```javascript
// Set (stores unique values)
let uniqueNumbers = new Set([1, 2, 2, 3, 3]);
console.log([...uniqueNumbers]);  // [1, 2, 3]

// Map (key-value pairs with any type of keys)
let userMap = new Map();
userMap.set('name', 'John');
userMap.set(42, 'answer');
console.log(userMap.get('name'));  // "John"

// Array methods
let fruits = ['apple', 'banana', 'cherry'];
fruits.push('date');  // Adds to end
fruits.pop();         // Removes from end
let filtered = fruits.filter(fruit => fruit.length > 5);  // ["banana", "cherry"]
```

### 41-50: Functions, Classes, and Web APIs
```javascript
// Function example
function greet(name) {
  return `Hello, ${name}!`;
}

// Class example
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  area() {
    return this.width * this.height;
  }
}

// DOM manipulation
document.getElementById('myButton').addEventListener('click', function() {
  alert('Button clicked!');
});
```

### 51-62: Web Technologies
```javascript
// JSON handling
let person = {name: "John", age: 30};
let jsonString = JSON.stringify(person);  // Convert to JSON string
let parsedPerson = JSON.parse(jsonString);  // Convert back to object

// LocalStorage
localStorage.setItem('username', 'john_doe');  // Store data
let username = localStorage.getItem('username');  // Retrieve data

// Canvas drawing (2D)
const canvas = document.getElementById('myCanvas');
const ctx = canvas.getContext('2d');
ctx.fillStyle = 'blue';
ctx.fillRect(10, 10, 150, 100);  // Draw a blue rectangle
```

## 63. SVG (Scalable Vector Graphics)
**Explanation**: SVG is an XML-based format for creating vector graphics. Unlike raster formats (like PNG), SVGs can scale to any size without losing quality.

```javascript
// Creating an SVG element with JavaScript
function createCircle() {
    // Create SVG namespace elements
    let svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
    svg.setAttribute("width", "200");
    svg.setAttribute("height", "200");

    let circle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
    circle.setAttribute("cx", "100");
    circle.setAttribute("cy", "100");
    circle.setAttribute("r", "80");
    circle.setAttribute("fill", "purple");

    svg.appendChild(circle);
    document.body.appendChild(svg);
}

// Manipulating SVG with JavaScript
function animateCircle() {
    // Select an existing SVG circle
    let circle = document.querySelector('circle');

    // Animate its radius
    let radius = 20;
    let growing = true;

    setInterval(() => {
        if (growing) {
            radius += 2;
            if (radius >= 80) growing = false;
        } else {
            radius -= 2;
            if (radius <= 20) growing = true;
        }

        circle.setAttribute("r", radius);
    }, 50);
}

// SVG can also be added directly in HTML:
/*
<svg width="200" height="100">
    <rect width="100" height="80" x="50" y="10" fill="blue" />
    <text x="100" y="50" text-anchor="middle" fill="white">SVG Text</text>
</svg>
*/

// Working with SVG Paths
function drawPath() {
    let svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
    svg.setAttribute("width", "300");
    svg.setAttribute("height", "200");

    let path = document.createElementNS("http://www.w3.org/2000/svg", "path");
    path.setAttribute("d", "M10,90 Q90,10 170,90 T330,90");
    path.setAttribute("fill", "none");
    path.setAttribute("stroke", "black");
    path.setAttribute("stroke-width", "2");

    svg.appendChild(path);
    document.body.appendChild(svg);
}
```

## 64. WebRTC (Web Real-Time Communication)
**Explanation**: WebRTC is a technology that enables direct peer-to-peer communication
between browsers for audio, video, and data sharing without requiring plugins or third-party software.

```javascript
// Basic WebRTC setup for video calling
async function startVideoCall() {
    try {
        // 1. Get local media stream (camera and microphone)
        const localStream = await navigator.mediaDevices.getUserMedia({
            audio: true,
            video: true
        });

        // Display local video in a <video> element
        const localVideo = document.getElementById('localVideo');
        localVideo.srcObject = localStream;

        // 2. Create peer connection
        const peerConnection = new RTCPeerConnection({
            iceServers: [{ urls: 'stun:stun.l.google.com:19302' }]
        });

        // Add local stream tracks to the connection
        localStream.getTracks().forEach(track => {
            peerConnection.addTrack(track, localStream);
        });

        // 3. Handle incoming remote stream
        peerConnection.ontrack = event => {
            const remoteVideo = document.getElementById('remoteVideo');
            if (remoteVideo.srcObject !== event.streams[0]) {
                remoteVideo.srcObject = event.streams[0];
                console.log('Received remote stream');
            }
        };

        // 4. Exchange signaling data (offer/answer)
        // Note: In real apps, you'd use a signaling server to exchange this data

        // Create offer
        const offer = await peerConnection.createOffer();
        await peerConnection.setLocalDescription(offer);

        console.log('Offer created:', offer);
        // Send this offer to the remote peer (through your signaling channel)

        // Once you receive an answer from the remote peer:
        // await peerConnection.setRemoteDescription(receivedAnswer);

        // 5. Handle ICE candidates
        peerConnection.onicecandidate = event => {
            if (event.candidate) {
                console.log('New ICE candidate:', event.candidate);
                // Send this candidate to the remote peer (through your signaling channel)
            }
        };

    } catch (error) {
        console.error('Error starting video call:', error);
    }
}

// Data channel example
function setupDataChannel() {
    const peerConnection = new RTCPeerConnection();

    // Create a data channel
    const dataChannel = peerConnection.createDataChannel("chat");

    // Set up data channel event handlers
    dataChannel.onopen = () => {
        console.log("Data channel is open");

        // Send a message
        dataChannel.send("Hello from the data channel!");
    };

    dataChannel.onmessage = event => {
        console.log("Received message:", event.data);
    };

    dataChannel.onclose = () => {
        console.log("Data channel closed");
    };

    // On the receiving end, listen for data channels
    peerConnection.ondatachannel = event => {
        const receivedChannel = event.channel;

        receivedChannel.onmessage = messageEvent => {
            console.log("Received on the other side:", messageEvent.data);
            receivedChannel.send("Message received!");
        };
    };
}

// Screen sharing with WebRTC
async function shareScreen() {
    try {
        // Get screen sharing stream
        const screenStream = await navigator.mediaDevices.getDisplayMedia({
            video: true
        });

        // Display the screen in a video element
        const screenVideo = document.getElementById('screenVideo');
        screenVideo.srcObject = screenStream;

        // You would then add this stream to your peer connection
        // to share it with the remote peer

        // Handle stream ending (user stops sharing)
        const videoTrack = screenStream.getVideoTracks()[0];
        videoTrack.onended = () => {
            console.log('User stopped sharing screen');
            screenVideo.srcObject = null;
        };

    } catch (error) {
        console.error('Error sharing screen:', error);
    }
}
```


### Functions:
Can either be created with the function keyword or as arrow functions.
Code will be executed when the function is called.
Functions in JavaScript are blocks of reusable code designed to perform a specific task. They are a fundamental building block and are treated as first-class citizens, meaning they can be:
- Assigned to variables
- Passed as arguments to other functions
- Returned from other functions
- Stored in data structures

### Types of Function Definitions

#### 1. Function Declarations

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
```

**Key characteristics:**
- Hoisted to the top of their scope (can be called before they're defined)
- Create a variable with the function name
- Have a named function for stack traces
- Can access `this` and `arguments` objects

#### 2. Function Expressions

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};

// Named function expression
const greet = function sayHello(name) {
    return `Hello, ${name}!`;
};
```

**Key characteristics:**
- Not hoisted (cannot be called before they're defined)
- The variable is hoisted, but its value is initially undefined
- Named function expressions are useful for recursion and clearer stack traces
- Can access `this` and `arguments` objects

#### 3. Arrow Functions
Typical arrow function syntax: `(parameters) => expression`
Normally used for short, concise functions where you don't create a name (anonymous functions).

```javascript
// Simple arrow function
const greet = name => `Hello, ${name}!`;

// Multiple parameters
const add = (a, b) => a + b;

// No parameters
const sayHi = () => "Hi there!";

// Multi-line arrow function
const formatGreeting = name => {
    const formattedName = name.toUpperCase();
    return `Hello, ${formattedName}!`;
};
```

**Key characteristics:**
- More concise syntax
- Don't have their own `this` (inherit from parent scope)
- Don't have `arguments` object
- Cannot be used as constructors (no `new` keyword)
- Can't change `this` with call, apply, or bind
- Great for short callback functions and preserving context

### Function Parameters and Arguments

#### Default Parameters

```javascript
function greet(name = "Guest", greeting = "Hello") {
    return `${greeting}, ${name}!`;
}

console.log(greet());               // "Hello, Guest!"
console.log(greet("John"));         // "Hello, John!"
console.log(greet("John", "Hi"));   // "Hi, John!"
```

#### Rest Parameters

```javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4, 5));  // 15

// Combined with regular parameters
function processItems(category, ...items) {
    console.log(`Category: ${category}`);
    console.log(`Items: ${items.join(', ')}`);
    return items.length;
}

processItems("Fruits", "Apple", "Banana", "Orange");
// Category: Fruits
// Items: Apple, Banana, Orange
// Returns: 3
```

#### Parameter Destructuring

```javascript
// Object destructuring in parameters
function displayPerson({name, age, location = "Unknown"}) {
    console.log(`${name} is ${age} years old from ${location}`);
}

displayPerson({name: "Alice", age: 30, location: "New York"});
displayPerson({name: "Bob", age: 25});  // location uses default

// Array destructuring in parameters
function displayCoordinates([x, y, z = 0]) {
    console.log(`X: ${x}, Y: ${y}, Z: ${z}`);
}

displayCoordinates([10, 20, 30]);
displayCoordinates([5, 15]);  // z uses default
```

## Callback Functions

**Definition**: A callback function is a function passed into another function as an argument, which is then invoked inside the outer function.

```javascript
// Basic callback example
function processData(data, callback) {
    // Process data...
    const processedData = data.toUpperCase();

    // Then execute the callback with the result
    callback(processedData);
}

// Using the function with a callback
processData("hello", function(result) {
    console.log(result);  // "HELLO"
});

// Using an arrow function as callback
processData("world", result => {
    console.log(result);  // "WORLD"
});
```

### Callbacks in Event Handling

```javascript
// Adding event listener with callback
document.getElementById("myButton").addEventListener("click", function(event) {
    console.log("Button clicked!", event);
});

// With arrow function
document.getElementById("myButton").addEventListener("click", (event) => {
    console.log("Button clicked with arrow function!", event);
});

// Referencing a named function
function handleClick(event) {
    console.log("Handled click!", event);
}

document.getElementById("myButton").addEventListener("click", handleClick);
```

### Optional Chaining with Function Calls

Optional chaining (`?.`) allows you to safely call methods that might not exist without causing an error.

```javascript
// Object with an onClick method
const component = {
    name: "Button",
    onClick: function(event) {
        console.log("Button clicked", event);
    }
};

// Object without onClick method
const emptyComponent = {
    name: "EmptyButton"
};

// Safe method calls with optional chaining
component.onClick?.({type: "click"}); // Calls the onClick function
emptyComponent.onClick?.({type: "click"}); // Nothing happens (undefined)

// With event object
function handleEvent(event) {
    // Safely call event methods that might not exist
    event.stopPropagation?.();
    event.preventDefault?.();

    // Process the event...
    console.log("Event handled:", event.type);
}
```

## Event Handling in React-like Environments

### Passing Functions vs. Function Calls in Event Handlers

This is a common source of confusion, especially in React and similar frameworks:

#### 1. Passing the Function Reference
```jsx
// Correct: Pass the function reference
<button onClick={handleClick}>Click me</button>
```
- Provides a reference to the function
- The function will be called when the event occurs
- The event object is automatically passed to the function

#### 2. Calling the Function Immediately (Usually Wrong)
```jsx
// Incorrect in most cases: Function is called during render
<button onClick={handleClick()}>Click me</button>
```
- This calls the function immediately during rendering
- The return value (if any) becomes the event handler
- The function doesn't receive the event object
- Often leads to bugs or unexpected behavior

#### 3. Using an Arrow Function Wrapper
```jsx
// Correct: Arrow function wrapper
<button onClick={() => handleClick()}>Click me</button>

// Passing custom arguments
<button onClick={() => handleClick(id, name)}>Click me</button>

// Passing the event object too
<button onClick={(e) => handleClick(id, name, e)}>Click me</button>
```
- Creates a new function that calls your handler
- Allows passing additional arguments
- Useful when you need to pass parameters
- Creates a new function on each render (potential performance impact)

### When to Use Each Approach:

1. **Use `onClick={handleClick}`** when:
   - You only need the event object
   - No additional parameters are needed
   - Best for performance

2. **Use `onClick={() => handleClick()}`** when:
   - You need to pass custom arguments: `onClick={() => handleClick(id, name)}`
   - You need to call multiple functions: `onClick={() => { handleClick(); trackAnalytics(); }}`
   - You need to transform the event: `onClick={(e) => handleClick(e.target.value)}`

3. **Avoid `onClick={handleClick()}`** in most cases because:
   - It executes during render, not on click
   - May cause infinite render loops if state is updated in the function
   - May not work as expected for event handling

## Event Delegation and Event Bubbling

### Event Bubbling

**Definition**: Event bubbling is a mechanism where an event triggered on a nested element "bubbles up" through its ancestors in the DOM tree.

```javascript
// HTML structure
// <div id="parent">
//   <div id="child">
//     <button id="button">Click me</button>
//   </div>
// </div>

// Adding event listeners to each element
document.getElementById("button").addEventListener("click", function(e) {
    console.log("Button clicked");
    // e.stopPropagation(); // Uncomment to stop bubbling
});

document.getElementById("child").addEventListener("click", function() {
    console.log("Child div clicked");
});

document.getElementById("parent").addEventListener("click", function() {
    console.log("Parent div clicked");
});

// When button is clicked, the output will be:
// "Button clicked"
// "Child div clicked"
// "Parent div clicked"
```

### Event Delegation

**Definition**: Event delegation is a technique where you attach a single event listener
to a parent element instead of multiple listeners on each child element. It leverages event bubbling.

**Benefits**:
- Fewer event listeners = better performance
- Works for dynamically added elements
- Less memory usage
- Simplifies code maintenance

```javascript
// HTML structure
// <ul id="todo-list">
//   <li>Task 1</li>
//   <li>Task 2</li>
//   <li>Task 3</li>
// </ul>

// Instead of adding listeners to each li...
document.getElementById("todo-list").addEventListener("click", function(e) {
    // Check if the clicked element is an li
    if (e.target.tagName === "LI") {
        console.log("Clicked on:", e.target.textContent);
        e.target.classList.toggle("completed");
    }
});

// Now even if we add new items dynamically, they'll still work
const newItem = document.createElement("li");
newItem.textContent = "Task 4";
document.getElementById("todo-list").appendChild(newItem);
```

### Real-world Example: Dynamic List with Event Delegation

```javascript
// HTML structure
// <div id="app">
//   <input id="new-task" placeholder="Add new task">
//   <button id="add-btn">Add</button>
//   <ul id="task-list"></ul>
// </div>

document.addEventListener("DOMContentLoaded", function() {
    const taskInput = document.getElementById("new-task");
    const addButton = document.getElementById("add-btn");
    const taskList = document.getElementById("task-list");

    // Add new tasks
    addButton.addEventListener("click", function() {
        if (taskInput.value.trim() !== "") {
            addTask(taskInput.value);
            taskInput.value = "";
        }
    });

    // Event delegation for the task list
    taskList.addEventListener("click", function(e) {
        // If delete button is clicked
        if (e.target.classList.contains("delete-btn")) {
            e.target.parentElement.remove();
        }
        // If task text is clicked
        else if (e.target.tagName === "SPAN") {
            e.target.classList.toggle("completed");
        }
    });

    function addTask(text) {
        const li = document.createElement("li");
        li.innerHTML = `
            <span>${text}</span>
            <button class="delete-btn">Delete</button>
        `;
        taskList.appendChild(li);
    }
});
```

### Event Phases

Events in the DOM actually go through three phases:

1. **Capture Phase**: From the window down to the target element
2. **Target Phase**: The target element itself
3. **Bubbling Phase**: From the target back up to the window

```javascript
// To listen during the capture phase, set the third parameter to true
document.getElementById("parent").addEventListener("click", function(e) {
    console.log("Parent - Capture phase");
}, true);

document.getElementById("child").addEventListener("click", function(e) {
    console.log("Child - Capture phase");
}, true);

// Regular listeners (bubbling phase)
document.getElementById("parent").addEventListener("click", function(e) {
    console.log("Parent - Bubbling phase");
});

document.getElementById("child").addEventListener("click", function(e) {
    console.log("Child - Bubbling phase");
});

// When child is clicked, the output order will be:
// "Parent - Capture phase"
// "Child - Capture phase"
// "Child - Bubbling phase"
// "Parent - Bubbling phase"
```

## Advanced Function Concepts

### Immediately Invoked Function Expression (IIFE)

```javascript
// IIFE - creates a private scope
(function() {
    const privateVar = "I'm private";
    console.log(privateVar);  // Accessible
})();

// console.log(privateVar);  // Error: privateVar is not defined

// IIFE with parameters
(function(name) {
    console.log(`Hello, ${name}!`);
})("John");  // Output: Hello, John!

// Arrow function IIFE
(() => {
    console.log("IIFE with arrow function");
})();
```

### Higher-Order Functions

Functions that take other functions as arguments or return functions.

```javascript
// Function that returns a function
function createMultiplier(factor) {
    return function(number) {
        return number * factor;
    };
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5));  // 10
console.log(triple(5));  // 15

// Higher-order function with array methods
const numbers = [1, 2, 3, 4, 5];

// map takes a function as an argument
const squared = numbers.map(function(num) {
    return num * num;
});

// Using arrow function
const doubled = numbers.map(num => num * 2);

console.log(squared);  // [1, 4, 9, 16, 25]
console.log(doubled);  // [2, 4, 6, 8, 10]
```

## Objects and classes
Objects are one of JavaScript's most powerful features—collections of related data and/or
functionality stored as key-value pairs. They allow you to group related information and behavior
together in a structured way.

### Object Basics

An object is an unordered collection of key-value pairs, where each key is a string (or Symbol) and each value can be any valid JavaScript data type, including other objects or functions.

```javascript
// Basic object literal
const person = {
    firstName: "Max",
    lastName: "Miller",
    age: 30,
    email: "max@example.com",
    isEmployed: true,
    hobbies: ["reading", "cycling", "photography"],
    address: {
        street: "123 Main St",
        city: "Boston",
        country: "USA"
    }
};
```

### Accessing Object Properties

```javascript
// Dot notation
console.log(person.firstName);  // "Max"
console.log(person.address.city);  // "Boston"

// Bracket notation (useful when property name is stored in a variable or contains special characters)
console.log(person["lastName"]);  // "Miller"

const propertyName = "age";
console.log(person[propertyName]);  // 30

// With properties that have spaces or special characters
const product = {
    "product name": "Laptop",
    "product-id": "LP2023"
};

console.log(product["product name"]);  // "Laptop"
console.log(product["product-id"]);  // "LP2023"
```

### Methods in Objects

Methods are functions that are properties of an object.

```javascript
const user = {
    name: "Max",
    age: 30,

    // Method defined using function expression
    greet: function() {
        console.log("Hi, I am " + this.name);
    },

    // Shorthand method syntax (ES6)
    sayAge() {
        console.log("I am " + this.age + " years old");
    },

    // Arrow function (behaves differently with 'this')
    showBio: () => {
        // 'this' refers to the outer scope, not the user object
        console.log("This user is " + this.name);  // this.name will likely be undefined
    }
};

user.greet();  // "Hi, I am Max"
user.sayAge();  // "I am 30 years old"
```

### The `this` Keyword

`this` is a crucial concept in JavaScript that refers to the current execution context.

1. **In methods**: `this` refers to the object the method was called on
2. **In regular functions**: `this` refers to the global object (or `undefined` in strict mode)
3. **In arrow functions**: `this` retains the value from the enclosing lexical context
4. **In event handlers**: `this` typically refers to the element that triggered the event

```javascript
const person = {
    name: "Max",

    regularMethod: function() {
        console.log("Regular method:", this.name);  // "Max"

        function innerFunction() {
            console.log("Inner function:", this.name);  // undefined (or global object)
        }
        innerFunction();

        // Solution 1: Store reference to 'this'
        const self = this;
        function innerFunction2() {
            console.log("Using self:", self.name);  // "Max"
        }
        innerFunction2();

        // Solution 2: Arrow function preserves 'this'
        const innerArrow = () => {
            console.log("Arrow function:", this.name);  // "Max"
        };
        innerArrow();
    },

    arrowMethod: () => {
        // 'this' here isn't the person object, it's from the outer scope
        console.log("Arrow method:", this.name);  // undefined
    }
};

person.regularMethod();
person.arrowMethod();

// Explicitly setting 'this' with call, apply, bind
function greet() {
    console.log(`Hello, ${this.name}!`);
}

const max = { name: "Max" };
const anna = { name: "Anna" };

greet.call(max);  // "Hello, Max!"
greet.apply(anna);  // "Hello, Anna!"

const maxGreet = greet.bind(max);
maxGreet();  // "Hello, Max!"
```

### Object Dynamic Properties

Objects in JavaScript are dynamic, allowing you to add, modify, and delete properties at runtime.

```javascript
const car = {
    make: "Toyota",
    model: "Corolla"
};

// Adding new properties
car.year = 2022;
car["color"] = "blue";

console.log(car);  // {make: "Toyota", model: "Corolla", year: 2022, color: "blue"}

// Modifying existing properties
car.model = "Camry";
console.log(car.model);  // "Camry"

// Deleting properties
delete car.color;
console.log(car);  // {make: "Toyota", model: "Camry", year: 2022}

// Checking if a property exists
console.log("model" in car);  // true
console.log("color" in car);  // false
console.log(car.hasOwnProperty("year"));  // true
```

### Object Property Descriptors

JavaScript objects have property descriptors that control how properties behave.

```javascript
const product = {
    name: "Laptop",
    price: 999
};

// Get property descriptor
console.log(Object.getOwnPropertyDescriptor(product, "name"));
// {value: "Laptop", writable: true, enumerable: true, configurable: true}

// Define property with custom descriptor
Object.defineProperty(product, "discount", {
    value: 0.1,
    writable: false,  // Can't change the value
    enumerable: true,  // Shows up in loops
    configurable: false  // Can't delete or change descriptor
});

product.discount = 0.2;  // Ignored in non-strict mode, throws error in strict mode
console.log(product.discount);  // Still 0.1

// Define multiple properties at once
Object.defineProperties(product, {
    tax: {
        value: 0.08,
        writable: true
    },
    inStock: {
        value: true,
        writable: true
    }
});
```

### Object Destructuring

Destructuring is a convenient way to extract values from objects into distinct variables.

```javascript
const person = {
    name: "Max",
    age: 30,
    location: {
        city: "Boston",
        country: "USA"
    },
    hobbies: ["reading", "cycling"]
};

// Basic destructuring
const { name, age } = person;
console.log(name, age);  // "Max" 30

// Destructuring with new variable names
const { name: fullName, age: years } = person;
console.log(fullName, years);  // "Max" 30

// Destructuring nested objects
const { location: { city, country } } = person;
console.log(city, country);  // "Boston" "USA"

// With default values
const { salary = 50000, name: userName = "User" } = person;
console.log(salary, userName);  // 50000 "Max"

// Rest pattern in object destructuring
const { name: personName, ...details } = person;
console.log(personName);  // "Max"
console.log(details);  // {age: 30, location: {...}, hobbies: [...]}
```

## Classes in JavaScript

Classes were introduced in ES6 as a syntactic sugar over JavaScript's existing prototype-based inheritance. They provide a cleaner and more familiar syntax for creating objects and dealing with inheritance.

### Class Declaration

```javascript
class Person {
    // Class constructor
    constructor(firstName, lastName, age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }

    // Instance method
    greet() {
        console.log(`Hello, I'm ${this.firstName} ${this.lastName}`);
    }

    // Another method
    haveBirthday() {
        this.age++;
        console.log(`Happy birthday! Now I'm ${this.age} years old`);
    }

    // Getter method
    get fullName() {
        return `${this.firstName} ${this.lastName}`;
    }

    // Setter method
    set fullName(name) {
        const parts = name.split(" ");
        this.firstName = parts[0];
        this.lastName = parts[1] || "";
    }

    // Static method (called on the class, not an instance)
    static createFromFullName(fullName) {
        const [firstName, lastName] = fullName.split(" ");
        return new Person(firstName, lastName, 0);
    }
}

// Creating instances
const max = new Person("Max", "Miller", 30);
const jane = new Person("Jane", "Smith", 25);

// Using methods
max.greet();  // "Hello, I'm Max Miller"
jane.haveBirthday();  // "Happy birthday! Now I'm 26 years old"

// Using getters and setters
console.log(max.fullName);  // "Max Miller"
max.fullName = "Maxwell Johnson";
console.log(max.firstName);  // "Maxwell"
console.log(max.lastName);   // "Johnson"

// Using static methods
const bob = Person.createFromFullName("Bob Wilson");
console.log(bob.fullName);  // "Bob Wilson"
```

### Class Inheritance

Classes can extend other classes to inherit their properties and methods.

```javascript
class Employee extends Person {
    constructor(firstName, lastName, age, position, salary) {
        // Call the parent constructor
        super(firstName, lastName, age);

        // Add new properties
        this.position = position;
        this.salary = salary;
    }

    // Method override
    greet() {
        console.log(`Hello, I'm ${this.firstName} ${this.lastName}, a ${this.position}`);
    }

    // New method specific to Employee
    promote(newPosition, salaryIncrease) {
        this.position = newPosition;
        this.salary += salaryIncrease;
        console.log(`Promoted to ${this.position} with salary ${this.salary}`);
    }
}

const developer = new Employee("Max", "Miller", 30, "Developer", 80000);
developer.greet();  // "Hello, I'm Max Miller, a Developer"
developer.haveBirthday();  // Method inherited from Person
developer.promote("Senior Developer", 20000);  // "Promoted to Senior Developer with salary 100000"

// Check inheritance
console.log(developer instanceof Employee);  // true
console.log(developer instanceof Person);    // true
```

### Private Class Features

ES2020 introduced private class fields and methods using the `#` prefix.

```javascript
class BankAccount {
    // Public field
    owner;

    // Private fields
    #balance = 0;
    #transactions = [];

    constructor(owner, initialDeposit = 0) {
        this.owner = owner;
        if (initialDeposit > 0) {
            this.#deposit(initialDeposit);
        }
    }

    // Public methods
    getBalance() {
        return this.#balance;
    }

    deposit(amount) {
        if (amount <= 0) {
            throw new Error("Deposit amount must be positive");
        }
        this.#deposit(amount);
    }

    withdraw(amount) {
        if (amount <= 0) {
            throw new Error("Withdrawal amount must be positive");
        }
        if (amount > this.#balance) {
            throw new Error("Insufficient funds");
        }
        this.#withdraw(amount);
    }

    // Private methods
    #deposit(amount) {
        this.#balance += amount;
        this.#transactions.push({
            type: "deposit",
            amount,
            date: new Date()
        });
    }

    #withdraw(amount) {
        this.#balance -= amount;
        this.#transactions.push({
            type: "withdrawal",
            amount,
            date: new Date()
        });
    }
}

const account = new BankAccount("Max", 1000);
console.log(account.getBalance());  // 1000
account.deposit(500);
console.log(account.getBalance());  // 1500
account.withdraw(200);
console.log(account.getBalance());  // 1300

// These would throw errors:
// console.log(account.#balance);  // SyntaxError
// account.#deposit(100);          // SyntaxError
```

### The `new` Keyword

The `new` keyword is used to create instances of a class or function constructor.

What happens when `new` is used:
1. A new empty object is created
2. The object's prototype is set to the constructor's prototype
3. The constructor function is called with `this` bound to the new object
4. If the constructor doesn't return an object, the new object is returned

```javascript
// Using 'new' with a class
const max = new Person("Max", "Miller", 30);

// Using 'new' with a constructor function
function Car(make, model, year) {
    this.make = make;
    this.model = model;
    this.year = year;

    this.getDescription = function() {
        return `${this.year} ${this.make} ${this.model}`;
    };
}

const myCar = new Car("Toyota", "Corolla", 2022);
console.log(myCar.getDescription());  // "2022 Toyota Corolla"

// What happens if you forget 'new'
const notACar = Car("Honda", "Civic", 2021);
console.log(notACar);  // undefined (function doesn't return anything)
// The properties were actually added to the global object!
console.log(window.make, window.model);  // "Honda" "Civic" (in a browser)
```

### Factory Functions

An alternative to classes and constructors are factory functions,
which are regular functions that return object instances without using `new`.

```javascript
function createPerson(firstName, lastName, age) {
    return {
        firstName,
        lastName,
        age,

        greet() {
            console.log(`Hello, I'm ${this.firstName} ${this.lastName}`);
        },

        haveBirthday() {
            this.age++;
            console.log(`Happy birthday! Now I'm ${this.age} years old`);
        }
    };
}

const john = createPerson("John", "Doe", 30);
john.greet();  // "Hello, I'm John Doe"

// Closure-based private variables
function createCounter() {
    // Private variable
    let count = 0;

    return {
        increment() {
            count++;
        },
        decrement() {
            count--;
        },
        getCount() {
            return count;
        }
    };
}

const counter = createCounter();
counter.increment();
counter.increment();
console.log(counter.getCount());  // 2
// console.log(counter.count);  // undefined (private)
```

### Object Methods and Prototypes

JavaScript objects inherit methods and properties from their prototype.

```javascript
// Every object inherits from Object.prototype
const obj = {};
console.log(obj.toString());  // "[object Object]"

// Creating a custom prototype
function Animal(name) {
    this.name = name;
}

Animal.prototype.speak = function() {
    console.log(`${this.name} makes a noise.`);
};

function Dog(name, breed) {
    Animal.call(this, name);
    this.breed = breed;
}

// Set up inheritance
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Add/override methods
Dog.prototype.speak = function() {
    console.log(`${this.name} barks!`);
};

Dog.prototype.fetch = function() {
    console.log(`${this.name} fetches the ball.`);
};

const rex = new Dog("Rex", "German Shepherd");
rex.speak();  // "Rex barks!"
rex.fetch();  // "Rex fetches the ball."
```

### Object Composition vs. Inheritance

While inheritance is powerful, composition (building objects by combining simpler objects) is often more flexible.

```javascript
// Object composition with mixins
const swimmer = {
    swim() {
        console.log(`${this.name} is swimming.`);
    }
};

const flyer = {
    fly() {
        console.log(`${this.name} is flying.`);
    }
};

const walker = {
    walk() {
        console.log(`${this.name} is walking.`);
    }
};

// Duck can do all three
const duck = {
    name: "Donald"
};

// Apply mixins
Object.assign(duck, swimmer, flyer, walker);

duck.swim();  // "Donald is swimming."
duck.fly();   // "Donald is flying."
duck.walk();  // "Donald is walking."

// A function to create a bird with needed abilities
function createBird(name, abilities) {
    const bird = { name };

    if (abilities.canSwim) Object.assign(bird, swimmer);
    if (abilities.canFly) Object.assign(bird, flyer);
    if (abilities.canWalk) Object.assign(bird, walker);

    return bird;
}

const penguin = createBird("Pingu", { canSwim: true, canWalk: true, canFly: false });
penguin.swim();  // "Pingu is swimming."
penguin.walk();  // "Pingu is walking."
// penguin.fly();  // Error: fly is not a function
```

## Advanced Object Features

### Object Immutability

JavaScript offers several ways to make objects immutable or restrict changes to them.

```javascript
// Object.freeze() - prevents adding, removing, or changing properties
const frozenObj = Object.freeze({
    name: "Max",
    age: 30
});

frozenObj.age = 31;  // Silently fails in non-strict mode
console.log(frozenObj.age);  // Still 30

// Object.seal() - prevents adding or removing properties, but allows changing existing ones
const sealedObj = Object.seal({
    name: "Jane",
    age: 25
});

sealedObj.age = 26;  // Works
sealedObj.location = "Boston";  // Silently fails
console.log(sealedObj);  // {name: "Jane", age: 26}

// Object.preventExtensions() - prevents adding properties
const restrictedObj = Object.preventExtensions({
    name: "Bob",
    age: 40
});

restrictedObj.age = 41;  // Works
restrictedObj.location = "New York";  // Silently fails
delete restrictedObj.age;  // Works
console.log(restrictedObj);  // {name: "Bob"}
```

### Object.create() and Prototypal Inheritance

`Object.create()` creates a new object with the specified prototype object.

```javascript
// Create an object with custom methods
const personMethods = {
    greet() {
        console.log(`Hello, I'm ${this.name}`);
    },
    haveBirthday() {
        this.age++;
        console.log(`Happy birthday! Now I'm ${this.age} years old`);
    }
};

// Create a person using Object.create()
const person = Object.create(personMethods);
person.name = "Max";
person.age = 30;

person.greet();  // "Hello, I'm Max"

// Factory function using Object.create()
function createPerson(name, age) {
    const person = Object.create(personMethods);
    person.name = name;
    person.age = age;
    return person;
}

const jane = createPerson("Jane", 25);
jane.haveBirthday();  // "Happy birthday! Now I'm 26 years old"
```

### Object Proxies

Proxies let you intercept and customize operations on objects (like property lookup, assignment, etc.).

```javascript
const user = {
    name: "Max",
    age: 30
};

const userProxy = new Proxy(user, {
    // Intercept property access
    get(target, property, receiver) {
        console.log(`Getting ${property}`);
        return Reflect.get(target, property, receiver);
    },

    // Intercept property assignment
    set(target, property, value, receiver) {
        console.log(`Setting ${property} to ${value}`);
        if (property === "age" && typeof value !== "number") {
            throw new TypeError("Age must be a number");
        }
        return Reflect.set(target, property, value, receiver);
    },

    // Intercept property deletion
    deleteProperty(target, property) {
        console.log(`Deleting ${property}`);
        return Reflect.deleteProperty(target, property);
    }
});

console.log(userProxy.name);  // "Getting name", then "Max"
userProxy.age = 31;           // "Setting age to 31"
// userProxy.age = "thirty";  // Throws TypeError: Age must be a number
delete userProxy.name;        // "Deleting name"
```

## Arrays and Array Methods

Arrays in JavaScript are ordered collections of values. They offer specialized methods for data manipulation and transformation, making them one of the most powerful data structures in the language.

### Array Basics

```javascript
// Creating arrays
const numbers = [1, 2, 3, 4, 5];
const mixed = [42, "hello", true, null, {name: "Max"}, [1, 2]];
const empty = [];
const prefilledArray = new Array(5).fill(0);  // [0, 0, 0, 0, 0]

// Accessing elements
console.log(numbers[0]);  // 1 (first element)
console.log(numbers[numbers.length - 1]);  // 5 (last element)
console.log(numbers.at(-1));  // 5 (using at() for last element, ES2022)

// Modifying arrays
numbers[2] = 10;  // Change value: [1, 2, 10, 4, 5]
numbers.push(6);  // Add to end: [1, 2, 10, 4, 5, 6]
numbers.unshift(0);  // Add to beginning: [0, 1, 2, 10, 4, 5, 6]
numbers.pop();  // Remove from end: [0, 1, 2, 10, 4, 5]
numbers.shift();  // Remove from beginning: [1, 2, 10, 4, 5]

// Basic array properties
console.log(numbers.length);  // 5
console.log(Array.isArray(numbers));  // true
```

### Key Array Methods

#### 1. map()

Transforms each element of an array and returns a new array with the results.

```javascript
const numbers = [1, 2, 3, 4, 5];

// Double each number
const doubled = numbers.map(num => num * 2);
console.log(doubled);  // [2, 4, 6, 8, 10]

// Convert to strings with unit
const prices = numbers.map(num => `$${num.toFixed(2)}`);
console.log(prices);  // ["$1.00", "$2.00", "$3.00", "$4.00", "$5.00"]

// Extract property from objects
const users = [
    { id: 1, name: "Alice", age: 25 },
    { id: 2, name: "Bob", age: 30 },
    { id: 3, name: "Charlie", age: 35 }
];
const names = users.map(user => user.name);
console.log(names);  // ["Alice", "Bob", "Charlie"]

// Map with index parameter
const indexed = numbers.map((num, index) => `Item ${index + 1}: ${num}`);
console.log(indexed);  // ["Item 1: 1", "Item 2: 2", "Item 3: 3", "Item 4: 4", "Item 5: 5"]
```

#### 2. filter()

Creates a new array containing elements that pass a test.

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// Get even numbers
const evens = numbers.filter(num => num % 2 === 0);
console.log(evens);  // [2, 4, 6, 8, 10]

// Filter objects based on a condition
const users = [
    { name: "Alice", age: 25, active: true },
    { name: "Bob", age: 17, active: false },
    { name: "Charlie", age: 30, active: true },
    { name: "David", age: 15, active: true }
];

// Get active adult users
const activeAdults = users.filter(user => user.active && user.age >= 18);
console.log(activeAdults);  // [{ name: "Alice", age:.., active: true }, { name: "Charlie", ... }]
```

#### 3. reduce()

Accumulates values from an array into a single result.

```javascript
const numbers = [1, 2, 3, 4, 5];

// Sum all numbers
const sum = numbers.reduce((accumulator, current) => accumulator + current, 0);
console.log(sum);  // 15

// Find maximum value
const max = numbers.reduce((max, current) => Math.max(max, current), -Infinity);
console.log(max);  // 5

// Group objects by a property
const people = [
    { name: "Alice", age: 25, department: "Engineering" },
    { name: "Bob", age: 30, department: "Marketing" },
    { name: "Charlie", age: 35, department: "Engineering" },
    { name: "David", age: 40, department: "HR" }
];

const byDepartment = people.reduce((groups, person) => {
    const department = person.department;
    // If this department doesn't exist in our accumulator yet, create an array for it
    if (!groups[department]) {
        groups[department] = [];
    }
    // Add this person to the department's array
    groups[department].push(person);
    return groups;
}, {});

console.log(byDepartment);
// {
//   Engineering: [{ name: "Alice", ... }, { name: "Charlie", ... }],
//   Marketing: [{ name: "Bob", ... }],
//   HR: [{ name: "David", ... }]
// }
```

#### 4. forEach()

Executes a function on each element of an array.

```javascript
const numbers = [1, 2, 3, 4, 5];

// Log each number
numbers.forEach(num => {
    console.log(`Number: ${num}`);
});

// With index
numbers.forEach((num, index, array) => {
    console.log(`Element ${index} of ${array.length}: ${num}`);
});

// Modifying the original array (not recommended, use map instead)
const doubled = [];
numbers.forEach(num => {
    doubled.push(num * 2);
});
console.log(doubled);  // [2, 4, 6, 8, 10]
```

#### 5. find() and findIndex()

`find()` returns the first element that matches a condition, while `findIndex()` returns its index.

```javascript
const numbers = [1, 5, 10, 15, 20];

// Find first number greater than 10
const found = numbers.find(num => num > 10);
console.log(found);  // 15

// Find index of first even number
const evenIndex = numbers.findIndex(num => num % 2 === 0);
console.log(evenIndex);  // 2 (index of 10)

// Finding in an array of objects
const users = [
    { id: 1, name: "Alice" },
    { id: 2, name: "Bob" },
    { id: 3, name: "Charlie" }
];

const bob = users.find(user => user.name === "Bob");
console.log(bob);  // { id: 2, name: "Bob" }
```

#### 6. some() and every()

`some()` checks if at least one element meets a condition, while `every()` checks if all elements meet it.

```javascript
const numbers = [1, 2, 3, 4, 5];

// Check if at least one number is even
const hasEven = numbers.some(num => num % 2 === 0);
console.log(hasEven);  // true

// Check if all numbers are positive
const allPositive = numbers.every(num => num > 0);
console.log(allPositive);  // true

// Check if all numbers are even
const allEven = numbers.every(num => num % 2 === 0);
console.log(allEven);  // false
```

#### 7. sort()

Sorts the elements of an array in place.

```javascript
// String sorting
const fruits = ["banana", "apple", "orange", "grape"];
fruits.sort();
console.log(fruits);  // ["apple", "banana", "grape", "orange"]

// Number sorting (requires comparison function)
const numbers = [40, 1, 5, 200];
numbers.sort();  // Warning: sorts as strings by default!
console.log(numbers);  // [1, 200, 40, 5] (wrong order)

// Correct numeric sort
numbers.sort((a, b) => a - b);  // Ascending
console.log(numbers);  // [1, 5, 40, 200]

numbers.sort((a, b) => b - a);  // Descending
console.log(numbers);  // [200, 40, 5, 1]

// Sorting objects
const people = [
    { name: "Alice", age: 25 },
    { name: "Bob", age: 30 },
    { name: "Charlie", age: 20 }
];

// Sort by age
people.sort((a, b) => a.age - b.age);
console.log(people);  // [{ name: "Charlie", ... }, { name: "Alice", ... }, { name: "Bob", ... }]

// Sort by name
people.sort((a, b) => a.name.localeCompare(b.name));
console.log(people);  // [{ name: "Alice", ... }, { name: "Bob", ... }, { name: "Charlie", ... }]
```

#### 8. Other Useful Methods

```javascript
const arr = [1, 2, 3, 4, 5];

// slice(): Returns a shallow copy of a portion of an array
console.log(arr.slice(1, 3));  // [2, 3]

// splice(): Changes the array by removing/replacing/adding elements
arr.splice(1, 2, "a", "b");  // Remove 2 elements from index 1, insert "a" and "b"
console.log(arr);  // [1, "a", "b", 4, 5]

// concat(): Merges arrays
const arr1 = [1, 2];
const arr2 = [3, 4];
const combined = arr1.concat(arr2);
console.log(combined);  // [1, 2, 3, 4]

// join(): Joins all elements into a string
console.log(arr.join("-"));  // "1-a-b-4-5"

// includes(): Checks if an array includes an element
console.log(arr.includes("a"));  // true

// flat(): Creates a new array with all sub-arrays concatenated
const nested = [1, [2, [3, 4]]];
console.log(nested.flat());  // [1, 2, [3, 4]]
console.log(nested.flat(2));  // [1, 2, 3, 4]
```

## Destructuring

Destructuring is a convenient way to extract values from arrays or properties from objects into distinct variables.

### Array Destructuring

```javascript
// Basic array destructuring
const rgb = [255, 100, 50];
const [red, green, blue] = rgb;
console.log(red, green, blue);  // 255 100 50

// Skip elements with commas
const [first, , third] = [1, 2, 3];
console.log(first, third);  // 1 3

// Rest pattern
const [leader, ...team] = ["Alice", "Bob", "Charlie", "David"];
console.log(leader);  // "Alice"
console.log(team);    // ["Bob", "Charlie", "David"]

// Default values
const [name = "Guest", age = 18] = ["Max"];
console.log(name, age);  // "Max" 18

// Swapping variables
let a = 1, b = 2;
[a, b] = [b, a];
console.log(a, b);  // 2 1

// Nested arrays
const colors = ["red", ["light green", "dark green"]];
const [primaryColor, [lightVariant, darkVariant]] = colors;
console.log(lightVariant);  // "light green"
```

### Object Destructuring

```javascript
// Basic object destructuring
const person = {
    name: "Alice",
    age: 30,
    city: "New York"
};
const { name, age } = person;
console.log(name, age);  // "Alice" 30

// Renaming variables
const { name: fullName, age: years } = person;
console.log(fullName, years);  // "Alice" 30

// Default values
const { name: userName = "Guest", country = "USA" } = person;
console.log(userName, country);  // "Alice" "USA"

// Rest pattern for objects
const { name: personName, ...details } = person;
console.log(personName);  // "Alice"
console.log(details);  // { age: 30, city: "New York" }

// Nested objects
const user = {
    id: 1,
    name: "Alice",
    address: {
        street: "123 Main St",
        city: "New York",
        coordinates: {
            lat: 40.7128,
            lng: -74.0060
        }
    }
};

const { address: { city: userCity, coordinates: { lat, lng } } } = user;
console.log(userCity, lat, lng);  // "New York" 40.7128 -74.0060

// Combining with arrays
const { hobbies: [firstHobby] } = { hobbies: ["reading", "swimming"] };
console.log(firstHobby);  // "reading"
```

### Destructuring in Function Parameters

Destructuring in parameter lists allows you to directly extract values from objects or arrays passed as arguments.

```javascript
// Object destructuring in parameters
function displayUser({ name, age, city = "Unknown" }) {
    console.log(`${name} is ${age} years old from ${city}`);
}

displayUser({ name: "Alice", age: 30, city: "New York" });  // "Alice is 30 years old from New York"
displayUser({ name: "Bob", age: 25 });  // "Bob is 25 years old from Unknown"

// With renamed variables
function getFullName({ firstName: fname, lastName: lname }) {
    return `${fname} ${lname}`;
}

console.log(getFullName({ firstName: "John", lastName: "Doe" }));  // "John Doe"

// Array destructuring in parameters
function processCoordinates([x, y, z = 0]) {
    return Math.sqrt(x ** 2 + y ** 2 + z ** 2);
}

console.log(processCoordinates([3, 4]));  // 5 (3-4-0 triangle)
console.log(processCoordinates([3, 4, 5]));  // ≈7.07

// Nested destructuring in parameters
function processUser({
    name,
    address: { city, country = "Unknown" },
    hobbies: [mainHobby, ...otherHobbies]
}) {
    console.log(`${name} lives in ${city}, ${country}`);
    console.log(`Main hobby: ${mainHobby}, others: ${otherHobbies.join(", ")}`);
}

processUser({
    name: "Alice",
    address: { city: "London" },
    hobbies: ["painting", "cooking", "hiking"]
});
// "Alice lives in London, Unknown"
// "Main hobby: painting, others: cooking, hiking"
```

## Spread and Rest Operators

The spread and rest operators both use the same `...` syntax but work differently based on context.

### Spread Operator (...)

The spread operator "spreads" or expands an iterable (like an array or string) into individual elements.

```javascript
// Spreading arrays
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

// Combine arrays
const combined = [...arr1, ...arr2];
console.log(combined);  // [1, 2, 3, 4, 5, 6]

// Insert elements in middle
const withMiddle = [...arr1.slice(0, 1), 'inserted', ...arr1.slice(1)];
console.log(withMiddle);  // [1, "inserted", 2, 3]

// Copy an array (shallow copy)
const original = [1, 2, 3];
const copy = [...original];
original.push(4);
console.log(copy);  // [1, 2, 3] (unchanged)

// Spreading strings into arrays
const str = "hello";
const chars = [...str];
console.log(chars);  // ["h", "e", "l", "l", "o"]

// Spread with objects (ES2018)
const obj1 = { name: "Alice", age: 30 };
const obj2 = { city: "New York", country: "USA" };

// Combine objects
const mergedObj = { ...obj1, ...obj2 };
console.log(mergedObj);  // { name: "Alice", age: 30, city: "New York", country: "USA" }

// Override properties
const updatedObj = { ...obj1, age: 31 };
console.log(updatedObj);  // { name: "Alice", age: 31 }

// With function arguments
function sum(a, b, c) {
    return a + b + c;
}

const numbers = [1, 2, 3];
console.log(sum(...numbers));  // 6

// Useful for cloning with modifications
const person = { name: "Max", age: 30, hobbies: ["reading", "cycling"] };
const updatedPerson = {
    ...person,
    age: 31,  // Update age
    hobbies: [...person.hobbies, "swimming"]  // Add a hobby
};
console.log(updatedPerson);
// { name: "Max", age: 31, hobbies: ["reading", "cycling", "swimming"] }
```

### Rest Operator (...)

The rest operator collects multiple elements and condenses them into a single array.

```javascript
// In array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first);  // 1
console.log(second);  // 2
console.log(rest);  // [3, 4, 5]

// In object destructuring
const { name, age, ...otherProps } = { name: "Alice", age: 30, city: "NYC", job: "Developer" };
console.log(name);  // "Alice"
console.log(age);  // 30
console.log(otherProps);  // { city: "NYC", job: "Developer" }

// In function parameters - gathering unlimited arguments
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4, 5));  // 15
console.log(sum(10, 20));  // 30

// Combining regular parameters with rest
function multiply(multiplier, ...numbers) {
    return numbers.map(num => num * multiplier);
}

console.log(multiply(2, 1, 2, 3));  // [2, 4, 6]
console.log(multiply(10, 5, 10));  // [50, 100]

// Rest parameter must be the last parameter
// This is invalid: function invalid(a, ...rest, b) { }
```

## Manipulating the DOM

The Document Object Model (DOM) represents the webpage as a tree of objects that can be manipulated with JavaScript.

### Selecting Elements

```javascript
// Select a single element
const header = document.getElementById("main-header");
const firstParagraph = document.querySelector("p");  // First matching p
const activeItem = document.querySelector(".item.active");  // Class selector

// Select multiple elements
const allParagraphs = document.getElementsByTagName("p");  // HTMLCollection
const navItems = document.getElementsByClassName("nav-item");  // HTMLCollection
const links = document.querySelectorAll("a");  // NodeList

// Converting HTMLCollection/NodeList to Array
const paragraphArray = Array.from(allParagraphs);
// Or:
const paragraphArray2 = [...allParagraphs];
```

### Modifying Elements

```javascript
// Changing text content
header.textContent = "New Header";  // Only text, doesn't parse HTML
header.innerText = "New Header";    // Text as displayed, respects CSS
header.innerHTML = "New <em>Header</em>";  // Parses HTML (use with caution)

// Changing attributes
const link = document.querySelector("a");
link.href = "https://example.com";
link.setAttribute("target", "_blank");
link.setAttribute("data-info", "custom-data");  // Custom data attribute
console.log(link.getAttribute("href"));  // "https://example.com"

// Working with classes
const element = document.querySelector(".box");
element.classList.add("highlight");
element.classList.remove("hidden");
element.classList.toggle("active");  // Adds if missing, removes if present
element.classList.replace("old-class", "new-class");
console.log(element.classList.contains("highlight"));  // true

// Modifying styles
element.style.color = "blue";
element.style.fontSize = "16px";
element.style.padding = "10px 20px";
// For hyphenated CSS properties, use camelCase in JS
element.style.backgroundColor = "lightgray";  // "background-color" in CSS
```

### Creating and Removing Elements

```javascript
// Creating elements
const newParagraph = document.createElement("p");
newParagraph.textContent = "This is a new paragraph.";
newParagraph.classList.add("info");

// Adding elements to the DOM
document.body.appendChild(newParagraph);  // Add at the end of body

const container = document.querySelector(".container");
container.prepend(newParagraph);  // Add as first child
container.appendChild(newParagraph);  // Add as last child (moves it)
container.insertBefore(newParagraph, container.firstChild);  // Insert before specific element

// Using insertAdjacentHTML
container.insertAdjacentHTML("beforeend", "<p>Inserted with HTML</p>");
// Positions: beforebegin, afterbegin, beforeend, afterend

// Removing elements
const elementToRemove = document.querySelector(".remove-me");
elementToRemove.remove();  // Modern way
// Or:
elementToRemove.parentNode.removeChild(elementToRemove);  // Older but more compatible
```

### Navigating the DOM

```javascript
// Parent relationships
console.log(element.parentNode);  // Parent node (any node type)
console.log(element.parentElement);  // Parent element node

// Child relationships
console.log(element.childNodes);  // All child nodes (including text, comments)
console.log(element.children);  // Only element nodes
console.log(element.firstChild);  // First child node (any type)
console.log(element.firstElementChild);  // First element child
console.log(element.lastChild);  // Last child node
console.log(element.lastElementChild);  // Last element child

// Sibling relationships
console.log(element.previousSibling);  // Previous sibling (any type)
console.log(element.previousElementSibling);  // Previous element sibling
console.log(element.nextSibling);  // Next sibling (any type)
console.log(element.nextElementSibling);  // Next element sibling
```

### Events

```javascript
// Basic event attachment
const button = document.querySelector("button");
button.addEventListener("click", function() {
    console.log("Button clicked!");
});

// Using named function
function handleClick(event) {
    console.log("Button clicked with named function!");
    console.log("Event info:", event.type, event.target);

    // Prevent default behavior (e.g., for links or forms)
    event.preventDefault();

    // Stop event bubbling
    event.stopPropagation();
}

button.addEventListener("click", handleClick);

// Using arrow function
button.addEventListener("click", (event) => {
    console.log("Button clicked with arrow function!");
});

// Removing event listener (must use named function)
button.removeEventListener("click", handleClick);

// Common events:
// click, dblclick, mousedown, mouseup, mouseover, mouseout, mousemove
// keydown, keyup, keypress
// submit, change, input, focus, blur
// load, DOMContentLoaded, resize, scroll

// Event delegation
document.querySelector("ul").addEventListener("click", function(event) {
    if (event.target.tagName === "LI") {
        console.log("List item clicked:", event.target.textContent);
        event.target.classList.toggle("selected");
    }
});
```

## Using Functions as Values

JavaScript treats functions as first-class citizens, allowing them to be assigned to variables, passed to other functions, and returned from functions.

### Functions as Variables

```javascript
// Assign function to variable
const greet = function(name) {
    return `Hello, ${name}!`;
};

console.log(greet("Alice"));  // "Hello, Alice!"

// Assign function to object property
const person = {
    name: "Max",
    sayHello: function() {
        return `Hello, I'm ${this.name}`;
    },
    // Method shorthand (ES6)
    greet() {
        return `Greetings from ${this.name}`;
    }
};

console.log(person.sayHello());  // "Hello, I'm Max"
```

### Functions as Arguments (Callbacks)

```javascript
// Simple callback example
function processUserInput(callback) {
    const name = "Max";  // In real code, this might come from user input
    callback(name);
}

processUserInput(function(name) {
    console.log(`Hello, ${name}`);  // "Hello, Max"
});

// With array methods
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(function(num) {
    return num * 2;
});
console.log(doubled);  // [2, 4, 6, 8, 10]

// Callback with timer
setTimeout(function() {
    console.log("This runs after 2 seconds");
}, 2000);

// Using named functions as callbacks
function handleSuccess(data) {
    console.log("Success:", data);
}

function handleError(error) {
    console.error("Error:", error);
}

function fetchData(onSuccess, onError) {
    const success = true;
    if (success) {
        onSuccess("Data retrieved successfully");
    } else {
        onError("Failed to retrieve data");
    }
}

fetchData(handleSuccess, handleError);
```

### Returning Functions (Closures)

```javascript
// Function that returns a function
function createMultiplier(factor) {
    // The returned function "remembers" the factor
    return function(number) {
        return number * factor;
    };
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5));  // 10
console.log(triple(5));  // 15

// Creating specific greeters
function createGreeter(greeting) {
    return function(name) {
        return `${greeting}, ${name}!`;
    };
}

const sayHello = createGreeter("Hello");
const sayHi = createGreeter("Hi");

console.log(sayHello("Alice"));  // "Hello, Alice!"
console.log(sayHi("Bob"));  // "Hi, Bob!"
```

## Defining Functions Inside Functions

Nesting functions is a powerful technique for encapsulation and creating closures.

```javascript
function outer() {
    console.log("I am the outer function");

    // Inner function defined inside
    function inner() {
        console.log("I am the inner function");
    }

    // Call inner function
    inner();
}

outer();  // Logs both messages
// inner();  // Error: inner is not defined (not accessible outside outer)

// Practical example with a closure
function createCounter() {
    let count = 0;  // Private variable

    // Return an object with methods that access the private variable
    return {
        increment() {
            count++;
            return count;
        },
        decrement() {
            count--;
            return count;
        },
        getValue() {
            return count;
        },
        reset() {
            count = 0;
            return count;
        }
    };
}

const counter = createCounter();
console.log(counter.increment());  // 1
console.log(counter.increment());  // 2
console.log(counter.decrement());  // 1
console.log(counter.getValue());   // 1
// console.log(counter.count);  // undefined (private)

// Another example: memoization with inner function
function memoizedFibonacci() {
    // Cache of previously calculated results
    const cache = {};

    // Inner recursive function with access to cache
    function fibonacci(n) {
        // Check if we've already calculated this value
        if (n in cache) {
            return cache[n];
        }

        // Base cases
        if (n <= 1) {
            return n;
        }

        // Calculate and store result
        const result = fibonacci(n - 1) + fibonacci(n - 2);
        cache[n] = result;
        return result;
    }

    // Return the inner function
    return fibonacci;
}

const fib = memoizedFibonacci();
console.log(fib(40));  // Calculates quickly due to memoization
```

## Reference vs Primitive Values

Understanding the difference between reference and primitive values is crucial for managing data in JavaScript.

### Primitive Values

Primitive values are immutable and passed by value. JavaScript has six primitive data types:
1. String
2. Number
3. Boolean
4. Null
5. Undefined
6. Symbol (ES6)
7. BigInt (ES2020)

```javascript
// Primitive values are copied when assigned
let a = 10;
let b = a;  // b gets a copy of the value
a = 20;     // Changing a doesn't affect b
console.log(a);  // 20
console.log(b);  // 10

// Strings (immutable)
let name1 = "Alice";
let name2 = name1;  // name2 gets a copy
name1 = "Bob";      // Changing name1 doesn't affect name2
console.log(name1);  // "Bob"
console.log(name2);  // "Alice"

// Comparing primitives (compares their values)
console.log(5 === 5);           // true
console.log("hello" === "hello");  // true
```

### Reference Values

Reference values (Objects, Arrays, Functions) are passed by reference. The variable stores a reference to the value's location in memory.

```javascript
// Objects are passed by reference
let obj1 = { name: "Alice", age: 30 };
let obj2 = obj1;  // obj2 references the same object

obj1.age = 31;    // Modifying obj1 also affects obj2
console.log(obj1.age);  // 31
console.log(obj2.age);  // 31

// Arrays (which are objects) work the same way
let arr1 = [1, 2, 3];
let arr2 = arr1;  // arr2 references the same array

arr1.push(4);     // Modifying arr1 also affects arr2
console.log(arr1);  // [1, 2, 3, 4]
console.log(arr2);  // [1, 2, 3, 4]

// Comparing references (compares memory locations, not contents)
console.log({} === {});  // false (different objects)
console.log([] === []);  // false (different arrays)

let objA = { value: 10 };
let objB = objA;
console.log(objA === objB);  // true (same reference)
```

### Handling Reference Values

```javascript
// Copying objects
// Shallow copy (only copies top-level properties)
let original = { name: "Alice", details: { age: 30 } };

// Using spread operator (shallow copy)
let shallowCopy1 = { ...original };

// Using Object.assign (shallow copy)
let shallowCopy2 = Object.assign({}, original);

original.name = "Bob";  // This change won't affect copies
original.details.age = 31;  // This change WILL affect copies (nested object)

console.log(original);      // { name: "Bob", details: { age: 31 } }
console.log(shallowCopy1);  // { name: "Alice", details: { age: 31 } }
console.log(shallowCopy2);  // { name: "Alice", details: { age: 31 } }

// Deep copy (copies all nested objects too)
// Method 1: JSON parse/stringify (works for simple objects without functions, dates, etc.)
let deepCopy1 = JSON.parse(JSON.stringify(original));

// Method 2: Structured clone API (modern browsers)
let deepCopy2 = structuredClone(original);

original.details.age = 32;  // Won't affect deep copies

console.log(deepCopy1.details.age);  // 31
console.log(deepCopy2.details.age);  // 31

// Copying arrays
let originalArray = [1, 2, [3, 4]];

// Shallow copy methods:
let arrayCopy1 = [...originalArray];
let arrayCopy2 = originalArray.slice();
let arrayCopy3 = Array.from(originalArray);

originalArray[0] = 99;       // Won't affect copies
originalArray[2][0] = 99;    // WILL affect copies (nested array)

console.log(arrayCopy1);  // [1, 2, [99, 4]]

// Deep copy for arrays
let deepArrayCopy = JSON.parse(JSON.stringify(originalArray));
// or structuredClone(originalArray)
```

### Immutability Patterns

```javascript
// Immutable updates (creating new objects instead of modifying)
const user = {
    name: "Max",
    age: 30,
    address: {
        city: "Berlin",
        country: "Germany"
    }
};

// Bad: Directly mutating
// user.age = 31;
// user.address.city = "Munich";

// Good: Creating new objects
const updatedUser = {
    ...user,
    age: 31,  // Override age
    address: {
        ...user.address,
        city: "Munich"  // Override city
    }
};

console.log(user);        // Original unchanged
console.log(updatedUser); // New object with updates

// Immutable array operations
const numbers = [1, 2, 3, 4, 5];

// Instead of: numbers.push(6);
const numbersWithSix = [...numbers, 6];

// Instead of: numbers.splice(2, 1);
const numbersWithoutThree = [...numbers.slice(0, 2), ...numbers.slice(3)];

// Instead of: numbers[0] = 10;
const numbersWithTen = [10, ...numbers.slice(1)];

console.log(numbers);             // Original: [1, 2, 3, 4, 5]
console.log(numbersWithSix);      // [1, 2, 3, 4, 5, 6]
console.log(numbersWithoutThree); // [1, 2, 4, 5]
console.log(numbersWithTen);      // [10, 2, 3, 4, 5]
```

## JS Array Functions

JavaScript provides a rich set of array methods for manipulation, transformation, and iteration. Here's a comprehensive guide to the most important ones:

### 1. Adding and Removing Elements

```javascript
const array = ['a', 'b', 'c'];

// Add to end
array.push('d');  // Returns new length: 4
console.log(array);  // ['a', 'b', 'c', 'd']

// Remove from end
const lastItem = array.pop();  // Returns removed element: 'd'
console.log(array);  // ['a', 'b', 'c']

// Add to beginning
array.unshift('z');  // Returns new length: 4
console.log(array);  // ['z', 'a', 'b', 'c']

// Remove from beginning
const firstItem = array.shift();  // Returns removed element: 'z'
console.log(array);  // ['a', 'b', 'c']

// Add/remove elements from any position
array.splice(1, 1, 'x', 'y');  // Remove 1 element at index 1, insert 'x' and 'y'
console.log(array);  // ['a', 'x', 'y', 'c']

// Remove elements without replacing
array.splice(1, 2);  // Remove 2 elements starting at index 1
console.log(array);  // ['a', 'c']
```

### 2. Finding Elements

```javascript
const items = ['apple', 'banana', 'orange', 'apple'];

// Find index of element
console.log(items.indexOf('banana'));  // 1
console.log(items.indexOf('grape'));   // -1 (not found)
console.log(items.lastIndexOf('apple'));  // 3 (last occurrence)

// Check if element exists
console.log(items.includes('orange'));  // true
console.log(items.includes('grape'));   // false

// Find element matching condition
const numbers = [5, 12, 8, 130, 44];
const foundNumber = numbers.find(num => num > 10);
console.log(foundNumber);  // 12 (first match)

// Find index of element matching condition
const foundIndex = numbers.findIndex(num => num > 10);
console.log(foundIndex);  // 1 (index of first match)

// Find all elements matching condition (ES2023)
const allBigNumbers = numbers.filter(num => num > 10);
console.log(allBigNumbers);  // [12, 130, 44]
```

### 3. Transforming Arrays

```javascript
const numbers = [1, 2, 3, 4, 5];

// Create new array by applying function to each element
const doubled = numbers.map(num => num * 2);
console.log(doubled);  // [2, 4, 6, 8, 10]

// Flattening nested arrays
const nested = [1, [2, 3], [4, [5, 6]]];
console.log(nested.flat());      // [1, 2, 3, 4, [5, 6]]
console.log(nested.flat(2));     // [1, 2, 3, 4, 5, 6]
console.log(nested.flat(Infinity));  // [1, 2, 3, 4, 5, 6]

// Map and flatten in one step
const nestedObjects = [[{id: 1}, {id: 2}], [{id: 3}]];
const ids = nestedObjects.flatMap(group => group.map(obj => obj.id));
console.log(ids);  // [1, 2, 3]

// Filling arrays
const filled = new Array(5).fill(0);
console.log(filled);  // [0, 0, 0, 0, 0]

// Replace part of array with values
const modified = [1, 2, 3, 4, 5];
modified.fill(0, 2, 4);  // Fill with 0 from index 2 up to (not including) 4
console.log(modified);  // [1, 2, 0, 0, 5]
```

### 4. Array Ordering

```javascript
const fruits = ['banana', 'apple', 'orange', 'grape'];

// Reverse array (modifies original)
fruits.reverse();
console.log(fruits);  // ['grape', 'orange', 'apple', 'banana']

// Sort array (modifies original)
fruits.sort();  // Alphabetical by default
console.log(fruits);  // ['apple', 'banana', 'grape', 'orange']

// Sort with custom function
const numbers = [40, 1, 5, 200];
numbers.sort((a, b) => a - b);  // Numeric ascending
console.log(numbers);  // [1, 5, 40, 200]

// Reversing sort
numbers.sort((a, b) => b - a);  // Numeric descending
console.log(numbers);  // [200, 40, 5, 1]

// Immutable sort (creates new array)
const origFruits = ['banana', 'apple', 'orange'];
const sortedFruits = [...origFruits].sort();
console.log(origFruits);     // ['banana', 'apple', 'orange'] (unchanged)
console.log(sortedFruits);   // ['apple', 'banana', 'orange'] (new array)
```

### 5. Array Iteration

```javascript
const items = ['a', 'b', 'c'];

// forEach: Execute function for each element (no return value)
items.forEach((item, index) => {
    console.log(`${index}: ${item}`);
});

// for...of: Iterate over array elements
for (const item of items) {
    console.log(item);
}

// for...in: Iterate over array indices (not recommended for arrays)
for (const index in items) {
    console.log(`${index}: ${items[index]}`);
}

// Entries, keys, values (returns iterators)
for (const [index, value] of items.entries()) {
    console.log(`${index}: ${value}`);
}

// Convert iterator to array
console.log([...items.keys()]);    // [0, 1, 2]
console.log([...items.values()]);  // ['a', 'b', 'c']
console.log([...items.entries()]);  // [[0, 'a'], [1, 'b'], [2, 'c']]
```

### 6. Array Transformation (Reduce)

```javascript
const numbers = [1, 2, 3, 4, 5];

// Reduce: Accumulate values
const sum = numbers.reduce((accumulator, current) => accumulator + current, 0);
console.log(sum);  // 15

// Reduce with other operations
const product = numbers.reduce((acc, curr) => acc * curr, 1);
console.log(product);  // 120

// Find max value
const max = numbers.reduce((max, curr) => Math.max(max, curr), -Infinity);
console.log(max);  // 5

// Create object from array
const fruits = ['apple', 'banana', 'apple', 'orange', 'banana', 'apple'];
const countMap = fruits.reduce((counts, fruit) => {
    counts[fruit] = (counts[fruit] || 0) + 1;
    return counts;
}, {});
console.log(countMap);  // {apple: 3, banana: 2, orange: 1}

// Group objects by property
const people = [
    {name: 'Alice', age: 25, city: 'New York'},
    {name: 'Bob', age: 30, city: 'Chicago'},
    {name: 'Charlie', age: 35, city: 'New York'},
    {name: 'Dave', age: 40, city: 'Chicago'}
];

const groupedByCity = people.reduce((groups, person) => {
    const city = person.city;
    groups[city] = groups[city] || [];
    groups[city].push(person);
    return groups;
}, {});

console.log(groupedByCity);
// {
//   'New York': [{name: 'Alice', ...}, {name: 'Charlie', ...}],
//   'Chicago': [{name: 'Bob', ...}, {name: 'Dave', ...}]
// }
```

### 7. Other Useful Array Methods

```javascript
// join: Combine array elements into string
const elements = ['Fire', 'Air', 'Water'];
console.log(elements.join());      // "Fire,Air,Water"
console.log(elements.join(''));    // "FireAirWater"
console.log(elements.join(' - ')); // "Fire - Air - Water"

// slice: Extract portion of array
const fruits = ['apple', 'banana', 'orange', 'mango', 'kiwi'];
console.log(fruits.slice(1, 3));  // ['banana', 'orange']
console.log(fruits.slice(-2));    // ['mango', 'kiwi']

// concat: Merge arrays
const arr1 = [1, 2];
const arr2 = [3, 4];
const arr3 = [5, 6];
const combined = arr1.concat(arr2, arr3);
console.log(combined);  // [1, 2, 3, 4, 5, 6]

// from: Create array from array-like object
const arrayLike = { 0: 'a', 1: 'b', 2: 'c', length: 3 };
const actualArray = Array.from(arrayLike);
console.log(actualArray);  // ['a', 'b', 'c']

// from with map function
const mapped = Array.from([1, 2, 3], x => x * 2);
console.log(mapped);  // [2, 4, 6]

// of: Create array from arguments
const numbers = Array.of(1, 2, 3, 4, 5);
console.log(numbers);  // [1, 2, 3, 4, 5]

// copyWithin: Copy portion of array to another location in the same array
const array = [1, 2, 3, 4, 5];
array.copyWithin(0, 3);  // Copy values at index 3+ to index 0
console.log(array);  // [4, 5, 3, 4, 5]

// at: Access elements with positive and negative indices (ES2022)
const fruits2 = ['apple', 'banana', 'orange'];
console.log(fruits2.at(1));    // 'banana'
console.log(fruits2.at(-1));   // 'orange' (last element)
```

### 8. Determining if Array Is Empty

```javascript
const emptyArray = [];
const nonEmptyArray = [1, 2, 3];

// Method 1: Check length
console.log(emptyArray.length === 0);       // true
console.log(nonEmptyArray.length === 0);    // false

// Method 2: Check first element
console.log(emptyArray[0] === undefined);   // true
console.log(nonEmptyArray[0] === undefined); // false
```

### 9. Advanced Array Techniques

```javascript
// Unique values (using Set)
const numbers = [1, 2, 2, 3, 4, 4, 5];
const uniqueNumbers = [...new Set(numbers)];
console.log(uniqueNumbers);  // [1, 2, 3, 4, 5]

// Intersection of arrays
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [3, 4, 5, 6, 7];
const intersection = arr1.filter(item => arr2.includes(item));
console.log(intersection);  // [3, 4, 5]

// Difference between arrays
const difference = arr1.filter(item => !arr2.includes(item));
console.log(difference);  // [1, 2]

// Union of arrays (with unique values)
const union = [...new Set([...arr1, ...arr2])];
console.log(union);  // [1, 2, 3, 4, 5, 6, 7]

// Remove falsy values
const withFalsy = [0, false, '', undefined, null, NaN, 1, 'hello', true];
const truthyOnly = withFalsy.filter(Boolean);
console.log(truthyOnly);  // [1, 'hello', true]

// Create array of numbers in range
const range = (start, end) => Array.from({length: end - start + 1}, (_, i) => start + i);
console.log(range(5, 10));  // [5, 6, 7, 8, 9, 10]

// Chunk array into groups
function chunkArray(array, size) {
    const chunked = [];
    for (let i = 0; i < array.length; i += size) {
        chunked.push(array.slice(i, i + size));
    }
    return chunked;
}

console.log(chunkArray([1, 2, 3, 4, 5, 6, 7], 3));  // [[1, 2, 3], [4, 5, 6], [7]]

// Shuffle array (Fisher-Yates algorithm)
function shuffleArray(array) {
    const shuffled = [...array];
    for (let i = shuffled.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
    }
    return shuffled;
}

console.log(shuffleArray([1, 2, 3, 4, 5]));  // Random order
```

### 10. Performance Considerations

```javascript
// Preallocating arrays for better performance
const size = 1000000;
console.time('with preallocation');
const preAllocated = new Array(size);
for (let i = 0; i < size; i++) {
    preAllocated[i] = i;
}
console.timeEnd('with preallocation');

console.time('without preallocation');
const dynamicArray = [];
for (let i = 0; i < size; i++) {
    dynamicArray.push(i);  // Causes reallocation as array grows
}
console.timeEnd('without preallocation');

// Use typed arrays for numeric data
const regular = new Array(10000).fill(0).map((_, i) => i);
const typed = new Int32Array(10000);
for (let i = 0; i < 10000; i++) {
    typed[i] = i;
}

// For operations on large arrays, consider:
// 1. Using for loops instead of forEach/map when performance is critical
// 2. Breaking operations into smaller chunks for long-running processes
// 3. Using Web Workers for CPU-intensive array operations
```

## References in JavaScript

In JavaScript, "references" can have multiple meanings depending on the context, but most commonly it refers to how non-primitive values are stored and passed.

### Object References

```javascript
// When a variable is assigned an object, it stores a reference to that object
let person1 = { name: "Alex" };
let person2 = person1;  // person2 references the same object as person1

// Modifying through either reference affects the single shared object
person2.name = "Sam";
console.log(person1.name);  // "Sam" (person1 is affected too)

// Comparing references
let obj1 = { value: 10 };
let obj2 = { value: 10 };
let obj3 = obj1;

console.log(obj1 === obj2);  // false (different objects with same content)
console.log(obj1 === obj3);  // true (same object reference)

// Function parameters are also passed by reference for objects
function changeName(personObj) {
    personObj.name = "Taylor";  // Modifies the original object
}

let employee = { name: "Jordan" };
changeName(employee);
console.log(employee.name);  // "Taylor"
```

### Circular References

A circular reference occurs when an object references itself directly or indirectly.

```javascript
// Direct circular reference
let circular = {};
circular.self = circular;
console.log(circular.self === circular);  // true

// Indirect circular reference
let parent = { name: "Parent" };
let child = { name: "Child" };
parent.child = child;
child.parent = parent;

console.log(parent.child.parent === parent);  // true

// Circular references and JSON
// Attempting to stringify a circular structure will fail
try {
    JSON.stringify(circular);  // Error: Converting circular structure to JSON
} catch (e) {
    console.log("Cannot stringify circular references");
}

// Solutions for circular references:
// 1. Using WeakMap to track visited objects
function decircularize(obj) {
    const seen = new WeakMap();

    return (function replacer(value) {
        // Handle non-objects or null
        if (typeof value !== 'object' || value === null) return value;

        // Handle circular reference
        if (seen.has(value)) {
            return { $ref: 'circular' };
        }

        // Add current object to visited
        seen.set(value, true);

        // Handle arrays
        if (Array.isArray(value)) {
            return value.map(replacer);
        }

        // Handle objects
        return Object.fromEntries(
            Object.entries(value).map(([key, val]) => [key, replacer(val)])
        );
    })(obj);
}

const decircularized = decircularize(circular);
console.log(JSON.stringify(decircularized));  // {"self":{"$ref":"circular"}}
```

### Memory References and Garbage Collection

```javascript
// Object is created and referenced
let user = { name: "Alice" };

// Another reference to the same object
let admin = user;

// Original reference is removed, but object remains accessible through admin
user = null;

console.log(admin.name);  // "Alice" (object still exists in memory)

// When all references are gone, the object becomes eligible for garbage collection
admin = null;  // Now the object can be garbage collected

// WeakMap and WeakSet maintain weak references that don't prevent garbage collection
let weakMap = new WeakMap();
{
    let obj = {};  // Object created in this block scope
    weakMap.set(obj, "data");
    // Obj is still the key in weakMap
}
// obj is out of scope and can be garbage collected
// even though it's a key in weakMap
```

## Forward References and Back References in RegExp

In regular expressions, back references and forward references refer to capturing groups that are matched earlier or later in the pattern.

### Back References

Back references allow you to refer to previously captured groups within the same regular expression.

```javascript
// Basic back reference example: matching repeated words
const repeatedWord = /(\b\w+\b)\s+\1/;
console.log(repeatedWord.test("hello hello"));  // true
console.log(repeatedWord.test("hello world"));  // false

// Capturing HTML tags and ensuring closing tag matches
const htmlTagPattern = /<([a-z][a-z0-9]*)\b[^>]*>(.*?)<\/\1>/i;
console.log(htmlTagPattern.test("<div>Content</div>"));  // true
console.log(htmlTagPattern.test("<div>Content</span>"));  // false

// Multiple back references
const duplicateChars = /(.)(.)(.)\1\2\3/;
console.log(duplicateChars.test("abcabc"));  // true
console.log(duplicateChars.test("abcdef"));  // false

// Named capture groups and back references (ES2018)
const namedTagPattern = /<(?<tag>[a-z][a-z0-9]*)\b[^>]*>.*?<\/\k<tag>>/i;
console.log(namedTagPattern.test("<div>Content</div>"));  // true
console.log(namedTagPattern.test("<div>Content</span>"));  // false

// Finding duplicated words in text with back references
const duplicateWordPattern = /\b(\w+)\b\s+\1\b/gi;
const text = "The the quick brown fox jumps over the lazy lazy dog";
const matches = text.match(duplicateWordPattern);
console.log(matches);  // ["The the", "lazy lazy"]

// Replace duplicated words
const deduped = text.replace(duplicateWordPattern, "$1");
console.log(deduped);  // "The quick brown fox jumps over the lazy dog"
```

### Forward References

Forward references refer to a group that appears later in the pattern.
In JavaScript regular expressions, forward references to capturing groups that haven't been matched yet will always match the empty string.

```javascript
// Forward reference in JavaScript
const forwardRef = /\1(test)/;  // References a group before it's defined
console.log(forwardRef.test("test"));  // false
console.log(forwardRef.test("test"));  // false - doesn't work as expected

// This pattern makes more sense with back references
const backRef = /(test)\1/;
console.log(backRef.test("testtest"));  // true

// Forward references have limited use in JavaScript RegExp, as they don't work like in some other regex engines
```

## Lookaheads and Lookbehinds in RegExp

Lookahead and lookbehind assertions are zero-width assertions that match positions based on surrounding content without including that content in the match.

### Positive Lookahead

Asserts that what follows the current position matches a pattern, without including it in the match.

```javascript
// Match a word only if followed by a colon
const wordBeforeColon = /\w+(?=:)/g;
console.log("apple: red, banana: yellow".match(wordBeforeColon));  // ["apple", "banana"]

// Password validation: at least 8 characters with at least one number and one uppercase letter
const strongPassword = /^(?=.*[A-Z])(?=.*[0-9])(?=.{8,})/;
console.log(strongPassword.test("Passw0rd"));  // true
console.log(strongPassword.test("password"));  // false (no uppercase)
console.log(strongPassword.test("PASSWORD1"));  // true
console.log(strongPassword.test("Pass1"));     // false (too short)

// Match a price only if it's followed by 'USD'
const usdPrice = /\$\d+(?=\s+USD)/g;
console.log("$100 USD, €50 EUR, $200 CAD, $300 USD".match(usdPrice));  // ["$100", "$300"]
```

### Negative Lookahead

Asserts that what follows the current position does NOT match a pattern.

```javascript
// Match a word only if NOT followed by a colon
const wordNotBeforeColon = /\w+(?!:)/g;
const text = "apple: red, banana";
console.log([...text.matchAll(wordNotBeforeColon)].map(m => m[0]));
// This is a bit tricky, might include "appl", "red", "banana"

// Better example: Match whole words not followed by colon
const betterPattern = /\b\w+\b(?!:)/g;
console.log("apple: red, banana".match(betterPattern));  // ["red", "banana"]

// Exclude specific words
const notJavaScript = /\b(?!JavaScript\b)\w+\b/g;
console.log("I love JavaScript and Python".match(notJavaScript));  // ["I", "love", "and", "Python"]

// Find numbers not followed by 'px' or '%'
const valueWithoutUnit = /\d+(?!px|%)/g;
console.log("width: 100px, height: 200px, margin: 10, padding: 5%".match(valueWithoutUnit));
// ["10"]
```

### Positive Lookbehind (ES2018+)

Asserts that what precedes the current position matches a pattern, without including it in the match.

```javascript
// Match a word only if preceded by 'Mr.'
const nameAfterMr = /(?<=Mr\.\s)\w+/g;
console.log("Mr. Smith and Ms. Johnson".match(nameAfterMr));  // ["Smith"]

// Match a number only if preceded by '$'
const dollarValue = /(?<=\$)\d+(\.\d+)?/g;
console.log("Items: $10.99, €15.49, $5".match(dollarValue));  // ["10.99", "5"]

// Extract values after specific property names
const valueAfterProp = /(?<=name:\s").+?(?=")/g;
const json = '{"name": "Alice", "age": 30, "name": "Bob"}';
console.log(json.match(valueAfterProp));  // ["Alice", "Bob"]
```

### Negative Lookbehind (ES2018+)

Asserts that what precedes the current position does NOT match a pattern.

```javascript
// Match a word only if NOT preceded by 'Mr.' or 'Ms.'
const nameNotAfterTitle = /(?<!Mr\.\s|Ms\.\s)\b[A-Z][a-z]+\b/g;
console.log("Mr. Smith and John with Ms. Johnson".match(nameNotAfterTitle));  // ["John"]

// Match a number not preceded by '$' or '€'
const nonCurrencyValue = /(?<!\$|€)\b\d+(\.\d+)?\b/g;
console.log("Items: $10.99, €15.49, 5 pieces".match(nonCurrencyValue));  // ["5"]

// Extract domain names not preceded by "www."
const nonWwwDomain = /(?<!www\.)[a-z0-9-]+\.[a-z]{2,}/gi;
const urls = "visit example.com or www.google.com";
console.log(urls.match(nonWwwDomain));  // ["example.com"]
```

### Combined Lookaround Patterns

```javascript
// Find words between quotes but don't include the quotes
const betweenQuotes = /(?<=['"]).*?(?=['"])/g;
console.log(`He said 'hello' and "goodbye"`.match(betweenQuotes));  // ["hello", "goodbye"]

// Extract numbers that are both preceded by $ and followed by USD
const usdCurrency = /(?<=\$)\d+(?=\s+USD)/g;
console.log("$100 USD, €50 EUR, $200".match(usdCurrency));  // ["100"]

// Match whole words that don't start with 'un' and don't end with 'ed'
const specialWords = /\b(?!un)\w+(?<!ed)\b/g;
console.log("untie the tied knot and fix the unmatched pattern".match(specialWords));
// ["the", "knot", "and", "fix", "the", "pattern"]

// Password validation with negative lookaheads
// Must be 8+ chars, contain upper & lower case, number, but no spaces
const passwordValidator = /^(?!.*\s)(?=.*[A-Z])(?=.*[a-z])(?=.*[0-9]).{8,}$/;
console.log(passwordValidator.test("Pass1word"));   // true
console.log(passwordValidator.test("Pass word1"));  // false (contains space)
console.log(passwordValidator.test("password"));    // false (no uppercase, no number)
```

### Practical Examples with Lookarounds

#### Email Validation

```javascript
// Email validation with lookahead for domain
const emailPattern = /^[a-zA-Z0-9._%+-]+@(?=[a-zA-Z0-9.-]+\.[a-zA-Z]{2,})[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
console.log(emailPattern.test("user@example.com"));  // true
console.log(emailPattern.test("invalid@.com"));     // false

// Advanced email validation with multiple lookaheads
const advancedEmail = /^(?=.{1,256}$)(?=.{1,64}@)[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
console.log(advancedEmail.test("user.name+tag@example.co.uk"));  // true
```

#### URL Parsing

```javascript
// Extract URL parameters
const url = "https://example.com/search?name=John&age=30";
const paramPattern = /(?<=\?|&)([^=&]+)=([^&]+)/g;
const params = {};

for (const match of url.matchAll(paramPattern)) {
    params[match[1]] = decodeURIComponent(match[2]);
}
console.log(params);  // { name: "John", age: "30" }

// Extract protocol from URL
const protocolPattern = /^(?<protocol>\w+)(?=:\/\/)/;
const protocolMatch = url.match(protocolPattern);
console.log(protocolMatch.groups.protocol);  // "https"
```

#### Code Refactoring

```javascript
// Find variable declarations not preceded by const, let, or var
const missingDeclaration = /(?<!const\s|let\s|var\s)\b([a-zA-Z_$][a-zA-Z0-9_$]*)\s*=/g;
const code = `
    const x = 1;
    y = 2;
    let z = 3;
    counter = 0;
`;
console.log([...code.matchAll(missingDeclaration)].map(m => m[1]));
// ["y", "counter"] - potential global leaks or missing declarations
```

#### Data Extraction

```javascript
// Extract text between HTML tags but not including the tags
const htmlContent = `<p>First paragraph</p><div>Content in div</div>`;
const textPattern = /(?<=<[^>]+>).*?(?=<\/)/g;
console.log(htmlContent.match(textPattern));  // ["First paragraph", "Content in div"]

// Extract JSON values for specific keys using lookbehind
const jsonData = '{"name": "Alice", "id": 12345, "details": {"age": 30}}';
const namePattern = /(?<="name":\s*")[^"]+/;
const idPattern = /(?<="id":\s*)\d+/;

console.log(jsonData.match(namePattern)[0]);  // "Alice"
console.log(jsonData.match(idPattern)[0]);    // "12345"
```

### Browser Support and Fallbacks

```javascript
// Feature detection for lookbehind (since it's relatively newer)
function supportsLookbehind() {
    try {
        new RegExp('(?<=test)');
        return true;
    } catch (e) {
        return false;
    }
}

// Fallback approach without lookbehind
function extractAfterDollar(text) {
    if (supportsLookbehind()) {
        // Modern approach with lookbehind
        return text.match(/(?<=\$)\d+(\.\d+)?/g);
    } else {
        // Fallback approach without lookbehind
        const matches = [];
        const regex = /\$(\d+(?:\.\d+)?)/g;
        let match;

        while ((match = regex.exec(text)) !== null) {
            matches.push(match[1]);
        }

        return matches;
    }
}

console.log(extractAfterDollar("Items: $10.99, $5"));  // ["10.99", "5"]
```

# Understanding forwardRef in React

## Introduction to forwardRef

`forwardRef` is a method in React that allows components to forward refs they receive to child DOM elements or components. This is a crucial technique for accessing DOM elements or component instances directly within parent components.

```jsx
import React, { forwardRef } from 'react';
```

## Why forwardRef is Needed

In React, refs don't work the same way as regular props - they cannot be automatically passed through components. For example:

```jsx
// THIS WON'T WORK AS EXPECTED
const MyInput = (props) => {
  return <input {...props} />;
};

function Form() {
  const inputRef = useRef(null);

  return (
    <div>
      <MyInput ref={inputRef} /> {/* The ref won't be passed to the input */}
      <button onClick={() => inputRef.current.focus()}>Focus</button>
    </div>
  );
}
```

In this example, the `ref` won't be forwarded to the inner `<input>` element because React components don't automatically pass refs to their children.

## Basic Usage of forwardRef

`forwardRef` creates a React component that forwards any `ref` attribute it receives to another component or DOM element.

```jsx
import React, { forwardRef, useRef } from 'react';

// Create a component that can forward refs
const MyInput = forwardRef((props, ref) => {
  return <input ref={ref} {...props} />;
});

function Form() {
  const inputRef = useRef(null);

  function handleClick() {
    inputRef.current.focus();
    console.log(inputRef.current.value);
  }

  return (
    <div>
      <MyInput ref={inputRef} defaultValue="Hello" />
      <button onClick={handleClick}>Focus Input</button>
    </div>
  );
}
```

## Key Behavior Characteristics of forwardRef

### 1. Component Signature

When using `forwardRef`, your component function will receive two parameters:
- `props`: The normal props passed to the component
- `ref`: The ref that needs to be forwarded

```jsx
const MyComponent = forwardRef((props, ref) => {
  // Component implementation
  return <div ref={ref}>...</div>;
});
```

### 2. Forwarding to DOM Elements

The most common use case is forwarding a ref to a DOM element:

```jsx
const FancyButton = forwardRef((props, ref) => {
  return (
    <button
      ref={ref}
      className="fancy-button"
      {...props}
    >
      {props.children}
    </button>
  );
});
```

### 3. Forwarding to Other Components

You can also forward refs to other components that themselves accept refs:

```jsx
const WrappedInput = forwardRef((props, ref) => {
  return (
    <div className="input-wrapper">
      <MyInput ref={ref} {...props} />
    </div>
  );
});
```

### 4. Exposing a Different Interface with useImperativeHandle

Sometimes you want to customize what the parent component can do with the ref. For this, combine `forwardRef` with `useImperativeHandle`:

```jsx
import React, { forwardRef, useRef, useImperativeHandle } from 'react';

const CustomInput = forwardRef((props, ref) => {
  const inputRef = useRef(null);

  // Expose only specific methods to the parent
  useImperativeHandle(ref, () => ({
    focus: () => {
      inputRef.current.focus();
    },
    clear: () => {
      inputRef.current.value = '';
    },
    // Don't expose the actual DOM element
  }));

  return <input ref={inputRef} {...props} />;
});

function Form() {
  const inputRef = useRef(null);

  function handleSubmit() {
    // We can use the methods we exposed
    console.log('Input value:', inputRef.current.value); // This won't work as we didn't expose value
    inputRef.current.focus();
    inputRef.current.clear();
  }

  return (
    <form onSubmit={handleSubmit}>
      <CustomInput ref={inputRef} />
      <button type="submit">Submit</button>
    </form>
  );
}
```

### 5. Display Name for DevTools

For better debugging, set a display name for components wrapped in `forwardRef`:

```jsx
const FancyButton = forwardRef((props, ref) => {
  return <button ref={ref} className="fancy-button" {...props} />;
});

// Set the display name
FancyButton.displayName = 'FancyButton';
```

## Advanced forwardRef Patterns

### 1. Conditional Ref Forwarding

You might want to dynamically forward refs to different elements:

```jsx
const ComplexInput = forwardRef((props, ref) => {
  const { variant = 'default', ...otherProps } = props;

  if (variant === 'textarea') {
    return <textarea ref={ref} {...otherProps} />;
  }

  if (variant === 'select') {
    return (
      <select ref={ref} {...otherProps}>
        {props.children}
      </select>
    );
  }

  // Default case: standard input
  return <input ref={ref} {...otherProps} />;
});
```

### 2. Higher-Order Component with forwardRef

Creating a higher-order component that properly handles refs:

```jsx
function withLogger(Component) {
  const WithLogger = forwardRef((props, ref) => {
    console.log('Component rendering with props:', props);

    return <Component ref={ref} {...props} />;
  });

  WithLogger.displayName = `WithLogger(${Component.displayName || Component.name || 'Component'})`;

  return WithLogger;
}

// Usage
const LoggedInput = withLogger(
  forwardRef((props, ref) => <input ref={ref} {...props} />)
);
```

### 3. Using TypeScript with forwardRef

```tsx
import React, { forwardRef, ForwardedRef } from 'react';

interface ButtonProps {
  type?: 'button' | 'submit' | 'reset';
  onClick?: () => void;
  children: React.ReactNode;
}

// Define a properly typed forwardRef component
const Button = forwardRef<HTMLButtonElement, ButtonProps>(
  (props, ref: ForwardedRef<HTMLButtonElement>) => {
    const { type = 'button', children, ...rest } = props;

    return (
      <button
        ref={ref}
        type={type}
        {...rest}
      >
        {children}
      </button>
    );
  }
);

Button.displayName = 'Button';

export default Button;
```

## Common Use Cases for forwardRef

### 1. Form Inputs with Focus Management

```jsx
const FormInput = forwardRef((props, ref) => {
  const { label, error, ...inputProps } = props;

  return (
    <div className="form-field">
      {label && <label>{label}</label>}
      <input ref={ref} {...inputProps} />
      {error && <span className="error">{error}</span>}
    </div>
  );
});

function LoginForm() {
  const emailRef = useRef(null);
  const passwordRef = useRef(null);

  function handleSubmit(e) {
    e.preventDefault();
    if (!emailRef.current.value) {
      emailRef.current.focus();
      return;
    }
    // Process form...
  }

  return (
    <form onSubmit={handleSubmit}>
      <FormInput ref={emailRef} label="Email" type="email" />
      <FormInput ref={passwordRef} label="Password" type="password" />
      <button type="submit">Login</button>
    </form>
  );
}
```

### 2. Measurement and Animation

```jsx
const MeasuredComponent = forwardRef((props, ref) => {
  const internalRef = useRef(null);

  // Merge the forwarded ref with our internal logic
  useEffect(() => {
    if (!ref) return;

    // If ref is a function
    if (typeof ref === 'function') {
      ref(internalRef.current);
    }
    // If ref is a mutable object
    else if (ref.hasOwnProperty('current')) {
      ref.current = internalRef.current;
    }
  }, [ref]);

  return <div ref={internalRef} {...props} />;
});

function Animation() {
  const elementRef = useRef(null);

  useEffect(() => {
    if (!elementRef.current) return;

    // Access the DOM element for measurements/animations
    const { width, height } = elementRef.current.getBoundingClientRect();
    console.log(`Element size: ${width}x${height}`);

    // You could start animations here
  }, []);

  return (
    <MeasuredComponent ref={elementRef}>
      Content to be measured
    </MeasuredComponent>
  );
}
```

### 3. Integration with Third-Party Libraries

```jsx
const ChartComponent = forwardRef((props, ref) => {
  const chartContainerRef = useRef(null);
  const chartInstance = useRef(null);

  useEffect(() => {
    if (!chartContainerRef.current) return;

    // Initialize third-party chart library
    chartInstance.current = new ChartLibrary(chartContainerRef.current, {
      data: props.data,
      options: props.options
    });

    // Forward necessary methods to the parent
    if (ref) {
      ref.current = {
        updateData: (newData) => chartInstance.current.update(newData),
        export: () => chartInstance.current.exportAsImage()
      };
    }

    // Cleanup
    return () => {
      if (chartInstance.current) {
        chartInstance.current.destroy();
      }
    };
  }, [props.data, props.options, ref]);

  return <div ref={chartContainerRef} className="chart-container" />;
});

function Dashboard() {
  const chartRef = useRef(null);

  function handleExportClick() {
    if (chartRef.current) {
      const imageUrl = chartRef.current.export();
      // Use the exported image...
    }
  }

  return (
    <div>
      <ChartComponent
        ref={chartRef}
        data={[1, 2, 3, 4]}
        options={{ animate: true }}
      />
      <button onClick={handleExportClick}>Export Chart</button>
    </div>
  );
}
```

## Potential Pitfalls with forwardRef

### 1. Overusing Refs and Imperative Code

While refs are powerful, they often lead to imperative code that can be harder to maintain than declarative React patterns. Only use refs when necessary, such as for:
- Focus management
- Text selection
- Third-party DOM library integration
- Imperative animations

### 2. Forgetting to Handle Missing Refs

When a component isn't given a ref, the ref parameter will be `null`. Always handle this case:

```jsx
const Button = forwardRef((props, ref) => {
  // Good: Handle when ref is null
  return <button ref={ref || undefined} {...props} />;
});
```

### 3. Not Cleaning Up Refs

When using imperative APIs through refs, don't forget to clean up:

```jsx
const Player = forwardRef((props, ref) => {
  const videoRef = useRef(null);

  useImperativeHandle(ref, () => ({
    play: () => videoRef.current.play(),
    pause: () => videoRef.current.pause()
  }));

  useEffect(() => {
    return () => {
      // Ensure video stops playing when component unmounts
      if (videoRef.current) {
        videoRef.current.pause();
      }
    };
  }, []);

  return <video ref={videoRef} src={props.src} />;
});
```

## Performance Considerations

`forwardRef` itself adds minimal overhead, but be careful with how you use refs:

1. **Avoid creating new ref callbacks on every render**:

```jsx
// Bad: Creates a new function every render
<MyInput ref={(el) => { this.inputRef = el; }} />

// Good: Stable callback
const setInputRef = useCallback((el) => {
  this.inputRef = el;
}, []);

<MyInput ref={setInputRef} />
```

2. **Be careful with useImperativeHandle dependencies**:

```jsx
// Potentially problematic: may recreate methods unnecessarily
useImperativeHandle(ref, () => ({
  doSomething: () => {
    // Implementation that uses props or state
  }
}), []); // Empty dependency array!

// Better: Include dependencies that affect the imperative methods
useImperativeHandle(ref, () => ({
  doSomething: () => {
    // Implementation
  }
}), [dependency1, dependency2]);
```

## Conclusion

`forwardRef` in React is a powerful pattern that enables refs to flow through component boundaries,
facilitating direct DOM access and component instance interactions.
It's especially valuable for reusable component libraries, form components,
and integrations with imperative APIs.

When used judiciously, `forwardRef` helps bridge the gap between React's declarative programming model
and scenarios that require imperative code, enabling more flexible component design while maintaining a clean API.

Remember that while `forwardRef` is powerful, it's generally best to keep most component
interactions prop-based and to use refs sparingly for cases where the React declarative model isn't sufficient.


# Performant Child Component Creation in React: Minimizing Rerenders

When building React applications with complex component hierarchies, managing renders efficiently becomes critical for performance. Let's explore strategies to optimize child components, particularly when you have a parent component that gathers data and children that handle layout composition.

## Key Principles for Performance Optimization

### 1. Component Memoization

```jsx
import React, { memo } from 'react';

// Basic memoization
const ChildComponent = memo(function ChildComponent({ name, onClick }) {
  console.log(`Rendering ${name}`);
  return (
    <div className="child-item" onClick={onClick}>
      {name}
    </div>
  );
});

// Parent component
function ParentComponent({ data }) {
  return (
    <div className="parent">
      {data.map(item => (
        <ChildComponent
          key={item.id}
          name={item.name}
          onClick={() => console.log(item.name)}
        />
      ))}
    </div>
  );
}
```

**Why it's inefficient**: Even with `memo`, the inline `onClick` function is recreated on every render of the parent, causing child components to rerender.

**Improved version**:

```jsx
function ParentComponent({ data }) {
  // Create stable callback functions with useCallback
  const handleItemClick = useCallback((id) => {
    console.log(`Clicked item ${id}`);
  }, []);

  return (
    <div className="parent">
      {data.map(item => (
        <ChildComponent
          key={item.id}
          name={item.name}
          onClick={() => handleItemClick(item.id)}
          // This still creates a new function on each render!
        />
      ))}
    </div>
  );
}
```

**Further improved**:

```jsx
function ParentComponent({ data }) {
  // Memoize callbacks per item
  const clickHandlers = useMemo(() => {
    return data.reduce((acc, item) => {
      acc[item.id] = () => console.log(`Clicked item ${item.id}`);
      return acc;
    }, {});
  }, [data]);

  return (
    <div className="parent">
      {data.map(item => (
        <ChildComponent
          key={item.id}
          name={item.name}
          onClick={clickHandlers[item.id]}
        />
      ))}
    </div>
  );
}
```

### 2. Data Preparation and Props Minimization

Move data transformations up in the component tree to avoid redundant calculations:

```jsx
// Before: Each child might process data independently
function ParentComponent({ rawData }) {
  return (
    <div>
      {rawData.map(item => (
        <ChildComponent
          key={item.id}
          rawData={item}
          // Passing large raw data objects to children
        />
      ))}
    </div>
  );
}

// After: Process data once in the parent
function ParentComponent({ rawData }) {
  // Transform all data once
  const processedData = useMemo(() => {
    return rawData.map(item => ({
      id: item.id,
      displayName: `${item.firstName} ${item.lastName}`,
      isActive: item.status === 'active',
      // Only needed properties, pre-computed
    }));
  }, [rawData]);

  return (
    <div>
      {processedData.map(item => (
        <ChildComponent
          key={item.id}
          // Pass only what the child needs
          name={item.displayName}
          active={item.isActive}
        />
      ))}
    </div>
  );
}
```

### 3. Component Composition Strategies

Use component composition to control what re-renders:

```jsx
function DataProvider({ children, data }) {
  // Fetch/process data here
  const processedData = useMemo(() => processData(data), [data]);

  // Pass processed data to children
  return children(processedData);
}

function LayoutComponent({ renderData }) {
  // Only focused on layout - doesn't rerender when data changes
  return (
    <div className="layout">
      <header>My App</header>
      <main>{renderData()}</main>
      <footer>© 2023</footer>
    </div>
  );
}

// Usage
function App({ data }) {
  return (
    <DataProvider data={data}>
      {(processedData) => (
        <LayoutComponent
          renderData={() => (
            <DataDisplay data={processedData} />
          )}
        />
      )}
    </DataProvider>
  );
}
```

### 4. Context Optimization

When using context, split it based on update frequency:

```jsx
// Bad: Single context for everything
const AppContext = React.createContext();

function AppProvider({ children }) {
  const [user, setUser] = useState(null);
  const [theme, setTheme] = useState('light');
  const [notifications, setNotifications] = useState([]);

  // Everything rerenders when any value changes
  return (
    <AppContext.Provider value={{
      user, setUser,
      theme, setTheme,
      notifications, setNotifications
    }}>
      {children}
    </AppContext.Provider>
  );
}

// Good: Split contexts by update frequency
const UserContext = React.createContext();
const ThemeContext = React.createContext();
const NotificationContext = React.createContext();

function AppProvider({ children }) {
  const [user, setUser] = useState(null);
  const [theme, setTheme] = useState('light');
  const [notifications, setNotifications] = useState([]);

  return (
    <UserContext.Provider value={{ user, setUser }}>
      <ThemeContext.Provider value={{ theme, setTheme }}>
        <NotificationContext.Provider value={{ notifications, setNotifications }}>
          {children}
        </NotificationContext.Provider>
      </ThemeContext.Provider>
    </UserContext.Provider>
  );
}
```

## Advanced Techniques for Performance

### 1. Component Content Segregation

Divide components based on their update frequency:

```jsx
// Define components based on what causes them to update
const StaticHeader = memo(function StaticHeader() {
  // Never changes after initial render
  return <header>Application Header</header>;
});

const UserProfileSection = memo(function UserProfileSection({ user }) {
  // Only updates when user changes
  return (
    <div className="profile">
      <img src={user.avatar} alt={user.name} />
      <h2>{user.name}</h2>
    </div>
  );
});

const DynamicContentSection = function DynamicContentSection({ content }) {
  // Updates frequently
  return (
    <div className="content">
      {content.map(item => (
        <ContentItem key={item.id} item={item} />
      ))}
    </div>
  );
};

// Main layout component
function Dashboard({ user, content }) {
  return (
    <div className="dashboard">
      <StaticHeader />
      <div className="main-area">
        <UserProfileSection user={user} />
        <DynamicContentSection content={content} />
      </div>
    </div>
  );
}
```

### 2. Virtualization for Large Lists

Use virtualization for large data sets:

```jsx
import { FixedSizeList } from 'react-window';

function VirtualizedList({ items }) {
  // Render only visible items
  const Row = ({ index, style }) => (
    <div style={style} className="list-item">
      {items[index].name}
    </div>
  );

  return (
    <FixedSizeList
      height={500}
      width="100%"
      itemCount={items.length}
      itemSize={50}
    >
      {Row}
    </FixedSizeList>
  );
}
```

### 3. State Colocation

Keep state as close as possible to where it's needed:

```jsx
// Bad: All state in parent
function ParentForm() {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');
  const [address, setAddress] = useState('');
  const [showAddressForm, setShowAddressForm] = useState(false);

  // ... handle lots of state

  return (
    <form>
      <InputField
        label="Name"
        value={name}
        onChange={e => setName(e.target.value)}
      />
      <InputField
        label="Email"
        value={email}
        onChange={e => setEmail(e.target.value)}
      />
      <button type="button" onClick={() => setShowAddressForm(!showAddressForm)}>
        {showAddressForm ? 'Hide Address' : 'Add Address'}
      </button>

      {showAddressForm && (
        <InputField
          label="Address"
          value={address}
          onChange={e => setAddress(e.target.value)}
        />
      )}
    </form>
  );
}

// Good: Colocated state
function AddressSection() {
  const [address, setAddress] = useState('');
  const [showAddressForm, setShowAddressForm] = useState(false);

  return (
    <div className="address-section">
      <button type="button" onClick={() => setShowAddressForm(!showAddressForm)}>
        {showAddressForm ? 'Hide Address' : 'Add Address'}
      </button>

      {showAddressForm && (
        <InputField
          label="Address"
          value={address}
          onChange={e => setAddress(e.target.value)}
        />
      )}
    </div>
  );
}

function ParentForm() {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');

  return (
    <form>
      <InputField
        label="Name"
        value={name}
        onChange={e => setName(e.target.value)}
      />
      <InputField
        label="Email"
        value={email}
        onChange={e => setEmail(e.target.value)}
      />
      <AddressSection />
    </form>
  );
}
```

### 4. Referential Stability with Props Collections

Create stable prop collections:

```jsx
function ParentComponent() {
  // Values that might change
  const [user, setUser] = useState({ name: 'John', role: 'admin' });
  const [theme, setTheme] = useState('dark');

  // Create stable collection of props for HeaderSection
  const headerProps = useMemo(() => ({
    title: 'Dashboard',
    user: user.name,
    theme
  }), [user.name, theme]);

  // Create stable collection of props for ContentSection
  const contentProps = useMemo(() => ({
    role: user.role,
    items: getSectionItems(user.role)
  }), [user.role]);

  return (
    <div className="app">
      <HeaderSection {...headerProps} />
      <ContentSection {...contentProps} />
    </div>
  );
}
```

### 5. Render Props for Flexible Composition

Use render props to decouple data from presentation:

```jsx
function DataManager({ children, dataSource }) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    setLoading(true);
    fetchData(dataSource)
      .then(result => {
        setData(result);
        setLoading(false);
      })
      .catch(err => {
        setError(err);
        setLoading(false);
      });
  }, [dataSource]);

  // Pass rendering control to consumer while providing data state
  return children({ data, loading, error });
}

// Usage
function UserDashboard() {
  return (
    <DataManager dataSource="users/current">
      {({ data, loading, error }) => {
        if (loading) return <LoadingSpinner />;
        if (error) return <ErrorMessage error={error} />;

        return (
          <div className="dashboard">
            <WelcomeHeader username={data.name} />
            <StatisticsPanel stats={data.stats} />
            <RecentActivity activities={data.recentActivities} />
          </div>
        );
      }}
    </DataManager>
  );
}
```

### 6. State Machines for Complex State Logic

For complex components, use state machines to make renders predictable:

```jsx
import { useMachine } from '@xstate/react';
import { createMachine } from 'xstate';

// Define possible states and transitions
const formMachine = createMachine({
  id: 'form',
  initial: 'editing',
  states: {
    editing: {
      on: { SUBMIT: 'submitting' }
    },
    submitting: {
      on: {
        SUCCESS: 'success',
        ERROR: 'error'
      }
    },
    error: {
      on: { RETRY: 'submitting' }
    },
    success: {
      type: 'final'
    }
  }
});

function SmartForm() {
  const [state, send] = useMachine(formMachine);
  const [formData, setFormData] = useState({});

  const handleSubmit = async (e) => {
    e.preventDefault();
    send('SUBMIT');

    try {
      await submitData(formData);
      send('SUCCESS');
    } catch (error) {
      send('ERROR');
    }
  };

  // Render based on current state
  return (
    <div className="form-container">
      {state.matches('editing') && (
        <form onSubmit={handleSubmit}>
          {/* Form fields */}
          <button type="submit">Submit</button>
        </form>
      )}

      {state.matches('submitting') && <LoadingSpinner />}

      {state.matches('error') && (
        <div>
          <ErrorMessage />
          <button onClick={() => send('RETRY')}>Try Again</button>
        </div>
      )}

      {state.matches('success') && <SuccessMessage />}
    </div>
  );
}
```

## Real-World Advanced Pattern Example

Here's a complete example implementing several of these patterns for a data-heavy dashboard:

```jsx
import React, { useState, useEffect, useCallback, useMemo, memo } from 'react';

// Pure layout component - doesn't change when data changes
const DashboardLayout = memo(function DashboardLayout({
  header,
  sidebar,
  mainContent,
  footer
}) {
  console.log('Rendering: DashboardLayout');
  return (
    <div className="dashboard">
      <header className="dashboard-header">{header}</header>
      <div className="dashboard-body">
        <aside className="dashboard-sidebar">{sidebar}</aside>
        <main className="dashboard-main">{mainContent}</main>
      </div>
      <footer className="dashboard-footer">{footer}</footer>
    </div>
  );
});

// Data processing component - processes data but doesn't render UI
function DataProcessor({ data, children }) {
  // Process data once and memoize the result
  const processedData = useMemo(() => {
    console.log('Processing data...');
    return {
      userStats: calculateUserStats(data.users),
      recentOrders: processOrders(data.orders),
      // ...other data transformations
    };
  }, [data.users, data.orders]);

  // Pass processed data to children
  return children(processedData);
}

// Specific content components - each one gets only what it needs
const UserStats = memo(function UserStats({ stats }) {
  console.log('Rendering: UserStats');
  return (
    <div className="user-stats">
      <h3>User Statistics</h3>
      <div className="stats-grid">
        <div className="stat-card">
          <span className="stat-value">{stats.totalUsers}</span>
          <span className="stat-label">Total Users</span>
        </div>
        <div className="stat-card">
          <span className="stat-value">{stats.activeUsers}</span>
          <span className="stat-label">Active Users</span>
        </div>
        {/* Other stats */}
      </div>
    </div>
  );
});

const RecentOrders = memo(function RecentOrders({ orders, onViewOrder }) {
  console.log('Rendering: RecentOrders');
  return (
    <div className="recent-orders">
      <h3>Recent Orders</h3>
      <ul className="order-list">
        {orders.slice(0, 5).map(order => (
          <li key={order.id} className="order-item">
            <span>Order #{order.id}</span>
            <span>${order.total.toFixed(2)}</span>
            <button onClick={() => onViewOrder(order.id)}>
              View Details
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
});

// The main dashboard component
function Dashboard() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [selectedOrderId, setSelectedOrderId] = useState(null);

  // Fetch data
  useEffect(() => {
    fetchDashboardData()
      .then(result => {
        setData(result);
        setLoading(false);
      });
  }, []);

  // Stable callbacks
  const handleViewOrder = useCallback((orderId) => {
    setSelectedOrderId(orderId);
    // ...additional logic
  }, []);

  // Stable header component
  const headerComponent = useMemo(() => (
    <h1>Admin Dashboard</h1>
  ), []);

  // Stable footer component
  const footerComponent = useMemo(() => (
    <div>© 2023 My Company</div>
  ), []);

  // Render loading state if needed
  if (loading) return <LoadingSpinner />;

  return (
    <DataProcessor data={data}>
      {(processedData) => (
        <DashboardLayout
          header={headerComponent}
          sidebar={
            <nav className="nav-menu">
              {/* Navigation items */}
            </nav>
          }
          mainContent={
            <>
              <UserStats stats={processedData.userStats} />
              <RecentOrders
                orders={processedData.recentOrders}
                onViewOrder={handleViewOrder}
              />
              {selectedOrderId && (
                <OrderDetails
                  orderId={selectedOrderId}
                  onClose={() => setSelectedOrderId(null)}
                />
              )}
            </>
          }
          footer={footerComponent}
        />
      )}
    </DataProcessor>
  );
}
```

## Performance Analysis and Optimization Tools

To identify unnecessarily rendering components:

1. **React DevTools Profiler**: Use React DevTools' Profiler to record renders and see which
components are rendering unnecessarily.

2. **Performance monitoring**:

```jsx
// Add a custom hook to log renders
function useTraceUpdate(props) {
  const prev = useRef(props);
  useEffect(() => {
    const changedProps = Object.entries(props).reduce((ps, [k, v]) => {
      if (prev.current[k] !== v) {
        ps[k] = [prev.current[k], v];
      }
      return ps;
    }, {});
    if (Object.keys(changedProps).length > 0) {
      console.log('Changed props:', changedProps);
    }
    prev.current = props;
  });
}

// Usage in component
function MyComponent(props) {
  useTraceUpdate(props);
  return <div>{/* ... */}</div>;
}
```

3. **why-did-you-render**: Add the `why-did-you-render` library to your project to get detailed
information about what caused a component to re-render.

## Summary of Best Practices

1. **Memoize components** that don't need to rerender when parent rerenders
2. **Memoize expensive calculations** with `useMemo`
3. **Stabilize callbacks** with `useCallback`
4. **Prepare data at the highest level possible** to avoid redundant processing
5. **Pass minimal props** to child components - only what they really need
6. **Use component composition** to separate stable and changing parts
7. **Split contexts** based on update frequency
8. **Colocate state** with the components that need it
9. **Create stable prop collections** with `useMemo`
10. **Use render props or children as functions** for flexible compositions
11. **Consider state machines** for complex state logic
12. **Virtual list rendering** for large datasets

By following these patterns, you can build React applications that maintain high performance
even with complex data and deep component hierarchies.

# Optimizing Data Manipulation in JavaScript: Loops, Types, and Performance

## Introduction to JavaScript Loops and Data Manipulation

Data manipulation is at the heart of modern JavaScript applications. This guide explores different looping methods, data types, and optimization techniques to ensure you're processing data in the most performant way possible.

## Core Loop Types and Their Performance Characteristics

### 1. for Loop (Classic)

The traditional `for` loop remains one of the fastest iteration methods in JavaScript.

```javascript
const array = [1, 2, 3, 4, 5];

// Classic for loop
for (let i = 0; i < array.length; i++) {
  // Process array[i]
}

// Performance optimization: cache the length
for (let i = 0, len = array.length; i < len; i++) {
  // Process array[i]
}
```

**Performance characteristics**:
- Very fast execution - often the fastest option for simple iterations
- Low abstraction overhead
- Manual index management (both an advantage and disadvantage)
- No closures or function calls per iteration
- Direct access to the array index

**Best used when**:
- Raw performance is critical
- You need the index
- You need to manipulate the iteration (skip items, break early)
- The loop body is simple

### 2. for...of Loop

Introduced in ES6, the `for...of` loop provides a cleaner syntax for iterating over iterable objects.

```javascript
// for...of loop for arrays
for (const item of array) {
  // Process item
}

// for...of with index (using entries())
for (const [index, item] of array.entries()) {
  // Process item with index
}
```

**Performance characteristics**:
- Generally faster than `forEach`, but slower than classic `for`
- Cleaner syntax than classic `for`
- Handles any iterable (arrays, strings, maps, sets, generators)
- Can use `break` and `continue`

**Best used when**:
- You need to iterate over any iterable object
- You want clean, readable code
- You might need to break or continue
- You don't need to optimize for absolute maximum performance

### 3. forEach Method

Array's built-in `forEach` method takes a callback function that executes for each element.

```javascript
array.forEach((item, index, array) => {
  // Process item
});
```

**Performance characteristics**:
- Slower than `for` and `for...of` due to function call overhead
- Cleaner, more declarative syntax
- Cannot break early (must process all elements)
- Creates a new function scope for each iteration

**Best used when**:
- You prioritize readability over raw performance
- You don't need to break the loop early
- You're performing simple operations on each item

### 4. map, filter, reduce (Functional Approaches)

These methods create new arrays based on transformations of the original data.

```javascript
// map - transform each element
const doubled = array.map(item => item * 2);

// filter - keep elements that pass a test
const evens = array.filter(item => item % 2 === 0);

// reduce - accumulate a single result
const sum = array.reduce((total, item) => total + item, 0);

// Chaining methods
const sumOfDoubledEvens = array
  .filter(item => item % 2 === 0)
  .map(item => item * 2)
  .reduce((total, item) => total + item, 0);
```

**Performance characteristics**:
- Creates new arrays (uses additional memory)
- Has function call overhead for each element
- More declarative and often more readable
- Immutable approach (doesn't modify original data)

**Best used when**:
- You need to transform data into a new form
- You want immutable operations
- Code readability is important
- Memory usage isn't a critical constraint

### 5. for...in Loop

The `for...in` loop iterates over an object's enumerable properties.

```javascript
const object = { a: 1, b: 2, c: 3 };

for (const key in object) {
  if (Object.hasOwnProperty.call(object, key)) {
    const value = object[key];
    // Process key/value
  }
}
```

**Performance characteristics**:
- Slower than other loops for arrays (not optimized for array iteration)
- Iterates over all enumerable properties (including inherited ones)
- Generally should not be used for arrays

**Best used when**:
- You need to iterate over object properties
- You need access to property names/keys
- Order of iteration isn't important

### 6. while and do...while Loops

These loops offer more control over iteration conditions.

```javascript
// while loop
let i = 0;
while (i < array.length) {
  // Process array[i]
  i++;
}

// do...while loop (always executes at least once)
let j = 0;
do {
  // Process array[j]
  j++;
} while (j < array.length);
```

**Performance characteristics**:
- Similar performance to classic `for` loops
- Useful when exit condition is complex
- Good for indeterminate number of iterations

**Best used when**:
- Loop continuation depends on conditions other than a simple counter
- You need to ensure the loop body executes at least once (`do...while`)
- You're reading data from an external source with unknown length

## Performance Comparison

For most array operations with small to medium-sized arrays (up to a few thousand elements), the performance differences between loop types won't significantly impact your application. However, for performance-critical code or large datasets, here's a general performance ranking (fastest to slowest):

1. Classic `for` loop
2. `while` loop
3. `for...of` loop
4. Array methods (`forEach`, `map`, `filter`, etc.)
5. `for...in` loop (for arrays)

## Data Types and Performance Optimization

The choice of data structure significantly impacts performance when processing large datasets.

### Arrays vs. Objects

```javascript
// Array lookups by index are fast
const array = [10, 20, 30, 40, 50];
const item = array[2];  // O(1) operation

// Object lookups by key are also fast
const object = { a: 10, b: 20, c: 30 };
const value = object.b;  // O(1) operation
```

**Key performance considerations**:
- Arrays have faster iteration performance
- Objects have faster key-based lookups
- Arrays maintain order; regular objects don't guarantee property order
- Arrays have O(n) lookups when searching by value
- Both have O(1) lookups when accessing by index/key

### Typed Arrays

For numeric data, Typed Arrays can offer better performance:

```javascript
// Regular array
const regularArray = [1, 2, 3, 4, 5];

// Typed array
const typedArray = new Int32Array([1, 2, 3, 4, 5]);

// Faster mathematical operations with typed arrays
function sumArray(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
}
```

**Benefits of Typed Arrays**:
- More efficient memory usage
- Faster operations for numeric computation
- Better performance for binary data manipulation
- Array-like API

### Sets and Maps

Modern JavaScript offers specialized collections for specific use cases:

```javascript
// Sets for unique values
const uniqueItems = new Set([1, 2, 3, 2, 1]);
console.log([...uniqueItems]);  // [1, 2, 3]

// Maps for key-value pairs
const userRoles = new Map();
userRoles.set('john', 'admin');
userRoles.set('sarah', 'editor');
console.log(userRoles.get('john'));  // 'admin'
```

**Performance benefits**:
- `Set`: O(1) for add, delete, has operations
- `Map`: O(1) for get, set, has, delete operations
- Both maintain insertion order
- Can use any value type as keys (unlike objects)

## Optimized Data Manipulation Patterns

### 1. Filtering and Finding

```javascript
const users = [
  { id: 1, name: 'Alice', age: 25, active: true },
  { id: 2, name: 'Bob', age: 30, active: false },
  { id: 3, name: 'Charlie', age: 35, active: true },
  { id: 4, name: 'David', age: 40, active: true },
];

// Option 1: filter (creates new array)
const activeUsers = users.filter(user => user.active);

// Option 2: for loop with early exit (finding first match)
function findFirstActiveUser(users) {
  for (let i = 0; i < users.length; i++) {
    if (users[i].active) {
      return users[i];
    }
  }
  return null;
}

// Option 3: Using find method (more readable, stops on first match)
const firstActiveUser = users.find(user => user.active);

// Option 4: Using Set for unique values
const uniqueAges = [...new Set(users.map(user => user.age))];
```

**Performance optimization**:
- Use `find` instead of `filter` when you only need the first match
- Use `some` or `every` when you only need to check existence
- Use `for` loop with `break` for maximum performance with early exit
- Use `Set` for efficient unique value extraction

### 2. Transforming Data (Mapping)

```javascript
// Option 1: map (functional, immutable)
const userNames = users.map(user => user.name);

// Option 2: for loop with new array (slightly faster)
function getUserNames(users) {
  const names = new Array(users.length);
  for (let i = 0; i < users.length; i++) {
    names[i] = users[i].name;
  }
  return names;
}

// Option 3: in-place transformation (fastest but mutates original)
function transformUsersInPlace(users) {
  for (let i = 0; i < users.length; i++) {
    users[i].formattedName = `${users[i].name} (${users[i].age})`;
  }
  return users;
}
```

**Performance considerations**:
- `map` creates a new array (uses more memory)
- Preallocating the result array size can improve performance
- In-place mutation is fastest but has side effects
- Consider memory usage vs. code clarity

### 3. Aggregating Data (Reducing)

```javascript
// Option 1: reduce (functional approach)
const totalAge = users.reduce((sum, user) => sum + user.age, 0);
const averageAge = totalAge / users.length;

// Option 2: for loop (slightly more performant)
function calculateAverageAge(users) {
  let sum = 0;
  for (let i = 0; i < users.length; i++) {
    sum += users[i].age;
  }
  return sum / users.length;
}

// Option 3: Advanced grouping with reduce
const usersByAgeGroup = users.reduce((groups, user) => {
  const ageGroup = Math.floor(user.age / 10) * 10;
  groups[ageGroup] = groups[ageGroup] || [];
  groups[ageGroup].push(user);
  return groups;
}, {});
```

**Optimization tips**:
- `reduce` is versatile but can be less readable for complex operations
- Simple for loops may be more performant for basic aggregations
- For complex transformations, consider breaking into multiple steps

### 4. Sorting Data

```javascript
// Option 1: Basic sort (sorts in place)
users.sort((a, b) => a.age - b.age);

// Option 2: Sort copy to avoid mutation
const sortedUsers = [...users].sort((a, b) => a.age - b.age);

// Option 3: Stable sort by multiple fields
function stableSortByNameAndAge(users) {
  return [...users].sort((a, b) => {
    // First by age
    if (a.age !== b.age) {
      return a.age - b.age;
    }
    // Then by name
    return a.name.localeCompare(b.name);
  });
}
```

**Performance notes**:
- JavaScript's native sort is O(n log n) on average
- Sorting is relatively expensive - avoid unnecessary sorts
- Consider maintaining sorted data if you sort frequently
- For very large arrays, consider implementing more efficient algorithms

### 5. Processing Large Datasets

For very large datasets, consider batching operations:

```javascript
// Process array in chunks to avoid blocking the main thread
function processLargeArray(array, processFn, chunkSize = 1000) {
  let index = 0;

  function processNextChunk() {
    const chunk = array.slice(index, index + chunkSize);
    index += chunkSize;

    // Process this chunk
    chunk.forEach(processFn);

    // Schedule next chunk if not done
    if (index < array.length) {
      setTimeout(processNextChunk, 0);
    }
  }

  processNextChunk();
}

// Usage
const largeArray = new Array(100000).fill().map((_, i) => i);
processLargeArray(largeArray, item => {
  // Complex processing
});
```

For truly massive datasets, consider Web Workers:

```javascript
// main.js
const worker = new Worker('dataWorker.js');

worker.postMessage({
  data: largeDataset,
  operation: 'transform'
});

worker.onmessage = function(e) {
  const result = e.data;
  // Use processed result
};

// dataWorker.js
self.onmessage = function(e) {
  const { data, operation } = e.data;

  let result;
  if (operation === 'transform') {
    result = data.map(item => /* complex transformation */);
  }

  self.postMessage(result);
};
```

## Advanced Optimization Techniques

### 1. Memoization for Expensive Operations

```javascript
// Simple memoization function
function memoize(fn) {
  const cache = new Map();

  return function(...args) {
    const key = JSON.stringify(args);
    if (cache.has(key)) {
      return cache.get(key);
    }

    const result = fn.apply(this, args);
    cache.set(key, result);
    return result;
  };
}

// Usage
const expensiveCalculation = memoize(function(a, b) {
  console.log('Calculating...');
  // Simulate expensive operation
  return a * b;
});

console.log(expensiveCalculation(4, 5));  // Calculates and returns 20
console.log(expensiveCalculation(4, 5));  // Returns cached result 20
```

### 2. Optimized Bulk Operations

```javascript
// Bad: Multiple DOM updates in a loop
function updateListItemsBad(items) {
  const list = document.getElementById('myList');

  // Causes reflow/repaint on each iteration
  items.forEach(item => {
    const li = document.createElement('li');
    li.textContent = item;
    list.appendChild(li);
  });
}

// Good: Use DocumentFragment for bulk DOM updates
function updateListItemsGood(items) {
  const list = document.getElementById('myList');
  const fragment = document.createDocumentFragment();

  items.forEach(item => {
    const li = document.createElement('li');
    li.textContent = item;
    fragment.appendChild(li);
  });

  // Single DOM update
  list.appendChild(fragment);
}
```

### 3. Lazy Evaluation with Generators

```javascript
// Generate infinite sequence of even numbers
function* evenNumbers() {
  let n = 0;
  while (true) {
    yield n;
    n += 2;
  }
}

// Take only what you need
function take(iterator, count) {
  const result = [];
  for (let i = 0; i < count; i++) {
    const next = iterator.next();
    if (next.done) break;
    result.push(next.value);
  }
  return result;
}

const evens = evenNumbers();
console.log(take(evens, 5));  // [0, 2, 4, 6, 8]
```

## Practical Performance Recipes

### 1. Finding Unique Items

```javascript
// Option 1: Using Set (fastest for primitive values)
function uniqueValues(array) {
  return [...new Set(array)];
}

// Option 2: Using filter (works with older browsers)
function uniqueValuesFilter(array) {
  return array.filter((item, index) => array.indexOf(item) === index);
}

// Option 3: For object arrays, unique by property
function uniqueById(array) {
  const seen = new Map();
  return array.filter(item => {
    if (seen.has(item.id)) {
      return false;
    }
    seen.set(item.id, true);
    return true;
  });
}
```

### 2. Efficient Data Searching

```javascript
// Option 1: Build a Map for O(1) lookups
function buildUserMap(users) {
  const userMap = new Map();
  for (const user of users) {
    userMap.set(user.id, user);
  }
  return userMap;
}

const userMap = buildUserMap(users);
const user = userMap.get(2);  // O(1) lookup

// Option 2: Index data for faster searches
function indexUsersByName(users) {
  const index = {};
  for (const user of users) {
    const firstLetter = user.name[0].toLowerCase();
    index[firstLetter] = index[firstLetter] || [];
    index[firstLetter].push(user);
  }
  return index;
}

const nameIndex = indexUsersByName(users);
const usersStartingWithA = nameIndex['a'] || [];  // Fast lookup
```

### 3. Efficient Intersection and Difference

```javascript
// Find intersection of two arrays
function intersection(arr1, arr2) {
  // Using Set for O(n) performance
  const set = new Set(arr2);
  return arr1.filter(item => set.has(item));
}

// Find difference between arrays
function difference(arr1, arr2) {
  const set = new Set(arr2);
  return arr1.filter(item => !set.has(item));
}

// Example
const array1 = [1, 2, 3, 4, 5];
const array2 = [3, 4, 5, 6, 7];

console.log(intersection(array1, array2));  // [3, 4, 5]
console.log(difference(array1, array2));    // [1, 2]
```

### 4. Processing Records by Chunks

```javascript
// Process records in batches
async function processBatchedRecords(records, batchSize = 100) {
  const totalBatches = Math.ceil(records.length / batchSize);

  for (let i = 0; i < totalBatches; i++) {
    console.log(`Processing batch ${i + 1}/${totalBatches}`);

    const batchStart = i * batchSize;
    const batchEnd = Math.min(batchStart + batchSize, records.length);
    const batch = records.slice(batchStart, batchEnd);

    // Process current batch
    await processBatch(batch);

    // Optional: Add delay to prevent UI freezing
    if (i < totalBatches - 1) {
      await new Promise(resolve => setTimeout(resolve, 0));
    }
  }
}

async function processBatch(records) {
  // Complex processing for each batch
  return Promise.all(records.map(async record => {
    // Process individual record
    return processRecord(record);
  }));
}
```

## Memory Efficiency Tips

### 1. Reusing Arrays

```javascript
// Bad: Creating new arrays unnecessarily
function processItems(items) {
  // This creates multiple intermediate arrays
  return items
    .map(item => item * 2)
    .filter(item => item > 10)
    .map(item => ({ value: item }));
}

// Better: Single loop with less memory overhead
function processItemsEfficient(items) {
  const result = [];
  for (let i = 0; i < items.length; i++) {
    const doubled = items[i] * 2;
    if (doubled > 10) {
      result.push({ value: doubled });
    }
  }
  return result;
}
```

### 2. Object Pooling for Frequent Creation/Disposal

```javascript
// Object pool for particle system
class ParticlePool {
  constructor(size) {
    this.pool = new Array(size).fill().map(() => ({ x: 0, y: 0, active: false }));
    this.nextIndex = 0;
  }

  getParticle() {
    // Find next inactive particle
    const startIndex = this.nextIndex;
    do {
      const particle = this.pool[this.nextIndex];
      this.nextIndex = (this.nextIndex + 1) % this.pool.length;

      if (!particle.active) {
        particle.active = true;
        return particle;
      }
    } while (this.nextIndex !== startIndex);

    return null; // No particles available
  }

  releaseParticle(particle) {
    particle.active = false;
  }
}

// Usage
const particlePool = new ParticlePool(1000);

function createExplosion(x, y) {
  for (let i = 0; i < 50; i++) {
    const particle = particlePool.getParticle();
    if (particle) {
      particle.x = x;
      particle.y = y;
      // Set other properties...
    }
  }
}
```

## Conclusion

When working with data in JavaScript, the choice of loop type, data structure,
and algorithm can significantly impact performance. Here are the key takeaways:

1. **Choose the right loop type**:
   - Use classic `for` loops when raw performance matters
   - Use `for...of` for cleaner, slightly slower iteration
   - Use array methods (`map`, `filter`, `reduce`) for readability and immutability
   - Avoid `for...in` for arrays

2. **Select appropriate data structures**:
   - Arrays for ordered, index-based data
   - Objects for key-value pairs with string keys
   - Maps for key-value pairs with any key type
   - Sets for unique values
   - Typed Arrays for numeric operations

3. **Optimize operations**:
   - Process data in batches for large datasets
   - Use early returns and breaks to avoid unnecessary work
   - Index data for frequent lookups
   - Reuse objects to reduce garbage collection
   - Consider memoization for expensive calculations
