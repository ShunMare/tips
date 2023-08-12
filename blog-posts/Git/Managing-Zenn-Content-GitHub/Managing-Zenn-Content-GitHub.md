---
title: Managing Zenn content in a GitHub repository 
published: true
description: description
tags: Git, Zenn
---
## Zenn CLI Installation and Project Creation
1. Installing Zenn CLI
Zenn CLI allows you to write and preview articles or books in your local environment. First, we will use npm (Node.js package manager) to install Zenn CLI.
    ```bash
    npm install zenn-cli --global
    ```
2. Creating a New Zenn Article
    ```bash
    zenn new:article
    ```
## GitHub Setup
1. Create a GitHub Repository
   1. Access the GitHub website and sign in.
   2. Click the '+' icon on the top right of the homepage and select 'New repository'.
   3. Input the repository name (e.g., zenn-contents). While the name is up to you, zenn-contents is recommended.
2. Push the Zenn Project to the GitHub Repository
   1. Clone the new GitHub repository using the following command:
      ```bash
      git clone [GitHub Repository URL]
      ```
   2. Move to the cloned repository directory and copy the Zenn project contents there.
   3. Commit and push the changes to the GitHub repository with:
      ```bash
      git add .
      git commit -m "Initial commit"
      git push origin main
      ```
## Editing and Publishing the Article
1. Edit the Article in VSCode
   1. Open Visual Studio Code (VSCode).
   2. Select 'File' > 'Open' and open the cloned GitHub repository.
   3. Edit the markdown file inside the `articles` directory with your article content.
2. Push Changes to GitHub
   1. Click on the Git icon on the left sidebar in VSCode.
   2. Stage the changes, input a commit message, then click the '✓' button to commit.
   3. Click the '...' icon above and select 'Push' to push the changes to GitHub.
3. GitHub Integration on Zenn
   1. Access the Zenn website and log in.
   2. From the dashboard, select 'GitHub Integration'.
   3. Follow on-screen instructions to integrate GitHub with Zenn.
4. Publish the Article on Zenn
   1. Navigate to your Zenn dashboard.
   2. Click on 'Articles' and then click the 'Publish' button next to the article you wish to release.