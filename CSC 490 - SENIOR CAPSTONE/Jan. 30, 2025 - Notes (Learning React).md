
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
JSX Version:
```jsx
const user = {
  name: 'Hedy Lamarr',
  imageUrl: 'https://i.imgur.com/yXOvdOSs.jpg',
  imageSize: 90,
};

export default function Profile() {
  return (
    <>
      <h1>{user.name}</h1>
      <img
        className="avatar"
        src={user.imageUrl}
        alt={'Photo of ' + user.name}
        style={{
          width: user.imageSize,
          height: user.imageSize
        }}
      />
    </>
  );
}
```

TSX Version:
```jsx
interface  User {
	name: string;
	imageUrl: string;
	imageSize: number;
}

const  user: User = {
	name:  'Hedy Lamarr',
	imageUrl:  'https://i.imgur.com/yXOvdOSs.jpg',
	imageSize:  90
};

export default function Profile() {
  return (
    <>
      <h1>{user.name}</h1>
      <img
        className="avatar"
        src={user.imageUrl}
        alt={'Photo of ' + user.name}
        style={{
          width: user.imageSize,
          height: user.imageSize
        }}
      />
    </>
  );
}
```

style = {{}} is not a special syntax, but a regular {} oblect inside of style={} JSX curly braces/ You can use it when the styles depend on JS variables.

### Conditional Rendering
You can use conditional statements like you do in JS/TS code. 

Works for both TS and JS.

```jsx
let content;

if (isLoggedIn) {
	content = <AdminPanel />
} else {
	content = <LoginForm />
}

return (
	<div>
		{content}
	</div>
	//OR
	/*<div>
		{isLoggedIn ? (
			<AdminPanel />
		) : (
			<LoginForm />
		)}
	</div>	*/
	//FOR A MORE COMPACT SOLUTION
)
```
If the else branch is not needed you can write it as:
```jsx
	<div>
		{isLoggedIn && <AdminPanel />}
	</div>
```

### Rendering List
You can use the ``for`` loop and array ``map()`` to render list components.

```jsx
const products = [
  { title: 'Cabbage', isFruit: false, id: 1 },
  { title: 'Garlic', isFruit: false, id: 2 },
  { title: 'Apple', isFruit: true, id: 3 },
];

export default function ShoppingList() {
  const listItems = products.map(product =>
    <li
      key={product.id}
      style={{
        color: product.isFruit ? 'magenta' : 'darkgreen'
      }}
    >
      {product.title}
    </li>
  );

  return (
    <ul>{listItems}</ul>
  );
}

```

For each item in a list you should pass a number or string that uniquely identifies each item from their sibling. The key usually comes from database ID. It helps React know which item has been inserted, deleted, or reordered.

### Responding to Events
You can respond to events by declaring _event handler_ functions inside your components. 
```jsx
function MyButton() {
	function handleClick() {
		alert('You clicked me!');
	}

	return (
		<button onClick={handleClick}>
			Click me
		</button>
	);
}
```
You don't need the parentheses at the end of onClick because you would be calling the event handler function and all you have to do 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5OTkwMTM1NDAsLTk1MDUyNDkzOCwxMT
cwMDEzODg1LDg3OTQwMDExMCwxMTQ4OTEwNDA1LDI1MjA3MTEw
NywtNjk5NjMwOTY3LDkzNDE2NTM0MiwyMTM0NzUxMjk3LDE3Mj
I4NzI5NCwtMTYzMDQ2NzE4Niw0OTc4MTg4MTBdfQ==
-->