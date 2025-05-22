+++
date = '2025-02-06T17:00:38-08:00'
title = 'Installing a Theme'
BookToC = false
weight = 30
+++

# Uploading Your Site Via GitHub Pages

So you've finished building your site locally, and now you're ready to deploy it for all the world to see. There are a whole host of ways you can do so -- check out all the ways listed on the Hugo site [here](https://gohugo.io/host-and-deploy/) -- but for this tutorial, we're using [GitHub Pages](https://pages.github.com/). This is a free option that eliminates the need to buy a custom domain. On top of that everything can be done using Git Bash, which you should already have some familiarity with if you've followed the tutorial up to this point.

### Step 1: Initialize Your Site in Git

In Git, navigate to your site directory. Then run the following: 

```pseudo
git init
git add .
git commit -m "Adding site to Git"
```

This creates an empty Git repository in your site directory and tells Git to start tracking your files.

### Step 2: Create and Link a GitHub Repository

To host your site on GitHub Pages you'll need a repository to store it. Log in to your GitHub account and click the + icon in the top right, then select "New Repository." Give your repository the same name as your local Hugo directory -- i.e., if the folder containing your site files is called "Example Site," the corresponding repository on GitHub should also be called "Example Site." Also set the repository to "public" and uncheck the box for "Add a README file" before creating it.

Once your repository is created, GitHub will display an HTML link that ends in `.git`. Copy that link. Now you can link the repository you just created on GitHub to your local one with the following Git command, replacing the HTML link with the one you copied:

```git
git remote add origin https://github.com/yourusername/repo-name.git
```

Additionally, you may need to rename your branch from "master" to "main" to match GitHub's default directory structure:

```git
git branch -M main
```

### Step 3: Update and Push Your Site

Open the Hugo config file in your local directory and replace the default `baseURL` value with the URL for your site. Since this will be a project page and not a user page, it should look something like `baseURL = 'https://username.github.io/site-name/'`.

Save and commit your changes and run the `hugo` command to build the latest version of your site. When your site is finalized locally, you can push it to GitHub:

```git
git push -u origin main
```

### Step 4: Finalize Your Site

Almost done! Access your GitHub repository online and go to Settings > Pages. Under "Source" select "Deploy from a branch," then select "main" and "/docs" under "Branch." Save your changes, and GitHub should now indicate that it's serving your website from the "main" branch.

Congratulations, you now have a working static site hosted on GitHub Pages! Your site should be accessible at `https://yourusername.github.io/site-name`.

 With just this basic Hugo and Git knowledge under your belt, you're ready to create some truly amazing webpages to show off your content. Thank you for reading this far! If you'd like to learn some formatting tips for making your site look pretty, check out the [Misc Formatting]({{< ref "/docs/misc-formatting" >}} "Misc Formatting") section for tips. Otherwise, to learn more about me and my projects, check out my personal page.

