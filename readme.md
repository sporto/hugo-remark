# Hugo Remark theme

What is **hugo**?

[Hugo](http://gohugo.io/) is a great static site generator built in Go.

What is **remark.js**?

[Remark](https://github.com/gnab/remark) is a simple slide show generator from markdown files.

## About this theme

This theme creates a remark presentation using Hugo to concatenate and serve the files.

## Why use Hugo and not just remark.js?

Remark.js doesn't come with a way of serving files or reload them on changes. Also it requires you to write all your slides on just one html page.

By using Hugo:

- You can serve your slideshows on localhost easily
- Hugo will watch for changes and reload immediatelly
- You can write your slides on different markdown files, Hugo will concatenate them

## Installation

Follow the hugo [installation intructions](http://gohugo.io/). On mac simply do `brew install hugo`

## How to use

### Generating the site

```bash
hugo new site /path/to/presentation
cd /path/to/presentation
```

### Install this theme

Inside the presentation folder do:

```bash
git clone https://github.com/sporto/hugo-remark themes/remark
```
Add to config file
```
theme = "remark"
```
### Generate new slides

Inside the presentation folder do:

```bash
hugo new 010.md
```

Note that this theme will just put slides in alphabetic order by their __title__, so name them something like 010, 020, 030...

e.g.
```
+++
title = "010"
+++
```

Slides will be created on `./content` subfolder.
Edit the slides using markdown.

### Serve the slideshow

To show your slides run:

```bash
hugo server --buildDrafts --watch
```

And open the given url in a browser, e.g. `http://localhost:1313`

### Custom styles

You can add custom styles to your slides:

- Create a file `./layouts/partials/custom_head.html`
- Link `custom_head.html` in `head.html` by adding `{{ partial "custom_head.html" }}` to where you want.
- In this file add a link to a CSS style sheet e.g.
  `<link rel="stylesheet" href="/css/[some-name].css" />`
- Add your CSS in `./static/css/[some-name].css`
- Or just write your CSS in this file using `style` tags.

### Custom JS on the head

- Create a file `./layouts/partials/custom_head.html`
- Link `custom_head.html` in `head.html` by adding `{{ partial "custom_head.html" }}` to where you want.
- In this file add a link to the JS libraries you want to load e.g.
  `<script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>`
  `<script src="/js/[some-name].js"></script>`
- Add your JS in `./static/js/[some-name].js`


### Custom JS on the footer

You can also add custom JS on the footer, this is loaded after the remark initialisation. This is useful for adding custom behaviour to your presentation.

- Create a file `./layouts/partials/custom_footer.html`
- Link `custom_footer.html` in `footer.html` by adding `{{ partial "custom_footer.html" }}` to where you want.
- Add a JS script link there or just write the JS using `script` tags


