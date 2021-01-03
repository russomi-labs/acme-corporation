# acme-corporation

A basic website for a company named Acme Corporation.

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)
- [Contributing](CONTRIBUTING.md)

## About <a name = "about"></a>

📖 [Hugo in Action](https://www.manning.com/books/hugo-in-action) teaches you to build and host your own fully customizable static website with the Hugo engine.

> A basic website for a company named Acme Corporation. Acme Corporation is a leading manufacturer of shapes like lines, circles, squares and triangle in digital form in the planet. We will be using an existing Hugo theme and start with understanding how to add content to a Hugo website.

Hugo skeleton generated by the hugo new command:

``` bash
❯ tree -C

acme-corporation
├── CONTRIBUTING.md
├── README.md
├── archetypes
│   └── default.md
├── config.yaml
├── content
├── data
├── layouts
├── static
└── themes

6 directories, 4 files
```

The various parts of a Hugo website consist of:

- the `archetypes` folder for the content templates,
- the `config` file for the settings and metadata,
- the `content` for the textual content,
- the `data` for structured content (key value pairs),
- the `layouts` and `themes` for the template and design of individual pages and
- the `static` folder for additional content that needs to be hosted but does not fit into any other category.

## Getting Started <a name = "getting_started"></a>

> Hugo is extremely easy to get started. It does not have any major dependencies and does not require a beefy hardware to run. It is fast and can be used on old hardware and the basic versions of cloud based virtual machines.

### Prerequisites

- [Git](https://git-scm.com/)
- [GitHub Account](https://github.com/join)

### Installing

``` bash
# Install Hugo https://gohugo.io/
brew install hugo

# Install Tree
brew install tree
```

## Usage <a name = "usage"></a>

``` bash
# Create a site skeleton with yaml.
hugo new site acme-corporation --format yaml

# Create an empty GitHub repository.
git init .

# Add files that were just created using the Hugo command line.
git add --all

# Check-in those files to version control with a commit message.
git commit -m "Create website skeleton"

# Add origin
git remote add origin https://github.com/russomi-labs/acme-corporation.git

# Move the current branch to "main" -M Shortcut for --move --force.
git branch -M main

# git push adding upstream tracking branch at origin main.
git push -u origin main
```

### Migrating to Hugo

Hugo supports importing content from Jekyll and automatically converts content from the Jekyll format to the format that Hugo understands.

You can use `hugo import jekyll <source jekyll folder> <target hugo folder>` command to import content from Jekyll into a Hugo website.

This command does not provide synchronization and is meant for a one time import.

### Adding a theme

There multiple ways to get a theme:

1. Use Hugo Modules to integrate the theme
2. Use git sub-modules to have a reference to the theme in the themes folder
3. Download and copy the theme to the themes folder

Configure the theme in `config.yaml` :

``` yaml
baseURL: http://example.org/
languageCode: en-us
title: My New Hugo Site
theme: Eclectic
```

This tells Hugo to look for a folder named `Eclectic` in the `themes` folder and load the theme from that folder.

### Running the dev server

You can run our `Acme` website in development mode using the command `hugo server` .

> This hosts the hugo based website locally (at <http://localhost:1313/>) and automatically rebuilds it as the content changes and the changes we do in the theme as well as in the content update in near realtime in the browser.

``` bash
# Run the development server locally
hugo server     # or hugo serve
```

## Adding content

> We will be converting the empty page generated with the theme into a fully functional website. This includes configuring the theme by providing it with some settings and metadata, adding pages like the privacy policy and terms of use and overriding the landing page provided by the theme with a custom version.

### Configuration

- Apart from settings, the config file is also used to label elements of the Hugo website.
- Other parts (like params) are different per theme and depend on the theme.
- Even image locations like that of the `logo.svg` is specific to the theme.

[config.yaml](config.yaml) - These changes provide the information to fill up the menus, the footer, copyright notices as well as the title and author information as per the requirements of the theme eclectic for Acme Corporation.

``` yaml
baseURL: https://github.com/russomi-labs/acme-corporation                      # Hosting location.
languageCode: en-us                           # Locale
title: Acme Corporation                       # Name of the website
theme: Eclectic                               # Name of the theme
author:                                       # Information about the website author
  facebook: "https://facebook.com/example"
  twitter: "https://twitter.com/example"
  email: "contact@example.org"
  name: "Acme Corporation"
  location: New York
  phone: (999) 999-9999
  hours: "**Mon-Fri:** 9:00AM - 6:00PM, ET"

menu:                                         # Menu placement
  main:                                       #    - Name of the menu

    - identifier: about                       #       - Identifier

      name: About                             #       - Display name (theme specific key)
      url: /about                             #       - Target URL
      weight: 1                               #       - Sorting order

    - identifier: contact

      name: Contact
      url: /contact
      weight: 2
params:                                       # Theme specific parameters
  color: "#71B180"
  copyright: "Copyright &copy; 2020 Acme Corporation. All Rights Reserved."
  footer:

    - title: About

      content: Acme Corporation is the world's leading manufacturer of digital shapes. From squares and circles to triangles and hexagons, we have it all. Browse through our collection of various forms with different thickness and line styles. We shape the world. You live in it.

    - title: Recent Blog Posts

      recents: blog
      recentCount: 7

    - title: Contact Us

      contact: true
```

### Content Pages

- Content pages can be created as text/markup files in the content folder.

### Index Page

- The index page, also called the home or the landing page is a special page in most websites whose content is unique and different from all other pages.
- Hugo provides a special template for the index page called the index template.

> We can override templates in a Hugo theme by placing a html template file in the layouts folder. Doing that provides someone who understands HTML a quick way to customize a website without learning Hugo. The custom HTML can be very specific to a particular website but until we use Hugo's template language, we have to be very careful with the HTML we are writing as the custom HTMl page does not change automatically when the content it links to changes. - [Hugo in Action - Chapter 2](https://livebook.manning.com/book/hugo-in-action/chapter-2/v-7/point-9294-88-88-0)

## Continuous Delivery

- The simplicity of Netlify and GitHub Pages is the best approach to get started with learning Hugo.
- When signing up for Netlify with GitHub, it provides an automatic integration where you can search repositories.

### Netlify

Key Features

- deployment services with built-in support for Hugo
- integration with GitHub
- build instructions via a config file called netlify.yaml
- command line tool
- branch domain for pull requests

Sign Up: <https://app.netlify.com/signup>

### GitHub Pages

Key Features

- best place to get started
- can render static HTML from a branch or a folder in your code repository
- need to provide build steps via GitHub Actions
- GitHub Actions for Hugo - <https://github.com/marketplace/actions/hugo-setup>

Join GitHub: <https://github.com/join>

## Resources

- [Hugo in Action](https://www.manning.com/books/hugo-in-action) - Static sites and dynamic Jamstack apps
- [GitHub Action Hero: Shohei Ueda](https://github.blog/2020-03-22-github-action-hero-shohei-ueda/)
- [Compose 404](https://codepen.io/imathis/pen/ZYMmLx)
