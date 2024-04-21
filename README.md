# jupyter-book-example


## Setup

```sh
conda create -n jbook-env python=3.10
conda activate jbook-env
```

```sh
pip install -r requirements.txt
```



## Managing the Book


The following command was used to create the structure for this book:

```sh
jupyter-book create example-book
```

### Building



Build book as LaTeX (see "example-book/_build/latex):

```sh
jupyter-book build example-book/ --builder latex
```


Build book as PDF (see "example-book/_build/latex/book.pdf):

```sh
jupyter-book build example-book/ --builder pdflatex
```

Build book as HTML: (see "example-book/_build/html/index.html"):

```sh
#jupyter-book build example-book/
jupyter-book build example-book/ --builder html
```
