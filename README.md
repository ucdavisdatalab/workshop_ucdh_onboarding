# A guide to UC Davis Medical Center information technology services for UC Davis researchers

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

_[UC Davis DataLab](https://datalab.ucdavis.edu/)_  
_Fall 2025_  
_Instructor: Wesley Brooks_  
_Maintainer: Wesley Brooks <<wbrooks@ucdavis.edu>>_  

* [Reader](https://ucdavisdatalab.github.io/workshop_ucdh_onboarding/)

This guide is intended to explain how to connect to technology services that are provided by UC Davis Health (UCDH). The tech systems used by UCDH are almost completely separate from those used by the Davis campus, and there are additional data security methods implemented to protect the human patients and subjects that are involved in medical data. 

## Learning Goals

After completing this workshop, learners should be able to:

- Request new services from the UCDH ServiceNow catalog
- Connect to the UCDH VPN
- Request and connect to a virtual machine using ACE
- Get CITI training for how to handle medical data

## Contributing

The course reader is a live webpage, hosted through GitHub, where you can enter
curriculum content and post it to a public-facing site for learners.

To make alterations to the reader:
	  
1.  Check in with the reader's current maintainer and notify them about your 
    intended changes. Maintainers might ask you to open an issue, use pull 
    requests, tag your commits with versions, etc.

2.  Run `git pull`, or if it's your first time contributing, see
    [Setup](#setup).

3.  Edit an existing chapter file or create a new one. Chapter files may be 
    either Markdown files (`.md`) or Jupyter Notebook files (`.ipynb`). Either 
    is fine, but you must remain consistent across the reader (i.e. don't mix 
    and match filetypes). Put all chapter files in the `chapters/` directory.
    Enter your text, code, and other information directly into the file. Make 
    sure your file:

    - Follows the naming scheme `##_topic-of-chapter.md/ipynb` (the only 
      exception is `index.md/ipynb`, which contains the reader's front page).
    - Begins with a first-level header (like `# This`). This will be the title
      of your chapter. Subsequent section headers should be second-level
      headers (like `## This`) or below.

    Put any supporting resources in `data/` or `img/`.

4.  Run the command `jupyter-book build .` in a shell at the top level of the
    repo to regenerate the HTML files in the `_build/`.

5.  When you're finished, `git add`:
    - Any files you edited directly
    - Any supporting media you added to `img/`

    Then `git commit` and `git push`. This updates the `main` branch of the
    repo, which contains source materials for the web page (but not the web
    page itself).

6.  Run the following command in a shell at the top level of the repo to update
    the `gh-pages` branch:
    ```
    ghp-import -n -p -f _build/html
    ```
    This uses the [`ghp-import` Python package][ghp-import], which you will
    need to install first (`pip install ghp-import`). The live web page will
    update automatically after 1-10 minutes.

[ghp-import]: https://github.com/c-w/ghp-import


## Setup

### Python Packages

We recommend using [conda][] to manage Python dependencies. The `env.yaml` file
in this repo contains a list of packages necessary to build the reader. You can
create a new conda environment with all of the packages listed in that file
with this shell command:

```sh
conda env create --file env.yaml
```

[conda]: https://docs.conda.io/en/latest/
