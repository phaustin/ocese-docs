# Documentation sequence, starting from scratch.

Here is a list of the documentation that should be included in the "Basic Skills" section.

1. Introduction  
   - An outline (list) of the components.
   - Summary of the reason for providing documentation in this order.
2. Working at the command line and Powershell  
   - Draw from first half of [Andrew's writeup](https://github.com/AndrewLoeppky/crash_course/blob/master/coding_crash_course.md).
   - This needs shortening to 'point form' for brevity.
   - See also PA's [numeric course page](https://phaustin.github.io/numeric/doc_notebooks/course_bootstrap/python.html).
   - Text editing: minimal options, but recommend & justify VS-Code.
   - Markdown: initial basics only.
3. Setting up conda and "environments".
    - [Here](https://protostar.space/why-you-need-python-environments-and-how-to-manage-them-with-conda) is an easy-to-read reference about "why" environments.
    - Use miniconda (install [miniconda via conda installation docs](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)):
        - Adapt instructions from [Numeric Course](https://phaustin.github.io/numeric/doc_notebooks/course_bootstrap/installing_jupytext.html). 
        - Original source for [miniconda installers](https://docs.conda.io/en/latest/miniconda.html) for iOS, Windows, Linux. 
    - For the environment, start with "numeric.yml" from PA's numerical course. 
        - Here is a [direct link to the yml file](https://github.com/phaustin/numeric_students/blob/downloads/utils/numeric.yml): 
        - Put it somewhere (eg. A repos folder), cd to that folder then run: 
                conda env create -f numeric.yml
        conda activate numeric
4. Git and github introduction
    - Draw from second half of [Andrew's writeup](https://github.com/AndrewLoeppky/crash_course/blob/master/coding_crash_course.md).
    - Shortening for brevity, and maybe add subtitles for clarity.
    - Also borrow from PA's numeric course. 
5. Github workflows, starting with simple "solo" workflow and moving up to a collaborative pull-request workflow. The [preliminary summary of git workflow options](gh-etc.html) includes:
    -  Solo no branching workflow
    - The simplest use of GitHub as a repository for your own work only
        - Clone to your local computer 
        - Solo with branch and merge to manage your own development of features. 
    - Sharing but with no branching (not ideal).
    - Fork & Pull Workflow.
6. Building a [Jupyter Book](https://jupyterbook.org/intro.html)
    - Installation
    - Writing, and the parts needed for including navigation
    - Testing: first locally, then send to your own GitHub for web-display
    - Markdown for Jupyter books
