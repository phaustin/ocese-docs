# Conda & environments

Setting up Conda and "environments". To include:

- [Here](https://protostar.space/why-you-need-python-environments-and-how-to-manage-them-with-conda) is an easy-to-read reference about "why" environments.
- Use miniconda (install [miniconda via conda installation docs](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)):
  - Adapt instructions from [Numeric Course](https://phaustin.github.io/numeric/doc_notebooks/course_bootstrap/installing_jupytext.html). 
  - Original source for [miniconda installers](https://docs.conda.io/en/latest/miniconda.html) for iOS, Windows, Linux. 
- For the environment, start with "numeric.yml" from PA's numerical course. 
  - Here is a [direct link to the yml file](https://github.com/phaustin/numeric_students/blob/downloads/utils/numeric.yml): 
  - Put it somewhere (eg. A repos folder), cd to that folder then run:

```bash
    conda env create -f numeric.yml
    conda activate numeric
```