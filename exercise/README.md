# ![Lifting State in React Lab - Exercise](./assets/hero.png)

## Introduction

Before diving into the exercise, take a moment to inspect the code provided to you during setup. You'll find code for several components and a complete CSS stylesheet. Your primary focus will be on using React to execute the user stories below, thus reinforcing the concept of **lifting state**.

> 🏆 Pay special attention to the `availableIngredients` array held in `src/App.jsx`. You'll likely begin by rendering this data.

## Our application

![tktk Hunter - screenshot of final product]()

Our application will be a burger stacker. Users will be able to select ingredients from one side of the screen, and in doing so, move them to the other side of the screen. Essentially, our users will be able to select ingredients to add to their burger order. Ingredients added to the burger should 'stack' upon one another, creating a visual that resembles a hamburger.

Take a look at the component hierarchy diagram below for a sense of how this application will be structured:

![tktk Hunter - crd]()

- **App**: The parent component containing `<BurgerStack>` and `<IngredientList>`. It will also contain `stack` state, and two functions for manipulating that state.
- **BurgerStack**: A `<ul>` that renders the elements held in `stack`. Each ingredient rendered in this component should contain a button for **removing** the ingredient from the `stack`.
- **IngredientList**: A `<ul>` that renders the elements held in `availableIngredients`. Each ingredient rendered in this component should contain a button for **adding** the ingredient to the `stack`.

## User stories

Here are the user stories for this lab:

- As a user, I want to be able to see a list of the ingredients that can be added to my burger on the left side of the screen.
- As a user, I want to be able to see a stack of the ingredients that make up my burger on the right side of the screen.
- As a user, I want to be able to add an ingredient from the list to my burger stack by clicking on a '+' button inside the ingredient. When I click on this button, the **ingredient is added to the stack** on the right side of the screen. The ingredient list on the left will not be altered by this action.
- As a user, I want to be able to remove an ingredient from my burger stack by clicking on an 'X' button inside the ingredient. When I click on this button, the ingredient should be **removed from the stack** on the right side of my screen. The ingredient list on the left will not be altered by this action.

## Lab Exercise

Your primary goal is to implement the user stories listed above. To get started, you can follow the steps below:

1. In `src/App.jsx`, import `src/components/IngredientList.jsx` and `src/components/BurgerStack.jsx` and add them to the provided `<section>`.

2. Initialize a new `useState` variable titled `stack` in `src/App.jsx`.

3. Reference the provided user stories to build out the remaining functionality of this application.

### Hints

1. There should be two child components held in `src/App.jsx`. One will be responsible for rendering elements in `availableIngredients`, and the other for elements in `stack`.

2. Your application will require two functions in `src/App.jsx`. One called `addToBurger` and another called `removeFromBurger`. Think carefully about what arguments might need to be passed in to each function.

3. Notice the properties of each object held in `availableIngredients`. This property can be applied for the purposes of *inline styling*, as shown in the example below:

  ```jsx
      <li style={{ backgroundColor: ingredient.color }}>
        {ingredient.name}
      </li>
  ```

> 📚 *Inline styling* in React involves applying CSS styles directly to elements using the `style` attribute. The attribute accepts an object with camelCased properties as its value.

tktk These level ups seem rather light for their own microlesson:

## Level up

1. Create a component called `Ingredient` that can be reused by both `src/components/IngredientList.jsx` and `src/components/BurgerStack.jsx`. It should display the `name` of a single ingredient, and conditionally render the add or remove button based on its parent.

2. Apply conditional rendering within `src/components/BurgerStack.jsx`, so that a message of 'No Ingredients' is displayed if there are no ingredients in the `stack`.