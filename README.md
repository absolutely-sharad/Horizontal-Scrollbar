# Horizontal ScrollBar

This repository contains a simple React project for demonstrating a horizontal scrollbar.

## Project Structure

The project consists of two main files:

1. **Horizontal_ScrollBar.js**: This file contains the functional component `ScrollBar` responsible for rendering a horizontal scrollbar and a list of items. It utilizes React Hooks (`useRef`) to create a reference to the container element and provides functions to scroll left and right.

2. **App.js**: This file imports and renders the `ScrollBar` component within the main application.

## Components

### Horizontal_ScrollBar.js

#### Functions
- **scrollLeft**: This function is called when the "Scroll Left" button is clicked. It scrolls the container element to the left by 500 pixels.
- **scrollRight**: This function is called when the "Scroll Right" button is clicked. It scrolls the container element to the right by 500 pixels.

#### Usage

```jsx
<App/>
import ScrollBar from './Horizontal_ScrollBar';
import './App.css';

function App() {
  return (
    <div className="App">
      <ScrollBar/>
    </div>
  );
}

export default App;
```
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


```jsx
<ScrollBar/>
import React, { useRef } from 'react';
import styles from './Horizontal_ScrollBar.module.css';

export default function ScrollBar() {
    const containerRef = useRef(null);

    const scrollLeft = () => {
        if (containerRef.current) {
            containerRef.current.scrollLeft -= 500;
        }
    };

    const scrollRight = () => {
        if (containerRef.current) {
            containerRef.current.scrollLeft += 500;
        }
    };

    let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30];

    return (
        <div>
            <div className={styles.scrollWrapper} ref={containerRef}>
                <ul className={styles.array}>
                    {arr.map((value,index) => (
                        <li key={index} className={styles.list}>
                            {value}
                        </li>
                    ))}
                </ul>
            </div>
        <button onClick={scrollLeft} className={styles.btn}> Scroll Left </button>
        <button onClick={scrollRight} className={styles.btn}>Scroll Right</button>
        </div>
    );
}
```

#### Getting Started
- To run the project locally:

#### Clone this repository to your local machine.
- Install dependencies using npm install.
- Start the development server using npm start.
- Access the application in your browser at http://localhost:3000.

#### Technologies Used
- React
- CSS Modules

### Author
[Sharad Singh Kushwaha]
