+++
date = '2025-02-06T17:00:38-08:00'
title = 'Installing a Theme'
BookToC = false
weight = 30
+++
# Installing a Theme

Themes are a quick and easy way for new Hugo users to make their sites look nice without needing any deep programming or design knowledge. Some awesome members of the Hugo community have created free themes for all kinds of purposes; you can browse a list of popular Hugo themes [here](https://themes.gohugo.io/). The theme used in this tutorial is called "Hugo Book," and can be found [here](https://github.com/alex-shpak/hugo-book).

There are two main ways to install your Hugo theme. Some people recommend cloning the repository for your desired theme into your "Themes" folder with `git clone theme-repository.git`. For this tutorial we'll instead be using **git submodules**, which will add the theme repository as a _subdirectory_ within your Hugo site repository. This avoids potential problems down the line in case you decide you'd like to host your website on a different platform (like Netlify) instead.

To start, make sure you're in the root directory for your Hugo site in Git. Then use the `git submodule` command to add the theme repository.

```pseudo
git submodule add https://github.com/alex-shpak/hugo-book.git themes/hugo-book
```

## Configuring Your Theme

Next, set your theme as Hugo Book in your site's configuration file, `hugo.toml`. This config file should have been automatically generated when you created your site. You can use the following command in Git:

```pseudo
echo "theme = 'Hugo Book'" >> hugo.toml
```

For the site to be hosted on GitHub Pages later on, configure Hugo so that it publishes the site files into a directory called `\docs` instead of the default `\public`. To do so, open the `hugo.toml` file and add the following line:

```pseudo
publishDir = 'docs'
```

Since by default GitHub expects pages to be built with Jekyll, you'll also have to specify not to do that by adding a file called "nojekyll" in your directory root. To create the file using your terminal, run:

```pseudo
touch docs/.nojekyll
```

For additional site configuration settings, you can copy the `hugo.toml` file from the example site for your chosen theme and update the values according to your own preferences. Typically theme authors will include a full list of possible parameters in the documentation, so don't be afraid to experiment with customizing your site!

Here is what the `hugo.toml` file for this site looks like:

```pseudo
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'Demo Hugo Site'
theme = 'hugo-book'
publishDir = 'docs'

[params]
BookTheme = 'auto'
sectionPagesMenu = 'main'
```

For this site, I added the `BookTheme` and `sectionPagesMenu` parameters under the `[params]` header.

* `BookTheme`: Sets the site to either dark, light, or auto (i.e. follows your browser/OS preferences) mode
* `sectionPagesMenu`: Automatically creates an item in the menu for every section of the site (i.e. every top-level folder under the `content` folder)

For a full list of parameters available with the Hugo Book theme, check out the [documentation](https://github.com/alex-shpak/hugo-book/tree/master?tab=readme-ov-file#configuration).

With your slick new theme installed, let's add some actual content to your site. You'll learn how to do that in the next section, [Adding Content Pages]({{< ref "/docs/adding-content-pages" >}} "Adding Content Pages")