# GEMINI.md

## Project Overview

This repository contains a Jekyll-based academic website for the "Innovation Analytics Lab". The site is built using the Academic Pages template, which is a fork of the Minimal Mistakes theme.

The website features several content types, including:
- Publications
- Talks
- Teaching materials
- Portfolio items
- Blog posts

Content is written in Markdown, and the site's structure and configuration is managed through Jekyll's standard directory structure and `_config.yml` file.

## Building and Running

### Prerequisites

- Ruby and Bundler
- Node.js and npm

### Running the Site Locally

To run the site on your local machine for development, follow these steps:

1.  **Install Ruby dependencies:**
    ```bash
    bundle install
    ```

2.  **Serve the site:**
    ```bash
    bundle exec jekyll liveserve
    ```
    This will start a local server at `http://localhost:4000`. The site will automatically rebuild and refresh when you make changes to the source files.

### Building JavaScript Assets

The project uses npm to manage JavaScript dependencies and build scripts. To minify the JavaScript assets, run:

```bash
npm run build:js
```

This command is typically run once before deploying the site or when JavaScript source files have been updated.

## Development Conventions

### Content Management

The website's content is organized into Jekyll collections, located in the following directories:

- `_posts/`: For blog posts.
- `_publications/`: For academic publications.
- `_talks/`: For presentations and talks.
- `_teaching/`: For teaching materials.
- `_portfolio/`: For portfolio items.
- `_pages/`: For static top-level pages (e.g., About, Contact).

To add new content, create a new Markdown file in the appropriate directory.

### Creating and Linking Pages

To create a new static page:

1.  Create a new `.md` or `.html` file in the `_pages/` directory (e.g., `_pages/my-new-page.md`).
2.  Add YAML Front Matter to the top of the file to define its properties, like `title` and `permalink`.

    ```yaml
    ---
    permalink: /my-new-page/
    title: "My New Page"
    ---

    This is the content of my new page, written in Markdown.
    ```

To link to this new page from any other page or post, use Jekyll's `link` tag to ensure the URL is generated correctly. This is the most robust method and avoids broken links if the site's `baseurl` changes.

**Example:**

```markdown
You can find more information on [My New Page]({% link _pages/my-new-page.md %}).
```

### Adding Navigation Items

To add a new item to the site's main navigation bar:

1.  Open the `_data/navigation.yml` file.
2.  Locate the `main:` section.
3.  Add a new entry with a `title` and `url`. The `url` should correspond to the `permalink` of an existing page or an external link.

    **Example:**

    ```yaml
    main:
      - title: "About"
        url: /about/
      - title: "My New Page"
        url: /my-new-page/
      - title: "External Site"
        url: https://example.com
    ```

### Key Elements of a YAML Header (Front Matter)

The YAML header, also known as Front Matter, is a block of YAML at the beginning of your Markdown or HTML files. It defines metadata for the page, which Jekyll uses to render the site. The block is delimited by triple-dashed lines (`---`).

Here are some key elements you'll commonly find:

-   **`layout`**: (Required for pages using a layout) Specifies the layout file (e.g., `default`, `single`, `archive`) from the `_layouts` directory that Jekyll should use to wrap your content.
    *   Example: `layout: single`

-   **`title`**: (Recommended) The title of your page, which will often be displayed prominently on the page and in the browser tab.
    *   Example: `title: "About Me"`

-   **`permalink`**: (Recommended for custom URLs) Defines the URL structure for your page. If omitted, Jekyll generates a URL based on the file path.
    *   Example: `permalink: /about/`

-   **`author_profile`**: (Common in this theme) A boolean (true/false) that controls whether the author's profile (defined in `_data/authors.yml` and `_config.yml`) is displayed on the page.
    *   Example: `author_profile: true`

-   **`date`**: (Common for posts and dated content) The date associated with the content, used for sorting and display. Format is typically `YYYY-MM-DD HH:MM:SS +/-TTTT`.
    *   Example: `date: 2024-01-15 10:00:00 -0500`

-   **`modified`**: (Optional) A date indicating when the content was last modified.
    *   Example: `modified: 2024-03-20`

-   **`excerpt`**: (Optional) A short summary of the page's content, often used in listings or RSS feeds.
    *   Example: `excerpt: "A brief overview of my professional background."`

-   **`share`**: (Common in this theme) A boolean that controls the display of social sharing buttons on the page.
    *   Example: `share: true`

-   **`comments`**: (Common in this theme) A boolean that controls the display of comments section on the page.
    *   Example: `comments: true`

**Example YAML Header:**

```yaml
---
layout: single
title: "My Research Interests"
permalink: /research-interests/
author_profile: true
date: 2023-11-01
modified: 2024-02-28
excerpt: "Exploring my current research areas and ongoing projects."
share: true
comments: false
---
```

### Automated Content Generation

The `markdown_generator/` directory contains Python scripts and Jupyter notebooks to automate the creation of Markdown files for publications and talks. These scripts read data from TSV files (`publications.tsv` and `talks.tsv`) and generate the corresponding `.md` files in the `_publications/` and `_talks/` directories.

To use these scripts, you will need Python and the necessary libraries installed. See the `markdown_generator/readme.md` for more details.

### Configuration

The main configuration file for the site is `_config.yml`. This file contains settings for the site's title, description, author information, and other global parameters. When you modify this file, you will need to restart the Jekyll server for the changes to take effect.
