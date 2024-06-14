# Evidence Bench

This cookiecutter creates a simple boilerplate for a Jupyter Book.

## Usage

### Building the book

If you'd like to develop and/or build the Evidence Bench book, you should:

1. Clone this repository
2. Run `pip install -r requirements.txt` (it is recommended you do this within a virtual environment)
3. (Optional) Edit the books source files located in the `evidence_bench/` directory
4. Run `jupyter-book clean evidence_bench/` to remove any existing builds
5. Run `jupyter-book build evidence_bench/`

A fully-rendered HTML version of the book will be built in `evidence_bench/_build/html/`.

### Hosting the book

NOTE: This has already been setup for the EvidenceBench website, all that needs to be done after editing the page, is to push to the main branch, which will start a Github Action (around 1 minute or so). After that action has been completed, the page should be updated.

Please see the [Jupyter Book documentation](https://jupyterbook.org/publish/web.html) to discover options for deploying a book online using services such as GitHub, GitLab, or Netlify.

For GitHub and GitLab deployment specifically, the [cookiecutter-jupyter-book](https://github.com/executablebooks/cookiecutter-jupyter-book) includes templates for, and information about, optional continuous integration (CI) workflow files to help easily and automatically deploy books online with GitHub or GitLab. For example, if you chose `github` for the `include_ci` cookiecutter option, your book template was created with a GitHub actions workflow file that, once pushed to GitHub, automatically renders and pushes your book to the `gh-pages` branch of your repo and hosts it on GitHub Pages when a push or pull request is made to the main branch.

### Additional Info

- The `_toc.yml` file is how the page is structured, the list in that file is the table of contents that is displayed on the navbar on the left of the page.

- To make a new page, make a new markdown file, and add a new file to the table of contents.

- To view changes without pushing to github, you can build the book on your local machine using the `clean` and `build` commands under `jupyter-book`. If the cleaning step is skipped, it can cause buggy behavior.

## Contributors

We welcome and recognize all contributions. You can see a list of current contributors in the [contributors tab](https://github.com/philiphan0109/evidence_bench/graphs/contributors).

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [executablebooks/cookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).