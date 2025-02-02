
# Learning React
## Steps for Thinking in UI
1. ***Break the UI into a component hierarchy***
	- Use the [single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle) when trying to figure out if you want a function or an object
	- A well structured JSON object is a great way to know how to structure your UI and components
2. ***Step 2: Build a static version in React***
	- First build a version that renders the UI from your data model without adding any interactivity.
	- To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props.
	- You can either build "top-down"(building from biggest components to smallest) or "bottom-up"(vice versa of top-down). *Bottom-up is easiest.*
3. ***Find the minimal but complete representation of UI state***
	- Making interactive UI requires the user to be able to change the underlying data model.
	- Think of state as the minimal set of changing data that your app needs to remember.
	- The most important principle for structuring state is to keep it [DRY (Don't Repeat Yourself)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
	- Example: If you have a list of items it should be an array state, but if you want the amount of items in that array use the length of the array.
	- *Props* are like arguments you pass to a function. *State* is like a component's memory.
4. ***Identify where your state should live***
	- You need to identify which components change the state/own the state.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMyNzAxODgxMCwtMTQ1MDYzMDY2N119
-->