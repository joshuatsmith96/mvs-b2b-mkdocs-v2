# e-Marketing Spot HTML Guide

HTML used in e-Marketing spots (e-spots) is processed by a parser that safely converts all elements into **React components**. This enables rich and extensible functionality and allows for styling that ties into the underlying site theme. Some React components can be explicitly set, others are set automatically, and the remaining HTML elements are wrapped by a MUI utility to enable them to support MUI styling.

-----

## Explicit React Elements

To tie into special React-based elements, use the `element` attribute:

```html
<div element="Stack">...</div>
```

Each React element has its own set of properties, which can be passed in using the `props` attribute with a single-quote JSON syntax:

```html
<div element="Stack" props="{'direction': 'row', 'spacing': ''}">...</div>
```

### Supported MUI Element docs:

  * **Box:** [React Box - Material UI](https://mui.com/material-ui/react-box/)
  * **Button:** [React Button component - Material UI](https://mui.com/material-ui/react-button/)
  * **Stack:** [React Stack component - Material UI](https://mui.com/material-ui/react-stack/)
  * **Container:** [React Container component - Material UI](https://mui.com/material-ui/react-container/)
  * **Grid:** [React Grid component - Material UI](https://mui.com/material-ui/react-grid/)
  * **Paper:** [React Paper component - Material UI](https://mui.com/material-ui/react-paper/)

### Custom Elements:

  * **Tabs:** Supports the `labels` prop as an array of strings. These labels correspond to the placement of a child element within the tabs element.

    ```html
    <div element="Tabs" props="{'labels': ['Tab 1', 'Tab 2', 'Tab 3']}">
      <div>Tab 1 content</div>
      <div>Tab 2 content</div>
      <div>Tab 3 content</div>
    </div>
    ```

  * **Accordion:** Also supports the `labels` prop as an array of strings. These labels correspond to the placement of a child element within the accordion element.

    ```html
    <div element="Accordion" props="{'labels': ['First Title', 'Second Title', 'Third Title']}">
      <div>First Content</div>
      <div>Second Content</div>
      <div>Third Content</div>
    </div>
    ```

  * **Sidebar:** Primarily used in the `Aside` layout slot. This element displays a title and content that is moved out of the normal document flow at a mobile breakpoint, becoming a collapsible drawer at the bottom of the screen. It supports `title`, `mobileBreakpoint`, `optional href`, and `optional scrollable` props.

    ```html
    <div element="Sidebar" props="{'title': 'Something', 'mobileBreakpoint': 'md', 'scrollable': false, 'href': '#'}">
      <div sx="{'p': 2}">
        <p>This is some content</p>
      </div>
    </div>
    ```

-----

## Automatic React Elements

Some HTML tags are automatically converted to corresponding React elements without the need for the `element` attribute.

  * `a`: A linkable React component that accepts the `type` property. You can set it to `'button'` to make the link display like a button.

    ```html
    <a href="#" props="{'type': 'button'}">Some Link</a>
    ```

  * `div`: Becomes the **Box** MUI component: [React Box - Material UI](https://mui.com/material-ui/react-box/)

  * `hr`: Becomes the **Divider** MUI component: [React Divider component - Material UI](https://mui.com/material-ui/react-divider/)

  * `h1`, `h2`, `h3`, `h4`, `h5`, `h6`, `p`, `strong`: Become the **Typography** MUI component with the appropriate variant set. You can optionally pass your own `variant` property to change the look of that specific element.

    ```html
    <p props="{'variant': 'caption'}">...</p>
    ```

    You can also override the output HTML element while keeping the style of the selected variant by setting the `component` property.

    ```html
    <h3 props="{'component': 'h1'}">...</h3>
    ```

  * `icon`: A custom **Icon** component that renders a known SVG icon.

    ```html
    <icon name="check">hover text</icon>
    ```

  * `img`: An **Img** React component that automatically optimizes the image for performance where possible. For optimization, the **alt text**, and integer **width** and **height** values must be provided. Hero images above the fold should also have `priority="true"`.

  * `input`/`textarea`: Become the **Input** MUI component: [Input API - Material UI](https://mui.com/material-ui/api/input/)

-----

## SX Property

The `sx` property lets you use a superset of CSS that includes all the style functions exposed in `@mui/system`. You can specify any valid CSS using this prop, as well as many theme-aware properties unique to MUI System.

The `sx` property is supported on all elements you use, even if they aren't explicitly or automatically converted to one of the supported React components.

### Syntax

The `sx` property is set in a **single-quote JSON syntax**.

```html
<div sx="{ 'backgroundColor': 'primary.main', 'color': 'primary.contrastText' }">
  <h2>...</h2>
</div>
```

### Documentation

Keep in mind that the documentation provided is for use within a React context using JavaScript syntax. When you use the `sx` property in an HTML element, it must be in a single-quote JSON syntax, meaning all the keys must have single quotes around them: `'background': {}` instead of JavaScript's `background: {}`.

For more information, see: [The sx prop - MUI System](https://mui.com/system/getting-started/the-sx-prop/)