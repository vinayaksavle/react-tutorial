<h1 align="center"><a href="https://codewithvvs.netlify.app/" target="_blank">CLICK HERE TO VISIT</a></h1>

Notes from Tania Rascia
https://www.taniarascia.com/getting-started-with-react/

- Best site to learn HTML CSS basics
https://www.internetingishard.com/

- Essential things need to know
<script src="https://unpkg.com/react@^16/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@16.13.0/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/babel-standalone@6.26.0/babel.js"></script>

React - the React top level API
React DOM - adds DOM-specific methods
Babel - a JavaScript compiler that lets us use ES6+ in old browsers

- To set up create-react-app, run the following code in your terminal, one directory up from where you want the project to live.

	npx create-react-app react-tutorial
	cd react-tutorial && npm start

- If you look into the project structure, you'll see a /public and /src directory, along with the regular node_modules, .gitignore, README.md, and package.json.

*Public
In /public, our important file is index.html, which is very similar to the static index.html file we made earlier - just a root div. This time, no libraries or scripts are being loaded in. The /src directory will contain all our React code.

- JSX: JavaScript + XML
We've been using what looks like HTML in our React code, but it's not quite HTML. This is JSX, which stands for JavaScript XML. With JSX, we can write what looks like HTML, and also we can create and use our own XML-like tags. Here's what JSX looks like assigned to a variable.
E.g. const heading = <h1 className="site-heading">Hello, React</h1>

Using JSX is not mandatory for writing React. Under the hood, it's running createElement, which takes the tag, object containing the properties, and children of the component and renders the same information. The below code will have the same output as the JSX above.
E.g. without JSX
const heading = React.createElement('h1', {className: 'site-heading'}, 'Hello, React!')

JSX is actually closer to JavaScript, not HTML, so there are a few key differences to note when writing it.

*className is used instead of class for adding CSS classes, as class is a reserved keyword in JavaScript.
*Properties and methods in JSX are camelCase - onclick will become onClick.
*Self-closing tags must end in a slash - e.g. <img />

JavaScript expressions can also be embedded inside JSX using curly braces, including variables, functions, and properties.
const name = 'Tania'
const heading = <h1>Hello, {name}</h1>

- Components
Almost everything in React consists of components, which can be class components or simple components.

Most React apps have many small components, and everything loads into the main App component. Components also often get their own file.

*Class Components
We capitalize custom components to differentiate them from regular HTML elements.
We could reuse this component over and over. 

*Simple Components
The other type of component in React is the simple component, which is a function. This component doesn't use the class keyword. 

*Compare a simple component with a class component
Simple Component
const SimpleComponent = () => {
  return <div>Example</div>
}

Class Component
class ClassComponent extends Component {
  render() {
    return <div>Example</div>
  }
}

Note that if the return is contained to one line, it does not need parentheses.

- Props
Right now, we have a cool Table component, but the data is being hard-coded. One of the big deals about React is how it handles data, and it does so with properties, referred to as props, and with state.

ES6 property shorthand to create a variable that contains this.props.characterData.
E.g. const {characterData} = this.props

You should always use keys when making lists in React, as they help identify each list item.
Props are an effective way to pass existing data to a React component, however the component cannot change the props - they're read-only. 

- State
Right now, we're storing our character data in an array in a variable, and passing it through as props. This is good to start, but imagine if we want to be able to delete an item from the array. With props, we have a one way data flow, but with state we can update private data from a component.

You can think of state as any data that should be saved and modified without necessarily being added to a database - for example, adding and removing items from a shopping cart before confirming your purchase.

You must use this.setState() to modify an array. Simply applying a new value to this.state.property will not work.
filter does not mutate but rather creates a new array, and is a preferred method for modifying arrays in JavaScript.


- Submitting Form Data

If you just want to compile all the React code and place it in the root of a directory somewhere, all you need to do is run the following line:

npm run build
This will create a build folder which will contain your app. Put the contents of that folder anywhere, and you're done!

