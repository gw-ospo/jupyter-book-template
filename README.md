# jupyter-book-example

This repository demonstrates a working implementation of [Jupyter Book](https://jupyterbook.org/), hosted on GitHub Pages, with automated deployments setup via GitHub Actions.

For more context about this process, or if you would like to start from scratch to setup your own book, consult the official [Jupyter Book Tutorial](https://jupyterbook.org/en/stable/start/your-first-book.html).

Otherwise, if you'd like to build on top of this template repository, follow the instructions below.

## Setup

[Make a copy](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) of this template repository.

Then clone your copy of the repository onto your local computer, and navigate there from the command line.

Setup a project-specific virtual environment, if you like that kind of thing (otherwise use an existing environment):

```sh
# using python 3.10 for example, but you can choose a different version if you'd like:
conda create -n jbook-env python=3.10
conda activate jbook-env
```

Install packages:

```sh
# install just the jupyer book package into your environment:
pip install jupyter-book

# consider alternatively leveraging the requirements file:
#pip install -r requirements.txt
```

## Managing the Book

### Initialization

The following command was used to create the structure for this book (where "example-book" was chosen as the name of the book):

```sh
jupyter-book create example-book

# consider alternatively:
#jupyter-book create --cookiecutter example-book
```

If you have created a copy of this repository, you won't need to repeat this initialization step.

### Building

> NOTE: the commands below assume your book is named "example-book", however if you choose a different book name, you'll need to update the commands accordingly

> NOTE: there are some contents in the [".gitignore" file](/.gitignore) which ignore certain artifacts from the build process from version control. If you choose a different book name, you may want to update the contents of your ".gitignore" file accordingly

Build book as LaTeX (see "example-book/_build/latex"):

```sh
jupyter-book build example-book/ --builder latex
```

Build book as PDF (see ["example-book/_build/latex/book.pdf"](/example-book/_build/latex/book.pdf)):

```sh
jupyter-book build example-book/ --builder pdflatex
```

Build book as HTML: (see "example-book/_build/html/index.html"):

```sh
jupyter-book build example-book/ --builder html
```

### Deployment

For more context, see the [Jupyter Book GitHub Pages Guide](https://jupyterbook.org/en/stable/publish/gh-pages.html).

In your GitHub repository's settings, under "pages" settings, configure GitHub Pages, specifically choosing to deploy from "GitHub Actions" source.

> NOTE: the [".github/workflows/deploy-book.yml"](/.github/workflows/deploy-book.yml) file controls the build process. If you use your own book name, customize "example-book" to refer to the book name you chose.

Commit and push to trigger an automated build of your HTML site. Visit the hosted site at your repository's GitHub Pages URL.
