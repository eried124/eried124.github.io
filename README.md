The documentation site is built using the static site generator [mdBook](https://github.com/rust-lang/mdBook) book and hosted as a static GitHub Page.

Markdown source files are located in `/src/book` and the sidebar navigation/chapter list is specified in `/src/SUMMARY.md`

The static published files are built to the `/docs` folder (valid GitHub Pages source directories are either the project root `/` or `/docs` ).

## Building

Building the book:

```
mdbook build
```

Running the book on a local webserver (`localhost:3000`) and rebuilding on file changes:

```
mdbook serve
```

