+++
date = '2025-02-06T17:00:38-08:00'
title = 'Basic Formatting'
weight = 50
+++

Now that you know how to create a Hugo site and add pages to it, you've got the fundamentals down! Below are some more advanced steps to help you customize your site:

## Configuring the menu

The Book theme used for this site automatically generates a navigation menu on the left side of the site. By default sections in this menu are ordered alphabetically based on the title assigned in the front matter, but you can manually specify the order by using **page weights**.

The `weight` parameter for a page determines its order in a collection when sorted by weight. Pages with "lighter" (i.e. smaller) weights will appear at the top, while those with "heavier" or unassigned weights will appear at the bottom of the list. Page weights are assigned in the front matter and can be any non-zero integer.

Since each page in this demo site represents a step in a process, they need to be arranged in the menu in chronological order. To do so, add a weight parameter in the front matter of each index page. For ease of understanding, I've used multiples of 10 for each page weight. Below is an example of what the front matter looks like for the very first section in this site:

```pseudo
date = '2025-02-06T17:00:38-08:00'
title = 'Optional: Understanding Hugo'
BookSection = 'docs'
weight = 10
```

## Setting light or dark mode

Depending on the theme you use for your Hugo site, you may have the option to change between light and dark modes. The Hugo Book theme has this functionality, along with an additional option to set the theme mode automatically based on a user's browser or device settings. The specific method for setting the theme mode will vary depending on the theme, but for Hugo Book it's done with the `BookTheme` parameter:

```pseudo
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'Demo Hugo Site'
theme = 'hugo-book'
publishDir = "docs"

[params]
BookTheme = 'auto'
sectionPagesMenu = 'main'
```

If you want to change the look of your site, refer to the documentation for your chosen theme to see if there are any handy built-in parameters you can use to easily make changes.

## Linking to other sections of the site

To make navigation easier for readers, many of the pages in this site include links to the next section they should read. To cross-reference other sections or pages in your site within the body text of a page, you can use either the `ref` or `relref` [shortcodes](https://gohugobrasil.netlify.app/content-management/shortcodes/#using-the-built-in-shortcodes). The only difference between the two is whether the resulting URL is absolute (e.g. http://example.com/about) or relative to the current page (e.g. /about/).

The syntax for `ref` and `relref` is as follows:

```pseudo
{{</* ref "example.md" */>}}
{{</* ref "#anchor" */>}}
{{</* ref "example.md#anchor" */>}}
{{</* relref "example.md" */>}}
{{</* relref "#anchor" */>}}
{{</* relref "example.md#anchor" */>}}
```
`ref` and `relref` can be used in conjunction with Markdown to create hyperlinks. A hyperlink that references the "Creating Your Hugo Site" page, for example, would look like the following in Markdown:

```pseudo
[Creating Your Hugo Site]({{< ref "/docs/creating-your-hugo-site" >}} "Creating Your Hugo Site") 
```

One caveat is that you cannot reference `_index.md` files this way -- instead, the path must point to the folder it is in. So if I wanted to create a link to the home page of this site, I would instead use this:

```pseudo
[This is a link to the home page]({{< ref "/docs" >}} "Home Page") 
```