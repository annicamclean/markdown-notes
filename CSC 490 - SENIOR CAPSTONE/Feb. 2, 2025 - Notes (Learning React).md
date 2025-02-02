
# Learning React
## Steps for Thinking in UI
1. ***Break the UI into a component hierarchy***
	- Use the [single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle) when trying to figure out if you want a function or an object
	- A well structured JSON object is a great way to know how to structure your UI and components
2. ***Step 2: Build a static version in React***
	- First build a version that renders the UI from your data model without adding any interactivity.
	- To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props.
	- You can either build "top-down"(building from biggest components to smallest) or "bottom-up"(vice versa of top-down). *Bottom-up is easiest.*

    function ProductRow({ product }) {
  const name = product.stocked ? product.name :
    <span style={{ color: 'red' }}>
      {product.name}
    </span>;

  return (
    <tr>
      <td>{name}</td>
      <td>{product.price}</td>
    </tr>
  );
}

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI5NTg0MDU1Nl19
-->