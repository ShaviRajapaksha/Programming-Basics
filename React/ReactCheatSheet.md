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

```











