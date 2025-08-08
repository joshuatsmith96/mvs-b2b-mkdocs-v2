This document outlines the main scripts used by the **MVS B2B E-Commerce Storefront**.


---

### Relevant project directories
Many of the folders and files inside of this project are considered **core**, which means they are integral to the project and should never be changed directly. Below are the relevant folders and files that developers will be involved in the most:

| Path                                         | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `/integration/data/custom/Content`           | This is where integration files for content areas are kept. API calls happen within these files. |
| `/integration/locales/custom/[language]`     | All of the website's text is located within these files.                    |
| `/integration/providers/custom/specs/custom` | Spec files that dictate API schemas.                                        |

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