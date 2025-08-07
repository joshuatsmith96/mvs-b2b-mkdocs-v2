-----

# Using Git with Bitbucket

This guide outlines the steps for managing your code with Git and Bitbucket, from retrieving the latest changes to creating a pull request.

-----

## 1\. Get the Latest `main` Branch

Before you start working, always ensure your local `main` branch is up to date with the remote repository.

1.  Open your terminal or IDE (like VS Code).
2.  Navigate to your working directory. For example, `cd C:\GitRepos\mvs-b2b-frontend`.
3.  Switch to the `main` branch with `git checkout main`.
4.  Pull the latest changes from the remote `main` branch:
    ```bash
    git pull origin main
    ```

-----

## 2\. Create a Local Branch

Create a new local branch for every new feature or bug fix you work on.

1.  In your terminal, use the following command to create and switch to a new branch. The naming convention is crucial here:

      * **For bug fixes:** `bugfix/MHBI-[ticket number]-short-description`
      * **For new features:** `feature/MHBI-[ticket number]-short-description`

2.  For example, to create a new feature branch for ticket `MHBI-820`, you would run:

    ```bash
    git checkout -b feature/MHBI-820-Product-Image-Disclaimer-Message
    ```

-----

## 3\. Push Your Local Branch to Bitbucket

Once you have finished making changes and are ready to push your code, follow these steps.

1.  **Add all changes:**
    ```bash
    git add .
    ```
2.  **Commit your changes:**
    ```bash
    git commit -m "Explain the change that was made"
    ```
3.  **Rebase with `main`:** This ensures your branch is up to date and clean before pushing.
    ```bash
    git rebase origin/main
    ```
4.  **Push to the remote repository (Bitbucket):**
    ```bash
    git push -u origin <your branch name>
    ```

-----

## 4\. Create a Pull Request

A pull request is required to merge your changes into the `main` branch. This process allows other developers to review your code.

1.  Navigate to your Bitbucket repository: `https://bitbucket.org/blueskytp/mvs-b2b-frontend`.
2.  Go to the **Branches** section.
3.  You should see the branch you just pushed. Click the **Create** button next to it.
4.  **Fill out the Pull Request details.**
      * Add a description if necessary.
      * Select the **"Delete branch after merge"** option to keep the repository clean.
      * Add a reviewer. At the time of this document, Tyler at BlueSky is the main reviewer.
5.  Click the **Create pull request** button to submit your request for review.