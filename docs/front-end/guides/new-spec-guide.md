# Add New API Spec
When changes are made to an API, the backend developers will create a new spec file. This spec file needs to be updated on the front-end.

1. To find the spec, we need to know which spec file is being updated. In this example, an update was made to the mvs-glcode spec. We can view the updated spec by visiting: `https://tsapp-testauth.midwestvet.net/wcs/resources/api/resource//mvs-glcode`

2. Once the spec has been located, copy the results and save it somewhere for later.

3. Inside the front-end code, navigate to `/integration/providers/custom/specs/custom/mvs-glcode.json`. Take the code that you got from step 2, and past it into the mvs-glcode.json file.

4. The last step is to open a terminal window, and type in `yarn integrate` to integrate the changes.