# Jupyter Books

This page will eventually include various approaches to building Jupyter Books.

So far, the rest of this page summarizes one approach to making Jupyter books using Jupyter Book 2.0 in Windows. Content is created in Markdown (and ipnb) files, and the book will be displayed online as HTML. The result will be a GitHub-based website looking like https://fhmjones.github.io/index.html. 

**Note** that the "normal approach" to displaying websites in your GitHub account works fine (see [https://pages.github.com/](https://pages.github.com/)) but requires correct and complete HTML and related files (i.e. you would have to write in HTML). Furthermore, it does NOT work to simply generate a Jupyter book from your markdown, then transfer the resulting HTML to your `username.github.io/` repo.

**Parts not yet written:**

- Writing, and the parts needed for including navigation
- Working with **[jb_tools](https://github.com/eoas-ubc/jb_tools/blob/master/tools_demo/Readme_conda.md)**.
- Markdown for Jupyter books


## 1. Setting up environments and working spaces

### 1.1 The Environment

The necessary conda environment file must be in the root directory, eg. `mywindocs.yml`:

```bash
name: win-docs
channels:
  - default
  - conda-forge
  - eoas_ubc
dependencies:
  - python=3.7.*
  - sphinx=2.4.4
  - pip
  - runjb
  - git
  - pandas
  - matplotlib
  - pip:
    - jupyter-book>=0.7.0b
```

NOTE: I am not at all sure this is the best environment for these purposes, but it is working for me in September 2020.

Set up this environment:

```bash
conda env create -f mywindocs.yml
conda activate windocs
```

This should only need to be done once.

### 1.2 Install [ghp-import](https://pypi.org/project/ghp-import/)

```bash
pip install ghp-import
```

### 1.3 Where to put working and resulting files

Build documentation in a repo OTHER than your `username.github.io/` repo. Continuing the example above: eg. https://github.com/fhmjones/FJ-ocesedocs. Working in the master branch may not be "best practice" but is OK for now.

This documentation repo is where documentation files will be edited, where JupyterBooks will be run to convert to HTML, and where results can be tested. There should be `README.md` and `LICENSE` files. A `.gitignore` file is recommended to prevent all the HTML and related files being sent when you `push` to GitHub. When satisfied, and local/remote repos are synchronized, [ghp-import](https://pypi.org/project/ghp-import/) is used to send. To summarize:

1. Write documentation locally using Markdown (possibly including code in `.ipnb` files) in a repo dedicated to the purpose. Manage GitHub version control normally.
1. Use Jupyterbooks to generate the HTML and book structure within that repo.
1. Copy resulting web materials to your local clone of your repo `username.github.io`.
1. Use `ghp-import` from the root of that local repo to ship web display files to your GitHub `username.github.io` repo.
1. The website is then found using a URL like https://fhmjones.github.io/index.html.

Details for steps 2-4 are below. 

## 2. Building a Jupyter Book

If you would like to work with a clean build, you can delete the build folder's contents "by hand", or empty it by running:

```bash
jb clean docs/
```

If jupyter execution is cached, this command will not delete the cached folder.

To remove the build folder (including `cached` executables), you can run:

```bash
jb clean --all docs/
```

Make the book by running the following command in your terminal:

```bash
jb build docs/
```

The  resulting contents of the `docs/_build` folder will be copied to GitHub `username.github.io` repo (next section), but test it locally first by opening the local `index.html` file that should be in the `docs/_build/html` folder.

## Publishing the Jupyter Book online

Publish to your own `username.github.io` repo so it can be checked by you or others. The first two steps are needed once. After this setup, regular "publishing" is done starting at step 3.

1. The `ghp-import` utility should have been installed (above).
2. Set a remote `upstream` as

   ```bash
   git remote add upstream https://github.com/username/username.github.io
   ```

3. The last step is to send the folder with all HTML and associated materials (images, CSS, etc.) that was generated using `jb build` to the `master` branch at `username.github.io` using the following. Do this on the command line from the "root" of this repo.

   ```bash
   ghp-import -f --no-jekyll -p -b master docs/_build/html -r upstream
   ```

## Notes

If the eventual location is elsewhere then the book contents should be shared with the other location's owner so they can (a) generate the HTML using JupyterBooks, then carry out the `ghp-import` step, or whatever other approach they use, or (b) share the whole HTML (etc.) package for more direct deployment.
