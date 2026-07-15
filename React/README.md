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
```js
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
```js
function App() {
	return (
		<h1>Hello React</h1>
		);
}

export default App;
```

## JSX
```js
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
```js
function App () {
	const name = "John";

	return (
		<h1>Hello ${name}</h1>
	);
}
export default App;
```

## JavaScript Expressions
```js
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
```js
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
```js
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
```js
function App() {
	return <h1>React Component</h1>;
}
export default App;
```

# Level 2
## Create Component
```js
function Header() {
	return <h1>Header</h1>;
}
export default Header;
```

## Import Component
```js
import Header from "./Header";

function App() {
	return <Header />;
}
export default App;
```

## Multiple Components
```js
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
```js
function User(Props) {
	return <h1>{props.name}</h1>;
}

function App() {
	return <User name="Anil" />;
}
export default App;
```

## Destructuring Props
```js
function User({ name }) {
	return <h1>{name}</h1>;
}

function App() {
	return <User name="Anil" />;
}

export default App;
```

## Multiple Props
```js
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
```js
function User({ name="Guest" }){
	return <h1>{name}</h1>;
}

function App() {
	return <User />;
}
export default App;
```

## Children Props
```js
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












