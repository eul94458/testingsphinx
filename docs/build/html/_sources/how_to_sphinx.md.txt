# How to Sphinx

- [installation](#installation)

- [brief walkthrough](#brief-walkthrough)

- [build the website](#build-the-website)

- [markdown rendering](#markdown-rendering)

- [change theme](#change-theme)

## Reference

- [Link to Read the Doc guide (recomended)](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html)

- [Link to the Official guide](https://www.sphinx-doc.org/en/master/usage/quickstart.html)

(#installation)=
## Installation

- [Link to Official installation guide](https://www.sphinx-doc.org/en/master/usage/installation.html)

Following the instruction given by the above link.

> pip install --update sphinx

Hence you should be able to call sphinx directly from the terminal.

(#brief-walkthrough)=
## Brief walkthrough

Create a new folder for tutorial

> mkdir sphinx_test

> cd sphinx_test

Then launch the sphinx tutorial

> sphinx-quickstart

It should ask you some questions about the project name or version, author name etc.  Just input anything, it doesn't matter. You can change any of those afterward anyway.

After that, there should be some new files created under the **~/sphinx_test** directory. Open **conf.py** using a text editor and you can see those information you are asked to input are stored here.

This is the configuration file. Assign global variables to configure Sphinx's internel modules. Also to setup parser of markdown, extensions to use, etc.

Return to the **~/sphinx_test** directory, there is another file call **index.rst**. Again, open it with a text editor.

This is the index page of this project's website. It is witten in reStructuredText format. Sphinx will render these text when you build the website.

You may see below thing within the text

        .. toctree::
           :maxdepth: 2

"toc" stands for Table Of Content. Literally it is what it is. It will later be rendered into a hyperlinked content page. So lets do something to it.

Return to the **~/sphinx_test** directory, make a new text file call "new.rst".

Then insert below code and save it.

        New Document
        ============

        This is a new document.

Go back to **index.rst**, insert the name of the previous new file under the toctree like this

        .. toctree::
           :maxdepth: 2

           new

Remind you that new lines matter in rst format. Sphinx parse stuffs be new line. If you are no inserting new lines between every function and class, error will occur.

(#build-the-website)=
## Build the website

Let's render a static html website.

Type these into your terminal. Script has been written to the folder by previous `sphinx-quickstart`, so just use that.

> make html

The website rendered is under **/sphinx_test/_build/html/index.html**. Open that with a browser and have a look at it.


## Auto Reload

It is cumbersome to rebuild the website every time you make some new arrangement. Why not just automatize this work.

First install `sphinx-autobuild`. Input below code in the terminal

> pip install sphinx-autobuild

You see the file structure of the **/sphinx_test** directory is this. You have a bunch of source file, and you build a html webpage base on those source. So what `sphinx-autobuild` is trying to do is, keep tract of any changes happen in the source file, then re-rendered that to the webpage. Therefore we have to provide it 2 basic information

        1. Directory of source file

        2. Directory of output webpage

In our case, they are

        1. ~/sphinx_test

        2. ~/sphinx_test/_build/html

Therefore, input below code into the terminal

> sphinx-autobuild  ~/sphinx_test ~/sphinx_test/_build/html

There it will start a server at `http://127.0.0.1:8000`. Open a browser and put `http://127.0.0.1:8000` into the address line to check for it.

(#markdown-rendering)=
## Markdown Rendering

Sphinx do support in Markdown, however, through a extension.

First you have to install the library that parse Markdown language

> pip install --upgrade myst-parser

Then in the **/sphinx_test/conf.py**, modify extensions entry

    extensions = ['myst_parser']

The reference syntax in markdown using Spinx is slightly different. Check this out.
[Link to markdown referencing tutorial](https://docs.readthedocs.io/en/stable/guides/cross-referencing-with-sphinx.html)

(#change-theme)=
## Change Theme

There is many different theme you can use on your website.

- [Link to the Sphinx theme gallery](https://sphinx-themes.org/#themes)

First you install the favor theme, then modify the conf.py to apply the theme. For example

in terminal

> pip install sphinx-book-theme

in /sphinx_test/conf.py

    html_theme = 'sphinx_book_theme'

