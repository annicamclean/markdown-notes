
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

```tsx
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


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY4MTQ1MTMxMywyMTM0NzUxMjk3LDE3Mj
I4NzI5NCwtMTYzMDQ2NzE4Niw0OTc4MTg4MTBdfQ==
-->