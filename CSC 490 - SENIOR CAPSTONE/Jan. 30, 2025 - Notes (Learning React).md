
# Learning React

### Steps to Set Up New Projects
1.`` npm create vite@latest ``
2. For project name put a period, for package name give a meaningful name, for Framework obviously React and for variant choose either JavaScript + SWC or Typescript + SWC 
3. ``npm install`` or ``npm i``
4. ``npm run dev``
5. Click on the link http://localhost:5173/
6. Ctrl + C to stop the process

## Actually Learning React
This section has code to help remember important parts about learning react.

### Components
React apps are made up of components. React components are JavaScript/Typescript functions that return markup.

```jsx
function MyButton() {
	return (
		<button>I'm a button</button>
	);
}

export default function MyApp() {
	return (
	<div>
		<h1>Welcome to my app</h1>
		<MyButton />
	</div>
	);
}
```

You can tell ``MyButton`` is a React component because it starts with a capital letter. React component names must start with an capital letter, while HTML tags must be lowercase.

### Writing markup with JSX/TSX
JSX/TSX is stricter than HTML. You have to close tags like ``<br />``. Your component also cannot return multiple JSX/TSX tags. They either need to be in a ``<div>...</div>`` or an empty ``<>...</>`` wrapper.

```jsx
function AboutPage() {
	return (
		<>
			<h1>About</h1>
			<p>Hello there. <br /> How do you do?</p>
		</>
	);
}
```

### Adding styles
Instead of using class for HTML tags you use ``className``.  You then link the CSS file. You can either use ``<link>`` tag in your HTML or import ``filepath`` of the CSS file. 
```jsx
<img className="avatar" />
```


### Displaying Data
Using curly brackets lets you add JS/TS into your HTML elements. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjUyMDcxMTA3LC02OTk2MzA5NjcsOTM0MT
Y1MzQyLDIxMzQ3NTEyOTcsMTcyMjg3Mjk0LC0xNjMwNDY3MTg2
LDQ5NzgxODgxMF19
-->