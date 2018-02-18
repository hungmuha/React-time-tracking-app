### Running the app

1. Ensure you have `npm` installed.

Follow the instructions for your platform [here](https://github.com/npm/npm).

2. Install all dependencies:

````
npm install
````

3. Boot the HTTP server

````
npm run server
````

The server is now running at [localhost:3000](localhost:3000)

law to determine stateful component
1. Is it passed in from a parent via props? If so, it probably isn’t state.
	A lot of the data used in our child components are already listed in their parents. This criterion helps us de-duplicate.
	For example, “timer properties” is listed multiple times. When we see the properties declared in EditableTimerList, we can consider it state. But when we see it elsewhere, it’s not.
2. Does it change over time? If not, it probably isn’t state.
	This is a key criterion of stateful data: it changes.
3. Can you compute it based on any other state or props in your component? If so, it’s not state.
	For simplicity, we want to strive to represent state with as few data points as possible.

React onClick and onChange can be used to invoke another function inside the component so that input don't conflict with the state

