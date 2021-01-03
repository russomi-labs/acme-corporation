# acme-corporation

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)
- [Contributing](../CONTRIBUTING.md)

## About <a name = "about"></a>

📖 [Hugo in Action](https://github.com/hugoinaction/hugoinaction) teaches you to build and host your own fully customizable static website with the Hugo engine.

> A basic website for a company named Acme Corporation. Acme Corporation is a leading manufacturer of shapes like lines, circles, squares and triangle in digital form in the planet. We will be using an existing Hugo theme and start with understanding how to add content to a Hugo website.

Hugo skeleton generated by the hugo new command:

``` bash
❯ tree -C
.
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

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See [deployment](#deployment) for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them.

``` bash
# Install Hugo
brew install hugo

# Install Tree
brew install tree
```

### Installing

A step by step series of examples that tell you how to get a development env running.

Say what the step will be

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

## Usage <a name = "usage"></a>

- How to use...

## Resources

- [Compose 404](https://codepen.io/imathis/pen/ZYMmLx)
