Using a python directive (simple python program) to do or say anything, such as "Hello World"
===============================================================================================

Following these instructions:
https://www.sphinx-doc.org/en/master/development/tutorials/helloworld.html

Steps:

Here is what needs to be done:: 

    mkdir hello-world-sphinx
    cd hello-world-sphinx
    sphinx-quickstart
    create source/_ext
    Create an _ext folder in source

Create a new Python file in the _ext folder called helloworld.py

modify conf.py
:: 

    import os
    import sys

    sys.path.append(os.path.abspath("./_ext"))

    extensions = ['helloworld']

You can now use the extension in a file. For example:

Some intro text here...

use the following directive anywhere and it will get expanded by the python program

.. code-block:: 
:directive:

    `::helloworld::`

Some more text here...
The sample above would generate:

Some intro text here...

Hello World!

Some more text here...

edit the file index.rst, which uses the directive, and view the generated index.html:: 

    make html
    cd build/html
    python3 -m http.server
    http://0.0.0.0:8000/

This bug report shows how to publish on github.io 

https://github.com/sphinx-doc/sphinx/issues/3382

suhailvs commented on Jul 30, 2018
update of @wxianxin ::

    Create an empty .nojekyll file in the root folder to turn off Jekyll.
    Create an index.html file in the root folder with contents:
    <meta http-equiv="refresh" content="0; url=./_build/html/index.html" />
    Run make html then add, commit and push the repo.
    In the GitHub Pages box in the project Settings page, choose to use master branch.
    Visit https://<username>.github.io/<repo>

The page should be viewable at https://coding-to-music.github.io/hello-world-directive-sphinx
