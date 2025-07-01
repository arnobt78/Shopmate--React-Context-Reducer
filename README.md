# Shopmate - React Context & Reducer E-Commerce Demo

<img width="1200" alt="Screenshot 2024-08-29 at 18 48 19" src="https://github.com/user-attachments/assets/c0f1abe9-ade8-4998-aa5a-08db61a9e2ca"> <img width="1200" alt="Screenshot 2024-08-29 at 18 48 40" src="https://github.com/user-attachments/assets/7ae1bb28-10c3-4e5e-88cd-e8cd24f334a6">

---

## Project Summary

**Shopmate** is a learning-focused, demo E-Commerce web application built with React. It demonstrates how to manage global state using **React Context** and **useReducer**—entirely without using Redux or Redux-Toolkit. The project is ideal for anyone wanting to understand practical state management in React applications, especially for scalable, real-world scenarios like shopping carts or product listings.

- **Live-Demo:** [https://shopmate-cr-arnob.netlify.app](https://shopmate-cr-arnob.netlify.app)

---

## Table of Contents

1. [Project Features](#project-features)
2. [Technology Stack](#technology-stack)
3. [Project Structure](#project-structure)
4. [Installation & Setup](#installation--setup)
5. [Key Concepts & Keywords](#key-concepts--keywords)
6. [Walkthrough: How It Works](#walkthrough-how-it-works)
7. [Available Scripts](#available-scripts)
8. [Learning Resources](#learning-resources)
9. [Examples & Code Snippets](#examples--code-scripts)
10. [Conclusion](#conclusion)

---

## Project Features

- Global state management using React Context API and useReducer
- Add-to-cart, remove-from-cart, and cart-totals functionality
- Modern React Hooks usage (useContext, useReducer)
- Modular and scalable file/component structure
- Responsive UI with HTML & CSS
- Routing via React Router DOM
- No Redux or Redux Toolkit dependencies

---

## Technology Stack

- **React** (Core, Hooks)
- **React Context API**
- **useReducer**
- **React Router DOM**
- **HTML5, CSS3, JavaScript (ES6+)**
- **Node.js** (for local development)
- **Create React App** (CRA)

---

## Project Structure

```
Shopmate--React-Context-Reducer/
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   ├── Cart.js
│   │   ├── CartCard.js
│   │   └── ProductCard.js
│   ├── context/
│   │   ├── CartContext.js
│   │   └── cartReducer.js
│   ├── App.js
│   ├── index.js
│   └── ...other files
├── package.json
└── README.md
```

- **components/**: UI components (Cart, CartCard, ProductCard)
- **context/**: State management (CartContext, cartReducer)
- **App.js**: Main entry point, wraps app in CartProvider
- **index.js**: App bootstrapper

---

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/arnobt78/Shopmate--React-Context-Reducer.git
cd Shopmate--React-Context-Reducer
```

---

### 2. Install Dependencies

Ensure you have **Node.js** installed ([Download Node.js](https://nodejs.org/en/)).

```bash
npm install
```

---

### 3. Install React Router DOM

```bash
npm install react-router-dom
```
[React Router Docs](https://reactrouter.com/en/main)

---

### 4. Run the Application

```bash
npm start
```
Visit [http://localhost:3000](http://localhost:3000) in your browser.

---

## Key Concepts & Keywords

- **context**: React API for passing data through the component tree without props.
- **reducer**: Pure function taking state & action, returning new state.
- **action**: Object literal describing state changes.
- **useContext**: React hook for accessing context.
- **useReducer**: React hook for complex state logic, alternative to useState.
- **dispatch**: Function for sending actions to reducer.

---

## Walkthrough: How It Works

### State Management Flow

1. **CartContext.js** defines the initial state and provides context to all components.
2. **cartReducer.js** manages state transitions based on dispatched actions (add, remove, etc.).
3. **CartProvider** (in CartContext.js) wraps the app, exposing state and actions via context.
4. **useCart** custom hook simplifies context consumption in components.
5. **Components** (Cart, CartCard, ProductCard) use `useCart()` to access and mutate cart state globally.

---

### File-by-File Instruction

#### `context/CartContext.js`
- Creates and exports CartContext.
- Provides CartProvider, wrapping children.
- Uses useReducer to manage cart state.
- Exposes cart actions via context value.

#### `context/cartReducer.js`
- Exports `cartReducer` function.
- Handles cart state transitions via switch-cases (add, remove, etc.).

#### `components/Cart.js`
- Displays items in cart, total price, and allows removing items.

#### `components/CartCard.js`
- Represents individual product card.
- Restricts "Add To Cart" to once per product.

#### `App.js`
- Wraps the app in the CartProvider.

---

## Available Scripts

| Script         | Description                                                                          |
| -------------- | ------------------------------------------------------------------------------------ |
| `npm start`    | Runs the app in development mode on [http://localhost:3000](http://localhost:3000)   |
| `npm test`     | Launches the test runner                                                             |
| `npm run build`| Builds the app for production to the `build` folder                                  |
| `npm run eject`| Copies configuration files and dependencies for advanced customization               |

---

## Learning Resources

- [React Context Docs](https://reactjs.org/docs/context.html)
- [useReducer Docs](https://react.dev/reference/react/useReducer)
- [React Router Docs](https://reactrouter.com/en/main)
- [Create React App Docs](https://facebook.github.io/create-react-app/docs/getting-started)

---

## Examples & Code Scripts

### Example: Cart Reducer

```js
// src/context/cartReducer.js
export const cartReducer = (state, action) => {
  switch (action.type) {
    case "ADD_TO_CART":
      // add item logic
      break;
    case "REMOVE_FROM_CART":
      // remove item logic
      break;
    default:
      return state;
  }
};
```

---

### Example: Using Cart Context

```js
// src/components/ProductCard.js
import { useCart } from "../context/CartContext";

function ProductCard({ product }) {
  const { addToCart } = useCart();
  return (
    <button onClick={() => addToCart(product)}>
      Add to Cart
    </button>
  );
}
```

---

### Example: CartProvider Usage

```js
// src/App.js
import { CartProvider } from "./context/CartContext";
import Cart from "./components/Cart";
import Products from "./components/Products";

function App() {
  return (
    <CartProvider>
      <Products />
      <Cart />
    </CartProvider>
  );
}
```

---

## Conclusion

**Shopmate** is a practical, modern, and learning-friendly E-Commerce app that shows how to build scalable global state management in React using only the Context API and useReducer. It's a perfect project for learners, educators, and developers seeking to master React state management without Redux.

---

## Happy Coding! 🎉

Thank you for exploring and learning with Shopmate!

---
