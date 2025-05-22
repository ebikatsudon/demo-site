+++
date = '2025-02-06T17:00:38-08:00'
title = 'Adding Content Pages'
weight = 40
+++

# Creating a Home Page

For our very first addition to the site, let's add an index page. This is the first page users will see when they visit your site. New pages can be added to your Hugo site with this command:

```pseudo
hugo new content content/_index.md
```

This creates the `_index.md` Markdown file within the "content" folder of your Hugo directory. If you open the file in an editor, you'll see that it contains some editable metadata: 

```pseudo
+++
date = '2020-02-02T20:20:20-02:00'
draft = true
title = 'Welcome!'
+++
```

You can add body text after this metadata section; however, note that the `draft = true` value means that Hugo will not publish the page when you build the site. When you're done making your changes, remember to change the value of draft to `false` so users can actually see the page.

For a full list of parameters that can be used in the front matter, refer to the [official documentation](https://github.com/alex-shpak/hugo-book/tree/master?tab=readme-ov-file#configuration) for the Hugo Book theme under the "Configuration" section.

The front matter for the home page of this site looks like this:

```pseudo
+++
date = '2025-02-06T17:00:38-08:00'
title = 'Welcome to my demo site!'
BookSection = 'docs'
+++
```

# Additional Content Pages

The above process can be repeated to create additional pages in your site. The sections of this site, for example, consist of a series of folders nested under the `/content/docs` folder. Each subfolder contains an `_index.md` file that makes up the written content for each page.

The resulting content tree looks like this:

```pseudo
content
├── docs
│   ├── optional-understanding-hugo
│   │   ├── _index.md
│   ├── creating-your-hugo-site
│   │   ├── _index.md
│   └── installing-a-theme
│   │   ├── _index.md
│   └── adding-content-pages
│   │   ├── _index.md
│   └── getting-your-site-online
│   │   ├── _index.md
│   └── misc-formatting
│       ├── _index.md
└── _index.md
```

If you don't want a page to appear in the sidebar, you can specify that in the front matter with the `toc_hide` flag:

```pseudo
toc_hide: true
```

One thing to note about page names and how they're reflected in the site URL -- when Hugo finds an index.md file it will use the name of its container folder as the post name. If a Markdown file is named anything other than index.md, that will be the post name. This means each of the following will render different:

- `/content/docs/example1/_index.md` will render as `baseurl.com/docs/example1/`
- `/content/docs/example2.md` will render as `baseurl.com/docs/example2/`
- `/content/docs/example3/test.md` will render as `baseurl.com/docs/test/`

If you want your URLs to follow a certain format, keep these differences in mind when organizing and naming folders in your directory.

At this point you've created your Hugo site, installed a theme, and added content. Now it's time for the final step -- [Getting Your Site Online]({{< ref "/docs/getting-your-site-online" >}} "Getting Your Site Online").
