# devx.pw

This is the repo where the [devx.pw](https://devx.pw) is built from

## prerequisites

All are optional, only rquired if you want to run `mkdocs` locally.

* vscode + vscode remote docker extension + docker: run mkdocs inside a container
* without docker: `pip install -r requirements.txt`

## Development (writing the webpages)

0. [Optional, Recommended] Open vscode using the suppllied devcontainer
1. create a `.md` inside the `docs/docs` folder.
2. Add a reference to it at `docs/mkdocs.yml` -> `theme.nav`
3. [Optional, Recommended] Run `cd docs && mkdocs serve` for a live preview.
4. Commit + Push
5. Github actions take care of the deployment
