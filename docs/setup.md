### Front-End Project Setup Guide

This guide provides a step-by-step process for setting up your front-end development environment and cloning the project repository.

-----

### 1\. Prerequisite Software

Before you begin, ensure you have the following software installed:

  * **Node.js**: A JavaScript runtime environment.
  * **Yarn**: A package manager for JavaScript.
  * **Git**: A version control system.

You can verify their installation and check their versions by running these commands in your PowerShell or terminal:

```bash
node --version
yarn --version
git --version
```

If any of these are not installed, you will need to install them. Additionally, confirm with Ryan at BlueSky that you have the necessary permissions to access the Bitbucket project.

-----

### 2\. Set up SSH Key

An SSH key is used to authenticate your machine with Bitbucket, granting you secure access to the repository.

1.  Open a command prompt and navigate to your user directory:
    ```bash
    cd C:\Users\yourusernamehere
    ```
2.  Create a new `.ssh` directory and enter it:
    ```bash
    mkdir .ssh
    cd .ssh
    ```
3.  Generate a new SSH key. When prompted, leave the file name and passphrase blank by simply pressing Enter.
    ```bash
    ssh-keygen -t rsa -b 2048
    ```
4.  Locate the `.ssh` folder in your user directory. Open the **`id_rsa.pub`** file with a text editor like Notepad and copy its entire contents.
5.  Navigate to your Bitbucket account settings: **`https://bitbucket.org/account/settings/ssh-keys/`**.
6.  Click **"Add key"**, provide a name for the key, and paste the copied content into the "SSH public key" text area.

-----

### 3\. Allow Long File Names

To prevent errors when cloning the repository, you need to enable support for long file paths on your system.

1.  Open Windows PowerShell as an **administrator**.
2.  Run the following command:
    ```bash
    git config --system core.longpaths true
    ```
    If you do not see a "permissions denied" message, the command was successful.

-----

### 4\. Clone the Repository

Once your system is configured, you can clone the project.

1.  Go to the repository's page on Bitbucket: **`https://bitbucket.org/blueskytp/mvs-b2b-frontend/src/main/`**.
2.  Ensure the dropdown is set to **SSH** and copy the provided clone URL.
3.  Open a terminal in the directory where you want to store the project (e.g., `Documents/BitBucket`).
4.  Execute the `git clone` command you copied.
    ```bash
    git clone git@bitbucket.org:blueskytp/mvs-b2b-frontend.git
    ```

-----

### 5\. Install Dependencies and Configure `.env` File

This final step prepares the project for development.

1.  Inside the cloned repository folder, create a new file named **`.env.local`**.

2.  Paste the following configuration into the file and save it:

    ```
    USE_MOCK=false
    MOCK_HOST_PORT=9003
    NODE_TLS_REJECT_UNAUTHORIZED=0

    # HCL_SEARCH_ORIGIN=https://orchestration:19443
    # HCL_TRANSACTION_ORIGIN=https://localhost:443

    HCL_SEARCH_ORIGIN=https://orchestration-testauth.midwestvet.net
    HCL_TRANSACTION_ORIGIN=https://tsapp-testauth.midwestvet.net
    HCL_CUSTOM_SEARCH_ORIGIN=https://search-testauth.midwestvet.net

    LOG_LEVEL=trace
    TRACE_DETAIL=
    LOG_CENSOR_STRING=******
    CACHE_TTL=0
    CACHE_SIZE=
    STARTUP_ARGUMENT=
    EXPOSE_SOURCE_DATA=true

    MAP_API_KEY=
    RECAPTCHA_3_KEY=
    RECAPTCHA_3_SECRET=
    GOOGLE_OAUTH_CLIENT_ID=
    NAVIGATION_DEPTH=
    IMAGE_REQUEST_TEMPLATE=https://images-mvs-b2b.evolvestorefront.com/${src}?format=auto&width=${width}&height=${height}
    ```

    You can also swap the search, transaction, and custom search endpoints out for the **testlive** endpoints instead. To do this, replace the `HCL_` endpoints with the following:

    ```
    HCL_SEARCH_ORIGIN=https://orchestration-testlive.midwestvet.net
    HCL_TRANSACTION_ORIGIN=https://tsapp-testlive.midwestvet.net
    HCL_CUSTOM_SEARCH_ORIGIN=https://search-testlive.midwestvet.net
    ```

3.  Open a new terminal window inside the project directory and run the `yarn` command to install all necessary dependencies.

    ```bash
    yarn
    ```

4.  To start the development server, run:

    ```bash
    yarn dev
    ```