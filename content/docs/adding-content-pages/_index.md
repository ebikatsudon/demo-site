+++
date = '2025-02-06T17:00:38-08:00'
title = 'Adding Content Pages'
weight = 40
+++

# Adding Content to Your Site

All content in a Hugo site is stored in a top-level `content/` folder. Easy, right? From there, you can create collections of static pages by structuring them in various subfolders, or [sections](https://gohugo.io/content-management/sections/). For example, you could have an "about me" section and a blog section.

> **Note:** In order for Hugo to define a folder as a section, it must contain an index file called `_index.md`. (Don't forget the underscore!) This is called a [branch bundle](https://gohugo.io/content-management/page-bundles/#branch-bundles), and tells Hugo to create a navigable URL for that section and any nested folders within.

For our very first addition we'll create the home page for the site.

## How to create an index page

To create a Markdown file called `_index.md` inside `content/`, run this command:

```pseudo
hugo new content content/_index.md
```

If you open the file in an editor, you'll see that it contains some metadata: 

```pseudo
+++
date = '2020-02-02T20:20:20-02:00'
draft = true
title = 'Welcome!'
+++
```

You can add body text after this metadata section; however, note that the `draft = true` value means that Hugo will not publish the page when you build the site. When you're done making your changes, remember to change the value of draft to `false` so users can actually see the page.

For a full list of parameters that can be used in the front matter, refer to the [official documentation](https://github.com/alex-shpak/hugo-book/tree/master?tab=readme-ov-file#configuration) for the Hugo Book theme under the "Configuration" section.

As an example, the front matter for the home page of this site looks like this:

```pseudo
+++
date = '2025-02-06T17:00:38-08:00'
title = 'Welcome to my demo site!'
BookSection = 'docs'
+++
```

## Adding additional content

The above process can be repeated to create additional pages in your site. The sections of this site, for example, are structured as a series of nested folders within the `/content/docs` folder. Each subfolder contains an `_index.md` file that makes up the written content for each page.

The resulting content tree looks like this:

```pseudo
content
├── docs
└── _index.md
    ├── optional-understanding-hugo
    │   ├── _index.md
    ├── creating-your-hugo-site
    │   ├── _index.md
    └── installing-a-theme
    │   ├── _index.md
    └── adding-content-pages
    │   ├── _index.md
    └── getting-your-site-online
    │   ├── _index.md
    └── misc-formatting
        └── _index.md
```

If you don't want a page to appear in the sidebar, you can specify that in the front matter with the `toc_hide` flag:

```pseudo
toc_hide: true
```

## Side note on content organization and URLs

When structuring your site, it's important to keep in mind that sections define how the URL for each page of your site will look. For example, say your content folder looks like this:

```pseudo
content
└── about-me
    └── _index.md
    └── my-projects
        └── project1.md
```

If the base URL for your site is `www.homepage.com`, then Hugo would generate these URLs:
 - `www.homepage.com/about-me/`
 - `www.homepage.com/about-me/my-projects/project1/`

But what happens if you create an index file _without_ the underscore? In that case, Hugo considers the container folder to be a [leaf bundle](https://gohugo.io/content-management/page-bundles/#branch-bundles), and any other `.md` file in the bundle will not get a corresponding navigable URL.

Also keep in mind that if a Markdown file is named anything other than index.md, Hugo will use the name of its container folder as the page name. Keeping with our previous example of `www.homepage.com`, this means each of the following will render differently:

- `/content/about-me/projects1/index.md` becomes `homepage.com/about-me/projects1/`
- `/content/about-me/projects2.md` becomes `homepage.com/about-me/projects2/`
- `/content/about-me/projects3/result.md` becomes `homepage.com/about-me/result/`

If you want your URLs to follow a certain format, keep these differences in mind when organizing and naming folders in your directory.

Now, at this point you've created your Hugo site, installed a theme, and added content. It's time for the final step -- [Getting Your Site Online]({{< ref "/docs/getting-your-site-online" >}} "Getting Your Site Online").
