# MRO Website Documentation

[![Docs Status](https://github.com/UWMRO/website-docs/actions/workflows/docs.yml/badge.svg)](https://github.com/UWMRO/website-docs/actions/workflows/docs.yml)

This repository contains documentation for observing at Manastash Ridge Observatory. The documentation can be accessed [here](https://uwmro.github.io/website-docs/index.html).

## Writing documentation

Documentation in this site is built using [Sphinx](https://www.sphinx-doc.org/en/master/), but you don't need to know much about it to write and edit pages. Documentation can be written using either [Markdown](https://www.markdownguide.org) or [reStructuredText (reST)](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html). Both allow to format plan text, add links, etc. Markdown is arguably simpler and well supported by GitHub, but `reST` is a bit more powerful and can be useful if you want to show auto-generated API documentation in Python.

Regardless of what language you choose, you can create a file in `docs/` with you new documentation (or edit an existing one) with extension `.md` if you're using Markdown, or `.rst` is using `reST`. You can create the file in a clone or fork of the repository, or directly in GitHub. Edit the file with any content you want to add, then commit the file (remember to use a commit message that's descriptive of what you changed!) This will trigger an automatic rebuild of the documentation (see below for details) and, after about a minute, the changes will be published [here](https://uwmro.github.io/website-docs/index.html).

If you have created a new page and want to add it to the table of contents, edit the file [docs/index.rst](https://github.com/UWMRO/website-docs/blob/main/docs/index.rst) and add the name of your page to the `toctree`. For example, if you created a new file `docs/evora.md` add `evora` under the `toctree` section (make sure you keep the same indentation)

```rst
.. toctree::
  :maxdepth: 2

  ...
  evora
  ...
```

You can use directories under `docs/`. If you created a file `docs/some_stuff/stuff1.md` add `some_stuff/stuff1` in the `toctree`.

### Writing documentation with `nox`

If you want to write a lot of documentation, it may be helpful to use a [nox](https://nox.thea.codes/en/stable/) server that will rebuild the documentation every time you save the file. For that, first clone the repository

```console
git clone git@github.com/uwmro/website-docs
```

and install the package dependencies

```console
cd website-docs
pip install .
```

Finally, run the `nox` server from the root of the repository

```console
nox
```

That will build the documentation and open a new window in your browser with the website that will be refreshed every time you modify a file. Then use the normal [Git commands](https://education.github.com/git-cheat-sheet-education.pdf) to commit and push changes.

## Deploying the documentation

Every time that you push a change to the repository the documentation is automatically rebuilt and deployed to [GitHub Pages](https://pages.github.com). [This](https://coderefinery.github.io/documentation/gh_workflow/) is basically how it works.

TL;DR when a change to the repository is detected, a GitHub workflow runs that installs Python, runs Sphinx, builds the documentation, and copies the resulting static HTML pages to the [gh-pages](https://github.com/UWMRO/website-docs/tree/gh-pages) branch.

When you make and push a change, you can check the [Actions](https://github.com/UWMRO/website-docs/actions) page to see your change beeing processed. Sphinx is quite resilient to problems in the code, but if the action fails, something has gone wrong and the static site may be broken. Be sure to fix that if it happens. You can also check the badge at the top of this page to see if the action is working properly.

After the action runs (which should take 30 seconds), a [deployment](https://github.com/UWMRO/website-docs/actions) actually updates the GitHub Pages for the documentation. Then you can go [here](https://uwmro.github.io/website-docs/index.html) to confirm the changes look fine.
