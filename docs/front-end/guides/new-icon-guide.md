I've cleaned up the provided text, corrected the grammar, and formatted it for better readability.

# Adding New Icons

This project uses **MUI icons** directly from the MUI GitHub repository. Follow the steps below to add a new icon.

***

## Finding and Downloading an Icon

1.  First, go to MUI's **Material Icon visual library** to find the name of the icon you want to add.
2.  Once you have the name, navigate to the official **MUI GitHub Repository**.
3.  Click on the "Go to file" search bar and type in the name of the icon. For example, if you're looking for the `Payments` icon, you'd type "payments".
4.  From the search results, look for a file with the following structure: `packages/mui-icons-material/material-icons/payments_[version of the icon you want to use].svg`.
5.  Click on the file you want to use. Right-click the preview image and select **"Save image as"**.
6.  When saving, be sure to remove any text after the icon's name, leaving it as just the icon name (e.g., `payments.svg`).

***

## Adding the SVG Image to React

1.  Drag and drop the downloaded SVG file into the `public/icons` folder.
2.  Once the icon is in the folder, open your terminal and run the command `yarn integrate`.