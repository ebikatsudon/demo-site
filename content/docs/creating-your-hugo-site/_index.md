+++
date = '2025-02-06T17:00:38-08:00'
title = 'Creating Your Hugo Site'
BookToC = false
weight = 20
+++
# Creating Your Hugo Site

This section will cover how to create a new GitHub repository, how to structure your local file directory for Hugo, and how to manually download and install Hugo.

### Step 1: Set up your Hugo file directory

Before installing Hugo, you'll need to prepare the file directory for your site. Create a folder named `bin` in your user directory with the file path `C:\Users\YOUR_USERNAME\bin`. Then, add this new `bin` folder to your system's PATH environment variable now so that when you run Hugo commands later, you won't have to specify the entire path every time.

Whenever you edit your PATH, however, it's recommended to first create a backup:

 1. Navigate to `System Properties` -> `Advanced system settings` -> `Advanced` tab -> `Environment Variables`.
 2. Select the `PATH` variable under "System Variables." Click "Edit," then "Edit text." Copy the entire value in "Variable value" and paste it into a text file editor such as Notepad.
 3. Save the file. If you need to restore the PATH, you can copy+paste the text back into the "Variable value."

 Now that your PATH is backed up, open the command line as administrator. To add your newly-created bin folder to the PATH, run the following: 
 `setx PATH "C:\Users\YOUR_USERNAME\bin;%PATH%"`. You can check if the directory was added successfully by running `echo %PATH%`, which will output the full value.

### Step 2: Download and install Hugo

Now that you've created the directory for Hugo, it's time to actually download and install it. There are two main ways to install Hugo:

 1. Use a package manager such as [Chocolatey](https://chocolatey.org/) or [Scoop](https://scoop.sh/) to handle the whole installation process for you
 2. Manually download and install Hugo from the [official Github repository](https://github.com/gohugoio/hugo/releases/tag/v0.142.0)
 
 To minimize the amount of programs you need to deal with, this guide will only cover the manual installation method. For a comprehensive step-by-step guide on installing Hugo via a package manager, Bryce Wray has a [great writeup](https://www.brycewray.com/posts/2022/07/really-getting-started-hugo/) on his site.

> Note: When downloading Hugo, it's almost always recommended to get the **extended version**.

Download the extended version of Hugo from the repository and extract its contents. Then move the `hugo.exe` file to the bin folder you created in the previous step.

### Step 3: Check that your installation was successful

To confirm that Hugo is now in the PATH, run the following in the command line: `hugo version`. The output should show the version of Hugo you installed.

Here's an example output:

```pseudo
hugo v0.142.0-1f746a872442e66b6afd47c8c04ac42dc92cdb6f+extended windows/amd64 BuildDate=2025-01-22T12:20:52Z VendorInfo=gohugoio
```

### Step 4: Initialize your Hugo site

Now that Hugo is installed, you can start creating your new website. In this tutorial we'll call the new site `demo-site`, but you can name it however you like.

To create your Hugo site, open Git and run the following: `hugo new site demo-site`.

If the site is created successfully, you'll get a message instructing you to install a theme as your next step.

```pseudo
PS C:\Users\Username> hugo new site demo-site
Congratulations! Your new Hugo site was created in C:\Users\Username\demo-site.

Just a few more steps...

1. Change the current directory to C:\Users\Username\demo-site.
2. Create or install a theme:
   - Create a new theme with the command "hugo new theme <THEMENAME>"
   - Or, install a theme from https://themes.gohugo.io/
3. Edit hugo.toml, setting the "theme" property to the theme name.
4. Create new content with the command "hugo new content <SECTIONNAME>\<FILENAME>.<FORMAT>".
5. Start the embedded web server with the command "hugo server --buildDrafts".

See documentation at https://gohugo.io/.
```

## Testing your site

To check if your site has been initialized properly, navigate to your newly-created directory in your console and run `hugo server` to build your site and run it locally. You can then view your site at `http://localhost:1313`.

Congratulations, you've officially created your first Hugo site! Right now it's basically a blank canvas -- let's add some pizzazz to it by installing a theme. To learn how to do so, proceed to the next section, [Installing a Theme]({{< ref "/docs/installing-a-theme" >}} "Installing a Theme").