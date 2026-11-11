# Exp 11 – Basic Calculator using React
## NAME: V.S.SREE VIVEKA
## REG NO: 2305001031
## Aim
To develop a basic calculator application using React that performs arithmetic operations such as addition, subtraction, multiplication, and division.

## Objectives
- To understand React components and JSX.
- To use the `useState()` hook to manage calculator values.
- To handle user input using `onChange` events.
- To perform arithmetic operations using conditional statements.
- To implement Calculate and Clear buttons using event handling.

## Program

### App.jsx

```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [num1, setNum1] = useState("");
  const [num2, setNum2] = useState("");
  const [operator, setOperator] = useState("+");
  const [result, setResult] = useState("");

  const calculate = () => {
    const a = Number(num1);
    const b = Number(num2);
    let answer;

    if (operator === "+") {
      answer = a + b;
    } else if (operator === "-") {
      answer = a - b;
    } else if (operator === "*") {
      answer = a * b;
    } else if (operator === "/") {
      answer = b !== 0 ? a / b : "Cannot divide by zero";
    }

    setResult(answer);
  };

  const clearCalculator = () => {
    setNum1("");
    setNum2("");
    setOperator("+");
    setResult("");
  };

  return (
    <div>
      <h1>Basic Calculator</h1>

      <input
        type="number"
        placeholder="Enter first number"
        value={num1}
        onChange={(e) => setNum1(e.target.value)}
      />

      <br /><br />

      <select
        value={operator}
        onChange={(e) => setOperator(e.target.value)}
      >
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>

      <br /><br />

      <input
        type="number"
        placeholder="Enter second number"
        value={num2}
        onChange={(e) => setNum2(e.target.value)}
      />

      <br /><br />

      <button onClick={calculate}>Calculate</button>
      <button onClick={clearCalculator}>Clear</button>

      <h2>Result: {result}</h2>
    </div>
  );
}

export default App;
```

### App.css

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f2f2f2;
  text-align: center;
}

div {
  margin-top: 50px;
}

h1 {
  color: #333;
}

input, select {
  padding: 10px;
  margin: 5px;
  width: 180px;
}

button {
  padding: 10px 20px;
  margin: 10px;
  background-color: blue;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: darkblue;
}

h2 {
  color: green;
}
```

## Output
<img width="925" height="622" alt="WhatsApp Image 2026-11-05 at 8 41 53 AM" src="https://github.com/user-attachments/assets/a17cde8c-d945-4329-830d-623a97370ebc" />
<img width="932" height="682" alt="WhatsApp Image 2026-11-05 at 8 54 40 AM" src="https://github.com/user-attachments/assets/2e32f00c-8d60-4da9-a3ff-0795b25a11c4" />


## Result
Thus, a basic calculator application was successfully implemented using React with `useState()`, event handling, and conditional statements to perform arithmetic operations.
