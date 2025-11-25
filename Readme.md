# Ex06 BMI Calculator
## Date: 25/11/2025

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

### PROGRAM
## App.jsx
```
import { useState } from "react";
import "./App.css";

export default function App() {
  const [weight, setWeight] = useState("");
  const [height, setHeight] = useState("");
  const [bmi, setBmi] = useState("");
  const [category, setCategory] = useState("");

  const calcBMI = () => {
    if (!weight || !height) return;
    const h = height / 100;
    const val = (weight / (h * h)).toFixed(1);
    setBmi(val);
    if (val < 18.5) setCategory("Underweight");
    else if (val < 25) setCategory("Normal");
    else if (val < 30) setCategory("Overweight");
    else setCategory("Obesity");
  };

  const reset = () => {
    setWeight("");
    setHeight("");
    setBmi("");
    setCategory("");
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>

      <div className="input-group">
        <label>Weight (kg)</label>
        <input
          type="number"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
      </div>

      <div className="input-group">
        <label>Height (cm)</label>
        <input
          type="number"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
      </div>

      <div className="btn-group">
        <button onClick={calcBMI}>Calculate</button>
        <button onClick={reset} className="reset">Reset</button>
      </div>

      {bmi && (
        <div className="result">
          <p>BMI: {bmi}</p>
          <p>Category: {category}</p>
        </div>
      )}
    </div>
  );
}

```
## App.css
```
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background: linear-gradient(#5f27cd, #1dd1a1);
  background-size: 300% 300%;
  font-family: "Poppins", sans-serif;
}

.box {
  background: rgba(0, 0, 0, 0.6);
  padding: 28px;
  width: 280px;
  border-radius: 18px;
  text-align: center;
  box-shadow: 0 0 18px rgba(255,255,255,0.25);
}

h2 {
  color: #ffffff;
  margin-top: 0;
  font-size: 22px;
  text-shadow: 0 0 6px rgba(255,255,255,0.6);
}

input {
  width: 100%;
  padding: 12px;
  margin: 12px 0;
  border-radius: 10px;
  border: 2px solid #ffffff;
  background: rgba(255,255,255,0.85);
  color: #000000;
  font-size: 15px;
  transition: 0.3s;
  box-sizing: border-box;
}

input:focus {
  outline: none;
  border-color: #00eaff;
  box-shadow: 0 0 10px #00eaff;
}

button {
  width: 100%;
  padding: 12px;
  background: linear-gradient(45deg, #00eaff, #007bff);
  color: white;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  margin-top: 12px;
  box-sizing: border-box;
  font-size: 15px;
  transition: 0.3s;
}

button:hover {
  transform: scale(1.05);
  box-shadow: 0 0 12px rgba(0, 200, 255, 0.7);
}

.reset-btn {
  background: linear-gradient( #ff9f43, #ff3838);
}

.reset-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 0 12px rgba(255, 80, 80, 0.7);
}

p {
  margin-top: 16px;
  font-weight: bold;
  font-size: 18px;
  color: #00eaff;
}


```

## OUTPUT
<img width="1906" height="908" alt="image" src="https://github.com/user-attachments/assets/c064148a-8326-483e-ad43-da8c23a15065" />
<img width="1907" height="908" alt="image" src="https://github.com/user-attachments/assets/d8b48201-a142-4782-83e5-f743ca6dd07d" />

<img width="1888" height="889" alt="image" src="https://github.com/user-attachments/assets/c7bdcc97-8dc6-425a-ad2f-09f29f24acd8" />





## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
