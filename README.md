# Andrea Muolo

My personal GitHub website. If you like it, please give it a star.


## Table Of Contents

  * [Getting started](#getting-started)
  * [Installation](#installation)
  * [Deployment](#deployment)
  * [Features](#features)
    + [Publications](#publications)
    + [Collections](#collections)
    + [Other features](#other-features)
      - [Theming](#theming)
      - [Layout](#layout)
      - [Social media previews](#social-media-previews)
      - [Atom (RSS-like) Feed](#atom-rss-like-feed)


## Getting started

Want to learn more about Jekyll? Check out [this tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/).
Why Jekyll? Read [Andrej Karpathy's blog post](https://karpathy.github.io/2014/07/01/switching-to-jekyll/)!

This theme allows to create blog posts in the [distill.pub](https://distill.pub/) style.
It also supports fast math typesetting through [MathJax](https://www.mathjax.org/).
Photo formatting is made simple using [Bootstrap's grid system](https://getbootstrap.com/docs/4.4/layout/grid/).


## Installation

Assuming you have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/) installed on your system, do the following:

```bash
$ cd <repo-name>
$ bundle install
$ bundle exec jekyll serve
```

The theme is ready for customization.

<details><summary> <strong>Including rows of images</strong></summary>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>
```

</details>

---


## Deployment

Deploying your website to [GitHub Pages](https://pages.github.com/) is the most popular option.
This repository will automatically re-deploy your webpage each time you push new changes to your repository! :sparkles:

1. Rename your repository to `<your-github-username>.github.io` or `<your-github-orgname>.github.io`.
2. In `_config.yml`, set `url` to `https://<your-github-username>.github.io` and leave `baseurl` empty.
3. Click on **Actions** tab and **Enable GitHub Actions**; do not worry about creating any workflos as everything has already been set for you.
4. Make changes, commit, and push!
5. Wait for a few minutes and let the action complete. You can see the progress in the **Actions** tab. If completed successfully, in addition to the 'master' branch, your repository should now have a newly built 'gh-papges' branch. 
6. Finally, in the **Settings** of your repository, in the Pages section, set the branch to `gh-pages` (**NOT** to `master`).
7. After deployment, the webpage will become available at `<your-github-username>.github.io`.

For more details, see [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source).


<details><summary> <strong>Manual deployment to GitHub Pages</strong></summary>

If you need to manually re-deploy your website to GitHub pages, run the deploy script from the root directory of your repository:
```bash
$ ./bin/deploy
```
uses the `master` branch for the source code and deploys the webpage to `gh-pages`.

</details>

<details><summary> <strong>Deployment to another hosting server (non GitHub Pages)</strong></summary>

If you decide to not use GitHub Pages and host your page elsewhere, simply run:
```bash
$ bundle exec jekyll build
```
which will (re-)generate the static webpage in the `_site/` folder.
Then simply copy the contents of the `_site/` foder to your hosting server.

**Note:** Make sure to correctly set the `url` and `baseurl` fields in `_config.yml` before building the webpage. If you are deploying your webpage to `your-domain.com/your-project/`, you must set `url: your-domain.com` and `baseurl: /your-project/`. If you are deploing directly to `your-domain.com`, leave `baseurl` blank.

</details>

---


## Features

### Publications

The publications page is generated automatically from your BibTex bibliography.
Simply edit `_bibliography/papers.bib`.
You can also add new `*.bib` files and customize the look of your publications however you like by editing `_pages/publications.md`.

<details><summary> <strong>Buttons (through custom bibtex keywords)</strong></summary>

There are several custom bibtex keywords that you can use to affect how the entries are displayed on the webpage:

- `abbr`: Adds an abbreviation to the left of the entry. You can add links to these by creating a venue.yaml-file in the _data folder and adding entries that match.
- `abstract`: Adds an "Abs" button that expands a hidden text field when clicked to show the abstract text
- `arxiv`: Adds a link to the Arxiv website (Note: only add the arxiv identifier here - the link is generated automatically)
- `bibtex_show`: Adds a "Bib" button that expands a hidden text field with the full bibliography entry
- `html`: Inserts a "HTML" button redirecting to the user-specified link
- `pdf`: Adds a "PDF" button redirecting to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `supp`: Adds a "Supp" button to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `blog`: Adds a "Blog" button redirecting to the specified link
- `code`: Adds a "Code" button redirecting to the specified link
- `poster`: Adds a "Poster" button redirecting to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `slides`: Adds a "Slides" button redirecting to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `website`: Adds a "Website" button redirecting to the specified link
- `altmetric`: Adds an [Altmetric](https://www.altmetric.com/) badge (Note: only add the altmetric identifier here - the link is generated automatically)

You can implement your own buttons by editing the bib.html file.

</details>

---

### Collections

This Jekyll theme implements `collections` to organize the work into categories. There are two default collections: `news` and `projects`.
Items from the `news` collection are automatically displayed on the home page.
Items from the `projects` collection are displayed on a responsive grid on projects page.

For customizations, edit the collections in the `_config.yml` file, create a corresponding folder, 
and create a landing page for your collection, similar to `_pages/projects.md`.

---

### Other features

This theme uses github-readme-stats to display GitHub repositories and user stats on the the `/repositories/` page.

Edit the `_data/repositories.yml` and change the `github_users` and `github_repos` lists to include your own GitHub profile and repositories to the the `/repositories/` page.

#### Theming

The default is purple, but you can quickly change it by editing the
`--global-theme-color` variable in the `_sass/_themes.scss` file.
Other color variables are listed there as well.
The stock theme color options available can be found at `_sass/variables.scss`.
You can also add your own colors to this file assigning each a name for ease of use across the template.

#### Social media previews

The theme supports preview images on social media.
To enable this functionality you will need to set `serve_og_meta` to `true` in your `_config.yml`.
Once you have done so, all your site's pages will include Open Graph data in the HTML head element.

You will then need to configure what image to display in your site's social media previews.
This can be configured on a per-page basis, by setting the `og_image` page variable.
If for an individual page this variable is not set, then the theme will fall back to a site-wide `og_image` variable, configurable in your `_config.yml`.
In both the page-specific and site-wide cases, the `og_image` variable needs to hold the URL for the image you wish to display in social media previews.

#### Atom (RSS-like) Feed

It generates an Atom (RSS-like) feed of your posts, useful for Atom and RSS readers.
The feed is reachable simply by typing after your homepage `/feed.xml`.






