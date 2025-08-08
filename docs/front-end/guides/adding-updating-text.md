# Changing / Adding Text with Localization

## What is localization?
Localization is used to populate all text within this project. There should be no statically added text within this project. Localization is what adds language support to the website. As of 8/8/2025, the site currently only supports English.

All text on the site must be populated using localization. ESLint should give out an error if static text / html tags are detected.

## Adding localized text

1. Open up your project. All localization files are located under `integration > locales > custom > en-US` (or whatever language folder you are adding text to)

2. Localization files are separated into *json* files. The file structure separates the content based on the content location. For example, all text on the *Back Order Inquiry* page are located inside of the *backorderInquiry.json* file. If the json file doesn't exist for the page you're working on, then you can create a new json file.

3. Once your text is added the JSON file, open up a new terminal window by going to the top of VSCode, and go to `terminal > new terminal`. Type in the following command: `yarn integrate`

4. The yarn integrate command will find the latest changes in the locale folder, and add those changes to a master language / localization file.

5. Once the yarn integrate is completed, navigate to the screen that you are currently working in. Import the useLocalization hook into the content file with `import { useLocation } from '@/data/Localization';`. 

6. For an example, lets say we added the OrderDate text inside of the **backorderInquiry.json** file. This is what that structure looks like:
```
{
    "BackorderInquiry":{
        "Title": "Backorder Inquiry",
		"Header": {
			"OrderDate": "Order Date",
			"OrderNumber": "Order Number",
			"AccountNumber": "Account Number",
			"Item": "Item",
			"Backordered": "Backordered",
			"Ordered": "Ordered",
			"RequestCancelation": "Action"
		},
    }
    ... other stuff here
}
```
When we call the hook, we will reference the first object name that we need to access, which in this case is BackorderInquiry. So the hook will look like this:<br>
`const localization = useLocalization('BackorderInquiry');`

7. Once the hook is initialized as a const, we can access this just like any other object. In this example, we need to retrieve "OrderDate". We can do this by adding `localization.Header.Ordernumber.t()`.


## Replacing existing text
Replacing text is very similar to adding text from scratch, but there are instances that require additional steps.

1. The easiest way to find the text you need to change is by searching for the current text in the VSCode search bar. In this example, we'll change "Add a want list" to "Add a new want list".

2. The search results may be long, but we're looking specifically for a .json file that is located within integration > locales > **custom** > en-US.

3. In some situations, the only file that shows up is located inside of integration > locales> **core** > en-US. We *never* want to make changes to a core file, so we would copy the entire core .json file, and paste it into custom. In this new custom file, we only need to include the main object, and the text that we need added. In our current example, a custom .json file has already been created, so this doesn't apply to us.

4. Once the change has been made, we will just need to open up a new terminal and run `yarn integrate`. Since we didn't add anything new, there are no new connections to be made.