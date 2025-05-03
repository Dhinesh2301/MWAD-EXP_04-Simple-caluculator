# MWAD-EXP_04-Simple-caluculator
## Date:30.04.2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
Calculator.jsx
```
import React, { useState } from 'react';

function Calculator() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      try {
        setInput(eval(input).toString());
      } catch {
        setInput('Error');
      }
    } else if (value === 'C') {
      setInput('');
    } else {
      setInput(input + value);
    }
  };

  const buttons = ['7', '8', '9', '/', '4', '5', '6', '*',
                   '1', '2', '3', '-', '0', '.', '=', '+', 'C'];

  return (
    <div className="calculator">
      <h3>Simple Calculator</h3>
      <input value={input} readOnly className="display" />
      <div className="button-grid">
        {buttons.map((btn) => (
          <button key={btn} onClick={() => handleClick(btn)}>{btn}</button>
        ))}
      </div>
    </div>
  );
}

export default Calculator;

```
Calculator.css
```
.calculator {
  max-width: 250px;
  margin: 40px auto;
  padding: 15px;
  text-align: center;
  background-color: #000000;
  border-radius: 8px;
}

.display {
  width: 100%;
  padding: 10px;
  font-size: 18px;
  text-align: right;
  margin-bottom: 10px;
  background-color: #ffffff;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.button-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 6px;
}

button {
  padding: 12px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

/* Colors */
button:nth-child(n) {
  background-color: #87ceeb; /* sky blue for default */
  color: #000;
}

button:nth-child(4n) {
  background-color: #ffb347; /* orange for operators */
}

button:nth-child(17), button:nth-child(18) {
  background-color: #ff6961; /* red for C and = */
  color: white;
}

```
App.jsx
```
import React from 'react';
import Calculator from './Calculator';
import './Calculator.css';

function App() {
  return (
    <div className="App">
      <Calculator />
    </div>
  );
}

export default App;

```



## OUTPUT
![image](https://github.com/user-attachments/assets/437897da-295e-4677-bd72-d2f85adcf0a9)
![image](https://github.com/user-attachments/assets/3fabb192-8793-4f57-9d4a-60ebd508c1dc)


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
