# React Cheat Sheet

# Level 1
## Create a React Project
```bash
npm create vite@latest react-app
cd react-app
npm install
npm run dev
```

## Project Structure
```
react-app/
|- public
|-src/
|  |- assets/
|  |- App.jsx
|  |- main.jsx
|  |- index.css
|
|- package.json
|- vite.config.js
```

## main.jsx
```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App frm "./App";
import "./index.css";

ReactDOM.createRoot(document.getElimentById("root")).render(
	<React.StrictMode>
	<App />
	</React.StrictMode>
);
```

## App Component
```jsx
function App() {
	return (
		<h1>Hello React</h1>
		);
}

export default App;
```

## JSX
```jsx
function App() {
	return (
		<div>
			<h1>Title</h1>
			<p>Description</p>
		</div>
	);
}
export default App;
```

## Variables
```jsx
function App () {
	const name = "John";

	return (
		<h1>Hello ${name}</h1>
	);
}
export default App;
```

## JavaScript Expressions
```jsx
function App () {
	const a = 10;
	const b = 20;

	return (
		<h1>{a+b}</h1>
	);
}
export default App;
```

## Comments in JSX
```jsx
function App() {
	return(
		<>
			{/* JSX Comment */}
			<>Hello</>
			}
		</>
	);
}
export default App;
```

## Multiple Elements
```jsx
function App() {
	return (
		<>
			<h1>Heading</h1>
			<p>Paragraph</p>			
		</>
	);
}
export default App;
```

## Export Component
```jsx
function App() {
	return <h1>React Component</h1>;
}
export default App;
```

# Level 2
## Create Component
```jsx
function Header() {
	return <h1>Header</h1>;
}
export default Header;
```

## Import Component
```jsx
import Header from "./Header";

function App() {
	return <Header />;
}
export default App;
```

## Multiple Components
```jsx
function Header() {
	return <h1>Header</h1>;
}

function Footer() {
	return <h1>Footer</h1>
}

function App() {
	return(
		<>
			<Header />
			<Footer />
		</>
	);
}
```

## Props
```jsx
function User(Props) {
	return <h1>{props.name}</h1>;
}

function App() {
	return <User name="Anil" />;
}
export default App;
```

## Destructuring Props
```jsx
function User({ name }) {
	return <h1>{name}</h1>;
}

function App() {
	return <User name="Anil" />;
}

export default App;
```

## Multiple Props
```jsx
function User({ name, age }) {
	return (
		<h1>
			{name} - {age}
		</h1>
	);
}

function App() {
	return <User name="Anil" age="25" />;
}
export default App;
```

## Default Props
```jsx
function User({ name="Guest" }){
	return <h1>{name}</h1>;
}

function App() {
	return <User />;
}
export default App;
```

## Children Props
```jsx
function Card({ children }) {
	return <div>{children}</div>
}

function App() {
	return (
		<Card>
			<h1>Hello</h1>
		</Card>
	)
}
export default App;
```

# Level 3
## useState
```jsx
import { useState } from "react";

function App() {
	const [count, setCount] = useState(0);

	return <h1>{count}</h1>
}
export default App;
```

## Update State
```jsx
import { useState } from "react";

function App() {
	const [count, setCount] = useState(0);

	return (
		<button onClick={() => setCount(count+1)}>
			{count}
		</button>
	);
}
export default App;
```

## Input State
```jsx
import { useState } from "react";

function App() {
	const[name, setName] = useState("");

	return (
		<>
			<input
				value={name}
				onChange={(e) => setName(e.target.value)}
			/>
			<h2>{name}</h2>
		</>
	);
}
export defalt App;
```

## Boolean State
```jsx
import { useState } from "react";

function App() {
	const [show, setShow] = useState(true);

	return (
		<button onClick = {() => setShow(!show)}>
			Toggle
		</button>
	);
}
```

## Conditional Rendering
```jsx
import { useState } from

function App() {
	const [show, setShow] = useState(true);

	return (
		<>
			<button onClick ={() => setShow(!show)}>
				Toggle
			</button>
			{show && <h1>Hello React</h1>}
		</>
	);
}
export default App;
```

## State Object
```jsx
import { useState } from "react";

function App() {
	const [user, setUser] = useState({
		name: "John";
		age: 25;
	});

	return <h1>{user.name}</h1>
}
export default App;
```

## Update Object State
```jsx
import { useState } from "react";

function App() {
	const [user, setUser] = useState({
		name: "john",
		age: 25,
	});

	return (
		<button
			onClick = {() => 
				setUser({
					...user,
					age:26,
				})
			}
		>
			{user.age}
		</button>
	);
}
export default App;
```

## State Array
```jsx
import { useState } from "react";

function App() {
	const [colors] = useState([
		"Red",
		"Blue",
		"Green",
	]);

	return <h1>{colors[0]}</h1>;
} 
export default App;
```

# Level 4
## Rendering List

```jsx
function App() {
	const fruits = ["Apple", "Banana", "Orange"];

	return (
		<>
			{fruits.map((fruit) => (
				<h2>{fruit}</h2>
			))}
		</>
	);
}
export default App;
```

## Key Prop
```jsx
function App() {
	const fruits = ["Apple", "Banana", "Orange"];

	return (
		<>
			{fruits.map((fruit, index) => (
				<h2 key={index}>{fruit}</h2>
			))}
		</>
	);
}
export default App;
```

## Render Objects

```jsx
function App() {
	const users = [
		{ id: 1, name: "John"},
		{ id: 2, name: "Shane"},
	];

	return (
		<>
			{users.map((user) => (
				<h2 key={user.id}>{user.name}</h2>
			))}
		</>
	);
}
export default App;
```

## Event Handler
```jsx
function App() {
	function handleClick() {
		alert("Button CLicked");
	}

	return(
		<button onClick={handleClick}>
			Click
		</button>
	);
}
export default App;
```

## Arrow Function Event
```jsx
function App() {
	return (
		<button onClick={() => alert("Hello")}>
			Click
		</button>
	)
}
export default App;
```

## Pass Arguments
```jsx
function App() {
	function greet(name) {
		alert(name);
	}
	return (
		<button
			onClick={() => greet("John")}
		>
			Click
		</button>
	)
}
export default App;
```

## Conditional Rendering
```jsx
function App() {
	const loggedIn = true;

	return (
		<>
			{loggedIn ? (
				<h1>Welcome</h1>
				) : (
				<h1>Please Login</h1>
				)
			}
		</>
	);
}
export default App;
```

## Dynamic Class
```jsx
function App() {
	const active = true;

	return (
		<h1 className={active ? "active" : ""}>
			React
		</h1>
	)
}
export default App;
```

## Dynamic Style
```jsx
function App() {
	const active = true;

	return (
		<h1
			style={{
				color: active ? : "green", "red",
			}}
		>
			React
		</h1>
	);
}
export defaul App;
```

# Level 5
## useEffect
```jsx
import { useEffect } from "react";

function App() {
	useEffect(() => {
		console.log("Component Mounted");
	}, []);

	return <h1>React</h1>
}
export default App;
```

# useEffect with State
```jsx
import { useState, useEffect } from "react";

function App() {
	const [count, setCount] = useState(0);

	useEffect(() => {
		console.log(count);
	}, [count]);

	return (
		<button onClick = {() => setCount(count+1)}>
			{count}
		</button>
	);
}
export default App;
```


















































































