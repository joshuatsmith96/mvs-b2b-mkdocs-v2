### `package.json` File: `evolve-storefront`

This document outlines the essential information from the `evolve-storefront` `package.json` file that a developer would use regularly.

---

### Key Scripts

These are the most frequently used commands for development and quality assurance.

* **`yarn dev`**: Starts the development server on port `3003`.
* **`yarn build`**: Compiles the application for production. This is run before deploying the storefront.
* **`yarn start`**: Starts the production server after a successful build.
* **`yarn test`**: Runs all the project's quality checks, including formatting, linting, and unit tests.
* **`yarn fix-format`**: Automatically formats your code with Prettier. Use this to ensure your code matches the project's style guidelines.
* **`yarn fix-lint`**: Automatically fixes linting errors reported by ESLint.
* **`yarn storybook`**: Launches the Storybook environment for developing and testing UI components in isolation.

---

### Dependencies

These are the core libraries the project relies on. You'll likely interact with these when building new features.

* **`next`**: The main framework for the application.
* **`react` & `react-dom`**: The fundamental libraries for building the user interface.
* **`@mui/material`**: The primary UI component library used for styling.
* **`swr`**: A React hook for data fetching.
* **`@tanstack/react-table`**: The library for creating tables and managing their state.

---

### Package Manager

This project uses **Yarn** as its package manager.

* **`packageManager`**: `yarn@3.3.0`
* **`engines`**: `npm` is explicitly forbidden. Always use `yarn` for installing and managing packages to avoid conflicts.