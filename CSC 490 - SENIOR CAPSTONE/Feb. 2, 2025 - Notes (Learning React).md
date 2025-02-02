
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
	- *How to Identify States:*
		- Does it **remain unchanged** over time? If so, it isn’t state.
		-  Is it **passed in from a parent** via props? If so, it isn’t state.
		-  **Can you compute it** based on existing state or props in your component? If so, it _definitely_ isn’t state!
4. ***Identify where your state should live***
	- You need to identify which components change the state/own the state.
	- *How to figure out where a state should live:*
		1. Identify _every_ component that renders something based on that state.
		2. Find their closest common parent component—a component above them all in the hierarchy.
		3. Decide where the state should live:
			1. Often, you can put the state directly into their common parent.
			2. You can also put the state into some component above their common parent.
			3. If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common parent component.
5. ***Step 5: Add inverse data flow***
	- To support user input you need to support data flowing the other way
	- 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4OTM3Mzk5OCwtMjY0Njc4MTAzLC0xND
UwNjMwNjY3XX0=
-->