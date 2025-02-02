
# Learning React
## Steps for Thinking in UI
1. ***Break the UI into a component hierarchy***
	- Use the [single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle) when trying to figure out if you want a function or an object
	- A well structured JSON object is a great way to know how to structure your UI and components
2. ***Step 2: Build a static version in React***
	- First build a version that renders the UI from your data model without adding any interactivity.
	- To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props.
	- You can either build "top-down"(building from biggest components to smallest) or "bottom-up"(vice versa of top-down). *Bottom-up is easiest.*
3. Step 3: Find the minimal but complete representation of UI state
	- Making interactive UI requires the user to be able to change the underlying data model.
	- Think of state as the minimal set of changin
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3ODE1NzU3OTcsLTE0NTA2MzA2NjddfQ
==
-->