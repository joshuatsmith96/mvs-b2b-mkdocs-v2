# Reusable Components

This is a list of all components that can be used on CMC, including the HTML structures needed to implement each one.

---

## Material UI Components

### Box

The **Box** component is an MUI component enabled for use on CMC and is used much like a `div`.

```html
<div element="Box"></div>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-box/).

### Button

The **Button** component is an MUI component enabled for use on CMC. It is a more versatile version of the standard button element.

```html
<button element="Button">Click Me</button>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-button/).

### Container

The **Container** component is an MUI component enabled for use on CMC that centers your content horizontally.

```html
<div element="Container"></div>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-container/).

### Divider

The **Divider** component is an MUI component enabled for use on CMC that provides a thin, unobtrusive line for grouping elements to reinforce visual hierarchy.

```html
<span element="Divider" props="{'orientation': 'vertical', 'flexItem'}"></span>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-divider/).

### Grid

The **Grid** component is an MUI component enabled for use on CMC. Its responsive layout grid adapts to screen size and orientation, ensuring consistency across layouts.

```html
<div element="Grid" props="{'container', 'spacing': '{2}'}">
     
  <div element="Grid" props="{'size': '{8}'}">Grid items go in here</div>
</div>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-grid/).

### Paper

The **Paper** component is an MUI component enabled for use on CMC. It's a container for displaying content on an elevated surface.

```html
<div element="Paper" props="{'elevation': '{1}'}" sx="{'p': 2}">
      Paper Testing
  <div></div>
</div>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-paper/).

### Stack

The **Stack** component is an MUI component enabled for use on CMC. It is a container component for arranging elements vertically or horizontally.

```html
<div element="Stack" props="{'spacing': '{2}'}"><div></div></div>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-stack/).

### List, ListItem, ListItemButton, and ListItemText

The **List** component is an MUI component enabled for use on CMC. It is a continuous, vertical index of text or images.

```html
<div element="List">
   
  <div element="ListItem" props='{"disablePadding": true}'>
       
    <div element="ListItemButton">
           
      <div element="ListItemText" props='{"primary": "Inbox"}'></div>
         
    </div>
     
  </div>
   
  <div element="ListItem" props='{"disablePadding": true}'>
       
    <div element="ListItemButton">
           
      <div element="ListItemText" props='{"primary": "Drafts"}'></div>
         
    </div>
     
  </div>
</div>
```

For more details, view the [Official MUI Documentation](https://mui.com/material-ui/react-list/).

---

## Custom Components

### JotForm Component

Use the **JotForm Component** to embed a JotForm without a separate embed script. Just use the following HTML tag with `element="JotForm"` and the form's ID in the `props` attribute.

```html
<div element="JotForm"
props="{'id': 'id_here', defaults: '{{input_id_here: '{{info_here}}'}}'}">
</div>
```

The **defaults** prop is used to automatically populate default values into the JotForm inputs. The value inside of the double braces are values that are pulled from a users account information. The currently available (8/26/2025) user information usable on JotForms are:

1. shipTo
2. billTo
3. firstName
4. lastName
5. email

If you're unsure what the input ID for a JotForm input is, you can find it by:

1. Going to the JotForm form in edit mode
2. Click on the input you want to pre-populate data into
3. Click the properties / settings wheel
4. Go to the *advanced* tab
5. Go to *Field Details* at the bottom
6. Copy the *Unique Name* name, inside of the curly braces.

### Tabs

Provides a clean tabbed interface.

Supports the "labels" prop as an array of strings. These labels correspond to the same placement of a child element within the tabs element:

```html
<div element="Tabs" props="{'labels': ['Tab 1', 'Tab 2', 'Tab 3']}">
  <div>Tab 1 content</div>
  <div>Tab 2 content</div>
  <div>Tab 3 content</div>
</div>
```

### Accordion
An accordion style dropdown menu.

Supports the "labels" prop as an array of strings. These labels correspond to the same placement of a child element within the tabs element:

```html
<div element="Accordion" props="{'labels': ['First Title', 'Second Title', 'Third Title']}">
    <div>First Content</div>
    <div>Second Content</div>
    <div>Third Content</div>
</div>
```

### Sidebar
Primary use case is in the Aside layout slot. This element displays a title and content that is moved out of the normal document flow at a mobile breakpoint becoming a collapsible drawer at the bottom of the screen. Supports title, mobileBreakpoint, optional href, optional scrollable props.

```html
<div element="Sidebar" props="{'title': 'Something', 'mobileBreakpoint': 'md', 'scrollable': false, 'href': '#'}">
    <div sx="{'p': 2}">
        <p>This is some content</p>
    </div>
</div>
```