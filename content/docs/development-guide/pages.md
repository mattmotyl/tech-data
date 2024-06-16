---
title: "Pages"
date: "2024-06-16T09:16:03-06:00"
lastmod: "2024-06-16T09:16:03-06:00"

description: "How to create and organize pages and configure menus"
icon: "article"
weight: 100 

draft: false 
toc: false 
---

## Create a new page

Though the markdown pages are essentially copy-able, when developing,
it's recommended to use the `hugo new` command to create a new page each time,
because this helps the devleopment server not get surprised by new pages
existing. If you're seeing unexpected behavior around menus in particular,
it's probably because you created a new page without running `hugo new` - 
delete the `public` folder and restart the hugo server to fix this.

```bash
hugo new docs/potential-folder/my-new-page.md
```

This creates a new page with a URL of `/potential-folder/my-new-page`  

## What are `index.md` & `_index.md` pages?

### `index.md`: When you want a folder for resources

`index.md` is typically used for individual content pages, such as blog posts, articles, or standalone pages. It is placed inside a specific content directory and represents a single piece of content.
Example: If you have a blog post, you might have a file like content/posts/my-first-post/index.md.

**This is most useful when you have associated assets (ex: images) that you want to colocate with the content for the page - it allows for better organization than having the markdown file and assets located separately.**

Note: when you create a page of this kind, the default frontmatter will be incorrect - copy the right front matter from elsewhere. 

### `_index.md`: the list page

This file is used for list pages or sections. It represents the content and configuration for an entire section or list of content.

**If you don't have an `_index.md` file for your section, your section does not exist! Instead nested pages would just be shown at a top level (or within whatever section they were in).** This is because you need metadata to tell hugo how to render the section: the name of the section, its icon, its position in the menu for example. 

It is placed in the root of a content directory or subdirectory to provide metadata, for that section's list page (which optionally can have its own content).
Example: a page for an overview of a section of content that has multiple sub-pages.

By default this kind of page generates a list of chips at the bottom (below the content) that links to each of the sub-pages within the section. This behavior is easy to tweak if you'd like me to (or to customize per-page).

## My page isn't showing up

This is a common issue. Some things to check:

- If the page is in a folder, does the folder have an `_index.md` page?
- If any parent diirectory of the page has an `index.md` page, is it's front-matter what you expect, or does it say `never` in it?

## Front Matter

These features of the front matter are less intuitive:

- `icon` used in menus, can be omitted
- `toc` generates a table of contents if enabled AND if headings are used in the page **TODO(grady) add an option for TOC only if screen size is greater than some size**
- `weight` decides the order of the page relative to other pages in the same section in menus
- `draft` currently not used to gate the creation of a page, this can be a good feature for checking paritally developed pages into code and then only deploying non-draft content. It defaults to `false`, but we can change that.