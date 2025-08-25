# Adding CMC-Usable Components

Before you can use your new React Component inside of CMC, you'll first have to setup the component so that it can be used inside of CMC.

1. Inside of your React code, navigate to `presentation / utils / parseHTML / constants / elements.tsx`. This file controls which components are accessible to CMC.

2. Import the component you want to enable for CMC, and add that component name to the ComponentMap object.

3. Once complete, the component should be usable on CMC. For information on how to use a component on CMC, please visit the [HTML Guide](/front-end/guides/e-marketing-html-guide/) and the [Re-Usable Components Guide](/front-end/guides/reusable-components/).