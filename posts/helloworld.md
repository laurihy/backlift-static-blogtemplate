{{$ embedin /layouts/post_template.html as maincontent }}

{{$ config }}
title: 'Hello there!'
intro: 'Welcome to your brand new blog. Hope you like it!'
public: yes
{{$ endconfig }}

# Hello there

This is a blog that runs on top of Backlift. *Check out your Dropbox /Apps/Backlift -folder to find files for this blog.

All posts are stored in *posts/*-folder. They are written in Markdown and compiled automatically into .html. Read more about Markdown at: **TODO: Add link**

## Curly braces and dollar signs?

They are Backlift template tags and provide a way to add interactivity to your website. In index.html:

    for post in /backlift/toc/posts/*.html | public True | sort modified
        post.title
        post.modified
        post.url
    endfor

This does several things. First, it uses Backlift's Table of Contents ("toc") API to fetch files from folder /posts/*.html. The things after pipe characters ("|") are filters. First we say that we should fetch only public posts (we'll get into this in a minute) and to sort them by "modified" property. This way we can loop through all of our posts.

Inside the block, we use template tags to refer to each post. Check out all available properties by opening /backlift/toc/posts/*.html in your browser.

## Embedin

Another important template tag is *embedin*. All it does, is read the template defined in URL ("parent"), and inject the rendered (i.e. template tags have been processed) content of the *current* file into parent, where position have been defined using a template tag. Most often the template tag to define position in parent is called "maincontent".

In parent template, you can use template tag "child" to refer to childs properties.

## Config

Configs are a bit weird. You use config ... endconfig to define additional variables, that will be available for that file. See the examples :)


