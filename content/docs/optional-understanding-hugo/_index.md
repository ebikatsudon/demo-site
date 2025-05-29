+++
date = '2025-02-06T17:00:38-08:00'
title = 'Optional: Intro to Hugo'
BookToC = false
weight = 10
+++

# Understanding Hugo and static site generators

The following information isn't necessary for installing Hugo, but may be interesting for anyone who plans on deepening their understanding of site generators and what's happening in the backend.

Hugo is a **static site generator** (abbreviated SSG), meaning it creates web pages with fixed, hard-coded (hence _static_) content that will not change unless the source code is changed. Each page on a static site is represented by an `.html` file on the server, and any given page will look the same to every person who accesses it.

In comparison, _dynamic_ site generators (such as Wordpress) rely on server-side languages and databases to display varying content in real time. This content can change based on different factors, such as time of day when the site is accessed or user interactions. The custom "For You" page on social media sites like X or Instagram, for example, are dynamic pages.

SSGs like Hugo work by converting plain text files to static site assets (HTML, CSS, or JavaScript files) using a template. When accessing a static site, the resulting web page is pre-rendered, cached, and served to the user. This results in faster load times, improved security (no dynamic content or databases that could be hacked), and less maintenance required.

With that high-level overview out of the way, let's get started on using Hugo to create your own static site. Click on [Creating Your Hugo Site]({{< ref "/docs/creating-your-hugo-site" >}} "Creating Your Hugo Site") in the sidebar to get started!