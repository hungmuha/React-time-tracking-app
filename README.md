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


Method to build a React Application
1. Break the app into components
	We mapped out the component structure of our app by examining the app’s working UI. We then applied the single-responsibility principle to break components down so that each had minimal viable functionality.
2. Build a static version of the app
	Our bottom-level (user-visible) components rendered HTML based on static props, passed
	down from parents.
3. Determine what should be stateful
	We used a series of questions to deduce what data should be stateful. This data was represented
	in our static app as props.
4. Determine in which component each piece of state should live
	We used another series of questions to determine which component should own each piece of state. TimersDashboard owned timer state data and ToggleableTimerForm and EditableTimer both held state pertaining to whether or not to render a TimerForm.
5. Hard-code initial states
	We then initialized state-owners’ state properties with hard-coded values.
6. Add inverse data flow
	We added interactivity by decorating buttons with onClick handlers. These called functions that were passed in as props down the hierarchy from whichever component owned the relevant state being manipulated.


