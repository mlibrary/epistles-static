# Design System 11ty (Eleventy) Starter

> Maintained by the [U-M Library Design System Team](https://design-system.lib.umich.edu/)

This is a minimal starter. There is basic page structure and navigation built in but add what you need.

## Development Quick Start
There are two ways to start developing: 
1. Use the template, or 
2. Clone the repo


*Use the template*

This repository is set up as a template so you may quickly generate a repository with the existing directory structure, branches, and files. Activate the "Use this template" button on this page to begin.

OR

*Clone the repo*
```
git clone https://github.com/mlibrary/design-system-11ty-starter.git
```

Install 11ty and dependencies

```
npm install
```

Start the 11ty development server and watch Sass (.scss) files

```
npm start
```

View in browser

```
http://localhost:8080
```

## Dev Scripts to Know

- `npm start` to start the eleventy server (serves the `/public` folder) and watch the Sass `/scss` folder
- `npm build` to create a production build. Outputs into `/public`.

### Building and watching files

`npm-run-all` is a CLI tool to run multiple npm-scripts in parallel or sequential. This is used in the dev scripts to watch Sass files and hot reload 11ty files in parallel.

---

## What's Included

There are four layouts:
- `base.njk`
- `home.njk`
- `page.njk`
- `static.njk` (used for 404 page)

The starter also contains the following U-M Library Design System web components

- Universal Header
- Website Header

As well as the:

- Design System CSS package
- Material Design font family (for using Material Icons)

The following is included in the `base.njk` `<head>` and is required for the web components, CSS package, and icons:

```
<link href="https://cdn.jsdelivr.net/npm/@umich-lib/web@1.3.0/umich-lib.css" rel="stylesheet"/>
<script type="module" src="https://cdn.jsdelivr.net/npm/@umich-lib/web@1.3.0/dist/umich-lib/umich-lib.esm.js"></script>
<script nomodule src="https://cdn.jsdelivr.net/npm/@umich-lib/components@1.1.0/dist/umich-lib/umich-lib.js"></script>
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

There are also partials components, including:
- `banner-hero.njk`
- `banner-feedback.njk`
- `breadcrumbs.njk`
- `cards.njk`
- `primary-nav.njk`
- `side-nav.njk`

---

## Building Your Site

This is some very basic information. Please read the official [11ty documentation](https://www.11ty.dev/docs/) for an in-depth guide to building with 11ty.

### Edit site metadata

Edit your site metadata (site name, author, contact, url, etc..). This information is used throughout the site and for your site's SEO.

```
src/_data/meta.json
```

### Layouts

Page layouts are located the the `layouts` folder.

```
src/_includes/layouts
```

Layouts use the Nunjucks templating language.
There is a `base.njk` file for the HTML boilerplate.
Additional layouts build off of that boilerplate.

### Create pages/ page content

Page content is created with Markdown (.md).

```
src/pages
```

Create your content in a markdown file. Use YAML front matter to add data to your content. Locally assigned front matter values override things further up the chain.

### Styles

Edit the styles in the `src/scss` folder. 11ty is watching that folder and building the Sass files into `src/css`. 11ty then passes through the CSS to the `public` folder.

### Images

Add images to the `src/img` folder. 11ty is watching that folder and passing through the files to the `public` folder.

Included is a template image called `social-card.png`. Replace that image with one of your own (1200px x 630px) to use as the social card linked for your SEO. This image will then show up when your site is shared on Facebook, Twitter, LinkedIn, etc...

### 11ty Features

#### **Plugins**

This starter uses the [11ty Navigation Plugin](https://www.11ty.dev/docs/plugins/navigation/).
This plugin supports infinite-depth hierarchical navigation and breadcrumbs.

Add the `eleventyNavigation` object to your front matter data (or in a data directory file). Assign a unique string to the key property inside of `eleventyNavigation`.

```
eleventyNavigation:
  key: about
```

#### **Collections**

Collections allow you to group data in certain ways using `tags`.

_Important distinction_: tags have a singular purpose in Eleventy... to construct collections of content. Not to be confused with tag labels used in blogs.

---

## Accessibility

This starter has been tested with ARC Toolkit, axe DevTools, WAVE, and keyboard. Once any new content has been added to it, please test again.

## Resources

Please visit the official [11ty](https://www.11ty.dev/docs/) docs.

## Bug Reports

Please file an issue or submit a PR. You can also email the Design System team at [library-design-system-team@umich.edu](library-design-system-team@umich.edu) and we will be in touch!
