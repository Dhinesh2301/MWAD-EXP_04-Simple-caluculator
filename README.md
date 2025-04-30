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
Calculator.js
```
import React, { useState } from 'react';
import './Calculator.css';

const Calculator = () => {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleCalculate = () => {
    try {
      setInput(eval(input).toString());
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator">
      <input type="text" value={input} readOnly />
      <div className="buttons">
        <button onClick={handleClear}>C</button>
        {[..."789/456*123-0.=+"].map((char) => (
          <button key={char} onClick={() => (char === '=' ? handleCalculate() : handleClick(char))}>
            {char}
          </button>
        ))}
      </div>
    </div>
  );
};

export default Calculator;
```
Calculator.css
```
.calculator {
  width: 300px;
  margin: 100px auto;
  padding: 20px;
  background: #f0f0f0;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.calculator input {
  width: 100%;
  height: 40px;
  margin-bottom: 10px;
  font-size: 1.2rem;
  text-align: right;
  padding: 5px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 15px;
  font-size: 1rem;
  border: none;
  border-radius: 5px;
  background-color: #4caf50;
  color: white;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background-color: #45a049;
}
```
App.js
```
import React from 'react';
import Calculator from './Calculator';

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
![image](https://github.com/user-attachments/assets/202be8db-e831-4d0d-b820-f327e367d545)
![image](https://github.com/user-attachments/assets/88aee12f-e32e-4817-b03f-4c8b70f98311)


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
