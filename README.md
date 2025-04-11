# Ex06 BMI Calculator
## Date:

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

## PROGRAM

index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import { BrowserRouter} from 'react-router-dom'; import App from './App';

const root = ReactDOM.createRoot(document.getElementByid('root')); root.render(
<BrowserRouter>
<App/>
</BrowserRouter>
);


App.js

import React from 'react';
import { Routes, Route, Link} from 'react-router-dom'; import Home from './Home';
import BMICalculator from './BMICalculator'; import './styles.css';

function App() { return (
<div className="app">
<nav className="navbar">
<Link to="/">Home</Link>
<Link to="/bmi">BMI Calculator</Link>
</nav>


<Routes>
<Route path="/" element={<Home />} />
<Route path="/bmi" element={<BMICalculator />} />
</Routes>
</div>
);
}


export default App;


Home.js
import React from 'react';


function Home() { return (
<div className="page">
<h2>  Welcome to the Health App</h2>

<p>This app helps you calculate your BMI using React Router and shows your health category.</p>
</div>
);
}


export default Home;


BMICalculator.js
import React, { useState } from 'react';


function BMICalculator() {
const [height, setHeight] = useState("); const [weight, setWeight] = useState("); const [bmi, setBmi] = useState(null); const [message, setMessage] = useState("); const [color, setColor] = useState(");

const calculateBMI = () => {
const h = parseFloat(height) / 100; const w = parseFloat(weight);

if (!h II !w II h <= 0 II w <= 0) {
setMessage("Please enter valid values."); setBmi(null);
setColor("); return;
}


const result= w I (h * h);
const rounded= result.toFixed(2); setBmi(rounded);

if (result< 18.5) { setMessage("Underweight"); setColor("blue");
} else if (result< 24.9) { setMessage("Normal weight"); setColor("green");
} else if (result< 29.9) { setMessage("Overweight"); setColor("orange");
} else {
setMessage("Obese"); setColor("red");
}
};


return (
<div className="page">
<h2>  BMI Calculator</h2>
<div className="form">
<input type="number"
placeholder="Height in cm" value={height}
onChange={(e) => setHeight(e.target.value)}
/>
<input type="number"
placeholder="Weight in kg" value={weight}
onChange={(e) => setWeight(e.target.value)}
/>

<button onClick={calculateBMI} >Calculate</button>
</div>


{bmi && (
<div className="result">
<h3 style={{color}}>Your BMI: {bmi}</h3>
<p>Status: <span style={{color}}>{message}</span></p>
</div>
)}


<div className="chart">
<h3>BMI Category Chart</h3>
<table>
<thead>
<tr>
<th>Category</th>
<th>BMI Range</th>
</tr>
</thead>
<tbody>
<tr><td>Underweight</td><td>&lt; 18.5</td></tr>
<tr><td>Normal weight</td><td>18.5 - 24.9</td></tr>
<tr><td>Overweight</td><td>25 -  29.9</td></tr>
<tr><td>Obese</td><td>30 and above</td></tr>
</tbody>
</table>
</div>
</div>
);
}


export default BMICalculator;

styles.css body { margin: 0;
font-family: 'Segoe UI', sans-serif; background-color: #f5f5f5;
}


.app {
text-align: center;
}


.navbar {
background-color: #282c34; padding: lrem;
}
.navbar a { color: white;
text-decoration: none; margin: 0 1rem;
font-weight: bold;
}
.page {
max-width: 600px; margin: auto; background: white; padding: 2rem; margin-top: 2rem; border-radius: lOpx;
box-shadow: 0 0 lOpx rgba(0, 0, 0, 0.1);
}

.form input { margin: 0.5rem; padding: 0.5rem; width: 45%; border-radius: 5px;
border: 1px solid #ccc;
}
.form button { margin-top: lrem;
padding: 0.5rem lrem; background-color: teal; color: white;
border: none; border-radius: 5px; cursor: pointer;
}
.result {
margin-top: lrem;
}
.chart {
margin-top: 2rem;
}


.chart table { width: 100%;
border-collapse: collapse;
}


.chart th, .chart td { border: 1px solid #ccc; padding: 0.5rem;
}

## OUTPUT


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
