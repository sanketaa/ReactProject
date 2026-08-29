# React Burger Builder

A component-based React learning project that lets a user visually assemble a burger, adjust ingredient quantities, calculate the price, and review an order summary.

## Background

This project was built to practice interactive frontend development with React. Instead of displaying a static page, the application maintains ingredient and purchase state, renders the burger dynamically, recalculates pricing after every change, and coordinates reusable UI components.

The repository includes an ejected Create React App toolchain, with local Webpack, Babel, Jest, ESLint, and build scripts committed under `config` and `scripts`.

This is a historical frontend learning project. The order flow stops at a demonstration alert and does not submit an order to a backend or payment service.

## Features

- Add salad, bacon, cheese, and meat
- Remove ingredients without allowing negative quantities
- Render a visual burger from the current ingredient state
- Calculate the total price dynamically
- Disable ordering until at least one ingredient is selected
- Display an order-summary modal
- Cancel or continue from the order summary
- Responsive toolbar and side-drawer navigation
- Reusable backdrop, modal, button, logo, and navigation components
- Basic application render test

## Component Flow

```text
App
 |
 v
Layout
 |
 v
BurgerBuilder
 |-- Burger visualization
 |-- BuildControls
 |-- Modal
     └-- OrderSummary
```

`BurgerBuilder` owns the application state and passes data and event handlers to presentational components through props.

## State and Pricing

The main container tracks:

- Quantity of each ingredient
- Total price, beginning at a base price of `4.00`
- Whether the current burger can be purchased
- Whether the order-summary modal is open

Ingredient pricing in the historical implementation:

| Ingredient | Price |
| --- | ---: |
| Salad | 0.50 |
| Cheese | 0.40 |
| Meat | 1.30 |
| Bacon | 0.70 |

## Technologies

- JavaScript
- React 16
- React DOM
- JSX
- CSS Modules
- Webpack
- Babel
- Jest
- ESLint
- Create React App build tooling
- Git

## Repository Structure

```text
.
├── config
├── scripts
├── public
└── src
    ├── App.js
    ├── containers
    │   └── BurgerBuilder
    ├── components
    │   ├── Burger
    │   ├── Layout
    │   ├── Logo
    │   ├── Navigation
    │   └── UI
    ├── hoc
    └── index.js
```

## Key Components

- `BurgerBuilder`: Stateful container coordinating ingredients, price, purchase availability, and modal state.
- `Burger`: Converts ingredient counts into rendered ingredient components.
- `BurgerIngredient`: Renders the visual representation of each ingredient type.
- `BuildControls`: Displays ingredient controls, price, and order button.
- `OrderSummary`: Displays ingredient quantities and total price.
- `Modal` and `Backdrop`: Provide the order-review overlay.
- `Layout`, `Toolbar`, and `SideDrawer`: Provide the responsive application shell.

## Skills Demonstrated

- Managing component state and immutable state updates
- Passing event handlers and data through props
- Building stateful and presentational components
- Rendering lists dynamically with stable keys
- Deriving UI state from application data
- Enabling and disabling controls based on validation
- Composing reusable modal, navigation, and button components
- Implementing responsive layouts with CSS
- Configuring and understanding a JavaScript build toolchain
- Writing a basic React render test

## Run Locally

The dependencies and build tooling are historical. Review and update them before running the project on a modern system.

Original workflow:

```bash
npm install
npm test
npm start
```

Create a production build:

```bash
npm run build
```

## Limitations and Modernization

- Checkout is represented by an alert; there is no backend order API.
- Orders and burger state are not persisted.
- There is no authentication, payment processing, or server-side validation.
- The automated test coverage is minimal.
- React, Webpack, Babel, Jest, ESLint, and other dependencies are outdated.
- The ejected build configuration increases maintenance responsibility.
- Error boundaries and accessible modal focus management should be added.
- Currency formatting should use an internationalization API.
- Add component, state-transition, accessibility, and end-to-end tests.
- Remove operating-system metadata files from source control and ignore them in future commits.

## Portfolio Context

This project demonstrates foundational React skills: state management, component composition, conditional UI behavior, dynamic rendering, event handling, responsive design, and frontend build tooling. It should be presented as an interactive frontend learning application, not as a production ordering or payment platform.
