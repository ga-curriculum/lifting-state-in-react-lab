# ![Lifting State in React Lab - Setup](./assets/hero.png)

## Setup

Open your Terminal application and navigate to your `~/code/ga/labs` directory:

```bash
cd ~/code/ga/labs
```

Create a new Vite project for your React app:

```bash
npm create vite@latest
```

You'll be prompted to choose a project name. Let's name it `lifting-state-in-react-lab`. 

- Select a framework. Use the arrow keys to choose the `React` option and hit `Enter`.

- Select a variant. Again, use the arrow keys to choose `JavaScript` and hit `Enter`.

Navigate to your new project directory and install the necessary dependencies:

```bash
cd lifting-state-in-react-lab
npm i
```

Open the project's folder in your code editor:

```bash
code .
```

### Configuring ESLint

Before we begin, we need to adjust the ESLint configuration. Add the following rules to the `.eslintrc.cjs` file:

```js
rules: {
  'react-refresh/only-export-components': [
    'warn',
    { allowConstantExport: true },
  ],
  'react/prop-types': 'off', // add this line
  'react/no-unescaped-entities': 'off' // add this line
},
```

The first addition prevents warnings if you're not declaring types for your props (which we're not), and the second prevents warnings if you're using contractions within JSX.

### Clear `App.jsx`

Open the `App.jsx` file in the `src` directory and replace the contents of it with the following:

```jsx
// src/App.jsx

const App = () => {

  return (
    <h1>Hello world!</h1>
  );
}

export default App
```

### GitHub setup

To add this project to GitHub, initialize a Git repository:

```bash
git init
```

Make a new repository on [GitHub](https://github.com/) named `lifting-state-in-react-lab`. 

Link your local project to your remote GitHub repo:

```bash
git remote add origin https://github.com/<github-username>/lifting-state-in-react-lab.git
git push origin main
```

> 🚨 Do not copy the above command. It will not work. Your GitHub username will replace `<github-username>` (including the `<` and `>`) in the URL above.





### Starter code

Clear out any existing code and add the following to `src/App.jsx`:

```jsx
// src/App.jsx

import './App.css';

export const availableIngredients = [
  { name: 'Kaiser Bun', color: 'saddlebrown' },
  { name: 'Sesame Bun', color: 'sandybrown' },
  { name: 'Gluten Free Bun', color: 'peru' },
  { name: 'Lettuce Wrap', color: 'olivedrab' },
  { name: 'Beef Patty', color: '#3F250B' },
  { name: 'Soy Patty', color: '#3F250B' },
  { name: 'Black Bean Patty', color: '#3F250B' },
  { name: 'Chicken Patty', color: 'burlywood' },
  { name: 'Lettuce', color: 'lawngreen' },
  { name: 'Tomato', color: 'tomato' },
  { name: 'Bacon', color: 'maroon' },
  { name: 'Onion', color: 'lightyellow' },
  { name: 'Cheddar Cheese', color: '#FDE18B' },
  { name: 'Swiss Cheese', color: '#F1E1A8' },
];

const App = () => {

	return (
		<main>
			<h1>Burger Stacker</h1>
			<section>
				{/* List & Stack components */}
			</section>
		</main>
	);
};

export default App;
```

Replace any existing code with the following in `src/App.css`:

```css
/* src/App.css */
* {
  box-sizing: border-box;
}

:root {
  line-height: 1;
  font-weight: 400;
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;

  color-scheme: light dark;
  color: rgba(255, 255, 255, 0.87);
  background-color: #242424;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

html,
body,
#root {
  margin: 0;
  height: 100%;
  overflow-x: hidden;
}

main {
  width: 100%;
  height: 100%;
  padding: 16px;
  display: flex;
  flex-direction: column;
}

section {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

h1 {
  text-align: center;
}

ul {
  width: 100%;
  height: 100%;

  margin: 0;
  padding: 16px;
  list-style: none;
  
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

li {
  padding: 8px;
  margin-bottom: 4px;
  border-radius: 8px;
  font-weight: bold;
  text-shadow: 0px 0px 2px #000000;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

button {
  cursor: pointer;
  border-radius: 8px;
  background-color: #1a1a1a;
  border: 1px solid transparent;
}
```

Run the following commands in your terminal:

```bash
touch src/components/IngredientList.jsx
touch src/components/BurgerStack.jsx
```

Add the following to `src/components/IngredientList.jsx`:

```jsx
// src/components/IngredientList.jsx
const IngredientList = (props) => {
  return (
    <ul>
      // map through props.ingredients
    </ul>
  );
};

export default IngredientList;
```

Add the following to `src/components/BurgerStack.jsx`:

```jsx
// `src/components/BurgerStack.jsx`
const BurgerStack = (props) => {
  return (
    <ul>
      // map through props.ingredients
    </ul>
  );
};

export default BurgerStack;
```

In `src/App.jsx`, import `src/components/IngredientList.jsx` and `src/components/BurgerStack.jsx` and add them to the provided `<section>`:

```jsx
// `src/App.jsx`
import './App.css';
import BurgerStack from './components/BurgerStack';
import IngredientList from './components/IngredientList';

export const availableIngredients = [
  { name: 'Kaiser Bun', color: 'saddlebrown' },
  { name: 'Sesame Bun', color: 'sandybrown' },
  { name: 'Gluten Free Bun', color: 'peru' },
  { name: 'Lettuce Wrap', color: 'olivedrab' },
  { name: 'Beef Patty', color: '#3F250B' },
  { name: 'Soy Patty', color: '#3F250B' },
  { name: 'Black Bean Patty', color: '#3F250B' },
  { name: 'Chicken Patty', color: 'burlywood' },
  { name: 'Lettuce', color: 'lawngreen' },
  { name: 'Tomato', color: 'tomato' },
  { name: 'Bacon', color: 'maroon' },
  { name: 'Onion', color: 'lightyellow' },
  { name: 'Cheddar Cheese', color: '#FDE18B' },
  { name: 'Swiss Cheese', color: '#F1E1A8' },
];

const App = () => {

	return (
		<main>
			<h1>Burger Stacker</h1>
			<section>
				<IngredientList />
				<BurgerStack />
			</section>
		</main>
	);
};

export default App;
```