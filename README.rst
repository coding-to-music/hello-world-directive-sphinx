Hello World Sphinx
===================

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

.. helloworld::

Some more text here...
The sample above would generate:

Some intro text here...

Hello World!

Some more text here...

.. code-block:: 
    :linenos:
    cd html
    python3 -m http.server
    http://0.0.0.0:8000/
