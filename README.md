# NorthCode Vault

This is our shared knowledge Vault. **This is a public repository so do not share any confidential information here!**

## Authoring new posts

Creating new pages is really easy. Everything is stored inside the [docs](docs) directory as Markdown files. Content should be organized in directories such that none of the posts are at the top level.  If you need a new top-level directory for your content, then just create one. This will appear as an item in the top navigation menu. Remember to add a file called `index.md` too if needed.

_Internal linking is encouraged!_ Create normal relative Markdown links to other posts as needed.

If you want to add a notification you can use [admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types) like this:

```
!!! note
    This is a notification
```

## Keeping track of topics

If you have an idea but don't have the time to write about it right now, you should create a new issue. New issues appear automatically in the [topic tracking project](https://github.com/TheProjectAurora/vault/projects/1), and they are also automatically marked as Done when closed. If you reference an issue in a pull request (e.g. `Closes #1` or `Resolves #2`) then merging the PR will automatically close the related issue.

## Implementation details

The website is generated with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/). It is published on GitHub Pages using GitHub Actions with the [deployment script](.github/workflows/deploy.yml). Basic configuration is done with the [mkdocs.yml](mkdocs.yml) file and theme overrides are located in the [theme](theme) directory.

You can build the site locally by installing the Python requirements and running the local development server:

```
python3 -m venv venv
. venv/bin/activate
python3 -m pip install -r requirements.txt
mkdocs serve
```
