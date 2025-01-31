
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

JSX:
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

TSX:
```jsx
interface Product {
	title: string;
	isFruit: boolean;
	id: number;
}

const products: Product[] = [
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
You don't need the parentheses at the end of onClick because you would be calling the event handler function and all you have to do is pass it down. React will acutally do the calling when the user clicks the button.

### Updating the Screen
Sometimes you want to remember some information and display it, that's where states come in.

First import ``useState`` from React then declare a ``state variable`` inside your component.

```jsx
import { useState } from 'react';


function MyButton() {
	const [count, setCount] = useState(0);

	function handleClick() {
		setCount(count + 1);
	}

	return (
		<button onClick={handleClick}>
			Clicked {count} times
		</button>
	);
}

```jsx
import { useState } from 'react';


function MyButton() {
	const [count, setCount] = useState<number>(0);

	function handleClick() {
		setCount(count + 1);
	}

	return (
		<button onClick={handleClick}>
			Clicked {count} times
		</button>
	);
}


```
With the useState you get the current state, and the function to update the current state. The convention is to write [something, setSomething]. 

### Using Hooks
Anything starting with ``use`` are called *Hooks*. You can write your own hooks by combining existing ones. You can only call hooks at the top of your components (or other Hooks). If you want to use useState in a condition or loop, extract a new component and put it there. 

If you wanted 2 buttons to have the same count they have to be at the top of the component. Here is an example:
```jsx

export default function MyApp() {

	const [count, setCount] = useState(0);  

	function  handleClick() {
		setCount(count + 1);
	}

	return (
		<div>
			<h1>Counters that update together</h1>
			<MyButton  count={count}  onClick={handleClick}  />
			<MyButton  count={count}  onClick={handleClick}  />
		</div>
	);
}
```

***READ OVER PROPS AGAIN***
Example of Hooks and Props:
```jsx
import { useState } from 'react';

export default function MyApp() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return (
    <div>
      <h1>Counters that update together</h1>
      <MyButton count={count} onClick={handleClick} />
      <MyButton count={count} onClick={handleClick} />
    </div>
  );
}

function MyButton({ count, onClick }) {
  return (
    <button onClick={onClick}>
      Clicked {count} times
    </button>
  );
}

```

## THE CODE I CREATED WITH IT (USING TSX)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzM3Njc3OTA0LC0xOTA3NjA1MDAwLDEzOT
M5MTg3OTIsLTM1NjAwNjQ1NSw0NzE1OTU4ODUsLTk1MDUyNDkz
OCwxMTcwMDEzODg1LDg3OTQwMDExMCwxMTQ4OTEwNDA1LDI1Mj
A3MTEwNywtNjk5NjMwOTY3LDkzNDE2NTM0MiwyMTM0NzUxMjk3
LDE3MjI4NzI5NCwtMTYzMDQ2NzE4Niw0OTc4MTg4MTBdfQ==
-->