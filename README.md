# React Presentation Handout

## Prerequisites
- Make sure you have Node.js installed on your system.

## Installation of Tic Tac Toe
1. Clone repo down to your local
  https://github.com/Akshat2923/react_demo

2. Run the following command to install the project dependencies:
   ```
   npm install
   ```

3. Start the development server:
   ```
   npm start
   ```
## Start a React App from scratch
1. Create a new React project: 
   ```
   npx create-react-app my-app
   ```

2. Start the development server:
   ```
   cd my-app
   npm start
## Table of Contents
1. [Introduction to React](#introduction-to-react)
2. [User Interface and Component-Based Design](#user-interface-and-component-based-design)
3. [JSX (JavaScript XML)](#jsx-javascript-xml)
4. [Interactive Components](#interactive-components)
5. [React Frameworks and Libraries](#react-frameworks-and-libraries)

## 1. Introduction to React
### Basic Information
- Initial release date: May 29, 2013
- Original author: Jordan Walke
- Maintained by: Meta & community

### React Features
- Free and open-source
- Front-end JavaScript library
- Popularity due to ease of use, easy to break down, and easy to build and maintain applications

### Use Cases
- Single-page applications
- Mobile applications
- Server-rendered applications

### Starting a New React Project
- Pick a React-powered framework (e.g., Next.js, Remix, Gatsby, Expo)
- Add React to an existing project (for a subroute, part of a page, or a native mobile app)

## 2. User Interface and Component-Based Design
### Components in React
- Foundational elements in React.js
- Serve as the building blocks for user interfaces
- Combination of markup, CSS, and JavaScript into reusable UI elements

### Defining and Using Components
```javascript
export default function Square() {
  return <button className="square">X</button>;
}
```

### Nesting Components
```javascript
export default function Square() {
  return (
    <>
      <button className="square">X</button>
      <button className="square">X</button>
    </>
  );
}
```

### Passing Props
- React components use props to communicate with each other
- Parent components can pass information to child components through props

### Importing and Exporting Components
- Components can be split into separate files for better organization and reusability
- Export components using either default or named exports
- Import components using the corresponding import technique

## 3. JSX (JavaScript XML)
### JSX Basics
- JSX is a syntax extension for JavaScript that allows you to write HTML-like markup within your JavaScript code
- JSX makes it easier to represent the UI structure and incorporate dynamic content

### JSX Markup and Curly Braces
```javascript
function Square({ value }) {
  return <button className="square">{value}</button>;
}

return (
  <>
    <div className="status">{status}</div>
    <div className="board-row">
      <Square value={squares[0]} onSquareClick={() => handleClick(0)} />
      <Square value={squares[1]} onSquareClick={() => handleClick(1)} />
      <Square value={squares[2]} onSquareClick={() => handleClick(2)} />
    </div>
  </>
);
```

## 4. Interactive Components
### Event Handlers
- React components can respond to events through event handlers
- Event handlers are defined within the component and passed as props to the JSX elements

```javascript
<button className="square" onClick={onSquareClick}>

<Square value={squares[0]} onSquareClick={() => handleClick(0)} />
```

### Event Propagation
- Event handlers will respond to any events that occur on their child components
- `stopPropagation()` can be used to prevent the event from bubbling up to the parent components

### State
- State is a built-in React object that contains data and information about the component
- State can change over time, causing the component to re-render
- State can be modified through user actions or network changes
```javascript
const [squares, setSquares] = useState(Array(9).fill(null));
const [xIsNext, setXIsNext] = useState(true);

function handlePlay(nextSquares) {
  setSquares(nextSquares);
  setXIsNext(!xIsNext);
}
```

## 5. React Frameworks and Libraries
### React Query
- A powerful library developed by TanStack that simplifies data fetching and state management
- Features include declarative data fetching, automatic caching, background data sync, infinite scrolling, and more

### React Native
- Developed by Facebook, it's a React library for building cross-platform mobile applications
- Allows developers to create mobile apps that run natively on both iOS and Android platforms
- Utilizes APIs and native UI components rather than HTML/CSS/JavaScript
