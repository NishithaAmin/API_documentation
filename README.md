# WM ESB Team Internal API Documentation
This repository contains the code necessary to build the static content Internal API Documentation website.

It is built using a tool called [MkDocs](http://www.mkdocs.org).

### MkDocs Installation<sup>[1](#myfootnote1)</sup>

In order to install MkDocs you'll need Python installed on your system, as well as the Python package manager, pip. You can check if you have these already installed like so:

```bash
$ python --version
Python 2.7.2
$ pip --version
pip 1.5.2
```

MkDocs supports Python 2.6, 2.7, 3.3, 3.4 and 3.5.

On Windows we recommend that you install Python and pip with [Chocolatey](https://chocolatey.org/).

Install the mkdocs package using pip:

```bash
pip install mkdocs
```

You should now have the `mkdocs` command installed on your system. Run `mkdocs --version` to check that everything worked okay.

```bash
$ mkdocs --version
mkdocs, version 0.15.3
```

<sup><a name="myfootnote1">1</a></sup>_installation information sourced from [here](http://www.mkdocs.org/#installation)_

### Writing documentation
MkDocs comes with a built-in web server that lets you preview your documentation as you work on it. We start the web server by making sure we're in the same directory as the `mkdocs.yml` config file, and then running the `mkdocs serve` command:

```bash
$ mkdocs serve
Running at: http://127.0.0.1:8000/
```

Open up http://127.0.0.1:8000/ in your browser, and you'll see the index page being displayed.  The web server also supports auto-reloading, and will rebuild your documentation whenever anything in the configuration file, documentation directory or theme directory changes.

### Publishing the documentation
_content coming soon..._
