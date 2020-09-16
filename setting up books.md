# OCESE documentation book

How to set up for bookmaking in Windows using Jupyter Book 2.0.

## Creating an Conda Environment

The conda environment is provided as `environment_ocesewin.yml`. This environment is used for all testing by Github Actions and can be setup by:

`1. conda env create -f environment_ocesewin.yml`

This should only need to be done once - I think?

`2. conda activate ocesedocs_win`

## Building a Jupyter Book

Run the following command in your terminal:

```bash
jb build docs/
```

If you would like to work with a clean build, you can empty the build folder by running:

```bash
jb clean docs/
```

If jupyter execution is cached, this command will not delete the cached folder.

To remove the build folder (including `cached` executables), you can run:

```bash
jb clean --all docs/
```

## Publishing this Jupyter Book

??Is this true? This repository is published automatically to `gh-pages` upon `push` to the `master` branch.

## Notes

This repository is used as a test case for [jupyter-book](https://github.com/executablebooks/jupyter-book) and a `requirements.txt` file is provided to support this `CI` application.
